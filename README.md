# **Medical Image Segmentation using Fuzzy Clustering Techniques**
This project explores the application of fuzzy clustering techniques for medical image segmentation, particularly for MRI scans. The primary objective is to improve segmentation accuracy by incorporating **Spatial Neighborhood Information (SNI)** into Fuzzy C-Means (FCM) clustering, reducing the impact of noise while preserving crucial structural details.

## **Project Overview**
- **Course:** CS-GY 6643: Computer Vision (Spring 2024)
- **Instructor:** Guido Gerig
- **Authors:** Inder Khatri, Erkang Xia, Aditya Mittal
- **Dataset:** BrainWeb MRI dataset (181×217×181 resolution)
- **Goal:** Improve segmentation robustness by modifying the objective function of FCM clustering.

## **Features**
- Implements **standard FCM**, **FCM with spatial information (FCM-S)**, and **FCM with mean and median filtering (FCM-S1, FCM-S2)**.
- Enhances segmentation performance under different noise levels (1%, 5%, 9%).
- Uses **Mean and Median Filtering** for computational efficiency.
- Evaluates segmentation accuracy using **Dice Coefficient** and **Average Segmentation Accuracy (ASA)**.
- Provides a modular pipeline for **preprocessing, clustering, and performance evaluation**.

## **Installation**
### **1. Clone the Repository**
```bash
git clone https://github.com/theadityamittal/MRI-Segmentation.git
cd MRI-Segmentation
```

### **2. Create a Virtual Environment (Optional but Recommended)**
```bash
python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate  # On Windows
```

### **3. Install Dependencies**
```bash
pip install -r requirements.txt
```

## **Usage**
### **Running the Jupyter Notebook**
1. Ensure you have Jupyter installed.
2. Start Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
3. Open **notebook.ipynb** and run the cells sequentially.

## **Methods and Implementation**
### **1. Data Preprocessing**
- MRI images are normalized.
- Noise is handled using **mean and median filtering** before segmentation.

### **2. Fuzzy Clustering Algorithms**
- **Standard FCM**: Assigns fuzzy memberships based on pixel intensity.
- **FCM-S**: Incorporates **spatial neighborhood information** into segmentation.
- **FCM-S1 & FCM-S2**: Approximate spatial information using **mean and median filtering** to optimize speed.

### **3. Performance Evaluation**
- **Dice Coefficient**: Measures segmentation overlap with ground truth.
- **ASA (Average Segmentation Accuracy)**: Quantifies clustering performance.

## **Results**
| **Noise Level** | **FCM** | **FCM-S** | **FCM-S1** | **FCM-S2** |
|---------------|-------|--------|--------|--------|
| **1%**        | **99.2%** | **97.9%** | 95.5% | 96.4% |
| **5%**        | **97.3%** | **97.1%** | 95.5% | 96.1% |
| **9%**        | **92.4%** | **95.6%** | 94.6% | 95.0% |

- **FCM-S outperforms standard FCM by 3.25% in high-noise conditions (9%).**
- **Mean and Median Filtering reduce computation time by 20% without significant accuracy loss.**

## **Dependencies**
- Python 3.8+
- NumPy
- SciPy
- OpenCV
- Matplotlib
- scikit-learn
- Jupyter Notebook

## **License**
This project is licensed under the MIT License.
