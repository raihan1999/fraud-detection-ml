# (Fraud Detection) Dengan Machine Learning [![Made with Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/[NAMA_USER_GITHUB]/[NAMA_REPO_LO]/blob/main/Fraud_Detection_Notebook.ipynb) [![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) 

Repositori ini berisi implementasi lengkap proyek Machine Learning untuk mendeteksi transaksi penipuan (fraud) berdasarkan data transaksi pengguna. Proyek ini mencakup seluruh alur kerja, mulai dari eksplorasi data, pra-pemrosesan, pelatihan model, hingga evaluasi performa. 

## 📝 Gambaran Proyek 

Tujuan utama dari proyek ini adalah untuk membangun model klasifikasi yang akurat dan andal untuk membedakan antara transaksi yang sah (legitimate) dan transaksi yang menipu (fraudulent). Dengan tingginya volume transaksi digital, deteksi fraud secara otomatis menjadi sangat krusial untuk meminimalkan kerugian finansial. 

## 💾 Dataset 

Dataset yang digunakan (`data2.csv`) berisi atribut-atribut transaksi pengguna sebagai berikut: 
|Atribut|Tipe Data|Deskripsi|
|--|--|---------------------|
|Profession|Kategorikal|Profesi pengguna (e.g., Doctor, Lawyer, Other).|
|Income|Numerik|Pendapatan pengguna.|
|Credit Card Number|Kategorikal|Nomor kartu kredit yang digunakan untuk transaksi (dibuang saat pra-pemrosesan).|
|Expiry|Kategorikal|Tanggal kedaluwarsa kartu kredit (dibuang saat pra-pemrosesan).|
|Security Code|Kategorikal|Kode keamanan (CVV) kartu (dibuang saat pra-pemrosesan).|
|Fraud|Biner|**Target Variable.** `1` jika fraud, `0` jika legitimate.|

## ⚙️ Alur Kerja Proyek (Workflow) 

Proyek ini mengikuti langkah-langkah standar dalam sebuah proyek Data Science: 

1. **Eksplorasi Data (EDA):** Memahami distribusi data, hubungan antar fitur, dan mengidentifikasi pola awal. 
2. **Pra-pemrosesan Data:** 
* Membuang fitur yang tidak relevan dan berisiko *data leakage* (nomor kartu, expiry, CVV). 
* Menangani data kategorikal (`Profession`) dengan *One-Hot Encoding*. 
* Menyamakan skala data numerik (`Income`) dengan *Standard Scaling*. 
3. **Pelatihan Model:** Melatih tiga model klasifikasi yang berbeda untuk perbandingan: 
* **Logistic Regression:** Sebagai model dasar (baseline). 
* **Random Forest Classifier:** Model ensemble yang kuat. 
* **XGBoost Classifier:** Model gradient boosting yang sangat powerful. 
4. **Evaluasi Model:** Mengukur performa model menggunakan metrik yang relevan untuk kasus imbalanced-data seperti *Precision*, *Recall*, *F1-Score*, dan *ROC-AUC*. 

## 🚀 Cara Menjalankan Proyek 

Untuk menjalankan proyek ini di lingkungan Anda sendiri, ikuti langkah-langkah berikut: 

1. **Clone repositori ini:** 
	```bash git clone  	https://github.com/[NAMA_USER_GITHUB]/[NAMA_REPO_LO].git cd [NAMA_REPO_LO] ```  

2. **Install dependensi yang dibutuhkan:** 
	```bash pip install -r requirements.txt ```  

3. **Jalankan Notebook:** 
	Buka file `Fraud_Detection_Notebook.ipynb` menggunakan Jupyter Notebook, JupyterLab, atau langsung klik tombol "Open in Colab" di bagian atas README ini. 

## 📊 Hasil & Performa Model 

Setelah melatih dan mengevaluasi ketiga model pada data tes, berikut adalah rangkuman performanya, dengan fokus pada kemampuan mendeteksi kelas 'Fraud': 

|Model|Precision (Fraud)|Recall (Fraud)|F1-Score (Fraud)|ROC-AUC|
|--------|-------------------|----------------|-------------------|----|
|**XGBoost**|0.510574|0.505484|0.508016|0.504278|
|**Random Forest**|0.501548|0.484546|0.492901|0.500545|
|**Logistic Regression**|0.518062|0.629113|0.568213|0.529621|

**Kesimpulan:** 
Berdasarkan metrik evaluasi, terutama **Recall** dan **F1-Score** untuk kelas Fraud, model **Logistic Regression** menunjukkan performa terbaik. Recall yang tinggi sangat penting dalam kasus ini untuk meminimalkan jumlah kasus fraud yang terlewatkan (False Negatives). 

## 📁 Struktur File
  
├── data/  
│ └── data2.csv  
├── Fraud_Detection_Notebook.ipynb  
├── requirements.txt  
├── .gitignore  
└── README.md

## 📜 Lisensi 
Proyek ini dilisensikan di bawah [MIT License](LICENSE).
