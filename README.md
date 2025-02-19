# grpc_proxy_yt_thumbnail (gRPC)

![Go Version](https://img.shields.io/badge/Go-1.23.3-blue)

**grpc_proxy_yt_thumbnail** — это gRPC-приложение на Go, которое позволяет скачивать изображения-миниатюры из заданного источника через консоль или обращение к серверу .

---
## Основное описание сервиса

- Используемый сервер под БД был мной арендован и использован для выгрузки необходимых данных. Весь основной код для работы с БД описаной мной в Services/sqlService.go
- Оставил возможность подключаться как с gRPC через метод и .proto, так и для консольных комманд

---
## Инструкция

Для использования async метода необходимо прописать в *CMD* <br>
**Пример**
```bash
go run main.go -urls=https://www.youtube.com/watch?v=fqg89xfLJMk -urls=https://www.youtube.com/watch?v=Ue0lAU-VjEQ  -async=true
```

**Пример использования sync метода. В таком случае можно грузить только 1 URL**
```bash
go run main.go -urls=https://www.youtube.com/watch?v=Ue0lAU-VjEQ
```

**Пример запуска gRPC сервера **
```bash
go run main.go
```

Но перед этим перейти через cd в папку, где находится скачанный проект
В случае если URL был загружен впервые, то никакого ответа не последуе - просто скачается картинка и БД будет заполнена данными, 
при вторичном выведутся данные с типом **[]byte**.

**Пример работы. Проверка была проведена в Postman.** <br>
В данном примере одно и двух видео было загружено дважды.
![{39050F63-D9D1-4D97-9DE7-43C1C9A97F62}](https://github.com/user-attachments/assets/e00f1d5a-6ab7-4057-8d46-f608ea06d887)


## Требования

- Go 1.23 или выше.
- Локальный доступ к `localhost` для работы gRPC-сервера.
- Установленный [protoc](https://grpc.io/docs/protoc-installation/) для генерации gRPC-кода (если будете компилировать `.proto` самостоятельно).

---

## Установка

1. **Клонируйте репозиторий**:
   ```bash
   git clone https://github.com/tishotahoe/grpc_proxy_yt_thumbnail.git
   ```
