# **docker**

## **namespace**
**namespace** - isola processos, processo pai e processos filhos

**namespace consegue isolar:**
- pid
- utilizadores
- redes
- sistema de ficheiros

**processos** - o processo com o pid 100 tem o container 1 em execução, todos os processos do container são subprocessos do processo pai com o pid 100

**container** - é um processo isolado em execução com subprocessos que consegue "simular" um sistema operativo

<br>

---

## **cgroups**
**cgroups** - controla recursos atribuídos ao container

**cgroups consegue isolar:**
- recursos disponíveis da máquina
- memoria
- cpu
- disco

<br>

---

## **overlay file system**
**overlay file system OFS** - trabalhar com camadas, ou layers. é um sistema de arquivos de sobreposição

[OverlayFS - Wikipedia](https://en.wikipedia.org/wiki/OverlayFS) - sobrepõem uma partição de leitura/gravação sobre uma partição somente leitura, como LiveCDs e dispositivos IoT com ciclos de gravação de memória flash limitados

[Overlay Filesystem - The Linux Kernel documentation](https://docs.kernel.org/filesystems/overlayfs.html) - arquivos de sobreposição, um sistema de arquivos de sobreposição tenta apresentar um sistema de arquivos que é o resultado da sobreposição de um sobre o outro, às vezes chamado de sistemas de arquivos de união

<br>

---

## **imagens**
**imagens** - são árvores de dependências. conjunto de dependências dependências numa árvore. **imagens são imutáveis**

**nome das imagens:**
- mysql:latest (latest)
- mysql:8.0.31 (versão 8.0.31)

<br>

---

## **dockerfile**
**dockerfile** - é uma receita criada a partir de uma imagem já existente que serve para construir uma nova imagem, modificada com as minhas alterações. o resultado final é sempre imutável. teria de construir outra imagem caso necessitasse de alterar alguma coisa. Dockerfile

```dockerfile
FROM: nome_da_imagem
RUN: comandos que necessito executar em cima da imagem original. apt install
EXPOSE: PORTA exposta para a máquina host
```

**dockerfile** -> build (gera) -> **imagem** -> run -> **container**

**imagem 1** -> altera o conteiner -> **commit** -> **imagem 2**
<br>

---

## **container**
**camadas de um container:**
- **processo**
- **imagem**
- **camada de leitura e escrita** que permite entrar dentro do container e escrever. *atenção que não é dentro da imagem é dentro do container. quando o container é destruído todas as alterações feitas dentro do container são apagadas*





