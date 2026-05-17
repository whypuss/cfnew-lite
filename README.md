# CFnew Lite

> 基於 [byJoey/cfnew](https://github.com/byJoey/cfnew) 精簡化的 Cloudflare Worker 訂閱節點生成器

## 與原版差異

- 移除了 -1ms 節點備注 bug（getIndexedName 計數器問題）
- 修復域名節點被錯誤編號的問題（域名不再添加 -01/-02 後綴）
- 基於 byJoey/cfnew main 分支（commit 578b96e+）

## 部署

### Pages 部署

1. 下載 [Pages.zip](https://github.com/whypuss/cfnew-lite/releases/latest/download/Pages.zip)
2. 登入 [Cloudflare Dashboard](https://dash.cloudflare.com/)
3. Workers 和 Pages → 建立 Pages 項目 → 上傳 zip
4. 設定兼容日期：`2026-01-20`

## 節點修復說明

舊版（8f2f9b6）在以下 commit 被修復：

```
578b96e 修复yxurl无xhttp节点并优化节点编号代码（域名和yxurl不编号）
```

修復內容：移除 `getIndexedName`（對所有節點強制編號），替換為 `createNodeNamer`（域名跳過編號）。

---
原作者 [@byJoey](https://github.com/byJoey/cfnew)
