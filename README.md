# Predicting Energy Consumption in Low-Energy Buildings

##  Overview
This project aims to predict **energy consumption** in a **low-energy building** by analyzing internal environmental conditions (e.g., room temperature, humidity) and external weather conditions. Using machine learning techniques, we seek to improve energy prediction accuracy and provide insights for energy-efficient strategies.

### Why Predict Energy Consumption?
- **Optimize Energy Usage**: Helps in better energy management and sustainability.
- **Reduce Costs**: More efficient energy prediction reduces waste and lowers costs.
- **Data-Driven Decision Making**: Supports smart energy-saving strategies in buildings.

---

##  Data and Preprocessing
### **Dataset**
- Source: **UC Irvine Machine Learning Repository**
- **19,735 samples** with **28 features**, including:
  - **Room conditions**: Temperature, Humidity
  - **External conditions**: Wind speed, Visibility, Dew point
  - **Energy consumption**: Measured in **Watts**
  
### **Data Preprocessing**
- **Encoding categorical variables** (`season`)
- **Feature scaling**: Applied **StandardScaler** for numerical variables.
- **Data split**: 
  - Training: **13,814 samples**
  - Validation: **2,960 samples**
  - Testing: **2,961 samples**

---

##  Model Architectures
The project explores various machine learning models to predict energy consumption:

### **1️⃣ Linear Regression & Regularization**
- **Linear Regression**: Established a baseline model.
- **Lasso & Ridge Regression**: Regularized models to handle feature importance.
- **Best Validation MSE**: **0.330**

### **2️⃣ K-Nearest Neighbors (KNN)**
- **Feature normalization** applied.
- **Optimal k**: **5**
- **Best Validation MSE**: **0.365**

### **3️⃣ Decision Trees & Random Forest**
- **Decision Tree Results**:
  - **Top Features**: Lights, RH_out, RH_8
  - **Best Validation MSE**: **0.255**
- **Random Forest Results**:
  - **Best Validation MSE**: **0.3378**
  - **Best R² Score**: **0.69**

### **4️⃣ Boosting (AdaBoost, Gradient Boosting)**
- **Optimal Hyperparameters found via GridSearchCV**
- **Best Validation MSE**: **0.368**

---

## Results and Evaluation
| **Model**         | **MSE (Test)** | **R² Score**  |
|------------------|--------------|--------------|
| **Linear Regression**  | 0.330        | 0.271        |
| **KNN**         | 0.365        | 0.231        |
| **Decision Tree** | 0.255        | 0.389        |
| **Random Forest** | 0.337        | 0.690        |
| **Boosting**      | 0.368        | 0.187        |

### **Key Insights**
- **Humidity and temperature** were key predictors of energy consumption.
- **Decision Trees outperformed linear models** but required careful tuning.
- **Boosting models underperformed**, possibly due to dataset size and feature interactions.

---



##  Future Scope
- **Granular Analysis**: Instead of seasonal breakdowns, analyze by day of the week.
- **Extended Time Frame**: Gather more than **4.5 months** of data.
- **Cross-Building Comparisons**: Compare energy consumption across different locations.

