# Twitter/X Sentiment Analysis using IndoBERT & Bi-LSTM (25K Dataset)

## Deskripsi Proyek

Proyek ini merupakan implementasi sistem **analisis sentimen berbasis Deep Learning** menggunakan **25.000 data tweet berbahasa Indonesia**. Dataset diklasifikasikan ke dalam **3 kelas utama (Positif, Netral, Negatif)** dengan performa tinggi menggunakan pendekatan **State-of-the-Art NLP (IndoBERT Transformer Model)**.

Model terbaik berhasil mencapai akurasi pengujian di atas **93%**, melampaui target awal (>92%).

---

## Tujuan

* Mengembangkan model klasifikasi sentimen berbasis NLP untuk bahasa Indonesia.
* Membandingkan performa beberapa pendekatan Machine Learning dan Deep Learning.
* Menghasilkan model dengan akurasi tinggi dan siap digunakan untuk inferensi real-time.

---

## Dataset

* Total Data: **25.000 tweet**
* Bahasa: Indonesia
* Kelas:

  * Positif (~33.3%)
  * Netral (~33.3%)
  * Negatif (~33.3%)
* Dataset bersifat **balanced** untuk menghindari bias model.

---

## Preprocessing & Labeling

Pipeline preprocessing dilakukan secara otomatis dengan tahapan:

* Case folding
* Text cleaning (hapus URL, mention, emoji, simbol)
* Regex filtering
* Normalisasi teks
* Tokenisasi

Labeling dilakukan secara semi-otomatis dengan validasi untuk menjaga kualitas data.

---

## Skema Eksperimen

Tiga pendekatan dibandingkan untuk mendapatkan performa terbaik:

| Komponen   | Skema 1 (Baseline) | Skema 2 (Deep Learning) | Skema 3 (Transformer)      |
| ---------- | ------------------ | ----------------------- | -------------------------- |
| Algoritma  | SVM                | Bi-LSTM                 | **IndoBERT (Fine-Tuning)** |
| Fitur      | TF-IDF             | Tokenizer + Embedding   | IndoBERT Tokenizer         |
| Split Data | 80:20              | 80:20                   | **90:10**                  |
| Akurasi    | ~86.20%            | ~90.15%                 | **93.45%**                 |

---

## Hasil Terbaik (IndoBERT)

Model IndoBERT menunjukkan performa terbaik dengan hasil evaluasi sebagai berikut:

```text
              precision    recall  f1-score   support

     Negatif       0.93      0.92      0.92       830
      Netral       0.92      0.94      0.93       850
     Positif       0.95      0.93      0.94       820

    accuracy                           0.93      2500
   macro avg       0.93      0.93      0.93      2500
weighted avg       0.93      0.93      0.93      2500
```

---

## Visualisasi

Notebook menyediakan beberapa visualisasi penting:

* Distribusi kelas (Bar Chart)
* Word Cloud tiap sentimen
* Kurva training (loss & accuracy)

---

## Inferensi (Prediksi Data Baru)

Model dapat digunakan langsung untuk memprediksi sentimen teks baru:

* **Input:**
  "Aplikasi ini bener-bener membantu dan cepat banget digunakan!"
  **Output:** Positif

* **Input:**
  "Sistem baru ini membingungkan dan sering error terus dari pagi."
  **Output:** Negatif

---
## Google Colab

(https://colab.research.google.com/drive/1uc_71mYgpkzgtp5MkwDuAGbFcE88BNzo?usp=sharing)

---

## Cara Menjalankan Proyek

### 1. Clone Repository

```bash
git clone https://github.com/yuzhuruuu/Analisis-Sentimen-Tweet.git
cd NAMA_REPO
```

### 2. Install Dependencies

Pastikan Python 3.10+ sudah terpasang:

```bash
pip install -r requirements.txt
```

### 3. Jalankan Notebook

* Buka file `.ipynb` di **Jupyter Notebook** atau **Google Colab**
* Jalankan semua cell dari atas ke bawah
* Gunakan **GPU (disarankan: NVIDIA T4)** untuk training IndoBERT

---

## Teknologi yang Digunakan

* Python
* Scikit-learn
* TensorFlow / PyTorch
* HuggingFace Transformers (IndoBERT)
* Pandas, NumPy
* Matplotlib, Seaborn

---

## Highlight

* 1. Dataset besar (25K) & balanced
* 2. Multi-model comparison (SVM vs BiLSTM vs IndoBERT)
* 3. High accuracy (>93%)
* 4. Siap inferensi real-time
* 5. Cocok untuk portfolio NLP / AI Engineer

---

##  Pengembangan Selanjutnya

* Deploy model ke web app (Gradio / Streamlit)
* Integrasi API untuk real-time sentiment tracking
* Fine-tuning dengan dataset domain spesifik (finance, e-commerce, dll)

---

## 📌 Kesimpulan

Pendekatan Transformer menggunakan IndoBERT terbukti memberikan performa terbaik dalam analisis sentimen bahasa Indonesia, mengungguli metode klasik maupun deep learning konvensional.

Proyek ini menunjukkan bahwa kombinasi dataset besar, preprocessing yang baik, dan fine-tuning model modern dapat menghasilkan sistem NLP dengan akurasi tinggi dan siap digunakan secara praktis.
