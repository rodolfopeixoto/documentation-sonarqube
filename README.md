# SONARQUBE DOCUMENTATION FOR DOCKER COMPOSE

O sonarqube é uma ferramenta "continuous code quality", onde faz algumas verificações como: CODE SMELLS, BUG E VULNERABILIDADE.

Linguagens suportadas:
 - C/C++
 - JavaScript
 - C#
 - Java
 - COBOL
 - TypeScript
 - PL/SQL
 - PHP
 - ABAP
 - T-SQL
 - VB.NET
 - VB6
 - Python
 - RPG
 - Flex
 - Objective-C
 - Swift
 - Web (HTML included in JSP, JSF, etc. pages )
 - XML 


Versão do Projeto 7.0
================

ATENÇÃO

---------------------

Caso, você pense em criar o projeto a partir do sistema de tour do sonarqube, basta você ir no icone ( ? ) ao lado da barra de busca, clicar na opção **Tutoriais** e em **Analyze a new project**


Configuração inicial

---------------------

Clone o repositório e acesse a pasta do projeto, no terminal:

```
docker-compose up
```
Aguarde o docker baixar as imagens e toda configurar ser feita, esse processo, poderá demorar em torno de 3 à 7 minutos.

Para acessar o sistema, após a inicialização do sistema, acesse: **localhost:9000**

**Login:** admin

**Senha:** admin

Documentação
----------------------

O sonarqube utiliza comandos diferentes para as diferentes formas de execução de código, como por exemplo: Java, C# ou VB.NET ou (Other [ JS, Python, PHP, Swift e etc... ] )

Para utilizar o sonarqube com Java, basta criar o projeto seguindo a criação do token, projeto key e selecionar o tipo de análise, se será com o Java, C#/VB.NET ou qualquer outra linguagem suportada pelo sonarqube. Todos os comandos abaixo, será mostrado com os comandos Linux, ao instalar o sonarqube, você terá acesso a um sistema para auxiliar na criação e execução do projeto.

Com a linguagem Java e o Maven, você poderá utilizar o comando abaixo:

```
mvn sonar:sonar \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=7606f36b936d0f83f08be1378c6a10ccf10ffc7c
```

Para utilizar o Java com o Gradle basta efetuar as configurações abaixo:

 1 - Vá ao seu arquivo build.gradle e declare o seguinte código

```
plugins {
  id "org.sonarqube" version "2.6"
}
```

No terminal execute o código abaixo:

```
./gradlew sonarqube \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=7606f36b936d0f83f08be1378c6a10ccf10ffc7c
```

Para analisar os códigos distintos ao de cima, basta fazer o download do sonarqube scanner. Para Linux, acesse [link](https://sonarsource.bintray.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-3.0.3.778-linux.zip).

Descompacte o arquivo, por exemplo: /home/carlos/Downloads , renomear sonar-scanner-cli-3.0.3.778-linux  para sonarscanner.
Utilizaremos esse arquivo, na pasta do projeto e assim, poderemos executar o comando abaixo, porém você deverá verificar qual o caminho, em que descompactou o sonnar scanner. Use o comando pwd para verificar qual o caminho.

**OBS:** É válido lembrar que em projectKey e login, você deverá adicionar suas informações, caso siga o passo a passo do **Analyze a new project** basta copiar e colocar, exceto na parte do sonar-scanner, caso não tenha adicionado o arquivo com **PATH** bin in linux.

```
pwd

# /home/rodolfogpeixoto/Documentos/cubo/projeto
```

Tendo o caminho você poderá executar o comando da seguinte forma:

```

/home/rodolfogpeixoto/Downloads/sonarscanner/bin/sonar-scanner \
  -Dsonar.projectKey=codemca \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=255d0df1a329e49f96f71f8662e8994a288d2f6a

```

### Links diretos

Desenvolvimento
---------------------
-   [Rodolfo Peixoto](http://www.rodolfopeixoto.com.br)
