# Customer Feedback Sentiment Analysis System

## 📖 Project Overview
This project is a complete **Customer Feedback Sentiment Analysis System** built using Natural Language Processing (NLP).
It classifies customer feedback into three sentiment categories:

- ✅ Positive
- ❌ Negative
- ⚪ Neutral

The system demonstrates a full NLP pipeline, comparing classical machine learning approaches and modern deep learning models.

---

## 🎯 Business Problem
Many companies receive large volumes of feedback from multiple channels such as:

- App reviews
- Customer support tickets
- Social media comments
- Product feedback forms

Manual analysis is:
- Time-consuming
- Inconsistent
- Not scalable

This project provides an automated solution for sentiment classification to support faster and more reliable decision-making.

---

## 👥 Target Users
- **Product Managers**: Track customer satisfaction and product issues
- **Support Teams**: Prioritize negative feedback quickly
- **Leadership Teams**: Monitor customer sentiment trends for business decisions

---

## 🧠 NLP Problem Framing
This is a **Text Classification Problem**:

- **Input:** Raw customer feedback text
- **Output:** Sentiment label (Positive / Negative / Neutral)

NLP is required because feedback is unstructured and often contains:
- Slang
- Emojis
- Spelling mistakes
- Sarcasm
- Context-based meaning

---

## 📂 Dataset
This project uses the **Twitter Sentiment Dataset**, which is suitable because:

- Tweets are short and informal (similar to real customer feedback)
- Data includes noise such as slang, emojis, and abbreviations
- Already labeled for sentiment classification

---

## ⚙️ Project Phases

### ✅ Phase 1 — Data Loading & Cleaning
- Load dataset from CSV
- Select relevant columns
- Remove missing values

---

### ✅ Phase 2 — Text Preprocessing (Classical NLP)
Preprocessing steps:
- Convert text to lowercase
- Remove URLs and special characters
- Remove stopwords
- Apply stemming using PorterStemmer

---

### ✅ Phase 3 — TF-IDF + Logistic Regression (Baseline Model)
TF-IDF converts text into numerical vectors.
A Logistic Regression classifier is trained on TF-IDF features.

**Performance:**
- Accuracy: ~84%
- Fast and interpretable

---

### ✅ Phase 4 — Word2Vec Based Model
- Train Word2Vec embeddings using Gensim
- Convert each sentence into a vector by averaging word vectors
- Train Logistic Regression model on embeddings

**Performance:**
- Accuracy: ~61%
- Captures semantic meaning but lacks contextual awareness

---

### ✅ Phase 5 — BERT Sentiment Model (Advanced)
Uses HuggingFace Transformers pipeline.

- Context-aware embeddings
- Minimal preprocessing required
- State-of-the-art performance

Example:
```python
from transformers import pipeline
bert_sentiment = pipeline("sentiment-analysis")
bert_sentiment("I love this product but the battery is bad")
