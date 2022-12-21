## usersテーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| mail               | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association

- has many: prototypes
- has many: comments

## prototypesテーブル

| Column     | Type      | Options                        |
| ---------- | ----------| ------------------------------ |
| title      | string    | null: false                    |     
| catch_copy | text      | null: false                    |
| concept    | text      | null: false                    |
| user       | reference | null: false, foreign_key: true |

### Association

- belongs_to : users 
- has many: comments

## commentsテーブル

| Column     | Type      | Options                        |
| ---------- | ----------| ------------------------------ |
| content    | text      | null: false                    |     
| prototype  | reference | null: false  foreign_key: true |
| user       | reference | null: false, foreign_key: true |

### Association

- belongs_to : users
- has many: prototype 
