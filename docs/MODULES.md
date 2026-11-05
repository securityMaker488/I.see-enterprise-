# Módulos e verticais

## Núcleo compartilhado

| Módulo | Descrição |
|---|---|
| Organizações | Hierarquia `Organization → Unit → Area`, perfis e redes de organizações. |
| Identidade e acesso | Login com JWT, sessão com revogação (logout), RBAC no backend. |
| Pessoas | Cadastro de pessoas com foto de perfil separada da biometria (biometria opcional). |
| Câmeras | Cadastro automático por URL/host, probe de compatibilidade, supervisão e reconexão. |
| Visão computacional | Detecção YuNet, embeddings Facenet512, confirmação temporal, deduplicação. |
| Eventos e incidentes | EventBus persistente, histórico, replay, correlação e gestão de incidentes. |
| Observabilidade | Logs estruturados, métricas, health checks, alertas e recuperação controlada. |
| Relatórios | Relatórios operacionais e de presença, com exportação. |
| I.See AI | Assistente operacional com ferramentas somente-leitura autorizadas. |

## I.See Corporate

- Monitoramento de câmeras e áreas por unidade.
- Eventos de acesso, alertas e incidentes com trilha de auditoria.
- Gestão de usuários e permissões por organização.
- Relatórios operacionais e auditoria de ações administrativas.

## I.See School

- Alunos, turmas, turnos e unidades escolares.
- Presença diária por reconhecimento **autorizado** ou por registro manual.
- **Correção manual auditável** *(em desenvolvimento)*: toda alteração guardará status anterior,
  novo status, origem, justificativa, operador e horário.
- Histórico de presença por período *(em desenvolvimento)*.
- **Planejamento de alimentação escolar** *(em desenvolvimento)*: relatório agregado (sem
  identificação individual) com presentes, margem de segurança para não marcados e estimativa de
  refeições por turno e por turma.

### Garantia de serviço essencial

> O reconhecimento facial **não** é condição para que um estudante seja atendido.
> Se a biometria estiver indisponível, incorreta ou não autorizada pelo responsável, a presença é
> registrada manualmente e o estudante continua contabilizado para alimentação e demais serviços.

Exemplo sintético da resposta: [`demo/school-meal-planning.json`](../demo/school-meal-planning.json).

## I.See AI

- Providers configuráveis: Gemini, Groq e **Ollama (IA local)**.
- Respostas fundamentadas em registros reais, restritas ao tenant e às permissões do usuário.
- *(em desenvolvimento)* Ferramentas de status de câmeras e serviços, proteção contra prompt
  injection, limite de requisições e controle de custos por organização.
- Ações sensíveis exigem confirmação humana (princípio de projeto).
- A IA é **opcional**: o produto opera integralmente sem ela.
