# Brain Tumor Classification Using Image Processing

## 📌 Overview

This project focuses on preprocessing brain MRI images and extracting meaningful image features for brain tumor classification.

The dataset contains four categories:

- **Glioma**
- **Meningioma**
- **Pituitary**
- **No Tumor**

The project uses image preprocessing techniques to improve image quality and then extracts **Histogram of Oriented Gradients (HOG)** features from the processed MRI images.

---

## 🎯 Objectives

The main objectives of this project are:

- Preprocess brain MRI images.
- Improve image contrast and quality.
- Remove unwanted noise from images.
- Apply image augmentation.
- Extract useful visual features using HOG.
- Prepare the extracted features for machine-learning-based classification.

---

## 🧠 Dataset

The dataset is organized into four classes:

```text
brain/
├── glioma/
├── meningioma/
├── pituitary/
└── no/

```

Each folder contains brain MRI images belonging to the corresponding class.

> **Note:** The dataset itself is not included in this repository.

---

## 🔬 Methodology

The project follows the pipeline below:

```text
Brain MRI Images
       ↓
Image Resizing
       ↓
Normalization
       ↓
Grayscale Conversion
       ↓
Histogram Equalization
       ↓
CLAHE Contrast Enhancement
       ↓
Gamma Correction
       ↓
Otsu Thresholding
       ↓
Morphological Operations
       ↓
Data Augmentation
       ↓
Median Filtering
       ↓
HOG Feature Extraction
       ↓
Train / Validation / Test Split
       ↓
Classification

```

---

## 🛠️ Image Preprocessing

Several preprocessing techniques are applied to the MRI images.

### 1. Image Resizing

Images are resized to:

```text
224 × 224 pixels

```

This provides a consistent input size for further processing.

### 2. Normalization

Pixel values are normalized using:

```python
image / 255.0

```

### 3. Histogram Equalization

Histogram equalization is applied to improve the distribution of image intensities and enhance image details.

### 4. CLAHE

**Contrast Limited Adaptive Histogram Equalization (CLAHE)** is used for adaptive contrast enhancement.

The implementation uses:

```python
clipLimit=2.0
tileGridSize=(8, 8)

```

### 5. Gamma Correction

Gamma correction is applied with:

```python
gamma = 1.5

```

This helps adjust the intensity of the processed image.

### 6. Otsu's Thresholding

Otsu's thresholding is used to convert the enhanced grayscale image into a binary image.

### 7. Morphological Operations

A morphological closing operation is applied using a:

```text
3 × 3 kernel

```

with two iterations.

### 8. Data Augmentation

Horizontal flipping is used as an example of image augmentation.

```python
A.HorizontalFlip(p=0.5)

```

### 9. Median Filtering

A median filter with kernel size `5` is applied to reduce noise.

---

## 📊 Feature Extraction

After preprocessing, **Histogram of Oriented Gradients (HOG)** is used to extract image features.

The HOG configuration used in the project is:

```python
orientations=9
pixels_per_cell=(8, 8)
cells_per_block=(2, 2)

```

The extracted HOG feature vector has the shape:

```text
(26244,)

```

HOG features describe local edge and gradient information within the MRI images.

---

## 💻 Technologies Used

- Python
- Google Colab
- OpenCV
- NumPy
- Albumentations
- Scikit-image
- Matplotlib / OpenCV visualization
- Google Drive

---

## 📦 Installation

Install the required Python libraries:

```bash
pip install numpy opencv-python albumentations scikit-image matplotlib

```

For Google Colab, the notebook also uses Google Drive:

```python
from google.colab import drive

drive.mount('/content/drive')

```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/your-username/brain-tumor-classification.git

```

### 2. Open the notebook

Open:

```text
AG3.ipynb

```

using Google Colab or Jupyter Notebook.

### 3. Prepare the dataset

Place the dataset in Google Drive and organize it into:

```text
brain/
├── glioma/
├── meningioma/
├── pituitary/
└── no/

```

### 4. Update the dataset path

Update the path in the notebook:

```python
folder_path = '/content/drive/MyDrive/brain'

```

### 5. Run the notebook

Execute the notebook cells sequentially to perform:

1. Dataset loading
2. Image preprocessing
3. Feature extraction
4. Dataset splitting
5. Feature generation

---

## 📁 Project Structure

```text
brain-tumor-classification/
│
├── AG3.ipynb
├── README.md
│
├── dataset/
│   ├── glioma/
│   ├── meningioma/
│   ├── pituitary/
│   └── no/
│
└── results/
    └── feature_outputs/

```

> The dataset and generated files can be excluded from Git using `.gitignore`.

---

## 🔄 Processing Pipeline

### Input

Brain MRI image:

```text
MRI Image

```

### Preprocessing

```text
Resize → Histogram Equalization → CLAHE
→ Gamma Correction → Otsu Thresholding
→ Morphological Closing → Augmentation
→ Median Filtering

```

### Feature Extraction

```text
Processed Image
       ↓
Grayscale Image
       ↓
HOG
       ↓
26244-dimensional Feature Vector

```

---

## 📈 Results

The notebook successfully performs HOG feature extraction on the MRI images.

Example output:

```text
HOG features extracted for <image_name>: (26244,)

```

The extracted features can subsequently be used as input to a machine-learning classifier for distinguishing between the four brain MRI categories.

---

## 🔮 Future Improvements

Possible improvements to the project include:

- Implementing a complete machine-learning classification pipeline.
- Comparing different classifiers such as SVM, Random Forest, and Logistic Regression.
- Using CNN/deep-learning-based feature extraction.
- Performing systematic hyperparameter optimization.
- Adding accuracy, precision, recall, F1-score, and confusion matrix evaluation.
- Creating a complete automated prediction system for new MRI images.
- Improving the preprocessing pipeline through experimental comparison.

---

## ⚠️ Disclaimer

This project is intended for **educational and research purposes only**.

It is not intended to provide medical diagnosis or replace professional medical advice.




Thanks to the developers and open-source community for providing these tools.
it look like over can you pls short little bit
