# CENTOS 7 ECLIPSE C++ UPDATE(C++17)
CENTOS 7 ECLİPSE C++ GÜNCELLEME(C++17)

CENTOS 7 ECLİPSE C++ GÜNCELLEME(C++17)
A)	CENTOS 7 KURULUMU
       1-Centos 7 kurulmalı

B) ECLİPSE SÜRÜM YÜKSELTİMİ
       1-Terminali aç
       2-yum install devtoolset-10 komutu ile gdb 10 kurulumu gerçekleşecektir.
a)Gerekli paketlerin indirimi
       1-yum install devtoolset-10-toolchain 
       2-yum list available devtoolset-10-\        //Tüm paketleri indirir
       3-yum install devtoolset-10-gdb-gdbserver devtoolset-10-gdb-doc
  b) Debug Bilgilerini Yükleme
        1-debuginfo-install devtoolset-10-dwz
   c)Sistemin mevcut gcc’ni güncellemek için
     scl enable devtoolset-10 bash

Not: Komuttaki 10 rakamını hangi sürümde istediğiniz ana sürüm numarasıyla değiştirmek mi istiyorsunuz? Bu, en son sürüme yükseltme. Örneğin, 10, 10.1 yerine 10.2.0'a yükseltilir.

    C)PATH’a gcc yükleme
        2 seçenek var. 
        1- yum groupinstall "Development Tools"
                             Veya
         2- yum grouplist



    D) Centos 7’ye Eclipse C/C++ Yükleme
         
1-
![image](https://user-images.githubusercontent.com/99322473/191609623-ad6b1f40-d762-43ce-97a8-ad5074f71fcc.png)

![image](https://user-images.githubusercontent.com/99322473/191609648-4c9738ac-8242-41bf-b827-c7c01c5552e9.png)

E) Eclipse C/C++ C++17 update
1-Önce terminalden gcc, g++ ve as nerde olduğu, hangi dosyalarda yer aldığı bulunmalı.
which gcc 
which g++
which as
….usr/bin/gcc gibi bir çıktılar alınmalı

2-Eclipse  Properties  C/C++ Build  Settings  Tool Settings
1-GCC C++ COMPİLER  Command  Terminalde which g++ ile alınan çıktı

 ![image](https://user-images.githubusercontent.com/99322473/191609739-6fe62787-1649-4574-9d6e-10c00b4c904d.png)

2-GCC C++ COMPİLER  Dialect  Language Standart  ISO C++17 (-std=c++17)

![image](https://user-images.githubusercontent.com/99322473/191609798-4a1907bc-d2a6-4195-9a81-73092e2754ca.png)

Language Standart’a tıklanarak yükseltilmek istenen sürüme yükseltilir. Veya hemen altta yer alan   Other dialect flags kutucuğuna dil standardı std cinsinden yazılmalı
4- GCC C COMPİLER  Command  Terminalde which gcc ile alınan çıktı
![image](https://user-images.githubusercontent.com/99322473/191609875-eff7224b-bf87-4d63-9cf4-896c296ac9da.png)

5- GCC C++ LİNKER  Command  Terminalde which g++ ile alınan çıktı
![image](https://user-images.githubusercontent.com/99322473/191609912-7e20c608-8bf6-458b-a29f-ea722ee832f6.png)

6- GCC ASSEMBLER Command  Terminalde which as ile alınan çıktı
![image](https://user-images.githubusercontent.com/99322473/191609956-1eda21a7-5190-4a52-8971-ee99a5120aa2.png)

Apply and Close

7- Eclipse  Properties  C/C++ Build  Settings  Tool Settings  C/C++ General Code Analysis Preprocessor Include Paths, Macros etc. Providers  CTD GCC Built-in Compiler Settings  Commands to get compiler specs  ${COMMAND} ${FLAGS} -E -P -v -dD --std=c++17 "${INPUTS}"

![image](https://user-images.githubusercontent.com/99322473/191609998-a7590ddf-4e4d-4330-aa13-4e3b5d42b0dc.png)

Apply and Close
8- Project  C/C++ Index  Rebuild
9-Debug
Not:Eğer Debug edilmezse ve Binary Not Found uyarısı alınırsa;
Eclipse  PropertiesRun/Debug SettingsLaunch configurations for “Proje ismi”  kısım boşsa
NewEdit Configuration C/C++ Application  Debug/Projenizin ismiApplyOK

CentOS çevrimdışı yükleme / gcc-c + +, make, nginx

1-Tar kaynak paketini kullanarak uygulamaları kurarken derleme yapmak gerekir, bu nedenle GCC ve G++ ortamına bağlıdır. Önce bunların mevcut olup olmadığını kontrol edin:

![image](https://user-images.githubusercontent.com/99322473/191610074-baf77a9f-51a4-4e37-ada0-0f3f5adf834c.png)

RPM çalışması gerekir
![image](https://user-images.githubusercontent.com/99322473/191610111-c810b0bf-97ce-4b5f-bd71-9c024d7bdfd5.png)

Gcc-c++ yükleyin
![image](https://user-images.githubusercontent.com/99322473/191610146-1c4d9771-4cca-4547-95d7-55195b128055.png)

Ardından RPM'yi tek tek kurun. İlk önce işletim sistemi türünü ve sürümünü kontrol edin

Yukarıdaki sürüm bilgilerine göre kendi bilgisayarınızda internet ile https://pkgs.org/   ilgili gcc-c + + RPM paketini indirin. Birçok pakete bağlı olduğunu görebilirsiniz . Bu bağımlı paketler için endişelenmeyin. Önce gcc-c + + – 8.3.1-5.1.el8.x86_ 64.rpm paketini sunucuya indirin ve buradan indirin: Yüklemeden önce sunucunun depolama dizinini planlayın:

![image](https://user-images.githubusercontent.com/99322473/191610183-1f33d860-947a-4091-bdde-4ed27543373e.png)

![image](https://user-images.githubusercontent.com/99322473/191610204-db323789-b7e7-4fdc-8956-84ecc15df323.png)

![image](https://user-images.githubusercontent.com/99322473/191610218-86256c99-065c-4f53-a135-895031b29664.png)

![image](https://user-images.githubusercontent.com/99322473/191610226-3eb1702a-7747-48a8-9400-9a3139649048.png)

Yüklemeden sonra kurulum için rpm kullanın
![image](https://user-images.githubusercontent.com/99322473/191610260-e8721ec5-69b7-4158-98ff-500ef3a0bdb7.png)

Daha önce bu bağımlılıkları önemsemedik çünkü hepsine ihtiyaç yok, bu yüzden sistemin ihtiyacımız olan paketleri algılamasına izin vermeye çalışıyoruz ve ardından istemlere göre karşılık gelen paketleri buluyoruz.
![image](https://user-images.githubusercontent.com/99322473/191610308-59e9de5f-0b1d-4eef-b53a-f2faaa10620c.png)

Aynı şekilde indirmek ve yüklemek için tıklayın. Yalnızca tüm bağımlılıklar yüklendiğinde ana paket başarıyla yüklenebilir. Bazı paketlerin derin bağımlılıkları olduğundan, paketleri bulma süreci daha zahmetlidir. Toplam 9 paket dahil:
![image](https://user-images.githubusercontent.com/99322473/191610348-d50ef018-e566-4d2e-abba-a44556f3abb1.png)

Hiyerarşik bağımlılıklar aşağıdaki gibidir:
![image](https://user-images.githubusercontent.com/99322473/191610382-a6b01489-bf1a-4c89-a532-270746bd2de9.png)

Ayrıca;
RPM'yi tek tek kurabilir veya tüm paketleri bulup birlikte kurabilirsiniz (gcc-c + + ile ilgili RPM paketleri Baidu ağ diskine yüklenmiştir — >  https://developpaper.com/go.php?go=aHR0cHM6Ly9wYW4uYmFpZHUuY29tL3MvMWhtWGpENXRHbWVuTjB2MUpuZXFaSEE=
Çıkarma kodu: 933g (uygun sürüme sahip olanlar için):

![image](https://user-images.githubusercontent.com/99322473/191610414-5b755333-3dce-43ee-86a0-487eb9211395.png)

Aşağıdakilerin başarıyla yüklenip yüklenmediğini kontrol edin
![image](https://user-images.githubusercontent.com/99322473/191610447-5e7041dd-386d-424b-b16e-fd10bf00ffda.png)

Install make
![image](https://user-images.githubusercontent.com/99322473/191610477-bf6f9555-c11c-4ab7-9aa3-a92bd43f3bb9.png)

Make paketini saklamak için baseenv altında bir make yolu oluşturun. 
![image](https://user-images.githubusercontent.com/99322473/191610503-88784c37-57ef-4005-9f7a-bb11bcf70de4.png)

Installing nginx
Ortam yüklendikten sonra, bir nginx yüklemek için tar paketini kullanın. Açtırma ve kurulum için tar paketini doğrudan / usr / local'e aktarın:
![image](https://user-images.githubusercontent.com/99322473/191610568-81c565f5-8c15-4755-aa69-5056eaa30e79.png)

Bu adıma koşun ve geçemeyeceğini bulun:
![image](https://user-images.githubusercontent.com/99322473/191610608-a669798c-6901-4af4-81f7-7f4a1c901435.png)

Nginx'in kendisi PCRE ve zlib'e bağlı olduğundan, önce bunları kurun:

[root@localhost make]# make -v
GNU Make 4.2.1
Is x86_ 64 RedHat Linux GNU compilation
Copyright (C) 1988-2016 Free Software Foundation, Inc.
License: GPLv3 +: GNU General Public License version 3 or later< http://gnu.org/licenses/gpl.html >。
This software is free software: you are free to modify and redistribute it.
There is no other guarantee to the extent permitted by law.

Installing nginx
After the environment is installed, use the tar package to install an nginx. Directly transfer the tar package to / usr / local for decompression and installation:

#Unzip the package
tar -zxvf  nginx-1.20.0.tar.gz
#Switch to / usr / local / nginx-1.20.0 to compile and install
./configure


Run to this step and find that it can’t pass

./configure: error: the HTTP rewrite module requires the PCRE library.
You can either disable the module by using --without-http_rewrite_module
option, or install the PCRE library into the system, or build the PCRE library
statically from the source with nginx by using --with-pcre=<path> option.

Because nginx itself depends on PCRE and zlib, install them first:
Install PCRE
•	Obtain the PCRE compilation and installation package, and http://www.pcre.org/ You can get the latest version on
•	Unzip the pcre-xx.tar.gz package.
•	Enter the decompression directory and execute. / configure.
•	make & make install
  
Install zlib
•	Get the zlib compilation and installation package. In the http://www.zlib.net/ You can get the latest version on.
•	Unzip the openssl-xx.tar.gz package.
•	Enter the decompression directory and execute. / configure.
•	make & make install
  
  Kurulumdan sonra nginx'i yükleyebilirsiniz:
  
  ![image](https://user-images.githubusercontent.com/99322473/191611036-4fcd9742-2840-49eb-9a2f-562af1dff6be.png)


