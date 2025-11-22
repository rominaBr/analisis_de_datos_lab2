# Análisis de Datos con Power BI - Mexico Toy Sales

## Descripción del Proyecto

Este repositorio contiene un informe interactivo (Dashboard) desarrollado en Microsoft Power BI para el análisis de ventas de una cadena de jugueterías en México. El proyecto abarca el ciclo completo de Business Intelligence: desde la ingesta y limpieza de datos (ETL) hasta el modelado en esquema de estrella y la visualización de KPIs clave.
El objetivo es permitir la exploración de datos históricos (2017-2018) para identificar patrones de venta estacionales, rendimiento por producto y distribución geográfica de las ganancias.

- Dataset Original: [Mexico Toy Sales](https://www.kaggle.com/datasets/mysarahmadbhat/toy-sales)

## Proceso de desarrollo

El desarrollo se estructuró en las siguientes fases:

1. Extracción y Transformación (Power Query):

   - Conexión a archivos planos (products.csv, sales.csv, inventory.csv, stores.csv).
   - Normalización de Datos: Se detectó redundancia en la tabla stores. Se aplicó un proceso de normalización extrayendo dimensiones geográficas (Cities y Locations) para optimizar el modelo.
   - Limpieza: Eliminación de duplicados, estandarización de textos y creación de claves subrogadas (Index Keys) para las relaciones.
   - Enriquecimiento Geográfico: Se incorporó una tabla externa con Latitud y Longitud exactas (generadas mediante IA) para corregir la geolocalización de ciudades homónimas en los mapas, integrándola mediante combinación de consultas (Merge).

2. Modelado de Datos:

   - Diseño de un Modelo Estrella (Star Schema).
   - Creación de una tabla calendario (dCalendar) con DAX para inteligencia de tiempo.
   - Relaciones optimizadas (1 a muchos) entre tablas de hechos y dimensiones.

3. Cálculos DAX:
   - Creación de una tabla dedicada a medidas.
   - Cálculo de KPIs: Ventas Totales, Promedio de Ventas, Total de Transacciones y Margen de Ganancia.
   - Lógica de tiempo para análisis por día de la semana.

## Guía de Uso

Para interactuar con el reporte:

1.  Cloná este repositorio o descargá el archivo .pbix.
2.  Aseguráte de tener instalado Power BI Desktop.
3.  Abrí el archivo Mexico_Toy_Sales_Report.pbix.

## Autor

- Romina M. Brutti
