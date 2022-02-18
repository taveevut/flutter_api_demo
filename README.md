# ตัวอย่างไฟล์
- [/lib/main.dart](/lib/main.dart)

# ตั้งค่า Certificate(X509Certificate)
- เพิ่มคลาส (class)
```dartclass MyHttpOverrides extends HttpOverrides{
  @override
  HttpClient createHttpClient(SecurityContext? context){
    return super.createHttpClient(context)
      ..badCertificateCallback = (X509Certificate cert, String host, int port)=> true;
  }
}
```

- เพิ่ม `HttpOverrides.global = new MyHttpOverrides();` ในฟังก์ชัน main()
```dart
void main() {
  HttpOverrides.global = new MyHttpOverrides();
  runApp(MyApp());
}
```

# ตัวอย่างการดึงข้อมูล
[ดึงข้อมูลจาก RESTFul API](https://sysadmin.psu.ac.th/2021/05/30/flutter-ดึงข้อมูลจาก-restful-api/)
