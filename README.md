# MaximusTeste

Boa tarde a todos.
Para a utilização desse código devemos focar no uso de duas partes principais. devemos iniciar a api do c# juntamente com o frontend desenvolvido em react.

Uma consideração importante é que o banco de dados conectado ao código se encontra no localhost porta 5432 database postgres com senha zanini, caso isso se diferencie do seu banco local será necessário fazer estas configurações primarias no appsettings.json

após isso devemos rodar o script para adiconarmos o schema com todas as tarefas no nosso banco de dados. Por fim será necessário atualizar os modulos do react para garantir que tudo rode bem. Com essas considerações feitas é possível darmos inicio ao uso do código.

## Tela de Login

A primeira tela apresenta representa quatro botões que permitem o usuário escolher sua ação, no caso adicionar, editar, excluir ou visualizar os clientes.

### Adicionar os clientes
Para adicionar um cliente novo é requisitado que o usuario informe o nome completo, data de nascimento, cpf e email do usuario.
Não sera permitido a requisição de adicionar um novo usuario sem os campos de email, data de nascimento e CPF.
Com o envio nosso código em C# ira verificar se o CPF informado é valido, caso seja ele ira fazer uma requisição ao banco de dados que verificara se já existe algum cpf ou email igual ao informado já cadastrado. Em caso positivo ira retornar um aviso que não é possível realizar o cadastro e caso positivo ira ser informado que o cadastro é realizado

## Editar Clientes e Excluir
Para editar os clientes, em um primeiro momento é requisitado que o usuario informe o cpf do usuario apresentado. Caso seja um cpf que se consta no banco de dados é possibilitado que o usuario faça as alterações que desejar. O mesmo vale para exclusão.
Ao excluir um usuario ou finalizar a venda não excluimops de verdade apenas modificamos seu status de inativo e de pago respectivamente. Dessa forma fica possível seguir fazendo buscas e trabalhando com os dados que já foram apresentados até então. Também não é possível excluir clientes que ainda possuem dividas ativas.
