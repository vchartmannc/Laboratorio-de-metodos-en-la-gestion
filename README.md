"""
REPOSITORIO OFICIAL: MÉTODOS CUANTITATIVOS APLICADOS A LA GESTIÓN
----------------------------------------------------------------
Institución: Universidad de Buenos Aires (UBA)
Carrera: Tecnicatura Universitaria en Administración y Gestión Pública
Finalidad: Centralización de actividades prácticas, laboratorios y exámenes.

Descripción:
Este script actúa como el núcleo organizativo del repositorio. Su función es 
gestionar de manera sistemática la carga de datasets, la ejecución de 
modelos de optimización (PuLP) y el análisis de datos (Pandas).
"""

import pandas as pd
import datetime

class RepositorioGestion:
    def __init__(self, alumno):
        self.alumno = alumno
        self.fecha_inicio = datetime.date.today()
        self.modulos = []
        self.examenes = {}

    def registrar_actividad(self, unidad, tema, descripcion):
        """
        Registra formalmente una nueva tarea o laboratorio al repositorio.
        """
        tarea = {
            "Unidad": unidad,
            "Tema": tema,
            "Descripción": descripcion,
            "Estado": "Completado"
        }
        self.modulos.append(tarea)
        print(f"✅ Tarea añadida: {tema} (Unidad {unidad})")

    def preparar_examen(self, instancia, temas_clave):
        """
        Prepara la estructura lógica para las evaluaciones parciales o finales.
        """
        self.examenes[instancia] = {
            "Temas": temas_clave,
            "Herramientas": ["Pandas", "Matplotlib", "PuLP"],
            "Fecha_Preparacion": datetime.date.today()
        }
        print(f"⚠️ Alerta: Estructura para '{instancia}' generada correctamente.")

    def mostrar_progreso(self):
        """
        Genera un DataFrame para visualizar el avance académico en el repositorio.
        """
        print(f"\n--- RESUMEN ACADÉMICO DE {self.alumno.upper()} ---")
        if not self.modulos:
            return "El repositorio se encuentra vacío."
        return pd.DataFrame(self.modulos)

repo = RepositorioGestion("Nombre del Alumno")

repo.registrar_actividad(1, "Programación Lineal", "Uso de PuLP para maximización de beneficios.")
repo.registrar_actividad(1, "Análisis de Sensibilidad", "Interpretación de precios sombra y rangos.")
repo.registrar_actividad(2, "Análisis de Datos", "Carga y limpieza de Datasets (YPF, Ventas) con Pandas.")
repo.registrar_actividad(2, "Visualización", "Generación de histogramas y gráficos de barras dinámicos.")

repo.preparar_examen("Primer Parcial", ["Optimización Lineal", "Modelado de Problemas"])
repo.preparar_examen("Examen Integrador", ["Análisis Exhaustivo de Datos", "Conclusiones de Gestión"])

df_progreso = repo.mostrar_progreso()
print(df_progreso)

print("\n--- NOTA FINAL ---")
print("Este repositorio se mantendrá actualizado como evidencia de aprendizaje")
print("y material de consulta para las evaluaciones cuantitativas de la materia.")
