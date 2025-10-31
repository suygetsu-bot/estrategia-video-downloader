# estrategia-video-downloader
Automação de download/salvamento de aulas com Python + Selenium (Edge)


## Passo a Passo

### 1. Criar as pastas

Execute o **PowerShell como Administrador** e cole:

```
mkdir C:\estrategia
cd C:\estrategia
mkdir downloads
mkdir driver
```

C:\estrategia → raiz do projeto

C:\estrategia\downloads → onde os vídeos vão cair

C:\estrategia\driver → onde vamos colocar o msedgedriver.exe


OBS.: Você pode alterar o destino do arquivo, se assim desejar.


### 2. Instalar as libs Python
Ainda no PowerShell:

```
pip install selenium requests
```
Se der erro de permissão, tente rodar com:
```
py -m pip install selenium requests
```


### 3. Baixar o msedgedriver.exe
Abra o Edge → clique onde tem 3 pontinhos no canto superior direito → Ajuda e comentários → Sobre o Microsoft Edge → anote a versão (ex.: 141.x.x).

Baixe o WebDriver da mesma versão (site da Microsoft → Edge WebDriver). → https://developer.microsoft.com/pt-br/microsoft-edge/tools/webdriver

Salve o arquivo em:
```
C:\estrategia\driver\msedgedriver.exe
```
O script já está apontando pra esse caminho.


### 4. Criar o script
Crie um arquivo chamado:
```
C:\estrategia\estrategia_download_edge_any.py
```
e cole o código que está nesse link aqui 👇:

https://gist.github.com/suygetsu-bot/cc3e764fadc66cbf6b127f2d37b0e9f5

OBS.: Na linha de código: 
```
CURSO_URL = "https://www.estrategiaconcursos.com.br/app/dashboard/cursos/21XXXX/aulas"
```
você DEVE preencher com o link do curso desejado no espaço entre aspas (").


### 5. Definir as variáveis de ambiente (login + pasta + qualidade opcional)

No PowerShell:
```
cd C:\estrategia
$env:ESTRATEGIA_EMAIL = "seu-email-aqui"
$env:ESTRATEGIA_PASSWORD = "sua-senha-aqui"
$env:DOWNLOAD_DIR = "C:\estrategia\downloads"
# opcional:
# $env:ESTRATEGIA_QUALITY = "720p"
```


PREENCHA NO CÓDIGO ACIMA SUAS CREDENCIAIS (LOGIN E SENHA)!


### 6. Rodar
```
cd C:\estrategia
py .\estrategia_download_edge_any.py
```


Ele vai abrir o Edge → você faz login → volta pro PowerShell → aperta ENTER → ele começa a percorrer as aulas e baixar.



### 7. Como mudar de curso

Quer baixar outro curso lá no Estratégia?

Basta alterar apenas uma linha do código (onde está CURSO_URL): 
```
CURSO_URL = "https://www.estrategiaconcursos.com.br/app/dashboard/cursos/XXXXXX/aulas"
```
e rodar de novo.


### 8. Organização dos arquivos

Por padrão ele salva num formato idêntico ao exemplo a seguir:

Aula 00 - Vídeo 01 - Ortografia oficial.mp4

Aula 00 - Vídeo 02 - Acentuação gráfica.mp4

Aula 21 - Vídeo 03 - Parênteses.mp4

Aula 58 - Vídeo 01 - Revisão geral.mp4



Ou seja: dá pra saber qual é a aula, qual vídeo é e o nome do vídeo.



É isso, galera. Espero que ajude s2


Bons estudos!!! 📚
