# Predicting Student Academic Performance Using Machine Learning

## 1. Project Overview

This project applies supervised machine learning techniques to predict students’ final academic performance based on demographic, social, and academic factors. The aim is to demonstrate the full machine learning workflow: data preparation, feature engineering, model selection, evaluation, and interpretation.

The project focuses on **regression**, predicting the final grade (`G3`) of secondary school students.

---

## 2. Problem Statement

Educational institutions often identify struggling students too late for effective intervention. This project addresses the following problem:

> Can a student’s final grade be accurately predicted using information available before the end of the academic year?

Solving this problem can support early-warning systems and targeted academic support.

---

## 3. Dataset

**Source:** UCI Machine Learning Repository – Student Performance Dataset
**Files used:** `student-mat.csv and student-por.csv`

**Dataset characteristics:**

* 395 student records
* 33 original features
* Mix of numerical and categorical variables
* Target variable: `G3` (final grade, range 0–20)

The dataset contains no missing values and is well-suited for supervised learning.

---

## 4. Data Preparation and Cleaning

The following steps were applied:

* Loaded the dataset using the correct delimiter (`;`)
* Verified data types and confirmed no missing values
* Performed exploratory analysis to understand distributions and relationships

No rows were removed, as the dataset was complete and consistent.

---

## 5. Feature Engineering

To improve predictive performance, additional features were created:

* **`past_grade_avg`**: Average of the first two grading periods (`G1` and `G2`)
* **`absence_rate`**: Absences normalized by study time
* **`failures_binary`**: Binary indicator of prior academic failure
* **`study_effort`**: Interaction between study time and past grades

Categorical variables were encoded using one-hot encoding with `drop_first=True` to reduce multicollinearity.

---

## 6. Models Used

The following models were implemented and compared:

1. **Linear Regression** – baseline, interpretable model
2. **Decision Tree Regressor** – captures non-linear relationships
3. **Random Forest Regressor** – ensemble model reducing overfitting
4. **Gradient Boosting Regressor** – sequential ensemble improving weak learners
5. **Tuned Random Forest** – optimized using GridSearchCV

---

## 7. Evaluation Metrics

Models were evaluated using:

* **R² Score** – proportion of variance explained
* **RMSE** – error magnitude
* **MAE** – average absolute prediction error

Cross-validation (5-fold) was applied where appropriate to assess generalization.

---

## 8. Key Findings

* Ensemble models significantly outperformed baseline models
* Previous academic performance (`G1`, `G2`, `past_grade_avg`) was the strongest predictor
* Absences and study time also had meaningful influence
* Hyperparameter tuning improved Random Forest performance and stability

---

## 9. Limitations

* The dataset is relatively small and country-specific
* Strong dependence on prior grades may limit early-stage prediction usefulness
* External factors such as teaching quality are not captured

---

## 10. Future Work

Possible improvements include:

* Framing the task as a classification problem (pass/fail)
* Testing additional datasets from other regions
* Deploying the model as an early-warning dashboard
* Applying explainability tools such as SHAP values

---

## 11. Conclusion

This project demonstrates how machine learning can be applied to educational data to generate actionable insights. Ensemble models, combined with thoughtful feature engineering, provide strong predictive performance and highlight key drivers of student success.
