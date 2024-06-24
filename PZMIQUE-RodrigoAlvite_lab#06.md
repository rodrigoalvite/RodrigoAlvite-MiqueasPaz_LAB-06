## PAZ MIQUEAS
# Actividad: Trabajando con Permisos en Linux

## Objetivo

Esta actividad tiene como objetivo que los estudiantes comprendan y practiquen la gestión de permisos en Linux, utilizando los comandos `chmod`, `chown` y `ls`.

## Instrucciones

### 1. Preparación

1. Abrí una terminal en tu distribución de Linux.
2. Crea un directorio llamado `actividad_permisos` y accede a él.

```sh
mkdir actividad_permisos
cd actividad_permisos
```
### 2. Creación de Archivos y Directorios
Dentro del directorio actividad_permisos, crea los siguientes archivos y un subdirectorio:
```sh
touch archivoA.txt archivoB.txt archivoC.txt
mkdir subdirectorio
```
### 3. Exploración de Permisos
Usa el comando ls -l para ver los permisos actuales de los archivos y directorios creados.
```sh
ls -l
```
2. Anota los permisos actuales de cada archivo y directorio en la siguiente tabla:

| **Nombre**      | **Permisos Actuales** |
|-----------------|-----------------|
| archivoA.txt	  | -rw-r---- 1     |
| archivoB.txt    | -rw-r--r--1     |
| archivoC.txt    | -rw-r--r--1     |
| subdirectorio   | drwxr-xr-x 2    |

### 4. Modificación de Permisos
Cambia los permisos de archivoA.txt para que el usuario tenga permisos de lectura y escritura, el grupo solo lectura y otros no tengan permisos.

    chmod 640 archivoA.txt
°Usuario: rw- (lectura y escritura)
°Grupo: r-- (Solo lectura)
°Otros: --- (nada)

Cambia los permisos de archivoC.txt para que el usuario tenga todos los permisos, el grupo solo lectura y otros solo ejecución.

    chmod 745 archivoC.txt
°Usuario: rwx (Todos los permisos)
°Grupo: r-- (solo lectura)
°Otros: --x (solo ejecución)

Cambia los permisos del subdirectorio para que el usuario tenga todos los permisos, el grupo y otros solo tengan permisos de lectura y ejecución.

    chmod 755 subdirectorio/
°Usuario: rwx (Todos los permisos)
°Grupo: r-x (Lectura y ejecución)
°Otros: (Lectura y ejecución)

### 5. Verificación de Cambios

ls -l

Anota los nuevos permisos de cada archivo y directorio en la siguiente tabla:

| **Nombre**      | **Permisos Actuales** |
|-----------------|-----------------|
| archivoA.txt	  | -rw-r----- 1    |
| archivoB.txt    | -rw-r--r-- 1    |
| archivoC.txt    | -rwxr--r-x 1    |
| subdirectorio   |  drwxr-xr-x 2   |

### 6. Cambio de Propietarios
1. Cambia el propietario de archivoA.txt a otro usuario (reemplaza otro_usuario con el nombre de un usuario existente en el sistema o crealo).

chown user01 archivoA.txt
ls -l archivoA.txt =
    -rw-r--r-- 1 user01 root 0 jun 10 15:23 archivoA.txt

3. Cambia el grupo de archivoB.txt a otro grupo (reemplaza otro_grupo con el nombre de un grupo existente en el sistema o crealo).
ls -l archivoB.txt =
    -rw-r--r-- 1 root archivos 0 jun 10 15:23 archivoB.txt

5. Cambia el propietario y grupo de archivoC.txt a otro_usuario y otro_grupo.
ls -l archivoC.txt =
    -rw-r--r-- 1 user02 archivos2 0 jun 10 15:23 archivoC.txt

### 7. Verificación de Cambios de Propietarios
1. Usa el comando ls -l para verificar los cambios en los propietarios y grupos.
2. Anota los nuevos propietarios y grupos de cada archivo en la siguiente tabla:

| **Nombre**      | **Nuevo propietario** | **Nuevo grupo**|
|-----------------|-----------------|-----------------------|
| archivoA.txt	  |    user01       |      root             |
| archivoB.txt    |     root        |     archivos          |
| archivoC.txt    |    user02       |    archivos2          |
| subdirectorio   |     root        |      root             |

### 8. Reflexión
¿Qué diferencias observaste en el comportamiento de los archivos y directorios al cambiar sus permisos y propietarios?
    Al cambiar los permisos y propietarios en Linux, los archivos y directorios tienen diferentes comportamientos. Los permisos controlan quién puede acceder, modificar o ejecutar un archivo, mientras que los propietarios determinan quién tiene control sobre ellos.
¿Por qué es importante gestionar correctamente los permisos en un sistema Linux?
    Es importante gestionar correctamente los permisos en Linux por razones de seguridad, privacidad y controles de acceso. Los permisos adecuados protegen los archivos sensibles, garantizan la privacidad de los datos y permiten establecer políticas de acceso específicas para usuarios y grupos. Esto contribuye a una organización segura y eficiente del sistema.
