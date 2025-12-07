# 🍇 Multispectral Grape Variety Classification

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn%20%7C%20NumPy%20%7C%20Matplotlib-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
This project focuses on the classification of seedless grape varieties using **Multispectral Imaging** techniques. Unlike standard RGB images, multispectral data captures specific wavelength ranges across the electromagnetic spectrum, allowing for the extraction of information invisible to the human eye (e.g., chemical composition, internal quality).

Using the **Bueda Dataset**, I analyzed the impact of different vegetation indices (**NDVI, EVI, SAVI**) on model accuracy and demonstrated how feature stacking can significantly improve classification performance.

## 📂 Dataset: Bueda
* **Source:** Bueda Multispectral Dataset
* **Content:** 37-band images (12 Visible Light + 25 Infrared)
* **Classes (5 Varieties):** Autumn Royal, Crimson Seedless, Itum4, Itum5, Itum9
* **Image Dimensions:** Resized to 140x200 pixels
* **Wavelengths:**
    * VIS: 488.38 nm - 625.71 nm
    * IR: 676.25 nm - 952.76 nm

## ⚙️ Methodology & Indices
The core of this project involves extracting vegetation indices to assess plant health and density, which serve as features for the Machine Learning model.

### 1. NDVI (Normalized Difference Vegetation Index)
Used to determine the density of green on a patch of land.
$$NDVI = \frac{(NIR - RED)}{(NIR + RED)}$$

### 2. EVI (Enhanced Vegetation Index)
Optimized to correct for soil signals and atmospheric influences.
$$EVI = G \times \frac{(NIR - RED)}{(NIR + C1 \times RED - C2 \times BLUE + L)}$$

### 3. SAVI (Soil-Adjusted Vegetation Index)
A modification of NDVI to correct for the influence of soil brightness.
$$SAVI = \frac{(NIR - RED)}{(NIR + RED + L)} \times (1 + L)$$

## 🚀 Model & Results
I used a **Random Forest Classifier** to train the model in two stages:
1.  **Individual Indices:** Training using only one index type at a time.
2.  **Combined Features:** Stacking all indices to create a rich feature set.

| Feature Used | Accuracy Score |
| :--- | :--- |
| **EVI Only** | 54% |
| **NDVI Only** | 57% |
| **SAVI Only** | 57% |
| **Combined (All Features)** | **87%** 🏆 |

> **Key Insight:** While individual indices provide limited information for classification (~57% accuracy), combining spectral features allows the model to capture complex patterns, boosting accuracy to **87%**.

## 📊 Visualizations

*(Place your 'NDVI Visualization' image here - e.g., images/ndvi_vis.png)*
*Visualization of spectral bands and NDVI transformation.*

*(Place your 'Accuracy Comparison' bar chart here - e.g., images/accuracy_chart.png)*
*Comparison of model accuracy across different feature sets.*


