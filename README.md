# Ambiente para testes em php com docker 🐋 &lt;3 🐘

- **Dockerfile**: Arquivo que contém as instruções para construir a imagem Docker.
- **app_php/**: Diretório contendo os arquivos da aplicação PHP.

## Dockerfile

O `Dockerfile` é responsável por:

1. Utilizar a imagem base do PHP com Apache.
2. Habilitar o módulo de reescrita do Apache.
3. Copiar os arquivos da aplicação PHP para o diretório padrão do Apache.
4. Ajustar permissões para o diretório da aplicação.
5. Expor a porta 80.
6. Iniciar o Apache quando o container é executado.

## Construção da Imagem
Para construir e executar a imagem Docker, execute o seguinte comando no diretório onde está o `Dockerfile`:

```bash
sudo docker build -t appphp . 

sudo docker run -d -p 8080:80 --name meu-apache-container appphp -- Sem "hot reload"
sudo docker run -d -p 8080:80 -v ~/.dev/php/app_php:/var/www/html --name containerapache appphp -- Com "hot reload"
