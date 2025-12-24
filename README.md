# 🏨 Hanoi Hotel Review Dataset for ABSA

[![Task](https://img.shields.io/badge/Task-Aspect_Based_Sentiment_Analysis-green.svg)]()
[![Language](https://img.shields.io/badge/Language-Vietnamese-red.svg)]()
[![Size](https://img.shields.io/badge/Size-20k_Samples-blue.svg)]()
[![License](https://img.shields.io/badge/License-CC_BY_4.0-orange.svg)]()

This repository hosts the **Hanoi Hotel Review Dataset**, a large-scale corpus collected from major online travel agencies, specifically focusing on hotels in Hanoi. 

This dataset was introduced and utilized in our research paper: **"COL-TransGCN: A Syntax-Aware Graph Convolutional Network with Contrastive Ordinal Learning for Aspect-Based Sentiment Analysis on Vietnamese Hotel Reviews"**.

It is designed to address the linguistic challenges of Vietnamese social media text, including teencode, slang, and complex syntactic structures.

---

## 📊 Dataset Statistics

The dataset comprises **20,076** samples, partitioned into Training, Validation, and Testing sets using a stratified **8:1:1** split strategy to ensure robust evaluation.

| Dataset Split | Sample Count | Percentage |
| :--- | :---: | :---: |
| **Train Set** | 16,062 | 80% |
| **Validation Set** | 2,007 | 10% |
| **Test Set** | 2,007 | 10% |
| **Total** | **20,076** | **100%** |

---

## 🏷️ Annotation Schema

Each review is annotated at the aspect level across **10 distinct categories**. The sentiment polarity for each aspect follows a **5-level ordinal scale**.

### 1. Aspects
1.  🛏️ **Room**
2.  💁 **Service**
3.  📍 **Location**
4.  💸 **Price**
5.  🍽️ **Food & Beverage**
6.  wf **Amenities**
7.  ✨ **Cleanliness**
8.  🚕 **Transportation**
9.  📋 **Policy**
10. 🧩 **Others**

### 2. Sentiment Scale (Ordinal)
* `+2`: **Very Positive** (Strongly recommend)
* `+1`: **Positive** (Satisfied)
* ` 0`: **Neutral** (No opinion / Average)
* `-1`: **Negative** (Dissatisfied)
* `-2`: **Very Negative** (Strongly complain)

> **Note:** If an aspect is not mentioned in the review text, it is assigned a `Null` or empty label.

---

## 📂 Data Format

The data is stored in `.csv` format with the following structure:

* **`data`**: The raw text of the user review.
* **`aspect_name`**: The ground truth sentiment label for that specific aspect.

**Example View:**

| data | room | service | location | ... |
| :--- | :---: | :---: | :---: | :---: |
| "Good location near the market, but the AC was broken." | -1 | 0 | +2 | ... |
| "Staff was super friendly. Highly recommended!" | 0 | +2 | 0 | ... |

---

## 🚀 Benchmark Results

This dataset serves as the benchmark for the **COL-TransGCN** model. The performance on the **Test Set** is as follows:

| Model | F1-Score | Accuracy | Precision | Recall |
| :--- | :---: | :---: | :---: | :---: |
| **COL-TransGCN** | **83.5%** | **85.6%** | **83.4%** | **85.6%** |
