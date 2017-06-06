# Magento-Docker

Configura-o-magento-docker.

Configuração mysql Magento Docker (docker toolbox)

apt-get update

apt-get install nano

#instalação de repositorios basicos

echo " ## Arquivo
Atualizações de Segurança
Security updates

deb http://security.debian.org/ jessie/updates main contrib non-free deb-src http://security.debian.org/ jessie/updates main contrib non-free
Espelho Debian
Base de dados do repositório
Base repository

deb http://ftp.br.debian.org/debian jessie main contrib non-free deb-src http://ftp.br.debian.org/debian jessie main contrib non-free
Atualizações estáveis
Stable updates

deb http://ftp.br.debian.org/debian jessie-updates main contrib non-free deb-src http://ftp.br.debian.org/debian jessie-updates main contrib non-free
backports estáveis
Stable backports

deb http://ftp.debian.org/debian jessie-backports main contrib non-free deb-src http://ftp.debian.org/debian jessie-backports main contrib non-free
Atualizações Propostas

deb http://ftp.debian.org/debian jessie-proposed-updates main contrib non-free " >/etc/apt/sources.list

apt-get update

#Instalação mysql

apt-get install mysql-server touch /var/run/mysqld/mysqld.sock chown -R mysql /var/run/mysqld chmod +x /var/run/mysqld/mysqld.sock /etc/init.d/mysql restart

apt-get install mariadb-server mariadb mysql_secure_installation mysql_install_db

#Configuração do banco de dados

mysql -u root -p create database magentodb; show databases; grant all privileges on magentodb.*to usuario@localhost identified by '123456'; flush privileges; Exit

#ficara assim

Banco de dados: magentodb usuario: root senha 123456 localhost:127.0.0.1
