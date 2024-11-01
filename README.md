# Sistema de Controle e Gerenciamento de Ordens de Serviço <br><br>
Este projeto é um sistema de controle e gerenciamento de ordens de serviço para uma oficina mecânica. O objetivo é fornecer uma solução que facilite o registro, acompanhamento e gerenciamento de ordens de serviço, desde a entrada dos veículos até a conclusão dos serviços. <br><br>

## Funcionalidades

- Cadastro de Clientes: Permite o registro de informações dos clientes, incluindo nome, endereço e telefone de contato.
- Gerenciamento de Veículos: Cada cliente pode cadastrar múltiplos veículos, incluindo detalhes como modelo, placa e ano.
- Registro de Mecânicos: Cadastro de mecânicos, incluindo informações como nome, endereço e especialidade.
- Emissão de Ordens de Serviço (OS): Geração de ordens de serviço, registrando data de emissão, valor total, status e data de conclusão. Cada OS é vinculada a um veículo e a um mecânico responsável.
- Gerenciamento de Serviços: Permite a inclusão de vários serviços em uma única ordem de serviço, consultando uma tabela de referência para calcular o custo.
- Registro de Peças: Cadastro de peças utilizadas nos serviços, permitindo que cada OS contenha múltiplas peças e serviços. <br><br>


# Estrutura do Banco de Dados <br><br>
O banco de dados é estruturado com as seguintes tabelas:<br><br>

## Clientes

- id_cliente
- nome
- endereco
- telefone
- Veículos

## Veículos

- id_veiculo
- modelo
- placa
- ano
- id_cliente (FK)
- Mecanicos

## Mecânicos

- id_mecanico
- nome
- endereco
- especialidade
- Ordens_de_Serviço

## Ordem de Serviço
- id_os
- data_emissao
- valor_total
- status
- data_conclusao
- id_veiculo (FK)
- id_mecanico (FK)
- Serviços


# Serviços
- id_servico
- descricao
- custo

## Peças
- id_peca
- descricao
- valor

  
### OS_Servicos (tabela de junção)

- id_os (FK)
- id_servico (FK)
- quantidade
- PRIMARY KEY (id_os, id_servico)

  
### OS_Pecas (tabela de junção)

- id_os (FK)
- id_peca (FK)
- quantidade
- PRIMARY KEY (id_os, id_peca)

  
## Tecnologias Utilizadas
Mysql Workbench
