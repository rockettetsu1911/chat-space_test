# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
## usersテーブル
|Column|Type|Options|
|------|----|-------|
｜name｜text|null: false,
|email|string|null: false, 
|password|string|null: false

### Association
- has_many :groups
- has_many :comments
- has_many :messages


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
｜name｜text|null: false,
| member|string|
|comment|

### Association
- has_many: users
- has_many: comments

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :tweet
- belongs_to :user