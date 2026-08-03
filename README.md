# Customer Churn Prediction

مشروع تعلم آلي لتوقع احتمال ترك العملاء (Customer Churn) باستخدام نماذج تصنيف.

## وصف المشروع

هذا المشروع يهدف لبناء نموذج يستطيع التنبؤ بما إذا كان العميل سيترك الخدمة أم لا بناءً على بيانات سلوك العميل وخصائصه. تم تجربة عدة نماذج تصنيف (مثل Logistic Regression, Random Forest, XGBoost) ومقارنة الأداء.

## مميزات

- تنظيف وتحليل البيانات الاستكشافي (EDA)
- هندسة ميزات (feature engineering)
- تدريب ونشر نماذج تصنيف
- تقييم النماذج باستخدام دقة، مصفوفة الارتباك، AUC-ROC، F1-score

## هيكل المجلدات (مقترح)

- data/                : ملفات البيانات (خام ومعالجة)
- notebooks/           : دفاتر Jupyter للـ EDA والتجارب
- src/                 : شفرة المصدر (تحميل البيانات، تجهيزها، تدريب النموذج)
- models/              : النماذج المدربة والأوزان
- reports/             : تقارير ونتائج التدريب والـ plots
- README.md            : هذا الملف

> ملاحظة: لا تحتفظ بملفات البيانات الكبيرة في المستودع، استعمل .gitignore أو ربطها بمستودع بيانات خارجي.

## المتطلبات (Requirements)

أنشئ بيئة افتراضية ثم ثبّت الحزم المطلوبة (مثال):

```bash
python -m venv venv
source venv/bin/activate  # على macOS/Linux
venv\Scripts\activate     # على Windows
pip install -r requirements.txt
```

محتوى مبدئي مقترح لملف requirements.txt:

```
pandas
numpy
scikit-learn
xgboost
matplotlib
seaborn
jupyter
joblib
```

## كيفية التشغيل

1. ضع ملفات البيانات في المجلد `data/` (مثال: train.csv, test.csv).
2. شغّل دفاتر Jupyter في `notebooks/` للـ EDA:

```bash
jupyter lab
```

3. لتشغيل التدريب من سكربت:

```bash
python src/train.py --data_path data/train.csv --output_dir models/
```

4. لتشغيل التقييم:

```bash
python src/evaluate.py --model_path models/best_model.pkl --test_path data/test.csv
```

5. للتنبؤ على عينات جديدة:

```bash
python src/predict.py --model_path models/best_model.pkl --input data/new_customers.csv --output predictions.csv
```

## نتائج نموذجية

- أضف هنا جدول أو وصف مختصر لأفضل نموذج والـ metrics (مثال: RF: AUC=0.85, F1=0.67)

## ملاحظات حول البيانات

- تأكد من التعامل مع القيم المفقودة
- استعمل التوزيع الزمني عند وجوده (مثال: تجزئة تدريب/اختبار زمنياً)
- تعامل مع الفئات غير المتوازنة (undersampling/oversampling/SMOTE)

## كيفية المساهمة

1. افتح issue لوصف المشكلة أو الميزة.
2. اخلق فرع جديد `feature/...` أو `fix/...` ثم أرسل Pull Request.
3. اشرح التغييرات وأضف أمثلة إن أمكن.

## الرخصة

ضع هنا نوع الرخصة (مثال: MIT). يمكنك إضافة ملف LICENSE بالمستودع.

## تواصل

- صاحب المشروع: @youssef151222
- البريد (اختياري): example@example.com
