## 🌐 Доступ к приложению

```bash
docker compose down
docker compose build
docker compose up -d
```

После запуска контейнеров приложение доступно по адресу:
http://localhost:8876/

---

## ⚡️ Обновление

```bash
# Добавляем официальный репозиторий Laravel как 'upstream'
git remote add upstream https://github.com/laravel/laravel.git

# Проверяем, что все добавилось правильно
git remote -v
# Должно показать что-то вроде:
# origin    https://github.com/твой-аккаунт/твой-проект.git (fetch/push)
# upstream  https://github.com/laravel/laravel.git (fetch/push)

# 1. Загрузить обновления из официального репозитория
git fetch upstream

# 2. Выполнить слияние с веткой 13.x
git merge upstream/13.x --allow-unrelated-histories

# 3. Обновить зависимости
composer update

# 4. Очистить кэш
php artisan optimize:clear
php artisan config:cache
php artisan config:clear
php artisan cache:clear
php artisan route:cache

# 5. Проверить версию
php artisan --version

# 6. Проверить на уязвимости
composer audit
```

## Cors
```bash
php artisan config:publish cors

После публикации редактируем файл config/cors.php
```

## Миграции
```bash
php artisan make:controller PostsController  - создать контроллер
php artisan make:migration create_posts_table - создать миграцию
php artisan migrate:refresh - перезоздать таблицы из миграции
php artisan make:model Posts - создать модель
php artisan make:seeder PostsSeeder - создать наполнитель текста
php artisan db:seed - запуск наполнителя текста
php artisan migrate:fresh --seed - Если нужно очистить базу и пересоздать все таблицы перед заполнением
```
## Generate key
```bash
php artisan key:generate
```

## Создать симлинк на storage
```bash
php artisan storage:link
```
