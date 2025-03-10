# 呷飽NO.1

## 目標
讓使用者可以更輕鬆找到自己飽餐一頓的餐廳

## 技術選擇原因


## 架構說明

## 安裝與執行指引
1. __複製專案倉庫__

    ```
    git clone
    cd
    ```
2. __安裝項目__

    * 後端：
        ```
        cd Backend
        npm install
        ```
    * 前端：
        ```
        cd Frontkend
        npm install
        ```
3. __設置環境變數__

    * 在後端資料夾中建立一個 `.env` 文件，內容如下：
        ```
        DBUSER = test
        DBPASSWORD = password
        DBHOST = 127.0.0.1
        DBPORT = 8888
        DBNAME = name
        PORT = 2083
        LogPath = logs
        assetsPath = /assets
        HomePagePath = /index.html
        privateKey = key
        ```
4. __執行程式：__
 
    * 後端：
    ```
    cd Backend
    npm run dev
    ```
    * 前端：
    ```
    cd Frontend
    npm run dev
    ```
5. 打開瀏覽器並訪問 `http://localhost:5173`

## API規格說明

### 基本URL

```
http://localhost:8888/api/v1/user
```
### 端點
1. __查詢所有餐廳列表__
    * 方法：GET
    * 端點：`/findAll`
    * 回應：
        ```
        {
            "code": 200,
            "message": "find success",
            "body": [
                {
                    "_id": "ID",
                    "rid": 編號,
                    "name": "餐廳名稱",
                    "category": "類別",
                    "rating": 評分,
                    "location": "地址"
                }...
            ]
        }
        ```
2. __新增餐廳資訊__
    * 方法：POST
    * 端點：`/insertOne`
    * 請求：
        ```
        {
            "rid": 編號,
            "name": "餐廳名稱",
            "category": "類別",
            "rating": 評分,
            "location": "地址"
         } 
        ```
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Restaurant added successfully",
            "body": {
                "rid": 編號,
                "name": "餐廳名稱",
                "category": "類別",
                "rating": 評分,
                "location": "地址",
                "_id": "ID",
                "__v": 0
            }
        }
        ```
3. __依名稱查詢餐廳資訊__
    * 方法：GET
    * 端點：`/findOne`
    * 請求：
        | 名稱    | 類型   |
        | ------- |:------:|
        | `name`  | String |
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Restaurant found",
            "body": {
                "_id": "ID",
                "rid": 編號,
                "name": "餐廳名稱",
                "category": "類別",
                "rating": 評分,
                "location": "地址",
                "__v": 0
            }
        }
        ```
4. __依ID更新餐廳名稱__
    * 方法：PUT
    * 端點：`/updateName`
    * 請求：
        | 名稱      | 類型   |
        | --------- |:------:|
        | `oldName` | String |
        | `newName` | String |
            

    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Update success",
            "body": {
                "_id": "ID",
                "rid": 編號,
                "name": "餐廳名稱",
                "category": "類別",
                "rating": 評分,
                "location": "地址",
                "__v": 0
            }
        }
        ```
5. __依ID刪除餐廳資訊__
    * 方法：Delete
    * 端點：`/deleteByName`
    * 請求：
        | 名稱  | 類型   |
        | ----- |:------:|
        | `name`  | String |
    * 回應：
        ``` 
        {
            "code": 200,
            "message": "Success",
            "body": {
                "acknowledged": true,
                "deletedCount": 1
            }
        }
        ```

## 架構圖

![架構圖](image/架構圖.png "架構圖")

## 流程圖

![流程圖](image/流程圖.png "流程圖")

## Demo影片

<https://youtu.be/o_c4FDAhUJE?si=tM1y9_pcEuEBtGMO>
