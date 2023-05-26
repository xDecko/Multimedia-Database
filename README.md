# MMDB
Multimedia Database 2019-I Project

## Descripción

El proyecto está dividido en dos partes, un cliente encargado del procesamiento de los datos y un encargado de almacenar los registros en MariaDB/MySQL.

El proyecto permite arrojar archivos multimedia a un área y que este sea pocesado y manejado adecuadamente, además, el usuario podrá almacenar dicho elemento en la base de datos junto con su metadata o características, las cuales nos ayudarán posteriormente a consultarle.

## Tecnologías

1. HTML5
2. CSS3
3. JS (ES6 OOP)
4. PHP
5. SHELL/BAT
6. SQL

## APIS HTML5

1. Drag & drop
2. FileReader
3. Audio
4. Video
5. Image
6. Canvas

## Configuración para el proyecto

Como el proyecto maneja archivos multimedia y peticiones de tipo CORS en entornos locales, existen ciertas configuraciones a tener en cuenta tanto en los archivos del servidor (my.conf, php.ini), como en las peticiones (en cuanto a las cabezeras tanto en el cliente como en el servidor). A continuación listaré la lista de acciones a tomar:

### 1. Configuraciones en httpd.conf


#### php.ini
```ini
	; máxima memoria de ejecución
	memory_limit=512M
	; Aceptar un valor máximo de 1GB para el envío por POST
	post_max_size=1024M
	; Maximum allowed size for uploaded files.
	; http://php.net/upload-max-filesize
	; opcional si posteriormente piensan adicionar inputs de tipo file 
	upload_max_filesize=1024M
```

#### my.cnf (en algunos casos my.ini)
```ini
	[mysqldump]
	quick
	max_allowed_packet = 128M
	
	# The MySQL server
	[mysqld]
	max_allowed_packet = 128M
	
	innodb_log_file_size = 256M
```


#### 1. Cliente
El cliente dispondrá de las siguientes capacidades:

1. **(20%)** El usuario podrá cargar archivos multimedia de tipo Imagen (png, jpeg, tiff, gif), Audio (mp3, ogg, mp4, wav, m4a), Video (webm, avi, mp4, wmv), Pdf, JS, PHP (Tanto JS como PHP deberán presentarse con colores highlight que los identifiquen como podrán encontrar [acá](https://highlightjs.org/)). Al procesar el archivo, el cliente previsualizará el contenido del archivo en pantalla para que el usuario pueda verlo.

2. **(20%)** El usuario podrá alojar dichos elementos en la base de datos para posteriormente realizar consultas con ellos, a continuación a lista de las consultas:
	1. El usuario podrá consultar todos los elementos de ese tipo alojados en la base de datos.
	2. El usuario podrá eliminar elementos multimedia de la base de datos. 

3. **(60%)** El usuario podrá hacer Queries de comparación con los archivos de tipo Imagen definiendo el valor de tolerancia a la diferencia, entonces el programa buscará en la base de datos las imagenes similares en contenido de color y las traerá como respuesta. Entre menor (__como ustedes__) sea la tolerancia, más certeros serán los resultados. 

#### 2. Server
Modifique su servidor para soportar los archivos multimedia que no esten ya soportados.

#### 3. SQL de base de datos (sin registros, sólo el esquema)



"# MMDB" 
