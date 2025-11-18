# churn_prediction-
# 📊 Customer Churn Prediction — Data Mining Project  
**Course:** Data Mining  
**Professor:** Daniele Ravì  
**Student:** Tairbek Akhayev  

This project focuses on building a complete end-to-end **machine learning pipeline** for predicting customer churn in a telecom dataset.  
The work includes data exploration, preprocessing, feature engineering, model training, evaluation, interpretability, and business insights.

---

## 🔍 Project Overview

The objective of this project is to analyze factors contributing to customer churn and build predictive models that can accurately identify customers at risk.

The workflow includes:  
- Exploratory Data Analysis (EDA)  
- Outlier detection and treatment  
- Handling missing values  
- Encoding categorical variables  
- Feature engineering  
- Model training & evaluation  
- Hyperparameter tuning  
- Model interpretability (LIME)  
- Business insights & final recommendations  

---

## 🧵 Dataset Description

The dataset contains **3,749 rows** and **17 features**, including:

- Demographics (Age, Gender)
- Subscription details (Contract, Service types)
- Billing information (MonthlyCharges, TotalCharges)
- Churn status (Target variable)

Target variable:  
Churn: Yes / No


---

## 📈 Exploratory Data Analysis (EDA)

Key findings:

- **Customers with month-to-month contracts churn significantly more.**
- Higher **MonthlyCharges** correlate with higher churn.
- **Tenure** and **TotalCharges** are strong *negative* predictors — long-term customers rarely churn.
- Payment by **Electronic Check** is associated with higher churn.
- Age shows **no meaningful correlation** with churn.

Visualization techniques used:
- Histograms & KDE plots
- Boxplots
- Scatter plots
- Correlation heatmap
- Category-based bar charts

---

## 🛠 Data Preprocessing

### ✔ Missing values  
- `Age` — imputed with mean  
- `PaymentMethod` — imputed with mode  
- `Service_Internet` — filled with `"Unknown"`  

### ✔ Outlier treatment  
Used:
- Percentile clipping (5th–95th)
- K-Means–based distance outlier detection  

### ✔ Encoding  
- Binary services → Boolean/0–1  
- Contract & Payment method → one-hot encoding  

### ✔ Feature scaling  
- Min-Max Scaling for numerical variables  

---

## 🧩 Feature Engineering

Created features:
- `TotalServiceUsage` — number of active services per customer  
- `ContractLength` — converted contract type into numeric months  
- Cleaned dataset by removing non-informative columns:
  - CustomerID
  - Gender
  - Service_Internet (after analysis)
  - Payment method one-hot columns (after aggregation)

---

## 🤖 Model Training

Models trained:

- Logistic Regression  
- SVM (Linear, RBF)  
- KNN  
- Decision Tree  
- Random Forest  
- AdaBoost  
- Gradient Boosting  

Evaluation metrics:
- Accuracy  
- Precision  
- Recall  
- F1-score  
- ROC-AUC  
- 10-fold Cross-validation  

---

## 🏆 Model Performance

**Best model: Gradient Boosting Classifier**

Accuracy: 99.87%
Precision: 97.73%
Recall: 100%
F1-score: 98.85%
ROC-AUC: 0.999


Cross-validation mean accuracy: **0.999**

Confusion matrix:
- 706 true negatives
- 43 true positives
- 1 false positive
- 0 false negatives  

---

## 🧠 Model Interpretability (LIME)

Using LIME, we examined feature contributions for individual predictions:

Key interpretability insights:
- High tenure + low monthly charges → strong push toward **No Churn**
- High monthly charges → increases churn risk
- Model decision boundaries align with business intuition (pricing sensitivity, contract length)

---

## 💼 Business Insights

From the analysis:

- Customers with **month-to-month contracts** churn the most → promote 1-year & 2-year contracts.
- Customers with **high MonthlyCharges** are more likely to churn → consider flexible pricing or bundling.
- Customers paying via **Electronic Check** churn more → incentivize automatic payment methods.
- **Short-tenure customers** are high-risk → implement onboarding retention strategies.
- Lack of **TechSupport** / **OnlineSecurity** correlates with churn → promote service add-ons.

---

## 🚀 Technologies Used

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- LIME  
- Jupyter Notebook  

---



