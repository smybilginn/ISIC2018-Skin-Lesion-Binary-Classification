# neural_networks_final_project
🧠 ISIC2018 Deri Lezyonu İkili Sınıflandırma (CNN ve Transfer Learning)

Bu repository, ISIC 2018 Skin Lesion Dataset kullanılarak geliştirilmiş derin öğrenme tabanlı bir ikili sınıflandırma (binary classification) pipeline’ını içermektedir.

Proje, Yapay Sinir Ağları dersi final ödevi kapsamında hazırlanmıştır.

Bu çalışmada üç farklı model kullanılmıştır:

✅ Scratch CNN (sıfırdan eğitilen CNN)

✅ MobileNetV2 (Transfer Learning)

✅ EfficientNetB0 (Transfer Learning)

📌 Problem Tanımı

Deri lezyonlarının sınıflandırılması, medikal görüntü işleme alanında kritik bir problemdir. Bu projede:

Veri setindeki en fazla örneğe sahip iki sınıf seçilmiştir:

Pigmented Benign Keratosis

Melanoma

Problem, ikili sınıflandırma (binary classification) olarak ele alınmıştır.

🗂 Veri Seti

Veri seti: ISIC 2018 Skin Lesion Dataset (Kaggle sürümü)

Görüntüler ham (raw) haliyle kullanılmıştır.

Uygulanan işlemler:

Tüm görüntüler 224×224 boyutuna getirilmiştir.

Normalize edilmiştir (1/255).

Ağır klasik ön işleme (hair removal, histogram equalization vb.) uygulanmamıştır.

⚙️ Çalışma Akışı (Pipeline)

Veri seti analizi ve en büyük iki sınıfın seçilmesi

Stratified Train / Validation / Test bölme

tf.data ile input pipeline oluşturulması

Sadece train seti için data augmentation uygulanması

Modellerin eğitimi:

Scratch CNN

MobileNetV2 (Transfer Learning)

EfficientNetB0 (Transfer Learning)

Transfer learning için iki aşamalı eğitim:

Feature Extraction (backbone freeze)

Fine-tuning (son %25 katman açma)

Test seti üzerinde değerlendirme:

Accuracy, Precision, Recall, F1-score, ROC-AUC

Confusion Matrix, ROC Curve, Classification Report

Model açıklanabilirliği için Grad-CAM analizi

🧪 Veri Artırma (Data Augmentation)

Sadece train seti için uygulanmıştır:

Random horizontal & vertical flip

Random rotation (±15°)

Random zoom

Random brightness ve contrast

📊 Değerlendirme Metrikleri

Modeller aşağıdaki metriklerle karşılaştırılmıştır:

Accuracy

Precision

Recall

F1-score

ROC-AUC

Kullanılan görseller:

Confusion Matrix

ROC Curve

Classification Report

🔍 Açıklanabilir Yapay Zeka (Grad-CAM)

Modelin karar verirken görüntünün hangi bölgelerine odaklandığını analiz etmek için Grad-CAM yöntemi kullanılmıştır.

Her model için test setinden:

3 doğru sınıflandırılmış

3 yanlış sınıflandırılmış (varsa)

örnek üzerinde:

Orijinal görüntü

Isı haritası

Overlay (bindirme)

şeklinde görselleştirme yapılmıştır.

🏆 Sonuç Özeti

Modeller karşılaştırıldığında en iyi performansı Scratch CNN modeli vermiştir.

MobileNetV2 modeli de oldukça iyi sonuçlar üretmiştir.

EfficientNetB0 modeli bu veri setinde yeterli performans gösterememiştir.

Grad-CAM sonuçları, modelin çoğu durumda lezyon bölgelerine odaklandığını göstermektedir.

🛠 Kullanılan Teknolojiler

Python

TensorFlow / Keras

NumPy, Matplotlib, Scikit-learn

Google Colab
