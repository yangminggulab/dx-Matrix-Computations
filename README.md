# 矩阵计算前三章 · 东邪笔记

依据潘建瑜《矩阵计算讲义》（2025 年 2 月）的已有 LaTeX 整理；本次没有启动 OCR，也没有进行 PDF 转 LaTeX。
正文覆盖前三讲的全部 17 个节，保留定义、定理、引理、推论、性质及必要公式；证明与例题移除。已有作业的完整题干、解答和提示集中在 `作业.tex`。

## 内容范围

| 章 | 内容 | 原编号条目 | 全部整理条目 |
| --- | --- | ---: | ---: |
| 第一章 | 线性代数基础：空间、矩阵与投影、范数、标准型、特殊矩阵、Kronecker 积 | 87 | 97 |
| 第二章 | 线性方程组直接方法：LU、特殊结构、扰动与误差分析、解的改进 | 25 | 43 |
| 第三章 | 线性最小二乘：矩阵变换、QR、SVD、求解、推广与应用 | 25 | 38 |
| 合计 | 17 个节 | 137 | 178 |

教材章标题为“讲”，本笔记按“章”排版。第四讲非对称特征值问题仅出现在全书结构图中，本次未整理其正文。
正文的各环境使用数理统计模板的自动编号；教材原编号及页文件保留在源码注释、`原文条目索引.md` 与 `条目清单.json` 中。
原文有个别公式笔误或隐含条件，整理时作了明确修正，见 [校勘记录](校勘记录.md)。原始教材与作业文件均未改动。

## 文件组织与模板

```text
矩阵计算-ElegantBook/
├── main.tex                 # 总入口，所有引用使用相对路径
├── 第一章.tex               # 开头直接写入功能结构树状图
├── 第二章.tex
├── 第三章.tex
├── 作业.tex                 # 按教材章分组；每次作业一个 section
├── elegantbook.cls          # 数理统计模板原件
├── reference.bib
├── images/cover.png         # Manim 高维球堆积素材
├── images/logo-blue.png
├── 矩阵计算前三章.pdf        # 33 页成品
├── build.sh
├── 原文条目索引.md
├── 条目清单.json
├── 原文校验清单.json
├── 校勘记录.md
├── 校验记录.md
└── ElegantBook-LICENSE
```

`elegantbook.cls` 直接复制自数理统计笔记，未修改。定义为绿色框，定理、引理、推论为橙色框，性质为蓝色框，作业提示使用紫色 `dxtips`。标题、背景、边框、自动编号与分页方式沿用原模板。
封面作者为“东邪”，座右铭沿用数理统计；保持上方图片、橙色横带、左侧书名与信息、右侧标志、底部座右铭的布局。图片区固定画布留白，原图按比例显示。

## 功能结构图的出处

结构图直接写在 `第一章.tex` 的开头，使用数理统计同款 `dirtree` 环境。按研究对象、问题、工具与联系，归纳为基础工具及求解线性约束、拟合数据、揭示谱与低秩结构三类功能，再对应潘建瑜讲义。

参考 [Cornell Charles Van Loan，CS 6210（2010）教学大纲](https://www.cs.cornell.edu/courses/cs6210/2010fa/)，其教材为 Golub 与 Van Loan 的 *Matrix Computations*；另参照 [Cornell Austin Benson，CS 6210（2020）课程说明](https://www.cs.cornell.edu/courses/cs6210/2020fa/)。
上述功能分组及本教材对应关系由本笔记归纳。课程大纲还包括稀疏迭代法、对称特征值问题、矩阵函数等，本册没有系统覆盖这些方向。

## 作业

现有第一章作业共九题，第九题为选做。`第一章作业.tex` 和日期作业目录是同一次作业的两个入口，合并时只计一次。
题干采用 `homework`，解答采用 `solution`，提示采用 `dxtips`。九道原题、九份解答与九份 tip 均保留，补录指定教材页码、原题提示及逐题知识点表。
同章后续作业在 `作业.tex` 中追加一个 `section`；进入教材下一章后，再新建 `chapter*` 分组并重置作业节计数。

## 编译与同步

使用包含 XeLaTeX、latexmk、Biber、Fandol 字体的 TeX Live 或 MacTeX：

```bash
bash build.sh
```

脚本在系统临时目录编译，仅将命名 PDF 放回项目，自动清理编译副产物。也可直接用 XeLaTeX 编译 `main.tex`。
已将主文件打开在 Codex 编辑器；内置独立文档编译器没有带入此工程的图片和自定义类，完整工程验收使用本机 XeLaTeX。

公开仓库：[yangminggulab/dx-Matrix-Computations](https://github.com/yangminggulab/dx-Matrix-Computations)。SSH 远端为 `git@github.com:yangminggulab/dx-Matrix-Computations.git`。
仓库包含三章源码、作业、模板、图片、命名 PDF 和说明。下载整个仓库 ZIP 上传到 Overleaf 后，主文档选 `main.tex`、编译器选 XeLaTeX；无需本机绝对路径或外部素材目录。
本次确认的是 GitHub 远端同步；没有创建或更新实际 Overleaf 项目。

原文来源：课程目录 `教材转换成果/矩阵计算讲义/LaTeX源码/章节/` 下前三讲的 118 个 `pages/*.tex`。
模板许可对应 `elegantbook.cls`；教材内容与原素材的权利归各自权利人。
