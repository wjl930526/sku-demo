# skuDemo

> 项目描述
> 商品详情，规格选择路径处理
# skuDemo

> 项目描述
>
> 1. 背景及业务介绍：商品详情，规格选择路径处理
> 2. 业务覆盖范围&应用范围：适用于所有规格选择

## 项目npm命令

- `npm run dev` 项目开发启动Demo命令
- `npm run build` 项目工具打包命令


## 目录结构

```
.
├── lib                                   # 公用包文件
│   ├── sku.js                            # 包引用入口
├── public                                # 示例文件入口
│   ├── favicon.ico                       # htmlIcon
│   ├── index.html                        # html入口
├── src                                   # 项目Demo
│   ├── components                        # 公共文件目录
│   │   ├── index.js                      # sku计算代码
│   ├── App.js                            # demo核心代码
│   ├── App.css                           # demo样式文件
│   ├── index.js                          # demo入口
│   ├── index.css                         # 统一样式入口
│   ├── logo.svg                          # icon
├── postcss.config.js                    
├── package.json                      
└── README.md      
```


1. 品类固定，只有颜色和尺寸，不可扩展
2. 原有商品格式中中文拼接为key，选择属性后进行匹配时比较麻烦
3. 选完所有品类的属性，匹配到商品后才知道这个商品是否有库存，而不能在提前知道该属性是否可点击


1. 将所有品类的所有属性整合
2. 拍平属性
3. 每个属性生成一个质数，对应这个属性
4. 根据品类，生成一个对应属性的质数的数组
5. 使用笛卡尔积计算sku
6. 筛选出可选的(有库存的)sku
7. 初始化展示内容
8. 获取当前可选属性