1# **MongoDB**

## 🔷 Tổng quan MongoDB

### MongoDB

- **MongoDB** là một hệ quản trị cơ sở dữ liệu NoSQL mã nguồn mở, được phát triển bởi MongoDB Inc. Được ra mắt vào năm 2009, MongoDB nhanh chóng trở thành một trong những hệ quản trị cơ sở dữ liệu NoSQL phổ biến nhất nhờ tính linh hoạt, khả năng mở rộng, và hiệu suất cao trong việc xử lý dữ liệu.

-  Đặc Điểm Chính Của MongoDB:
    + **NoSQL** MongoDB là một cơ sở dữ liệu NoSQL, tức là không sử dụng bảng và hàng như các cơ sở dữ liệu quan hệ truyền thống (RDBMS). Thay vào đó, nó lưu trữ dữ liệu dưới dạng các tài liệu (documents).

    + **Định Hướng Tài Liệu (Document-Oriented)** Thay vì lưu trữ dữ liệu trong các bảng, MongoDB lưu trữ các tài liệu dưới dạng BSON (Binary JSON). Các tài liệu này tương tự như cấu trúc JSON, rất linh hoạt và có thể chứa dữ liệu dạng phức tạp.

    + **Linh Hoạt (Schema-less)** MongoDB không yêu cầu một schema cố định. Điều này có nghĩa là các tài liệu trong cùng một collection có thể có cấu trúc dữ liệu khác nhau.

    + **Mở Rộng Ngang (Horizontal Scaling)** MongoDB hỗ trợ tính năng sharding, cho phép phân phối dữ liệu trên nhiều server, giúp mở rộng quy mô khi dữ liệu và tải công việc tăng lên.

    + **Replication** Để đảm bảo tính sẵn sàng cao, MongoDB cung cấp tính năng replication. Một replica set bao gồm một primary node và nhiều secondary node. Nếu primary gặp sự cố, một secondary sẽ được bầu chọn thành primary.

    + **Dễ bảo trì** MongoDB thường được xem là dễ bảo trì hơn so với cơ sở dữ liệu truyền thống do có lượt đồ linh hoạt và quy trình tối ưu hoá đơn giản hơn

- Kiến Trúc Cơ Bản
    + **Database** Tập hợp các collection. Một MongoDB server có thể chứa nhiều database.

    + **Collection** Tương tự như một bảng trong cơ sở dữ liệu quan hệ, nhưng không yêu cầu các document trong collection phải có cùng một cấu trúc.

    + **Document** Là đơn vị lưu trữ cơ bản, tương tự như một hàng (row) trong cơ sở dữ liệu quan hệ, nhưng linh hoạt hơn. Mỗi document là một đối tượng BSON (mở rộng của JSON) chứa các cặp key-value.

- Các Tính Năng Nổi Bật
    + **Hiệu Suất Cao** MongoDB tối ưu hóa hiệu suất cho các ứng dụng xử lý khối lượng dữ liệu lớn nhờ cơ chế lưu trữ tài liệu và các chỉ mục (index) đa dạng.

    + **Sharding** MongoDB có thể phân chia dữ liệu thành các phân đoạn nhỏ hơn (shard) và lưu trữ trên nhiều máy chủ khác nhau, giúp hệ thống dễ dàng mở rộng quy mô khi có nhu cầu.

    + **Replication** Tính năng này đảm bảo rằng dữ liệu không bị mất ngay cả khi một trong các node gặp sự cố.

    + **Khả Năng Xử Lý Dữ Liệu Linh Hoạt** MongoDB hỗ trợ aggregation framework, giúp xử lý và biến đổi dữ liệu phức tạp với nhiều công cụ mạnh mẽ như `$group`, `$match`, `$sort`...

- Ứng Dụng MongoDB: MongoDB được sử dụng rộng rãi trong nhiều lĩnh vực nhờ tính linh hoạt và khả năng mở rộng của nó. Một số ứng dụng tiêu biểu:
    + **Web & Mobile Apps** MongoDB là sự lựa chọn lý tưởng cho các ứng dụng web và mobile vì nó có thể xử lý được khối lượng dữ liệu lớn và phi cấu trúc.

    + **Hệ Thống Quản Lý Nội Dung (CMS)**  Đối với các hệ thống quản lý nội dung, MongoDB cho phép lưu trữ nội dung với nhiều định dạng và cấu trúc khác nhau.

    + **Mạng Xã Hội** Các mạng xã hội cần xử lý lượng lớn dữ liệu người dùng và tương tác, một trong những thế mạnh của MongoDB.

    + **Internet of Things (IoT)** Dữ liệu phi cấu trúc và khối lượng lớn từ các thiết bị IoT rất phù hợp với MongoDB.

- Lợi Ích và Hạn Chế
    + Lợi Ích
        + Dễ mở rộng quy mô (scalable).
        + Linh hoạt trong việc lưu trữ dữ liệu không có cấu trúc cố định.
        + Hỗ trợ xử lý dữ liệu nhanh chóng và hiệu quả.
    + Hạn chế
        + Không hỗ trợ các giao dịch phức tạp (trong các phiên bản cũ hơn), mặc dù từ phiên bản 4.0 trở đi, MongoDB đã hỗ trợ giao dịch đa tài liệu.
        + Do không tuân thủ schema cố định, dữ liệu có thể trở nên phức tạp và khó quản lý nếu không thiết kế cẩn thận.

### Data Modeling

- **Data Modeling** là quá trình thiết kế cấu trúc dữ liệu của một ứng dụng để tối ưu hóa việc lưu trữ và truy vấn dữ liệu. Trong MongoDB, data modeling rất linh hoạt nhờ tính năng không yêu cầu schema cố định, nhưng việc lựa chọn mô hình dữ liệu đúng là rất quan trọng để đảm bảo hiệu suất và khả năng mở rộng của ứng dụng.

- Khái Niệm Cơ Bản Trong Data Modeling
    + Embed (nhúng dữ liệu)
        + **Embed** là quá trình nhúng các dữ liệu liên quan vào một document duy nhất. Điều này rất hữu ích khi dữ liệu có quan hệ 1-1 hoặc 1-n (một-nhiều) và bạn thường xuyên cần truy vấn toàn bộ dữ liệu cùng một lúc.
        + **Ưu điểm**: Truy vấn nhanh vì chỉ cần truy cập một document duy nhất.
        + **Nhược điểm**: Dữ liệu có thể bị lặp lại nếu nhúng dữ liệu vào nhiều nơi (dư thừa dữ liệu).
    + Reference (tham chiếu)
        + **Reference** là quá trình lưu trữ các dữ liệu liên quan trong các collection khác nhau và chỉ lưu trữ ID của các tài liệu khác trong document hiện tại. Điều này thường được sử dụng khi dữ liệu có mối quan hệ phức tạp, đặc biệt là quan hệ nhiều-nhiều.
        + **Ưu điểm**: Tránh lặp lại dữ liệu, dễ dàng quản lý các thực thể độc lập.
        + **Nhược điểm**: Truy vấn phức tạp hơn vì cần thực hiện nhiều truy vấn để lấy đủ dữ liệu.

### Tạo Database trong MongoDB

- Lệnh use trong MongoDB
    + Lệnh **use DATABASE_NAME** trong MongoDB được sử dụng để tạo cơ sở dữ liệu. Lệnh này sẽ tạo một cơ sở dữ liệu mới, nếu nó chưa tồn tài, nếu không thì, lệnh này sẽ trả về cơ sở dữ liệu đang tồn tại.
    + Cú pháp cơ bản của lệnh use DATABASE_NAME là như sau:
        ```
        use DATABASE_NAME
        ```
    + Ví dụ 
        ```
        >use mydb
        switched to db mydb
        ```
    + Để kiểm tra db tạo hay chưa 
        ```
        >db
        mydb
        ```
    + Kiểm tra danh sách csdl 
        ```
        >show dbs
        local     0.78125GB
        test      0.23012GB
        ```

### Xóa Database trong MongoDB

- Phương thức dropDatabase() trong MongoDB: Lệnh db.dropDatabase() trong MongoDB được sử dụng để xóa một cơ sở dữ liệu đang tồn tại.
    ```
        db.dropDatabase()
    ```
>Lệnh này sẽ xóa cơ sở dữ liệu đã chọn. Nếu bạn không chọn bất kỳ cơ sở dữ liệu nào, thì nó sẽ xóa cơ sở dữ liệu mặc định test.

- Ví dụ: kiểm tra danh sách các cơ sở dữ liệu có sẵn bởi sử dụng lệnh show dbs
    ```
    >show dbs
    local      0.78125GB
    mydb       0.23012GB
    test       0.23012GB
    >
    ```

- Nếu bạn muốn xóa cơ sở dữ liệu mới mydb, thì lệnh dropDatabase() sẽ là như sau:
    ```
    >use mydb
    switched to db mydb
    >db.dropDatabase()
    >{ "dropped" : "mydb", "ok" : 1 }
    >
    ```

### Tạo Collection trong MongoDB

- Phương thức db.createCollection(name, options) trong MongoDB được sử dụng để tạo Collection.
- Cú pháp cơ bản của lệnh createCollection() trong MongoDB như sau:
    ```
    db.createCollection(name, options)
    ```
- Ví dụ cú pháp cơ bản của phương thức createCollection() mà không có các options là như sau:

    ```
        >use test
        switched to db test
        >db.createCollection("mycollection")
        { "ok" : 1 }
        >
    ```

### Kiểu dữ liệu trong MongoDB
- **Chuỗi**: Đây là kiểu dữ liệu được sử dụng phổ biến nhất để lưu giữ dữ liệu. Chuỗi trong MongoDB phải là UTF-8 hợp lệ.

- **Số nguyên**: Kiểu dữ liệu này được sử dụng để lưu một giá trị số. Số nguyên có thể là 32 bit hoặc 64 bit phụ thuộc vào Server của bạn.

- **Boolean**: Kiểu dữ liệu này được sử dụng để lưu giữ một giá trị Boolean (true/false).

- **Double**: Kiểu dữ liệu này được sử dụng để lưu các giá trị số thực dấu chấm động.

- **Min/ Max keys**: Kiểu dữ liệu này được sử dụng để so sánh một giá trị với các phần tử BSON thấp nhất và cao nhất.

- **Mảng**: Kiểu dữ liệu này được sử dụng để lưu giữ các mảng hoặc danh sách hoặc nhiều giá trị vào trong một key.

- **Timestamp**: Giúp thuận tiện cho việc ghi chép hoặc đánh dấu thời điểm một Document được sửa đổi hoặc được thêm vào.

- **Object**: Kiểu dữ liệu này được sử dụng cho các Document được nhúng vào.

- **Null**: Kiểu dữ liệu này được sử dụng để lưu một giá trị Null.

- **Symbol**: Kiểu dữ liệu này được sử dụng giống như một chuỗi, tuy nhiên, nói chung nó được dành riêng cho các ngôn ngữ mà sử dụng kiểu symbol cụ thể.

- **Date** : Kiểu dữ liệu này được sử dụng để lưu giữ date và time hiện tại trong định dạng UNIX time. Bạn có thể xác định date time riêng cho bạn bằng việc tạo đối tượng Date và truyền ngày, tháng, năm vào trong đó.

- **Object ID**: Kiểu dữ liệu này được sử dụng để lưu giữ ID của Document.

- **Binary data**: Kiểu dữ liệu này được sử dụng để lưu giữ dữ liệu nhị phân.

- **Code**: Kiểu dữ liệu này được sử dụng để lưu giữ JavaScrip code vào trong Document.

- **Regular expression**: Kiểu dữ liệu này được sử dụng để lưu giữ Regular Expresion.

### Chèn Document trong MongoDB
- là một trong những thao tác cơ bản, cho phép bạn thêm dữ liệu vào collection. Trong MongoDB, mỗi document được lưu trữ dưới dạng một đối tượng BSON (Binary JSON). Bạn có thể sử dụng lệnh `insert()` hoặc các phương pháp tương tự để chèn một hoặc nhiều document vào collection.

- Chèn Một Document
    ```
    db.collection.insertOne(document);
    ```
- Ví dụ: 
    ```json
    db.users.insertOne({
    "name": "Nguyen Van A",
    "age": 25,
    "email": "nguyenvana@example.com"
    });
    ```
- Kết quả: 
    ```json
    {
    "acknowledged": true,
    "insertedId": ObjectId("5f4d8c9fa21b5e2f3c12f500")
    }
    ```

- Chèn nhiều document
    ```
    db.collection.insertMany([document1, document2, ...]);
    ```
- Ví dụ: 
    ```json
   db.users.insertMany([
  {
    "name": "Le Thi B",
    "age": 22,
    "email": "lethib@example.com"
  },
  {
    "name": "Tran Van C",
    "age": 30,
    "email": "tranvanc@example.com"
  }]);
    ```

- Kết quả: 
    ```json
    {"acknowledged": true,
    "insertedIds": {
        "0": ObjectId("5f4d8c9fa21b5e2f3c12f501"),
        "1": ObjectId("5f4d8c9fa21b5e2f3c12f502")
    }}
    ```

### Truy vấn Document trong MongoDB

- Truy Vấn Tất Cả Document: Lệnh `find()` được sử dụng để truy vấn dữ liệu trong MongoDB. Khi không truyền tham số nào, `find()` sẽ trả về tất cả các document trong collection.

    ```
    db.users.find();
    ```

- Truy Vấn Với Điều Kiện (Filter)
    ```
    db.collection.find({ field: value });
    ```
- Ví dụ: Truy vấn tất cả người dùng có tên là "Nguyen Van A":
     ```
    db.users.find({ name: "Nguyen Van A" });
    ```

### Cập nhật Document trong MongoDB

- là quá trình thay đổi nội dung của các document trong một collection. MongoDB cung cấp một số phương thức để cập nhật document, bao gồm cập nhật một document hoặc nhiều document, thay thế document, và sử dụng các toán tử cập nhật để thay đổi các trường cụ thể.

    ```
    db.collection.updateOne(filter, update, options);
    ```

- Ví dụ: 
    ```json
    db.users.updateOne(
    { name: "Nguyen Van A" },
    { $set: { age: 30 } }
    );
    ```

- Update many 
    ```
    db.collection.updateMany(filter, update, options);
    ```

- Ví dụ: 
    ```json
    db.users.updateMany(
    { age: { $lt: 18 } },
    { $set: { status: "not allowed" } }
    );
    ```

### Xóa Document trong MongoDB

- là thao tác loại bỏ các document khỏi một collection dựa trên các điều kiện cụ thể. MongoDB cung cấp các phương thức như `deleteOne()` và `deleteMany()` để hỗ trợ việc xóa một hoặc nhiều document. Dưới đây là hướng dẫn chi tiết về cách xóa document trong MongoDB cùng các ví dụ minh họa.

    ```
    db.collection.deleteOne(filter);
    ```
- Ví dụ: 
    ```json
    db.users.deleteOne({ name: "Nguyen Van A" });
    ```

- Xóa tất cả Document trong MongoDB

    ```
    >db.mycol.remove()
    >db.mycol.find()
    >
    ```

### Giới hạn bản ghi trong MongoDB

- Phương thức `limit()` trong MongoDB
    + Để giới hạn các bản ghi trong MongoDB, bạn cần sử dụng phương thức limit(). Phương thức limit() nhận một tham số ở dạng kiểu số, là số Document mà bạn muốn hiển thị.
- Cú pháp
    ```
    >db.COLLECTION_NAME.find().limit(NUMBER)
    ```
- Ví dụ
    + Collection với tên mycol có dữ liệu sau:
        ```json
            { "_id" : ObjectId(5983548781331adf45ec5), "title":"MongoDB Overview"}
            { "_id" : ObjectId(5983548781331adf45ec6), "title":"NoSQL Overview"}
            { "_id" : ObjectId(5983548781331adf45ec7), "title":"Tutorials Point Overview"}
        ```
    + Ví dụ sau chỉ hiển thị 2 Document trong khi truy vấn.
        ```json
            >db.mycol.find({},{"title":1,_id:0}).limit(2)
            {"title":"MongoDB Overview"}
            {"title":"NoSQL Overview"}
            >
        ```
    
- Phương thức `skip()` trong MongoDB
    + Ngoài phương thức `limit()`, trong MongoDB có một phương thức khác là `skip()` cũng nhận một tham số ở dạng số và được sử dụng để nhảy qua số Document đã xác định.
    + Cú pháp 
        ```
            >db.COLLECTION_NAME.find().limit(NUMBER).skip(NUMBER)
        ```
    + Ví dụ sau sẽ chỉ hiển thị Document thứ hai.
        ```json
            >db.mycol.find({},{"title":1,_id:0}).limit(1).skip(1)
            {"title":"NoSQL Overview"}
            >
        ```

### Sắp xếp bản ghi trong MongoDB

- Cú Pháp Cơ Bản của sort()
    ```
    db.collection.find(query).sort({ field: order });
    ```

- Ví dụ sắp xếp theo 1 trường
    ```
    db.users.find().sort({ age: 1 });
    ```

### Chỉ mục (Index) trong MongoDB

- Chỉ mục (Index) hỗ trợ việc phân giải các truy vấn hiệu quả hơn. Nếu không có chỉ mục, MongoDB phải quét qua mọi Document của một Collection để chọn các Document mà kết nối với lệnh truy vấn. Việc quét này có thể không hiệu quả và yêu cầu MongoDB xử lý một số lượng lớn dữ liệu.

- Phương thức ensureIndex() trong MongoDB
    + Cú pháp
        ```
        >db.COLLECTION_NAME.ensureIndex({KEY:1})
        ```
    + Ví dụ
        ```
        >db.mycol.ensureIndex({"title":1})
        >
        ```



## 🔷 Quan hệ (Relations)

### Mô hình One - One Relationships với Embedded Document

- Một quan hệ 1:1 có nghĩa là mỗi document trong collection này chỉ có thể liên kết với một document duy nhất trong một collection khác (và ngược lại). Khi sử dụng Embedded Document, chúng ta nhúng toàn bộ thông tin của document thứ hai vào bên trong document thứ nhất.

- Trong MongoDB, mô hình quan hệ **One-to-One (1:1)** có thể được thực hiện bằng cách sử dụng Embedded Document. Với Embedded Document, các dữ liệu liên quan được lưu trữ trong cùng một document thay vì tạo các document riêng biệt hoặc collections khác nhau. Điều này giúp tối ưu hóa cho các trường hợp truy xuất dữ liệu nhanh chóng và ít phức tạp khi mối quan hệ giữa các document là **1:1**.

    ```js
    {
    "_id": 1,
    "name": "Ngo Xuan A",
    "email": "hieunx@example.com",
    "profile": {
        "address": "123 Le Loi, DN",
        "phone": "0123456789",
        "birthday": "1990-01-01"
    }
    }
    ```

### Mô hình One - Many Relationships với References Document

- Trong MongoDB, mô hình **One-to-Many** Relationships được sử dụng khi một document (chủ thể) có mối quan hệ với nhiều document khác. Với mô hình Reference Documents, các document được lưu trữ riêng biệt trong các collection khác nhau và có thể tham chiếu đến nhau thông qua các trường chứa ObjectId hoặc các khóa duy nhất khác. Điều này rất phù hợp khi dữ liệu giữa các collection có tính độc lập tương đối hoặc dữ liệu có thể lớn và phức tạp.

- References Document được sử dụng tối ưu nhất để mô tả mối quan hệ **One-to-Many** giữa dữ liệu được kết nối

    ```js
    // customers
    db.customers.insertOne({
    _id: 1,
    name: "Nguyen Van A",
    email: "nguyenvana@example.com"
    });
    ```

    ```js
    // orders
    db.orders.insertOne({
    _id: 101,
    orderDate: "2024-09-01",
    totalAmount: 150.5,
    customerId: 1
    });
    ```

### Mô hình Many - Many Relationships với References Document

- Trong MongoDB, mô hình **Many-to-Many Relationships** được sử dụng khi một document trong một collection có thể liên kết với nhiều document trong một collection khác và ngược lại. Để quản lý mối quan hệ này, sử dụng Reference Documents là cách hiệu quả và linh hoạt. Với phương pháp này, các document sẽ tham chiếu đến nhau thông qua các trường khóa như **ObjectId** hoặc khóa duy nhất khác.

- References Document được sử dụng tối ưu nhất để mô tả mối quan hệ **Many - Many** giữa dữ liệu được kết nối

    ```js
    // students
    db.students.insertOne({
    _id: 1,
    name: "abc",
    email: "hieunx@example.com",
    enrolledCourses: [101, 102] // Tham chiếu đến các khóa học
    });
    ```

    ```js
    // courses
    db.courses.insertOne({
    _id: 101,
    courseName: "MongoDB Basics",
    description: "Learn the basics of MongoDB",
    studentsEnrolled: [1] // Tham chiếu đến các học viên
    });
    ```

    ```js
    // Cập nhật học viên: thêm khóa học vào danh sách
    db.students.updateOne(
    { _id: 1 },
    { $addToSet: { enrolledCourses: 103 } } // Thêm khóa học mới
    );

    // Cập nhật khóa học: thêm học viên vào danh sách
    db.courses.updateOne(
    { _id: 103 },
    { $addToSet: { studentsEnrolled: 1 } }
    );
    ```

### Hợp nhất các quan hệ tham chiếu (Merging Reference Relations)

- Trong MongoDB, việc hợp nhất các quan hệ tham chiếu (reference relations) liên quan đến việc kết hợp dữ liệu từ nhiều collection lại với nhau dựa trên mối quan hệ đã được định nghĩa. Điều này thường áp dụng khi sử dụng mô hình **One-to-Many** hoặc **Many-to-Many** với **Reference Documents**. Mục tiêu chính là lấy được thông tin liên quan từ nhiều collection một cách hiệu quả.

- MongoDB không có câu lệnh **JOIN** như trong SQL, nhưng bạn có thể sử dụng **Aggregation Framework** với lệnh $lookup để hợp nhất (merge) dữ liệu từ các collection khác nhau.

- Cách Hợp Nhất Quan Hệ Tham Chiếu Bằng `$lookup`

```json

{
  $lookup: {
    from: "<foreign_collection>",       // Tên collection cần tham chiếu
    localField: "<local_field>",        // Trường trong collection hiện tại
    foreignField: "<foreign_field>",    // Trường trong collection được tham chiếu
    as: "<new_field>"                  // Tên của mảng chứa kết quả hợp nhất
  }
}
```
- Các Tham Số Quan Trọng
    + `from`: Tên của collection mà bạn muốn tham chiếu (collection chứa dữ liệu cần hợp nhất).
    + `localField`: Trường trong collection hiện tại để thực hiện kết hợp.
    + `foreignField`: Trường trong collection được tham chiếu mà MongoDB sẽ so sánh với localField.
    + `as`: Tên mảng mới chứa dữ liệu hợp nhất từ collection tham chiếu.

- Ví Dụ: Hợp Nhất Dữ Liệu Học Viên và Khóa Học
    + `students` chứa thông tin về học viên, bao gồm danh sách các khóa học mà họ đã đăng ký.
    + `courses` chứa thông tin về khóa học, bao gồm danh sách học viên đã đăng ký khóa học đó.

    ```json
        // Collection students
        {
        "_id": 1,
        "name": "Nguyen Van A",
        "email": "nguyenvana@example.com",
        "enrolledCourses": [101, 102]
        }

        // Collection courses
        {
        "_id": 101,
        "courseName": "MongoDB Basics",
        "description": "Learn the basics of MongoDB"
        }
    ```
    > muốn lấy thông tin chi tiết về các khóa học mà học viên Nguyen Van A đã đăng ký, sử dụng quan hệ Many-to-Many với tham chiếu.

- Sử Dụng `$lookup` Để Hợp Nhất **Quan Hệ Many-to-Many**
    + Truy vấn aggregation với `$lookup`:
    ```json
        db.students.aggregate([
        {
            $lookup: {
            from: "courses",               // Collection chứa thông tin khóa học
            localField: "enrolledCourses", // Trường trong collection students (danh sách các khóa học đã đăng ký)
            foreignField: "_id",           // Trường khóa chính trong collection courses
            as: "courseDetails"            // Tên của mảng chứa kết quả hợp nhất
            }
        }
        ]);
    ```

    + Kết quả: MongoDB sẽ trả về dữ liệu học viên cùng với thông tin chi tiết về các khóa học mà họ đã đăng ký trong một mảng `courseDetails`
    
    ```json
        {
        "_id": 1,
        "name": "Nguyen Van A",
        "email": "nguyenvana@example.com",
        "enrolledCourses": [101, 102],
        "courseDetails": [
            {
            "_id": 101,
            "courseName": "MongoDB Basics",
            "description": "Learn the basics of MongoDB"
            },
            {
            "_id": 102,
            "courseName": "Advanced MongoDB",
            "description": "Dive deeper into MongoDB concepts"
            }
        ]
        }
    ```


## 🔷 Tương tác với cơ sở dữ liệu

### Truy vấn dữ liệu

- Truy vấn cơ bản với `find()` và `findOne()`
    + `findOne()`: Trả về một document đầu tiên mà MongoDB tìm thấy phù hợp với điều kiện.
    ```json
    db.customers.findOne({ name: "Nguyen Van A" });
    ```

    + `find()`: Trả về nhiều document phù hợp với điều kiện truy vấn. Mặc định trả về tất cả các document nếu không có điều kiện nào được đặt ra.
    ```json
    db.customers.find({ city: "DaNang" });
    ``
- Truy vấn với các toán tử so sánh
    + `$eq`: Bằng
    + `$ne`: Không bằng
    + `$gt`: Lớn hơn
    + `$gte`: Lớn hơn hoặc bằng
    + `$lt`: Nhỏ hơn
    + `$lte`: Nhỏ hơn hoặc bằng
    ```json
    db.orders.find({ totalAmount: { $gt: 100 } });
    ```
    > Truy vấn này sẽ trả về tất cả các đơn hàng có giá trị totalAmount lớn hơn 100.

- Truy vấn logic
    + `$and`: Kết hợp các điều kiện với logic AND
    + `$or`: Kết hợp các điều kiện với logic OR
    + `$not`: Phủ định điều kiện
    + `$nor`: Trả về kết quả không phù hợp với bất kỳ điều kiện nào
    ```json
        db.products.find({
        $and: [
            { price: { $gt: 100 } },
            { stock: { $gt: 10 } }
        ]
        });
    ```

- Truy vấn trên mảng
    + `$in`: Kiểm tra xem giá trị có tồn tại trong danh sách các giá trị được chỉ định.
    + `$all`: Kiểm tra xem mảng chứa tất cả các giá trị chỉ định.
    + `$size`: Kiểm tra kích thước của mảng.
    + `$elemMatch`: Trả về các document có ít nhất một phần tử trong mảng thỏa mãn tất cả các điều kiện.
    ```json
    // Tìm các sản phẩm có tags bao gồm cả "tech" và "smart"
    db.products.find({ tags: { $all: ["tech", "smart"] } });
    ```

     ```json
    // Tìm các sản phẩm có kích thước mảng tags bằng 3
    db.products.find({ tags: { $size: 3 } });
    ```

     ```json
    // Tìm các đơn hàng có ít nhất một sản phẩm có giá lớn hơn 100 và số lượng lớn hơn 2
    db.orders.find({
    items: { 
        $elemMatch: { 
        price: { $gt: 100 }, 
        quantity: { $gt: 2 }
        } 
    }
    });
    ```

- Truy vấn với **projection** (Chọn trường cần lấy)
    + Projection trong MongoDB cho phép chỉ định các trường mà muốn trả về từ kết quả truy vấn. Điều này giúp tiết kiệm bộ nhớ và tăng tốc độ truy vấn.
    + `1`: Trả về trường đó.
    + `0`: Không trả về trường đó.
    ```json
    // Chỉ trả về tên và email của khách hàng
    db.customers.find(
    { city: "Hanoi" },
    { name: 1, email: 1, _id: 0 }
    );
    ```
    > Truy vấn này sẽ trả về danh sách khách hàng từ Hanoi chỉ với các trường `name` và `email`, không trả về `_id`.

- Sắp xếp kết quả truy vấn `(sort())`
MongoDB cho phép sắp xếp kết quả theo một hoặc nhiều trường bằng cách sử dụng sort().

    + `1`: Sắp xếp tăng dần.
    + `-1`: Sắp xếp giảm dần.
    ```json
    // Trả về các sản phẩm sắp xếp theo giá từ cao xuống thấp
    db.products.find().sort({ price: -1 });
    ```

- Giới hạn và bỏ qua kết quả (`limit()` và `skip()`)
    + `limit()`: Giới hạn số lượng kết quả trả về.
    + `skip()`: Bỏ qua một số lượng kết quả nhất định.
    ```json
    // Lấy 5 sản phẩm đầu tiên có giá từ cao xuống thấp
    db.products.find().sort({ price: -1 }).limit(5);
    ```

- Truy vấn với regex (Biểu thức chính quy)
MongoDB hỗ trợ biểu thức chính quy (regex) để tìm kiếm các document với điều kiện chuỗi ký tự.
```json
// Tìm tất cả các khách hàng có tên bắt đầu bằng "Nguyen"
db.customers.find({ name: { $regex: "^Nguyen" } });
```

- Truy vấn với `aggregation`
    + Aggregation framework trong MongoDB cung cấp cách mạnh mẽ hơn để nhóm, lọc, và biến đổi dữ liệu. `$match`, `$group`, `$sort`, và `$project` là một số stage phổ biến trong aggregation.
    + Ví dụ: Tính tổng số lượng đơn hàng theo khách hàng
    ```json
    db.orders.aggregate([
    { $group: { _id: "$customerId", totalOrders: { $sum: 1 } } },
    { $sort: { totalOrders: -1 } }
    ]);
    ```
    >Truy vấn này sẽ nhóm các đơn hàng theo `customerId`, tính tổng số lượng đơn hàng của từng khách hàng và sắp xếp theo số lượng đơn hàng giảm dần.

- Truy vấn kết hợp với `$lookup`
    + `$lookup` được sử dụng để kết hợp dữ liệu từ nhiều collection.
    + Ví dụ: 
    ```json
    db.orders.aggregate([
    {
        $lookup: {
        from: "customers",
        localField: "customerId",
        foreignField: "_id",
        as: "customerDetails"
        }
    }
    ]);
    ```
    > Truy vấn này sẽ kết hợp dữ liệu từ collection `orders` và `customers`, thêm thông tin chi tiết của khách hàng vào mỗi đơn hàng.

### Thêm mới dữ liệu

- Trong MongoDB có thể thêm mới dữ liệu vào collection bằng các lệnh như `insertOne()` hoặc `insertMany()`. MongoDB lưu trữ dữ liệu dưới dạng các document JSON và khi bạn chèn một document mới, nó sẽ tự động gán một `_id` duy nhất cho mỗi document nếu bạn không cung cấp.
    + Sử dụng `insertOne()`
    ```js
    db.customers.insertOne({
    name: "Nguyen Van A",
    email: "nguyenvana@example.com",
    city: "DaNang"
    });
    ```
    > Document mới sẽ được thêm vào collection customers. Nếu không cung cấp trường _id, MongoDB sẽ tự động tạo một giá trị _id duy nhất.

    Kết quả
    ```json
    {
    "acknowledged": true,
    "insertedId": ObjectId("64fb45a9d5b5d1010f6c57e7")
    }
    ```

    +  Sử dụng insertMany()

        ```js
            db.customers.insertMany([
            { name: "Nguyen Van B", email: "nguyenvanb@example.com", city: "Hanoi" },
            { name: "Tran Thi C", email: "tranthic@example.com", city: "Ho Chi Minh" }
            ]);
        ```
        > Truy vấn này sẽ chèn hai document mới vào collection customers
        + Kết quả: MongoDB sẽ trả về danh sách các _id của những document đã được thêm.
        ```json
        {
        "acknowledged": true,
        "insertedIds": {
            "0": ObjectId("64fb45a9d5b5d1010f6c57e8"),
            "1": ObjectId("64fb45a9d5b5d1010f6c57e9")
        }
        }

        ```
    + Chèn Document với _id tùy chỉnh: có thể chỉ định giá trị _id của riêng mình thay vì để MongoDB tự động tạo.
    ```json
        db.customers.insertOne({
        _id: 1001,
        name: "Nguyen Van D",
        email: "nguyenvand@example.com",
        city: "Da Nang"
        });
    ```
    > Trong ví dụ này, document được chèn vào với `_id` là `1001`.

### Cập nhật dữ liệu

- MongoDB cung cấp nhiều phương thức để cập nhật dữ liệu trong các collection, cho phép thay đổi một hoặc nhiều document. Những phương thức này bao gồm `updateOne()`, `updateMany()`, và `replaceOne()`. Có thể chọn cập nhật toàn bộ document hoặc chỉ một số trường cụ thể trong document.
    +  Sử dụng `updateOne()`: được sử dụng để cập nhật một document đầu tiên phù hợp với điều kiện tìm kiếm. Nếu có nhiều document thỏa mãn điều kiện, chỉ document đầu tiên sẽ được cập nhật.
    ```js
    db.customers.updateOne(
    { name: "Nguyen Van A" },                // Điều kiện lọc
    { $set: { email: "newemail@example.com" } }  // Thao tác cập nhật
    );
    ```
    
    + Sử dụng `updateMany()`: được sử dụng để cập nhật tất cả các document phù hợp với điều kiện.
    ```js
    db.customers.updateMany(
    { city: "Hanoi" },                      // Điều kiện lọc
    { $set: { city: "Ha Noi" } }            // Thao tác cập nhật
    );
    ```
    >MongoDB sẽ cập nhật tất cả các document có trường `city` là "Hanoi" thành "Ha Noi"

    + Sử dụng `replaceOne()`
    ```js
    db.customers.replaceOne(
    { name: "Nguyen Van A" },                // Điều kiện lọc
    { name: "Nguyen Van A", email: "nguyenvana@example.com", city: "Da Nang" }  // Document mới
    );
    ```
    > Document của khách hàng "Nguyen Van A" sẽ bị thay thế hoàn toàn bằng document mới, chỉ chứa các trường `name`, `email`, và `city`.

    >`replaceOne()` thay thế toàn bộ document bằng một document mới. Cách này khác với `updateOne()` ở chỗ nó không chỉ cập nhật các trường cụ thể mà thay thế toàn bộ document.

### Xoá dữ liệu

- Trong MongoDB có thể xóa dữ liệu từ collection bằng các phương thức như `deleteOne()` và `deleteMany()`. Các phương thức này cho phép bạn xóa một hoặc nhiều document phù hợp với điều kiện tìm kiếm.
    + Sử dụng `deleteOne()`
    ```js
    db.customers.deleteOne({ name: "Nguyen Van A" });
    ```
    > MongoDB sẽ xóa document đầu tiên có trường name là "Nguyen Van A".

    + Sử dụng `deleteMany()`
    ```js
    db.customers.deleteMany({ city: "Hanoi" });
    ```
    > MongoDB sẽ xóa tất cả các document có trường `city` là "Hanoi"

### Toàn vẹn dữ liệu (Atomicity)

- **Tính nguyên tử (Atomicity) - tính toàn vẹn dữ liệu** trong MongoDB đảm bảo rằng các hoạt động CRUD trên document là thành công toàn bộ hoặc thất bại toàn bộ. Nghĩa là, nếu chỉ với một field của document xảy ra lỗi trong quá trình truy vấn dữ liệu thì toàn bộ field của document đó cũng sẽ rollback

- Atomicity ở cấp độ mỗi document, nghĩa là document có cấp cao nhất vì vậy nó bao gồm tất cả field trong document kể cả các Embedded Document, các mảng, ... 

- Khi một thao tác thực hiện thêm mới hoặc sửa đổi nhiều document (insertMany, updateMany) thì việc đó với mỗi document là Atomicity nhưng toàn bộ thao tác không phải Atomacity

    ```js
    db.insertMany([
        {
            // document insert success
            name: 'Xinmmeng X98 Keyboard',
            price: 1050000
        }, 
        {
            // document insert fail with price field error
            name: 'Hoco H35 Air',
            price: 'aaaaa'          
        },
        {
            // document insert success
            name: 'NB F80 Arm',
            price: 355000
        }
    ], {
        // insert without order
        ordered: false
    })
    ```

### Toán tử cập nhật

- **$set**
    + Toán tử này được sử dụng để cập nhật một hoặc nhiều trường trong document. Nếu trường không tồn tại, `$set` sẽ tạo trường mới với giá trị được cung cấp.
    + Ví dụ: Cập nhật địa chỉ email của khách hàng với `_id` là `1`
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $set: { email: "newemail@example.com" } }
    );
    ```

- **$unset**
    + Toán tử này được sử dụng để xóa một trường khỏi document.
    + Ví dụ: Xóa trường address khỏi document của khách hàng có `_id` là `1`
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $unset: { address: "" } }
    );
    ```
- **$inc**
    + Toán tử này được sử dụng để tăng hoặc giảm giá trị của một trường số nguyên.
    + Ví dụ: Tăng số lượng đơn hàng của khách hàng với `_id` là `1` lên 5.
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $inc: { orderCount: 5 } }
    );
    ```

- **$push**
    + Toán tử này được sử dụng để thêm một giá trị vào một mảng trong document.
    + Ví dụ: Thêm một sản phẩm vào mảng `purchasedItems` của khách hàng với `_id` là `1`.
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $push: { purchasedItems: "Product A" } }
    );
    ```

- **$addToSet**
    + Toán tử này tương tự như `$push`, nhưng chỉ thêm giá trị vào mảng nếu giá trị đó chưa tồn tại trong mảng.
    + Ví dụ: Thêm một sản phẩm vào mảng `purchasedItems` của khách hàng với `_id` là `1`, nhưng chỉ nếu sản phẩm đó chưa tồn tại.
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $addToSet: { purchasedItems: "Product A" } }
    );
    ```

- **$pop**
    + Toán tử này được sử dụng để xóa phần tử đầu tiên hoặc cuối cùng khỏi mảng.
    + Ví dụ: Xóa phần tử cuối cùng khỏi mảng `purchasedItems` của khách hàng với `_id` là `1`.
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $pop: { purchasedItems: 1 } }
    );
    ```

- **$setOnInsert**
    + Toán tử này chỉ được sử dụng trong giao dịch `upsert`. Nó sẽ thiết lập giá trị của trường chỉ khi document mới được chèn vào.
    + Ví dụ: Chèn một khách hàng mới nếu không có khách hàng nào có `_id` là `1`, và thiết lập giá trị cho trường `createdAt`.
    ```json
    db.customers.updateOne(
        { _id: 1 },
        { $setOnInsert: { createdAt: new Date() } },
        { upsert: true }
    );
    ```
