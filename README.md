# nhanes-kidney-screening-ml
# Explainable Machine Learning for Kidney Abnormality Screening Among Adults with Diabetes

## Project Overview

Diabetic kidney disease is a major complication of diabetes and may remain undetected until kidney function has declined. This project explores the use of explainable machine learning to identify kidney abnormalities among adults with diabetes using publicly available data from the National Health and Nutrition Examination Survey (NHANES).

The project uses demographic, clinical, laboratory and lifestyle information to develop and compare machine learning classification models. SHAP is used to interpret model predictions, and a Streamlit dashboard is planned as a research and educational demonstration.

**This project is for research and educational purposes only. It is not a clinical diagnostic tool.**

## Objectives

- Integrate and preprocess relevant NHANES datasets.
- Define a diabetes cohort and a kidney abnormality outcome.
- Explore data quality, missing values and population characteristics.
- Develop and compare Logistic Regression, Random Forest and XGBoost.
- Evaluate model performance using appropriate classification metrics.
- Interpret model predictions using SHAP.
- Develop a Streamlit research prototype and investigate subgroup performance where feasible.

## Dataset

**Source:** National Health and Nutrition Examination Survey (NHANES), conducted by the U.S. Centers for Disease Control and Prevention (CDC).

**Study cycle:** 2017–March 2020 pre-pandemic cycle.

The project uses relevant demographic, diabetes questionnaire, laboratory, examination and smoking questionnaire data. Datasets are linked using the participant identifier `SEQN`.

The analysis focuses on adults aged 20 years or older who meet the project's defined diabetes criteria.

## Outcome Definition

Kidney abnormality is defined as either:

- Estimated glomerular filtration rate (eGFR) below 60 mL/min/1.73 m², calculated using the race-free CKD-EPI 2021 creatinine equation.
- Urine albumin-to-creatinine ratio (UACR) of at least 30 mg/g.

Predictors used directly to construct the outcome, along with closely related kidney-function indicators, are excluded to reduce target leakage.

Because NHANES is cross-sectional, this study examines existing kidney abnormalities and associated predictive patterns rather than predicting future disease or establishing causality.

## Machine Learning Methods

The planned model comparison includes:

1. Logistic Regression
2. Random Forest
3. XGBoost

Model performance is assessed using ROC-AUC, precision, recall, F1-score and confusion matrices. SHAP is used for global feature importance and individual prediction explanations.

## Project Structure

```text
nhanes-kidney-screening-ml/
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
├── notebooks/
│   ├── 01_data_audit.ipynb
│   ├── 02_data_integration.ipynb
│   ├── 03_cohort_and_outcome.ipynb
│   ├── 04_eda.ipynb
│   ├── 05_modeling.ipynb
│   ├── 06_final_evaluation.ipynb
│   └── 07_explainability.ipynb
├── src/
├── app/
├── models/
├── reports/
├── docs/
├── requirements.txt
├── .gitignore
└── README.md
```

The directory structure may be updated as implementation progresses.

## Technologies

- Python
- Pandas and NumPy
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib and Seaborn
- Streamlit
- Jupyter Notebook

## Reproducibility and Data Access

NHANES data are publicly available through the CDC website:

https://wwwn.cdc.gov/nchs/nhanes/

Download the relevant files for the specified survey cycle. See the notebooks for the data-processing workflow and analysis steps.

Install the project's dependencies using:

```bash
pip install -r requirements.txt
```

Run the notebooks in numerical order after configuring the data paths and environment.

## Responsible Use and Limitations

- The dataset is cross-sectional and does not establish causality.
- The study outcome represents kidney abnormality according to the specified thresholds, not a confirmed diagnosis of chronic kidney disease.
- Missing data, cohort selection, class imbalance and subgroup representation may affect model performance.
- Model explanations describe learned predictive patterns and do not establish causal relationships.
- The model is intended for research and educational use, not clinical decision-making.





## Acknowledgements

We acknowledge the U.S. Centers for Disease Control and Prevention for providing public NHANES data for research and public-health analysis.
