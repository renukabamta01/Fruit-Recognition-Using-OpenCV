# 🍎 Fruit Recognition Using OpenCV & Machine Learning


## 📌 Project Overview

Fruit Recognition is a Machine Learning classification project that identifies different types of fruits from images using OpenCV and Scikit-learn.

The project classifies fruit images into four categories:

- Apple
- Banana
- Mango
- Orange

The main objective is to perform image preprocessing using OpenCV, extract pixel values from images, and train machine learning models to recognize different fruits.

## 🎯 Project Objectives


- Read and process fruit images using OpenCV.
- Convert images into grayscale.
- Resize images into a fixed dimension of 28 × 28 pixels.
- Flatten images into one-dimensional arrays.
- Create a structured dataset using Pandas.
- Train and evaluate machine learning classification models.
- Predict fruit categories from new images.

## 🛠️ Technologies & Libraries Used


- Python
- OpenCV
- NumPy
- Pandas
- Scikit-learn
- Jupyter Notebook

## 📂 Dataset Description


The dataset contains 120 fruit images divided into four categories.

| Fruit Category | Number of Images |
| -------------- | ---------------: |
| Apple          |               30 |
| Banana         |               30 |
| Mango          |               30 |
| Orange         |               30 |
| **Total**      |          **120** |

### Dataset Structure


```text
fruit_images_dataset/
│
├── Apple/
├── Banana/
├── Mango/
└── Orange/
```

## ⚙️ Project Workflow

### 1. Data Extraction


- Extracted the fruit image dataset from a ZIP file using Python's `zipfile` module.
- Organized images into four fruit categories.

### 2. Image Preprocessing


Performed the following preprocessing operations using OpenCV:

- **Grayscale Conversion:** Converted colored images into grayscale using `cv2.imread(image, 0)`.
- **Image Resizing:** Resized all images to 28 × 28 pixels using `cv2.resize()`.
- **Flattening:** Converted 2D image arrays into 1D arrays using `flatten()`.

Each image generates 784 pixel values (28 × 28), which are used as input features for machine learning models.

### 3. Dataset Creation


- Stored flattened pixel values in a Pandas DataFrame.
- Created a separate label column containing fruit categories.
- Combined pixel features and labels into a single dataset.

**Final Dataset Shape:** 120 rows × 785 columns.

### 4. Train-Test Split


Divided the dataset into training and testing sets:

- Training Data: 80% (96 images)
- Testing Data: 20% (24 images)

Used `train_test_split()` with `random_state=42` and `stratify=y`.

### 5. Model Training


Implemented and compared two supervised machine learning classification algorithms:

- K-Nearest Neighbors (KNN)
- Decision Tree Classifier

### 6. Model Evaluation


Evaluated both models using the Accuracy Score.

| Algorithm                | Accuracy |
| ------------------------ | -------: |
| K-Nearest Neighbors      |   79.17% |
| Decision Tree Classifier |     100% |

The Decision Tree Classifier achieved the highest accuracy on the test dataset.

### 7. Fruit Prediction


Created a custom prediction function that:

1. Accepts an image path.
2. Reads the image in grayscale.
3. Resizes it to 28 × 28 pixels.
4. Flattens the image into 784 pixel values.
5. Predicts the fruit category using the trained Decision Tree model.

## 📊 Results


The Decision Tree Classifier achieved 100% accuracy on the 24 test images, while KNN achieved 79.17%.

The prediction function was also tested with new image paths from the dataset.

**Sample Predictions:**

| Input Image    | Predicted Output |
| -------------- | ---------------- |
| banana_012.jpg | Banana           |
| mango_018.jpg  | Mango            |

*Note: The dataset is relatively small, so further testing with more independent images is required to evaluate generalization.*

## 🚀 How to Run the Project


1. Clone the repository:

```bash
git clone https://github.com/your-username/Fruit-Recognition-OpenCV.git
```

2. Navigate to the project folder:

```bash
cd Fruit-Recognition-OpenCV
```

3. Install the required libraries:

```bash
pip install opencv-python numpy pandas scikit-learn jupyter
```

4. Extract the dataset ZIP file and update the dataset paths in the notebook according to your system.

5. Open Jupyter Notebook:

```bash
jupyter notebook
```

6. Open `Fruit_Recognition_OpenCV.ipynb` and run the cells sequentially.

## 💡 Key Learnings


- Understanding basic image processing using OpenCV.
- Working with grayscale images and pixel values.
- Understanding image resizing and flattening.
- Converting image data into a structured DataFrame.
- Understanding supervised machine learning classification.
- Training and comparing KNN and Decision Tree models.
- Making predictions on fruit images.
