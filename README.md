# Tableau E-Commerce Sales Analytics Dashboard

## Project Overview

This project presents an interactive Tableau dashboard built using an e-commerce sales dataset. The dashboard provides a comprehensive overview of business performance through key indicators such as **Sales**, **Profit**, and **Order Quantity**. Year-to-date (YTD), prior year comparisons, and year-on-year (YoY) growth metrics are visualised.

Here is a preview of the E-commerce Sales Dashboard :

![HR Analytics Dashboard](https://github.com/valerijarudjko/tableau-ecomm-project/blob/main/Tableau%20E-comm%20Project.png?raw=true)

##  KPI Formulas Used in Tableau

### 📈 Sales Graph
```text
YTD Sales KPI:
{ FIXED : SUM(IF YEAR([Order Date]) = {MAX(YEAR([Order Date]))} THEN [Sales] END) }

Previous YTD Sales KPI:
{ FIXED : SUM(IF YEAR([Order Date]) = {MAX(YEAR([Order Date])) - 1} THEN [Sales] END) }

Year on Year:
([YTD Sales LOD] - [PYTD Sales LOD]) / [PYTD Sales LOD]

YOY Sales Margin:
IF [YOY Sales] > 0 THEN '▲'
ELSEIF [YOY Sales] < 0 THEN '▼' END
```

### 💰 Profit Graph
```text
YTD Profit KPI:
{ FIXED : SUM(IF YEAR([Order Date]) = {MAX(YEAR([Order Date]))} THEN [Profit Per Order] END) }

Previous YTD Profit KPI:
{ FIXED : SUM(IF YEAR([Order Date]) = {MAX(YEAR([Order Date])) - 1} THEN [Profit Per Order] END) }

Year on Year:
([YTD Profit Per Order LOD] - [PYTD Profit Per Order LOD]) / [PYTD Profit Per Order LOD]

YOY Profit Margin:
IF [YOY Profit Per Order] > 0 THEN '▲'
ELSEIF [YOY Profit Per Order] < 0 THEN '▼' END
```

### 📦 Order Quantity Graph
```text
YTD Order Quantity KPI:
{ FIXED : SUM(IF YEAR([Order Date]) = {MAX(YEAR([Order Date]))} THEN [Order Quantity] END) }

Previous YTD Order Quantity KPI:
{ FIXED : SUM(IF YEAR([Order Date]) = {MAX(YEAR([Order Date])) - 1} THEN [Sales] END) }

Year on Year:
([YTD Sales LOD] - [PYTD Sales LOD]) / [PYTD Sales LOD]

YOY Sales Margin:
IF [YOY Sales] > 0 THEN '▲'
ELSEIF [YOY Sales] < 0 THEN '▼' END
```

### Sales Margin (Category wise YTD vs PYTD Sales)
```text
IF SUM([YTD Sales])-SUM([PYTD Sales ])<0 THEN 'Less than PY'
ELSEIF SUM([YTD Sales])-sum([PYTD Sales ])>0 THEN 'Greater than PY'
ELSEIF ISNULL(SUM([PYTD Sales ])) THEN 'No sales in PY'
END
```

### Positive / Negative % Difference / No sales
```text
IF [% Difference]> 0 THEN '▲' END
IF [% Difference]< 0 THEN '▼' END
If [Sales Margin]= 'No Sales in PY' THEN 'No Sales in PY' END
```


###  Tools Used:

- **Tableau** – for dashboard creation and visualization
-[LOD Calculations** – to compute fixed YTD and comparative metrics]
- **Excel/CSV** – data preprocessing





Author: V.R

Credits: @datatutorials1
