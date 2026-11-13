# avalia-sintaxe-trabalho-academico-unirv

Skill que verifica estrutura, formatação e gramática de Trabalhos de Fim de Curso (Projeto de Pesquisa, Monografia, Relatório DERS, Relatório GDD) contra o Guia de Padronização de TFC da Fasoft/UniRV v1.0.2.

Entrada: PDF, DOCX ou LaTeX. Saída: lista de inconsistências por página, com regra violada e correção.
Escopo: somente sintático. Não avalia conteúdo, método, relevância ou coerência de argumento.

## Conteúdo

- `skills/avaliar-sintaxe-trabalho-academico/SKILL.md`: a skill.
- `referencia/Guia-padronizacao-TFC-Fasoft-v1.0.2.pdf`: guia de origem.
- `referencia/extracao-guia-tfc.md`: 288 regras extraídas do guia, com ID, escopo, tipo e página.

## Instalação

Clonar e copiar a pasta da skill para o diretório do agente.

```
git clone https://github.com/vnmartinez/avalia-sintaxe-trabalho-academico-unirv.git
```

Claude Code (global):
```
cp -r avalia-sintaxe-trabalho-academico-unirv/skills/avaliar-sintaxe-trabalho-academico ~/.claude/skills/
```

Codex:
```
cp -r avalia-sintaxe-trabalho-academico-unirv/skills/avaliar-sintaxe-trabalho-academico ~/.codex/skills/
```

Antigravity e agentes que leem `~/.agents/skills`:
```
cp -r avalia-sintaxe-trabalho-academico-unirv/skills/avaliar-sintaxe-trabalho-academico ~/.agents/skills/
```

Windows (PowerShell), exemplo para Codex:
```
Copy-Item -Recurse avalia-sintaxe-trabalho-academico-unirv\skills\avaliar-sintaxe-trabalho-academico $HOME\.codex\skills\
```

Claude.ai: compactar a pasta `avaliar-sintaxe-trabalho-academico` em .zip e enviar em Configurações > Capacidades > Skills.

## Uso

Pedir ao agente: "verifique este TFC com a skill avaliar-sintaxe-trabalho-academico" e anexar o arquivo.

## Limites

- O guia não traz regra de citação longa nem recuo de citação; a skill não cobra esses pontos.
- Propriedades não extraíveis do arquivo (gramatura, impressão frente/verso) saem como NÃO VERIFICÁVEL.
- Ambiguidades do próprio guia saem como AVISO.
- O PDF de referência pertence à Fasoft/UniRV.
