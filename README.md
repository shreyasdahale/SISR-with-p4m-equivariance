# Exploring p4m Equivariance in Image Processing Models

This repository contains the implementation of a study exploring the impact of **p4m equivariance** on convolutional neural networks (CNNs) for image processing tasks. Specifically, the tasks involve **image denoising** and **4x single image super-resolution (SISR)**. The project leverages the `e2cnn` library to incorporate group symmetry in CNNs and compares performance between a standard CNN and its p4m-equivariant variant.

## Project Highlights

- **Dual-Task Model**: 
  - Designed a CNN to perform **image denoising** and **4x resolution enhancement** simultaneously.
  
- **p4m Equivariance**: 
  - Integrated p4m group symmetry into the second model using the `e2cnn` library, significantly reducing parameter space while maintaining superior texture and line preservation.

- **Augmented Training Dataset**:
  - Expanded the training dataset by applying **4 90-degree rotations** and **mirror reflections**, increasing the dataset size by 8x.

- **Performance Comparison**:
  - **Baseline CNN (without p4m)**: 2,441,011 parameters.
  - **p4m-Equivariant CNN**: 1,878,515 parameters (~25% reduction).
  - The **p4m-equivariant model achieved a PSNR score of approximately 36**, demonstrating superior image quality with enhanced texture and line preservation.

---

## Repository Structure

```plaintext
.
├── sisr.ipynb               # Notebook for baseline CNN (without p4m equivariance)
├── sisr-p4m.ipynb           # Notebook for p4m-equivariant CNN
├── model.pth                # Trained model (baseline CNN)
├── modelp4m.pth             # Trained model (p4m-equivariant CNN)
├── README.md                # Project documentation
```

---

## Getting Started

### Prerequisites

- Python 3.8+
- Libraries:
  - PyTorch
  - e2cnn
  - NumPy
  - Matplotlib
  - cv2
  - PIL

Install the required dependencies:

```bash
pip install torch e2cnn numpy matplotlib
```

---

### Running the Notebooks

1. **Baseline Model**: Open and run `sisr.ipynb` to explore the baseline CNN without p4m equivariance.
2. **p4m-Equivariant Model**: Open and run `sisr-p4m.ipynb` for the p4m-equivariant CNN implementation.

Each notebook contains detailed explanations of the architecture, training process, and performance evaluation.

---

## Results

### Parameter Comparison

| Model                  | Parameters   | Key Features                     |
|------------------------|--------------|-----------------------------------|
| Baseline CNN           | 2,441,011    | Standard convolutional layers    |
| p4m-Equivariant CNN    | 1,878,515    | Leverages p4m group symmetry     |

### Performance Metrics

- **Baseline Model**: Slightly lower output quality with more parameters.
- **p4m-Equivariant Model**:
  - Achieved a **PSNR score of ~36**, highlighting improved output quality.
  - **25% reduction in parameter space**.
  - Demonstrated **better texture preservation** and **sharper lines**, especially on augmented datasets.

---

## Model Weights

- **Baseline Model**: [Download `model.pth`](./model.pth)
- **p4m-Equivariant Model**: [Download `modelp4m.pth`](./modelp4m.pth)

---

## References

- **e2cnn Library**: [https://github.com/QUVA-Lab/e2cnn](https://github.com/QUVA-Lab/e2cnn)
- Dataset augmentation techniques for symmetry-aware training.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

Feel free to suggest improvements or raise issues in the repository!

--- 
