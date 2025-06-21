# Credit Card Fraud Detection - Kaggle Dataset

This project aims to develop a classification model capable of identifying **fraudulent credit card transactions**. Detecting fraud accurately is crucial to protecting customers and financial institutions from financial loss and reputation damage.

To address this problem, we used the **Credit Card Fraud Detection** dataset from Kaggle, which presents a highly **imbalanced binary classification** challenge. The positive class (fraud) represents only 0.172% of all transactions.

The final model selected was the **XGBoost Classifier**, after comparing several algorithms and tuning hyperparameters. Its performance stood out especially in terms of **precision-recall trade-off**, which is essential in imbalanced datasets.

**Dataset link on Kaggle:**  
[Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

---

## About the Dataset

- 284,807 credit card transactions
- 492 fraudulent transactions (0.172%)
- Features V1–V28: Anonymized principal components from PCA
- `Time`: Seconds since the first transaction
- `Amount`: Transaction value
- `Class`: Target variable (`1` = fraud, `0` = legitimate)

---

## Access

- **Interactive notebooks, model results, and visualizations available locally.**
- **Model outputs and benchmarking tables included in reports.**

---

## Project Structure

```
├── .gitignore
├── README.md
|
├── data
│ └── creditcard.csv
|
├── notebooks
│ ├── 01_EDA.ipynb
│ ├── 02_Modeling.ipynb
|
├── src
│ ├── init.py
│ ├── config.py
│ ├── models.py
│ ├── graficos.py
│ └── plots.py
|
├── references
│ └── docs.md
|
├── relatorios
│ ├── results.html
│ └── imagens
```


---

## Modeling Approach

### Step-by-step:
1. **EDA:** Identified data imbalance, outliers, and feature distributions.
2. **Preprocessing:** Applied robust and power transformations to numerical columns.
3. **Model Comparison:** Benchmarked models like Logistic Regression, XGBoost, LGBM, etc.
4. **Feature Selection:** Used `permutation_importance` and XGBoost feature types (`weight`, `gain`, `cover`).
5. **Optimization:** Applied GridSearchCV to tune top-performing models.

### Final Model
- **XGBoostClassifier**
- `Average Precision`: **0.89**
- `ROC-AUC`: **0.986**
- Superior recall and precision for identifying rare fraud cases.

---

## Challenges

- Highly imbalanced dataset
- Confidential features with PCA-transformed data
- Balancing interpretability with performance

---

## Metrics Focus

Due to the severe class imbalance, we prioritized:
- **Average Precision (AUPRC)**
- **Recall** (false negatives are critical in fraud)
- **ROC-AUC**
