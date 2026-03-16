

📊Madhav E-Commerce Sales Dashboard — Power BI

Transforming raw e-commerce data into actionable business intelligence using Power BI.


📌 Project Overview
The Madhav E-Commerce Sales Dashboard is an interactive Power BI report built to help an e-commerce business track and analyze its sales performance across states, categories, payment modes, and customers.
The project was built using a real-world Kaggle dataset containing transactional order data. The primary goal was to convert raw CSV files into a rich, interactive dashboard that surfaces meaningful insights for business decision-making.
This project strengthened skills in:

Data Modeling — Joining multiple tables via relationships
DAX Calculations — Writing measures for KPIs and aggregations
KPI Tracking — Monitoring revenue, profit, quantity, and averages
Data Storytelling — Designing visuals that communicate insights clearly
Interactive Dashboard Design — Slicers, filters, and drill-through navigation


# 📁 Dataset

This project utilizes the [Madhav E-Commerce Sales Dataset](https://www.kaggle.com/datasets/saadharoon27/madhav-store-dataset) from Kaggle. The data is split across two CSV files.

## File Descriptions


| File | Description |
| :--- | :--- |
| `Orders.csv` | Order-level data — Order ID, Date, Customer Name, State, City |
| `Details.csv` | Transaction-level data — Amount, Profit, Quantity, Category, Sub-Category, Payment Mode |

## Schema — `Orders.csv`


| Column | Type | Description |
| :--- | :--- | :--- |
| `Order ID` | String | Unique order identifier |
| `Order Date` | Date | Date the order was placed |
| `Customer Name` | String | Name of the customer |
| `State` | String | Indian state of the customer |
| `City` | String | City of the customer |

## Schema — `Details.csv`


| Column | Type | Description |
| :--- | :--- | :--- |
| `Order ID` | String | Foreign key linking to Orders |
| `Amount` | Integer | Sale amount (INR) |
| `Profit` | Integer | Profit on the order (INR) |
| `Quantity` | Integer | Number of items ordered |
| `Category` | String | Product category (Electronics, Furniture, Clothing) |
| `Sub-Category` | String | Product sub-category |
| `Payment Mode` | String | Payment method used |

# 🛠️ Tech Stack

*   **Power BI Desktop**: Dashboard development & visualization
*   **Power Query (M)**: Data transformation & cleaning
*   **DAX**: Calculated measures & KPIs
*   **Microsoft Excel / CSV**: Raw data source
*   **Kaggle**: Dataset sourcing


🛠️ Tech Stack
ToolPurposePower BI DesktopDashboard development & visualizationPower Query (M)Data transformation & cleaningDAXCalculated measures & KPIsMicrosoft Excel / CSVRaw data sourceKaggleDataset sourcing

✨ Key Features

🔢 KPI Cards — Sum of Amount, Profit, Quantity, and Average displayed prominently
📅 Quarter Filter — Toggle between Q1, Q2, Q3, Q4 to compare seasonal performance
🗺️ State Dropdown — Filter the entire dashboard by any Indian state
📊 Profit by Month — Bar chart tracking monthly profit trends (January–March shown)
🏙️ Sum of Amount by State — Horizontal bar chart comparing top states (Maharashtra, Madhya Pradesh, Delhi, Gujarat)
🍩 Sum of Quantity by Category — Donut chart showing Clothing (61.97%), Electronics (21.14%), Furniture (16.88%)
💳 Sum of Quantity by Payment Mode — Donut showing COD (40.77%), UPI (19.41%), EMI (14.53%), Debit Card (13.46%), Credit Card (11.83%)
👤 Sum of Amount by Customer — Bar chart highlighting top customers (Shiva, Madhav, Sarita, Madan Mohan)
📦 Sum of Profit by Sub-Category — Horizontal bar chart ranking Printers, Phones, Bookcases, Accessories, Stole


📈 KPIs Tracked
KPIValueTotal Revenue (Sum of Amount)₹139KTotal Profit₹18KTotal Quantity Sold1,783Average Order Value₹37K

📊 Dashboard Visuals
1. Profit by Month
A bar chart visualizing monthly profit across January, February, and March. January and March show peak profit (~6K), while February shows a slight dip (~5K).
2. Sum of Amount by State
Maharashtra leads in total sales amount (~₹40K), followed by Madhya Pradesh and Delhi.
3. Sum of Quantity by Category
Clothing dominates product quantity at 61.97%. Electronics accounts for 21.14% and Furniture for 16.88%.
4. Sum of Quantity by Payment Mode
Cash on Delivery (COD) is the most popular payment method at 40.77%, followed by UPI at 19.41%.
5. Sum of Amount by Customer
Top customers by purchase amount are Shiva, Madhav, Sarita, and Madan Mohan.
6. Sum of Profit by Sub-Category
Printers and Phones are the highest-profit sub-categories, while Stole and Accessories are lower contributors.

🗃️ Data Model
Orders (Order ID, Order Date, CustomerName, State, City)
    |
    | One-to-Many on Order ID
    |
Details (Order ID, Amount, Profit, Quantity, Category, Sub-Category, PaymentMode)
The two tables are related via Order ID, allowing cross-table calculations such as total revenue by state or profit by product category.

🧮 DAX Calculations
dax-- Total Revenue
Total Amount = SUM(Details[Amount])

-- Total Profit
Total Profit = SUM(Details[Profit])

-- Total Quantity
Total Quantity = SUM(Details[Quantity])

-- Average Order Value
Avg Order Value = AVERAGE(Details[Amount])

-- Profit Margin %
Profit Margin = DIVIDE(SUM(Details[Profit]), SUM(Details[Amount]), 0)

-- Quantity by Category %
Category % = DIVIDE(
    CALCULATE(SUM(Details[Quantity])),
    CALCULATE(SUM(Details[Quantity]), ALL(Details[Category])),
    0
)

💡 Business Insights

Clothing drives volume — 62% of total quantity sold is clothing, suggesting it's the core product line.
Printers and Phones are profit leaders — Despite lower volume, these electronics sub-categories generate the highest profit margins.
COD remains dominant — 41% of transactions use Cash on Delivery, indicating a market preference for deferred payment.
Maharashtra is the top revenue state — Targeted marketing campaigns in Maharashtra could yield the highest ROI.
February shows a profit dip — Worth investigating for seasonality, supply chain issues, or promotional discount over-spend.
Top 4 customers are high-value — Loyalty programs for Shiva, Madhav, Sarita, and Madan Mohan could drive repeat revenue.


📂 Project Structure
madhav-ecommerce-dashboard/
│
├── 📄 README.md                  # Project documentation
├── 📊 Madhav_Dashboard.pbix      # Power BI report file
├── 📁 data/
│   ├── Orders.csv                # Order master data
│   └── Details.csv               # Order details & financials
└── 📁 assets/
    └── Powerbi1.png              # Dashboard screenshot

🚀 How to Run

Clone this repository

bash   git clone https://github.com/sarahsair25/madhav-ecommerce-dashboard.git
   cd madhav-ecommerce-dashboard

Open Power BI Desktop

Download from Microsoft Power BI


Load the .pbix file

Open Madhav_Dashboard.pbix in Power BI Desktop


Refresh Data Source (if needed)

Go to Home → Transform Data → Data Source Settings
Update the file path to point to the local /data/ folder


Explore the Dashboard

Use the Quarter buttons (Qtr 1–4) to filter by quarter
Use the State dropdown to filter by geography
Hover on any chart for interactive tooltips




🎯 Skills Demonstrated

✅ Data importing & connecting multiple CSV files in Power BI
✅ Data cleaning and transformation using Power Query
✅ Building a relational data model (star schema)
✅ Writing DAX measures for KPIs, ratios, and aggregations
✅ Designing interactive visuals: bar charts, donut charts, KPI cards
✅ Dashboard layout and UX design for business audiences
✅ Adding slicers and filters for interactive exploration
✅ Data storytelling — turning numbers into business narratives


🤝 Connect With Me
If you found this project helpful or have suggestions, feel free to connect!

💼 LinkedIn :https://www.linkedin.com/in/sarahsair/
📧 Email :sarahsair@gmail.com
🐙 GitHub :https://github.com/sarahsair25


⭐ If you found this useful, please consider giving this repository a star!

Tags: #PowerBI #DataAnalytics #DataVisualization #ECommerce #DAX #BusinessIntelligence #Dashboard #Kaggle #DataScience
