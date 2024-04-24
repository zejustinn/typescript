# TypeScript
É um superset do JavaScript o que significa que nao e uma linguagem construida do zero mas sim uma linguagem construida em cima do JavaScript e que adiciona novas funcionalidades a ele
Ele funciona como um compilador de codigo JavaScript ou seja ele e utilizado para gerar codigo JavaScript

## Types
Tipo      | Exemplo                           | Valores aceitos
----------|-----------------------------------|-------------------------------------------------------------------------------------|
number    | 1, 53., -10                       | Abrange todos os numeros sem diferenciacao entre inteiros ou com ponto flutuante
string    | 'Exemplo', "Exemplo", \`Exemplo\` | Todos os textos
boolean   | true, false                       | Apenas true ou false
object    | { idade: 30 }                     | Qualquer objeto JavaScript, ou objetos mais especificos
Array     | [1, 2, 3]                         | Qualquer array JavaScript, pode possuir qualquer tipo(flexible) ou apenas 1(strict)
Tuple     | [1, 2]                            | Um array de tamanho fixo
Enum      | enum { NOVO, VELHO }              | Valores enumerados em constates globais
any       | *                                 | Qualquer tipo de valor
undefined | let variable;                     | É o valor de uma variavel nao definida e representa a ausencia de valor
null      | let variable = null;              | Tambem é uma representacao de ausencia de valor
Function  | function exemplo(): void {}       | Tipo dado a uma variavel que é um ponteiro para uma funcao
unknown   | let variable: unknown;            | Um tipo que forca uma conversao explicita para seu tipo correto
never     | function exemplo(): never {}      | Tipo usado para evitar o uso do resultado de uma funcao que nao tem resultado

### Union type 
É utilizado para informar que podemos armazenar mais de um tipo de valor. Isso pode ser utilizado com o simbolo '|'

Exemplo: 
```typescript
let example: number | string;
example = 30;
example = 'name';
example = false; // ERRO!
```

### Literal type
É utilizado para informar os valores especificos aceitos pela variavel

Exemplo: 
```typescript
let example: 'value1' | 'value2';
example = 'value1';
example = 'name'; // ERRO!
```

### Custom types ou Types aliases
É utilizado para declarar tipos e os poder os reutilizar

Exemplo: 
```typescript
type ExampleType = number | string;

let example: ExampleType;
example = 30;

let example: ExampleType;
example = 'Pedro';
```

### Function types
É utilizado para declarar um formato especifico de uma funcao que ira ser armazenada em uma variavel

Exemplo: 
```typescript
function adicionar(numero1: number, numero2: number) {
    return numero1 + numero2;
}

function concatenar(palavra1: string, palavra2: string) {
    return palavra1 + palavra2;
}

let futuraFuncao = (a: number, b: number) => number;
futuraFuncao = adicionar;
futuraFuncao = concatenar; // ERRO!
```

## Commands
### Watch mode
Utilizando o comando "tsc <file> --watch" o codigo do arquivo em questao vai ser recompilado automaticamente sempre que haver mudancas

### init
Utilizando o comando "tsc init" sera gerado um arquivo de configuracao do qual indicara que o projeto é escrito em TypeScript, assim quando o comando "tsc --watch" todos os aquivos do diretorio serao recompilado automaticamente
O arquivo gerado pode ser alterado para configurar o compilador da maneira que melhor agradar os desenvolvedores e o mesmo deve ser gerado no diretorio inicial do projeto

## Settings
### exclude
Adicionando a opcao "exclude" faz com que no momento da compilacao alguns arquivos ou diretorios possam ser excluidos

### include
Adicionando a opcao "include" apenas os arquivos nela descritos serao compilados, automaticamente ignorando todos os outros

### Compiler options
#### target
Especifica qual versao do JavaScript tu quer que o codigo seja gerado. Versoes mais antigas do JavaScript garantem que versoes mais antigas de navegadores suportem o codigo

#### declaration and declarationMap
Sao opcoes utilizadas para criar bibliotecas utilizadas por outras pessoas e ajuda na criacao de um arquivo de manifesto que descreve todos os tipos que tu tem no projeto

#### sourceMap
Gera arquivos .js.map que permitem o uso do debug dos arquivos em TypeScript diretamente no navegador 

#### noEmitOnError
Evita que o compilador gere os arquivos em JavaScript caso exista algum error

