# Sistema de Atividades Extracurriculares - Mergington High School

Um sistema web completo que permite aos alunos visualizar atividades extracurriculares e aos professores gerenciar inscrições de estudantes. A aplicação oferece uma interface moderna e intuitiva para facilitar o gerenciamento de atividades escolares.

## Visão Geral da Aplicação

O sistema oferece uma plataforma centralizada para o gerenciamento de atividades extracurriculares, permitindo que estudantes explorem opções disponíveis e professores administrem as inscrições de forma eficiente.

### Tecnologias Utilizadas

- **Backend**: FastAPI (Python) - Framework moderno para APIs REST
- **Frontend**: HTML, CSS e JavaScript - Interface responsiva e interativa
- **Banco de Dados**: MongoDB (com modo de backup em memória)
- **Servidor**: Uvicorn ASGI - Servidor de alta performance
- **Autenticação**: Sistema de login para professores com senhas criptografadas

## Funcionalidades Principais

### Para Estudantes
- **Visualização de Atividades**: Explore todas as 13 atividades extracurriculares disponíveis
- **Filtros Avançados**: 
  - Por categoria (Esportes, Artes, Acadêmico, Comunidade, Tecnologia)
  - Por dia da semana (Segunda a Domingo)
  - Por horário (Antes da Aula, Depois da Aula, Final de Semana)
- **Busca Inteligente**: Encontre atividades específicas por nome
- **Informações Detalhadas**: Veja horários, vagas disponíveis e participantes atuais
- **Interface Responsiva**: Acesse de qualquer dispositivo

### Para Professores
- **Sistema de Login Seguro**: Autenticação necessária para gerenciar inscrições
- **Gerenciamento de Inscrições**: Registrar e remover estudantes das atividades
- **Controle de Vagas**: Monitorar capacidade e participantes de cada atividade

### Atividades Disponíveis

O sistema oferece uma variedade de atividades organizadas por categoria:

**🎯 Acadêmico:**
- Chess Club, Math Club, Debate Team, Science Olympiad, Sunday Chess Tournament

**💻 Tecnologia:**
- Programming Class, Weekend Robotics Workshop

**🏃 Esportes:**
- Morning Fitness, Soccer Team, Basketball Team

**🎨 Artes:**
- Art Club, Drama Club, Manga Maniacs

Cada atividade possui horários específicos, limites de participantes e está categorizada para facilitar a navegação.

## Como Usar o Sistema

### Acesso para Estudantes
1. Acesse a página principal em seu navegador
2. Use os filtros na barra lateral para encontrar atividades de interesse
3. Visualize detalhes como horários e vagas disponíveis
4. Entre em contato com um professor para realizar a inscrição

### Acesso para Professores
1. Clique no botão "Login" no topo da página
2. Faça login com suas credenciais de professor
3. Registre ou remova estudantes das atividades conforme necessário

## Configuração e Desenvolvimento

### Pré-requisitos
- Python 3.7 ou superior
- Dependências listadas em `requirements.txt`

### Instalação
```bash
# Instalar dependências
pip install -r requirements.txt
```

### Executar a Aplicação
```bash
# A partir da pasta raiz do projeto
python -m uvicorn src.app:app --host 0.0.0.0 --port 8000 --reload
```

### Acessar o Sistema
- **Site Principal**: http://localhost:8000
- **Documentação da API**: http://localhost:8000/docs
- **Documentação Alternativa**: http://localhost:8000/redoc

## API Endpoints

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| GET | `/activities/` | Lista todas as atividades com filtros opcionais |
| POST | `/activities/{nome}/signup` | Inscreve um estudante (requer autenticação) |
| POST | `/activities/{nome}/unregister` | Remove inscrição (requer autenticação) |

## Configuração do Banco de Dados

A aplicação funciona em dois modos:
- **Modo MongoDB**: Quando um servidor MongoDB está disponível em `localhost:27017`
- **Modo Backup**: Usa dados em memória quando MongoDB não está disponível

> **Nota**: No modo backup, os dados são reiniciados a cada reinicialização do servidor.

## Guia de Desenvolvimento

Para instruções detalhadas de configuração e desenvolvimento, consulte nosso [Guia de Desenvolvimento](../docs/how-to-develop.md).
