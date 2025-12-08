
# **📘 Student Performance Prediction – Machine Learning Project**

This project implements an end-to-end machine learning pipeline to predict student academic outcomes (final grades) using the **UCI Student Performance Dataset**. The workflow includes data merging, preprocessing, feature engineering, RFE-based feature selection, model evaluation, and model explainability.

---

## **📂 Dataset**

* Two datasets used: **student-mat.csv** and **student-por.csv**
* Merged on **13 shared student attributes**
* Final merged dataset shape: **382 rows × 53 columns**

---

## **🔧 Data Preprocessing**

* Removed duplicates
* Handled missing values using mode/mean
* Converted all `"yes"` / `"no"` fields to binary
* Applied one-hot encoding to categorical variables
* Standardized all numeric features (except targets)
* Final cleaned dataset shape: **382 rows × 67 columns**

---

## **⚙️ Feature Engineering**

Created new derived features:

* `avg_grade_math`, `avg_grade_por`
* `avg_alcohol_math`, `avg_alcohol_por`

Saved processed dataset: **student_final_ready.csv**

---

## **🧪 Feature Selection (RFE)**

* Removed leakage features (`G1`, `G2`, `avg_grade` variables)
* Applied **Recursive Feature Elimination (RFE)**
* Selected **15 best features** for predicting:

  * `G3_math`
  * `G3_por`

Saved reduced datasets:

* **student_model_input_math.csv**
* **student_model_input_por.csv**

---

## **🤖 Models Trained**

All models evaluated using:

* **80/20 train–test split**
* **5-fold cross-validation**
* Pipelines with **StandardScaler**

Models:

* Linear Regression
* LASSO Regression
* Random Forest Regressor

---

## **📊 Results**

### **Math Prediction**

* **Best Model:** LASSO Regression
* **Test R²:** 0.153

### **Portuguese Prediction**

* **Best Model:** Linear Regression
* **Test R²:** 0.283

---

## **📈 Explainability**

* Coefficient plots for Linear and LASSO models
* Feature importance for Random Forest
* Residual analysis
* Performance banding created using R² quantiles

---

## **🛠️ Technologies Used**

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Plotly
* Scikit-learn

---

