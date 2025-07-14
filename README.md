# 🏠 Guest Satisfaction & Rating Prediction

## 🎯 Objective

This project aims to **analyze Airbnb listings data** and build **two machine learning models**:

- **Regression**: Predict the **review_scores_rating** of a listing.
- **Classification**: Predict the **guest satisfaction label** (Average , High , very_High).

---

## 📊 Dataset Overview

The dataset contains diverse information about Airbnb listings, including:

- **Host details** (e.g., host status, response rate)
- **Pricing** (nightly, stay-based, fees)
- **Property features** (beds, bedrooms, amenities, etc.)
- **Location coordinates**
- **Textual content** (e.g., host_about, description)
- **Review statistics** (number of stays, reviews)

---

## 🧪 Project Workflow

### 1. Data Preprocessing

- **Missing value imputation** using `KNNImputer`
- **Standardization** using `StandardScaler`
- **Log-transforming skewed features** (e.g., prices, reviews)
- **Date feature engineering**: Days since host joined, review times, cyclical date features
- **Text preprocessing & sentiment analysis** using `VADER`
- **TF-IDF extraction** from textual columns
- **SMOTE oversampling** for balancing the classification target variable

### 2. Feature Engineering

- Derived features:
  - `host_experience`, `super_experience`, `reviews_per_stay`
  - Location-based clusters using **KMeans**
  - Sentiment scores for host/about sections
  - Important amenity detection + `amenity_score`
  - Interaction features (e.g., `price_per_guest`, `superhost_reviews_interaction`)
  - Property type grouping (e.g., Apartments, Unique Stays)

### 3. Encoding

- Label Encoding and One-Hot Encoding
- Target and Frequency Encoding for high-cardinality categorical features

### 4. Feature Selection

- Removed highly correlated features (correlation > 0.9)
- Selected top features using **Mutual Information** (`SelectKBest`)

### 5. Modeling

- **Regression Models**:
  - `LinearRegression`, `Ridge`, `Lasso`, `ElasticNet`, `Huber`
  - `Random Forest`, `Gradient Boosting`, `XGBoost`, `CatBoost`, `LightGBM`
  - `SVR`, `KNN`, `Neural Network`
- **Classification Models**:
  - Applied after balancing with **SMOTE**
  - Predicts if the guest will be satisfied or not

### 6. Evaluation Metrics

- R² Score for regression
- Accuracy, F1 Score, and Confusion Matrix for classification

---

## 🧠 Technologies & Tools Used

- **Python**, **Pandas**, **NumPy**
- **Scikit-learn**, **XGBoost**, **LightGBM**, **CatBoost**
- **Matplotlib**, **Seaborn**, **Folium**
- **NLTK**, **Swifter**, **Joblib**
- **SMOTE** for class balancing

---

## 🔍 Insights & Value

- Helps **Airbnb hosts** improve their listings by identifying what impacts guest satisfaction.
- Understand how **pricing, amenities, and host behavior** affect guest perception.
- Supports **dynamic pricing models** and **customer experience improvement**.

---

## 🚀 Future Improvements

- Add **deep learning-based sentiment models** (e.g., BERT)
- Build a **dashboard for real-time guest satisfaction prediction**
- Integrate external factors (e.g., seasonal trends, local events)

---

## 🏆 Achievement

🏅 **Won 2nd place** in a university-level data science competition using this project.
