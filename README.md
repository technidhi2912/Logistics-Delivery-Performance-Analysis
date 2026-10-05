# Logistics Delivery Performance Analysis and Optimization Using Python

## About the Project

This project is about analyzing logistics and supply chain data to understand how well deliveries are performing and where the main problems are.

I used Python to clean the data, explore different delivery patterns, create visualizations, and analyze profitability. I also built a machine-learning model to predict whether an order is likely to be a late delivery.

The main idea was to use the available data to find useful patterns and then turn those findings into practical suggestions for improving logistics performance.

## What I Worked On

* Cleaned and prepared the logistics dataset
* Checked missing values and duplicate records
* Analyzed delivery status and shipping delays
* Compared different shipping modes
* Looked at monthly delivery performance
* Compared late-delivery rates across regions
* Analyzed order profitability
* Compared profitability across product categories
* Built and compared two classification models
* Prepared visualizations for the main findings

## Dataset

The project uses the **DataCo Supply Chain dataset**, which contains information about orders, products, customers, shipping, delivery status and profitability.

Some unnecessary personal-information columns were removed during the cleaning process.

The cleaned dataset is available in:

`data/cleaned_logistics_data.csv`

The original dataset is also kept in the `data` folder for reference.

## Project Structure

```text
Logistics-Delivery-Performance-Analysis/
│
├── data/
│   ├── cleaned_logistics_data.csv
│   └── DataCoSupplyChainDataset.csv
│
├── image/
│   └── charts/
│       ├── 01_late_delivery_rate_by_shipping_mode.png
│       ├── 02_shipping_delay_distribution.png
│       ├── 03_delivery_status_by_shipping_mode.png
│       ├── 04_monthly_late_delivery_rate.png
│       ├── 05_late_delivery_rate_by_region.png
│       └── 06_top_10_categories_by_average_profit.png
│
├── python/
│   └── logistics_delievery_analysis.ipynb
│
└── reports/
```

## Some Key Findings

During the analysis, a few things stood out:

* Around **54.83%** of the records were classified as late deliveries.
* **First Class** shipments had the highest late-delivery rate at **95.32%**.
* **Standard Class** had the highest number of orders, with **107,752 records**.
* **Central Africa** had the highest late-delivery rate among the regions at **57.96%**.
* Around **18.71%** of the records were loss-making.
* **Computers** had the highest average profit per order at **157.59**.
* **CDs** had the lowest average profit per order at **1.42**.

These findings helped in understanding where delivery and profitability issues may need more attention.

## Machine Learning

For the prediction part, I created a binary target called `Is_Late`, where:

* `1` = Late delivery
* `0` = Not a late delivery

I compared two models:

* Logistic Regression
* Decision Tree Classifier

After comparing their results, I selected **Logistic Regression** as the final model.

### Logistic Regression Results

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 69.65% |
| Precision | 84.42% |
| Recall    | 54.76% |
| F1 Score  | 66.43% |
| ROC-AUC   | 0.7334 |

The model is not meant to perfectly predict every late delivery. Instead, it can be used as an early-warning approach to identify orders that may have a higher chance of being delayed.

## Main Recommendations

Based on the analysis, some areas that could be looked into further are:

1. Investigating why First Class shipments have such a high late-delivery rate.
2. Using the prediction model to identify potentially risky deliveries earlier.
3. Reviewing scheduled shipping times for orders with higher delivery risk.
4. Paying closer attention to regions with higher late-delivery rates.
5. Looking into the reasons behind loss-making orders.
6. Reviewing product categories with very low average profit.
7. Continuing to monitor delivery performance by shipping mode, region and product category.

## Tools Used

* Python
* Pandas
* Matplotlib
* Scikit-learn
* Jupyter Notebook

## Conclusion

Overall, this project helped me understand how logistics data can be used to look at delivery performance, shipping delays and profitability.

The analysis showed that late deliveries are a significant issue in the dataset, and there are also noticeable differences between shipping modes, regions and product categories.

The machine-learning part added a predictive side to the analysis by providing an early-warning approach for potentially late deliveries.

There is still scope for improving the model by trying other algorithms, adding more useful operational features and adjusting the prediction threshold depending on the actual business requirement.
