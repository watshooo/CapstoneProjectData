# CapstoneProjectData
Menganalisa sentimen komentar youtube channel investasi dengan klasifikasi menggunakan IBM Granite Instruct

Mendekati HUT RI ke 80, BEI mengharapkan IHSG dapat mencapai 8000. Hal Tersebut disambut baik oleh OJK dan OJK menyambut baik optimisme tersebut (CNBC Indonesia). 

Hanya saja belakangan ini ekonomi sedang melemah. Mengutip dari layarbursa.com harga saham lebih dipengaruhi oleh pandangan investor terkait narasi masa depan. Jadi tidak perlu heran apa bila pasar saham bisa bertumbuh dibandingan keadaan ekonomi pada kondisi saat ini.

Untuk mencari tahu pandangan masyarakat, saya menggunakan IBM Granite Instruct untuk mengklasifikasi komentar pada beberapa video channel investasi. Harapannya saya mendapatkan insight mengenai sentimen terkait IHSG yang akan naik

Step by step secara singkat untuk membuat Project Capstone ini adalah sebagai berikut
1. Persiapkan API
   API Crawling data komentar Youtube
   API Replicate untuk menjalankan IBM Granite Instruct
2. Crawling Data komentar
3. Feed data komentar ke model IBM Granite Instruct yang sudah di Beri Prompt dan setting param
   
   Setting parameter yang digunakan:
   ===================
     temperature: 0.01,
     max_new_tokens: 12,
     top_p: 0.5,
     repetition_penalty: 1.2

   Prompt yang dipakai:
   ===================
   [PERAN DAN KONTEKS]
   Anda adalah model klasifikasi sentimen yang sangat akurat, dilatih khusus untuk komentar investor di YouTube. Tugas Anda adalah menganalisis komentar YouTube         terkait prediksi IHSG (Indeks Harga Saham Gabungan) akan menembus 8080 sebelum 17 Agustus 2025.

   [TUGAS]
   Klasifikasikan komentar berikut ke dalam salah satu dari 3 kategori di bawah.

   [DEFINISI KATEGORI]
   - PRO: Komentar optimis, percaya, mendukung, atau setuju IHSG akan tembus 8080 sebelum HUT RI.
   - CONTRA: Komentar pesimis, tidak percaya, meragukan, atau menolak IHSG tembus 8080 sebelum HUT RI.
   - NEUTRAL: Komentar yang tidak mengandung pendapat jelas, tidak relevan, ambigu, bertanya, atau hanya menyatakan fakta tanpa sikap.

   [CONTOH KLASIFIKASI]
   - Komentar: "Gaskeun lah 8080 optimis!" -> Jawaban: PRO
   - Komentar: "mimpi kali, ga mungkin sampe segitu" -> Jawaban: CONTRA
   - Komentar: "ini channel bahas saham apa ya?" -> Jawaban: NEUTRAL

   [INSTRUKSI OUTPUT]
   1. Jawab HANYA dengan salah satu dari tiga kata kunci: PRO, CONTRA, atau NEUTRAL.
   2. JANGAN menyalin, mengulang, atau mengutip isi komentar.
   3. JANGAN menambahkan penjelasan, opini, alasan, atau kalimat lain.
   4. Jika komentar sangat ambigu atau sama sekali di luar topik, prioritaskan NEUTRAL.

   [KOMENTAR UNTUK DIANALISIS]
   Komentar: "{snippet}
  
5. Muat Hasil LLM ke dalam CSV dan dibuat plot/chart sebagai penggambaran hasil klasifikasi komentar youtube
6. Hasil nya seperti berikut
 <img width="528" height="504" alt="image" src="https://github.com/user-attachments/assets/8642b159-8f0f-4008-922c-c0786a7347a9" />

Conclusion
Beberapa Narasi memang ada yang mendukung IHSG untuk sampai ke 8000. Walaupun tidak signifikan dan lebih banyak yang neutral. Kemungkinan IHSG ke 8000 masih ada.

Recomendation
Untuk analisa sentimen ada baiknya data yang digunakan sudah lebih matang/ sudah siap untuk di feedkan ke LLM IBM Granite. Saya bukan pakar ahli yang bisa menentukan stopwords apa yang sekiranya harus diberikan dan berpengaruh terhadap hasil analisa LLM IBM Granite. 



