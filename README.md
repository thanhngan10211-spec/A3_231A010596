# Lab A3: Thiet ke giao dien voi XML Layout & Tai nguyen

Mon hoc: Lap trinh tren cac thiet bi di dong (INT4211)
Sinh vien thuc hien: Vo Phan Thanh Ngan
MSSV: 231A010596
Lop: CNTT - LTDD
Truong: Dai hoc Van Hien

---

## 1. Mo ta du an 
Du an Lab A3 thuc hien thiet ke giao dien Android su dung XML Layout, thuc hanh tach va quan ly tai nguyen (strings, colors, dimens, drawables), xay dung giao dien phang voi ConstraintLayout, ho tro man hinh ngang (layout-land), man hinh may tinh bang (layout-sw600dp), va Che do toi (Dark Mode).


## 2. Cong nghe su dung 
- Ngon ngu lap trinh: Java / Android SDK (API 24+)
- Giao dien UI: XML Layout, Material Design 3 Components
- IDE & Cong cu: Android Studio, Git / GitHub
- Kien truc Layout: LinearLayout, FrameLayout, ScrollView, ConstraintLayout

## 3. Cac tinh nang & Bo cuc trong du an
- Cau truc giao dien LinearLayout & FrameLayout:
  - Header anh bia bo goc nen gradient ket hop FrameLayout de dat anh dai dien tron de len mep duoi.
  - Form dang nhap chuan Material Design voi TextInputLayout (OutlinedBox), ho tro icon dau o va nut an/hien mat khau (password_toggle).
  - Hang tuy chon gom CheckBox "Ghi nho dang nhap" va nut "Quen mat khau?" can chinh 2 ben qua Space (layout_weight="1").
  - Dai phan cach chu "hoac" can doi 2 ben bang 2 the <View> cao 1dp.
  - The ho so sinh vien (view_profile_card.xml) duoc nhung qua the <include>, chua thong tin ca nhan va 2 o thong ke chia doi bang layout_weight.
  - Toan bo giao dien chinh dat trong ScrollView ho tro cuon man hinh.

- Dung lai bang ConstraintLayout phang (ConstraintDemoActivity):
  - Giam do sau cay view xuong 1 tang duy nhat.
  - Su dung Guideline trai/phai de co dinh le.
  - Su dung Chain ngang (spread) de chia deu khong gian nut bam.

- Bo cuc man hinh ngang (res/layout-land):
  - Bo cuc 2 cot linh hoat (Cot trai: Header + The ho so; Cot phai: Form dang nhap).
  - Giu nguyen toan bo android:id de khong phai chinh sua code Java.

### Bai nang cao 
1. NC1 - Che do toi (Dark Mode):
   - Dinh nghia bang mau toi trong res/values-night/colors.xml.
   - Tu dong chuyen doi mau nen, van ban va be mat phan tu theo cai dat he thong.
2. NC2 - Bo cuc may tinh bang (res/layout-sw600dp):
   - Thiet ke giao dien 2 cot toi uu khong gian hien thi cho man hinh Tablet (kich thuoc sw600dp).

## 4. Cau truc thu muc du an 
app/src/main/
├── java/vn/edu/vhu/ltdd/a3layout/
│   ├── MainActivity.java            # Activity chinh xu ly giao dien va su kien
│   └── ConstraintDemoActivity.java  # Activity minh hoa ConstraintLayout
└── res/
    ├── drawable/
    │   ├── bg_avatar.xml            # Shape oval lam vien avatar
    │   ├── bg_header.xml            # Gradient header bo goc duoi
    │   └── bg_stat.xml              # Nen khoi thong ke
    ├── layout/
    │   ├── activity_constraint_demo.xml # Giao dien phang ConstraintLayout
    │   ├── activity_main.xml            # Giao dien chinh doc (LinearLayout)
    │   └── view_profile_card.xml        # The ho so nhung bang <include>
    ├── layout-land/
    │   └── activity_main.xml            # Bo cuc 2 cot man hinh ngang
    ├── layout-sw600dp/
    │   └── activity_main.xml            # Bo cuc 2 cot danh cho Tablet
    ├── values/
    │   ├── colors.xml              # Bang mau giao dien sang (Light Mode)
    │   ├── dimens.xml              # Thang khoang cach dung chung (space_sm, md, lg...)
    │   └── strings.xml             # Tai nguyen chuoi van ban
    └── values-night/
        └── colors.xml              # Bang mau giao dien toi (Dark Mode - NC1)
