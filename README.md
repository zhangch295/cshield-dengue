# 🛡️ cshield-dengue

**长沙市登革热风险防控平台**  
*Changsha Shield against Dengue – Risk Prevention & Control Platform*

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit 1.58.0](https://img.shields.io/badge/Streamlit-1.58.0-red.svg)](https://streamlit.io)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

`cshield-dengue` 是一款面向**长沙市**的登革热本地化风险防控工具。它以小区、单位或任意地址为圆心，自动划定**核心区**（0–100m）和**警戒区**（100–300m），并基于高德地图 POI 数据，快速生成入户排查清单、蚊媒监测点清单、重点场所处置清单等，辅助公共卫生工作人员开展精准防控。

---

## 📌 主要功能

- **精准定位**：支持省市、区县（市）、街道、小区名称四级地址输入，强制区县校验，避免同名地址跨区误定位。
- **双半径防控圈**：
  - **核心区**（默认 100m）：入户排查、病例搜索、健康宣教、积水容器清理。
  - **警戒区**（核心区外扩 200m）：蚊媒孳生地调查、诱蚊诱卵器监测、环境消杀。
- **自定义不规则边界**：在地图上可分别将核心区/警戒区拖拽为不规则多边形，贴合实际地形或小区边界。
- **POI 智能分类**：自动识别学校、农贸市场、工地、公园、医院、酒店、居民小区等**重点场所**，并给出针对性处置建议。
- **多维度清单导出**：
  - 核心区入户排查清单（含楼栋线索）
  - 警戒区蚊媒监测点清单
  - 重点场所处置清单
  - 完整 POI 清单（Excel）
- **地图截图下载**：一键导出当前防控圈及 POI 分布图，用于报告或存档。
- **多核心区管理**：支持在地图上新增额外核心区（如病例工作单位、活动场所），独立调整半径与不规则边界。
- **卫星图/路况图切换**：内置高德标准图、卫星图、卫星注记、路况图，辅助现场勘察。

---

## 🗺️ 技术栈

| 类别       | 技术                                      |
|-----------|-------------------------------------------|
| 前端       | Streamlit + 自定义 Leaflet 组件 (HTML/JS) |
| 地图服务   | 高德地图 Web API (地理编码/逆地理/POI/静态图) |
| 数据处理   | Pandas, NumPy                             |
| 图像处理   | Pillow                                     |
| Excel 导出 | openpyxl                                   |
| 其他       | Requests, re, math, pathlib                |
