---
layout: page
title: OPEN API EMTQ 
permalink: /emtq/
---

**Daftar Isi**

- [Open Api Emtq Jabar](#open-api-emtq-jabar)
- [Success Response](#success-response)
- [Error Response](#error-response)
- [List Api](#list-api)
  - [List Kafilah](#list-kafilah)
  - [List Cabang Musabaqah](#list-cabang-musabaqah)
  - [List Peserta Berdasarkan Kafilah](#list-peserta-berdasarkan-kafilah)
  - [List Peserta Berdasarkan Cabang](#list-peserta-berdasarkan-cabang)
  - [Peringkat & Nilai Peserta Per Cabang](#peringkat--nilai-peserta-per-cabang)


# Open Api Emtq Jabar

| Environtment        | Url                               | Extension |
| ------------------- | --------------------------------- | --------- |
| Production          | `on development`                  | -         |
| Development / Dummy | [rizlantamima.github.io/emtq](./) | .json     |

Untuk production, akan diberikan `key` berupa token yang wajib diberikan / dikirim menjadi request query parameter, contoh
`https://rizlantamima.github.io/emtq/cabang?key=aoi7s8aydaih`





# Success Response

Setiap request yang berhasil, akan mendapatkan http response code `200`, dengan sample response sebagai berikut :
```
{
    "code": 200,
    "status": "success",
    "message": "Ok!",
    "data": null / [] / {}
}
```

Deskripsi Response  : 

| Key     | Type                  | Value   | Description                                                                                      |
| ------- | --------------------- | ------- | ------------------------------------------------------------------------------------------------ |
| code    | int                   | 200     | Int sama dengan reponse code yang di dapat                                                       |
| status  | string                | success | Indikasi bahwa request berhasil                                                                  |
| message | string                | Ok      | String keterangan                                                                                |
| data    | null / array / object | null    | Tergantung dari request yang di kirim, jika list akan mendapatkan array, detail berbentuk object |

# Error Response

Setiap request yang gagal / ditemukan error, akan mendapatkan http response code `400` / `5xx`, dengan sample response sebagai berikut :
```
{
    "code": 400,
    "status": "failed",    
    "message": "Peserta tidak ditemukan!",
    "data": null
}
```

Deskripsi Response  : 

| Key     | Type   | Value  | Description                                |
| ------- | ------ | ------ | ------------------------------------------ |
| code    | int    | 400    | Int sama dengan reponse code yang di dapat |
| status  | string | failed | Indikasi bahwa request gagal failed        |
| message | string | Ok     | String keterangan error                    |
| data    | null   | null   |                                            |

***
# List Api
***

## List Kafilah

**REQUEST**

| Environtment        | Method | Url                                                        |
| ------------------- | ------ | ---------------------------------------------------------- |
| Production          | GET    | `on development`                                           |
| Development / Dummy | GET    | [rizlantamima.github.io/emtq/kafilah.json](./kafilah.json) |

**QUERY PARAM**

| Environtment | Required | Description                                       |
| ------------ | -------- | ------------------------------------------------- |
| key          | required | token yang diberikan                              |
| search       | optional | Digunakan untuk searching kafilah bedasarkan nama |

## List Cabang Musabaqah

**REQUEST**

| Environtment        | Method | Url                                                      |
| ------------------- | ------ | -------------------------------------------------------- |
| Production          | GET    | `on development`                                         |
| Development / Dummy | GET    | [rizlantamima.github.io/emtq/cabang.json](./cabang.json) |

**QUERY PARAM**

| Environtment | Required | Description                                      |
| ------------ | -------- | ------------------------------------------------ |
| key          | required | token yang diberikan                             |
| search       | optional | Digunakan untuk searching cabang bedasarkan nama |


## List Peserta Berdasarkan Kafilah

Api untuk menampilkan list peserta berdasarkan kafilah

**REQUEST**

| Environtment        | Method | Url                                                                              |
| ------------------- | ------ | -------------------------------------------------------------------------------- |
| Production          | GET    | `on development`                                                                 |
| Development / Dummy | GET    | [rizlantamima.github.io/emtq/peserta-by-kafilah.json](./peserta-by-kafilah.json) |

**QUERY PARAM**

| Environtment | Required | Description                                       |
| ------------ | -------- | ------------------------------------------------- |
| key          | required | token yang diberikan                              |
| search       | optional | Digunakan untuk searching peserta bedasarkan nama |


## List Peserta Berdasarkan Cabang

Api untuk menampilkan list peserta berdasarkan cabang

**REQUEST**

| Environtment        | Method | Url                                                                            |
| ------------------- | ------ | ------------------------------------------------------------------------------ |
| Production          | GET    | `on development`                                                               |
| Development / Dummy | GET    | [rizlantamima.github.io/emtq/peserta-by-cabang.json](./peserta-by-cabang.json) |

**QUERY PARAM**

| Environtment | Required | Description                                       |
| ------------ | -------- | ------------------------------------------------- |
| key          | required | token yang diberikan                              |
| search       | optional | Digunakan untuk searching peserta bedasarkan nama |


## Peringkat & Nilai Peserta Per Cabang

Api untuk menampilkan list perinfkat dan nilai peserta berdasarkan cabang

**REQUEST**

| Environtment        | Method | Url                                                                        |
| ------------------- | ------ | -------------------------------------------------------------------------- |
| Production          | GET    | `on development`                                                           |
| Development / Dummy | GET    | [rizlantamima.github.io/emtq/nilai-by-cabang.json](./nilai-by-cabang.json) |

**QUERY PARAM**

| Environtment | Required | Description                                       |
| ------------ | -------- | ------------------------------------------------- |
| key          | required | token yang diberikan                              |
| search       | optional | Digunakan untuk searching peserta bedasarkan nama |