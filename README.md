# opencart
Расширение API для  интеграции со складской программой  [ZStore](http://zippy.com.ua/zstore).   

Модуль позволяет  получать заказы  с магазина, обновлять их статусы, отправлять в магазин новые  товары (синхронизация выполняется  по артикулу) обновить цены и количества  со  склада  в  магазине

Может быть использован  и с  другими складскими  программами. 

Совместим  с  Опенкарт 2.3 и 3.02


## Установка
 Установка  производится  как  обычно добавлением расширения на странице  администратора загрузкой файла zstore.ocmod.zip.
 Можно также установать вручную скопировав  файл zstore.php в каталог  catalog\controller\api\


 Авторизация выполняется  обычным образом как  и со встроеным  API.

## Методы API
* statuses()
Возвращает список  статусов заказов  в  магазине
* orders() 
возвращает список  заказов  по  укащаному статусу. Статус передеется  параметром status_id  (через POST как  и все в  API)
* updateorder()   Обновляет статусы ордеров  в магазине после  обработки на  складе. Передается в поле data как  массив  ключ значение - opder_id=>ststus_id
* articles()  Получение списка  артикулов  с магазина  чтобы  понимать  какие  товары  уже  там
* cats()  Возвращает список  категоритй товаров
* addproducts()  добавляет  товары  со склада  в магазин. Параметр cat  содержт категортию в  которую нужно добавить товар,
параметр  data массив товаров.  Передается  название, артикул описание, количество и цена.
* updatequantity()  Обновляет количество  товаров в магазине. Параметр data передает  массив ключ-значение - артикул товара=>количество
* updateprice() Обновляет цену товаров в магазине. Параметр data передает  массив ключ-значение - артикул товара=>цена

* getproducts() Загружает с  магазина товары которых нет на  складе на случай если товары были  добавлены  сначала  в  магазин



