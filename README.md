# Online-Retail-II

Bộ dữ liệu Online Retail II này bao gồm tất cả các giao dịch của một doanh nghiệp bán lẻ trực tuyến (không có cửa hàng vật lý) có trụ sở và đăng ký kinh doanh tại Vương quốc Anh, diễn ra trong khoảng thời gian từ ngày 01/12/2009 đến ngày 09/12/2011. Công ty chủ yếu kinh doanh các mặt hàng quà tặng độc đáo phù hợp cho mọi dịp; trong đó, nhiều khách hàng của công ty là các đơn vị bán buôn. \

Dataset source (https://archive.ics.uci.edu/dataset/502/online+retail+ii)

1. Load & làm sạch dữ liệu 

Đọc file dữ liệu dạng ARFF (dataset_), parse phần @ATTRIBUTE để lấy tên cột và phần @DATA để lấy dữ liệu. \
Gán tên cột: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country. \
Kiểm tra describe(), info(), shape, missing values. \
Phát hiện và xử lý giá trị âm ở Quantity và Price (chuyển thành trị tuyệt đối bằng .abs()).

2. EDA - Phân tích khám phá 

Biểu đồ top 10 quốc gia theo số giao dịch. \
Top StockCode và Description phổ biến nhất. \ 
Phát hiện outlier bằng phương pháp IQR cho Quantity và Price. \
Vẽ histogram phân phối đầy đủ + zoom cho cả 2 biến. \
Cho phép nhập tên quốc gia (input()), sau đó liệt kê top 50 sản phẩm bán chạy nhất tại quốc gia đó.

3. Mô hình dự đoán Customer Churn 

Định nghĩa "churn" = khách hàng không mua trong 90 ngày gần nhất. \
Tạo feature RFM (Recency, Frequency, Monetary) + các đặc trưng khác (CustomerLifetime, PurchaseFrequency...). \
Train 3 mô hình: Logistic Regression, Random Forest, Gradient Boosting. \
So sánh Train vs Test performance (Accuracy, Precision, Recall, F1, ROC-AUC), cảnh báo overfitting. \
Vẽ Feature Importance, ROC Curves, Confusion Matrix, biểu đồ tỷ lệ churn. \
Liệt kê top 20 khách hàng có nguy cơ churn cao nhất.
