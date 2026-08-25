# Análisis de Churn de Clientes — Telecomunicaciones

Proyecto de análisis de datos y modelo predictivo para identificar qué clientes de una compañía de telecomunicaciones tienen mayor riesgo de darse de baja (*churn*), y qué factores lo explican.

![Churn por tipo de contrato](img/02_churn_por_contrato.png)

## Objetivo

Responder tres preguntas de negocio:
1. ¿Cuál es la tasa de churn y qué variables se le asocian?
2. ¿Esa asociación es estadísticamente significativa?
3. ¿Se puede priorizar a qué clientes dirigir una campaña de retención?

## Resumen de hallazgos

- Tasa de churn global: **26,6%**.
- El **tipo de contrato** es la variable más determinante: los clientes con contrato mes a mes concentran la gran mayoría de las bajas frente a los contratos de 1-2 años (test Chi-cuadrado, p < 0,001).
- Los clientes con **fibra óptica** se dan de baja al doble de ritmo que los de DSL, pese a ser el servicio más caro.
- Un modelo de **regresión logística** alcanza un ROC-AUC de 0,84 y permite priorizar campañas de retención sobre el 20-25% de clientes de mayor riesgo en lugar de campañas masivas.
- La **antigüedad del cliente** (`tenure`) es el factor individual que más protege frente al churn.

El análisis completo, con el razonamiento paso a paso y las recomendaciones de negocio, está en [`Analisis_Churn_Telecomunicaciones.ipynb`](Analisis_Churn_Telecomunicaciones.ipynb).

## Estructura del repositorio

```
├── Analisis_Churn_Telecomunicaciones.ipynb   # Notebook principal (EDA + estadística + modelo)
├── data/
│   └── Telco-Customer-Churn.csv              # Dataset (IBM Telco Customer Churn, 7.043 clientes)
├── img/                                       # Gráficos exportados
└── requirements.txt
```

## Cómo ejecutarlo

```bash
pip install -r requirements.txt
jupyter notebook Analisis_Churn_Telecomunicaciones.ipynb
```

## Herramientas

Python · pandas · scipy (inferencia estadística) · scikit-learn (regresión logística) · matplotlib / seaborn

## Fuente de datos

[IBM Telco Customer Churn Dataset](https://github.com/IBM/telco-customer-churn-on-icp4d)

---
*Diana Rodríguez Cámara — Graduada en Matemáticas, Universidad de Málaga*
