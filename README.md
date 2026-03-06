# Support Tickets API

API REST desenvolvida em Node.js para gerenciamento de chamados de suporte técnico.

O sistema permite criar, listar, atualizar, alterar status e remover tickets de suporte.

---

## Tecnologias utilizadas

* Node.js
* JavaScript
* API HTTP nativa do Node
* File-based database (JSON)

---

## Estrutura do projeto

```
src
 ├ controllers
 │   └ tickets
 │       ├ create.js
 │       ├ remove.js
 │       ├ update.js
 │       └ updateStatus.js
 │
 ├ database
 │   ├ database.js
 │   └ db.json
 │
 ├ middlewares
 │   ├ jsonHandler.js
 │   └ routeHandler.js
 │
 ├ routes
 │   ├ index.js
 │   └ tickets.js
 │
 ├ utils
 │   ├ extractQueryParams.js
 │   └ parseRoutePath.js
 │
 └ server.js
```

---

## Funcionalidades

* Criar um ticket de suporte
* Listar tickets
* Atualizar informações do ticket
* Alterar status do ticket
* Remover ticket

---

## Estrutura de um Ticket

```json
{
  "id": "uuid",
  "equipment": "Computador",
  "description": "Computador não liga",
  "user_name": "Usuário",
  "status": "open | closed",
  "created_at": "timestamp",
  "updated_at": "timestamp",
  "solution": "Descrição da solução"
}
```

---

## Endpoints da API

### Criar ticket

POST /tickets

### Listar tickets

GET /tickets

### Atualizar ticket

PUT /tickets/:id

### Atualizar status do ticket

PATCH /tickets/:id/status

### Remover ticket

DELETE /tickets/:id

---

## Banco de dados

O projeto utiliza um banco de dados simples baseado em arquivo JSON (`db.json`).

A persistência é gerenciada pela classe `Database`, responsável por:

* inserir registros
* consultar registros
* atualizar registros
* remover registros

---

## Router personalizado

O projeto implementa um sistema de roteamento próprio utilizando expressões regulares para interpretar parâmetros de rota.

Exemplo:

```
/tickets/:id
```

Isso é convertido para uma expressão regular que permite capturar o parâmetro dinamicamente.

---

## Como executar o projeto

Clone o repositório:

```
git clone <repo>
```

Entre na pasta do projeto:

```
cd support-tickets-api
```

Instale as dependências:

```
npm install
```

Execute o servidor:

```
npm run dev
```

A API estará disponível em:

```
http://localhost:3333
```

---

## Objetivo do projeto

Este projeto foi desenvolvido com fins educacionais para praticar conceitos de backend como:

* criação de APIs REST
* organização de arquitetura em camadas
* manipulação de rotas
* persistência de dados
* middlewares
* separação de responsabilidades no código
