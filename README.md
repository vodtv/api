# MoonTV/LunaTV 配置编辑器（自用）
https://vodtv.github.io/api

--- 

##  MoonTV/LunaTV配置
订阅使用：复制下面链接  

👉 Base58编码订阅链接[精简版🎬源链接](https://raw.githubusercontent.com/vodtv/api/refs/heads/main/jin18.txt)    （推荐使用自己部署的代理）精简版禁18源

```bash
https://mconfig.viptv.work?config=0&encode=base58
```
```bash
https://raw.githubusercontent.com/vodtv/api/refs/heads/main/jin18.txt
```
👉 Base58编码订阅链接[精简版🎬+🔞源链接](https://https://mconfig.viptv.work?config=0&encode=base58) （推荐使用自己部署的代理）精简版剔除无搜索结果和污染搜索结果源                             
```bash
https://mconfig.viptv.work?config=0&encode=base58
```
```bash
https://raw.githubusercontent.com/vodtv/api/refs/heads/main/jingjian.txt
```

--- 

# 🌐 CORSAPI（API 代理 & JSON 订阅器）

> 基于 Cloudflare Workers 的 API 中转与 JSON 前缀替换工具，支持代理任意 API、自动添加中转、生成 Base58 订阅格式。一键部署即可拥有自己的中转 API 与订阅链接！

<details>
<summary>🚀 部署方法</summary>
  
#   
  
**部署代码：**  
- [精简版代码](https://raw.githubusercontent.com/vodtv/api/refs/heads/main/CORSAPI/jingjian_worker.js)  
- [禁18版代码](https://raw.githubusercontent.com/vodtv/api/refs/heads/main/CORSAPI/jin18_worker.js)

### 🧭 部署步骤
1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)  
2. 新建 **Workers & Pages → Worker**  
3. 将上述 `worker.js` 代码粘贴到编辑器中  
4. 保存并部署  

部署完成后，你就拥有了自己的 API 代理与订阅转换服务！

---   

</details>

<details>
<summary>🔗 使用示例</summary>
  
#  

```bash
假设你的 Worker 部署在：

https://api.example.workers.dev

### ① 代理任意 API  
https://api.example.workers.dev/?url=https://ikunzyapi.com/api.php/provide/vod

### ② 获取原始 JSON 配置  
https://api.example.workers.dev/?config=0

### ③ 获取API 代理的 JSON 配置  
https://api.example.workers.dev/?config=1

### ④ 获取API 代理的 Base58 编码订阅  
https://api.example.workers.dev/?config=1&encode=base58
```
---   
  
</details>

<details>
<summary>🛠️ 参数说明</summary>
  
# 
  
| 参数 | 说明 | 示例 |
|------|------|------|
| `url` | 代理任意 API 请求 | `?url=https://...` |
| `config=0` | 返回原始 JSON 配置 | `?config=0` |
| `config=1` | 返回使用api代理的 JSON 配置 | `?config=1` |
| `encode=base58` | 将 JSON 配置编码为 Base58 | `?config=1&encode=base58` |
| `(可选) prefix` | 手动指定 API 代理前缀，默认使用当前域名 | `?config=1&prefix=https://api.example.com/?url=` |

🧩 **前缀替换逻辑**  
- 若 JSON 中的 `api` 字段已包含旧前缀（`?url=`），系统会自动去除旧前缀并替换为新的代理前缀。  
- 可自定义代理路径，方便接入私有 API 或多 Worker 配置。
  
---   
  
</details>

<details>
<summary>📌 注意事项</summary>
  
# 
  
- ☁️ **Workers 免费额度：**  
  每日 10 万次请求，适合轻量部署与个人订阅使用。  

- 🔄 **API代理逻辑：**  
  自动替换 JSON 中的 `api` 字段前缀，保证所有接口都经过中转代理。  

- 💾 **Base58 编码：**  
  生成的 Base58 结果可直接导入支持订阅的客户端。  

---   
  
</details>


## 🆕 更新内容

- 📄 **Luna-TV配置编辑器**：专业的 JSON 配置文件可视化编辑器。  
- 🔍 **自动检测API状态**：每 1 小时检测一次 API 可用性，并记录最近 100 次测试报告。  
- 🧩 **源名称前添加图标**：源名称前添加图标，方便区分。  
- 🌐 **被墙资源自动中转**：为受限 API 提供 CF Worker 中转能力。  
  
---   

## 🧪 测试与示例

### ✅ 使用中转API测试
- 通过 CORSAPI 转发后，大幅提升视频源可用率。  
- 可“复活”原本无法访问的资源。  

### ⚙️ 精简版源更新
- 去除污染源与无搜索结果源（如 🎬虎牙、🔞丝袜、🔞色猫）。  
- 精简后共 **66 个可用源**，在中转代理下全部可访问。  
<details>
<summary>示例</summary>
<img width="1025" height="486" alt="61" src="https://github.com/user-attachments/assets/81c80108-7c03-4583-87ab-b7b57cdfd3bd" />
  
  
</details>

---   
  
# API 健康报告（每日自动检测API状态）

## API 状态（最近更新：2026-04-16 02:00 CST）

- 总 API 数量：77
- 成功 API 数量：68
- 失败 API 数量：9
- 平均可用率：0.0%
- 完美可用率（100%）：0 个
- 高可用率（80%-99%）：0 个
- 中等可用率（50%-79%）：0 个
- 低可用率（<50%）：77 个

<div style="font-size: 11px;">

<!-- API_TABLE_START -->
| 状态 | 资源名称 | 地址 | API | 搜索功能 | 成功次数 | 失败次数 | 成功率 | 最近7天趋势 |
|------|---------|-----|-----|---------|---------:|--------:|-------:|--------------|
| ✅ | 🎬-爱奇艺- | [Link](https://iqiyizyapi.com) | [Link](https://iqiyizyapi.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬360 资源 | [Link](https://360zy.com) | [Link](https://360zyzz.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬iKun资源 | [Link](https://ikunzy.com) | [Link](https://ikunzyapi.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬U酷影视 | [Link](https://www.ukuzy.com) | [Link](https://api.ukuapi88.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬优质资源 | [Link](https://1080zyk4.com) | [Link](https://api.yzzy-api.com/inc/apijson.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬光速资源 | [Link](https://api.guangsuapi.com) | [Link](https://api.guangsuapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬最大点播 | [Link](https://zuidazy.co) | [Link](https://zuidazy.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬最大资源 | [Link](https://zuida.xyz) | [Link](https://api.zuidapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬卧龙资源 | [Link](https://wolongzyw.com) | [Link](https://wolongzyw.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | 🎬如意资源 | [Link](https://www.ryzyw.com) | [Link](https://pz.168188.dpdns.org/?url=https://cj.rycjapi.com/api.php/provide/vod) | ❌ | 13 | 17 | 43.3% | ❌❌❌❌❌❌❌ |
| 🚨 | 🎬山海资源 | [Link](https://zy.sh0o.cn) | [Link](https://zy.sh0o.cn/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 🎬快车资源 | [Link](https://kuaichezy.com) | [Link](https://caiji.kuaichezy.org/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬新浪资源 | [Link](https://xinlangapi.com) | [Link](https://api.xinlangapi.com/xinlangapi.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬无尽影视 | [Link](https://wujinzy.com) | [Link](https://api.wujinapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬无尽资源 | [Link](https://wujinzy.com) | [Link](https://api.wujinapi.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬旺旺短剧 | [Link](https://wwzy.tv) | [Link](https://wwzy.tv/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬旺旺资源 | [Link](https://api.wwzy.tv) | [Link](https://api.wwzy.tv/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬暴风资源 | [Link](https://bfzy.tv) | [Link](https://bfzyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬极速资源 | [Link](https://jszyapi.com) | [Link](https://jszyapi.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬樱花资源 | [Link](https://yhzy.cc) | [Link](https://m3u8.apiyhzy.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬猫眼资源 | [Link](https://www.maoyanzy.com) | [Link](https://api.maoyanapi.top/api.php/provide/vod) | ✅ | 28 | 2 | 93.3% | ✅❌✅✅✅✅✅ |
| ✅ | 🎬电影天堂 | [Link](http://caiji.dyttzyapi.com) | [Link](http://caiji.dyttzyapi.com/api.php/provide/vod) | ❌ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | 🎬百度云zy | [Link](https://bdzy1.com) | [Link](https://pz.168188.dpdns.org/?url=https://api.apibdzy.com/api.php/provide/vod) | ❌ | 13 | 17 | 43.3% | ❌❌❌❌❌❌❌ |
| ✅ | 🎬红牛资源 | [Link](https://www.hongniuzy.com) | [Link](https://www.hongniuzy2.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬索尼资源 | [Link](https://suonizy.net) | [Link](https://suoniapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 🎬艾旦影视 | [Link](https://lovedan.net) | [Link](https://pz.168188.dpdns.org/?url=https://lovedan.net/api.php/provide/vod) | ❌ | 13 | 17 | 43.3% | ❌❌❌❌❌❌❌ |
| ✅ | 🎬茅台资源 | [Link](https://mtzy.me) | [Link](https://caiji.maotaizy.cc/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬虎牙资源 | [Link](https://www.huyaapi.com) | [Link](https://www.huyaapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬豆瓣资源 | [Link](https://dbzy.tv) | [Link](https://caiji.dbzy5.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | 🎬豪华资源 | [Link](https://www.haohuazy.com) | [Link](https://pz.168188.dpdns.org/?url=https://hhzyapi.com/api.php/provide/vod) | ❌ | 13 | 17 | 43.3% | ❌❌❌❌❌❌❌ |
| ✅ | 🎬速播资源 | [Link](https://www.subozy.com) | [Link](https://subocaiji.com/api.php/provide/vod) | ✅ | 28 | 2 | 93.3% | ✅❌✅✅✅✅✅ |
| ✅ | 🎬量子影视 | [Link](https://lzizy.net) | [Link](https://cj.lziapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬量子资源 | [Link](https://cj.lzcaiji.com) | [Link](https://cj.lzcaiji.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬金蝉影视 | [Link](https://zy.jinchancaiji.com) | [Link](https://zy.jinchancaiji.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬金鹰点播 | [Link](https://jinyingzy.com) | [Link](https://jinyingzy.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬闪电资源 | [Link](https://shandianzy.com) | [Link](https://xsd.sdzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬非凡资源 | [Link](https://cj.ffzyapi.com) | [Link](https://api.ffzyapi.com/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬飘零资源 | [Link](https://p2100.net) | [Link](https://p2100.net/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬魔都动漫 | [Link](https://caiji.moduapi.cc) | [Link](https://caiji.moduapi.cc/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬魔都资源 | [Link](https://www.moduzy.net) | [Link](https://www.mdzyapi.com/api.php/provide/vod) | ✅ | 27 | 3 | 90.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🎬鸭鸭资源 | [Link](https://yayazy3.com) | [Link](https://cj.yayazy.net/api.php/provide/vod) | ❌ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞 CK-资源 | [Link](https://ckzy.me) | [Link](https://ckzy.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞--AIvin- | [Link](http://lbapiby.com) | [Link](http://lbapiby.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞-大奶子- | [Link](https://apidanaizi.com) | [Link](https://apidanaizi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞-奥斯卡- | [Link](https://aosikazy.com) | [Link](https://aosikazy.com/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| 🚨 | 🔞-幸资源- | [Link](https://xzytv.com) | [Link](https://xzybb2.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 🔞-美少女- | [Link](https://www.msnii.com) | [Link](https://www.msnii.com/api/json.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞-老色逼- | [Link](https://apilsbzy1.com) | [Link](https://apilsbzy1.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞-黄AVZY | [Link](https://www.pgxdy.com) | [Link](https://www.pgxdy.com/api/json.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞155-资源 | [Link](https://155zy2.com) | [Link](https://155api.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 🔞91-精品- | [Link](https://91jpzyw.com) | [Link](https://91jpzyw.com/api.php/provide/vod) | ❌ | 0 | 30 | 0.0% | ❌❌❌❌❌❌❌ |
| ✅ | 🔞jkun资源 | [Link](https://jkunzyapi.com) | [Link](https://jkunzyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞souavZY | [Link](https://api.souavzyw.net) | [Link](https://api.souavzyw.net/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞丝袜资源 | [Link](https://siwazyw.tv) | [Link](https://siwazyw.tv/api.php/provide/vod) | 不匹配 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞乐播资源 | [Link](https://lbapi9.com) | [Link](https://lbapi9.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| 🚨 | 🔞优优资源 | [Link](https://www.yyzywcj.com) | [Link](https://www.yyzywcj.com/api.php/provide/vod) | ❌ | 14 | 16 | 46.7% | ❌❌❌❌❌❌❌ |
| ✅ | 🔞大地资源 | [Link](https://dadizy11.com) | [Link](https://dadiapi.com/feifei) | 不匹配 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞奶香资源 | [Link](https://Naixxzy.com) | [Link](https://Naixxzy.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞小鸡资源 | [Link](https://xiaojizy.live) | [Link](https://api.xiaojizy.live/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞杏吧资源 | [Link](https://xingba111.com) | [Link](https://xingba222.com/api.php/provide/vod) | 无结果 | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞桃花资源 | [Link](https://thzy8.me) | [Link](https://thzy1.me/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞森林资源 | [Link](https://slapibf.com) | [Link](https://beiyong.slapibf.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞滴滴资源 | [Link](https://didizy.com) | [Link](https://api.ddapi.cc/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞玉兔资源 | [Link](https://apiyutu.com) | [Link](https://apiyutu.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞番号资源 | [Link](http://fhapi9.com) | [Link](http://fhapi9.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞白嫖资源 | [Link](https://www.kxgav.com) | [Link](https://www.kxgav.com/api/json.php) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞百万资源 | [Link](https://api.bwzym3u8.com) | [Link](https://api.bwzyz.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞精品资源 | [Link](https://www.jingpinx.com) | [Link](https://www.jingpinx.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞细胞资源 | [Link](https://www.xxibaozyw.com) | [Link](https://www.xxibaozyw.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞色猫资源 | [Link](https://semaozy1.com) | [Link](https://caiji.semaozy.net/inc/apijson_vod.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞豆豆资源 | [Link](https://doudouzy.com) | [Link](https://api.douapi.cc/api.php/provide/vod) | ✅ | 18 | 12 | 60.0% | ✅✅❌✅✅✅✅ |
| 🚨 | 🔞辣椒资源 | [Link](https://apilj.com) | [Link](https://pz.168188.dpdns.org/?url=https://apilj.com/api.php/provide/vod) | ❌ | 12 | 18 | 40.0% | ❌❌❌❌❌❌❌ |
| ✅ | 🔞香蕉资源 | [Link](https://www.xiangjiaozyw.com) | [Link](https://www.xiangjiaozyw.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞鲨鱼资源 | [Link](https://shayuapi.com) | [Link](https://shayuapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞麻豆视频 | [Link](https://91md.me) | [Link](https://91md.me/api.php/provide/vod) | ✅ | 29 | 1 | 96.7% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞黄色仓库 | [Link](https://hsckzy.xyz) | [Link](https://hsckzy.xyz/api.php/provide/vod) | ✅ | 25 | 5 | 83.3% | ✅✅✅✅✅✅✅ |
| ✅ | 🔞黑料资源 | [Link](https://heiliaozy.cc) | [Link](https://www.heiliaozyapi.com/api.php/provide/vod) | ✅ | 30 | 0 | 100.0% | ✅✅✅✅✅✅✅ |
<!-- API_TABLE_END -->


