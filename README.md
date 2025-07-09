# Análise de Churn de Clientes - Telecom X

![Telecom Banner](https://i.imgur.com/8Bv2s2A.png)
*Banner ilustrativo para o projeto*

## 📖 Sobre o Projeto

Este projeto consiste em uma **análise de evasão (churn) de clientes** para a empresa fictícia de telecomunicações **Telecom X**. O objetivo principal é realizar um processo completo de **Extração, Transformação e Carga (ETL)** e uma **Análise Exploratória de Dados (EDA)** para identificar os principais fatores que levam os clientes a cancelarem seus serviços.

A análise busca encontrar padrões no comportamento e no perfil dos clientes que evadem, fornecendo insights valiosos que podem ser utilizados pela equipe de Data Science para construir modelos preditivos e, consequentemente, ajudar a empresa a desenvolver estratégias eficazes para a retenção de clientes.

O relatório completo, com todas as visualizações de dados, análises detalhadas e conclusões, está documentado no notebook `analise_churn.ipynb` contido neste repositório.

## 🛠️ Tecnologias Utilizadas

O projeto foi desenvolvido utilizando as seguintes tecnologias e bibliotecas Python:

* `Python 3.x`
* `Requests:` Para a extração dos dados via API/URL.
* `Pandas:` Para manipulação, limpeza e transformação dos dados.
* `Matplotlib & Seaborn:` Para a criação dos gráficos e visualizações de dados.
* `Jupyter Notebook:` Como ambiente para desenvolvimento e documentação da análise.

## 🚀 Etapas do Projeto

O desenvolvimento foi dividido em duas etapas macro, seguindo as melhores práticas de análise de dados.

### 1. Extração, Transformação e Limpeza (ETL)

* **Extração:** Os dados foram extraídos em formato JSON diretamente de uma URL do repositório da Alura no GitHub, utilizando a biblioteca `requests`.
* **Transformação:** A estrutura aninhada do JSON foi "achatada" (normalizada) para um formato tabular (DataFrame) com o Pandas, facilitando a análise. As colunas foram renomeadas para nomes mais intuitivos.
* **Limpeza:** Foram realizados tratamentos essenciais nos dados, como:
    * Conversão de tipos de dados (ex: `TotalCharges` de texto para numérico).
    * Tratamento de valores inconsistentes ou faltantes (ex: espaços em branco na coluna `TotalCharges` e valores vazios na coluna `Churn`).
    * Mapeamento de valores categóricos para melhor legibilidade (ex: `SeniorCitizen` de 0/1 para 'Não'/'Sim').

### 2. Análise Exploratória de Dados (EDA)

Com os dados devidamente tratados, foi realizada uma investigação visual para identificar os principais preditores de churn. A análise focou em:

* **Visão Geral do Churn:** Quantificação da taxa de evasão na base de dados.
* **Fatores Demográficos:** Relação do churn com gênero, idade (idosos), parceiros e dependentes.
* **Informações Contratuais:** Análise do impacto do tipo de contrato, método de pagamento e fatura online no churn.
* **Valores e Tempo de Contrato:** Investigação sobre como as taxas mensais (`MonthlyCharges`) e o tempo de permanência do cliente (`Tenure`) influenciam a evasão.
* **Serviços Contratados:** Verificação da correlação entre o tipo de serviço de internet (DSL vs. Fibra Óptica) e serviços adicionais (Suporte Técnico, Segurança Online, etc.) com a taxa de churn.

## 📈 Principais Insights Encontrados

A análise revelou padrões claros que definem o perfil do cliente propenso ao churn:

1.  **Tipo de Contrato:** Clientes com contrato **mensal** (Month-to-month) possuem uma taxa de churn drasticamente superior aos de contrato anual.
2.  **Serviços Adicionais:** A ausência de serviços de proteção, como **Segurança Online** e **Suporte Técnico**, está fortemente correlacionada com uma maior chance de cancelamento.
3.  **Serviço de Internet:** Clientes com **Fibra Óptica** tendem a cancelar mais, o que pode indicar problemas de satisfação com o preço ou a qualidade do serviço.
4.  **Tempo de Contrato (Tenure):** Clientes com **pouco tempo de casa** (baixo `Tenure`) e, consequentemente, baixos gastos totais (`TotalCharges`), são os que mais cancelam.

## ▶️ Como Executar o Projeto

Para replicar a análise, siga os passos abaixo:

1.  **Clone este repositório:**
    ```bash
    git clone https://github.com/vivianebatista92/churn_TelecomX.git
    cd churn_TelecomX
    ```

2.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Observação: Recomenda-se criar um ambiente virtual antes de instalar as dependências.)*

3.  **Execute o Jupyter Notebook:**
    Abra o arquivo `analise_churn.ipynb` em um ambiente com Jupyter Notebook para ver todo o processo de análise, desde o código até as conclusões detalhadas.
    ```bash
    jupyter notebook churn_TelecomX.ipynb
    ```

---
*Este projeto foi desenvolvido como parte do desafio Telecom X da Alura.*

---

