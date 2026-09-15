# TI-Assistant UIN Palangka Raya

Chatbot berbasis AI untuk informasi Program Studi Teknologi Informasi UIN Palangka Raya.

## Fitur
- Chatbot berbasis Groq + LangChain
- Function Calling menggunakan `@tool`
- Informasi profil/keunggulan Prodi
- Profil lulusan
- Kurikulum dan mata kuliah
- Tiga konsentrasi keilmuan
- Capaian Pembelajaran Lulusan (CPL)
- MBKM dan konversi SKS
- Antarmuka Streamlit

## 1. Buka project di VS Code

Buka folder `TI_Assistant_UIN_Palangka_Raya`.

## 2. Buat environment

Jika menggunakan Anaconda:

```bash
conda create -n ti-assistant python=3.13 -y
conda activate ti-assistant
```

Jika Bapak sudah memiliki environment `avpn-project`, langkah ini boleh dilewati.

## 3. Install library

Di Terminal VS Code:

```bash
pip install -r requirements.txt
```

## 4. Masukkan API key

Salin `.env.example` menjadi `.env`.

Isi:

```env
GROQ_API_KEY=gsk_API_KEY_ANDA
```

Jangan masukkan API key ke `app.py` dan jangan upload `.env` ke GitHub.

## 5. Jalankan

```bash
streamlit run app.py
```

Browser akan membuka aplikasi Streamlit.

Jika tidak terbuka otomatis, buka alamat yang ditampilkan di terminal, biasanya:

```text
http://localhost:8501
```

## Contoh pertanyaan

- Apa keunggulan Prodi Teknologi Informasi UIN Palangka Raya?
- Apa saja profil lulusan?
- Apa saja konsentrasi yang tersedia?
- Berapa total SKS?
- Apa mata kuliah semester 4?
- Bagaimana skema MBKM?
- Apa saja CPL Prodi?

## Catatan sumber

Basis pengetahuan proyek ini disusun dari dokumen kurikulum/profil Prodi Teknologi Informasi UIN Palangka Raya yang digunakan dalam proyek. Informasi yang tidak ada di basis pengetahuan tidak boleh dianggap sebagai fakta resmi.

## Struktur project

```text
TI_Assistant_UIN_Palangka_Raya/
├── app.py
├── knowledge_base.py
├── requirements.txt
├── .env.example
├── .gitignore
├── run_app.bat
└── README.md
```

## Basis Pengetahuan Dokumen
Project ini menyertakan dua dokumen sumber di folder `data/`:
1. Kurikulum dan Profil Prodi Teknologi Informasi UIN Palangka Raya.
2. Keputusan Menteri Pendidikan Tinggi, Sains, dan Teknologi Nomor 553/B/O/2026 tentang izin pembukaan Prodi Teknologi Informasi Program Sarjana pada UIN Palangka Raya.

`knowledge_base.py` membaca dokumen tersebut saat aplikasi berjalan dan menyediakan pencarian berbasis kata kunci melalui Function Calling.

Logo Prodi tersedia di `assets/logo_prodi.png` dan ditampilkan pada header aplikasi.
