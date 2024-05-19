# pos-golang-cobra-cli
Repositório para as aulas referentes ao Cobra CLI


## Inicialização banco de dados

Criar a tabela no banco de dados

```bash

wander@bsnote283:~/pos-golang-cobra-cli$ sqlite3 data.db
SQLite version 3.37.2 2022-01-06 13:25:41
Enter ".help" for usage hints.
sqlite> create table categories (id string, name string, description string);
sqlite> 

```


# Anotações
O Cobra CLI tem uma integração nativa com o Viper

Instalar a última versão:

```bash

go install github.com/spf13/cobra-cli@latest

```

Para testar a instalação, basta executar o comando `cobra-cli` diretamente no shell e o help será exibido.

Após a instalação, podemos realizar a inicialização do projeto através do comando `cobra-cli init`.Será criado o arquivo `main.go` e pasta `cmd`, onde também será criado o arquivo `root.go`. 

Também é gerado um arquivo de licença vazio. A licença pode ser informada por parâmetro.
 
O Cobra tem três elementos principais:

- A chamada de execução

- O Comando

- Flags para inicalização


O comando principal é o rootCmd, que fica no arquivo root.go. A função init inicializa o comando e adiciona as flags.

Todo comando adicionado é adicionado ao rootCmd. Para adicionar um comando, basta executar:

```bash

wander@bsnote283:~/pos-golang-cobra-cli$ cobra-cli add ping
ping created at /home/wander/pos-golang-cobra-cli
wander@bsnote283:~/pos-golang-cobra-cli$ 


```
Será criado o arquivo ping.go dentro da pasta cmd. Além de adicionar ao rootCmd, também será adicionado ao help. Abaixo segue o exemplo da execução do arquivo main.go:

```bash

wander@bsnote283:~/pos-golang-cobra-cli$ go run main.go 
A longer description that spans multiple lines and likely contains
examples and usage of using your application. For example:

Cobra is a CLI library for Go that empowers applications.
This application is a tool to generate the needed files
to quickly create a Cobra application.

Usage:
  pos-golang-cobra-cli [command]

Available Commands:
  completion  Generate the autocompletion script for the specified shell
  help        Help about any command
  ping        Descrição curta do comando ping

Flags:
  -h, --help     help for pos-golang-cobra-cli
  -t, --toggle   Help message for toggle

Use "pos-golang-cobra-cli [command] --help" for more information about a command.
wander@bsnote283:~/pos-golang-cobra-cli$ 
wander@bsnote283:~/pos-golang-cobra-cli$ 
wander@bsnote283:~/pos-golang-cobra-cli$ go run main.go ping
Comando ping executado!
wander@bsnote283:~/pos-golang-cobra-cli$ 



```

A opção completion ajuda a gerar o autocomplete para o shell. Será gerado um script (bash, powershell, zsh) para habilitar no seu ambiente. 


Importar na aplicação:

```bash

import "github.com/spf13/cobra"

```



go mod init github.com/wandermaia/pos-golang-cobra-cli

## Referências

Repositório Cobra CLI

https://github.com/spf13/cobra