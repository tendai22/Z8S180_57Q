# Z8S180_57Q kuma's repository

GazelleさんのZ8S180_57Q基板を回路図に起こすためのリポジトリです。

以下、気づいたことを追記してゆきます。

* 直結方式: CPUの/MREQ,/RD,/WRが直接SRAMに入っており、かつPICにも入っている。
  アドレスバスはA0-A15まで全つなぎであるため、PICはCPUをBUSRQで止めてからSRAMに直接アクセスする。

* A17が選択方式: 回路図ではジャンパが3個あり、それぞれ、VCC, GND, PIC-RC7とショートできるようになっている。現状ではどれにもつながっていない。ブートローディングのためにはGNDショートとすべき。

* クロックはCPUに水晶を接続して生成させる方法と、PIC-RA3から供給する方法とがある。

* CPUのUART0が直接引き出せるようになっている。J6に出ている。

* シリアルのVCCはジャンパで切断できるようになっている。というか、ジャンパピンを挿さないと接続しない(J5とJ15)。

* 電源は3種類から選択できる。ACジャック、USBシリアル2種(Z8S180側、PIC側)。

