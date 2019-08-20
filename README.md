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


# usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null:false,index:true|
|mail|string|null:false|
|password|string|null:false|

・ has_many :messeges
・ has_many :groups_users
・ has_many :users,through: :groups_users

#groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null:false|

・ has_many :messeges
・ has_many :groups_users
・ has_many :groups,through: :groups_users

#messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|
|image|text|
|users_id|references|null:false, foreign_key:true|
|group_id|references|null:false, foreign_key:true|

・ beiongs_to :user
・ beiongs_to :group

#groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|users_id|references|null:false, foreign_key:true|
|group_id|references|null:false, foreign_key:true|

・ beiongs_to :user
・ beiongs_to :group