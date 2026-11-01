# 英语学习合集

一个入口，多套分开学。首页是索引，每套各自一个文件夹、一个页面、一套本地存储键。

访问：https://youanzhan25-debug.github.io/english-hub/

## 现有套数

| 序号 | 名称 | 路径 | 规模 | 本地存储键 |
|---|---|---|---|---|
| 01 | TED 精读站 · Teach girls bravery, not perfection | `ted/` | 97 句 · 149 生词 · 132 句型 | `p2t_*` |
| 02 | 阿里巴巴国际站 · 类目英语 | `alibaba/` | 38 一级 · 408 单元 · 3346 条 | `aliexpress_cat_learn_v1` |

## 再加一套（三步）

1. 新建文件夹，把单文件页面放成 `<slug>/index.html`；
2. 确认它的本地存储键与现有键**不重名**（重名就用前缀改名，如 `new_*`）；
3. 在根目录 `index.html` 的 `DECKS` 数组里加一条：`tag / name / sub / meta / href / accent / total / unit / read()`。

`read()` 返回 `{done, total, note}`，首页据此画进度条；读不到数据就返回 0，不会报错。

## 隔离说明

- 内容隔离：每套是独立页面，词条不混。
- 数据隔离：同一域名下 localStorage 共享，靠**键前缀**区分；两套之间不读写对方键。
- 删除某一套只需删文件夹与 `DECKS` 里那一行，其他套不受影响。
