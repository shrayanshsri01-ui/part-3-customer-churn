# Customer Churn Prediction and Retention Strategy

## Project Title
Customer Churn Prediction and Retention Strategy

## Business Problem
Churn refers to customers canceling their subscriptions or leaving a service. It is a critical business issue because acquiring new customers is significantly more expensive than retaining existing ones. Predicting churn allows businesses to identify at-risk customers proactively and offer targeted interventions, thereby saving revenue. False negatives (failing to identify a churning customer) are generally more expensive than false positives (offering a retention bonus to a customer who wasn't going to leave anyway), making Recall a priority metric.

## Dataset Description
The dataset contains customer information such as demographic metrics (gender, senior citizen, partner, dependents), account info (tenure, contract type, payment method, monthly charges, total charges), and the target variable (`Churn`), which indicates if the customer left or stayed.

## Data Cleaning and Preprocessing Summary
- Removed irrelevant columns like `Customer ID`.
- Handled missing values (e.g., empty strings in `Total Charges` converted to numeric and filled with mean/median).
- Encoded categorical variables using One-Hot Encoding and Label Encoding.
- Scaled numerical features (`tenure`, `MonthlyCharges`, `TotalCharges`) using StandardScaler to normalize distributions for models like Logistic Regression.
- Split data into 80% training and 20% testing sets.

## EDA Insights
- **Overall Churn Rate**: Displayed as a percentage, indicating the class imbalance.
- **Contract Type**: Month-to-month contracts have the highest churn rate.
- **Tenure**: Newer customers are far more likely to churn than long-term customers.
- **Charges**: Higher monthly charges correlate slightly with a higher likelihood of leaving.

## Models Used
- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier (Optional/Comparison)

## Model Evaluation Results
Evaluated models based on Accuracy, Precision, Recall, F1-Score, and Confusion Matrix metrics. 

## Confusion Matrix Analysis
- **True Positives**: Correctly identified churning customers.
- **True Negatives**: Correctly identified retained customers.
- **False Positives**: Happy customers misidentified as churning.
- **False Negatives**: Churning customers misidentified as staying (Most costly).

## Final Model Selection
Logistic Regression is often selected as the final model due to its high interpretability and strong recall when class weights or thresholds are tuned, making it easier to explain risk factors directly to stakeholders.

## Retention Strategy
1. **Target Month-to-Month Users**: Offer discounts to switch to 1-year or 2-year contracts.
2. **First-Year Support**: Implement proactive onboarding and check-ins during the first 6 months, where churn risk is highest.
3. **Price Sensitivity interventions**: Provide targeted discounts or personalized packages for customers with high monthly charges showing signs of disengagement.

## How to Run
1. Clone the repository.
2. Ensure you have the dataset `part_3_customer_churn_prediction.csv` in the root folder.
3. Install dependencies: `pip install -r requirements.txt`
4. Run `notebook.ipynb` block by block.
