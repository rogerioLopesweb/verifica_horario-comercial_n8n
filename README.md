# 🕒 Horario_comercial - n8n Workflow

Este repositório contém um fluxo do [n8n](https://n8n.io/) que verifica se uma mensagem de chat foi recebida dentro do horário comercial e responde automaticamente com base nisso.

![image](https://github.com/user-attachments/assets/9e82c012-cfd4-436b-8739-4ba746aa8472)


## 📌 Funcionalidade

O fluxo implementa a seguinte lógica:

- Ao receber uma nova mensagem de chat:
  - Obtém a hora atual em São Paulo (UTC-3).
  - Verifica se a hora está dentro do horário comercial:
    - Segunda a sexta: 09h às 18h
    - Sábado: 09h às 14h
  - Retorna uma mensagem personalizada:
    - Dentro do horário: `"Olá! Perfeito, estamos disponíveis para te atender!"`
    - Fora do horário: `"Olá! No momento estamos fora do horário comercial. Em breve retornaremos."`

## 📂 Estrutura

O fluxo contém os seguintes nós principais:

- `When chat message received` - Gatilho de entrada.
- `Code` - Código JavaScript que determina se a mensagem está dentro do horário comercial.
- `IF` - Verifica a variável `horarioComercial`.
- `Set` - Define a mensagem de resposta apropriada.
- `Respond to Webhook` - Envia a resposta de volta ao usuário.

## 🚀 Como usar

1. Importe o arquivo `HorArio_comercial.json` no seu ambiente n8n.
2. Conecte o nó de gatilho `When chat message received` ao seu webhook/chatbot.
3. Ative o fluxo no n8n.
4. Pronto! Agora o fluxo irá responder automaticamente com base no horário.

## 🛠️ Requisitos

- n8n (self-hosted ou na nuvem)
- Conexão com um serviço de chat via webhook

## 🧠 Observações

- O fuso horário utilizado é o de **São Paulo (America/Sao_Paulo)**.
- Você pode adaptar os horários ou mensagens conforme sua necessidade.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
