<B> Thư mục app  </B>

Đây là thư mục quan trọng nhất của project vì đây là nơi chứa phần lớn source code của ứng dụng, cũng là nơi mà bạn sẽ thao tác nhiều nhất trong quá trình phát triển ứng dụng Rails.

Thư mục này chứa các thư mục con :

<I>	assets :</I> chứa các file ảnh, css, javascripts đây là những file được tạo ra bởi developer. Còn các thư viện css, javascript bên thứ 3 cung cấp như bootstrap, jquery, ... sẽ được lưu trữ ở thư mục Vendor phía bên dưới. Ngoài ra các bạn cũng có thể sử dụng các thư viện css, javascripts thông qua các gem mà Ruby cung cấp, chúng ta sẽ tìm hiểu kỹ ở phần này khi đến phần Gemfile.

<I>	 controllers :</I>  chứa các tập tin controller làm nhiệm vụ điều hướng các luồng chạy của ứng dụng. Các file controller bản chất là các file ruby nên có phần mở rộng .rb

<I>	models:</I> là nơi chứa các đối tượng chính trong ứng dụng Rails, các model khi được tạo ra từ câu lệnh

		rails generate model <tên model>

Mặc định sẽ được kế thừa từ lớp ApplicationRecord < ActiveRecord::Base trong rails lớp ActiveRecord đóng vai trò trung gian để kết nối ứng dụng Rails với Database do đó các tập tin model còn đóng vai trò kết nối với Database để lưu trữ và truy vấn dữ liệu.

Các file model bản chất là các file ruby nên có phần mở rộng .rb

<I>	views:</I> chứa các tập tin views được sử dụng bởi controller để hiển thị nội dung web cho người dùng.

Các tập tin views khi được sinh ra mặc định sẽ có phần mở rộng là .html.erb

<I>	helpers:</I> các tập tin helpers chứa các hàm(hoặc các lớp) hỗ trợ được sử dụng bởi controller, views, models.

<I>	mailers:</I> chứa các tập tin liên quan đến việc gửi mails của ứng dụng.

<B> Thư mục bin</B>

Thư mục này bao gồm các đoạn mã script dùng để khởi động ứng dụng rails hoặc dùng để thiết lập deloy ứng dụng

<B> Thư mục config</B>

Thư mục này chứa các tập tin liên quan đến việc cấu hình của ứng dụng Rails.

<I>	Tập tin database.yml </I> là tập tin dùng để cấu hình kết nối tới database của ứng dụng rails. Ở đây sẽ khai báo hệ quản trị csdl nào sẽ được sẽ dụng (SQL Server, My SQL, SQLite, Oracle,...)và các thông số cần thiết để truy cập (username, password, database name).

<I>	Tập tin routes.rb </I> đây là tập tin mà chúng ta cần lưu ý nhất trong thư mục này vì sau này các bạn sẽ làm việc với nó khá nhiều. Tập tin này là nơi để khai báo các đường dẫn đến các file controller/action khi bạn gọi request ở phía client.

Chi tiết về việc khai báo hay sử dụng file này mình sẽ hướng dẫn kĩ hơn ở phần sau, khi chúng ta bắt tay vào thực hành xây dựng một ứng dụng "Login" đơn giản.

Ngoài ra thư mục này còn chứa các thư mục con khác :

<I>	environments</I> là nơi chứa các tập tin cấu hình cho từng môi trường phát triển developement, production hay test,...

<I>	initializers</I> là nơi chứa các tập tin cho việc khởi tạo ban đầu của ứng dụng hay của các gem,...

<I>	locales </I>là nơi chứa các tập tin phục vụ cho việc hiển thị đa ngôn ngữ của ứng dụng (I18n)

<B>Thư mục db </B>

Thư mục này chứa các tập tin migrations dùng để tạo cấu trúc schema cho database.

<I>	Tập tin seeds</I> là nơi để nhà phát triển viết các đoạn mã script để cập nhật dữ liệu cho database.

Để gọi thực thi file này ta thực hiện lệnh

	rake db:seed

<B> Thư mục lib</B>

Bao gồm các thư viện được dùng trong ứng dụng. Thông thường các thư viện này được viết bởi chính những lập trình viên tham gia vào viết ứng dụng. Các thư viện của bên thứ 3 thường không được đặt ở trong thư mục này mà được đặt ở thư mục Vendor

Thư mục này còn chức thư mục con là tasks đây là thư mục dùng để chứa các rake task trong ứng dụng rails

<B> Thư mục log</B>

Chứa các bản ghi log các thông tin trong quá trình cài đặt, khởi động, chạy hay ngừng ứng dụng.

<B> Thư mục public</B>

Nội dung của các tập tin đặt trong thư mục này sẽ có thể được tải trực tiếp về trình duyệt. Như các file hình ảnh, âm thanh,...

<B> Thư mục test</B>

Thư mục này chức các tập tin và thư mục con phục vụ cho việc test ứng dụng : testcase, unit test, intergration test,...

<B> Tập tin Gemfile và Gemfile.lock</B>

<I>	Gemfile</I> là một trong những tập tin quan trọng nhất trong Rails mà chúng ta làm việc thường xuyên nhất.

Rails là một framework được xây dựng với mục đích hỗ trợ nhà phát triển xây dựng ứng dụng web nhanh nhất do đó việc tích hợp các thư viện hỗ trợ là một trong những chức năng đặc trưng của Rails.

Các thư viện hỗ trợ được tích hợp vào ứng dụng Rails thông qua các gem, các bạn có thể tìm hiểu thêm về Ruby gem ở đây https://rubygems.org/

Chỉ cần khai báo tên gem vào trong tập tin Gemfile như bên dưới

	gem 'sqlite3'

Sau đó chạy lệnh:

	bundle install

Là gem đó đã được tích hợp vào ứng dụng Rails.

<B>	Tập tin Rakefile</B>

Tập tin Rakefile được Rails sử dụng để tìm kiếm các tác vụ mà chúng có thể được thực thi trên cửa sổ dòng lệnh thông qua rake. Bạn không nên định nghĩa trực tiếp các tác vụ này trong Rakefile mà việc định nghĩa các tác vụ này được thực hiện thông qua các tập tin trong thư mục lib/tasks.
