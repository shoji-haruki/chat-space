# README
Name
====
chat-space

## Demo


## Overview
- user registration
- Login, Logout
- Post, edit, delete text
- Display flash message

## Description
- user registration-New registration is required to post
- Login, Logout-Menu changes when logging out
- Post, edit, delete text-Registration makes it possible to submit new posts. You can edit and delete only your own posts
- Display flash message-A flash message will be displayed according to the screen to improve usability

## Dependency
- ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-darwin18]
- Rails 5.2.2.1

## Database

### messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_up|integer|null: false, refference|
|user_id|integer|null: false, refference|

#### Association
- belongs_to :group
- belongs_to :user

### usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|strinng|null: false|
|Email|string|null: false, unique: true|
|password|string|null: false|

#### Association
- has_many :messages
- has_many :groups, through: :members
- has_many :members

### groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

#### Association
- has_many :messages
- has_many :users, through: :members
- has_many :members
accepts_nested_attributes_for :members

### membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, refference|
|group_id|integer|null: false, refference|

#### Association
- belongs_to :group
- belongs_to :user

## Author

[syoji-haruki](https://github.com/syoji-haruki)

<!-- # README

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
 -->
