# Fake-Review-Bounty-Hunter
---
# Credit Card Fruad Detection
![](https://img.shields.io/github/last-commit/shivamshinde123/Fake-Review-Bounty-Hunter)
![](https://img.shields.io/github/languages/count/shivamshinde123/Fake-Review-Bounty-Hunter)
![](https://img.shields.io/github/languages/top/shivamshinde123/Fake-Review-Bounty-Hunter)
![](https://img.shields.io/github/repo-size/shivamshinde123/Fake-Review-Bounty-Hunter)
![](https://img.shields.io/github/directory-file-count/shivamshinde123/Fake-Review-Bounty-Hunter)
![](https://img.shields.io/github/license/shivamshinde123/Fake-Review-Bounty-Hunter)

A  system to detect and flag suspicious or fake reviews on platforms like Yelp using machine learning, NLP, and graph algorithms. The project combines ETL pipelines, database design, review-pattern detection, and an interactive frontend to show the detected patterns.

## Detailed Documentation

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/shivamshinde123/Fake-Review-Bounty-Hunter)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Code Structure](#code-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Technical Details](#technical-details)
- [Sample Workflow](#sample-workflow)
---

## Overview

**Fake-Review-Bounty-Hunter** automates the process of ingesting raw Yelp review data, preprocessing and storing it Neo4j, and provides a web frontend for users and admins to detect fake or suspicious review patterns.

Key objectives:
- Load, filter, and save reviews, users, and businesses data.
- Provide a Streamlit web app for authentication, review submission, and automatic pattern detection.
- Detect fake reviews using NLP, semantic embeddings, and graph-based logic.

---

## Features

- **ETL Pipeline:** From raw Yelp JSON to clean relational data in PostgreSQL.
- **Streamlit Frontend:** User signup/login, review submission, and instant feedback on suspicious activities.
- **Fake Review Detection:**
    - Duplicate review detection across businesses (Sentence-Transformers)
    - Sentiment/text and rating consistency (Transformers + custom logic)
    - Rating deviation and temporal review bursts
    - Age-inappropriate content checks
- **Neo4j Integration:** For efficient graph pattern queries and visualization.
- **Pluggable Evaluation Metrics:** Customizable, extensible pattern identification.

---

## Code Structure

```
Fake-Review-Bounty-Hunter/
│
├── Project_Demo/                  # Demo notebooks or presentations
├── test_phase/
│   ├── src/
│   │   ├── data_preprocessing/    # ETL and data loading scripts
│   │   │   ├── data_loader.py
│   │   │   ├── etl.py
│   │   └── webapp/                # Streamlit app and detection modules
│   │       ├── login_and_signup.py
│   │       ├── sentiment_analysis.py
│   │       ├── neo4j_db_operations.py
│   │       ├── age_and_time_related_patterns.py
│   │       ├── sentiment_rating_consistency.py
│   │       ├── duplicate_review_across_businesses.py
│   │       ├── rating_deviation_pattern.py
│   │       └── Images/
│   └── data/
│       ├── processed/             # Processed CSV data
│       └── raw/                   # Raw Yelp JSON data
├── requirements.txt               # Dependency list
├── README.md                      # README file
└── .gitignore
```

---

## Installation

1. **Clone the repository:**
   ```
   git clone https://github.com/shivamshinde123/Fake-Review-Bounty-Hunter.git
   cd Fake-Review-Bounty-Hunter
   ```

2. **Create a Python virtual environment:**
   ```
   python -m venv venv
   source venv/bin/activate  # (Windows: venv\Scripts\activate)
   ```

3. **Install dependencies:**
   ```
   pip install -r requirements.txt
   ```

4. **Set up PostgreSQL and Neo4j:**
   - Ensure local PostgreSQL and Neo4j services are running.
   - Add environment variables (`SQL_ENGINE`, `JDBC_URL`, Neo4j credentials) in a `.env` file.

---

## Usage

1. **Run ETL scripts to ingest Yelp data:**
    - Use scripts in `test_phase/src/data_preprocessing/` to process data and populate the database.

2. **Launch Streamlit web app:**
   ```
   streamlit run test_phase/src/webapp/login_and_signup.py
   ```
   - Use the dashboard for user registration, login, review posting, and automatic flagging.

---

## Technical Details

- **Key Libraries:**
    - `streamlit`, `transformers`, `sentence-transformers`, `pandas`, `neo4j`, `torch`, `scikit-learn`, etc.
- **Pattern Detection:**
    - Embedding-based similarity search for duplicate reviews
    - Sentiment analysis for rating/text mismatch
    - Temporal/spatial analysis for review burstiness
    - Age restriction logic for reviews
- **Databases:**
    - **PostgreSQL:** Tabular data storage and analytics
    - **Neo4j:** Graph modeling and suspicious pattern queries

---

## Sample Workflow

1. Load and preprocess Yelp data with ETL scripts.
2. Start the Streamlit dashboard, sign up or log in as a user.
3. Submit a review through the web UI.
4. The system automatically scans for duplicate content, inconsistent ratings, burst patterns, and inappropriateness, alerting the user/admin as necessary.

---



