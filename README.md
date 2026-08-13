# 📊 CUSUM Paper Experiments  
### Roland Bolboaca · MIT License  

This repository contains the experimental code and dataset references for the paper:

**"Cumulative Sums Robustness and Resilience in the Context of Time Series Anomaly Detection"**  
(*To appear in: Journal, 2026*)  

## 📚 Citation

If you use this code or dataset in your research, please cite the article:

```bibtex
@Article{rolandcusumbib,
  AUTHOR = {Bolboacă, Roland },
  TITLE = {Cumulative Sums Resilience and Robustness in the Context of Time Series Anomaly Detection},
  JOURNAL = {Quality and Reliability Engineering International, Wiley},
  VOLUME = {},
  YEAR = {2026},
  NUMBER = {},
  ARTICLE-NUMBER = {},
  URL = {},
  ISSN = {},
  DOI = {}
}
```
---

## 🧪 CUSUM Papers Referenced

- 📘 Page's Classical CUSUM (1st order, 2-sided) – [1954 Biometrika](https://doi.org/10.1093/biomet/41.1-2.100)  
- 📘 1-CUSUM Scheme (1st/2nd order, 1-sided) – [Wu & Wang, 2007](https://www.tandfonline.com/doi/abs/10.1080/00207540600792267)  
- 📘 ACUSUM with Hampel Control – [Akhtar et al., 2024](https://onlinelibrary.wiley.com/doi/pdf/10.1002/qre.3463)  
- 📘 Higher-Order CUSUM – [Pearson, 1976](http://www.mit.bme.hu/system/files/oktatas/targyak/9132/Nonlinear_Input_Output_Modeling.pdf)  
- 📘 UCUSUM Mean Shift – [Roman et al., 2021](https://www.mdpi.com/2079-9292/10/24/3161)  
- 📘 Variance-Shift CUSUM – [Bolboacă et al., 2019](https://ieeexplore.ieee.org/document/8959745)  

---

## 📁 Datasets Used

### 🔹 [TEP – Tennessee Eastman Process](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/6C3JR1)
- **Variables**: 55 (C1: Fault, C2: Simulation, C3: Sample, C4–C55: Process variables)  
- **Clean**: 500 simulations × 500 points = 250,000 samples  
- **Anomaly**: 500 simulations × 960 points = 480,000 samples  
- **Fault files**: 20  
- **Rate**: 3 minutes  
- 📖 [Exploration](https://keepfloyding.github.io/posts/data-explor-TEP-1/) | [Source](https://www.sciencedirect.com/science/article/pii/S0098135414000969?via%3Dihub)

---

### 🔹 [LBNL – Fault Detection and Diagnostics](https://faultdetection.lbl.gov/data/)
- **Variables**: 23 (C1: Time, C2–C23: Process variables)  
- **Clean & Anomaly**: 365 days × 1-min = 525,500 observations each  
- **Fault files**: 16  
- 📖 [PDF Description](https://fdddata.lbl.gov/data/Simulated_LBNL_FDD_Data_Sets_Boiler_Plant/LBNL_FDD_Data_Sets_Boiler_Plant.pdf)

---

### 🔹 [SKAB – Skoltech Anomaly Benchmark](https://www.kaggle.com/datasets/yuriykatser/skoltech-anomaly-benchmark-skab)
- **Variables**: 11  
- **Clean**: 9,406 observations  
- **Anomaly**: 3 types × 10 files each ≈ 1,100 observations/file  
- **Rate**: 1 second

---

### 🔹 [RMFD – Rotating Machine Fault Detection](https://www.kaggle.com/datasets/sumairaziz/vibration-faults-dataset-for-rotating-machines)
- **Variables**: 2 (Time, Acceleration)  
- **Clean**: 103 files × 5,000 observations  
- **Anomaly**: 117 files × 5,000 observations (100 fault files)  
- **Rate**: 1,000 Hz  

---

## 📈 Evaluation Metrics

- **FAR** – False Alarm Rate on normal data  
- **TPR** – True Positive Rate on anomalies  
- **DD** – Detection Delay (time until first anomaly detection)  

**Robustness Metrics**
- **Noise and outliers robustness score (NORS)** - The relative drop in performance compared to the baseline scenario (e.g., on the clean dataset without noise and/or outliers)

**Resilience Metrics**
- **Recovery Time (RT)** – Time to stabilize after detection  
- **Stability Time (ST)** - time until the decision statistic is stable for N consecutive samples

---

## ⚙️ Setup

```bash
pip install -r requirements.txt
```

## ▶️ Run Instructions

-   Execute Setup Functions Blocks
-   First time loading the data takes time. 
    - However, they are stored first in a dictionary for access to file names and everything.
    - Secondly in np arrays (this is way faster).

-   If you dont have the datasets:
    1.   You can download them from the links in the dataset section
    2.   You can load them from the pickle file!
    3.   You can generate them from the code in the dataset section
    4.   You can use the pkl files: np_all_data_..._.pkl.
        - They are already converted to np arrays (recommended). Place them in the dataset dir.
        
-   Play arround with the parameters in the Setup Functions Blocks
-   Play arround with the parameters in the lower blocks:
    -   Robustness and Resilience Experiments
    -   Dataset Params
    -   CUSUM Params
    -   Model Params
    -   Comparissons
-   Execute CUSUM Experiments
-   Execute Robustness and Resilience Experiments
-   Execute Anomaly Detection Experiments
-   Execute Comparissons
-   Execute Parameter Analysis
-   Execute Plotting
-   **Due to the enormity of the datasets and experiments, running times might be high!** 
-   Be patient or feel free to further optimize the code!

## 📚 References

### 📄 Paper
[1] Bolboaca R., *Cumulative Sums Resilience and Robustness in the Context of Time Series Anomaly Detection*, Journal: , 2025.  
➡️ *Link pending* (check Google Scholar)

### 📄 CUSUM Literature
- [2] Page ES., Biometrika, 1954 [[link](https://doi.org/10.1093/biomet/41.1-2.100)]
- [3] Wu & Wang, Int. J. Production Research, 2007 [[link](https://www.tandfonline.com/doi/abs/10.1080/00207540600792267)]
- [4] Akhtar et al., QREI, 2024 [[link](https://onlinelibrary.wiley.com/doi/pdf/10.1002/qre.3463)]
- [5] Pearson, 1976 [[link](http://www.mit.bme.hu/system/files/oktatas/targyak/9132/Nonlinear_Input_Output_Modeling.pdf)]
- [6] Roman et al., Electronics, 2021 [[link](https://www.mdpi.com/2079-9292/10/24/3161)]
- [7] Bolboacă et al., IEEE ICCP, 2019 [[link](https://ieeexplore.ieee.org/document/8959745)]
- [8] Pignatiello & Runger, JQT, 1990 [[link](https://courses.washington.edu/ie599/MCUSUM.pdf)]

---

## 🗃 Dataset References

- [9] Rieth et al., 2017 – [TEP Dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/6C3JR1)  
- [10] Granderson et al., 2022 – [LBNL Data](https://faultdetection.lbl.gov/data/)  
- [11] Katser & Kozitsin, 2020 – [SKAB](https://www.kaggle.com/datasets/yuriykatser/skoltech-anomaly-benchmark-skab)  
- [12] Kafeel et al., 2021 – [RMFD](https://www.kaggle.com/datasets/sumairaziz/vibration-faults-dataset-for-rotating-machines)  
- [13] Sarkar, 2025 – [VSD](https://www.kaggle.com/datasets/neuralsorcerer/voltage-signal-dataset)

---

## ⚖️ License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

---

## 👤 Authors

**Roland Bolboaca**  
