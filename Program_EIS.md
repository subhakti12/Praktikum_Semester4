// Tentukan pin analog yang terhubung ke sensor kelembaban tanah YL-69
const int moistureSensorPin = A1;

void setup() {
  Serial.begin(9600); // Inisialisasi komunikasi serial untuk debugging
}

void loop() {
  // Baca nilai analog dari sensor kelembaban tanah
  int moistureValue = analogRead(moistureSensorPin);

  // Konversi nilai analog menjadi persentase (diasumsikan rentang 0 hingga 1023)
  int moisturePercentage = map(moistureValue, 0, 1023, 0, 100);

  // Tampilkan nilai kelembaban dan persentase ke serial monitor
  Serial.print("Nilai Kelembaban: ");
  Serial.print(moistureValue);
  Serial.print(", Persentase Kelembaban: ");
  Serial.println(moisturePercentage);

  // Tambahkan delay untuk mencegah pembacaan yang terlalu cepat (sesuaikan jika diperlukan)
  delay(1000);
}
