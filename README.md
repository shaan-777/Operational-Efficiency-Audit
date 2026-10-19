# Inventory Optimisation & Operational Efficiency Analysis

**A data-driven inventory analytics project focused on inventory performance, demand patterns, category and location analysis, stockout risk, and inventory optimization using business intelligence dashboards.**

## 📌 Project Overview

Effective inventory management requires balancing product availability against the cost of holding excess stock. Insufficient inventory can lead to stockouts and lost sales, while excessive inventory can tie up working capital and increase storage costs.

This project examines inventory performance across products, categories, and locations. It brings together inventory value, demand trends, stock availability, turnover, days of supply, and stockout risk to support operational decision-making.

The goal is to move beyond descriptive reporting and identify where inventory needs attention, which categories require closer monitoring, and how inventory decisions can be improved.

## 🎯 Business Objectives

- Monitor inventory value, stock levels, and demand patterns.
- Analyze inventory performance across product categories.
- Compare inventory distribution and operational performance across locations.
- Identify products with potential stockout or overstock risk.
- Evaluate inventory turnover and days of supply.
- Apply ABC–XYZ segmentation to prioritize inventory management.
- Identify demand variability and potential replenishment issues.
- Develop actionable recommendations for inventory allocation and operational efficiency.

## 📊 Dataset

**Dataset:** Inventory Dataset

The dashboard designs show product-, category-, location-, and time-based inventory metrics. The final repository should document the exact dataset source and the fields available in the downloaded data.

The following fields are relevant if they exist in the source dataset:

| Data field | Business purpose |
|---|---|
| Date | Analyze inventory and demand trends over time |
| Product ID | Identify individual products |
| Product Name | Make product-level results interpretable |
| Category | Compare inventory performance across product groups |
| Location | Analyze stock distribution across locations |
| Current Stock | Measure available inventory |
| Units Sold / Demand | Understand product demand |
| Inventory Value | Estimate the financial value of stock |
| Units Ordered | Review replenishment activity |
| Supplier | Compare supplier-related inventory performance |
| Lead Time | Support replenishment and safety-stock calculations |
| Forecast Demand | Compare expected demand with actual demand |

Not every field is guaranteed to exist in the dataset. Calculations involving lead time, safety stock, supplier performance, or forecast accuracy require the corresponding source data or explicitly documented assumptions.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Tableau | Dashboard design, interactive filtering, and visual analysis |
| Python | Data preparation and exploratory analysis, where implemented |
| Pandas | Data cleaning and aggregation, where implemented |
| NumPy | Numerical calculations, where implemented |
| SQL | Data validation and analytical queries, where implemented |
| Git and GitHub | Version control and project documentation |

The final technology list should reflect the tools actually used to build and validate the project.

## 🔄 End-to-End Analysis Process

### 1. Data Understanding and Preparation

The first stage is to understand the source data, its granularity, available dimensions, and the meaning of each metric.

Key checks include:

- Inspecting row counts, column names, and data types.
- Identifying the product, location, and date fields.
- Checking missing values and duplicate records.
- Validating inventory and demand quantities.
- Checking whether inventory value is supplied or calculated.
- Confirming that metrics use consistent units and time periods.

**Why it matters:** Incorrect joins, inconsistent units, and duplicate records can distort inventory value, demand, and stockout calculations.

### 2. Inventory Performance Analysis

Inventory performance is evaluated through the principal KPIs displayed in the overview dashboard.

| KPI | Definition | Business interpretation |
|---|---|---|
| Total Products | Count of distinct product identifiers | Measures product assortment size |
| Total Inventory Value | Sum of inventory value at the selected grain | Indicates capital tied up in inventory |
| Inventory Turnover | Cost of goods sold divided by average inventory value, when the required data exists | Measures how efficiently inventory is converted into sales |
| Stockout Rate | Stockout events divided by eligible product-location-period observations | Measures the frequency of stock unavailability |
| Days of Supply | Available stock divided by average daily demand | Estimates how long current inventory may last |
| Demand Trend | Units sold or demanded over time | Highlights changes in demand |
| Inventory Trend | Inventory value or units over time | Shows changes in stock position |

**Important:** Inventory turnover and stockout rate must be defined consistently. A chart showing a category-level turnover value should use a documented formula and a compatible aggregation method.

### 3. Category-Level Analysis

The Category Analysis dashboard compares inventory performance across product groups such as beverages, snacks, personal care, household products, dairy, stationery, and others, where those categories exist in the source data.

The analysis focuses on:

- Inventory value by category.
- Current stock and inventory distribution.
- Average days of supply.
- Monthly demand by category.
- Category-level stockout rates.
- Comparison of inventory value with stockout exposure.

**Business interpretation**

A category with a large inventory value may account for a substantial share of working capital. A category with low days of supply and high demand may need closer replenishment monitoring.

High inventory value alone does not mean a category is overstocked. Demand, service requirements, replenishment lead time, and stockout history must also be considered.

### 4. Location-Level Analysis

The Location Analysis dashboard compares inventory and operational metrics across locations.

Key analytical views include:

- Inventory value by location.
- Current stock by location.
- Location-wise days of supply.
- Stockout rate by location.
- Geographic inventory distribution, where supported by valid location data.
- Comparison of inventory value against stockout rate.

**Business interpretation**

Locations with high inventory value may be holding a large share of the available stock. Locations with low days of supply and higher stockout rates may require replenishment or stock reallocation analysis.

The aim is to determine whether inventory is positioned where demand occurs, rather than simply maximizing total stock.

### 5. Stockout and Overstock Risk Identification

Inventory risk is assessed by comparing stock availability with expected demand and replenishment requirements.

| Risk | Potential impact | Analytical response |
|---|---|---|
| Stockout risk | Lost sales, delayed fulfillment, or reduced service levels | Identify products with insufficient stock relative to demand |
| Overstock risk | Excess working capital and potential holding costs | Investigate high stock relative to expected demand |
| Low inventory turnover | Potentially slow-moving stock | Review demand trends and inventory accumulation |
| Low days of supply | Inventory may be depleted before replenishment | Compare stock cover with expected replenishment timing |
| Demand variability | Forecast errors and unstable replenishment requirements | Analyze historical demand variation |
| Location imbalance | Excess stock in one location and shortages in another | Compare location-level supply and demand |
| Data quality risk | Incorrect inventory decisions | Validate stock, demand, value, and date fields |

These are risk indicators, not automatic proof of a problem. Thresholds should reflect actual business requirements, demand patterns, and replenishment lead times.

### 6. ABC–XYZ Inventory Segmentation

ABC–XYZ analysis provides a structured approach to prioritizing inventory management.

**ABC classification** groups products according to their contribution to a selected measure of annual consumption value, subject to the availability of appropriate data.

- **A items:** Highest-value contribution and typically higher monitoring priority.
- **B items:** Intermediate contribution.
- **C items:** Lower-value contribution.

**XYZ classification** groups products according to demand variability.

- **X items:** Relatively stable demand.
- **Y items:** Moderate variability or trend/seasonality effects.
- **Z items:** Highly variable or less predictable demand.

Combining both dimensions produces a nine-cell matrix, such as AX, AY, AZ, BX, and CZ.

**Business interpretation**

- AX items may be suitable for tightly controlled replenishment due to high value and stable demand.
- AZ items may require more careful forecasting because they combine high value with unpredictable demand.
- CZ items may be managed with simpler controls, depending on service requirements and criticality.

Actual classifications require a defined consumption-value measure, a demand variability formula, and documented classification thresholds.

## 🖥️ Dashboard Suite

The dashboard suite presents inventory performance from four complementary perspectives: overall performance, category analysis, location analysis, and inventory performance comparisons.

### Dashboard 1 — Inventory Performance Overview

**Screenshot:** Save the actual dashboard image as `images/01-inventory-performance.png`.

![Inventory Performance Overview](images/01-inventory-performance.png)

**Purpose:** Provide a consolidated view of inventory health and demand.

**Key components**

- Total products.
- Total inventory value.
- Average inventory turnover.
- Stockout rate.
- Inventory value and demand trend.
- Inventory turnover by category.
- Top products by inventory value.
- Current stock, days of supply, and stockout-risk indicators.

**What it signifies**

This dashboard helps stakeholders identify the overall inventory position, observe changes in demand, and identify products that may need investigation.

The top-products table provides a product-level view of inventory value and stock coverage. Risk labels such as Low, Medium, and High should be driven by documented business rules rather than arbitrary colors.

### Dashboard 2 — Inventory Optimisation Analysis

**Screenshot:** Save the actual dashboard image as `images/02-inventory-optimisation.png`.

![Inventory Optimisation Analysis](images/02-inventory-optimisation.png)

**Purpose:** Summarize inventory efficiency and highlight potential optimization opportunities.

**Key components**

- Inventory and demand trends.
- Inventory turnover by category.
- Inventory performance KPIs.
- Product-level inventory details.
- Filters for date, category, location, and product.

**What it signifies**

The dashboard supports the investigation of how inventory levels compare with demand and how turnover varies across product categories.

An inventory optimization decision should consider both availability and cost. Reducing stock indiscriminately may reduce inventory value but increase stockout risk.

### Dashboard 3 — Category Analysis

**Screenshot:** Save the actual dashboard image as `images/03-category-analysis.png`.

![Category Analysis](images/03-category-analysis.png)

**Purpose:** Compare inventory value, stock levels, demand, and supply coverage across categories.

**Key components**

- Inventory value by category.
- Current stock and in-transit stock, where available.
- Average days of supply.
- Monthly demand by category.
- Category-wise stockout rates.
- Category-level KPI table.

**What it signifies**

The combined views help identify categories with high inventory value, different demand patterns, or potential availability problems.

For example, a category with relatively low days of supply and high stockout frequency may deserve a replenishment review. A category with high stock and weak demand may warrant a slow-moving inventory investigation.

These conclusions should be validated against the actual source data and the relevant replenishment rules.

### Dashboard 4 — Location Analysis

**Screenshot:** Save the actual dashboard image as `images/04-location-analysis.png`.

![Location Analysis](images/04-location-analysis.png)

**Purpose:** Compare inventory allocation and stock availability across locations.

**Key components**

- Inventory value by location.
- Total stock by location.
- Number of locations.
- Average days of supply.
- Geographic inventory distribution, where supported by the source data.
- Location-wise stockout rates.
- Inventory value versus stockout-rate analysis.

**What it signifies**

This dashboard helps identify whether stock is distributed in line with location-level requirements.

Locations with high stockout rates and low days of supply may need replenishment attention. Locations holding substantial inventory may be candidates for stock reallocation only when demand, transport cost, and service requirements support the move.

## 📈 Additional Inventory Optimization Methods

The following methods extend the dashboard analysis into replenishment planning. They should be implemented only when the required data fields and calculations are available.

### Economic Order Quantity (EOQ)

EOQ estimates an order quantity that balances ordering costs with inventory holding costs.

\[
EOQ = \sqrt{\frac{2DS}{H}}
\]

Where:

- \(D\) = annual demand.
- \(S\) = cost per order.
- \(H\) = annual holding cost per unit.

**Business use:** Evaluate order quantities that balance replenishment frequency against holding costs.

### Reorder Point (ROP)

A basic reorder point can be estimated as:

\[
ROP = dL + SS
\]

Where:

- \(d\) = average demand per period.
- \(L\) = replenishment lead time in the same period units.
- \(SS\) = safety stock.

**Business use:** Establish a stock threshold at which replenishment should be initiated, considering lead time and the desired service level.

### Safety Stock

Safety stock provides a buffer against demand variability and replenishment uncertainty.

Its calculation depends on the selected service level, demand variability, lead-time variability, and assumptions about their distributions.

**Business use:** Reduce the likelihood of stockouts during periods of uncertainty.

### Demand Forecasting

Forecasting can estimate future demand from historical observations. Model selection should account for trend, seasonality, demand intermittency, and forecast horizon.

Forecast performance should be evaluated with suitable metrics, such as MAE or WAPE, where appropriate.

**Business use:** Support more informed purchasing and replenishment decisions.

### Service-Level and Cost Trade-Off

Inventory policies should balance availability against the cost of holding stock.

Relevant measures may include:

- Inventory holding cost.
- Ordering cost.
- Stockout frequency.
- Service level or fill rate.
- Excess and obsolete inventory.
- Forecast error.

These metrics require the appropriate data and should not be estimated as actual business outcomes without supporting evidence.

## 💡 Business Recommendations

1. **Prioritize stockout-prone products:** Review products with low days of supply relative to demand and replenishment lead time.
2. **Investigate slow-moving inventory:** Examine products with high stock relative to demand and low turnover before reducing purchase quantities.
3. **Use category-specific inventory policies:** Avoid applying one replenishment rule to every category when demand and criticality differ.
4. **Review location imbalances:** Compare local supply and demand before recommending stock transfers.
5. **Apply ABC–XYZ segmentation:** Allocate analytical and operational attention according to inventory value and demand predictability.
6. **Improve demand planning:** Evaluate forecast accuracy and identify products with persistent forecast errors.
7. **Document risk thresholds:** Make stockout and overstock classifications reproducible and explainable.
8. **Validate financial assumptions:** Quantify holding costs, ordering costs, and expected savings only when the required inputs are available.

## 📁 Suggested Project Structure

```text
Inventory-Optimisation-Analysis/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
├── sql/
├── tableau/
│   └── inventory_analysis.twbx
├── images/
│   ├── 01-inventory-performance.png
│   ├── 02-inventory-optimisation.png
│   ├── 03-category-analysis.png
│   └── 04-location-analysis.png
├── reports/
├── README.md
└── .gitignore
```

This is a suggested structure. Keep the README aligned with the files actually present in the repository.

## ⚠️ Limitations

- Inventory KPIs must be verified against the actual source dataset.
- The dataset source and whether its data is synthetic or real-world should be documented accurately.
- Inventory value and turnover calculations depend on consistent units and aggregation rules.
- Stockout risk classifications require defined thresholds and relevant demand and replenishment information.
- EOQ, reorder point, safety stock, and expected savings require additional inputs where they are not supplied by the dataset.
- Dashboard screenshots are visual summaries; all displayed figures should be reproducible from the underlying data.
- Recommendations are analytical proposals and should be evaluated against real operational constraints before implementation.

## 🚀 Future Enhancements

- Add a reproducible data-quality and KPI validation pipeline.
- Implement ABC–XYZ classification using documented thresholds.
- Calculate safety stock and reorder points where demand and lead-time data permit.
- Add forecast accuracy metrics and demand variability analysis.
- Develop what-if scenarios for service level, order quantity, and holding cost.
- Evaluate location-level stock transfer opportunities.
- Document the calculation and assumptions behind each financial recommendation.

## 👤 Author

**Krith Thakker**

[GitHub Profile](https://github.com/shaan-777)

[Inventory Optimisation Analysis Repository](https://github.com/shaan-777/Inventory-Optimisation-Analysis)
