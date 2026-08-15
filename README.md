# 火箭云观测站 · GitHub Pages 部署

纯静态单文件网站，通过 GitHub Pages 免费托管，零积分消耗。

## 数据来源

本网站数据来自另一个 GitHub 仓库（已由 GitHub Actions 每 30 分钟自动抓取）：

```
https://uwuyou.github.io/huojianyun-data/data
```

- `prediction.json` — 未来发射预测
- `history.json` — 历史发射归档
- `status.json` — 同步状态

## 部署步骤

1. 在 GitHub 新建一个**公开**仓库，例如 `huojianyun`
2. 把本目录所有文件 push 上去：
   ```bash
   git init
   git add .
   git commit -m "init"
   git branch -M main
   git remote add origin https://github.com/你的用户名/huojianyun.git
   git push -u origin main
   ```
3. 进入仓库 **Settings → Pages**，`Source` 选择 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`，保存
4. 等待 1-2 分钟，网站即可通过 `https://你的用户名.github.io/huojianyun/` 访问

## 注意事项

- 公开仓库的 GitHub Actions 与 GitHub Pages **完全免费**、无限流量
- 若数据仓库名或用户名不同，请修改 `index.html` 中第 3200 行的 `DATA_BASE_URL`
- 数据仓库保持公开，GitHub Actions 才有无限分钟额度
