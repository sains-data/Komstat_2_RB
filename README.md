# Analisis & Visualisasi Data Pendidikan Dasar Provinsi Lampung (2019-2024)

[![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)](https://www.r-project.org/)
[![RMarkdown](https://img.shields.io/badge/RMarkdown-75AADB?style=flat&logo=markdown&logoColor=white)](https://rmarkdown.rstudio.com/)
[![GIS](https://img.shields.io/badge/Spatial%20Data-SF-green?style=flat)]()

**Quick Access:** 🎞️ [Video](https://drive.google.com/file/d/1Je4fRD05nJuFM3gvSNsX5UpNi6BoEQeT/view?usp=drive_link) • 📄 [Laporan PDF](Laporan_2_RB.pdf) • 🖼️ [Poster](Poster_2_RB.pdf)

Tugas Besar Komputasi Statistik - Program Studi Sains Data, Institut Teknologi Sumatera

---

## 👥 Anggota Kelompok 2

| NIM         | Nama                        |
|-------------|-----------------------------|
| 123450115  | Muhammad Fadil Alfaizi       |
| 123450027  | Wulan Lumbantoruan           |
| 123450017  | Nayla Shafira Roza           |
| 123450068  | Mia Almusdari                |

---

## 📂 Struktur Repository

```
Komstat/
│
├── Dataset/
├── Visualisasi/
├── KodeR_2_RB.Rmd             # Kode utama Implementasi Visualisasi Data (R Markdown)
├── Laporan_2_RB.pdf           # Laporan
├── PPT_2_RB.pdf               # Presentasi poster proyek
├── Poster_2_RB.png            # Poster presentasi (PNG)
|
└── README.md                  # Dokumentasi proyek 
```

---

## 🧠 Ringkasan Proyek

Penelitian ini menganalisis kondisi pendidikan dasar (SD) di Provinsi Lampung dengan fokus:

- Jumlah **murid**, **guru**, dan **sekolah** (2019–2024)  
- **Rasio murid-guru** sebagai indikator pemerataan  
- **Analisis spasial** menggunakan SIG (sf + ggplot2)  
- **Peta tematik dan animasi** untuk melihat tren temporal  

Hasil analisis mengungkap **ketimpangan spasial** antara wilayah urban dan rural, serta pola distribusi yang penting untuk kebijakan pemerataan pendidikan.

---

## 🛠 Metodologi

### 1. Data Sources
- **BPS Provinsi Lampung (2019–2024)**  
  - Jumlah murid SD  
  - Jumlah guru SD  
  - Jumlah sekolah SD  
- **Data Spasial ADM2 Lampung (GADM / geodata)**

### 2. Data Processing Pipeline
- Pembersihan & standarisasi nama kabupaten  
- Integrasi data tabular + spasial (`left_join`)  
- Perhitungan variabel turunan: rasio = jumlah_murid / jumlah_guru
- Pembuatan peta: choropleth, bar chart, line chart, scatterplot  
- Pembuatan peta animasi (`gganimate`)

### 3. Tools Used
- **tidyverse**  
- **sf**  
- **ggplot2**  
- **gganimate**  
- **geodata**  

---

## ▶️ Cara Menjalankan Kode

### Install Packages
```r
install.packages(c("tidyverse", "sf", "ggplot2", "geodata", "gganimate"))
```

---

## 📊 Hasil Utama

### 1. Tren Pendidikan (2019–2024)

- Jumlah murid **menurun** setiap tahun.
- Jumlah guru **stabil**.
- Jumlah sekolah **bervariasi signifikan antar kabupaten**.

### 2. Rasio Murid-Guru (Indikator Pemerataan)

Wilayah **rasio tinggi (>25)** → *kekurangan guru*  
- Lampung Timur  
- Lampung Tengah  

Wilayah **rasio rendah (<15)** → *lebih ideal*  
- Way Kanan  
- Tulang Bawang  

### 3. Temuan Spasial

- Daerah urban (Bandar Lampung, Lampung Tengah) memiliki jumlah murid tinggi.  
- Wilayah rural memiliki keterbatasan sarana dan akses pendidikan.  
- Peta animasi menunjukkan tren ketimpangan yang **persisten** tiap tahun.

### Visualisasi Distribusi Sampling

![Choropleth Map Distribusi Jumlah Murid SD per Kabupaten/Kota di Provinsi Lampung](Visualisasi/Hasil_Visualisasi_7.png)

**Interpretasi:**
- Warna biru muda menunjukkan daerah dengan jumlah murid SD paling sedikit (≈ < 25.000 – 50.000), yang menandakan kepadatan penduduk usia sekolah yang relatif rendah, terlihat dominan di wilayah bagian barat (pesisir) dan sebagian utara.
- Warna biru sedang menggambarkan wilayah dengan jumlah murid kategori menengah (≈ 50.000 – 75.000), yang tersebar di beberapa bagian utara dan selatan provinsi.
- Warna biru tua menunjukkan daerah dengan populasi murid SD tertinggi (≈ 100.000 – 125.000), mengindikasikan pusat konsentrasi penduduk atau wilayah padat hunian (kemungkinan besar meliputi wilayah Lampung Tengah dan sekitarnya).
- Pola spasial memperlihatkan ketimpangan distribusi di mana konsentrasi murid terpusat di bagian tengah hingga timur provinsi, sedangkan wilayah bagian barat cenderung memiliki jumlah murid yang jauh lebih rendah.

![Choropleth Map Rasio Murid per Guru SD 2019 - 2024](Visualisasi/Hasil_Visualisasi_Final.gif)

**Interpretasi:**
- Warna kuning–hijau menunjukkan daerah dengan rasio murid per guru yang lebih rendah (≈ 12–14), menandakan ketersediaan guru relatif memadai.
- Warna hijau–biru menggambarkan rasio menengah (≈ 15–17) yang merupakan kondisi umum di sebagian besar wilayah Provinsi Lampung.
- Warna biru tua–ungu menunjukkan rasio tinggi (≥ 18), mengindikasikan potensi kekurangan guru atau ketidakseimbangan distribusi guru.
- Pola spasial memperlihatkan bahwa bagian tengah dan barat cenderung memiliki rasio yang lebih rendah, sedangkan bagian timur dan selatan memiliki rasio yang lebih tinggi.


### Poster Presentasi

![Poster Projek](Poster_2_RB.png)

---

## 🧾 Kesimpulan

1. Terjadi penurunan jumlah murid SD di Lampung pada 2019–2024.
2. Ketimpangan rasio murid-guru antar kabupaten cukup signifikan.
3. Integrasi data statistik + spasial menghasilkan visualisasi yang kuat untuk memahami konteks pendidikan.
4. Visualisasi membantu mengidentifikasi zona merah dan wilayah yang membutuhkan intervensi segera.

---

## 💡 Rekomendasi

- Prioritaskan distribusi guru di wilayah **rasio tinggi** (Lampung Timur & Lampung Tengah).
- Perkuat infrastruktur pendidikan di wilayah rural: Mesuji, Pesisir Barat.
- Gunakan dashboard berbasis R untuk monitoring berkelanjutan.
- Tambahkan variabel sosial-ekonomi pada penelitian lanjutan.


---

## Referensi

1. Dent, B. D. (1999). *Cartography: Thematic Map Design*. WCB/McGraw-Hill.
2. Hakim, H. D. I. (2024). *Analisis Rata-Rata, Median, dan Visualisasi Jumlah Kepala Sekolah dan Guru Berdasarkan Kelompok Umur di Prov. Lampung, Riau, Aceh, Papua Barat*.
3. Montgomery, D. C., & Runger, G. C. (2014). *Applied Statistics and Probability for Engineers* (6th ed.). Wiley.
4. Widayanti, T., Sari, R. M., & Putra Perdana, A. M. (2025). *Spatial Analysis of the Distribution of Educational Facilities in Central Lampung Regency, Lampung Province, Indonesia*, 5(01).
5. Hermawan, D. D., & Andriansyah, M. (2025). *Visualisasi Data Pendidikan SD & SMP Daerah Kabupaten Tangerang Menggunakan Aplikasi Microsoft Power Business Intelligence*. Journal of Comprehensive Science, 4(2), 750.
6. Fauzianti, N., & Suparta, I. W. (2024). *Analisis Pengaruh Pengeluaran Pemerintah Sektor Pendidikan, dan Tingkat Pengangguran Terhadap Pertumbuhan Ekonomi di Kabupaten/Kota Provinsi Lampung Tahun 2015–2022*. Economics and Digital Business Review, 5(2), 367–376.
7. Saifuddin, R. (2019). *Peningkatan Mutu Pendidikan Melalui Sinergi Kebijakan Antara Pemerintah Provinsi, Kabupaten, dan Kota*. Journal Balitbangda Provinsi Lampung, 7(3), 253–264.
8. Supiyandi, E. P., Cynthia, M. N. H. Siregar, A. Badawi, & F. Sari. (2024). *Pengenalan Sistem Informasi Geografis*. Tahta Media Group.
9. Rahmawati, L., Febrian, W. D., Fachruzzaki, Mardiyati, S., Lengam, R., & Suarnatha, I. P. D. (2024). *Pengembangan Sistem Informasi Geografis (SIG) untuk Analisis Spasial dalam Pengambilan Keputusan*. Jurnal Review Pendidikan dan Pengajaran, 7(3), 4058–4086.
10. Ramadhan, H., Syamsuar, D., & Ariandi, M. (2019). *Sistem Informasi Geografis Kependudukan Kecamatan Makarti Jaya dan Kecamatan Muara Padang Menggunakan Metode Choropleth Map*. Fakultas Ilmu Komputer, Universitas Bina Darma, 292–297.
11. Qori'atunnadyah, M. (2022). *Pengelompokkan Wilayah Berdasarkan Rasio Guru–Murid pada Jenjang Pendidikan Menggunakan Algoritma K-Means*. Journal of Informatics Development, 1(1), 33–38.
12. Widodo, B., Sastrawan, U., & Kuntari, W. (2024). *Komparasi Paket R untuk Aplikasi Analisis Spasial dalam Penelitian Sosial*. Jurnal Sosial Terapan, 2(2). https://doi.org/10.29244/jstrsv.2.2.46-52
13. Wickham, H. (2014). *Tidy Data*. Journal of Statistical Software, 55(2), 1–24.
14. Pebesma, E. (2018). *Simple Features for R: Standardized Support for Spatial Vector Data*. The R Journal, 10(1), 439–446.
15. Wickham, H. (2015). *ggplot2: Elegant Graphics for Data Analysis* (2nd ed.). Springer.
16. *Ketimpangan Pendidikan di Wilayah Urban dan Rural Provinsi Banten Tahun 2011–2014*. Skripsi Sarjana, Ilmu Ekonomi dan Studi Pembangunan, UIN Syarif Hidayatullah Jakarta, 2016.