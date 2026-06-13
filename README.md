# 🖼️ CIFAR-10 Image Classification with MobileNetV2

A deep learning image classifier built using **Transfer Learning (MobileNetV2)** on the CIFAR-10 dataset — part of the **InternSpark AI Internship Task 2**.

---

## 📌 Project Overview

This project implements an image classification model that:
- Uses **MobileNetV2** pretrained on ImageNet (Transfer Learning)
- Applies **data augmentation** (flip, rotation, zoom) during training
- Trains on the **CIFAR-10** dataset (10 classes, 60,000 images)
- Plots **training curves** (accuracy & loss)
- Provides an **inference script** to classify any image

---

## 🗂️ Project Structure

```
cifar10-image-classifier/
│
├── notebook/
│   └── train.ipynb                  # Training notebook with full pipeline
│
├── model/
│   └── cifar10_mobilenetv2.keras    # Saved trained model
│
├── images/
│   └── training_curves.png          # Accuracy & loss plots
│
├── sample/
│   └── OIP.jpg                      # Sample image for inference
│
├── inference.py                     # Script to run predictions on new images
├── requirements.txt                 # Python dependencies
└── README.md
```

---

## 🧠 Model Architecture

| Component | Details |
|---|---|
| Base Model | MobileNetV2 (pretrained on ImageNet) |
| Input Shape | 32×32×3 → resized to 96×96 internally |
| Data Augmentation | Random Flip, Rotation (0.1), Zoom (0.1) |
| Classification Head | GlobalAveragePooling2D → Dropout(0.2) → Dense(10, softmax) |
| Optimizer | Adam (lr=0.001) |
| Loss | Sparse Categorical Crossentropy |
| Epochs | 5 |
| Batch Size | 64 |

---

## 📊 CIFAR-10 Classes

`airplane` · `automobile` · `bird` · `cat` · `deer` · `dog` · `frog` · `horse` · `ship` · `truck`

---

## 📈 Training Curves

![Training Curves](images/training_curves.png)

---

## ⚙️ Setup & Installation

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/cifar10-image-classifier.git
cd cifar10-image-classifier
```

### 2. Create and activate a virtual environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

---

## 🚀 How to Run

### Training
```bash
jupyter notebook
```
Open `notebook/train.ipynb` and run all cells. The model will be saved to `model/cifar10_mobilenetv2.keras`.

### Inference (predict a single image)
```bash
python inference.py --image_path sample/OIP.jpg
```

**Expected output:**
```
Image: sample/OIP.jpg
Predicted Class: dog
Confidence: 87.43%
```

You can replace `sample/OIP.jpg` with any image path on your machine.

---

## 🛠️ Technologies Used

- Python 3.x
- TensorFlow / Keras
- MobileNetV2 (Transfer Learning)
- matplotlib, numpy, Pillow
- Jupyter Notebook

---

## 👤 Author

Internship Project — InternSpark | Artificial Intelligence Domain | Task 2
