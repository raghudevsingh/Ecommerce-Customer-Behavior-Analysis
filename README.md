# E-Commerce Customer Behavior Analysis & Purchase Prediction

## 📌 Project Overview

This project analyzes online shopping session behavior and uses machine learning to predict whether a visitor will make a purchase.

The project combines **Exploratory Data Analysis (EDA)**, **Supervised Machine Learning**, and **Unsupervised Learning** to understand customer behavior and identify meaningful visitor segments.

---

## 🎯 Objectives

- Analyze online shopping behavior
- Identify factors associated with purchase intent
- Explore customer/session behavior using EDA
- Predict whether a shopping session will result in a purchase
- Segment visitors based on browsing behavior
- Identify important features influencing purchase prediction

---

## 📊 Dataset

**Dataset:** UCI Online Shoppers Purchasing Intention Dataset

The original dataset contains:

- 12,330 shopping sessions
- 18 columns
- 17 input features
- 1 target variable: `Revenue`

After removing duplicate sessions, the project uses **12,205 records**.

### Target Variable

`Revenue`

- `0` → No purchase
- `1` → Purchase

---

## 🔍 Exploratory Data Analysis

The project analyzes:

- Visitor type
- Monthly purchase behavior
- Weekend vs weekday purchasing
- Administrative page activity
- Informational page activity
- Product-related page activity
- Bounce rates
- Exit rates
- Page values
### 📊 Project Visualizations

#### Purchase Distribution
![Purchase Distribution](images/purchase_distribution.png)

#### Monthly Purchase Rate
![Monthly Purchase Rate](images/monthly_purchase_rate.png)

#### Feature Importance
![Feature Importance](images/feature_importance.png)

#### ROC Curve
![ROC Curve](images/roc_curve.png)

#### Visitor Segmentation
![Visitor Segmentation](images/customer_segments.png)
### Key EDA Findings

- New visitors showed a higher purchase rate than returning visitors.
- Weekend sessions had a slightly higher purchase rate than weekday sessions.
- Purchasing sessions showed higher product-related browsing activity and duration.
- Purchasing sessions had lower bounce and exit rates.
- `PageValues` showed a strong relationship with purchase behavior.

---

## 🤖 Machine Learning

### Models Used

#### 1. Logistic Regression

Used as a baseline classification model.

#### 2. Random Forest

Used as the primary classification model because it captures nonlinear relationships between behavioral features.

Class imbalance was considered during model training using `class_weight="balanced"`.

---

## 📈 Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 85.13% | 51.64% | 78.53% | 62.31% | 0.9110 |
| **Random Forest** | **90.05%** | **74.39%** | 55.50% | **63.57%** | **0.9253** |

### Final Model

**Random Forest**

It achieved:

- **90.05% Accuracy**
- **74.39% Precision**
- **63.57% F1-Score**
- **0.9253 ROC-AUC**

Logistic Regression achieved higher recall, which means it identified more actual purchasing sessions, while Random Forest provided better overall precision and ROC-AUC.

---

## 🌲 Feature Importance

The Random Forest model identified the following among the most important features:

1. PageValues
2. ExitRates
3. ProductRelated_Duration
4. ProductRelated
5. BounceRates
6. Administrative_Duration
7. Administrative
8. Month_Nov
9. TrafficType
10. Region

These results indicate that visitor engagement and product-related browsing behavior are important for predicting purchase intent.

---

## 👥 Customer Segmentation

K-Means clustering was used to identify behavioral groups.

### Optimal Number of Clusters

The number of clusters was evaluated using the **Silhouette Score**.

The best result was obtained with:

**K = 3**

Silhouette Score:

**≈ 0.453**

### Identified Segments

#### Cluster 0 — Low-Engagement Visitors

- Very low product browsing
- Short product-related browsing duration
- High bounce and exit rates
- Very low purchase rate

#### Cluster 1 — Moderate/Regular Shoppers

- Moderate product browsing
- Moderate browsing duration
- Lower bounce and exit rates
- Moderate purchase activity

#### Cluster 2 — Highly Engaged Shoppers

- High product-page activity
- Long product-related browsing duration
- Low bounce and exit rates
- Highest PageValues
- Highest purchase rate

### Key Segmentation Insight

Highly engaged visitors showed substantially higher purchase rates than low-engagement visitors.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab
- UCI Machine Learning Repository

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Feature Engineering
   ↓
Categorical Encoding
   ↓
Train/Test Split
   ↓
Machine Learning
   ├── Logistic Regression
   └── Random Forest
   ↓
Model Evaluation
   ↓
Feature Importance
   ↓
K-Means Customer Segmentation
   ↓
Business Insights
