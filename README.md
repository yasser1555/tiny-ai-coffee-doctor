# Tiny AI Coffee Doctor ☕

**Deep Learning · Computer Vision · Efficient AI · Model Quantization**

A research project investigating the trade-offs between classification performance, model size, and CPU inference efficiency for coffee-leaf disease recognition.

**Status:** Experimental Results Obtained — Further Validation in Progress  
**Source Code:** Not Included in This Showcase

## Research Objective

The project investigates whether CBAM attention improves the classification performance of MobileNetV3-Small and whether INT8 quantization reduces deployment size without significantly degrading accuracy.

The task covers five conditions:

Healthy, Miner, Rust, Cercospora, and Phoma.

## Experimental Models

| Model | Approach |
|---|---|
| M0 | MobileNetV3-Small baseline |
| M1 | MobileNetV3-Small with CBAM attention |
| M2 | Selective and full INT8 quantization of M1 |

## Preliminary Validation Results

| Model | Macro-F1 | ONNX Size |
|---|---:|---:|
| M0 — FP32 | 98.08% | 5.82 MiB |
| M1 — CBAM FP32 | 95.82% | 5.98 MiB |
| M2 — Selective INT8 | 95.82% | 4.29 MiB |
| M2 — Full INT8 | 17.37% | 1.70 MiB |

The experiments showed that CBAM did not improve validation performance over the baseline.

Selective INT8 reduced the CBAM model's file size by approximately 28.22%, but did not improve measured CPU latency in the reported recovery session.

## Dataset & Evaluation

The project uses JMuBEN and JMuBEN2 coffee-leaf datasets.

Dataset auditing revealed substantial image duplication and limited digitally unique samples in the Healthy class. Consequently, the current validation results are provisional.

A reserved test set of 558 images was held for later evaluation.

## Technologies

Python, PyTorch, MobileNetV3-Small, CBAM, ONNX Runtime, INT8 Quantization, Google Colab.

## Research Status & Next Steps

- Improve source-image independence checks.
- Evaluate on reserved and external datasets.
- Compare class-specific errors and generalization.
- Perform consistent CPU benchmarking on the same hardware.
- Investigate quantization-related accuracy and latency trade-offs.

**Research limitation:** Validation accuracy does not establish reliable diagnosis on unseen real-world leaf photographs.

## Academic Contribution

The project was formally documented under a university group assignment.

**Yasser Alassad independently carried out the technical experimentation and implementation**, as described by the developer. The academic group context is acknowledged separately.

## Developer

**Yasser Alassad**  
Computer Science — Artificial Intelligence Specialization  
Effat University

[GitHub](https://github.com/yasser1555) · [LinkedIn](https://www.linkedin.com/in/yasser-alassad/) · [Portfolio](https://yasser-alassad-portfolio.vercel.app/)
