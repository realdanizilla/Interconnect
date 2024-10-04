# Predicting Customer Churn for Interconnect

- [Predicting Customer Churn for Interconnect](#predicting-customer-churn-for-interconnect)
  - [Project Objective](#project-objective)
  - [Project Structure and Steps](#project-structure-and-steps)
  - [Tools and Techniques Utilized](#tools-and-techniques-utilized)
  - [Specific Results and Outcomes](#specific-results-and-outcomes)
  - [Key Insights and Learnings](#key-insights-and-learnings)
  - [What I Learned From This Project](#what-i-learned-from-this-project)


## Project Objective
The objective of the project was to predict customer churn for Interconnect, a communications service provider. If it is detected that a customer is planning to leave the service, the company aims to retain them by offering promotional codes and special plan options. The dataset includes customer personal information, contract details, and information on the Internet and phone services they use. The primary goal was to create a model with a high **AUC-ROC** score for predicting churn.

[back to top](#predicting-customer-churn-for-interconnect)

## Project Structure and Steps
1. **Data Loading and Exploration**
   - **Datasets used**: `contract.csv`, `personal.csv`, `internet.csv`, and `phone.csv`. Each contains specific customer information linked by a `customerID`.
   - Merged these datasets to create a comprehensive dataset for modeling.
   - The target variable is determined by the column `EndDate` (if equal to "No", the customer did not churn).

2. **Exploratory Data Analysis (EDA)**
   - Analyzed customer characteristics to understand distribution and identify potential features contributing to churn.
   - Evaluated and managed missing data, examined class distributions, and assessed relationships between features and churn.

3. **Feature Engineering and Data Preparation**
   - Performed preprocessing, such as converting categorical variables and ensuring numerical values are correctly formatted.
   - Created additional features to help improve the model’s predictive power.
   - Managed class imbalance as most customers did not churn, which was critical to improving model performance.

4. **Model Training and Evaluation**
   - Experimented with several machine learning models suitable for binary classification:
     - **Logistic Regression**
     - **Decision Trees**
     - **Random Forest**
     - **Gradient Boosting** (including models like XGBoost)
     - **K-Nearest Neighbors (KNN)**
     - **Neural Networks**
   - The models were trained and evaluated primarily based on their **AUC-ROC** scores, which is the key performance metric for classification accuracy.
   - Applied cross-validation and grid search to optimize model hyperparameters.

5. **Model Selection and Testing**
   - Selected the best-performing model using **AUC-ROC** scores from cross-validation.
   - The final model’s performance was tested and validated on unseen test data to ensure generalization.

[back to top](#predicting-customer-churn-for-interconnect)

## Tools and Techniques Utilized
- **Python Libraries**: 
  - `pandas` for data manipulation.
  - `scikit-learn` for model building and evaluation.
  - `hyperopt` for Bayesian optimization and hyperparameter tuning.
  - **Visualization Tools**: `matplotlib` and `seaborn` for EDA and feature analysis.
- **Data Processing Techniques**:
  - Merging and cleaning datasets from different sources.
  - Handling categorical variables through encoding.
  - Balancing classes to prevent biased model predictions.
- **Modeling Techniques**:
  - Various machine learning algorithms for binary classification.
  - Hyperparameter tuning using grid search and cross-validation.
- **Evaluation Metrics**:
  - **Primary**: AUC-ROC to assess classification performance.
  - **Additional**: Accuracy for supplemental model evaluation.

[back to top](#predicting-customer-churn-for-interconnect)

## Specific Results and Outcomes
- **Data Processing and EDA**:
  - Successfully merged data across four different files, resulting in a dataset ready for model training.
  - Key insights from EDA highlighted features with potential predictive power for customer churn, such as contract type and monthly charges.
  
- **Model Performance and Evaluation**:
  - The **Gradient Boosting Classifier** emerged as the best model during trials, with optimized hyperparameters achieving an **AUC-ROC score of approximately 0.85**.
  - Comparisons among models revealed that tree-based methods (e.g., Gradient Boosting, Random Forests) generally outperformed simpler models like Logistic Regression, particularly after hyperparameter tuning.
  
- **Hyperparameter Optimization and Model Selection**:
  - Used Bayesian optimization (with `hyperopt`) to find the best hyperparameters for the Gradient Boosting Classifier, such as `learning_rate`, `max_depth`, and `n_estimators`.
  - Conducted multiple rounds of model training and testing to confirm that the chosen model generalized well across both training and test datasets.

[back to top](#predicting-customer-churn-for-interconnect)

## Key Insights and Learnings
1. **Importance of Data Integration**:
   - Successfully integrating data from multiple sources was crucial for improving model performance and ensuring all relevant features were available for training.

2. **Feature Engineering Impact**:
   - Crafting new features and understanding their relationships to churn significantly contributed to the model's ability to make accurate predictions.

3. **Balancing Class Distribution**:
   - Addressing the class imbalance was essential to ensure the model did not bias predictions toward the non-churning class, thus improving AUC-ROC scores.

4. **Hyperparameter Tuning**:
   - Fine-tuning model parameters using Bayesian optimization played a key role in enhancing model performance and achieving the project’s goals.

[back to top](#predicting-customer-churn-for-interconnect)

## What I Learned From This Project
- **Data Preparation and Cleaning**:
  - Developed strong skills in handling datasets from different sources, including merging, cleaning, and preprocessing data for modeling.

- **Model Building and Evaluation**:
  - Gained experience in training a variety of machine learning models and assessing them with metrics like AUC-ROC and accuracy.
  - Learned the importance of model validation using cross-validation and test data to prevent overfitting.

- **Hyperparameter Optimization Techniques**:
  - Acquired experience in advanced optimization techniques, such as Bayesian search with `hyperopt`, to improve model performance.

- **Feature Engineering and Analysis**:
  - Developed a deeper understanding of how to create and analyze features to maximize predictive power in binary classification tasks.

[back to top](#predicting-customer-churn-for-interconnect)