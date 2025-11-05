# 📚 Agente de IA para Processamento de PDF

Uma aplicação completa para processamento inteligente de documentos PDF usando **AgentOS**, com **API REST** e **interface web**.

---

## 🚀 Visão Geral

Este projeto consiste em:

- **Backend API**: API REST construída com FastAPI/AgentOS para processamento de documentos PDF  
- **Frontend Web**: Interface Streamlit para interação com o agente de IA  
- **Agente Inteligente**: Agente especializado em análise e Q&A de documentos PDF  

---

## 🏗️ Estrutura do Projeto

```
agente-pdf-ia/
├── 📁 src/                # Código fonte principal
│   ├── deploy2.py         # Script de deploy e inicialização
│   └── agent_setup.py     # Configuração do agente
├── 📁 frontend/           # Aplicação Streamlit
│   └── app.py             # Interface web
├── 📁 temp/               # Arquivos temporários (gerado automaticamente)
├── requirements.txt       # Dependências Python
├── runtime.txt            # Versão do Python (3.11.0)
└── README.md              # Esta documentação
```

---

## ⚙️ Funcionalidades

### 🔙 Backend (API)
- ✅ Processamento de documentos PDF  
- ✅ Q&A inteligente sobre o conteúdo  
- ✅ Integração com AgentOS  
- ✅ API REST endpoints  
- ✅ Armazenamento vetorial com ChromaDB  

### 🖥️ Frontend (Streamlit)
- ✅ Upload de arquivos PDF  
- ✅ Interface para perguntas e respostas  
- ✅ Visualização de resultados  
- ✅ Histórico de interações  

---

## 🛠️ Tecnologias

**Backend:**
- Python 3.11.0  
- FastAPI / AgentOS  
- ChromaDB (vector store)  
- OpenAI Embeddings  
- Uvicorn (ASGI server)

**Frontend:**
- Streamlit  
- Python  
- Requests (para chamadas à API)

---

## 📦 Instalação e Execução

### 🔧 Pré-requisitos
- Python 3.11.0  
- [UV](https://github.com/astral-sh/uv) (package manager)  
- Chave API da OpenAI  

---

### 1. Clone o repositório

```bash
git clone <seu-repositorio>
cd agente-pdf-ia
```

### 2. Instale as dependências

```bash
uv sync
```

### 3. Configure as variáveis de ambiente

```bash
export OPENAI_API_KEY="sua-chave-openai"
```

### 4. Execute o backend

```bash
cd src
uv run python deploy2.py
```

A API estará disponível em:  
👉 **https://servidor-api-agente-de-pdf.onrender.com**

---

### 5. Execute o frontend (em outro terminal)

```bash
cd frontend
uv run streamlit run app.py
```

A interface estará em:  
👉 **https://servidor-api-agente-de-pdf-1.onrender.com/**

---

## 🌐 Deploy no Render

**Configuração do Serviço Web:**

- **Runtime:** Python 3.11.0  
- **Build Command:** `uv sync`  
- **Start Command:**  
  ```bash
  uv run python -m uvicorn src.deploy2:app --host 0.0.0.0 --port $PORT
  ```

**Variáveis de Ambiente no Render:**
```
OPENAI_API_KEY = sua-chave-da-openai
PORT = 10000
```

---

## 📋 Endpoints da API

### **POST /process-pdf**
Processa um documento PDF e extrai o conteúdo para a base de conhecimento.

**Body:** `FormData` com o arquivo PDF.

---

### **POST /ask**
Faz uma pergunta sobre os documentos processados.

**Body:**
```json
{
  "question": "Sua pergunta aqui"
}
```

---

## 🎯 Uso da Aplicação

1. **Upload de PDF:** Faça upload do documento via interface Streamlit  
2. **Processamento:** O agente extrai e indexa o conteúdo  
3. **Perguntas:** Interaja com o documento através de perguntas em linguagem natural  
4. **Respostas:** Receba respostas contextuais baseadas no conteúdo do PDF  

---

## ⚠️ Observações Importantes

- A pasta `temp/` é criada automaticamente durante a execução  
- Certifique-se de ter uma **chave OpenAI API válida**  
- O projeto está configurado especificamente para **Python 3.11.0**  
- Para deploy, configure corretamente as **variáveis de ambiente**

---

## 🔧 Troubleshooting

**Problemas Comuns:**

| Problema | Solução |
|-----------|----------|
| Pasta `temp` não existe | É criada automaticamente no startup |
| Erro de coroutine | Certifique-se de usar `await` em funções assíncronas |
| Porta em uso | Verifique se a porta `10000` está livre |
| Dependências | Use **Python 3.11.0** para compatibilidade |


---

**Desenvolvido com por Diego Ribeiro, usando AgentOS e Streamlit**
