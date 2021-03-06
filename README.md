# BugTracker - Programación en Capas


## 1. Clonar Repositorio (Clone/Checkout)

**1.1. Ejecutar comando clone para descargar repositorio:** 
```sh
$ git clone https://github.com/utn-frc-pav1-3k5-2020/actividad_programacion_capas.git
```
**1.2. Ubicarse en la carpeta generada con el nombre del repositorio:**

```sh
$ cd actividad_programacion_capas
```

**1.3. Crear un nuevo branch (rama)**

Para crear una nueva rama (branch) y saltar a ella, en un solo paso, puedes utilizar el comando  `git checkout`  con la opción  `-b`, indicando el nombre del nuevo branch (reemplazando el nro de legajo) de la siguiente forma branch_{legajo}, para el legajo 12345:

```sh
$ git checkout -b branch_12345 
Switched to a new branch "12345"
```
Y para que se vea reflejada en GitHub:
```sh
$ git push --set-upstream origin branch_12345
```

## 2. Ejecutar Script Base de datos
**2.1. Iniciar la aplicación `Sql Server Management Studio`**

Solicitará ingresar los datos de la base de datos para generar una conexión, completar los datos y hacer click en **Connect**. Los datos del servidor del labsis son:

 - **Tipo Servidor:** Database Engine
 - **Nombre Servidor:** .\SQLEXPRESS
 - **Autenticación:** Windows Authentication.
 
 
 **2.2. Abrir archivo `BugTracker_Crear_BaseDatos.sql`**
 Ir a la opción `Archivo -> Abrir -> Archivo` (o combinación de teclas `Ctrl + O`) y buscar el archivo BugTracker_Crear_BaseDatos.sql en el disco local.
  

**2.5. Ejecutar Script** 
Para ejecutar el script hacer click sobre el botón `Ejecutar` (o usar la tecla `F5`)


## 3. Temas



### 3.1. Programación en 3 Capas 

- **Presentación (GUILayer):** Mediante la capa de presentación se separa la interacción del usuario respecto a la lógica de negocio.
- **Lógica (BusinessLayer):** La capa de negocio expone la lógica necesaria a la capa de presentación para que el usuario, a través de la interfaz, interactúe con las funcionalidades de la aplicación.
- **Acceso a datos (Data Access):**  La necesidad de vincular los datos guardados en una base de datos relacional, con los objetos de una aplicación orientada a objetos, determinó la aparición del concepto de persistencia de objetos. Siguiendo el estilo de desarrollo en tres capas, la persistencia queda recogida en su propia capa, separada de la lógica de negocio y de la interfaz de usuario.

- **Entidades (Entity):** Aunque aparentemente es una cuarta capa realmente no lo es. Se encarga de contener todos aquellos objetos (clases) que representan al negocio, y esta es la única que puede ser instanciada en las 3 capas anteriores, es decir, solo ella puede tener comunicación con el resto pero su función se limita a únicamente ser un puente de transporte de datos. Esta capa complementa a la Capa de Negocio

**![](https://lh5.googleusercontent.com/o76z7uQg0dRkDHxpMdMwBfyJOb6fftiCzMah3wk5X94-oiaYaROi1ohtM_mEuWXW_87Jo9Qp3aCJR213Y4jMcN6SlPXc2dlQYDBVPmfwkE0_wAJaAljLUjTecL49Jzli40jmfV1V)**

### 3.2. Patrón DAO

Dado lo anterior, el patrón DAO propone separar por completo la lógica de negocio de la lógica para acceder a los datos, de esta forma, el DAO proporcionará los métodos necesarios para insertar, actualizar, borrar y consultar la información; por otra parte, la capa de negocio solo se preocupa por lógica de negocio y utiliza el DAO para interactuar con la fuente de datos.

**![](https://jossjack.files.wordpress.com/2014/06/dao.jpg)**

### 3.3. Patrón Mapper

Patrón Mapper, que toma como argumento algún tipo de fuente de datos "en bruto" (por ejemplo, un ADO.NET DataReader o DataSet) y asigna los campos a propiedades en un objeto de negocio / dominio.

**![](https://martinfowler.com/eaaCatalog/databaseMapperSketch.gif)**

###  Paso a paso hacia programación en 3 Capas

## 4. Actividades
4.1. Desarrollar la capa de Lógica (BusinessLayer) de las siguientes entidades de negocio para obtener el listado de cada usando programación en 3 capas (usar como base lo ya desarrollado para la entidad Bug):
* Producto
* Criticidad
* Prioridad
* Usuario
* Estado

4.2. En `frmConsultarBug` modificar el método `LlenarCombos` para usar los desarrollado en el punto anterior para obtener los datos del punto anterior.

## 5. Versionar en GitHub los cambios locales (add / commit / push)

> A continuación vamos a crear el **commit** y subir los cambios al servidor GitHub.

5.1. **Status**. Verificamos los cambios pendientes de versionar.

```sh
$ git status
```

5.2. **Add**. Agregamos todos los archivos nuevos no versionados.

```sh
$ git add -A
```

5.3. **Commit**. Generamos un commit con todos los cambios y agregamos un comentario.

```sh
$ git commit -a -m "Comentario"
```

5.4. **Push**. Enviamos todos los commits locales a GitHub

```sh
$ git push
```

5.5. **Status**. Verificar que no quedaron cambios pendientes de versionar

```sh
$ git status
```
