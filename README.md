# MRD
MRD: High-fidelity synthetic LiDAR–camera data for off-road semantic segmentation
<!--
  ============================================================================
  AVMI DATASET — README SCAFFOLD
  How to use this file:
   - Fill every  <!-- TODO ... -->  comment and every  TBD  placeholder.
   - Delete a section only if it truly does not apply.
   - Section order is modeled on RELLIS-3D / GOOSE, adapted for a SYNTHETIC set.
   - On GitHub, heading levels (#, ##, ###) control the "fonts"/sizes.
  ============================================================================
-->

<div align="center">

<!-- TODO: add lab / university logos. Put image files in an images/ folder. -->
<!-- <img src="images/university_logo.png" height="70"/> &nbsp; <img src="images/lab_logo.png" height="70"/> -->

# AVMI: <!-- TODO: full dataset name, e.g. "A Synthetic Multimodal Dataset for Off-Road UGV Perception" -->

**<!-- TODO: one-line tagline, e.g. "High-fidelity synthetic LiDAR–camera data for off-road semantic segmentation" -->**

<!-- TODO: authors and affiliations -->
Author One<sup>1</sup>, Author Two<sup>2</sup>, Author Three<sup>1</sup>
<br>
<sup>1</sup> Affiliation One &nbsp;&nbsp; <sup>2</sup> Affiliation Two

<!-- Badges: replace the # links once you have them -->
[![Paper](https://img.shields.io/badge/Paper-arXiv-b31b1b.svg)](#)
[![Website](https://img.shields.io/badge/Project-Website-1f6feb.svg)](#)
[![Download](https://img.shields.io/badge/Data-Download-2ea44f.svg)](#)
[![License](https://img.shields.io/badge/License-TBD-lightgrey.svg)](#license)

</div>

---

## Table of Contents
- [Updates](#updates)
- [Overview](#overview)
  - [Generation Pipeline](#generation-pipeline)
  - [Simulated Sensor Setup](#simulated-sensor-setup)
- [Folder Structure](#folder-structure)
- [Annotated Data](#annotated-data)
  - [Ontology / Classes](#ontology--classes)
  - [Dataset Statistics](#dataset-statistics)
  - [Download](#download)
- [Benchmarks](#benchmarks)
- [Getting Started](#getting-started)
- [Full Data Download](#full-data-download)
- [Citation](#citation)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Related Work](#related-work)

---

## Updates
<!-- Newest first. Keep the format: MM/DD/YYYY  short note (version) -->
- **MM/DD/YYYY** — v1.0 initial release.
- **MM/DD/YYYY** — <!-- TODO: e.g. added LiDAR labels in SemanticKITTI format -->

---

## Overview

<!-- TODO: 1 short paragraph. What AVMI is, that it is SYNTHETIC, the engine used,
     the modalities (RGB + LiDAR + IMU/GPS), the scale, and your headline result. -->
AVMI is a **synthetic** multimodal dataset for off-road, unstructured-environment
perception, generated in TBD (engine). It provides paired **RGB images** and
**LiDAR point clouds** with automatic **2D pixel** and **3D per-point** semantic
labels across **N** classes, plus **IMU/GPS** streams. TBD (one-line headline result).

<!-- TODO: teaser figure (RGB | label | point cloud). -->
<!-- ![AVMI data example](images/data_example.png) -->

<!-- OPTIONAL: short comparison to existing datasets (link to your full table). -->
| Dataset | Real/Syn | Modalities | #Classes | 2D/3D labels |
|---|---|---|---|---|
| RUGD | Real | RGB | 24 | 2D |
| RELLIS-3D | Real | RGB + LiDAR | 20 | 2D + 3D |
| GOOSE | Real | RGB + LiDAR | 64 | 2D + 3D |
| **AVMI (ours)** | **Synthetic** | **RGB + LiDAR + IMU/GPS** | **TBD** | **2D + 3D (auto)** |

### Generation Pipeline
<!-- This is your core novelty — describe how the data is made. -->
- **Engine / simulator:** TBD
- **Environment assets / source:** TBD
- **Scene construction:** TBD (biomes, terrain generation)
- **Domain randomization:** TBD (lighting, weather, vegetation density, materials)
- **Data-collection agent:** TBD (trajectory / autonomous capture)
- **Automatic annotation:** TBD (how 2D + 3D ground truth is produced)

<!-- ![Generation pipeline](images/pipeline.png) -->

### Simulated Sensor Setup
<!-- Fill the table with AVMI's virtual sensors. Match real rigs where possible. -->

| Sensor | Model emulated | Key specs | Rate (Hz) |
|---|---|---|---|
| LiDAR | TBD | TBD channels, TBD horiz. res, TBD° vFOV, TBD m range | TBD |
| Camera (RGB) | TBD | TBD resolution, TBD° FOV, mono/stereo | TBD |
| IMU | TBD | TBD | TBD |
| GPS/GNSS | TBD | TBD | TBD |

- **Calibration (intrinsics / extrinsics):** exact, exported from simulation.
- **Synchronization:** all streams sim-synchronized (shared clock).

<!-- ![Sensor setup](images/sensor_setup.png) -->

---

## Folder Structure
<!-- Update the tree to match your actual release layout. -->
```
AVMI
├── train.lst                 -- list of training frame ids
├── val.lst                   -- list of validation frame ids
├── test.lst                  -- list of test frame ids
├── ontology.yaml             -- class ids, names, and color map
├── calib/                    -- intrinsics + LiDAR–camera extrinsics
└── 00000/                    -- sequence / scene id
    ├── image/                -- RGB images (.png)
    ├── image_label_id/       -- 2D label maps, class-id encoded (.png)
    ├── image_label_color/    -- 2D label maps, color encoded (.png)
    ├── lidar_bin/            -- point clouds (KITTI .bin)
    ├── lidar_label/          -- 3D per-point labels (.label)
    ├── imu.txt               -- IMU stream
    ├── gps.txt               -- GPS/GNSS stream
    └── poses.txt             -- per-frame poses
```

---

## Annotated Data

### Ontology / Classes
<!-- TODO: list AVMI's classes; keep them mappable to RELLIS/GOOSE for cross-dataset eval. -->
AVMI defines **N** semantic classes (+ void).

| ID | Class | Color (R,G,B) |
|---|---|---|
| 0 | void | 0,0,0 |
| 1 | TBD | TBD |
| 2 | TBD | TBD |
| … | … | … |

**Ontology definition:** [Download](#) <!-- link ontology.yaml -->

### Dataset Statistics
<!-- TODO: counts + class-distribution figures. -->
- **Annotated images:** TBD
- **Annotated point clouds:** TBD
- **Scenes / sequences:** TBD
- **Split (train / val / test):** TBD / TBD / TBD

<!-- ![Class distribution](images/class_distribution.png) -->

### Download
<!-- Provide per-modality links so users can grab only what they need. -->
| Content | Size | Link |
|---|---|---|
| Sample (small) | TBD | [Download](#) |
| RGB images | TBD | [Download](#) |
| 2D labels (id + color) | TBD | [Download](#) |
| LiDAR point clouds | TBD | [Download](#) |
| 3D labels | TBD | [Download](#) |
| Calibration | TBD | [Download](#) |
| Split files | TBD | [Download](#) |

---

## Benchmarks
<!-- Report per-class IoU + mIoU. Add rows as you run models. -->

### Image Semantic Segmentation
| Model | mIoU | Notes |
|---|---|---|
| TBD | TBD | TBD |

### LiDAR Semantic Segmentation
| Model | mIoU | Notes |
|---|---|---|
| TBD | TBD | TBD |

### Sim-to-Real (headline result)
<!-- Train on AVMI (synthetic), test on a REAL set; compare to a real-trained baseline. -->
| Train set | Test set | Model | mIoU |
|---|---|---|---|
| AVMI (synthetic) | RELLIS-3D (real) | TBD | TBD |
| RELLIS-3D (real) | RELLIS-3D (real) | TBD | TBD (baseline) |

**Reproduce:** see [`benchmarks/`](#) for configs and instructions.

---

## Getting Started

### Requirements
```bash
# TODO: pin your versions
python >= 3.9
pip install -r requirements.txt   # torch, numpy, opencv-python, open3d, pyyaml, ...
```

### Load a sample
```python
# Minimal example — adapt paths to your release.
import cv2, numpy as np

img   = cv2.imread("AVMI/00000/image/000000.png")
label = cv2.imread("AVMI/00000/image_label_id/000000.png", cv2.IMREAD_GRAYSCALE)
cloud = np.fromfile("AVMI/00000/lidar_bin/000000.bin", dtype=np.float32).reshape(-1, 4)  # x,y,z,intensity
pts   = np.fromfile("AVMI/00000/lidar_label/000000.label", dtype=np.uint32)              # per-point class id

print(img.shape, label.shape, cloud.shape, pts.shape)
```

### Visualize
<!-- TODO: point to any viewer / script you provide (e.g. Open3D, CloudCompare). -->

---

## Full Data Download
<!-- Single access link (Google Drive / Hugging Face / institutional host). -->
**Access:** [Download AVMI](#)

> Note: if hosting on Google Drive, large files may be rate-limited — mention a retry/email fallback.

---

## Citation
<!-- Update once the paper is public. -->
```bibtex
@article{avmi2026,
  title   = {AVMI: TBD full title},
  author  = {TBD},
  journal = {TBD},
  year    = {2026}
}
```

---

## License
<!-- TODO: pick and state a license (e.g. CC BY-NC-SA 4.0). Add a LICENSE file too. -->
This dataset is released under **TBD**. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgements
<!-- Funding, collaborators, asset sources, compute (e.g. HPC cluster). -->
TBD

---

## Related Work
<!-- Link the datasets you compare against. -->
- [RELLIS-3D](https://github.com/unmannedlab/RELLIS-3D)
- [RUGD](http://rugd.vision/)
- [GOOSE](https://goose-dataset.de/)
- TBD
