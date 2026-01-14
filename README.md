# Lab-Introducao-ao-Linux

Introdução a uma imagem de máquina da Amazon (AMI) no Amazon Linux
Este laboratório reforçará seu conhecimento sobre a funcionalidade básica da interface de linha de comando e fornecerá uma base sólida a partir da qual você pode continuar a aprender sobre novos comandos e recursos dentro dos shell do Linux.

 

Duração
A duração do laboratório é de aproximadamente 30 minutos.

 

Restrições de serviço da AWS
Neste ambiente de laboratório, o acesso aos serviços e às ações de serviço AWS pode ser restrito aos que forem necessários para concluir as instruções do laboratório. Você poderá encontrar erros se tentar acessar outros serviços ou executar ações além das que este laboratório descreve.

 

Cenário
Neste laboratório, você usará o Secure Shell (SSH) para acessar uma imagem de máquina da Amazon (AMI) no Amazon Linux dentro dos laboratórios Vocareum. Em seguida, você usa o comando man para acessar as man pages.

Objetivos
Depois de concluir este laboratório, você será capaz de:

Usar o SSH para acessar uma AMI do Amazon Linux dentro dos laboratórios Vocareum.

Entender a finalidade do comando man.

Demonstrar o atributo de busca das man pages.

Examinar os cabeçalhos das man page.

Os seguintes componentes são criados para você como parte do ambiente de laboratório:

Amazon Elastic Compute Cloud – Host de comando (na sub-rede pública): você faz o login nesta instância para usar os comandos listados neste laboratório.

A seguir estão listados outros componentes deste laboratório. Mais adiante neste curso, você examinará esses componentes.

Sub-rede pública

Amazon Virtual Private Cloud (Amazon VPC)

 

Acesso ao Console de Gerenciamento da AWS
Na parte superior destas instruções, selecione Start Lab (Iniciar laboratório) para iniciar o laboratório.
Um painel Iniciar laboratório é aberto com o status do laboratório.

Dica: se você precisar de mais tempo para concluir o laboratório, selecione novamente o botão Iniciar laboratório para reiniciar o cronômetro do ambiente.

Aguarde a mensagem Lab status: ready (Status do laboratório: pronto) ser exibida e, depois, feche o painel Iniciar laboratório clicando em X.

Na parte superior destas instruções, selecione AWS.
O Console de Gerenciamento da AWS abrirá em uma nova guia do navegador. O sistema fará o login automaticamente.

Dica: se uma nova guia não for aberta, você verá um banner ou um ícone na parte superior do navegador com uma mensagem informando que o navegador está impedindo que o site abra janelas pop-up. Clique no banner ou ícone e selecione Allow pop ups (Permitir pop-ups).

Organize a guia do Console de Gerenciamento da AWS para que ela seja exibida junto com essas instruções. De preferência, deixe as duas guias do navegador abertas para acompanhar mais facilmente as etapas do laboratório.

 

Tarefa 1: Usar SSH para se conectar a uma instância do Amazon Linux EC2
Nesta tarefa, você se conectará a uma instância do EC2 do Amazon Linux. Você usará um utilitário SSH para realizar todas essas operações. As instruções a seguir variam um pouco, dependendo de você usar Windows ou Mac/Linux.

 Usuários de Windows: como usar SSH para conexão
 Estas instruções são especificamente para usuários de Windows. Se estiver usando macOS ou Linux, vá para a próxima seção.

Selecione o menu suspenso Detalhes acima das instruções que você está lendo no momento e selecione Exibir. Uma janela Credentials (Credenciais) será exibida.

Selecione o botão Download PPK (Baixar PPK) e salve o arquivo labsuser.ppk.
Normalmente, o navegador o salva no diretório Downloads.

Anote o endereço do PublicIP.

Em seguida, saia do painel Detalhes com um clique no X.

Baixe o PuTTY para SSH na instância do Amazon EC2. Se você não tiver o PuTTY instalado no computador, baixe-o aqui.

Abra o putty.exe.

Configure sua sessão PuTTY seguindo as instruções do link a seguir: Conectar-se à instância do Linux usando PuTTY

Usuários de Windows: clique aqui para avançar para a próxima tarefa.


 

Usuários do macOS e Linux 
Estas instruções são especificamente para usuários de Mac/Linux. Se você for usuário do Windows, avance para a próxima tarefa.

Selecione o menu suspenso Detalhes acima das instruções que você está lendo no momento e selecione Mostrar. Uma janela Credentials (Credenciais) será exibida.

Clique no botão Download PEM (Baixar PEM) e salve o arquivo labsuser.pem.

Anote o endereço do PublicIP.

Em seguida, saia do painel Detalhes com um clique no X.

Abra uma janela do terminal e altere o diretório cd para o diretório no qual foi baixado o arquivo labsuser.pem. Por exemplo, se o arquivo labuser.pem tiver sido salvo no diretório Downloads, execute este comando:

cd ~/Downloads
Altere as permissões na chave para que se tornem somente leitura executando este comando:

chmod 400 labsuser.pem
Execute o comando abaixo (substitua <public-ip> pelo endereço PublicIP que você copiou anteriormente).
Como alternativa, retorne ao console do Elastic Compute Cloud e selecione Instâncias. Marque a caixa ao lado da instância com a qual você quer se conectar e, na guia Descrição, copie o valor de IPv4 Public IP (IP público IPv4).

ssh -i labsuser.pem ec2-user@<public-ip>
Digite yes na solicitação para permitir a primeira conexão ao servidor SSH remoto.
Como você está usando um par de chaves para autenticação, não será necessário fornecer uma senha.


Tarefa 2: Exercício – Explorar as man pages do Linux
Neste exercício, você usará um terminal bash para visualizar o sistema de ajuda padrão do Linux. Este sistema geralmente é denominado páginas do manual (ou man pages).

Para abrir as páginas do manual para o programa man, digite o seguinte comando na janela do terminal PuTTY e pressione Enter:

man man
A janela do terminal, no prompt de comando, mostrará o resultado do comando man man. 

Figura: no prompt de comando, o comando man man foi inserido.

 

Para identificar as principais seções das man pages, examine os cabeçalhos no terminal (como mostra a figura a seguir).

Observação: você pode se movimentar nas man pages pressionando as teclas de seta para cima e para baixo.

Estes são alguns dos cabeçalhos importantes da man page. (Esta lista não é completa.):

NAME (NOME)

SYNOPSIS (SINOPSE)

DESCRIPTION (DESCRIÇÃO)

OVERVIEW (VISÃO GERAL)

EXAMPLES (EXEMPLOS)

FILES (ARQUIVOS)

OPTIONS (OPÇÕES)

SEE ALSO (VEJA TAMBÉM)

<img width="705" height="432" alt="image" src="https://github.com/user-attachments/assets/b1f8bf00-7715-4b61-a72c-e78d26e17674" />


Figura: a man page exibe informações importantes sobre um comando. 

Tome nota do cabeçalho DESCRIPTION (DESCRIÇÃO), particularmente os números de seção.

<img width="967" height="435" alt="image" src="https://github.com/user-attachments/assets/17c3706e-9ffc-45da-918a-d250cdfec6b3" />

O cabeçalho DESCRIPTION (DESCRIÇÃO) contém uma visão geral de um comando.

Para sair das man pages, digite q

Laboratório concluído 
 Parabéns. Você concluiu o laboratório.

Selecione End Lab (Encerrar laboratório) na parte superior desta página e selecione Yes (Sim) para confirmar que você deseja encerrar o laboratório.
Um painel será exibido com a mensagem: "DELETE has been initiated... You may close this message box now." ("A EXCLUSÃO foi iniciada... Você pode fechar esta caixa de mensagem agora.")

Clique no X no canto superior direito para fechar o painel.
