# テーブル設計

## users テーブル

| Column        | Type    | Options                  |
|---------------|---------|--------------------------|
| email         | string  | null: false, unique:true |
| encrypted     | string  | null: false              |
| name          | string  | null: false              |
| profile       | string  | null: false              |
| occupation    | text    | null: false              |
| position      | text    | null: false              |

- has_many :prototypes
- has_many :comments


##　prototypes テーブル

| Column       | Type      | Options                         |
|--------------|-----------|---------------------------------|
| title        | string    | null: false                     |
| catch_copy   | text      | null: false                     |
| concept      | text      | null: false                     |
| user         | reference | null: false, foreign_key: true  |

- has_many :comments
- belong_to :user

## comments テーブル

| Column       | Type      | Options                        |
|--------------|-----------|--------------------------------|
| content      | text      | null: false                    |
| prototype    | reference | null: false, foreign_key: true |
| user         | reference | null: false, foreign_key: true |

- belong_to :user
- belong_to :prototype

