# Практика 2026. Оглавление и выдержки чек-листов

**Полный документ:** `AI_Practice_2026_RU.md` (~45 тыс. знаков)  
**Версия lockstep:** 2026.10.28.1  
**В репозитории:** выдержка. Полный текст, только по запросу.

---

## Оглавление полного документа (структура)

1. Подходы к разработке и оркестрации (prompt-native, tool-calling, sandbox, workflow hosts)
2. От прототипа к industrial rollout (offline eval → sandbox → shadow → narrow live → broader authority)
3. Model Routing (классы моделей, не бренды)
4. Инфраструктура и развёртывание (local, VPS+MaaS, GPU, open-weight serving)
5. Базовые блоки промышленного агента (operational checklist)
6. MCP в industrial среде (Host & Gateway)
7. RAG Operations (метрики retrieval / generation / end-to-end)
8. Observability & Tracing
9. Pre-production Checklist
10. Design-Pipeline Operations
11. Типовые use cases
12. Свод лучших практик 2026
13. Чего не переносить из демо в production

---

## Выдержка: стадии rollout

| Этап | Что активно | Что отключено |
|------|-------------|----------------|
| Offline eval | Golden sets | Боевые tools, живые пользователи |
| Sandbox | Агент + mocks | Production credentials |
| Shadow mode | Копия трафика, только логи | Ответы пользователям |
| Narrow live | Одна задача, HITL на необратимом | Широкая автономия |
| Broader authority | После доказанной стабильности | Безлимитные бюджеты |

---

## Выдержка: Pre-production Checklist (сжато)

1. Владелец и Least Agency (NHI): критерии успеха/сбоя.
2. Разбор Agentic Top 10 (особенно ASI01, ASI08, ASI09).
3. Golden set в CI.
4. MCP: JSON Schema, идемпотентность актуаторов, таймауты.
5. HITL через независимый consent, не только кнопка в чате.
6. Бюджеты шагов / токенов / времени / spend + ESCALATE.
7. Shadow или sandbox на реальном профиле нагрузки.
8. Trace Context: восстановление траектории по логам.
9. Version-pin зависимостей; секреты только на gateway.

---

## Выдержка: Design-Pipeline Operations

- Dual gate: параметры → аналитика → только потом архитектура.
- Явный hard out-of-scope и NFR (latency class, privacy).
- 2–3 коротких сценария до полных Job Stories.
- Выдача KB в чате: манифест → HITL → порции для ручного переноса (не «тихая запись»).
- Lockstep версий Core / Standard / Index + Changelog.

---

Полный текст Практики — операционные таблицы, serving stack, anti-demo правила. Для интервью предоставляется по запросу.
