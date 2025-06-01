# 📈 Stock Market Analyzer Using PCA and Clustering

**Project Title:** Build a Stock Market Analyzer  
**Course:** MA7098 Data Analysis for Business Intelligence (2024–25)  
**Presented by:** Dennis Noel  
**Supervisors:** Dr. Yanshan Shi & Prof. Valerio Lucarini

---

## 📚 Project Overview

This project builds a data-driven pipeline for analyzing the **Nasdaq-100 stock index** using feature engineering, dimensionality reduction, and clustering. The goal is to identify **natural market segments** and uncover **stock behavior patterns** beyond traditional sector classifications.

---

## 🚀 Workflow Summary

| Stage | Description |
|-------|-------------|
| **Data Collection** | Stock data fetched via Norgate. |
| **Preprocessing** | Log return normalization, ADF test for stationarity. |
| **Feature Engineering** | Computation of volatility and momentum over 5/10/20/30-day windows. |
| **Dimensionality Reduction** | PCA, t-SNE, and UMAP compared. PCA selected for performance and clarity. |
| **Clustering** | K-Means, Hierarchical, Spectral, and DBSCAN implemented. |
| **Interpretation** | Clusters analyzed by volatility, momentum, and sector composition. |
| **Presentation** | Visual insights and investment implications detailed in slides. |

---

## 📂 Repository Contents

- `Cells 1-6_v1.0.ipynb`  
  Loads feature data from `.npz` files, aggregates and saves the data in clean format.
  
- `Post PCA_v1.0.ipynb`  
  Handles imputation, standardization, PCA transformation, and saves the reduced dataset for clustering.

- `ppt_v3.0.pptx`  
  Summarizes the full workflow, cluster interpretation, and investment takeaways in a presentation format.

---

## 🧮 Feature Engineering

- **Volatility:** Calculated over 5/10/20/30-day windows.
- **Momentum:** Same intervals used. Top/bottom momentum stocks highlighted.
- **Correlation Matrices:** Constructed for all stock pairs based on momentum.
- **Additional Indicators:** RSI, Skewness, Kurtosis, and ADF test for stationarity.

---

## 📉 Dimensionality Reduction

- Compared PCA, t-SNE, and UMAP:
  - **PCA selected** for best performance:  
    - Captured 70% variance  
    - Best Silhouette (0.16), lowest Davies-Bouldin (1.47)  
    - Fastest runtime (0.007s vs 6.9s for UMAP)

---

## 🔗 Clustering Techniques

Implemented four unsupervised learning methods on PCA-reduced data:

| Algorithm       | Highlights |
|----------------|------------|
| **K-Means**     | Best separation (Silhouette = 0.296) |
| **Hierarchical**| Strong grouping, good dendrogram insights |
| **Spectral**    | Identified nuanced cluster boundaries |
| **DBSCAN**      | Flagged outliers and noise effectively |

---

## 📊 Cluster Insights

- **3 optimal clusters** (validated using 3 evaluation metrics).
- **Red Cluster**: Dominant group, high internal diversity (tech giants, market leaders).
- **Orange Cluster**: FinTech & digital services (e.g. COIN, SNOW).
- **Green Cluster**: Emerging tech (e.g. NIO, ARKK, PLTR).
- DBSCAN successfully highlighted **outlier stocks** with unique behaviors.

---

## 💡 Key Takeaways

- Stocks naturally segment beyond traditional sectors.
- Clustering reveals diversified investment strategies:
  - Red = Large caps & market leaders  
  - Orange = Cloud, data & FinTech  
  - Green = Disruptive innovators
- Portfolio diversification possible by combining stocks across clusters.
- Volatility and momentum are **partially correlated** (0.2654) but offer **complementary** insights.

---

## 🛠️ Technologies Used

- **Languages:** Python (Jupyter Notebooks)  
- **Libraries:** pandas, numpy, sklearn, matplotlib, seaborn  
- **Data Source:** Norgate premium data (Nasdaq-100, ^NDX)

---

## 📌 How to Run

1. Clone the repository.
2. Run `Cells 1-6_v1.0.ipynb` to load and process raw data.
3. Run `Post PCA_v1.0.ipynb` to apply PCA and reduce dimensions.
4. Use the results for clustering, visualization, and portfolio strategy design.

---

## 🧭 Future Enhancements

- Incorporate fundamentals (P/E, earnings) alongside technical indicators.
- Extend to other indices (e.g., S&P 500, Russell 2000).
- Deploy as a Streamlit dashboard for interactive exploration.
- Apply time-series clustering to capture temporal trends.

---
