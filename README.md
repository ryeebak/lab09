# lab09
Данную лабораторную работу я буду выполнять на операционной системе Windows.
Для развертывания виртуальной машины я буду использовать сервисы:
1. Vagrant
2. Laravel Homestead
После установки Vagrant первым делом установим Laravel Homestead с помощью команды :

$ git clone https://github.com/laravel/homestead.git ~/Homestead

![изображение](https://github.com/ryeebak/lab09/assets/124439291/8b2008fc-dfad-40f8-a616-53d933dcb003)

Требуется сгенерировать публичный и приватный ssh ключи, сделаем это с помощью команды:

$ ssh-keygen -t rsa -C “ryeebak@gmail.com”

![изображение](https://github.com/ryeebak/lab09/assets/124439291/300abffb-4945-4326-96f0-9bcab34a6ea7)

Далее, переместив файлы с содержимым ssh ключей в папку, путь который указан в файле Homestead.yaml, запускаю виртуальную машину с помощью команды:

$ vagrant up

Сразу же после успешного запуска можно проверить статус виртуальной машины командой:

$ vagrant status

![image_2023-09-05_18-55-27](https://github.com/ryeebak/lab09/assets/124439291/19d3c0a6-20f2-49df-b761-2cf4f73361ca)

Войдем в виртуальную машину с помощью команды:

$ vagrant ssh

![изображение](https://github.com/ryeebak/lab09/assets/124439291/09b3990e-5f0d-426a-ad31-abe826c5e69d)

В файле Homestead.yaml в том числе указывается расположение файлов виртуальной машины:

folders:
    - map: C:\web
      to: /home/vagrant/code
sites:
    - map: homestead.test
      to: /home/vagrant/code/public

Добавим папку test с помощью интерфейса ВМ и обнаружим изменение на диске основной операционной системы по указанному пути C:\web:

![image_2023-09-05_19-16-00](https://github.com/ryeebak/lab09/assets/124439291/061542c7-5a83-4be4-b022-ff0bf26a0c58)

Тем самым, можно сделать вывод о работоспособности нашей виртуальной машины.
Для того, чтобы покинуть интерфейс виртуальной машины и выключить ее, используем:

vagrant@homestead:~/code$ exit
  
logout

4epe3@DESKTOP-OL49DUF MINGW64 ~/Homestead (main)

$ vagrant halt

==> homestead: Attempting graceful shutdown of VM...







