# Customer-Segmentation-Marketing-Strategy

## Project Objective

The objective of this project is to analyze customer purchasing behavior and segment customers into meaningful groups using RFM (Recency, Frequency, Monetary) analysis. These segments help businesses design targeted marketing strategies to improve customer retention, increase revenue, and optimize marketing spend.

## Dataset Overview

The dataset contains transactional data from an online retail company.
Each row represents a product purchased in an order.

### Key columns:
  - Invoice → Order ID
  - StockCode → Product ID
  - Description → Product name
  - Quantity → Number of items purchased
  - InvoiceDate → Date and time of purchase
  - Price → Price per unit
  - Customer ID → Unique customer identifier
  - Country → Customer location

The dataset is transactional, so it must be transformed into customer-level data for segmentation.

### Data Cleaning & Preparation
The following steps were performed to ensure data quality:
- Removed rows with missing Customer IDs
- Removed cancelled orders (Invoice numbers starting with “C”)
- Removed records with zero or negative quantity
- Converted InvoiceDate into datetime format
- Created a new column:
 TotalAmount = Quantity × Price

### RFM Analysis
RFM stands for:
| Metric    | Meaning                  | Business Interpretation          |
| --------- | ------------------------ | -------------------------------- |
| Recency   | Days since last purchase | How recently the customer bought |
| Frequency | Number of purchases      | How often the customer buys      |
| Monetary  | Total spend              | How valuable the customer is     |

RFM table was created by grouping data at customer level:
- Recency = Difference between latest transaction date and customer’s last purchase
- Frequency = Number of unique invoices per customer
- Monetary = Sum of total amount spent by the customer
Each row in the RFM table represents one customer.

### RFM Scoring
Each metric was divided into quartiles:
#### Recency:
- 4 = Most recent
- 1 = Least recent
#### Frequency & Monetary:
- 4 = Highest
- 1 = Lowest
  Then a combined score was created:
  RFM_Score = R_Score + F_Score + M_Score
Example:
444 → Best customers
111 → Worst customers

### Customer Segmentation

Customers were grouped into business-friendly segments:
| Segment         | Description                     |
| --------------- | ------------------------------- |
| Champions       | Recent, frequent, high spenders |
| Loyal Customers | Regular buyers                  |
| At Risk         | Used to buy often, now inactive |
| New Customers   | Recently joined                 |
| Lost Customers  | Long inactive and low value     |
| Others          | Medium or mixed behavior        |

This converts raw numbers into actionable business insights.

### Marketing Strategy Recommendations
| Segment         | Marketing Strategy                          |
| --------------- | ------------------------------------------- |
| Champions       | VIP programs, early access, premium rewards |
| Loyal Customers | Upselling, cross-selling, loyalty points    |
| At Risk         | Win-back campaigns, limited-time discounts  |
| New Customers   | Welcome emails, onboarding offers           |
| Lost Customers  | Heavy discounts or reactivation campaigns   |
| Others          | Personalized product recommendations        |

### Advanced Step – K-Means Clustering
Advanced Step – K-Means Clustering

K-Means clustering was applied on normalized RFM values to identify natural groupings in customer behavior.

Steps:
- Standardized RFM features
- Used Elbow Method to choose optimal clusters
- Applied K-Means
- Analyzed clusters based on average R, F, M values

This added a machine learning component to the project, making it more advanced and resume-ready.

### Business Impact

This project enables a company to:
- Identify high-value customers
- Reduce churn
- Improve targeting of marketing campaigns
- Increase customer lifetime value
- Optimize promotional budgets

### Conclusion

This project demonstrates a complete analytics pipeline:
- Data cleaning
- Feature engineering
- Customer segmentation
- Business interpretation
- Marketing strategy design

It shows strong practical understanding of:
- Customer analytics
- Marketing intelligence
- Business problem solving
