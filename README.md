# Marketing Campaign Analysis

This project analyzes the performance of marketing campaigns across different regions and campaign types using Power BI.The objective of this project is to help marketing analysts understand which campaigns generate the highest returns, compare campaign performance across regions, and support data-driven marketing decisions.

# 📊 Marketing Campaign Analysis Dashboard Using Power BI

## 📌 Project Overview

This project analyzes the performance of marketing campaigns across different regions and campaign types using Power BI. The dashboard provides insights into marketing spend, revenue generation, return on investment (ROI), campaign effectiveness, and regional performance.

The objective of this project is to help marketing analysts understand which campaigns generate the highest returns, compare campaign performance across regions, and support data-driven marketing decisions.

---

## 🎯 Problem Statement

As a Marketing Analyst, the goal is to evaluate how different marketing campaigns perform across various regions and marketing platforms.

The dashboard helps answer questions such as:

- Which campaign generates the highest ROI?
- Which region contributes the most revenue?
- How much is being spent on marketing campaigns?
- How does campaign type affect performance?
- What is the overall marketing ROI?

---

## 📂 Dataset

The project uses three CSV files:

### 1. Marketing_Campaign_Details.csv

Contains campaign-level information:

- Campaign Name
- Campaign Type
- Average Spend
- Average ROI
- Total Campaigns

### 2. Marketing_Campaign_Performance.csv

Contains detailed campaign performance records:

- Campaign ID
- Campaign Name
- Region
- Industry
- Spend
- Impressions
- Clicks
- Conversions
- Revenue
- ROI

### 3. Region_Performance.csv

Contains region-level aggregated metrics:

- Region
- Total Spend
- Total Revenue
- Average ROI

---

## 📁 Project Structure

```text
Marketing-Campaign-Analysis-PowerBI/
│
├── Data/
│   ├── Marketing_Campaign_Details.csv
│   ├── Marketing_Campaign_Performance.csv
│   └── Region_Performance.csv
│
├── Dashboard/
│   └── Dashboard_Screenshot.png
│
├── README.md

```

---

## 🛠️ Data Preparation

The following data preparation steps were performed:

- Imported all CSV files into Power BI.
- Verified and corrected data types.
- Checked for missing values and duplicates.
- Renamed columns for better readability.
- Created relationships between tables.
- Validated campaign and region data consistency.

---

## 📐 Data Modeling

### Relationship 1

```text
Campaign Details (1)
        │
        │
Campaign Performance (*)
```

Key:

- Campaign Name

### Relationship 2

```text
Region Performance (1)
        │
        │
Campaign Performance (*)
```

Key:

- Region

The model follows a star-schema design with single-direction filtering.

---

## 📊 DAX Measures

```DAX
Total Impressions =
SUM('campaign performance'[Impressions])

Total Clicks =
SUM('campaign performance'[Clicks])

Total Conversions =
SUM('campaign performance'[Conversions])

Total Revenue =
SUM('campaign performance'[Revenue])

Total Spend =
SUM('campaign performance'[Spend])

Total ROI =
SUM('campaign performance'[ROI])

Average ROI =
AVERAGE('campaign performance'[ROI])

ROI Percentage =
DIVIDE(
    [Total Revenue] - [Total Spend],
    [Total Spend]
)

Best Campaign =
MAXX(
    TOPN(
        1,
        SUMMARIZE(
            'campaign performance',
            'campaign performance'[Campaign Name],
            "RevenueValue",
            SUM('campaign performance'[Revenue])
        ),
        [RevenueValue],
        DESC
    ),
    'campaign performance'[Campaign Name]
)
```

---

## 📈 Dashboard Features

### KPI Cards

- Total Revenue
- Total Spend
- Average ROI
- Best Campaign

### Visualizations

#### 1. Stacked Column Chart

**Total Revenue vs Total Spend by Region**

Compares revenue generation and marketing expenditure across regions.

#### 2. Combo Chart

**Total Spend and Average ROI by Campaign**

Displays campaign spending alongside ROI performance.

#### 3. Bar Chart

**Total ROI by Campaign**

Ranks campaigns based on ROI.

#### 4. Pie Chart

**Number of Campaigns by Campaign Type**

Shows the distribution of Digital and Traditional campaigns.

#### 5. Gauge Chart

**ROI Performance vs Average ROI**

Compares overall ROI performance against the average ROI benchmark.

---

## 🎛️ Interactive Features

The dashboard includes the following slicers:

- Region
- Campaign Type

Users can dynamically filter all visualizations and KPIs.

---

## 📷 Dashboard Preview

### Final Dashboard

![Dashboard Preview](Assets/Dashboard_Preview.png)

---

## 🔍 Key Insights

- Search Engine Ads emerged as the best-performing campaign.
- Digital campaigns account for the majority of campaigns.
- ROI varies significantly across campaign types.
- Marketing spend and revenue differ across regions.
- Overall campaign performance generated positive ROI.

---

## 🖥️ Technologies Used

- Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)
- Data Modeling
- Data Visualization

---

## 🚀 Learning Outcomes

This project helped strengthen skills in:

- Data Cleaning
- Data Transformation
- Data Modeling
- Relationship Management
- DAX Calculations
- KPI Development
- Dashboard Design
- Business Intelligence Reporting

---

## 👨‍💻 Author

**Iron Man**

B.Tech – Artificial Intelligence & Data Science

Aspiring Data Scientist | Power BI Developer | Machine Learning Enthusiast

---

⭐ If you found this project useful, consider giving it a star.
