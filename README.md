## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |


### Association

- has_many :comments
- has_many :prototypes, through: comments

## prototypes テーブル

| Column      | Type       | Options     |
| ----------- | ---------- | ----------- |
| title       | string     | null: false |
| catch_copy  | string     | null: false |
| concept     | text       | null: false |
| image       |            |             |
| user        | refarences | null: false |


### Association

- belongs_to :users
- has_many :users, through: comments
- has_many :comments


## comments テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| text        | text       | null: false                    |
| user        | references | null: false, foreign_key: true |
| prototype   | references | null: false, foreign_key: true |

### Association

- belongs_to :users
- belongs_to :prototypes