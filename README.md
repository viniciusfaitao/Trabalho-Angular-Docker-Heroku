# Integrantes do grupo e Informações
• João Paulo Nunes Pereira (201610658) <br/>
• Luan Martins Correa (202023809) <br/>
• Nicolas Prates Anacleto (201816957) <br/>
• Thailon dorneles (202014087) <br/>
• Vinicius Faitão (202065022) <br/>

### Processos e tecnologias utilizadas:
• ReactApp. :heavy_check_mark: <br/>
• Docker CLI e Docker Desktop. :heavy_check_mark: <br/>
• Heroku CLI. :heavy_check_mark: <br/>
• Versionamento em repositório público (Github). :heavy_check_mark: <br/>
• Instruções para rodar o projeto (README). :heavy_check_mark: <br/>

### Matéria e professor:
• Práticas de Engenharia de Software <br/>
• Jean Paul Fonseca Lopes

### Fontes:
• https://developer.okta.com/blog/2020/06/24/heroku-docker-react

### Comandos criados no package.json que serão utilizados no tutorial a seguir:

```
 "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "docker-build": "docker build -t trabalhordh .",
    "docker-run": "docker run -p 3000:80 trabalhordh",
    "docker-tag": "docker tag trabalhordh registry.heroku.com/trabalhordh/web",
    "docker-push": "docker push registry.heroku.com/trabalhordh/web",
    "heroku-login": "heroku login",
    "heroku-create": "heroku create trabalhordh",
    "heroku-container-login": "heroku container:login",
    "heroku-container-release": "heroku container:release web --remote heroku",
    "heroku-open": "heroku open --remote heroku"
  },
```

### Necessario para funcionamento
- <a href=“https://devcenter.heroku.com/articles/heroku-cli#download-and-install“>Heroku CLI</a>
- <a href=“https://docs.docker.com/get-docker/“>Docker</a>


```
Não é necessario utilizar o comando NPM INSTALL após clonar o repositório pois é feito o build da aplicação 
quando o docker criar a imagem. 
```

# Criando imagem e subindo container com docker

### `git clone https://github.com/viniciusfaitao/Trabalho-React-Docker-Heroku.git`
- Faça clone do repositório

### `1 - Execute npm run docker-build`
- Ao executar será buildado a aplicação e criada uma imagem chamada trabalhordh

### `2 - Execute npm run docker-run`
- Ao executar será iniciado um container em localhost na porta 3000 com a imagem trabalhordh

### `3 - Entre na url http://localhost:3000/`
- Nesta url voce verá a aplicação rodando corretamente


# Hospedando a imagem criada no heroku


### `1 - Execute npm run heroku-login`
- Ao executar irá logar no ambiente do heroku, repare no seu cmd que é necessario clicar qualquer tecla quando for solicitado e irá 0abrir o heroku no seu browser, faça o login, após retorne ao cmd e verá que receberá um retorno de login com sucesso.

### `2 - Execute npm run heroku-container-login`
- Ao executar irá logal no container do heroku e voce receberá um retorno no proprio cmd escrito "Login Succeeded".

### `3 - Execute npm run heroku-create`
- Ao executar será criada uma nova aplicação no heroku chamada trabalhordh, voce poderá acompanhar o processo pelo seu cmd e no retorno receberá a url do git do heroku e a url já acessivel, porem apenas com a mensagem "Welcome to your new app", ainda aguardando subir algo.

### `4 - Execute npm run docker-tag`
- Ao executar será feito um registro da imagem e já subira o container automaticamente, voce pode verificar executando no cmd o comando "docker images".

### `5 - Execute npm run docker-push`
- Ao executar será feito envio da imagem

### `6 - Execute npm run heroku-container-release`
- Ao executar será feito deploy e hospedará a imagem no heroku, voce pode verificar que o seu site já estará funcionando se entrar no link https://trabalhordh.herokuapp.com/ ou se executar o proximo passo do tutorial.

### `7 - Execute npm run heroku-open`
- aqui abrirá o ambiente do heroku automaticamente no seu browser.
