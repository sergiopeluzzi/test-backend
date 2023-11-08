# Projeto

Você vai desenvolver seu app utilizando a arquitetura MSC!

Neste novo projeto deverá ser possível fazer o cadastro e login de pessoas usuárias, onde apenas essas pessoas poderão acessar, modificar e deletar as receitas que cadastrou.

---

---

---

# Desenvolvimento

Você vai desenvolver todas as camadas da aplicação (Models, Service e Controllers).

Através dessa aplicação, será possível realizar as operações básicas que se pode fazer em um determinado banco de dados: Criação, Leitura, Atualização e Exclusão.

Para realizar qualquer tipo de alteração no banco de dados (como cadastro, edição ou exclusão de receitas) será necessário autenticar-se.

Além disso, as pessoas usuárias devem poder ser clientes ou administradores.
Pessoas clientes apenas poderão disparar ações nas receitas que ele mesmo criou. Já uma pessoa administradora pode disparar qualquer ação em qualquer receita.

A autenticação deverá ser feita via JWT

Deverá ser possível adicionar uma imagem à uma receita, utilizando o upload de arquivos fornecido pelo multer

---

---

---

# Requisitos do projeto

1. Criar um endpoint para Cadastro de usuários
2. Criar um endpoint para Login de usuários
3. Criar um endpoint para Cadastro de Receitas
4. Criar um endpoint para Listagem de Receitas
5. Criar um endpoint para Visualizar uma Receita específica
6. Criar um endpoint para Edição de Receitas
7. Criar um endpoint para Exclusão de Receitas
8. Criar um endpoint para adição de uma imagem a uma receita
9. Criar um endpoint para acessar a imagem de uma receita
10. Criar testes unitários que cubram no mínimo 30% dos arquivos

## Requisitos Bônus

11. Criar um endpoint para cadastro de administradores
12. Criar testes unitários que cubram no mínimo 60% dos arquivos
13. Criar testes unitários que cubram no mínimo 90% dos arquivos

---

---

---

# Especificações

### 1. Criar um endpoint para Cadastro de usuários

-   A rota deve ser (/users).
-   No banco um usuário precisa ter os campos Email, Senha, Nome e Role.
-   Para criar um usuário através da API, todos os campos são obrigatórios, com exceção do Role.
-   O campo Email deve ser único.
-   Usuários criados através desse endpoint devem ter seu campo Role com o atributo user, ou seja, devem ser usuários comuns, e não admins.

### 2. Criar um endpoint para Login de usuários

-   A rota deve ser (/login).
-   A rota deve receber os campos Email e Senha e esses campos devem ser validados no banco de dados.
-   Um token JWT deve ser gerado e retornado caso haja sucesso no login. No seu payload deve estar presente o id, email e role do usuário.

### 3. Criar um endpoint para Cadastro de Receitas

-   A rota deve ser (/recipes).
-   A receita só pode ser criada caso o usuário esteja logado e o token JWT validado.
-   No banco, a receita deve ter os campos Nome, Ingredientes, Modo de preparo, URL da imagem e Id do Autor.
-   O campo dos ingredientes pode ser um campo de texto aberto.
-   O campo ID do autor, deve ser preenchido automaticamente com o ID do usuário logado, que deve ser extraído do token JWT.
-   A URL da imagem será preenchida através de outro endpoint

### 4. Criar um endpoint para Listagem de Receitas

-   A rota deve ser (/recipes).
-   A rota pode ser acessada por usuários logados ou não

### 5. Criar um endpoint para Visualizar uma Receita específica

-   A rota deve ser (/recipes/:id).
-   A rota pode ser acessada por usuários logados ou não

### 6. Criar um endpoint para Edição de Receitas

-   A rota deve ser (/recipes/:id).
-   A receita só pode ser atualizada caso o usuário esteja logado e o token JWT validado.
-   A receita só pode ser atualizada caso pertença ao usuário logado, ou caso esse usuário seja um admin.

### 7. Criar um endpoint para Exclusão de Receitas

-   A rota deve ser (/recipes/:id).
-   A receita só pode ser excluída caso o usuário esteja logado e o token JWT validado.
-   A receita só pode ser excluída caso pertença ao usuário logado, ou caso o usuário logado seja um admin.

### 8. Criar um endpoint para adição de uma imagem a uma receita

-   A rota deve ser (/recipes/:id/image/).
-   A imagem deve ser lida do campo image.
-   O endpoint deve aceitar requisições no formato multipart/form-data.
-   A receita só pode ser atualizada caso o usuário esteja logado e o token JWT validado.
-   A receita só pode ser atualizada caso pertença ao usuário logado ou caso o usuário logado seja admin.
-   O upload da imagem deverá ser feito utilizando o Multer.
-   O nome do arquivo deve ser o ID da receita, e sua extensão .jpeg.
-   A URL completa para acessar a imagem através da API deve ser gravada no banco de dados, junto com os dados da receita.

### 9. Criar um endpoint para acessar a imagem de uma receita

-   As imagens devem estar disponíveis através da rota `/images/<id-da-receita>.jpeg` na API.

### 10. Criar testes unitários que cubram no mínimo 30% dos arquivos

-   Os testes de integração devem ser criados na pasta ./tests
-   Os arquivos .spec.ts podem ser alterado, renomeado ou removido;
-   Os testes devem ser criados usando o instrumental e boas práticas;
-   Para rodar os testes, utilize o comando npm run test;
-   Para visualizar a cobertura, utilize o comando npm run test:cov;

### 11. Criar um endpoint para cadastro de administradores

-   A rota deve ser (/users/admin).
-   Só será possível adicionar um admin caso esta ação esteja sendo feita por outro admin, portanto, deve ser validado se há um admin logado.
-   Por padrão, as requisições pra esse endpoint devem adicionar um usuário com a role admin.

### 12. Criar testes unitários que cubram no mínimo 60% dos arquivos

-   Os testes de integração devem ser criados na pasta ./tests
-   Os arquivos .spec.ts podem ser alterado, renomeado ou removido;
-   Os testes devem ser criados usando o instrumental e boas práticas;
-   Para rodar os testes, utilize o comando npm run test;
-   Para visualizar a cobertura, utilize o comando npm run test:cov;

### 13. Criar testes unitários que cubram no mínimo 90% dos arquivos

-   Os testes de integração devem ser criados na pasta ./tests
-   Os arquivos .spec.ts podem ser alterado, renomeado ou removido;
-   Os testes devem ser criados usando o instrumental e boas práticas;
-   Para rodar os testes, utilize o comando npm run test;
-   Para visualizar a cobertura, utilize o comando npm run test:cov;

---

---

---

# MISC

-   eslint
-   git
-   prettier
-   jest
