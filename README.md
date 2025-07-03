# Network Intrusion Detection using Real and Encrypted Synthetic Attack Traffic

## Project Overview

- **Goal**: Detect anomalous or malicious activity in network flow data using supervised machine learning techniques.
- **Approach**: Extract key flow-level features from the dataset, clean and preprocess them, and train multiple classifiers to evaluate detection performance.


##  Dataset Summary

- **Type**: Real-world and encrypted synthetic network traffic.
- **Size**:
  - Training Set: 388,694 samples  
  - Testing Set: 166,584 samples
- **Imbalance**: The dataset is highly imbalanced (normal traffic is the majority class).
- **Handling**: Used **stratified train-test split** to preserve class distribution.

##  Preprocessing Pipeline

- **Initial Cleaning**: Removed non-informative columns (`uid`, `originh`, `unnamed`, etc.).
- **Encoding**: Applied One-Hot Encoding for categorical features.
- **Splitting**: Used `train_test_split()` from Scikit-learn (80:20 ratio, stratified).

##  Models Used

1. **Random Forest Classifier**
   - Ensemble method with 100 decision trees
   - High performance in flow-based classification
   - Visualized with a confusion matrix

2. **Decision Tree Classifier**
   - Simple interpretable tree model
   - Fast inference

3. **K-Nearest Neighbors (KNN)**
   - Distance-based classification
   - Predicts based on neighborhood majority

##  Evaluation Metrics

- **Confusion Matrices**: Used to evaluate performance across all models.
- **Precision-Recall Curves**
- **ROC Curves**

##  Feature Importance

- **Top Predictive Features**:
  - `IAT` (Inter-Arrival Time)
  - `flow_duration`, `active.max`, `active.tot`
  - `bwd_iat.tot`, `flow_iat.tot`

These features were particularly effective in distinguishing normal vs. malicious flow behavior.


