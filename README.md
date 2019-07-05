# DB設計

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|encrypted_password|string|null: false|
|reset_password_token|string||
|reset_password_sent_at|datetime||
|remember_created_at|datetime||

### Association
- has_many :tweets
- has_many :comments

## tweetsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string||
|text|text||
|image|text||

### Association
- belongs_to :user
- has_many :comments

## commentsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer||
|tweet_id|integer||
|text|text||

### Association
- belongs_to :user
- belongs_to :tweets