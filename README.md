# Employee Attrition Prediction by Using Machine Learning

## 1. Goals & Objectives
**Goals:**
1. Mengurangi tingkat employee attrition (resign) untuk pekerja yang berada di perusahaan hingga di bawah 10%.
2. Mengetahui faktor-faktor yang dapat menyebabkan seorang karyawan resign.

**Objectives:**
1. Menganalisa faktor-faktor dari data yang dimiliki terhadap potensi employee attrition (resign).
2. Membuat model yang dapat digunakan untuk memprediksi karyawan-karyawan yang berpotensi untuk meninggalkan perusahaan.

## 2. Exploratory Data Analysis
<p align="center"><img src="images/Employee Attrition Ratio.png" alt="Employee Attrition Ratio" width=40%></p>

Berdasarkan ilustrasi di atas, dapat disimpulkan bahwa **16.1%** dari total karyawan memilih untuk **keluar** dari perusahaan sedangkan **83.9%** dari total karyawan memilih untuk **bertahan**.

### 2.1. Univariate Analysis
<p align="center"><img src="images/Univariate Analysis for Numerical Features.png" alt="Univariate Analysis for Numerical Features"></p>

#### Observation:
- Karyawan dengan *Monthly Income* sekitar 1800 - 3200 merupakan tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi. Kemudian karyawan dengan *Monthly Income* sekitar 13000 - 19000 merupakan tipe karyawan yang memiliki *Attrition Rate* yang paling rendah.
- Karyawan dengan rentang umur di bawah 40 tahun cenderung memiliki *Attrition Rate* yang lebih tinggi. Kemudian, karyawan dengan rentang umur sekitar 25 - 35 tahun memiliki *Attrition rate* yang paling tinggi.
- Karyawan dengan nilai *Distance From Home* lebih dari 10 km cenderung memiliki *Attrition Rate* yang lebih tinggi.
- Karyawan dengan nilai *Daily Rate* kurang dari 800 cenderung memiliki *Attrition Rate* yang lebih tinggi.
- Karyawan dengan nilai *Total Working Years* sekitar 0 - 2 tahun serta 4,5 - 6 tahun merupakan dua tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi.
- Karyawan dengan nilai *Years at Company*, *Years in Current*, and *Years with Current Manager* sekitar 0 - 1 tahun tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi.

<p align="center"><img src="images/Univariate Analysis for Categorical Features.png" alt="Univariate Analysis for Categorical Features"></p>

#### Observation:
- Karyawan yang bekerja melebihi jam kerja reguler (*over time*) memiliki *Attrition Rate* yang lebih tinggi dibandingkan dengan karyawan yang tidak bekerja lembur.
- Karyawan yang memiliki tingkat *Job Satisfaction* yang lebih rendah cenderung memiliki *Attrition Rate* yang lebih tinggi. Kemudian, didapatkan bahwa karyawan yang memiliki *Job Satisfaction* bernilai 1 merupakan tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi.
- Karyawan yang memiliki tingkat *Environment Satisfaction* yang lebih rendah cenderung memiliki *Attrition Rate* yang lebih tinggi. Kemudian, didapatkan bahwa karyawan yang memiliki *Environment Satisfaction* bernilai 1 merupakan tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi.
- Karyawan yang memiliki tingkat *Relationship Satisfaction* yang lebih rendah cenderung memiliki *Attrition Rate* yang lebih tinggi. Kemudian, didapatkan bahwa karyawan yang memiliki *Relationship Satisfaction* bernilai 1 merupakan tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi.
- Karyawan yang memiliki *Job Level* yang lebih rendah cenderung memiliki *Attrition Rate* yang lebih tinggi. Kemudian, karyawan yang memiliki *Job Level* 1 merupakan tipe karyawan dengan *Attrition Rate* paling tinggi.
- Karyawan yang memiliki tingkat *Work Life Balance* yang lebih rendah cenderung memiliki *Attrition Rate* yang lebih tinggi. Kemudian, didapatkan bahwa karyawan yang memiliki *Work Life Balance* bernilai 1 merupakan tipe karyawan yang memiliki *Attrition Rate* yang paling tinggi.
- Karyawan yang memiliki keterlibatan kerja yang lebih rendah memiliki *Attrition Rate* yang lebih tinggi.
- Karyawan yang bekerja pada Departemen *Sales* memiliki *Attrition Rate* yang paling tinggi dibandingkan dengan departemen lainnya.
- Karyawan yang menjabat sebagai *Sales Representative*, *Laboratory Technician*, dan *Human Resources* merupakan 3 tipe karyawan yang memiliki *Attrition rate* paling tinggi.

### 2.2. Bivariate Analysis
<p align="center"><img src="images/Bivariate Analysis.png" alt="Bivariate Analysis"></p>

#### Observation:
Dari grafik di atas yang menunjukkan hubungan `MonthlyIncome` dengan fitur lain (`OverTime`, `JobSatisfaction`,`EnvironmentSatisfaction`, `RelationshipSatisfaction`, `JobLevel`, `WorkLifeBalance`, `JobInvolvement`, `Department`, `JobRole`) dapat disimpulkan bahwa karyawan dengan pendapatan bulanan (`Monthly Income`) yang **lebih rendah** cenderung memiliki *Attrition Rate* yang lebih tinggi atau kecenderungan untuk meninggalkan perusahaan lebih besar.

## 3. Data Preprocessing
1. Tidak terdapat **missing values** atau **data duplikat** pada dataset.
2. Dilakukan penghapusan **outliers** sehingga hanya tersisa **1387** baris data.
3. Merubah fitur kategorik dengan **Label Encoding** jika memiliki 2 *unique values* atau data ordinal dan menggunakan **OHE** jika data nominal.
4. Melakukan **feature engineering** untuk membuat 2 fitur baru, yaitu **EmployeeSatisfaction** dan **JobLevelSatisfaction**.
5. Melakukan **feature selection** menggunakan **Pearson Correlation**.
6. **Standarisasi** untuk data training dan test.
7. Menangani **class imbalance** dengan menggunakan teknik **SMOTE**.
8. Membagi data dengan proporsi 70:30, **70% untuk training** dan **30% untuk testing**.

## 4. Modeling
### 4.1. Model Training & Evaluation
Metrics yang akan digunakan untuk mengukur tingkat keberhasilan model *machine learning* adalah *metric* **recall**. Hal ini dilakukan untuk menghindari tingginya kesalahan prediksi karyawan yang tidak akan keluar dari perusahaan, sedangkan pada faktanya karyawan tersebut memilih untuk keluar (**false negative**). Hal ini karena *false negative* memiliki dampak negatif yang lebih besar kepada perusahaan seperti terjadinya kekosongan jabatan sehingga dapat berpotensi menurunkan performa perusahaan ketimbang *false positive*.





