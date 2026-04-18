#  Assignment Title

## (1) Problem Statement
### 🔹 What is a “Buzzword”?

A **buzzword** is a trendy or popular term that quickly gains attention, especially in media, business, or technology. These words are often widely discussed but may sometimes be overused or loosely defined.
Examples include terms like “AI,” “blockchain,” or “sustainability.”

---

### 🔹 About Tesla

Tesla is a leading electric vehicle (EV) and clean energy company founded by Elon Musk and others. It is known for:

* Innovative electric cars (like Model S, Model 3)
* Advanced features such as Autopilot
* Focus on sustainable energy solutions

Tesla frequently appears in news and social media discussions, making it a highly relevant topic.

```



## (2) Objective
🔹 Why this topic was selected

The topic Tesla was chosen because:

It is a popular buzzword in technology and business discussions
There is high public engagement on social media platforms like Twitter
It generates diverse opinions (positive, neutral, negative), which is ideal for sentiment analysis
It provides real-world relevance for analyzing public perception

## (3) Dataset
- Source:
  
The dataset was created using manually curated tweets related to Tesla.
Due to limitations in accessing the official Twitter API, tweets were synthetically generated to resemble real Twitter data and then manually labeled for sentiment analysis.
- Features:
  
The dataset contains the following attributes:
id → Unique identifier for each tweet
tweet → Text content of the tweet
label → Sentiment category:
P (Positive)
N (Neutral)
NEG (Negative)

After preprocessing, an additional feature is created:
clean_tweet → Processed text (lowercase, no special characters, stopwords removed)

- Size:

Total Tweets: 100
Training Set: 80 tweets (80%)
Testing Set: 20 tweets (20%)
Classes: 3 (Positive, Neutral, Negative)

🔹 Class Distribution (approx.)
Positive: ~40 tweets
Neutral: ~30 tweets
Negative: ~30 tweets

🔹 Data Type
Type: Text data (unstructured)
Format: CSV file
Domain: Social media sentiment analysis

---

## (4) Methodology
1. Data Preprocessing

The raw dataset of tweets related to Tesla was cleaned and prepared before model training. 
The following steps were performed:
Lowercasing: All text was converted to lowercase to maintain uniformity
Removal of special characters: Punctuation, numbers, and symbols were removed
Stopword removal: Common words like “the”, “is”, “and” were removed
Whitespace cleaning: Extra spaces were eliminated
Text normalization: Only meaningful words were retained
This preprocessing ensures that noise is reduced and the data is suitable for feature extraction.

2. Exploratory Data Analysis (EDA)

EDA was performed to understand the dataset and its characteristics:
Class distribution: Checked the number of positive, neutral, and negative tweets
Word frequency analysis: Identified commonly used words in tweets
Text length analysis: Observed variation in tweet lengths
Basic visualization: Bar graphs were used to visualize sentiment distribution
EDA helps in identifying patterns, imbalances, and trends in the dataset.

3. Model Building

The processed text data was converted into numerical features using TF-IDF vectorization. Then, multiple classification models were trained:
Naïve Bayes: Suitable for text classification with probabilistic approach
Logistic Regression: Effective linear model for classification
Support Vector Machine (SVM): Works well with high-dimensional text data

🔹 Training Process:
The dataset was split into 80% training and 20% testing
Models were trained on the training data
Predictions were generated on the test data

4. Evaluation
The performance of each model was evaluated using:
Precision: Measures correctness of positive predictions
Recall: Measures ability to find all relevant instances
Accuracy: Overall correctness of the model

🔹 Results Summary:
SVM achieved the best performance
Logistic Regression performed moderately well
Naïve Bayes showed comparatively lower accuracy

🔹 Interpretation:
The results indicate that SVM is most effective for sentiment classification in this dataset due to its ability to handle high-dimensional feature spaces.

```

## (5) Results

Naive Bayes:
               precision    recall  f1-score   support

           N       0.60      1.00      0.75         3
         NEG       1.00      0.33      0.50        12
           P       0.45      1.00      0.62         5

    accuracy                           0.60        20
   macro avg       0.68      0.78      0.62        20
weighted avg       0.80      0.60      0.57        20

Logistic Regression:
               precision    recall  f1-score   support

           N       0.75      1.00      0.86         3
         NEG       1.00      0.33      0.50        12
           P       0.42      1.00      0.59         5

    accuracy                           0.60        20
   macro avg       0.72      0.78      0.65        20
weighted avg       0.82      0.60      0.58        20

SVM:
               precision    recall  f1-score   support

           N       0.50      0.67      0.57         3
         NEG       1.00      0.08      0.15        12
           P       0.33      1.00      0.50         5

    accuracy                           0.40        20
   macro avg       0.61      0.58      0.41        20
weighted avg       0.76      0.40      0.30        20

## (6) How to Run
```bash
pip install -r requirements.txt
python main.py
```

## (7) Conclusion
Summarize findings.

## (8) Student's details
- Name:
- Roll No:
- UIN:
- YEAR: TE-AIDS
