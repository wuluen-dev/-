<!DOCTYPE html>
<html lang="zh-TW"><head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>運動風潮 - 團服尺寸登記表</title>
  <style>
    * {
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Microsoft JhengHei", "PingFang TC", sans-serif;
    }
    body {
      background-color: #e9ecef;
      margin: 0;
      padding: 10px 8px 50px 8px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .poster-container {
      width: 100%;
      max-width: 820px;
      background: #ffffff;
      border: 1px solid #bdc3c7;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    }

    /* 頂部海報圖片顯示區 */
    .banner-img-container {
      width: 100%;
      background-color: #f8f9fa;
      position: relative;
    }
    #bannerImage {
      width: 100%;
      height: auto;
      display: block;
      border-bottom: 2px solid #0b377b;
    }

    /* 一鍵自動轉 Base64 內嵌工具盒 (匯出後會自動移除，維持成品簡潔) */
    .uploader-box {
      background: #eef6ff;
      border: 2px dashed #0d6efd;
      padding: 15px 12px;
      margin: 12px;
      border-radius: 8px;
      text-align: center;
    }
    .uploader-tip {
      font-size: 15px;
      font-weight: bold;
      color: #0b377b;
      margin-bottom: 8px;
    }
    .btn-pack {
      margin-top: 10px;
      padding: 12px 20px;
      background: #198754;
      color: #ffffff;
      border: none;
      border-radius: 6px;
      font-size: 15px;
      font-weight: 900;
      cursor: pointer;
      box-shadow: 0 3px 8px rgba(25,135,84,0.3);
      display: inline-block;
    }

    /* 表單區塊 */
    .form-section {
      padding: 12px;
      background: #ffffff;
    }
    .mobile-scroll-tip {
      font-size: 12px;
      color: #d32f2f;
      font-weight: bold;
      margin-bottom: 6px;
      display: flex;
      justify-content: space-between;
    }

    .tables-wrapper {
      display: flex;
      flex-direction: column;
      gap: 14px;
    }
    @media (min-width: 768px) {
      .tables-wrapper { flex-direction: row; gap: 10px; }
      .mobile-scroll-tip { display: none; }
    }
    .table-col {
      flex: 1;
      width: 100%;
      overflow-x: auto;
      -webkit-overflow-scrolling: touch;
    }
    table {
      width: 100%;
      min-width: 390px;
      border-collapse: collapse;
      text-align: center;
      font-size: 13px;
    }
    table, th, td {
      border: 1px solid #000000;
    }
    th, td {
      padding: 4px 1px;
      height: 28px;
    }
    .table-title {
      background-color: #ffffff;
      font-weight: bold;
      font-size: 13.5px;
      padding: 6px 2px;
    }
    .size-head-female { background-color: #fcebe6; font-weight: bold; }
    .size-head-male { background-color: #e5f1fa; font-weight: bold; }
    .qty-row { background-color: #fffde7; }
    .qty-row td:first-child {
      font-weight: bold;
      color: #b71c1c;
      font-size: 12px;
    }

    /* 輸入格 */
    .qty-input {
      width: 88%;
      height: 32px;
      border: 1.5px solid #555;
      border-radius: 4px;
      text-align: center;
      font-size: 16px;
      font-weight: 900;
      color: #0b377b;
      background: #ffffff;
    }
    .qty-input:focus {
      outline: 2px solid #0d6efd;
      background: #eef6ff;
    }

    .note-bar {
      margin-top: 12px;
      font-size: 12px;
      border: 1px solid #000;
      padding: 6px 8px;
      background: #fafafa;
    }

    /* 資訊欄 */
    .bottom-info-grid {
      margin-top: 14px;
      display: grid;
      grid-template-columns: 1fr;
      row-gap: 12px;
      column-gap: 15px;
      font-size: 14.5px;
      font-weight: bold;
    }
    @media (min-width: 580px) {
      .bottom-info-grid {
        grid-template-columns: repeat(3, 1fr);
      }
    }
    .info-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .info-label {
      white-space: nowrap;
      margin-right: 6px;
    }
    .underline-input {
      flex: 1;
      border: none;
      border-bottom: 1.5px solid #000;
      padding: 5px;
      font-size: 15px;
      outline: none;
      background: transparent;
    }
    .box-input {
      width: 95px;
      height: 32px;
      border: 1.5px solid #000;
      text-align: center;
      font-size: 16px;
      font-weight: 900;
      background-color: #f8f9fa;
      color: #000;
    }
    .box-total {
      background: #e7f1ff;
      color: #0b377b;
      border: 2px solid #0b377b;
      font-size: 18px;
    }

    /* 底部按鈕區 */
    .submit-container {
      margin-top: 20px;
      padding: 5px;
      text-align: center;
    }
    .btn-main-send {
      width: 100%;
      max-width: 480px;
      padding: 15px 20px;
      background: #06C755;
      color: #ffffff;
      border: none;
      border-radius: 8px;
      font-size: 18px;
      font-weight: 900;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(6, 199, 85, 0.35);
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      text-decoration: none;
    }

    /* 傳送視窗 */
    .modal-overlay {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.7);
      z-index: 9999;
      justify-content: center;
      align-items: center;
      padding: 15px;
    }
    .modal-card {
      background: #fff;
      width: 100%;
      max-width: 420px;
      border-radius: 12px;
      padding: 20px 16px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.3);
    }
    .modal-title {
      font-size: 18px;
      font-weight: 900;
      text-align: center;
      margin-bottom: 8px;
    }
    .modal-desc {
      font-size: 13px;
      color: #555;
      text-align: center;
      margin-bottom: 15px;
    }
    .modal-actions {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
    .modal-btn {
      padding: 13px;
      border-radius: 8px;
      border: none;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      text-decoration: none;
    }
    .btn-line { background-color: #06C755; color: #fff; }
    .btn-copy-text { background-color: #0d6efd; color: #fff; }
    .btn-close-modal { background-color: #e9ecef; color: #333; margin-top: 5px; }

    .preview-textarea {
      width: 100%;
      height: 90px;
      font-size: 12px;
      padding: 6px;
      border: 1px solid #ccc;
      border-radius: 4px;
      background: #fdfdfd;
      margin-top: 8px;
      resize: none;
    }
  </style>
</head>
<body>

  <div class="poster-container">
    
    <!-- 頂部海報圖片 (已支援 Base64 內嵌) -->
    <div class="banner-img-container">
      <img id="bannerImage" src="data:image/jpeg;base64,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" alt="運動風潮海報" style="display: block;">
      
      <!-- 一鍵轉 Base64 內嵌轉換盒 -->
      
    </div>

    <!-- 尺寸登記表單區 -->
    <div class="form-section">
      <div class="mobile-scroll-tip">
        <span>👇 請在黃色「件數統計」填入數量</span>
        <span>👉 表格可向右滑動</span>
      </div>

      <div class="tables-wrapper">
        <!-- 女款表格 -->
        <div class="table-col">
          <table>
            <tbody><tr>
              <th colspan="9" class="table-title">版套尺寸 - DHD0103P-女公版 POLO</th>
            </tr>
            <tr class="size-head-female">
              <th style="width: 15%;"></th>
              <th>S</th><th>M</th><th>L</th><th>XL</th><th>2XL</th><th>3XL</th><th>4XL</th><th>5XL</th>
            </tr>
            <tr>
              <td>肩寬</td><td>36.2</td><td>38.7</td><td>41.3</td><td>43.3</td><td>43.3</td><td>46.4</td><td>51.4</td><td>54.0</td>
            </tr>
            <tr>
              <td>胸圍</td><td>44.5</td><td>47.0</td><td>49.5</td><td>52.1</td><td>54.6</td><td>57.2</td><td>59.7</td><td>62.2</td>
            </tr>
            <tr>
              <td>下擺</td><td>62.2</td><td>64.8</td><td>67.3</td><td>69.9</td><td>72.4</td><td>74.9</td><td>77.5</td><td>80.0</td>
            </tr>
            <tr>
              <td>袖口</td><td>15.8</td><td>18.4</td><td>18.4</td><td>19.7</td><td>17.8</td><td>22.2</td><td>23.5</td><td>24.5</td>
            </tr>
            <tr class="qty-row">
              <td>件數統計</td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="S" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="M" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="L" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="2XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="3XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="4XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input f-qty" data-size="5XL" oninput="calc()" onkeyup="calc()"></td>
            </tr>
          </tbody></table>
        </div>

        <!-- 男款表格 -->
        <div class="table-col">
          <table>
            <tbody><tr>
              <th colspan="9" class="table-title">版套尺寸 - DHD0102P -男POLO</th>
            </tr>
            <tr class="size-head-male">
              <th style="width: 15%;"></th>
              <th>XS</th><th>S</th><th>M</th><th>L</th><th>XL</th><th>2XL</th><th>4XL</th><th>5XL</th>
            </tr>
            <tr>
              <td>肩寬</td><td>38.7</td><td>41.3</td><td>43.8</td><td>48.4</td><td>48.9</td><td>51.4</td><td>56.5</td><td>59.1</td>
            </tr>
            <tr>
              <td>胸圍</td><td>47.0</td><td>49.5</td><td>52.1</td><td>54.6</td><td>57.2</td><td>59.7</td><td>64.8</td><td>67.3</td>
            </tr>
            <tr>
              <td>衣長</td><td>64.8</td><td>67.3</td><td>69.9</td><td>72.4</td><td>74.9</td><td>80.0</td><td>80.0</td><td>80.0</td>
            </tr>
            <tr>
              <td>袖長</td><td>15.9</td><td>18.4</td><td>19.7</td><td>17.8</td><td>21.5</td><td>24.9</td><td>20.0</td><td>21.0</td>
            </tr>
            <tr class="qty-row">
              <td>件數統計</td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="XS" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="S" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="M" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="L" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="2XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="4XL" oninput="calc()" onkeyup="calc()"></td>
              <td><input type="text" inputmode="numeric" class="qty-input m-qty" data-size="5XL" oninput="calc()" onkeyup="calc()"></td>
            </tr>
          </tbody></table>
        </div>
      </div>

      <div class="note-bar">
        <div><strong>【多選尺寸登記】</strong>請在對應方格內填寫件數</div>
        <div style="font-size: 11px; color: #555;">尺寸僅供參考，正面平量誤差約1~1公分屬正常</div>
      </div>

      <!-- 基本資料 -->
      <div class="bottom-info-grid">
        <div class="info-item">
          <span class="info-label">姓名:</span>
          <input type="text" id="custName" class="underline-input" placeholder="請填寫姓名" oninput="calc()">
        </div>
        <div class="info-item">
          <span class="info-label">電話:</span>
          <input type="tel" id="custPhone" class="underline-input" placeholder="請填寫電話" oninput="calc()">
        </div>
        <div class="info-item">
          <span class="info-label">男款總件數:</span>
          <input type="text" id="maleTotal1" class="box-input" readonly="" value="0">
        </div>

        <div class="info-item">
          <span class="info-label">部門:</span>
          <input type="text" id="custDept" class="underline-input" placeholder="請填寫部門" oninput="calc()">
        </div>
        <div class="info-item">
          <span class="info-label">組別:</span>
          <input type="text" id="custTeam" class="underline-input" placeholder="請填寫組別" oninput="calc()">
        </div>
        <div class="info-item">
          <span class="info-label">女款總件數:</span>
          <input type="text" id="femaleTotal1" class="box-input" readonly="" value="0">
        </div>

        <div class="info-item">
          <span class="info-label">男款總件數:</span>
          <input type="text" id="maleTotal2" class="box-input" readonly="" value="0">
        </div>
        <div class="info-item">
          <span class="info-label">女款總件數:</span>
          <input type="text" id="femaleTotal2" class="box-input" readonly="" value="0">
        </div>
        <div class="info-item">
          <span class="info-label" style="color:#0b377b;">總件數總計:</span>
          <input type="text" id="grandTotal" class="box-input box-total" readonly="" value="0">
        </div>
      </div>

      <!-- 底部儲存與傳送審查 -->
      <div class="submit-container">
        <button type="button" class="btn-main-send" onclick="openSendModal()">
          💬 填寫完成：傳送 LINE 給我審查
        </button>
      </div>
    </div>
  </div>

  <!-- 傳送對話視窗 -->
  <div class="modal-overlay" id="sendModal">
    <div class="modal-card">
      <div class="modal-title">傳送審查結果</div>
      <div class="modal-desc">已為您自動彙整件數明細，請點擊下方直接傳送：</div>

      <div class="modal-actions">
        <a id="lineDirectLink" class="modal-btn btn-line" href="https://line.me/R/msg/text/?%E3%80%90%E9%81%8B%E5%8B%95%E9%A2%A8%E6%BD%AE%20-%20%E5%9C%98%E6%9C%8D%E7%99%BB%E8%A8%98%E5%AF%A9%E6%9F%A5%E5%96%AE%E3%80%91%0A%E5%A7%93%E5%90%8D%EF%BC%9A%E6%9C%AA%E5%A1%AB%0A%E9%9B%BB%E8%A9%B1%EF%BC%9A%E6%9C%AA%E5%A1%AB%0A%E9%83%A8%E9%96%80%2F%E7%B5%84%E5%88%A5%EF%BC%9A%E6%9C%AA%E5%A1%AB%20%2F%20%E6%9C%AA%E5%A1%AB%0A-------------------------%0A%F0%9F%91%9A%20%E5%A5%B3%E6%AC%BEPOLO%EF%BC%9A0%E4%BB%B6%20(%E5%B0%8F%E8%A8%88%200%20%E4%BB%B6)%0A%F0%9F%91%95%20%E7%94%B7%E6%AC%BEPOLO%EF%BC%9A0%E4%BB%B6%20(%E5%B0%8F%E8%A8%88%200%20%E4%BB%B6)%0A%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%3D%0A%E2%AD%90%20%E7%B8%BD%E4%BB%B6%E6%95%B8%E5%90%88%E8%A8%88%EF%BC%9A0%20%E4%BB%B6%0A%0A%F0%9F%94%97%20%E9%BB%9E%E6%93%8A%E7%B6%B2%E5%9D%80%E6%9F%A5%E7%9C%8B%E5%A1%AB%E5%A5%BD%E7%9A%84%E5%AE%8C%E6%95%B4%E5%9C%96%E8%A1%A8%EF%BC%9A%0Afile%3A%2F%2F%2FC%3A%2FUsers%2FASUS%2FDownloads%2Fai_studio_code%2520(4).html%23%257B%2522name%2522%253A%2522%2522%252C%2522phone%2522%253A%2522%2522%252C%2522dept%2522%253A%2522%2522%252C%2522team%2522%253A%2522%2522%252C%2522fSizes%2522%253A%257B%257D%252C%2522mSizes%2522%253A%257B%257D%257D" target="_blank" onclick="executeLineSend(event)">
          🟢 點此開啟 LINE 傳送給我
        </a>

        <button type="button" class="modal-btn btn-copy-text" onclick="copyResultText()">
          📋 複製訂單文字 (手動貼到 LINE)
        </button>

        <textarea id="resultPreview" class="preview-textarea" readonly=""></textarea>

        <button type="button" class="modal-btn btn-close-modal" onclick="closeSendModal()">關閉返回</button>
      </div>
    </div>
  </div>

  <script>
    let embeddedBase64 = '';

    // 監聽圖片選取，自動轉成 Base64
    document.getElementById('localImageInput').addEventListener('change', function(e) {
      const file = e.target.files[0];
      if (!file) return;

      const reader = new FileReader();
      reader.onload = function(evt) {
        embeddedBase64 = evt.target.result;
        const img = document.getElementById('bannerImage');
        img.src = embeddedBase64;
        img.style.display = 'block';
        document.getElementById('downloadReadyBox').style.display = 'block';
      };
      reader.readAsDataURL(file);
    });

    // 一鍵下載已永久內嵌 Base64 圖片的新 HTML 檔案
    function downloadPackedHtml() {
      if (!embeddedBase64) {
        alert('請先選取圖片！');
        return;
      }

      // 解析當前頁面，將 Base64 永久寫死進 img 標籤中
      const parser = new DOMParser();
      const newDoc = parser.parseFromString(document.documentElement.outerHTML, 'text/html');

      const targetImg = newDoc.getElementById('bannerImage');
      targetImg.setAttribute('src', embeddedBase64);
      targetImg.style.display = 'block';

      // 移除上傳工具方塊，讓匯出的成品乾淨純粹
      const uploader = newDoc.getElementById('imageUploaderBox');
      if (uploader) uploader.remove();

      const finalHtml = '<!DOCTYPE html>\n' + newDoc.documentElement.outerHTML;
      const blob = new Blob([finalHtml], { type: 'text/html;charset=utf-8' });
      const a = document.createElement('a');
      a.href = URL.createObjectURL(blob);
      a.download = '運動風潮_團服登記表(永久內嵌版).html';
      document.body.appendChild(a);
      a.click();
      document.body.removeChild(a);

      alert('🎉 恭喜！已下載「永久內嵌圖片版 HTML」！\n\n圖片已成功轉換為代碼內嵌在檔案內，以後傳送此檔案給任何人打開都不會破圖！');
    }

    // 安全將字串轉整數
    function cleanInt(v) {
      if (!v) return 0;
      v = String(v).trim();
      v = v.replace(/[\uff10-\uff19]/g, function(ch) {
        return String.fromCharCode(ch.charCodeAt(0) - 0xfee0);
      });
      v = v.replace(/\D/g, '');
      return parseInt(v, 10) || 0;
    }

    // 核心計算函式
    function calc() {
      var fSum = 0;
      var fInputs = document.querySelectorAll('.f-qty');
      for (var i = 0; i < fInputs.length; i++) {
        fSum += cleanInt(fInputs[i].value);
      }

      var mSum = 0;
      var mInputs = document.querySelectorAll('.m-qty');
      for (var j = 0; j < mInputs.length; j++) {
        mSum += cleanInt(mInputs[j].value);
      }

      var total = fSum + mSum;

      document.getElementById('femaleTotal1').value = fSum;
      document.getElementById('femaleTotal2').value = fSum;
      document.getElementById('maleTotal1').value = mSum;
      document.getElementById('maleTotal2').value = mSum;
      document.getElementById('grandTotal').value = total;

      updateSummaryContent();

      try {
        var cache = collectData();
        localStorage.setItem('polo_cache_v3', JSON.stringify(cache));
      } catch(e){}
    }

    function collectData() {
      var data = {
        name: document.getElementById('custName').value.trim(),
        phone: document.getElementById('custPhone').value.trim(),
        dept: document.getElementById('custDept').value.trim(),
        team: document.getElementById('custTeam').value.trim(),
        fSizes: {},
        mSizes: {}
      };

      document.querySelectorAll('.f-qty').forEach(function(inp) {
        var c = cleanInt(inp.value);
        if (c > 0) data.fSizes[inp.getAttribute('data-size')] = c;
      });

      document.querySelectorAll('.m-qty').forEach(function(inp) {
        var c = cleanInt(inp.value);
        if (c > 0) data.mSizes[inp.getAttribute('data-size')] = c;
      });

      return data;
    }

    function buildSummary() {
      var d = collectData();
      var text = "【運動風潮 - 團服登記審查單】\n";
      text += "姓名：" + (d.name || "未填") + "\n";
      text += "電話：" + (d.phone || "未填") + "\n";
      text += "團體/其他：" + (d.dept || "未填") + " / " + (d.team || "未填") + "\n";
      text += "-------------------------\n";

      var fArr = [];
      for (var k in d.fSizes) { fArr.push(k + ": " + d.fSizes[k] + "件"); }
      text += "👚 女款POLO：" + (fArr.length ? fArr.join(', ') : "0件") + " (小計 " + document.getElementById('femaleTotal1').value + " 件)\n";

      var mArr = [];
      for (var m in d.mSizes) { mArr.push(m + ": " + d.mSizes[m] + "件"); }
      text += "👕 男款POLO：" + (mArr.length ? mArr.join(', ') : "0件") + " (小計 " + document.getElementById('maleTotal1').value + " 件)\n";
      text += "=========================\n";
      text += "⭐ 總件數合計：" + document.getElementById('grandTotal').value + " 件\n";

      try {
        var hash = encodeURIComponent(JSON.stringify(d));
        var fullUrl = window.location.origin + window.location.pathname + '#' + hash;
        text += "\n🔗 點擊網址查看填好的完整圖表：\n" + fullUrl;
      } catch(e){}

      return text;
    }

    function updateSummaryContent() {
      var text = buildSummary();
      var preview = document.getElementById('resultPreview');
      if (preview) preview.value = text;

      var lineBtn = document.getElementById('lineDirectLink');
      if (lineBtn) {
        lineBtn.href = "https://line.me/R/msg/text/?" + encodeURIComponent(text);
      }
    }

    function openSendModal() {
      calc();
      document.getElementById('sendModal').style.display = 'flex';
    }
    function closeSendModal() {
      document.getElementById('sendModal').style.display = 'none';
    }

    function executeLineSend(e) {
      calc();
      var text = buildSummary();
      var lineUrl = "https://line.me/R/msg/text/?" + encodeURIComponent(text);
      window.location.href = lineUrl;
    }

    function copyResultText() {
      calc();
      var text = buildSummary();
      var textarea = document.getElementById('resultPreview');
      textarea.select();
      textarea.setSelectionRange(0, 99999);
      try {
        document.execCommand('copy');
        alert("✅ 訂單文字已複製！\n請直接切換到 LINE 貼上並傳送給我。");
      } catch(err) {
        prompt("請手動選取並複製以下文字：", text);
      }
    }

    document.addEventListener('input', function(e) {
      if (e.target && (e.target.classList.contains('qty-input') || e.target.classList.contains('underline-input'))) {
        calc();
      }
    });

    function restoreFromData(data) {
      if (!data) return;
      if (data.name) document.getElementById('custName').value = data.name;
      if (data.phone) document.getElementById('custPhone').value = data.phone;
      if (data.dept) document.getElementById('custDept').value = data.dept;
      if (data.team) document.getElementById('custTeam').value = data.team;

      if (data.fSizes) {
        document.querySelectorAll('.f-qty').forEach(function(inp) {
          var s = inp.getAttribute('data-size');
          if (data.fSizes[s] !== undefined) inp.value = data.fSizes[s];
        });
      }
      if (data.mSizes) {
        document.querySelectorAll('.m-qty').forEach(function(inp) {
          var s = inp.getAttribute('data-size');
          if (data.mSizes[s] !== undefined) inp.value = data.mSizes[s];
        });
      }
      calc();
    }

    (function init() {
      // 若已有內嵌 Base64 則直接顯示
      const bannerImg = document.getElementById('bannerImage');
      if (bannerImg && bannerImg.getAttribute('src') && bannerImg.getAttribute('src').startsWith('data:image')) {
        bannerImg.style.display = 'block';
        const uploader = document.getElementById('imageUploaderBox');
        if (uploader) uploader.style.display = 'none';
      }

      calc();
      if (window.location.hash && window.location.hash.length > 1) {
        try {
          var raw = decodeURIComponent(window.location.hash.substring(1));
          restoreFromData(JSON.parse(raw));
          return;
        } catch(e){}
      }
      try {
        var saved = localStorage.getItem('polo_cache_v3');
        if (saved) restoreFromData(JSON.parse(saved));
      } catch(e){}
    })();
  </script>

</body></html>
