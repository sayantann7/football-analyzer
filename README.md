# Football Analyzer

This project analyzes international football results from 1872 to 2024. Using historical match data, the project aims to provide creative insights into international football trends and answer questions such as:

- **Who is the best team of all time?**
- **Which teams dominated different eras of football?**
- **What trends have there been in international football throughout the ages?**
  - Home advantage trends  
  - Total goals scored over time  
  - Distribution of teams' strength  
- **Geopolitical insights from football fixtures:**
  - How has the number of participating countries changed over time?  
  - Which teams frequently play each other?  
- **Hosting Analysis:**
  - Which countries host the most matches where they do not participate?  
  - How much does hosting a major tournament help a country's performance?  
- **Friendlies Analysis:**
  - Which teams are most active in playing friendlies, and does this help or hurt their overall performance?

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Features & Analyses](#features--analyses)
  - [Advanced Elo Rating System](#advanced-elo-rating-system)
  - [Dominance by Era](#dominance-by-era)
  - [Trends Over Time](#trends-over-time)
  - [Geopolitical Insights](#geopolitical-insights)
  - [Hosting Analysis](#hosting-analysis)
  - [Friendlies Analysis](#friendlies-analysis)
- [Usage](#usage)
- [Installation & Setup](#installation--setup)
  
## Overview

The Football Analyzer project leverages historical match data to derive multiple insights through advanced statistical and machine learning techniques. By incorporating an Elo rating system and additional feature engineering, the project goes beyond simple win-loss records to offer a deeper understanding of team performance, era dominance, and even geopolitics in international football.

## Dataset

The dataset covers international football match results from 1872 to 2024. Key columns include:
- **date:** Date of the match  
- **home_team:** Name of the home team  
- **away_team:** Name of the away team  
- **home_score:** Goals scored by the home team  
- **away_score:** Goals scored by the away team  
- **tournament:** Type of tournament (e.g., FIFA World Cup, Friendly, UEFA Euro, etc.)  
- **city:** City where the match took place  
- **country:** Country where the match took place  
- **neutral:** Indicates whether the match was played at a neutral venue (True/False)

For convenience, the dataset is downloaded directly from Kaggle using Kaggle CLI (or kagglehub) within the notebook.

## Features & Analyses

### Advanced Elo Rating System

- **Objective:** Rank teams over time using a dynamic Elo rating system that updates based on match outcomes.
- **Features:**  
  - Incorporates home advantage  
  - Tracks rating evolution over time  
  - Filters to include teams with more than a given number of matches (e.g., >800 or >500 matches per era)

### Dominance by Era

- **Objective:** Identify which teams dominated each decade.
- **Approach:**  
  - Compute win percentages per team for each decade  
  - Only consider teams with a sufficient number of matches (e.g., more than 500 matches in that decade)  
  - Output the best team per decade based on win percentage

### Trends Over Time

- **Home Advantage:** Analyze how the average home score difference has changed over time.
- **Goals Scored:** Plot the average total goals per match by year.
- **Team Strength Distribution:** Visualize the distribution of all-time win percentages.

### Geopolitical Insights

- **Participation Trends:** Examine the number of unique teams (a proxy for participating countries) per year.
- **Matchup Frequencies:** Identify the most frequent head-to-head matchups between teams.

### Hosting Analysis

- **Non-Participating Hosts:** Determine which countries host the most matches where they do not participate.
- **Major Tournament Advantage:** Analyze whether hosting a major tournament (e.g., FIFA World Cup) improves a host nation's performance.

### Friendlies Analysis

- **Friendlies Frequency:** Identify teams that play the most friendly matches.
- **Performance Correlation:** Investigate if there is any correlation between the number of friendlies played and overall team performance (e.g., Elo rating).

## Usage

This project is implemented as a Google Colab notebook. The notebook is structured into cells that:
1. Install and import libraries.
2. Download the dataset from Kaggle.
3. Clean and preprocess the data.
4. Compute advanced team statistics using an Elo rating system.
5. Perform various analyses and visualizations (dominance by era, trends, geopolitics, hosting, and friendlies).
6. Save outputs and provide summary visualizations.

## Installation & Setup

1. **Google Colab Setup:**
   - Open the notebook in Google Colab.
   - Upload your `kaggle.json` file (using `files.upload()`) to set up Kaggle API credentials.
   - Run the cells sequentially.

2. **Local Setup:**
   - Install the required packages:
     ```bash
     pip install kagglehub pandas matplotlib seaborn
     ```
   - Set up your Kaggle API credentials as described in the notebook.
   - Run the notebook cells in a Jupyter environment.
