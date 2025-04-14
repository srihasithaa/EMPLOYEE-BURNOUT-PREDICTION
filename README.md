# 🔥 Burn Rate Prediction - EDA & Linear Regression

## 📊 Dataset Overview

- **Total Entries:** 22,750  
- **Columns:** 9  
- **Target Variable:** `Burn Rate`

### Features

- `Employee ID` (dropped during preprocessing)  
- `Date of Joining`  
- `Gender`  
- `Company Type`  
- `WFH Setup Available`  
- `Designation`  
- `Resource Allocation`  
- `Mental Fatigue Score`  
- `Burn Rate` (Target)

### Key Stats

- Missing values handled via `.dropna()`  
- Data cleaned and transformed  
- Strong correlation of Burn Rate with:  
  - `Mental Fatigue Score` (0.94)  
  - `Resource Allocation` (0.85)  
  - `Designation` (0.73)

---

## 📈 Exploratory Data Analysis (EDA)

- Checked for nulls, data types, unique values  
- Investigated statistical summaries  
- Plotted:
  - Pairplots
  - Countplots for categorical values
  - Employee joining trends by month

---

## 🔄 Preprocessing

- Dropped irrelevant or redundant features:
  - `Employee ID`
  - `Date of Joining`
  - `Days` (seniority proxy)
- One-hot encoded categorical columns:
  - `Company Type`
  - `WFH Setup Available`
  - `Gender`
- Scaled numeric features using `StandardScaler`
- Saved scaler as `models/scaler.pkl`
- Train-test split:
  - **Train Size:** 30%
  - **Test Size:** 70%

---

## 🧠 Modeling

### Linear Regression


from sklearn.linear_model import LinearRegression

# Initialize and train the model
linear_regression_model = LinearRegression()
linear_regression_model.fit(X_train, y_train)

# Make predictions
y_pred = linear_regression_model.predict(X_test)

---

### ✅ Model Performance

- **Mean Squared Error:** 0.0031  
- **Root Mean Squared Error:** 0.0559  
- **Mean Absolute Error:** 0.0457  
- **R² Score:** 0.92

---

### 💾 Output

- **Processed Data:** Scaled and cleaned train/test datasets saved in  
  `data/processed/`

- **Scaler Artifact:** Saved scaler object in  
  `models/scaler.pkl`



