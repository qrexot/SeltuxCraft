# SeltuxCraft · Seltuks Launcher

[![Windows build](https://github.com/qrexot/SeltuxCraft/actions/workflows/windows-release.yml/badge.svg)](https://github.com/qrexot/SeltuxCraft/actions/workflows/windows-release.yml)
[![Telegram](https://img.shields.io/badge/Telegram-@Seltux-26A5E4?logo=telegram)](https://t.me/Seltux)

Лаунчер **Seltuks** для Windows. Автор версии Seltuks, оформления и доработок: **Леонард — [@Seltux](https://t.me/Seltux)**.

**Статус:** оформление и автоматическая сборка подготовлены. Публикация исходников и первого EXE-релиза ещё не завершена.

## Скачать

После успешной сборки готовые файлы появятся в [Releases](https://github.com/qrexot/SeltuxCraft/releases/latest):

- `Seltuks-Launcher.exe` — портативный запуск.
- `seltuks-launcher-setup-x64.exe` — установка для текущего пользователя.
- `Seltuks-Launcher-windows-x64.zip` — комплект с лицензией и контрольными суммами.

Поддерживается 64-разрядная Windows. EXE не подписан коммерческим сертификатом.
Для Minecraft необходима собственная лицензия; файлы игры в репозиторий не включены.
Вход Microsoft требует настройки `HORIZON_MSA_CLIENT_ID` в Settings → Secrets and variables → Actions → Variables.

## Сборка

Установите Rust stable и Visual Studio Build Tools с компонентами C++ и Windows SDK:

```powershell
cargo build --release --locked --manifest-path launcher/Cargo.toml
```

Результат: `launcher/target/release/horizon-launcher.exe` (в релизе переименован в Seltuks).

## Автоматические релизы

Каждое обновление `main` собирается в GitHub Actions и публикует отдельный релиз `build-<номер>` после успешной сборки. Ручной запуск доступен в Actions → Windows release → Run workflow. Релиз содержит EXE, установщик, ZIP и SHA-256.

## Исходники и авторство

`launcher/` — полный исходный код лаунчера; `crates/` — только 15 локальных библиотек, прямо указанных в `launcher/Cargo.toml`; `packaging/` — иконки; `tools/` — проверка EXE. Машинные отчёты бенчмарков и отдельный игровой клиент не публикуются.

Seltuks основан на **Horizon** (Ludovic Marie и участники Horizon), лицензия MIT. Авторство исходной основы и сторонние уведомления сохранены в [LICENSE](LICENSE) и [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). [Документация основы](docs/HORIZON_UPSTREAM_README.md).

Связь с автором Seltuks: **[@Seltux](https://t.me/Seltux)**.
