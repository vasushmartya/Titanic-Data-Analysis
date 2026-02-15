# Titanic Survival Prediction 🚢

This project performs Exploratory Data Analysis (EDA) and builds a Machine Learning model to predict passenger survival on the Titanic using the Seaborn `titanic` dataset.

## 📊 Project Overview

The goal of this project is to determine which factors (age, gender, class, family size) most strongly influenced a passenger's chance of survival. We achieved a final model accuracy of **81.01%**.

## 🛠️ Data Processing & Feature Engineering

Before training the model, the data underwent several cleaning and transformation steps:

* **Missing Value Imputation**: Filled missing `age` values with the median and `embark_town` with the most frequent value (mode).
* **Feature Removal**: Dropped redundant columns like `deck`, `alive`, and `who` to reduce noise.
* **Family Size Engineering**: Combined `sibsp` and `parch` to create a `family_size` variable.
* **Binning**: Categorized family sizes into three groups: `Alone`, `Small`, and `Large`.

## 📈 Visual Insights

We utilized Seaborn to uncover patterns in the data:

* **Correlation Heatmaps**: Identified strong negative correlations between `pclass` and survival.
* **Survival by Family Size**: Discovered a "sweet spot" for survival in small families (2-4 members), while large families and solo travelers had lower survival rates.

## 🤖 Machine Learning Model

We implemented a **Random Forest Classifier** to handle the binary classification task.

### Model Configuration:

* **Features Used**: `pclass`, `fare`, `age`, `adult_male`, `family_category`
* **Encoding**: One-Hot Encoding for categorical variables.
* **Data Split**: 80% Training / 20% Testing.
* **Hyperparameters**: `n_estimators=100`, `max_depth=5`.

### Performance:

| Metric | Result |
| --- | --- |
| **Accuracy** | 81.01% |

## 💡 Key Findings

According to the model's **Feature Importance**, the most critical predictors for survival were:

1. **Gender (adult_male)**: By far the strongest predictor.
2. **Fare & Class**: Economic status played a major role.
3. **Age**: Younger passengers had a statistical advantage in certain classes.

## 🚀 How to Run

1. Ensure you have Python installed.
2. Install dependencies:
```bash
pip install pandas seaborn matplotlib scikit-learn

```


3. Run the Jupyter Notebook `titanic.ipynb`.

---
**Tools used:** Python, Pandas, Seaborn, Scikit-Learn
