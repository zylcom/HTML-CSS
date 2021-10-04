# CSS Flexbox

## Apa Itu Flexbox

Flexbox adalah metode tata letak satu dimensi untuk mengatur item dalam baris atau kolom. Flexbox diperkenalkan di CSS versi terbaru yaitu, CSS3. Dengan flexbox, mudah untuk memusatkan elemen pada halaman dan membuat antarmuka pengguna dinamis yang menyusut dan meluas secara otomatis.

Untuk membuat elemen HTML menjadi flexbox kita bisa pilih elemen tersebut dengan menggunakan CSS selector dan menambahkan properti `display` dengan value `flex`.

```css
.flex-container {
  display: flex;
}
```

## Flexbox Layout

![flex-model](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png)

- Main axis merupakan sumbu utama yang arahnya horizontal atau mendatar. Awal sumbu disebut main start dan akhir sumbu disebut main end.
- Cross axis merupakan sumbu yang arahnya vertikal atau tegak. Awal sumbu disebut cross start dan akhir sumbu disebut cross end.
- Flex container merupakan parent elemen dari flex item yang telah kita atur dengan CSS menggunakan `display: flex;`.
- Flex item merupakan child elemen dari flex container.
- Main size merupakan lebar dari flex item.
- Cross size merupakan tinggi dari flex item.
- Beberapa CSS properti di flex container:
  - `flex-direction`
  - `flex-wrap`
  - `flex-flow`
  - `justify-content`
  - `align-items`
  - `align-content`
- Beberapa CSS properti di flex item:
  - `order`
  - `flex-grow`
  - `flex-shrink`
  - `flex-basis`
  - `flex`
  - `align-self`

## Properti di Flex Container

Berikut adalah beberapa properti CSS yang ada di flex container untuk mengatur flex item:

- `flex-direction` - Untuk menentukan arah flex item di dalam flex container.

  Contoh:

  Untuk mengatur flex item secara vertikal dengan arah dari atas ke bawah.

  ```css
  .flex-container {
    flex-direction: column;
  }
  ```

  Result:
  ![column](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-direction_column.png)

  Untuk mengatur flex item secara horizontal dengan arah dari kiri ke kanan

  ```css
  .flex-container {
    flex-direction: row;
  }
  ```

  Result:
  ![row](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-direction_row.png)

  Sama seperti row namun dengan arah sebaliknya

  ```css
  .flex-container {
    flex-direction: row-reverse;
  }
  ```

  Result:
  ![row-reverse](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-direction_row-reverse.png)

  Sama seperti column namun dengan arah sebaliknya

  ```css
  .flex-container {
    flex-direction: column-reverse;
  }
  ```

  Result:
  ![column-reverse](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-direction_column-reverse.png)

- `flex-wrap` - Untuk menentukan apakah flex item harus wrap atau tidak, jika tidak ada cukup ruang untuk mereka pada main axis.

  Contoh:

  Flex item akan wrap jika tidak ada cukup ruang di dalam container

  ```css
  .flex-container {
    flex-wrap: wrap;
  }
  ```

  Result:
  ![wrap](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-wrap_wrap.png)

  Flex item tidak akan wrap meskipun tidak ada cukup ruang di dalam container

  ```css
  .flex-container {
    flex-wrap: nowrap;
  }
  ```

  Result:
  ![nowrap](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-wrap_nowrap.png)

  Flex item akan wrap dengan arah yang sebaliknya

  ```css
  .flex-container {
    flex-wrap: wrap-reverse;
  }
  ```

  Result:
  ![wrap-reverse](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-wrap_wrap-reverse.png)

- `flex-flow` - Shorthand untuk `flex-direction` dan `flex-wrap`.

  Contoh:

  ```css
  .flex-container {
    flex-direction: row;
    flex-wrap: wrap;
  }
  ```

  Maka shorthand nya akan seperti ini

  ```css
  .flex-container {
    flex-flow: row wrap;
  }
  ```

- `justify-content` - Untuk menyejajarkan flex item secara horizontal saat item tidak menggunakan semua ruang yang tersedia di main axis.

  Contoh:

  Menyejajarkan flex item di tengah main axis

  ```css
  .flex-container {
    justify-content: center;
  }
  ```

  Result:
  ![center](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/justify-content_center.png)

  Menyejajarkan flex item di awal main axis

  ```css
  .flex-container {
    justify-content: flex-start;
  }
  ```

  Result:
  ![flex-start](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/justify-content_flex-start.png)

  Menyejajarkan flex item di akhir main axis

  ```css
  .flex-container {
    justify-content: flex-end;
  }
  ```

  Result:
  ![flex-end](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/justify-content_flex-end.png)

  Flex item akan memiliki ruang kosong diantara flex item

  ```css
  .flex-container {
    justify-content: space-between;
  }
  ```

  Result:
  ![space-between](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/justify-content_space-between.png)

  Flex item akan memiliki ruang kosong disekitarnya

  ```css
  .flex-container {
    justify-content: space-around;
  }
  ```

  Result:
  ![space-around](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/justify-content_space-around.png)

  Flex item akan memiliki ruang kosong disekitarnya dengan ukuran yang sama sesuai panjang main axis

  ```css
  .flex-container {
    justify-content: space-evenly;
  }
  ```

  Result:
  ![space-evenly](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/justify-content_space-evenly.png)

- `align-items` - Untuk menyejajarkan flex item secara vertikal saat item tidak menggunakan semua ruang yang tersedia pada cross axis.

  Contoh:

  Menyejajarkan flex item di tengah cross axis

  ```css
  .flex-container {
    align-items: center;
  }
  ```

  Result:
  ![center](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-items_center.png)

  Flex item akan diregangkan sesuai dengan panjang cross axis

  ```css
  .flex-container {
    align-items: stretch;
  }
  ```

  Result:
  ![stretch](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-items_stretch.png)

  Menyejajarkan flex item di awal cross axis

  ```css
  .flex-container {
    align-items: flex-start;
  }
  ```

  Result:
  ![flex-start](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-items_flex-start.png)

  Menyejajarkan flex item di akhir cross axis

  ```css
  .flex-container {
    align-items: flex-end;
  }
  ```

  Result:
  ![flex-end](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-items_flex-end.png)

  Flex item akan diposisikan di garis dasar container

  ```css
  .flex-container {
    align-items: baseline;
  }
  ```

  Result:
  ![baseline](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-items_baseline.png)

- `align-content` - Untuk memodifikasi perilaku properti flex-wrap. Hal ini mirip dengan align-item, tapi bukan untuk menyelaraskan flex item, melainkan untuk menyelaraskan garis flex.

  Contoh:

  Garis dikemas ke arah tengah container

  ```css
  .flex-container {
    align-content: center;
  }
  ```

  Result:
  ![center](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_center.png)

  Garis meregang untuk mengambil ruang yang tersisa di container

  ```css
  .flex-container {
    align-content: stretch;
  }
  ```

  Result:
  ![stretch](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_stretch.png)

  Garis dikemas ke awal cross axis

  ```css
  .flex-container {
    align-content: flex-start;
  }
  ```

  ![flex-star](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_flex-start.png)

  Garis dikemas ke akhir cross axis

  ```css
  .flex-container {
    align-content: flex-end;
  }
  ```

  Result:
  ![flex-end](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_flex-end.png)

  Garis didistribusikan secara merata di dalam container

  ```css
  .flex-container {
    align-content: space-between;
  }
  ```

  Result:
  ![space-between](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_space-between.png)

  Garis didistribusikan secara merata di dalam container, dengan ruang setengah ukuran di kedua ujungnya

  ```css
  .flex-container {
    align-content: space-around;
  }
  ```

  Result:
  ![space-around](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_space-around.png)

  Garis didistribusikan secara merata di dalam container, dengan ruang yang sama di sekelilingnya

  ```css
  .flex-container {
    align-content: space-evenly;
  }
  ```

  Result:
  ![space-evenly](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-content_space-evenly.png)

## Properti di Flex Item

Berikut adalah beberapa properti CSS yang ada di flex item:

- `order` - Untuk menentukan urutan flex item di dalam container yang sama.

  Contoh:

  Flex item akan berurutan mulai dari flex-item-1, flex-item-2, flex-item-3 sesuai order yang diberikan. Nilai defaultnya adalah 0.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    order: 3;
  }

  .flex-container .flex-item-2 {
    order: 2;
  }

  .flex-container .flex-item-3 {
    order: 1;
  }
  ```

  Result:
  ![order](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/order.png)

- `flex-grow` - Untuk menentukan seberapa banyak flex item akan tumbuh relatif terhadap flex item lainnya di dalam container yang sama.

  Contoh:

  flex-item-1 akan memiliki ukuran lebih besar relatif terhadap flex item lainnya. Nilai defaultnya adalah 0.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    flex-grow: 3;
  }

  .flex-container .flex-item-2 {
    flex-grow: 1;
  }

  .flex-container .flex-item-3 {
    flex-grow: 1;
  }
  ```

  Result:
  ![flex-grow](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-grow.png)

- `flex-shrink` - Untuk menentukan seberapa banyak flex item akan menyusut relatif terhadap flex item lainnya di dalam wadah yang sama.

  Contoh:

  flex-item-1 akan menyusut lebih kecil relatif terhadap ukuran flex item lainnya. Nilai defaultnya adalah 1.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    flex-shrink: 3;
  }
  ```

  Result:
  ![flex-shrink](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-shrink.png)

- `flex-basis` - Untuk menentukan panjang awal flex item.

  Contoh:

  flex-item-1 akan memiliki panjang awal dengan ukuran 300px.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    flex-basis: 300px;
  }
  ```

  Result:
  ![flex-basis](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/flex-basis.png)

- `flex` - Untuk shorthand properti flex-grow, flex-shrink, dan flex-basis.

  Contoh:

  Tidak menggunakan shorthand.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    flex-grow: 1;
    flex-shrink: 2;
    flex-basis: 300px;
  }
  ```

  Saat menggunakan shorthand.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    flex: 1 2 300px;
  }
  ```

- `align-self` - Untuk menentukan perataan flex item secara spesifik untuk item tertentu (menimpa properti align-items container).

  Contoh:

  flex-item-1 akan berada di tengah cross axis, flex-item-2 akan berada di awal cross axis,
  flex-item-3 akan berada di akhir cross axis.

  ```css
  .flex-container {
    display: flex;
  }

  .flex-container .flex-item-1 {
    align-self: flex-start;
  }

  .flex-container .flex-item-2 {
    align-self: center;
  }

  .flex-container .flex-item-3 {
    align-self: flex-end;
  }
  ```

  Result:
  ![align-self](https://raw.githubusercontent.com/zylcom/flexbox-img/main/images/align-self.png)

  ## Referensi

  Untuk referensi lengkapnya, kalian bisa mengunjungi website berikut:

  - [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
  - [W3Schools](https://www.w3schools.com/css/css3_flexbox.asp)
