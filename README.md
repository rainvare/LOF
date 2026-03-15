# LOF — Learning Optimization Framework

> *Un agente pedagógico que aprende cómo pensás y enseña en consecuencia.*

LOF es un protocolo abierto para Claude que construye tu perfil cognitivo
observando cómo interactuás — y usa ese perfil para adaptar cómo te enseña
cuando querés aprender algo nuevo.

**No te pregunta cómo preferís aprender. Lo infiere.**

---

## El problema que resuelve

Los sistemas educativos, incluso los asistidos por IA, enseñan igual a todos.
Te dan la misma explicación, el mismo orden, los mismos ejemplos. Si esa forma
no es la tuya, tenés que adaptarte vos.

LOF invierte eso. En lugar de que el humano se adapte al sistema, el sistema
se adapta al humano — observando patrones reales en cómo pensás, no en lo que
decís que preferís.

---

## Cómo funciona

### El perfil cognitivo

LOF modela cinco dimensiones de cómo procesás información. Cada una es un
continuo entre dos polos:

| Dimensión | Polo − | Polo + |
|-----------|--------|--------|
| **Codificación** | Verbal | Visual |
| **Abstracción** | Concreto | Abstracto |
| **Procesamiento** | Secuencial | Holístico |
| **Estructura** | Lógico | Narrativo |
| **Validación** | Frecuente | Autónomo |

Cada dimensión tiene un valor entre −2 y +2, y un nivel de confianza
(baja / media / alta) que crece con la evidencia acumulada.

### Cómo se construye el perfil

El agente observa señales en cómo escribís y qué pedís:

- ¿Pedís ejemplos antes de entender el principio, o vas directo a la regla?
- ¿Necesitás cerrar cada paso antes de avanzar, o preferís el panorama completo?
- ¿Respondés mejor a historias y analogías, o a relaciones causales explícitas?
- ¿Buscás confirmación frecuente, o avanzás de forma autónoma?

El perfil se actualiza con cada interacción. Las señales fuertes mueven más
el valor; las contradictorias bajan la confianza en lugar de invertir el valor.

### Cómo se usa para enseñar

Cuando querés aprender algo, el agente diseña el plan instruccional basado en
tu perfil:

- Si sos holístico, empieza con el panorama completo
- Si sos concreto, arranca con un caso real antes del principio
- Si sos visual, usa metáforas espaciales y escenas imaginadas
- Si preferís validación frecuente, hace pausas y confirma comprensión
- Si sos autónomo, avanza sin interrumpir y deja que vos marques el ritmo

---

## Instalación

### Opción A — Claude Code (recomendada)

```bash
git clone https://github.com/tuusuario/lof.git
cd lof
claude .
```

Claude Code lee `CLAUDE.md` automáticamente. El agente LOF queda activo.
No hay dependencias. No hay instalación de paquetes.

#### En Termux (Android)

```bash
pkg install git
git clone https://github.com/tuusuario/lof.git
cd lof
claude .
```

### Opción B — Claude.ai (sin código)

1. Creá un nuevo **Proyecto** en Claude.ai
2. Andá a las instrucciones del proyecto
3. Copiá el contenido completo de `LOF_PROMPT.md`
4. Guardá

El perfil cognitivo vive en la memoria del proyecto y se actualiza
automáticamente con cada sesión.

---

## Uso

```
/lof [tema]       Iniciar sesión de aprendizaje sobre un tema
/lof perfil       Ver tu perfil cognitivo actual en lenguaje natural
/lof analizar     Analizar conversaciones históricas en conversations/
/lof reset        Resetear el perfil (pide confirmación)
```

O simplemente escribí: **"quiero aprender [tema]"**

### Análisis de conversaciones pasadas

1. Copiá el texto de conversaciones previas (Claude, ChatGPT, foros, etc.)
2. Guardalo como `.txt` o `.md` en la carpeta `conversations/`
3. Escribí `/lof analizar`

---

## Estructura del repositorio

```
lof/
├── README.md              → Este archivo
├── LOF_PROMPT.md          → Prompt completo para usar en Claude.ai
├── CLAUDE.md              → Instrucciones del agente para Claude Code
├── lof_profile.md         → Tu perfil cognitivo (se actualiza automáticamente)
├── lof_history.md         → Historial de sesiones de aprendizaje
└── conversations/
    └── README.md          → Instrucciones para el análisis histórico
```

---

## Principios de diseño

**Sin código de ejecución.** El protocolo vive en lenguaje natural.

**Sin tests de estilos de aprendizaje.** LOF infiere desde el comportamiento
real, no desde la autoevaluación. La literatura científica es clara: los
cuestionarios de estilos tienen validez predictiva baja.

**Sin servidores.** Todo corre en tu sesión de Claude. El perfil es tuyo.

**Abierto y extensible.** Podés ajustar dimensiones, señales y reglas
sin tocar código — todo está en texto plano.

---

## Fundamentos teóricos

| Dimensión | Fundamento |
|-----------|------------|
| Codificación Visual/Verbal | Dual Coding Theory (Paivio, 1971) |
| Abstracción Concreto/Abstracto | Experiential Learning Theory (Kolb, 1984) |
| Procesamiento Secuencial/Holístico | Estilos cognitivos (Pask, 1976; Witkin, 1977) |
| Estructura Lógico/Narrativo | Pensamiento narrativo vs. paradigmático (Bruner, 1986) |
| Validación Frecuente/Autónomo | Autorregulación del aprendizaje (Zimmerman, 2000) |

---

## Contribuciones

Las áreas más útiles ahora mismo:

- **Nuevas señales de inferencia** — patrones que discriminen mejor las dimensiones
- **Traducciones** — el protocolo en otros idiomas
- **Casos de uso** — documentación de experiencias reales con LOF
- **Nuevas dimensiones** — propuestas con fundamento teórico y señales operacionalizables

Abrí un issue antes de PR en cambios grandes.

---

## Licencia

MIT — libre para usar, modificar y distribuir.

---

*LOF es un protocolo, no una plataforma. No recopila datos, no tiene servidor,
no requiere cuenta. Solo Claude y vos.*
