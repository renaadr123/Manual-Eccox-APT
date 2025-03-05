<header>

<!--
  <<< Author notes: Renato Adriano >>>
      Manual de utilização do APT.
-->

# Introduction to Git Hub Git Hub Git Hub Git HubGitHub


Guia de Utilização


Eccox Application Environment Management

for Parallel Testing

Release 2.0.6

 














Direitos de Cópia© – Eccox Software S.A. 
Todos os direitos de cópia e de distribuição são reservados.
Esta publicação contém informações confidenciais de propriedade de Eccox Software S.A. O seu uso, revelação e reprodução são proibidos sem a expressa autorização da mesma. O acesso é limitado a usuários autorizados e o uso deste produto está sujeito aos termos e condições do contrato de licença firmado com a Eccox Software S.A.
Eccox Application Environment Management for Parallel Testing
é marca comercial registrada por Eccox Software S.A.
DB2, CICS, IMS, RACF e z/OS são marcas comerciais registradas por International Business Machines Corporation (IBM).
Todas as outras companhias ou nomes de produtos mencionados são marcas de seus respectivos proprietários.
Doc. APTDC01/2025.
 
Conteúdo	

1	Sobre este Manual	13
1.1	Visão Geral	13
1.2	Como utilizar este manual	13
1.3	Onde encontrar mais informações	14
1.4	A quem se destina este manual	14
1.5	Terminologia	14
1.6	Comentários e sugestões	14
2	Acesso à interface WEB	15
2.1	Realizando LOGIN	15
2.2	Navegação na interface Web	15
3	Test Container (Create) - Criação de um novo container de teste	18
3.1	Criação de um novo plano de teste	20
4	Test Container (Browse) - Gerenciando a lista de containers via Browse	21
4.1	Visualização e edição de um container a partir da tela de browse	25
4.2	Aplicando ações em um container a partir da tela de browse	25
4.3	Duplicando um container via de tela de browse	26
4.4	Removendo um container via tela de Browse	28
4.4.1	Deletar ou restaurar totalmente um container via Recycle Bin	28
4.5	Ativando containers de teste com erro via tela de browse	29
5	Adicionando componentes no container de teste	30
5.1	Serviços buscadores	30
5.1.1	SCM Discovery	32
5.1.2	Library	35
5.1.3	Transaction	37
5.1.4	Programs	39
5.1.5	Tables	40
5.1.6	Jobs	42
5.1.7	GIT	43
5.1.8	Schedules	44
5.1.9	DLI/DB	46
5.1.10	Typing	47
5.1.11	Typing for BND File	49
5.2	Selecionando componentes encontrados pelos serviços buscadores	50
5.3	Reprocessando serviços já executados	58
5.4	Acessando e exportando logs da aba Show Requests	59
6	Gerenciando um container de teste	61
6.1	Aplicando ações a todos os componentes do container	62
6.2	Aplicando ações individualmente ou em lote por componente	64
6.3	Gerenciando a carga inicial das tabelas clones	66
6.4	Executando o processamento do container	67
6.5	Identificação de componentes clones gerados	68
6.6	Verificando a biblioteca do programa original utilizada para criação do clone de um programa	69
6.7	Aplicando um critério de redução para carga das tabelas DB2	70
6.8	Feature Alter Table de tabelas DB2	71
6.8.1	Adicionando comandos via função ALTER TABLE	71
6.8.2	Removendo comandos ALTER TABLE incluídos	74
6.9	Verificando logs de processamento de um container	74
6.9.1	Logs por componente do container	74
6.9.2	Log geral do container	74
6.10	Unique Identifier	75
6.11	SnapShot	77
6.11.1	Configurações do SnapShot	78
6.11.2	Criação de um novo SnapShot	78
6.11.3	Restaurando SnapShot	80
6.11.4	Destruindo SnapShot	81
6.11.5	Logs do SnapShot	82
6.12	Cópia de dados entre ambientes (Data Mover)	82
7	Configuration	84
7.1	Rules identifier	85
7.1.1	Cadastrando uma nova regra para um identificador único formatado	85
7.1.2	Definindo o layout para uma regra de protocolo Message	87
7.1.3	Definindo o layout para uma regra de protocolo JSON	88
7.1.4	Definindo o layout para uma regra de protocolo XML	89
7.1.5	Definindo o layout para uma regra de channel	90
7.1.6	Ativando as regras para identificadores formatados	91
7.1.7	Removendo uma regra de identificador único para uma transação	91
7.1.8	Logs de processamento de regras.	91
7.2	Applications	92
7.3	Alerts	93
8	Security	96
8.1	Profiles	96
8.1.1	Cadastrando um novo profile	96
8.1.2	Definições de um profile	97
8.2	Users	101
8.2.1	Cadastro de novos usuários	101
9	Administration	103
9.1	Show Unique Identifier	103
9.2	Display Active Unique	103
9.3	Utilization Report	104
9.3.1	Synthetic Billing Report	105
9.3.2	Analytic Billing Report	106
9.3.3	Billing Data Report	107
9.4	Dashboard	108
10	Traces	110
10.1	CICS Trace	110
10.1.1	Request Trace	110
10.1.2	Browse Trace	111
10.2	IMS Trace	112
10.2.1	Request Trace	112
10.2.2	Browse Trace	113
11	Apêndice I - Uso do APT em filas IBM MQ for z/OS	115
12	Bibliografia	116
 
Índice de Imagens	
Figura 1: Tela inicial de Login.	15
Figura 2: Tela inicial.	16
Figura 3: Opções menu lateral.	16
Figura 4: Tela de criação de um novo container de teste.	18
Figura 5: Container de teste após criação inicial.	19
Figura 6: Lista de containers cadastrados (Browse).	19
Figura 7: Pop-up de criação de um plano de teste.	20
Figura 8: Browse (lista de containers).	22
Figura 9: Duplicate de um container.	27
Figura 10: Recycle Bin.	28
Figura 11: Serviços buscadores.	30
Figura 12: Busca via Serviço Changeman®.	32
Figura 13: Incluindo e processando via serviço CHANGEMAN®.	33
Figura 14: Serviço buscador ENDEVOR ® PACKAGE.	33
Figura 15: Serviço buscador ENDEVOR® ELEMENT.	34
Figura 16: Busca via serviço LIBRARY.	36
Figura 17: Incluindo e processando via serviço LIBRARY.	36
Figura 18: Busca via serviço TRANSACTION.	37
Figura 19: Incluindo e processando via serviço TRANSACTION.	38
Figura 20: Inclusão em lote de transações.	38
Figura 21: Busca via serviço PROGRAMS.	39
Figura 22: Incluindo e processando via serviço PROGRAMS.	39
Figura 23: Inclusão em lote de programas.	40
Figura 24: Busca via serviço TABLES.	40
Figura 25: Incluindo e processando via serviço TABLES.	41
Figura 26: Inclusão em lote de tabelas.	41
Figura 27: Busca via serviço JOBS.	42
Figura 28: Incluindo e processando via serviço JOBS.	43
Figura 29: GIT Pop-up	43
Figura 30: Discovery Schedules	44
Figura 31: Busca via Discovery SCHEDULES.	45
Figura 32: Incluindo e processando via serviço SCHEDULES.	45
Figura 33: Inclusão em lote de JOBNAMES.	46
Figura 34: Busca via serviço DLI/DB.	46
Figura 35: Incluindo e processando via serviço DLI/DB.	47
Figura 36: Busca via serviço Typing.	48
Figura 37: Incluindo e processando via serviço TPYPING.	49
Figura 38: Usando o serviço TPYPING for BND File.	50
Figura 39: Requisições em Show Requests	51
Figura 40: Componentes retornados por um serviço buscador	52
Figura 41: Seleção automática de componentes	54
Figura 42: Divergence of origins identified	55
Figura 43: Browse divergences	55
Figura 44: Componentes recentemente adicionados	56
Figura 45: Lista de componentes GIT	57
Figura 46: Tela de componentes Discovery Shedule	58
Figura 47: Reprocessamento de serviços	58
Figura 48: Download lista Show Requests	59
Figura 49: Logs de usuário e sistema	60
Figura 50: Pop-up de logs de execução de um serviço buscador	60
Figura 51: Test container interface	61
Figura 52: Container Actions.	62
Figura 53: Informando diferentes ações para componentes.	65
Figura 54: Ações em lote para determinados componentes do container.	66
Figura 55: Gerenciamento de carga das bases.	67
Figura 56: Container em manutenção.	67
Figura 57: Show components clones.	68
Figura 58: Container information.	69
Figura 59: Reduction Criteria	70
Figura 60: DB2 Layout Modifier Framework.	72
Figura 61: Aplicando Alter Replace.	73
Figura 62: Test Container maintenance Logs.	75
Figura 63: Unique Identifier.	76
Figura 64: Exclusão de um identificador único.	77
Figura 65: Configuração SnapShot.	78
Figura 66: Criação de um novo SnapShot.	79
Figura 67: Pop-up de criação de SnapShot.	79
Figura 68: SnapShot Log de arquivos.	80
Figura 69: Restaurando SnapShot.	81
Figura 70: Destruindo SnapShot.	82
Figura 71: Edit Component information.	83
Figura 72: Cadastro de regras de identificadores formatados.	85
Figura 73: Pop-up de cadastro de uma nova transação para layout.	86
Figura 74: Regra de CICS Channel	87
Figura 75: Definição de layout de uma regra com protocolo message para um identificador único formatado.	88
Figura 76: Definição de layout de uma regra com protocolo JSON para um identificador único formatado.	89
Figura 77: Definição de layout de uma regra com protocolo XML para um identificador único formatado.	90
Figura 78: Definição de layout para uma Channel	91
Figura 79: Logs das regras processadas.	92
Figura 80: Applications.	92
Figura 81: Pop-up de cadastramento de aplicações.	93
Figura 82: Alerts via menu lateral.	94
Figura 83: Alertas cabeçalho.	94
Figura 84: New Profile.	96
Figura 85: Permissões Define Features.	98
Figura 86: Permissões Change Functionalities.	99
Figura 87: Usuários de um profile.	100
Figura 88: Lista de usuários cadastrados.	101
Figura 89: Pop-up de cadastro de novos usuários.	102
Figura 90: Show Unique Identifier.	103
Figura 91: Display Active Unique.	104
Figura 92: Utilization Report.	105
Figura 93: Relatório Synthetic Billing Report.	106
Figura 94: Analytic Billing Report.	107
Figura 95: Billing Data Report.	108
Figura 96: Dashboards e indicadores.	109
Figura 97: CICS Request Trace.	111
Figura 98: CICS Browse Trace.	112
Figura 99: IMS Request Trace.	113
Figura 100: IMS Browse Trace.	114
 
Índice de Tabelas	

Tabela 1: Status de um container de teste.	21
Tabela 2: Browse Container Actions.	22
Tabela 3: Funções da coluna Operations em Show Requests	51
Tabela 4: Lista de ações para componentes de um container.	62
Tabela 5: Tabela de ações para componentes.	64
Tabela 6: Definições de um profile.	97

 
1	Sobre este Manual
Este manual integra um conjunto de manuais sobre o produto Eccox Application Environment Management for Parallel Testing.
1.1	Visão Geral
O produto Eccox Application Environment Management for Parallel Testing provê tecnologia adequada para adoção de processos Agile associados ao DevOps nos quais, na esteira de entregas, a criação de containers isolados de testes proporcionam a rapidez, segurança e aderência necessárias na disponibilização de ambiente para testes de forma a atender múltiplos projetos paralelos e sem conflito. Auxilia ainda na padronização dos processos de testes de programas e de sistemas, transformando o acervo dos planos de testes em um patrimônio da empresa de forma análoga aos seus sistemas e programas.
As informações da infraestrutura dos Planos de Teste são armazenadas, retendo a inteligência da confecção desses planos, possibilitando assim automatizar a construção e limpeza da infraestrutura para execução dos Testes de aplicativos em ambiente mainframe z/OS de forma fácil e rápida.  
Através de uma arquitetura altamente flexível e configurável, permite que vários de seus processos sejam configurados sem a necessidade de alteração de seus programas e com o mínimo de intervenção possível das equipes de suporte (CICS, IMS, DBA) trazendo economia e maior agilidade nos testes. Algumas configurações inicialmente carregadas durante a instalação foram adotadas baseadas em padrões de melhores práticas de mercado. 
Os ambientes alvos para utilização do produto, normalmente são os destinados aos vários tipos de testes de aplicativos das empresas como, por exemplo, testes unitários, testes integrados ou mesmo homologação. 
1.2	Como utilizar este manual
Este manual pertence a um conjunto de manuais desenvolvidos pela Eccox Software S.A. para o produto Eccox Application Environment Management for Parallel Testing. Esse conjunto de manuais procura descrever o produto sob os aspectos de uso geral. 
1.3	Onde encontrar mais informações
Sempre que necessário, no curso do texto, este manual faz referências a outros manuais Eccox ou de terceiros através de referências bibliográficas. Veja o capítulo 12 - Bibliografia ao final deste manual para mais esclarecimentos acerca dessas referências bibliográficas.
1.4	A quem se destina este manual
Este manual especificamente destina-se a orientar os diversos perfis de usuário do produto quanto às suas necessidades no uso da interface online do produto Eccox Application Environment Management for Parallel Testing como utilizar o produto para manter as diversas entidades que o compõem, além de planejar, preparar e executar Planos e Ciclos de Teste. 
1.5	Terminologia
Para facilitar e simplificar os procedimentos contidos neste Guia de Utilização, adotaremos as seguintes terminologias: 
•	APT representa o produto Eccox Application Environment Management for Parallel Testing;
•	DB2 representa o produto IBM® DB2;
•	CICS ou CICS TS representa o produto IBM® CICS Transaction Server;
•	IMS ou IMS/TM representa o produto IBM® IMS Transaction Manager;
•	MVS representa o componente MVS do sistema operacional IBM® z/OS®;
•	MQ representa o produto IBM® MQ for z/OS®.
1.6	Comentários e sugestões
Para comentários ou sugestões sobre o produto ou sobre este manual, por favor, envie e-mail para support@eccox.com, sempre citando o produto, sua versão e release e identificando-se para possibilitar o retorno necessário.
2	Acesso à interface WEB
O acesso à interface WEB é feito via URL de acesso correspondente ao deploy realizado no servidor de aplicação. Para obter acesso à interface WEB solicite ao administrador da instalação a URL de acesso.
2.1	Realizando LOGIN
A URL de acesso à interface WEB dará acesso à tela de login do produto mostrada na Figura 1:
Figura 1: Tela inicial de Login.
 
A autenticação do login é feita via LDAP (Lightweight Directory Access Protocol), fornecendo um login único de acesso, sendo este geralmente o login utilizado para acessar a rede.
Para acessar o produto, forneça suas credências de login e senha utilizados na rede e pressione o botão ENTER.
2.2	Navegação na interface Web
Tendo realizado o login com sucesso, será exibida a tela inicial do produto mostrada na Figura 2:

Figura 2: Tela inicial.
 

Conforme mostrado na Figura 3 existem opções de navegações que são acessíveis a partir de qualquer tela no produto. 
Figura 3: Opções menu lateral.
 
As opções destacadas na Figura 3 estão detalhas abaixo:
Menu Lateral: Menu posicionado no canto esquerdo superior da tela mostrada no qual possui as opções abaixo:
OBS.: Algumas opções podem estar disponíveis ou não a depender do nível de autorização do usuário logado.
•	Test Container: Acesso as opções de criação, busca e manutenção de um container de teste. Suas opções são:
o	Create: Interface de criação de container.
o	Browse: Interface de busca, acesso e manutenção de containers cadastrados no produto
•	Configuration: Acesso as opções de configuração e manutenção de alertas, string e aplicações. 
o	Rules Identifier: Interface de criação e manutenção de regras de identificadores únicos formatados.
o	Applications: Interface de criação de sistemas.
o	Alerts: Interface de gerenciamento de alertas do sistema.
•	Security: Acesso a opções de segurança
o	Profiles: Definição de acessos e permissões por profile.
o	Users: Gerenciamento de usuários que podem acessar o produto. 
•	Administration: Acesso à administração de identificadores únicos
o	Show Unique Identifier: Exibe identificadores únicos do sistema
o	Display Active Unique: Lista apenas identificadores únicos em containers ativos.
•	CICS Trace: Acesso a definição e exibição de traces de transações CICS.
o	Request Trace: Definição de traces CICS. 
o	Browse Trace: Exibição dos trace feitos. 
•	IMS Trace: Acesso a definição e exibição de traces de transações IMS.
o	Request Trace: Definição de traces IMS. 
o	Browse Trace: Exibição dos trace feitos. 
Home: O acesso a home pode ser realizado clicando no logo sinalizado. 
Idiomas: Acesso as opções de idiomas disponíveis no sistema. 
Alertas: Acesso aos alertas do sistema.
Logout/User info: Acesso ao logout do produto e informações de perfil do usuário logado. 
 
3	Test Container (Create) - Criação de um novo container de teste
Para criar um container expanda as opções de container clicando na opção Test Container no menu lateral e em seguida acesse a opção Create para exibir a tela mostrada na Figura 4:
Figura 4: Tela de criação de um novo container de teste.
 
Para criação de um container de teste deve ser fornecido as seguintes informações:
•	Test Container Name: Descrição do container de teste.
•	Environment: Ambiente de criação do container onde será definido o ambiente principal definido para instalação.
•	Application: Sistema ou aplicação a qual o container vai pertencer. 
•	Test Plan: Plano de teste a qual o container vai pertencer. Os planos de testes são cadastrados e associados a um Environment e Application, logo a lista exibida dependerá do Environment e Application selecionados. Para detalhes de como criar um novo plano de teste verifique o capítulo 3.1 - Criação de um novo plano de teste.
Tendo preenchido as informações necessárias clique no botão CREATE NEW CONTAINER para consolidar a criação do novo container e ser direcionado para dentro do container já criado.
Figura 5: Container de teste após criação inicial.
 

Obs.: Para a figura acima, botões dos serviços buscadores podem variar conforme as features contratadas e acessos de cada usuário.
O container poderá ser acessado a qualquer momento através da função Browse presente na opção Test Container do Menu Lateral através de botões de apenas visualização ( ) ou edição ( ). Esses botões estão x’ na coluna Container Actions e são acessíveis por container. Caso deseje consultar maiores detalhes relaciona a função Browse do menu Test Container consulte maiores detalhes no capítulo 4 - Test Container (Browse) - Gerenciando a lista de containers via Browse.
Figura 6: Lista de containers cadastrados (Browse).
 

Para verificar como adicionar componentes no container acesse o capítulo 5 - Adicionando componentes no container de teste.
3.1	Criação de um novo plano de teste
Para criar um novo plano de teste as opções Test Container Name e Environment precisam estar preenchidas e em seguida o clique no botão   mostrado na Figura 4 para exibir a pop-up da Figura 7.
Figura 7: Pop-up de criação de um plano de teste.
 
 
4	Test Container (Browse) - Gerenciando a lista de containers via Browse
Os containers cadastrados no sistema são exibidos através da opção Browse do menu lateral da aplicação da sessão Test Container.
A tela de Browse oferece uma visualização dos containers do sistema possibilitando usar filtros, serviços para duplicar ou remover containers, assim como também estão disponíveis ações de processamento para o container.
Cada container possuirá um status indicando sua situação atual conforme Tabela 1.
Tabela 1: Status de um container de teste.
Ícone	Status	Descrição
 
New Container	Indica que o container foi cadastrado, porém ainda não foi realizado um primeiro processamento.
 
Container Under Maintenance
Container Under Activation
Pending Activation on Container
Pending maintenance on Container 
Container under activation
Copying data from remote environment
Generating Snapshot
Restoring data from a Snapshot  	Container em manutenção.

 
Active Container	Indica que o processamento ocorreu com sucesso e o container possui componentes ativos, ou seja, possui estruturas clones criadas no Mainframe.
 
Inactive Container	O container não possui nenhum componente ativo, ou seja, todas as estruturas clones do container foram removidos do Mainframe.
 
Container in error	Aconteceu algum erro no processamento do container. Verifique os logs de processamento para identificar o erro.

Figura 8: Browse (lista de containers).
 

As ações aplicáveis a um container estão listadas na Tabela 2 abaixo:
Tabela 2: Browse Container Actions.
Ícone	Descrição	Uso
 	View Current Container	Permite acessar o container em modo visualização não sendo possível editar ou realizar execuções no container.
 	View and edit current Container	Permite acessar o container em modo de edição possibilitando edição e realizar execuções no container. Caso deseja verificar como incluir e gerenciar componentes no container, por favor, verifique detalhes nos capítulos 5 - Adicionando componentes no container de teste e 6 - Gerenciando um container de teste 

 
Execute Component Pending Action	A ação desse botão é executar as ações presentes na coluna Pending Action para cada componente da lista aba Container preparation. 
Todo componente adicionado pela primeira vez receberá a ação New e esse botão pode ser usado para criar um componente clone equivalente ao original para uso no teste. 
Esse botão também é usado para processar outras ações parametrizadas individualmente por componente, contudo caso o valor da coluna Pending Action esteja com o valor None significa que não existe uma ação a ser feita para aquele componente.
Ao ser utilizado a partir da tela de Browse processará as ações definidas para o container da linha onde o botão foi pressionado.
Se o container estiver com todos os componentes destruídos (status Inactive Container) e você necessita recriar todos os componentes, use o botão de replace  . Caso deseje recriar apenas alguns componentes acesse o container e defina ação de replace para os componentes desejados e pressione  .
Para informações de como incluir e gerenciar componentes do container, verifique nos capítulos 5 - Adicionando componentes no container de teste e 6 - Gerenciando um container de teste.
OBS.: É necessário que existam componentes cadastrados no container para usar essa função.
 
Replace all components by a new copy	Executa a substituição dos componentes de toda o container por uma nova cópia da situação atual do componente original, ou seja, será feita a ação de Replace para todos os componentes existentes no container.
Ao ser utilizado a partir da tela de Browse realizará o Replace de todos os componentes para o container da linha onde o botão foi pressionado.
OBS.: Para containers que estão com todos os componentes destruídos (status Inactive Container) esse botão deve ser usado para recriar todos os componentes.
Para informações de como incluir e gerenciar componentes do container, verifique nos capítulos 5 - Adicionando componentes no container de teste e 6 - Gerenciando um container de teste.
OBS.: É necessário que existam componentes cadastrados no container para usar essa função.
 
Destroy all Container components	Elimina todos os componentes clones criados para o container de teste, ou seja, será feita a ação de Destroy para todos os componentes do container.
Ao ser utilizado a partir da tela de Browse realizará o Destroy de todos os componentes para o container da linha onde o botão foi pressionado.
Para informações de como incluir e gerenciar componentes do container, verifique nos capítulos 5 - Adicionando componentes no container de teste e 6 - Gerenciando um container de teste.
OBS.: É necessário que existam componentes cadastrados no container para usar essa função.
 
Duplicate a Container from a selected one	Permite duplicar um container e todos os seus componentes para um novo container. Durante a cópia é possível utilizar um plano de teste diferente do container original.
 
Delete	Remove o container da aplicação.
 
Exec comp Pending Actions with errors	Permite ativar um container que possui componentes com erro, porém os componentes com erro serão desconsiderados nos testes usando então a versão original em momento de execução. Esse botão fica disponível apenas para o container que o status indica erro.
4.1	Visualização e edição de um container a partir da tela de browse
A visualização e edição de um container são acessíveis a partir dos botões   e   conforme mostrado na Tabela 2.
A visualização permite apenas acessar as informações do container, sem edições ou qualquer tipo de processamento, seja via serviços buscadores ou processamento de ações do container.
A edição permite alterar, incluir e atualizar informações do container, assim como também consultar as informações do container.
4.2	Aplicando ações em um container a partir da tela de browse
A partir da tela de Browse é possível disparar comandos de processamento para um container especifica semelhante aos processamentos executados a partir da tela do container. Essas ações são feitas pelos botões da sessão Container Actions disponíveis na linha do container a qual se deseja efetuar a ação:
•	 : Faz o processamento das ações definidas pelos componentes na tela do container via tela a partir da tela de Browse.
•	 : Cria um novo clone a partir das versões originais definidas para todos os componentes do container.
•	 : Elimina os componentes clones criados no Mainframe, mantém os componentes cadastrados no container, porém o container fica inativado.
Caso queria consultar maiores detalhes sobre definição de ações e processamento do container verifique os capítulos 6.1 - Aplicando ações a todos os componentes , 6.2 - Aplicando ações individualmente ou em lote por componente, 6.3 - Gerenciando a carga inicial das tabelas clones e 6.4 - Executando o processamento .
4.3	Duplicando um container via de tela de browse
Um container de teste pode ser duplicado com um novo nome e pode ser mantida no mesmo plano de teste ou ser colocada em um plano de teste diferente conforme a necessidade.
Para duplicar um container, a partir da tela de Browse pressione o botão   na linha do container que deseja duplicar e a tela será redirecionada para a tela de Duplicate de container.
Figura 9: Duplicate de um container.
 
Conforme mostrado na Figura 9 será exibida uma tela com os campos Environment e Application já preenchidos em conjunto com as informações do container original que está sendo usado como base para a duplicata. 
Para concluir o processo que duplica o container preencha as informações do campo Test Container Name e Test Plan que serão usados para o novo container e em seguida escolha estre as duas opções de duplicata do container:
•	Same Source as Original Container: Todos os componentes duplicados para o novo container vão ter a mesma origem de dados do componente escolhido via duplicate.
•	Clones of Original Container: as bases de dados duplicadas serão geradas a partir da versão clone da base de dados escolhida via duplicate, porém apenas componentes ativos do outro container serão considerados por esse critério, logo caso existam bases de dados não ativas, essas bases de dados serão duplicadas para o novo container com a origem de dados das bases originais.
Para finalizar o processo clique no botão DUPLICATE CONTAINER para cadastrar um novo container com os mesmos componentes do container escolhido com base no critério de escolha gerar o novo container. Contudo, apenas os componentes serão cadastrados e esse processo não cria os componentes clones no momento de gerar a duplicata do container, logo todos os componentes serão cadastrados com a ação NEW possibilitando um novo processamento e criação de novos componentes clones para teste.
4.4	Removendo um container via tela de Browse
Um container pode ser removido da lista de containers do produto através do botão   que está na sessão Container Action da linha do container na tela de Browse. Ao clicar nesse botão o container será removido da lista do container, porém essa ação só pode ser executada para containers inativos ou novos. Esse botão fica disponível para containers que não possuem componentes clones, ou seja, container que estão nos status New Container e Inactive Container.
Quando um container é removido incialmente da lista de containers do sistema, o container é enviado para um repositório de containers removidos e poderá ser deletada definitivamente ou restaurada a partir desse repositório de containers excluídos. Para mais detalhes consulte o capítulo 4.4.1 - Deletar ou restaurar totalmente um container via Recycle Bin.
4.4.1	Deletar ou restaurar totalmente um container via Recycle Bin
Os containers removidos são enviados para um repositório de containers removidos acessível através da opção Recycle BIN do menu Test Container.
Figura 10: Recycle Bin.
 
Semelhante à tela da opção Browse possui um conjunto de botões na coluna Container Actions da lista para cada container:
•	 : Permite visualizar as informações do container em modo de visualização sem edições ou execuções de processamento e serviços buscadores.
•	 : Permite deletar definitivamente o container do produto. Um container deletado a partir dessa opção não poderá ser mais recuperado.
•	 : Permite restaurar o container para lista de containers exibidos na opção Browse.
Também localizados no canto superior da tela mostrada na Figura 10 estão localizados dois botões que permitem deletar ou restaurar todos os containers da lista da opção Recycle BIN. Caso deseje deletar todos os containers da lista exibida, pressione o botão   presente no canto superior da tela, porém caso deseje restaurar todos os containers da lista, utilize o botão  .
4.5	Ativando containers de teste com erro via tela de browse
Em alguns casos a clonagem de um componente pode vir a terminar com status de erro devido fatores externos do ambiente ou alguma instabilidade do produto.
Em casos como esse o recomendável é verificar as mensagens e tentar resolver o problema antes de seguir, contudo caso deseje-se ativar o container, o botão   situado na coluna "Container actions" para ativação do container. Use o botão relacionado a linha do container que se deseja ativar. 
OBS.: Esse botão fica disponível apenas para containers que o status indica erro.
Essa funcionalidade irá habilitar o container, desconsiderando os erros encontrados em componentes, porém os componentes com erro serão desconsiderados para uso nos testes, logo em casos de execução serão utilizados os componentes originais.
 
5	Adicionando componentes no container de teste
