# preptaiwan LINE Official Account Handover

## Purpose

This handover is for an authorized operator or implementation agent who will configure the `preptaiwan` LINE Official Account rich menu and auto-reply flow.

## Account Scope

- LINE Official Account name: `preptaiwan`
- LINE Official Account ID: `@gbp6115u`
- LINE Manager admin URL: <https://manager.line.biz/account/@gbp6115u>
- Public LINE account URL to verify: <https://line.me/R/ti/p/@gbp6115u>

Do not place the LINE Manager admin URL in customer-facing messages or rich-menu buttons.

## Credential Handling

Do not store real credentials in this repository, commit history, screenshots, shared docs, or chat logs. The account owner should enter credentials directly into LINE Official Account Manager and rotate any password previously exposed in chat before handing access to another operator.

If environment variables are needed for a private automation environment, use local-only placeholders such as:

```env
LINE_MANAGER_EMAIL=
LINE_MANAGER_PASSWORD=
LINE_ACCOUNT_ID=@gbp6115u
```

The local `.env` file must remain uncommitted.

## Implementation Approach

Use a six-button rich menu. Configure every button as a LINE **Text action**. The text sent by each button should be the same as the visible topic so users see a natural message in chat.

## Rich Menu Button Map

| Button | Visible label | Action type | Text action / trigger keyword |
| --- | --- | --- | --- |
| 1 | 非詐騙平台 | Text | `非詐騙平台` |
| 2 | 回覆時間 | Text | `回覆時間` |
| 3 | 代辦流程 | Text | `代辦流程` |
| 4 | 到貨時間 | Text | `到貨時間` |
| 5 | 急需 PrEP | Text | `急需使用PrEP` |
| 6 | 曼谷自取 | Text | `曼谷自取` |

## Suggested Visual Direction

Primary rich-menu style:

- Main colors: red and white
- Secondary colors: light grey and dark grey
- Icons: simple line icons
- Layout: six equal tappable areas
- Tone: clear, official, high contrast, mobile readable

Suggested icons:

| Button | Icon idea |
| --- | --- |
| 非詐騙平台 | shield with checkmark |
| 回覆時間 | clock with chat bubble |
| 代辦流程 | checklist with arrows |
| 到貨時間 | delivery truck or calendar |
| 急需 PrEP | medical cross or warning mark |
| 曼谷自取 | map pin or hotel |

## Auto-Reply Messages

### 1. 非詐騙平台

Trigger keyword:

```text
非詐騙平台
```

Auto-reply message:

```text
【公告｜非詐騙平台】

我司雖在台灣沒有成立公司，但在新加坡及泰國有設立公司。

公司分別為：
・Vensure Medical Pte Ltd
・Vensure Enterprise Co. Ltd

皆可查詢得到相關資料，也找得到人，請不用擔心。
```

### 2. 回覆時間

Trigger keyword:

```text
回覆時間
```

Auto-reply message:

```text
【公告｜回覆時間】

客服為兼職，沒有固定上下班時間，會盡快依照訊息順序回覆。

請勿重複發送訊息，否則回覆順序可能會往後推，導致回覆時間延後。

也請勿同時在 Facebook 私訊，以免造成資訊重複及處理延誤。

感謝您的耐心等候。
```

### 3. 代辦流程

Trigger keyword:

```text
代辦流程
```

Auto-reply message:

```text
【代辦流程】

每次代辦流程皆相同：

1. 填寫代辦表單
2. Email 收到付款連結
3. 收到款項後，我司提供配合醫生資訊
4. 您自行掛號看診及抽血檢查
   一般醫療端約需 2 週左右出報告
5. 請拍照診斷書給我們
6. 我們跟醫師取得處方簽
   一般醫師約需 2 週處理
7. 拿到處方簽後，我司協助您向 FDA／食藥署申報
8. 您需提供身分證正反面照片及線上簽名
9. 您線上簽名送出後，我司通知物流安排出貨事宜
   約 1～3 天寄出
10. 約 2 週後，您會收到台灣海關綠單，以及 FDA email 同意公文，內含 2 個 PDF 檔案
11. 同時收到後，請致電海關綠單上的電話，告知已收到 FDA 同意，請海關自行開箱檢驗後放行寄出
12. 如海關要求 Invoice，可在付款連結 email 附件中找到
```

### 4. 到貨時間

Trigger keyword:

```text
到貨時間
```

Auto-reply message:

```text
【什麼時候到貨？】

請以代辦流程中的以下階段開始計算：

「您線上簽名送出後，我司通知物流安排出貨事宜」

從此階段開始計算，約 14～30 天到貨。

此時間不包含：
・海關處理時間
・FDA／食藥署審核時間
・其他不可控物流延誤

因此實際到貨時間可能依個案情況不同而有所變動。
```

### 5. 急需使用PrEP

Trigger keyword:

```text
急需使用PrEP
```

Auto-reply message:

```text
【急需使用 PrEP】

很抱歉，如您急需服用 PrEP，我司服務可能不適合您。

本服務需要完成完整代辦流程，包含：
・看診
・抽血檢查
・診斷書
・處方簽
・FDA／食藥署申報
・物流及海關流程

整體流程需要時間，請您在填寫代辦前，先自行評估時間與風險。

若您有急迫需求，建議優先諮詢當地合格醫療院所或醫師。
```

### 6. 曼谷自取

Trigger keyword:

```text
曼谷自取
```

Auto-reply message:

```text
【曼谷自取注意事項】

我司目前僅提供【曼谷】自取服務。

自取方式：
我司曼谷同事會送到您的飯店大廳，您需下樓親自接收。

另外，填寫代辦訂單前，請先確認：

【可以讓我司在自取日 2 週前拿到處方簽】

這樣才來得及安排曼谷自取。

若無法在自取日前 2 週取得處方簽，可能無法安排自取。
```

## Setup Checklist for the Implementing Agent

1. Log in to LINE Official Account Manager with credentials entered directly by the account owner.
2. Open the `preptaiwan` account.
3. Create a new rich menu with six tappable areas.
4. Upload the red/white menu graphic.
5. Configure each rich-menu area using the button map above.
6. Create or update auto-reply messages using the trigger keywords and message bodies above.
7. Save without publishing if LINE Manager offers draft/preview.
8. If no draft mode is available, keep the new rich menu inactive until testing is complete.
9. Test each button from a LINE mobile account.
10. Confirm each message appears exactly once and in the correct sequence.
11. Publish the rich menu only after all six buttons pass testing.

## Testing Checklist

- Button 1 sends `非詐騙平台` and receives the non-scam platform notice.
- Button 2 sends `回覆時間` and receives the response-time notice.
- Button 3 sends `代辦流程` and receives the full process message.
- Button 4 sends `到貨時間` and receives the delivery-time message.
- Button 5 sends `急需使用PrEP` and receives the urgent-use guidance.
- Button 6 sends `曼谷自取` and receives the Bangkok pickup notice.
- Public LINE account URL opens correctly on mobile.
- No admin-only URL is exposed to customers.
- No credentials are stored in files, chat notes, graphics, or screenshots.

## Notes for Medical and Regulatory Content

The auto-replies should avoid giving medical advice. For urgent PrEP needs, the message should direct users to consult a qualified local medical provider. Any statements about Taiwan FDA, customs, or import timing should be treated as operational estimates and reviewed by the account owner before publication.
