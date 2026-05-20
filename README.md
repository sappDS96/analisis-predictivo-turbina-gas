# Análisis predictivo y optimización de turbina de gas

Proyecto de Data Science aplicado a operación industrial para analizar el rendimiento energético y las emisiones de una turbina de gas. El trabajo combina análisis exploratorio, modelado predictivo y segmentación estadística para identificar condiciones históricas de operación con mayor generación energética y menores emisiones.

## Objetivo

Evaluar la relación entre variables ambientales y operativas de una turbina de gas con tres variables objetivo:

- `TEY`: energía generada por la turbina.
- `CO`: emisiones de monóxido de carbono.
- `NOX`: emisiones de óxidos de nitrógeno.

El proyecto compara modelos de regresión individuales frente a un enfoque multisalida y utiliza un criterio basado en percentiles para identificar condiciones operativas favorables.

## Enfoque técnico

- Limpieza y exploración de datos con Python y Pandas.
- Análisis de relaciones entre variables operativas, rendimiento y emisiones.
- Entrenamiento de modelos de regresión para `TEY`, `CO` y `NOX`.
- Comparación entre regresión por separado y modelado multisalida.
- Evaluación con `MAE`, `RMSE` y `R2`.
- Identificación de condiciones óptimas mediante percentiles:
  - `TEY` en el cuartil superior.
  - `CO` en el cuartil inferior.
  - `NOX` en el cuartil inferior.
- Preparación de resultados para visualización en Power BI.

## Estructura recomendada del repositorio

```text
.
├── Optimización de emisiones y rendimiento en turbinas de gas.ipynb
├── gt_full.csv
├── gt_full_modificado.csv
├── predicciones_xgb_final.csv
├── resultados_modelos.csv
├── resultados_multisalida.csv
├── resultados_multisalida_global.csv
├── feature_importance.csv
├── comparacion_condiciones_optimas_turbina.xlsx
├── Ciclo-Brayton.jpg
├── requirements.txt
└── README.md
```

## Archivos principales

- `Optimización de emisiones y rendimiento en turbinas de gas.ipynb`: notebook principal del análisis.
- `gt_full.csv`: dataset base de operación de la turbina.
- `gt_full_modificado.csv`: dataset preparado para análisis y visualización.
- `resultados_modelos.csv`: métricas de modelos entrenados por objetivo.
- `resultados_multisalida.csv` y `resultados_multisalida_global.csv`: resultados del enfoque multisalida.
- `predicciones_xgb_final.csv`: predicciones finales del modelo seleccionado.
- `feature_importance.csv`: importancia de variables para interpretación del modelo.
- `comparacion_condiciones_optimas_turbina.xlsx`: comparación entre condiciones globales y condiciones óptimas.

## Herramientas utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- Power BI

## Principales conclusiones

- Variables como `TIT`, `CDP` y `GTEP` muestran una relación relevante con la generación energética.
- `CO` y `NOX` presentan comportamientos distintos, por lo que deben analizarse como objetivos ambientales separados.
- El enfoque multisalida con XGBoost permitió modelar simultáneamente energía y emisiones.
- El análisis de percentiles permitió aislar condiciones históricas con mejor equilibrio entre rendimiento energético y emisiones.

## Nota

Este proyecto no implementa control automático en tiempo real. El objetivo es construir una metodología analítica reproducible para apoyar el entendimiento operativo, el benchmarking histórico y la toma de decisiones en sistemas industriales.
