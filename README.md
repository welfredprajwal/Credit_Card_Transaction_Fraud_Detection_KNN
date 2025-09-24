# Credit Card Transaction Fraud Detection
# Overview

This project applies the K-Nearest Neighbors (KNN) algorithm to detect fraudulent credit card transactions. By analyzing transaction patterns and identifying similarities with past data, the model classifies transactions as Fraudulent (1) or Legitimate (0).

KNN works by finding the k closest neighbors to a given transaction and predicting its class based on the majority vote among neighbors. The performance depends on the choice of k and the distance metric used.

# Dataset

The dataset consists of anonymized credit card transactions with numerical features derived using PCA (Principal Component Analysis).

| Feature | Description                                                                       |
| ------- | --------------------------------------------------------------------------------- |
| Time    | Seconds elapsed between this transaction and the first transaction in the dataset |
| V1–V28  | PCA-transformed numerical features to preserve confidentiality                    |
| Amount  | Transaction amount                                                                |
| Class   | Label (0 = Legitimate, 1 = Fraudulent)                                            |

# Methodology

1. Data Preprocessing

    Handle class imbalance (fraud cases are very rare) using undersampling/oversampling (SMOTE)

    Normalize transaction amount and features

    Split dataset into training and testing sets

2. Model Training (KNN)

    Choose an optimal value of k

    Train using Euclidean distance (or other distance metrics)

    Leverage nearest neighbors to classify each transaction

3. Evaluation

    Evaluate with metrics:

    Accuracy
  
    Precision

    Recall

    F1-Score

    Confusion Matrix

# Process

1.Load and preprocess data

    Separate features (Time, V1–V28, Amount) and target (Class).

    Normalize features (StandardScaler) so that KNN distance works properly.

    Handle imbalance

    Fraud cases are very rare (<0.2% of data).

    Use SMOTE oversampling or undersample majority class for balance.

2.Train-Test Split

    Split into 70% training, 30% testing.

    Train KNN

    Fit with an optimal k (usually between 3–7).

3.Evaluate

    Compute confusion matrix, accuracy, precision, recall, F1-score, ROC-AUC.
    

# Results

| Metric    | Score (Example) |
| --------- | --------------- |
| Accuracy  | 94%             |
| Precision | 92%             |
| Recall    | 89%             |
| F1-score  | 90%             |
| ROC-AUC   | 0.95            |
