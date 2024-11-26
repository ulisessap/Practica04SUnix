# Practica04SUnix

# Creacion de paquetes .deb
## Paquetes .deb:
Son los paquetes de software utilizados por Debian y sus derivados (como Ubuntu). Estos paquetes contienen programas, bibliotecas y otros archivos necesarios para instalar software en el sistema. Los archivos .deb incluyen metadatos que describen el paquete, scripts que se ejecutan en varias etapas de la instalación/desinstalación (como postinst y prerm), y los archivos binarios o de configuración que se instalarán.

## Páginas de manual (man):
Son los documentos que proporcionan información sobre comandos, programas, configuraciones, y otros aspectos del sistema. Estas páginas están organizadas por secciones y se pueden acceder a través del comando man seguido del nombre del comando o tema deseado. Cada paquete .deb puede incluir sus propias páginas de manual, que suelen instalarse en directorios como /usr/share/man/.

## Comandos previos de deb

Ahora ejecutamos los sieguientes comandos: 
nano mkbackup.sh:
Este archivo es un script que probablemente contiene comandos para realizar un respaldo del directorio home de un usuario específico.

![image](https://github.com/user-attachments/assets/c1319cff-749f-44b5-8a8c-2b46424993ad)

chmod +x mkbackup.sh:
Otorgamos permisos de ejecución al archivo mkbackup.sh, lo que permite que se pueda ejecutar como un programa o script.

mkdir -p deb/usr/bin:
Creamos el directorio deb/usr/bin, incluyendo cualquier directorio padre necesario. Este es el directorio donde se colocará el script mkbackup.sh en la estructura del paquete.

![image](https://github.com/user-attachments/assets/6aea4934-b90c-43cf-8a21-563473e543a7)

cp ./mkbackup.sh ./deb/usr/bin:
Copiamos el script mkbackup.sh al directorio deb/usr/bin, dentro de la estructura que representará el paquete .deb.

mkdir ./deb/DEBIAN:
Creamos el directorio DEBIAN dentro del directorio deb. Este directorio es crucial para un paquete .deb, ya que contendrá archivos de control como control y otros posibles scripts como postinst o prerm.

nano ./deb/DEBIAN/control:
Abrimos nano para crear o editar el archivo control dentro del directorio DEBIAN. Este archivo contiene metadatos sobre el paquete, como su nombre, versión, descripción, etc.

![image](https://github.com/user-attachments/assets/f9314d93-fb01-4a08-b858-922dc7fa2d41)


dpkg -b deb/:
Construye un archivo de paquete .deb a partir de los archivos y directorios dentro de deb/. Esto genera un archivo .deb en el mismo directorio.

dpkg -b deb/ mkbackup.deb:
Similar al comando anterior, pero esta vez especifica el nombre del archivo .deb que se generará, en este caso, mkbackup.deb.

sudo chown -R root:root deb/:
Cambia el propietario y grupo de todos los archivos y directorios dentro de deb/ a root. Esto es importante para asegurar que el paquete se instale con los permisos correctos.

![image](https://github.com/user-attachments/assets/c31baf90-852a-4845-a6e1-89875d266019)

## Comandos para man

mkdir -p deb/usr/share/man/man8: Creamos un directorio llamado man8 dentro de la ruta deb/usr/share/man/. La opción -p asegura que se creen todos los directorios intermedios necesarios si no existen.

sudo nano deb/usr/share/man/man8/mkbackup.8: Abrimos el editor de texto nano con permisos de superusuario (sudo) para editar o crear el archivo mkbackup.8 en el directorio deb/usr/share/man/man8/. Este archivo normalmente contendrá la página de manual para el comando mkbackup.

![image](https://github.com/user-attachments/assets/a92e61fb-4964-457f-ab95-3744ae642358)

![image](https://github.com/user-attachments/assets/e952b43a-11a8-4103-974c-9176157094ba)





