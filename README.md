# Analyzing Income and Savings Behaviour Using Machine Learning
### Pakistan Findex 2025

## Overview

This project uses the World Bank Global Findex 2025 survey data for Pakistan
to predict whether an individual saved in the past year, and to identify
natural behavioural groups using clustering. The dataset contains 1,880 records
after augmentation, with 8 features including two engineered variables.

---

## Research Question

Is income the main factor that determines whether a person in Pakistan saves?

---

## Files

| File | Description |
|---|---|
| `Findex_Pakistan_2025_Improved.csv` | Cleaned, augmented, and feature-engineered dataset (1,880 rows, 9 columns) |
| `ML_Project_Improved.ipynb` | Full analysis notebook: EDA, model building, evaluation, clustering |

---

## Dataset

Source: World Bank Global Findex 2025, Pakistan module.

| Variable | Description |
|---|---|
| inc_q | Income quintile (1 = poorest, 5 = richest) |
| saved | Target variable: saved in past year (0 = No, 1 = Yes) |
| age | Age of respondent (15–79) |
| female | Gender (1 = Female, 2 = Male) |
| educ | Education level (1 = Primary, 2 = Secondary, 3 = Tertiary) |
| urbanicity | Residence (1 = Urban, 2 = Rural) |
| emp_in | Employment status (1 = Employed, 2 = Not Employed) |
| inc_educ | Engineered: income × education interaction |
| age_group | Engineered: age grouped into decades (1=15-24 to 5=55+) |

---

## How to Run

1. Clone the repository
2. Make sure both files are in the same folder
3. Install dependencies (see below)
4. Open `ML_Project_Improved.ipynb` in Jupyter and run all cells top to bottom

---

## Models Used

**Gradient Boosting Classifier**
- n_estimators = 200, max_depth = 6, learning_rate = 0.1
- Selected over Logistic Regression based on higher F1-score and recall

**K-Means Clustering**
- k = 3, selected using the Elbow Method
- Features: inc_q and saved (standardised)

---

## Results

| Metric | Score |
|---|---|
| Accuracy | 87.8% |
| Precision | 83.6% |
| Recall | 100.0% |
| F1-Score | 91.1% |
| CV Mean F1 (5-fold) | 89.9% |

**Key findings:**
- Age is the strongest predictor of savings behaviour (importance: 48.9%)
- Income and education together account for 27.5% of model importance
- K-Means identified 704 above-average-income individuals who do not save,
  showing income alone does not determine savings behaviour

---

## References

- Demirguc-Kunt et al., Global Findex Database 2021, World Bank, 2022
- Friedman, Gradient Boosting Machine, Annals of Statistics, 2001
- Chawla et al., SMOTE, JAIR, 2002
- Razzaq et al., Financial Inclusion Gaps in Pakistan, Scientific Reports, 2024
- Full reference list in the project report

---

## Dependencies
