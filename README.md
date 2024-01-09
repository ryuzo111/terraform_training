## 補足

- key pair 作成時に実行したコマンド

```
ssh-keygen -t rsa -b 2048 -f tastylog-dev-keypair
```

- tf.state ファイル共有ように s3 バケットを作成する

- 作成済み環境のリソース一覧を確認

```
terraform state list
```

- 指定されたリソースの詳細情報を確認

```
terraform state show <リソース名>
terraform state show aws_instance.app_server
```

- 指定されたリソース詳細を移動(名前を変更)

```
terraform state mv <移動元リソース名> <移動先リソース名>
```

- 現状の aws リソースを取り込む 指定されたリソース詳細を移動

```
terraform import <取り込みたいリソース名> <取り込みたい稼働中のリソースID>
terraform import aws_instance.test i-0000000000
```

- terraform 管理外にする方法

```
// コードを削除する

terraform state rm <対象外にしたいリソース名>
```

- コンソール上で手作業した内容を反映させる方法 (tfstate を最新化)

```
terraform refresh
terraform apply -auto-approve
```
