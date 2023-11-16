# UTS Metode Numerik
Dosen Pengampuh : Anggay Luri Pramana,M.Kom

# Penulis
	Nama	: Moch Rafli Muchibbin
 	Kelas	: TIF22A(pagi)
  	Nim	: 23422029

# Soal : 
No. 1  Persamaan Non Linier <br>
      3 + x³ - x = 4 <br>
No. 2  Persamaan Linier <br>
      2x - 4 = 8 

Intruksi : <br>
1. Carilah Solusi dari 2 soal diatas (metode bebas) <br>
2. Buatlah Program untuk mencari solusi diatas <br>
3. Dan tunjukkan nilai x di setiap iterasinya <br>

# 1. Penyederhanaan Persamaan Non Linier
Persamaan non linier yang diberikan adalah: <br>
    3 + x³ - x = 4 <br>
    3 + x³ - x - 4 = 0 <br>
    x³ - x + 3 - 4 = 0 <br>
    x³ - x - 1 = 0 atau <br>
    x³ - x = 1

# Solusi Diatas : 
  Untuk mencari solusi dari persamaan non-linier tersebut, anda dapat menggunakan metode iteratif seperti, 
  metode Newton-Raphson untuk persamaan non-linier dan metode eliminasi untuk persamaan linier. 
  Berikut contoh program sederhana menggunakan Python: 

``python
def fungsi_non_linier(x):
    return x**3 - x + 3 - 4
	
def turunan_fungsi_non_linier(x):
    return 3*x**2 - 1

def metode_newton_raphson(x0, toleransi, maks_iter):
    iterasi = 1
    while iterasi <= maks_iter:
          x1 = x0 - fungsi_non_linier(x0) / turunan_fungsi_non_linier(x0)
          print(f'Iterasi {iterasi}: x = {x1}')

	  if abs(x1 - x0) < toleransi:
	     print(f'Solusi ditemukan setelah {iterasi} iterasi: x = {x1}')
	     return x1

	     x0 = x1
	     iterasi += 1

	  print('Iterasi maksimum tercapai. Metode Newton-Raphson tidak konvergen.')
	  return None

# Tentukan nilai awal, toleransi, dan maksimum iterasi
    x0 = 1.0
    toleransi = 1e-6
    maks_iter = 100

# Panggil fungsi untuk metode Newton-Raphson
solusi = metode_newton_raphson(x0, toleransi, maks_iter)
```


Output:

      Iterasi 1: x = 1.5 
  	Iterasi 2: x = 1.3478260869565217 
  	Iterasi 3: x = 1.325200398950907 
  	Iterasi 4: x = 1.3247181739990537 
  	Iterasi 5: x = 1.3247179572447898 
  	Solusi ditemukan setelah 5 iterasi: x = 1.3247179572447898 

# 2. Penyederhanaan Persamaan Linier 
Persamaan linier yang diberikan adalah: <br>
     2x - 4 = 8 <br>
     2x = 8 + 4 <br>
     2x = 12 <br>
     x = 6 <br>
     Jadi, solusi persamaan linier ini adalah x = 6.

# Solusi Diatas :
Persamaan linear dapat dipecahkan secara langsung tanpa menggunakan metode iteratif karena ini adalah persamaan linear sederhana. 
Berikut adalah implementasi dalam Python:

	``python
	def solve_linear_equation(coef, constant):
	# Persamaan linear: coef * x = constant
	x = constant / coef
	return x
	
	# Koefisien persamaan
	coef = 2
	
	# Konstanta persamaan
	constant = 8 + 4  # Sisi kanan persamaan dipindahkan ke sisi kiri dengan menggabungkan konstanta
	
	# Panggil fungsi untuk menyelesaikan persamaan linear
	solusi = solve_linear_equation(coef, constant)
	
	# Cetak solusi
	print(f"Solusi persamaan 2x - 4 = 8 adalah x = {solusi}")
	```


Output :

	Solusi persamaan 2x - 4 = 8 adalah x = 6.0
