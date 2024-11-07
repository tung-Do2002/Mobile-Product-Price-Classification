# Mobile Price Classification Project

## Overview

This repository contains code and analysis for a mobile phone dataset and a machine learning model used to classify the price range of mobile phones. 

## Dataset

The dataset contains information about various features of mobile phones, such as battery power, screen size, RAM, and others. Each observation represents a mobile phone.

## Data Analysis

**Missing Values:** The dataset has no missing values, which simplifies analysis and model building.

**Correlations:**
![image](https://github.com/user-attachments/assets/4cc24594-13ea-4d50-b11a-1e85b124f8f1)

* There is a moderate positive correlation between `ram` and `battery_power`, suggesting that phones with higher RAM tend to have larger battery capacity.
* There is a weak negative correlation between `battery_power` and `three_g`. This could indicate that phones with larger battery capacity might be less likely to support 3G, or vice versa.

**Visualizations:**

* **Countplot of Price Range:** Shows the distribution of phones across different price ranges. The plot indicates a relatively balanced distribution of classes, which is beneficial for model training.
* **Scatterplot of Talk Time and RAM:**  Helps visualize the relationship between talk time and RAM, colored by price range. There might be a slight positive trend, suggesting that phones with higher RAM tend to have longer talk time.
* **Boxplot of Pixel Width:** Displays the distribution of pixel width. The boxplot reveals a wide range of values with some potential outliers.
* **Scatterplot of Height and Width:** Shows the relationship between screen height and width, colored by price range. This visualization can help identify any patterns or trends related to screen dimensions and price.
* **Boxplot of Pixel Height:** Displays the distribution of pixel height. Similar to the pixel width boxplot, it shows a wide range of values and potential outliers.

## Machine Learning Model

A **Logistic Regression** model was used to classify mobile phones into different price ranges. 

**Results:**

* **Best Parameters:**
    * `C`: 10 (Regularization strength)
    * `solver`: 'liblinear' (Algorithm used for optimization)
* **Classification Report:**

| Class | precision | recall | f1-score | support |
|---|---|---|---|---|
| 0 | 0.88 | 0.99 | 0.93 | 95 |
| 1 | 0.70 | 0.52 | 0.60 | 92 |
| 2 | 0.67 | 0.65 | 0.66 | 99 |
| 3 | 0.88 | 1.00 | 0.94 | 114 |

* **Overall Accuracy:** 80% 
* **Macro average:** 0.78 (precision), 0.79 (recall), 0.78 (f1-score)
* **Weighted average:** 0.79 (precision), 0.80 (recall), 0.79 (f1-score)
* **F1 Score (Overall):** 0.7889

**Detailed Analysis of Classification Report:**

* **Class 0:** The model performs well in classifying phones in the lowest price range with high precision and recall. This suggests that the model can effectively identify features associated with low-cost phones.
* **Class 1:** The model struggles with this price range, particularly with a lower recall. This indicates that the model might misclassify some phones belonging to this category into other price ranges. Further investigation is needed to understand the reasons for this misclassification.
* **Class 2:** The model shows moderate performance for this price range. The precision and recall values are relatively balanced, suggesting that the model is neither particularly good nor bad at identifying phones in this category.
* **Class 3:** The model excels in classifying phones in the highest price range with perfect or near-perfect precision and recall. This indicates that the model effectively captures the features that distinguish high-cost phones.

**Overall Performance:**

The model achieves an overall accuracy of 80%, which is a decent performance. However, the performance varies across different price ranges. The model shows excellent performance for the lowest and highest price ranges but struggles with the mid-range price points, especially class 1. This suggests that further analysis and model improvement are needed to address the inconsistencies in classification performance across different classes.

## Code

The code for data analysis and model training is stored in the file `analysis.py`.

## Discussion

* Further analysis could be done to understand the relationship between features and price range, particularly for the misclassified instances in class 1.
* Different models or feature engineering techniques could be explored to potentially improve performance, especially for the mid-range price categories.
* Analyzing the confusion matrix can provide more insights into the types of misclassifications the model is making.
* Experimenting with different algorithms (e.g., Decision Trees, Random Forests, Support Vector Machines) might lead to better overall performance.

## Contributing

Feel free to fork this repository and contribute to the project. 

## Author

[Your Name]
