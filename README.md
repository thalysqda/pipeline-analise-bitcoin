# 🪙 Pipeline e Análise de Dados: Cotação do Bitcoin (ETL & Dashboard)

![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=Databricks&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=Apache-Spark&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

## 📋 Sobre o Projeto

Este projeto demonstra a construção de uma solução completa de dados, unindo **Engenharia** e **Análise de Dados**. O objetivo principal foi desenvolver um pipeline automatizado para extrair cotações do Bitcoin em tempo real, tratar essas informações e construir um modelo analítico robusto para monitorar a volatilidade da criptomoeda.

A infraestrutura foi construída no **Databricks**, utilizando a arquitetura Lakehouse com **Delta Tables** para garantir o histórico seguro dos dados e habilitar consultas SQL de alta performance.

---

## 🎯 Arquitetura da Solução

O fluxo de dados segue o processo ETL tradicional, desenhado para ser escalável e tolerante a falhas:

```mermaid
flowchart TB
    A["🌐 API Coinbase<br/><b>Bitcoin USD</b>"] --> E["📥 EXTRACT"]
    B["🌐 API CurrencyFreaks<br/><b>USD-BRL Rate</b>"] --> E
    E --> T["🔄 TRANSFORM<br/>• Convert USD→BRL<br/>• Add timestamp<br/>• Limpeza e Tipagem"]
    T --> L["💾 LOAD<br/>Delta Table<br/>Unity Catalog"]
    L --> D["📊 DATA ANALYSIS<br/>Databricks Dashboard<br/>Consultas SQL e Métricas"]
    
    style A fill:#e1f5ff,stroke:#0066cc,stroke-width:2px
    style B fill:#e1f5ff,stroke:#0066cc,stroke-width:2px
    style E fill:#fff4e1,stroke:#ff9900,stroke-width:2px
    style T fill:#ffe1f5,stroke:#cc0066,stroke-width:2px
    style L fill:#e1ffe1,stroke:#00cc66,stroke-width:2px
    style D fill:#ffe1f0,stroke:#cc0099,stroke-width:2px
