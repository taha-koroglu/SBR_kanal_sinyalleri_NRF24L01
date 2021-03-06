# Kanal sinyallerinin NRF24L01 kablosuz modülüyle transferi
## Verici (Transmitter) işlevi gören NRF24L01 ve Arduino (Arduino 1)
İlk önce 1. Arduino'muz olan verici (transmitter) Arduino'muza **transmitter.ino** kodunu yükleyelim. Unutmayın Arduino'nun {A0, A1} analog giriş pinlerini joysticklerin çıkış bacaklarına bağlamalısınız.</br>
NRF24L01+PA modülünü adaptörüne takın ve adaptörün **CE** çıkışını Arduino'nun Digital 7 (**D7**), **CSN** çıkışını Arduino'nun **D8**, **SCK** çıkışını Arduino'nun **D13**, **MO** çıkışını **D11** ve de **MI** çıkışını Arduino'nun **D12** girişine bağlayın.</br>
Ayrıca NRF24L01 adaptörünün üzerindeki **V<sub>cc</sub>** çıkışını Arduino'nun **5V**, **GND** çıkışını Arduino'nun **GND** pinine bağlayın. 
**NRF24L01 adaptörünün V<sub>cc</sub> çıkışını 3.3V'a bağlamayın**. Zaten adaptör 5V'dan 3.3V'a voltajı düşürüyor (regüle ediyor) ve ayrıca stabil (yani kararlı ve güvenilir) bir voltaj sağlıyor.</br>
Eğer NRF24L01 adaptörünüz yoksa bağlantıları yine bahsedilen konfigürasyonda yapabilirsiniz ama Vcc ile GND arasına 10uF'lık elektrolitik kapasitör bağlamanız tavsiye ediliyor. 
Sadece NRF24L01 kullanıyorsanız (adaptörünüz yoksa) SAKIN Vcc'ye 5V bağlamayın, NRF24L01'e zarar verirsiniz.
## Alıcı (Receiver) işlevi gören NRF24L01 + Arduino (Arduino 2)
Yukarıda anlatılan verici (transmitter) kodunu yükledikten sonra 2. Arduino'ya **receiver.ino** kodunu yükleyin ve Arduino IDE ayarlar --> port --> COMX<br/>
Burada X 2. Arduino'nun COM numarası, sakın transmitter olan 1. Arduino'nun COM adresini seçmeyin. Doğru COM numarasını seçtikten sonra sağ üstte seri port penceresini açıp sağ altta seri port iletişim hızı olan baud rate'i **57600** seçin ve JOYSTICK ile oynayarak ekranda kanal 1 ve 2 değerlerinin değiştiğini gözlemleyin. Eğer yukarı-aşağı hareketi yapan potansiyometrenin çıkışını verici konumunda olan 1. Arduino'nun **A<sub>0</sub>** pinine bağladıysanız, JOYSTICK ile yukarı-aşağı hareketini yaptığınızda ekranda 1. kanal sinyalinin [0-255] arasında değiştiğini göreceksiniz. Benzer mantıkla, eğer sağa-sola hareket yapan potansiyometrenin çıkışını verici konumunda olan 1. Arduino'nun **A<sub>1</sub>** pinine bağladıysanız, JOYSTICK ile sağ-sol hareketini yaptığınızda ekranda 2. kanal sinyalinin [0-255] arasında değiştiğini göreceksiniz.<br/>
## Arduino --> MATLAB Seri Port iletişimi ile kanal sinyallerinin görselleştirilmesi
Ardından MATLAB kodumuz olan **serial_port_receiver.m** dosyasını doğru port ismini girerek çalıştırın. Doğru portu belirlemek için MATLAB'ı açınca **serialportlist** komutunu kullanabilirsiniz veya Windows'da Aygıt Yöneticisi'ne gidip orada Bağlantı Noktaları (COM ve LPT) üzerine tıklayabilirsiniz.</br>
Yukarıda Code yazan yeşil bağlantıya tıklarsanız bu sayfadaki kodları zip dosyası halinde bilgisayarınıza indirebilirsiniz.</br>
<img src="figure/connections.jpg" alt="Arduino NRF24L01 connections" height="200"/>

*Şekil 1:* Arduino ve NRF24L01 kablosuz modül arasındaki bağlantılar.

## Malzemeler
[1] NRF24L01 kablosuz modül - https://www.direnc.net/nrf24l01-wireless-modul<br/>
[2] NRF24L01kablosuz modül adaptörü - https://www.direnc.net/8-pin-nrf24l01-wireless-modul-adaptoru<br/>
[3] NRF24L01 + PA kablosuz modülü (daha kuvvetli bir iletişim - anten var) - https://www.direnc.net/nrf24l01-plus-pa-wireless-modul</br>
# Videoyu aşağıdaki resime tıklayarak izleyebilirsiniz 
[![IMAGE ALT TEXT HERE](figure/thumbnail.jpg)](https://www.youtube.com/watch?v=FZUj0kXy1hs)</br></br>
