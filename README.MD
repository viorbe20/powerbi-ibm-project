# Data Analytics Capstone Project

## Contenido
[1. Introducción](#1-introducción)
[2. Objetivo](#2-objetivo)
[3. Actividades](#3-actividades)
[4. Los datos: Overview Marketing Data](#4-los-datos-overview-marketing-data)

## 1. Introducción
El presente documento forma parte del proyecto final del curso Power BI - IBM SkillsBuild. En el se reflejan las pautas de dicho proyecto y se adjuntan imágenes que demuestran la realización de la actividad.

## 2. Objetivo
DH Marketing Consultants te ha contratado como analista de datos para explorar y analizar una serie de datos del departamento de marketing. El director de marketing necesita generar valor a través de estos datos y te pide hacer un análisis. El análisis debe basarse en los diferentes factores que podemos medir del dataset. 

La empresa requiere que como mínimo organices los datos por fechas, campañas, productos.

## 3. Actividades
• Limpieza de datos.
• Transformación de datos.
• Visualizaciones de datos.

## 4. Los datos: Overview Marketing Data
Los datos proporcionados corresponden a una fuente de datos abiertos, la cual nos proporciona data relacionada con 5 campañas de marketing que realizo una empresa, las plataformas que se utilizaron y la cantidad de veces que se hicieron ventas a través de estas plataformas entre otros datos muy interesantes a los cuales se les puede extraer una gran cantidad de información

## 5. Fuente del conjunto de datos
Link de la fuente de datos: [Datos](https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign?resource=download)

## 6. Proyecto

### Actividad 1: carga de datos

- 1.1. Conecta los datos csv con power BI.

![CSV connection](./img/1.1.png)

- 1.2. Revisa los datos en el transformador de datos de Power Query y analiza el contenido de las columnas.

![Data transformation](./img/1.2.png)

Análisis por columnas:

1. **Columna ID**
- Tipo de dato: Numérico (Entero).
- Representa: Identificador único para cada cliente.
- Comentarios: No hay duplicados.

2. **Columna Year_Birth**
- Tipo de dato: Numérico (Año).
- Representa: Año de nacimiento del cliente.
- Comentarios: Podrías calcular la edad como una nueva columna para facilitar análisis demográficos. Ejemplo: 2024 - Year_Birth. Si hay valores extremos (por ejemplo, años irreales como 1900), se deben limpiar o imputar.

- 1.3.  Analiza y modifica los tipos de datos de las columnas

### Actividad 2: Limpieza de datos
- Busca errores en los datos: valores atípicos, datos en blanco o errores de escritura, verifica por ejemplo que las fechas son coherentes y no hay clientes con más de cien años.

**2.1. Columna Year_Birth**
Los valores se distribuyen entre 1976 y 1993, por lo que aparentemente parecen correctos. 

### Actividad 3: Transformación de datos
- Renombra las columnas y organízalas de la mejor manera posible. Proporciona la razón por la que realizaste los cambios en estas columnas para el análisis de datos.
- Analiza y modifica los tipos de datos de las columnas.
- Lee el archivo csv de datos y conviértelo en un data set valido.
- Revisar los datos en el transformador de datos de Power Query y analizar el contenido de las columnas.
- Busca errores o valores atípicos en los datos.
- Edita las columnas en caso de ser necesario.

**3.1. Creación de nuevas columnas**
A partir de los años de la columna *Year_Birth* se calcula la edad y se guarda en  una nueva columna  *Age*.

```DAX  
Date.Year(DateTime.LocalNow()) - [Year_Birth]
```




### Actividad 4: Modelado de datos
- 4.1. Cree un modelo de datos cuya estructura se base en una única tabla de hechos. La tabla de hechos debe estar en el centro del modelo conectada a las tablas de dimensiones en forma de estrella.

### Actividad 5: Visualizaciones
- 5.1. Crear las visualizaciones necesarias para la comprensión de los datos. El cuadro de mandos debe contener al menos 3 hojas, deben estar correctamente enlazadas para el correcto funcionamiento de filtros y botones.
Estructura mínima:
    1. Una hoja de la visión general de los datos.
    2. Una hoja de los datos analizando las campañas.
    3. Una hoja de los datos analizando los productos.
    4. Una hoja cero oculta donde haremos anotaciones.
- 5.2. Crea un modelo estrella con tus tablas.
- 5.3. Crea una descripción general de los datos
- 5.4. Crea visualizaciones de los datos de las 5 campañas.
- 5.5. Crea visualizaciones con los datos de estado civil, hijos, etc.
- 5.6. Crea visualizaciones de los datos de los tipos de productos
- 5.7. Crea visualizaciones de los datos de plataforma de compra