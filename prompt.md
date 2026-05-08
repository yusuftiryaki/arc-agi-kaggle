Kaggle üzerindeki  [Neuro Golf 2026](https://www.kaggle.com/competitions/neurogolf-2026/overview) yarışmasın katılacağız.

Yarışma ile ilgili detayları [docs](docs) klasöründe bulabilirsin.

Başlangıç için Kaggle üzerinde çalışacak ve Benchmark task'ları kullanarak LMM çağıracak bir [notebook](arc-agi-kaggle.ipynb) hazırlandı.

Yarışma komitesi tarafından  ONNX değerlendirme ve skorlama için gerekli script: [script](neurogolf_utils.py) Ürtilen scriptin yada derlenen ONNX'in görevi çözüp çözülmediği yada alınan skor buradaki fonksiyonlar kullanılarak hesaplanabilir.

Proje için genel yaklaşım prensiplerimiz şu şekilde:

- ARC-AGI görevini çözme scriptini yazma görevi LLM'e atanır
- LLM uygun yönergeler ile çözüm uzayını daraltacak şekilde yönlendirilir
- LLM için yönergeler sentezci adı verilen bir modül tarafından yapılır.
- gozlemci adlı bir modül üzerinde çalışılan ARC-AGI görevi için LLM'e verilmek üzere görev hakkında açıklayıcı ve yardımcı bilgiler çıkarır.
- hakem adlı bir modül LLM' den gelen cevabı inceler ve yarışma için değerlendirir. LLM'e yapılacak geri bildirimin hazırlanmasını sağlar.
- Elde edilmesi gereken minumum skor ve LLM ile maksimum deneme sayısı parametrik olmalıdır. Bu denemeler sonucunda elde edilen maksimum skora(yada çözülememe durumuna) ilişkin ham LMM cevapları, LLM tarafından oluşturulan python script ve derlenmiş ONNX dosyanın path'i daha sonra ulaşılmak üzere kaydedilmelidir. 
- hakem görevin neden çözülemediğine dair yada sokurun neden düşük olduğuna dair detaylı açıklamalar vermelidir
