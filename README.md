# Optimizaci-n-Din-mica-de-Microrredes-H-bridas-y-Log-stica-de-AGVs

En las plantas de manufactura moderna, el aumento de la automatización introduce un desafío logístico crítico: coordinar decenas de Vehículos de Guía Automática (AGVs) sin que se bloqueen en pasillos estrechos, al mismo tiempo que se optimiza el consumo de una microrred eléctrica industrial. Los métodos clásicos sufren de cuellos de botella exponenciales ($N!$) al recalcular trayectorias y restricciones en tiempo real.Este proyecto propone un enfoque híbrido cuántico-clásico utilizando el algoritmo QAOA (Quantum Approximate Optimization Algorithm) adaptado específicamente para ejecutarse en el motor de iones atrapados IonQ Aria 1. Gracias a su conectividad completa (all-to-all), el sistema modela los conflictos de tráfico e interacciones de ruta de manera nativa, logrando explorar el espacio combinatorio de rutas de forma exponencialmente más eficiente y reduciendo los tiempos muertos y costos energéticos de la planta.

Para llevar un problema físico del mundo real al procesador cuántico, seguimos una metodología de tres pasos:

1- Mapeo a Variables Binarias: Cada decisión logística del sistema se representa mediante cúbits. Por ejemplo, el estado del cúbit $q_0$ define si el AGV 1 toma una ruta alternativa o la principal, y el cúbit $q_1$ hace lo propio para el AGV 2.

2- Construcción de la Función de Costo (Hamiltoniano de Ising): El problema industrial se traduce en una función matemática de penalización compuesta por:
  - Términos Lineales ($Z_i$): Representan el costo operativo, distancia o consumo base de que cada AGV elija una ruta específica.
  - Términos de Interacción ($Z_0 Z_1$): Actúan como un "semáforo inteligente". Si ambos AGVs intentan ocupar el mismo carril o cuello de botella simultáneamente, se aplica un coeficiente de penalización alto en la función de costo.

3- Explotación del Hardware (Aria 1): En arquitecturas basadas en qubits superconductores tradicionales, las interacciones entre cúbits lejanos requieren compuertas $SWAP$ adicionales que acumulan ruido rápidamente. Al correr sobre IonQ Aria 1, las compuertas de entrelazamiento global ($ZZ$) se ejecutan de forma directa y limpia gracias a su conectividad all-to-all, permitiendo mantener la fidelidad en problemas con múltiples restricciones de tráfico.

Este proyecto reduce los tiempos de inactividad por tráfico dentro de la nave industrial y además reduce los desgastes de la flota de maquinaria y los picos de demanda energética de la red.

Link circuito en Qollab: https://qollab.xyz/u/tincho/optimizaci-n-din-mica-de-micro#run
Link video: 
