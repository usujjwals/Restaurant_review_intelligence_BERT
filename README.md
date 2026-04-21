# Restaurant Review Intelligence: NLP & Sentiment Analysis

This project analyzes competitor restaurant reviews in the Sacramento fried chicken market using **NLP, sentiment analysis, topic modeling, EDA, and time series analysis**. The main goal was to turn customer review text into actionable business insights for market positioning and competitive benchmarking.

## Data Source
The dataset was built from **original Yelp business reviews scraped with Apify**. We collected multiple raw CSV exports, merged them, cleaned them in Python, and removed duplicates to create a final analysis-ready dataset. The final dataset includes **11,215 deduplicated reviews** across **10 competitor restaurants**, with review text, ratings, dates, reviewer information, and business details. 

## Project Focus: NLP & Sentiment Analysis
The core of this project is **sentiment analysis on review text**.

We applied a full NLP workflow, including:
- text cleaning with regex
- lowercasing and stopword removal
- WordNet lemmatization
- removal of restaurant names to reduce brand bias
- n-gram extraction (bigrams, trigrams, and 4-grams)
- word cloud analysis
- topic modeling with LDA

For sentiment modeling, we compared two approaches:
- **VADER** for rule-based sentiment classification
- **Hugging Face transformer-based BERT/DistilBERT sentiment analysis** for context-aware classification

This comparison helped us measure how traditional lexicon-based sentiment differs from deep learning-based sentiment. The transformer model captured more mixed and complaint-heavy reviews, making it more useful for business interpretation. 

## Key Outcomes
- Most reviews were positive overall, but **BERT detected more negative sentiment than VADER**, showing that it was better at identifying nuanced dissatisfaction. 
- The two models **disagreed on 1,619 reviews**, which showed the value of comparing lexicon-based and transformer-based methods. 
- The biggest recurring complaint themes were **customer service, wait times, and consistency**. 
- The most important food-related terms in customer language were **fried chicken** and **mac & cheese**, making them key drivers of restaurant perception. 
- Topic modeling showed that the market conversation centers around **Southern comfort food, soul food sides, hot chicken, and service quality**. 
- Time series analysis suggested that the market grew sharply after 2020 and is now beginning to stabilize, indicating a maturing but still competitive space. 

## Files Included
- `Business Case Data Analysis.pdf` — data collection, preprocessing, and cleaning summary
- `Competitive_Market_Analysis_Report.docx.pdf` — final report with results and business recommendations
- `EDA - MSBA212_GP (1).ipynb` — exploratory data analysis and descriptive review patterns
- `nlpsentimentalfinal.ipynb` — main NLP and sentiment analysis notebook using **VADER** and **Hugging Face transformer sentiment modeling**
- `MSBA212 GP Topic Modeling.ipynb` — LDA topic modeling workflow
- `Time_Series_Analysis.ipynb` — review trend and ARIMA forecasting
- `1.csv`, `2.csv`, `3.csv` — raw scraped review exports
- `finaldataset.csv` / `finaldataset (1).csv` — cleaned final dataset used for analysis 

## Tools & Libraries
Python, Pandas, NLTK, Scikit-learn, Hugging Face Transformers, Matplotlib, Seaborn, and Apify
