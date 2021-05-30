title: i18next
speaker: 杜甫
plugins:
    - echarts
    - mermaid

<slide class="bg-black-blue aligncenter" image="https://source.unsplash.com/C1HhAQrbykQ/ .dark">

# i18next {.text-landing.text-shadow}

By 杜甫 {.text-intro}

<slide class="bg-black-blue aligncenter">

# 多语言更新现状 {.text-landing.text-shadow}

<slide class="bg-black-blue aligncenter">

# 代码里直接写中文 {.text-landing.text-shadow}

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[代码里写中文] --> B{肉眼筛查代码里的中文}
    B -- 有TODO,FIXME等标位 --> C[平台上下载 Excel 模版, 手动录入数据]
    B -- 无标位 --> C
    C --> D[Excel 里的 key 回调到代码]
    C --> E[产品翻译 Excel]
    E --> F[平台上传 Excel]
    C --> F
    F --> G[多语言发布]
```

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[代码里写中文] --> B[每完成一个多语言文件 iot pick 提取文案到 zh json]
    B --> C[导出待筛选 Excel]
    C --> D[Excel 筛选]
    D --> E[产品翻译 Excel]
    E --> F[平台上传 Excel]
    D --> F
    F --> G[多语言发布]
```

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[代码里写中文] --> B[肉眼筛查代码里的中文]
    B --> C[zh json 新增 key]
    C --> D[key 回调到之前写的中文]
    D --> E[导出 Excel]
    E --> F[产品翻译 Excel]
    F --> G[平台上传 Excel]
    E --> G
    G --> H[多语言发布]
```

<slide class="bg-black-blue aligncenter">

# 代码里直接写key {.text-landing.text-shadow}

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[平台上配置多语言] --> B[多语言发布]
    B --> C[新增多语言同步到本地]
    C --> D[代码里写 key]
    D --> E[wiki 上手动记录本次需求修改, 新增的 key 的checklist]
    E --> F[产品翻译多语言 checklist]
    F --> G[预发发布需要手动新增修改 wiki 上的多语言 checklist]
```

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[同步预发多语言到本地] --> B[zh json 新增 key]
    B --> C[代码里写 key]
    C --> D[导出 Excel]
    D -->  E[产品翻译 Excel]
    E --> F[平台上传 Excel]
    D --> F
    F --> G[多语言发布]
```

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[平台上下载 Excel 模版, 手动录入数据] --> B[平台上传Excel]
    B --> C[多语言发布]
    C --> D{新增多语言同步到本地}
    D -- 是--> E[代码里写 key]
    A --> F[产品翻译 Excel]
    F --> C
```

<slide class="bg-black-blue aligncenter">

# 我认为的多语言更新最佳实践 {.text-landing.text-shadow}

<slide class="bg-white aligncenter">

```mermaid
graph TD
    A[同步预发多语言到本地] --> B{代码里写中文}
    B -- 是 --> C[i18n ally extract text to i18n messages]
    C --> D[i18next-parser]
    B -- 否 --> I[动态多语言, 组件多语言]
    I --> D
    D --> E[i18next-export 新增 key]
    E --> F[产品翻译 Excel]
    F --> G[平台上传 Excel]
    E --> G
    G --> H[多语言发布]
```
