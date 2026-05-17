# 🖼️ Part 2: Computer Vision – CNN-Based Defect Classification

## 📌 Overview

This project focuses on building a Convolutional Neural Network (CNN) to classify product images into different defect categories. The objective is to understand how CNNs learn visual patterns using convolution, pooling, and dense layers.

---

## 🎯 Problem Statement

The task is to classify images into one of four categories:

* Normal
* Scratch
* Dent
* Stain

This is a **multi-class image classification problem**, where each image belongs to exactly one class.

---

## 📂 Dataset

### 📂 Setup Instructions

The dataset is not included in this repository as per submission guidelines.

Please download the dataset from the following link:

👉 https://drive.google.com/drive/folders/1akV6po4Nrgkc3yQrJkzA6cJlV-wBvUYs

### 📁 Setup Steps:

1. Download the dataset
2. Extract the files
3. Place the `images` folder inside the project directory

Final structure should look like:

part-2-cnn-computer-vision/
├── notebook.ipynb
├── README.md
├── images/
│   ├── normal/
│   ├── scratch/
│   ├── dent/
│   └── stain/

---

The dataset consists of images organized into four folders:

* `images/normal/`
* `images/scratch/`
* `images/dent/`
* `images/stain/`

Each folder contains images corresponding to a specific defect type.
### ⚠️ Note

If the dataset is not present, the notebook will not run and will prompt the user to download it.

---

## 🔍 Dataset Exploration

* Total classes: **4**
* Images per class were analyzed using directory structure
* Sample images were visualized to understand defect patterns
* Images are RGB with consistent dimensions (resized during preprocessing)

### ⚖️ Observation:

* Dataset is (balanced / slightly imbalanced — update based on your output)

---

## ⚙️ Image Preprocessing

The following preprocessing steps were applied:

* **Resizing**: All images resized to 128 × 128 pixels
* **Normalization**: Pixel values scaled to range [0, 1]
* **Train-Validation Split**: 80% training, 20% validation
* **Data Augmentation**:

  * Rotation
  * Zoom
  * Horizontal flip

These steps help improve model generalization and stability.

---

## 🤖 CNN Model Architecture

A Convolutional Neural Network (CNN) was built using TensorFlow/Keras.

### 🧱 Model Structure:

* Convolution Layer (32 filters, ReLU)
* MaxPooling Layer
* Convolution Layer (64 filters, ReLU)
* MaxPooling Layer
* Convolution Layer (128 filters, ReLU)
* MaxPooling Layer
* Flatten Layer
* Dense Layer (128 neurons, ReLU)
* Output Layer (4 neurons, Softmax)

---

## 📊 Model Training & Evaluation

* Model trained for multiple epochs using training data
* Validation data used to monitor performance

### 📈 Results:

* Training Accuracy: 0.43380001187324524
* Validation Accuracy: 0.8333333134651184

### 🔍 Confusion Matrix:

* Most predictions are correctly classified
* Minor misclassification may occur between similar defect types

### 🖼️ Sample Predictions:

* Model predictions were visualized on sample images
* Correct classification observed for most cases


## 🧠 CNN Concept Explanation

### 🔹 What is Convolution?

Convolution is a process where a small filter (kernel) slides over an image to detect patterns such as edges, textures, or shapes.

* It helps the model focus on important features in different parts of the image
* Each filter learns a specific pattern (e.g., scratch lines or edges)

👉 In simple terms:
**Convolution = scanning the image to find useful patterns**

---

### 🔹 Why is Pooling Used?

Pooling reduces the size of feature maps while keeping the most important information.

* It makes the model faster and more efficient
* It helps reduce overfitting
* It keeps only the strongest features

👉 Example: MaxPooling takes the highest value from a region

👉 In simple terms:
**Pooling = shrinking the image while keeping important details**

---

### 🔹 Why is ReLU Commonly Used in CNNs?

ReLU (Rectified Linear Unit) replaces negative values with zero.

* It helps the model learn faster
* It avoids problems like vanishing gradients
* It introduces non-linearity, allowing the model to learn complex patterns

👉 Formula:
ReLU(x) = max(0, x)

👉 In simple terms:
**ReLU = keep useful signals, remove noise**

---

### 🔹 Why are CNNs Better than Regular Neural Networks for Images?

CNNs are designed specifically for image data.

* They capture **spatial relationships** (how pixels are arranged)
* They use fewer parameters compared to fully connected networks
* They automatically detect features (edges, shapes, patterns)

In contrast:

* Regular neural networks treat images as flat data (lose structure)
* They require more parameters and are less efficient

👉 In simple terms:
**CNNs understand images better because they preserve image structure**

---

### 🚀 Summary

* Convolution extracts features
* Pooling reduces size and keeps important information
* ReLU helps the model learn efficiently
* CNNs are optimized for image data and outperform regular networks in vision tasks


## 🏭 Business Use Case Mapping

### 🔹 Application in Manufacturing (Quality Inspection)

This computer vision solution can be applied in the manufacturing industry for **automated defect detection and quality control**.

In traditional manufacturing, quality inspection is often done manually, which is:

* Time-consuming
* Prone to human error
* Not scalable

Using a CNN-based image classification model:

* Products can be automatically classified as:

  * Normal
  * Scratch
  * Dent
  * Stain

### 📊 Benefits:

* Faster inspection process
* Reduced human error
* Consistent quality standards
* Real-time defect detection on production lines

### 🚀 Real-World Impact:

Such systems can be integrated with cameras on assembly lines to:

* Identify defective products instantly
* Trigger alerts or remove defective items
* Improve overall production efficiency

---

### 💡 Conclusion

CNN-based computer vision models enable scalable and accurate quality inspection, making them highly valuable in modern manufacturing systems.
