# data-engineering-pipeline

# Pipeline de Dados: Integração de APIs, ETL, Data Warehouse e Dashboard de Vendas

## 📌 Sobre o Projeto

Este projeto simula uma arquitetura de Engenharia de Dados utilizada em ambientes corporativos.

O objetivo é integrar dados provenientes de diferentes fontes, realizar processos de limpeza e enriquecimento dos dados, armazená-los em um Data Warehouse e disponibilizar informações consolidadas para análise em dashboards de Business Intelligence.

---

## 🎯 Objetivos

- Integrar dados de diferentes fontes
- Enriquecer informações utilizando APIs externas
- Padronizar e limpar os dados
- Converter arquivos CSV e JSON para Parquet
- Construir um Data Warehouse
- Criar um Data Mart para análises
- Disponibilizar indicadores em um dashboard de vendas

---

## 🏗 Arquitetura do Projeto

```
                Receita Federal API
                        │
                        │
                Correios API
                        │
                        ▼
                 Dados Brutos (Raw)
             CSV • JSON • APIs Externas
                        │
                        ▼
            Limpeza e Transformação (ETL)
                        │
                        ▼
              Dados Limpos (Parquet)
                        │
                        ▼
                 Data Warehouse (DW)
                        │
                        ▼
                  Data Mart
                        │
                        ▼
               Dashboard Power BI
```

---

## 📂 Fontes de Dados

### Sistema OLTP

Contém os dados operacionais da empresa.

- Clientes
- Vendas

Exportados em formato CSV.

---

### API da Receita Federal

Utilizada para validar e enriquecer informações de CPF.

---

### API dos Correios

Responsável pela validação dos CEPs e obtenção de informações de localização.

---

## 🔄 Pipeline ETL

### Extração

- Dados do banco OLTP
- Dados das APIs externas

### Transformação

- Tratamento de valores nulos
- Padronização de formatos
- Conversão CSV → Parquet
- Conversão JSON → Parquet
- Validação de CPF
- Validação de CEP

### Carga

Os dados tratados são carregados para o Data Warehouse.

---

## 📁 Estrutura dos Dados

### Camada Raw

```
clientes.csv
vendas.csv
CPFs_validos.json
custo_rota.json
```

---

### Camada Processada

```
clientes.parquet
vendas.parquet
CPFs_validos.parquet
custo_rota.parquet
```

---

## 🗄 Data Warehouse

O DW consolida todas as informações tratadas para análise.

Tabelas principais:

- Clientes
- Vendas
- CPF_Válidos
- Custo_Rota

---

## 📊 Data Mart

Após a modelagem dimensional, os dados são organizados para consumo pelo Power BI.

Exemplo de indicadores:

- Receita Total
- Clientes Ativos
- Ticket Médio
- Quantidade de Vendas
- Custos por Região
- Vendas por Cliente

---

## 🛠 Tecnologias

- Python
- Pandas
- SQL
- APIs REST
- CSV
- JSON
- Parquet
- Data Warehouse
- Power BI

---

## 📈 Fluxo do Projeto

1. Extração dos dados do OLTP
2. Consulta às APIs
3. Enriquecimento dos dados
4. Limpeza dos registros
5. Conversão para Parquet
6. Carga no Data Warehouse
7. Modelagem do Data Mart
8. Construção do Dashboard

---

## 🚀 Resultados Esperados

- Centralização das informações
- Dados padronizados
- Melhor desempenho utilizando Parquet
- Informações confiáveis para tomada de decisão
- Dashboard atualizado com dados tratados

---

## 👨‍💻 Autor

**Vitor Nogueira Rocha**

Estudante de Análise e Desenvolvimento de Sistemas, com foco em Engenharia de Dados, ETL, SQL, Python e Business Intelligence.
