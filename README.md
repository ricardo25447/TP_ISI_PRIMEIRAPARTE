# 💹 Monitorização de Criptomoedas — Projeto Pentaho

Este projeto foi desenvolvido no **Pentaho Data Integration (Spoon)** com o objetivo de **consultar, transformar e exportar dados de criptomoedas em tempo real**, obtidos através da **API pública da CoinGecko**.

---

## 📘 Descrição do Projeto

A transformação principal (`TrabalhoPraticoPrimeiraParte.ktr`) automatiza todo o processo de recolha e atualização de dados.  
A cada execução, o Pentaho:

1. **Consulta a API da CoinGecko** — obtendo as informações mais recentes das criptomoedas monitorizadas.  
2. **Trata o ficheiro JSON** — removendo caracteres desnecessários e extraindo apenas os campos relevantes.  
3. **Exporta os dados tratados** para três formatos: `.CSV`, `.TXT` e `.XML`.  
4. **Regista a execução num log** (`LOGS.txt`) — indicando a data, hora e se houve atualização de valores.

---

## 🪙 Criptomoedas Monitorizadas

- **Bitcoin (BTC)**  
- **Ethereum (ETH)**  
- **Solana (SOL)**  
- **Cardano (ADA)**  

---

## 🧩 Estrutura do Repositório

📂 Projeto_Pentaho_Criptomoedas

│

├── TrabalhoPraticoPrimeiraParte.ktr → Ficheiro principal da transformação (Pentaho)

│

├── crypto_live.json → Dados brutos recebidos da API CoinGecko
│

├── moedas.csv → Ficheiro exportado em formato CSV

├── moedas.txt → Ficheiro exportado em formato TXT

├── moedas.xml → Ficheiro exportado em formato XML

│

└── LOGS.txt → Log da execução com data, hora e estado da atualização


---

## ⚙️ Funcionamento da Transformação

O processo de ETL (Extract, Transform, Load) segue esta sequência:

1. **OPEN JSON C**  
   - Lê o ficheiro `crypto_live.json` ou a resposta da API CoinGecko.  

2. **CONSULTA DA API**  
   - Recolhe os dados em tempo real e envia-os para o próximo step.  

3. **TRATAMENTO DE DADOS JSON (Modified JavaScript Value)**  
   - Limpa e estrutura os dados JSON, deixando apenas os campos necessários:  
     `id`, `symbol`, `current_price`, `market_cap_rank`, `last_updated`.

4. **EXTRACT DATA**  
   - Extrai os dados tratados e prepara-os para exportação.  

5. **EXPORTAÇÃO DE FICHEIROS**  
   - Cria três ficheiros de saída: `moedas.csv`, `moedas.txt` e `moedas.xml`.  

6. **EXTRACT TO LOG**  
   - Gera uma linha de log indicando o estado da atualização, data e hora.

---

## 📊 Exemplo de Log Gerado


---

## 🧠 Ferramentas Utilizadas

| Ferramenta | Função |
|-------------|--------|
| **Pentaho Data Integration (Spoon)** | Criação e execução do fluxo ETL |
| **CoinGecko API** | Fonte dos dados das criptomoedas |
| **Modified JavaScript Value** | Processamento e lógica condicional |
| **CSV/TXT/XML Output** | Exportação de ficheiros |
| **Text Output (Logs)** | Registo automático de cada execução |

---

## 🚀 Como Executar

1. Abre o **Pentaho Spoon**.  
2. Carrega o ficheiro `TrabalhoPraticoPrimeiraParte.ktr`.  
3. Executa a transformação.  
4. Os ficheiros exportados (`moedas.csv`, `moedas.txt`, `moedas.xml`) e o `LOGS.txt` serão atualizados automaticamente no disco C.

---

## 👨‍💻 Autor

**Ricardo Marques**  
Estudante de Engenharia de Sistemas Informáticos  
📧 [a25447@alunos.ipca.pt]

---

> 💡 *Este projeto demonstra a integração de dados em tempo real, desde a recolha em API até à exportação automatizada, aplicando conceitos de ETL com Pentaho.*


