# 🎧 MusicGraph Analytics: Análise de Dados de Streaming com Neo4j

Este projeto foi desenvolvido como parte do **Bootcamp da DIO (Digital Innovation One): Análise de Dados com Grafos e Neo4j**. O objetivo é demonstrar como a estrutura de grafos supera o modelo relacional na análise de conexões complexas em plataformas de streaming como o Spotify.

---

## 📌 Contexto do Projeto
No ecossistema musical, os dados são interconectados por natureza: um artista pode ser também compositor; usuários que ouvem sertanejo podem ter "pontes" de interesse com o pop internacional. 

Modelar isso em SQL exigiria JOINs exaustivos. Com **Neo4j e Cypher**, as conexões são exploradas de forma nativa, permitindo recomendações em tempo real e análise de nichos globais.

---

## 🛠️ O Dataset (Modelo de Dados)
O banco de dados foi populado com um cenário diversificado:
- **30 Artistas:** Mesclando grandes nomes nacionais (Sertanejo, Pagode, Funk, Rock) e internacionais (Pop, R&B, Hip Hop).
- **45 Músicas:** Distribuídas entre gêneros que cruzam fronteiras culturais.
- **10 Usuários:** Localizados em diferentes regiões (Brasil, Japão, EUA) para simular comportamentos de expatriados e fãs globais.

### Entidades e Relações
- `(:Artista)-[:CANTOU]->(:Musica)`
- `(:Musica)-[:GENERO]->(:Gênero)`
- `(:Usuario)-[:OUVIU {nota: Int}]->(:Musica)`

---

## 🔍 Perguntas de Negócio (BI Insights)

O projeto responde a 3 perguntas estratégicas para a gestão de uma plataforma de streaming:

1. **Caminhos de Influência:** Como um fã de Funk chega ao Rock Internacional através de conexões de terceiros?
2. **Densidade de Rede:** Qual gênero musical conecta o maior número de artistas globais?
3. **Sistema de Recomendação:** Sugestão de músicas baseada no comportamento de "usuários espelhos".

---


## 🚀 Como Executar

1. Abra o **Neo4j Desktop** ou **Sandbox**.
2. No console, limpe o banco:
   ```cypher
   MATCH (n) DETACH DELETE n;

```

3.  Execute o script de carga (disponível na pasta `/scripts`).
    
4.  Visualize a rede completa:
    
    Cypher
    
    ```
    MATCH (n)-[r]->(m) RETURN n, r, m LIMIT 100;
    
    ```
    

----------

## 📈 Conclusão

A análise de grafos se mostrou a ferramenta definitiva para entender o comportamento humano no consumo de mídia. Este projeto solidifica os conceitos de **Cypher Query Language**, modelagem de propriedades e análise de rede aprendidos no Bootcamp da DIO.

----------

**Desenvolvido por Suzi Sayuri Terruya - Estudante de Data Science – 2026** _Análise de Dados com Grafos | DIO Bootcamp_
