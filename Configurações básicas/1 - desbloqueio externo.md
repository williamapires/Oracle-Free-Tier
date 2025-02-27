# 1. Instale a versão ubuntu mais recente
- Sempre que for criar uma nova VM, crie com ubuntu (mais recente) que não tem erro.
- Depois de criar, baixe as chaves ssh para logar na maquina. o passo a passo para consegui isso é o seguinte:
  ```
  # De as permissões necessárias para sua key:

  chmod 400 <private_key_file>
  ```
  Depois das permissões, para fazer o login na VM:
  ```
  ssh -i <private_key_file> ubuntu@<public-ip-address>

  ```

  # 2. Abra a conexão externa
  - Para abrir a conexão externa, segue o comando: (faça isso depois de atualizar o sistema).
    ```
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT

    #logo em seguida:

    sudo netfilter-persistent save

    ```
    Com essas configuraçôes vamos consguir acessar de qualquer lugar a VM.
