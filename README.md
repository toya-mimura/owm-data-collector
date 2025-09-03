# Weather Data Collector

[OpenWeatherMap](https://openweathermap.org/)から10分毎に天気データを取得し、JSONファイルとして保存するリポジトリです。

## 機能

- 📊 10分毎にOpenWeatherMap APIから天気データを自動取得
- 💾 データを`data/`フォルダにJSON形式で保存
- 🗂️ ファイル命名規則：`yyyy-mmdd-hhmm.json`
- 🧹 直近24時間分（144ファイル）のみ保持し、古いファイルは自動削除

## セットアップ

1. このリポジトリをフォーク
2. GitHub Secretsに以下を設定：
   - `OPENWEATHER_API_KEY`: OpenWeatherMapのAPIキー
   - `LAT`: 取得地点の緯度（例：35.443707）
   - `LON`: 取得地点の経度（例：139.638031）
      - 本リポジトリでは例として「横浜」の緯度経度を利用中。

## データ構造
- 各JSONファイルにはOpenWeatherMapの標準レスポンスが含まれます：
- 参考：https://openweathermap.org/current

```json
{
  "coord": {"lon": 139.64, "lat": 35.44},
  "weather": [{"id": 800, "main": "Clear", "description": "clear sky"}],
  "main": {"temp": 20.5, "humidity": 65},
  "name": "Tokyo"
}
```

## 謝辞
- このサイトの天気情報はOpenWeatherMap(https://openweathermap.org/)から取得しています / Powered by OpenWeatherMap
