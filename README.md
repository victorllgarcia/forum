# ForumHub API

## Descrição do Projeto
ForumHub é uma API REST desenvolvida em Java utilizando Spring Boot. Esta API é destinada a gerenciar tópicos de um fórum, permitindo a criação, leitura, atualização e exclusão de tópicos. Além disso, utiliza autenticação básica para restringir o acesso aos endpoints.

## Funcionalidades
- Criar um novo tópico.
- Listar todos os tópicos.
- Obter detalhes de um tópico específico.
- Atualizar um tópico existente.
- Excluir um tópico.

## Pré-requisitos
- Java 17 ou superior.
- Maven 3.8 ou superior.
- IDE com suporte a Java (IntelliJ, Eclipse, etc.).

## Configuração do Projeto

### Estrutura do Projeto
```
src/
├── main/
│   ├── java/
│   │   └── com/
│   │       └── example/
│   │           └── forumhub/
│   │               ├── ForumhubApplication.java
│   │               ├── model/
│   │               │   └── Topic.java
│   │               ├── repository/
│   │               │   └── TopicRepository.java
│   │               ├── service/
│   │               │   └── TopicService.java
│   │               └── controller/
│   │                   └── TopicController.java
│   └── resources/
│       ├── application.properties
│       └── static/
│
└── test/
```

### Configuração do Banco de Dados
A aplicação utiliza o banco de dados H2 em memória. As configurações estão no arquivo `application.properties`:

```properties
spring.datasource.url=jdbc:h2:mem:forumhub
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
```

### Segurança
A autenticação básica está configurada com as seguintes credenciais padrão:
- **Usuário:** admin
- **Senha:** admin

## Como Rodar o Projeto

1. Clone o repositório:
   ```bash
   git clone <URL_DO_REPOSITORIO>
   ```

2. Navegue até o diretório do projeto:
   ```bash
   cd forumhub-api
   ```

3. Compile o projeto com Maven:
   ```bash
   mvn clean install
   ```

4. Execute a aplicação:
   ```bash
   mvn spring-boot:run
   ```

5. Acesse a aplicação em: `http://localhost:8080`

## Endpoints da API

### Criar Tópico
**POST /api/topics**
```json
{
  "title": "Título do tópico",
  "content": "Conteúdo do tópico",
  "author": "Autor do tópico"
}
```

### Listar Todos os Tópicos
**GET /api/topics**

### Obter Detalhes de um Tópico
**GET /api/topics/{id}**

### Atualizar Tópico
**PUT /api/topics/{id}**
```json
{
  "title": "Novo título",
  "content": "Novo conteúdo"
}
```

### Excluir Tópico
**DELETE /api/topics/{id}**

## Tecnologias Utilizadas
- Spring Boot
- Spring Data JPA
- Spring Security
- Banco de Dados H2
- Maven

## Próximos Passos
- Implementar paginação e ordenação nos endpoints de listagem.
- Melhorar a autenticação, integrando com OAuth2 ou JWT.
- Criar testes unitários e de integração.

---

Para dúvidas ou sugestões, entre em contato. Aproveite o projeto!
