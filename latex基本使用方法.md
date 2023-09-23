# latex基本操作
## 注释
**使用 % 可以进行行注释**


## 文章开头使用
**\documentclass{article}**

## 中文文档使用固定格式
**\documentclass[UTF8]{ctexart}**

因为文档要使用中文, 需要ctexart的文档类型

## 前言部分（作者、写作日期、文章标题）

+ **\title{文章的标题名}**

+ **\author{作者名称}**
  
+ **\date{\today}** 文章写作的日期，\today 表示会自动生成当天的日期

⭐⭐⭐ 如果要想在正文中添加上面的信息，需要在正文中加入命令行
**\maketitle**


## 在文章中添加图片
### ① 在文档中添加图片，需要先在前言中引用graphicx这个包
\usepackage{graphicx}

## 正文开始
使用关键语句
**\begin{document}
\end{doucument}**


\begin{document}
% begin和end之间的内容是正文


%要显示前言部分添加的那些信息，还需要在文档的正文区添加一个\maketitle命令，

%-----------------------------------------------------
% 文章的章和节
% 比chapter还要大的是part,通常用来表示书籍中的第几部
\part{part通常表示书籍的第几部}

% \chapter{}命令表示第几章
% \chapter{chapter表示第几章}
% ⭐chapter和part适用于\documentclass[UTF8]{ctexbook}



% 开启新的章节，使用\section{}命令
\section{这是一个章节}
我们可以在章节下面添加一些内容

% 在章节下创建一个子章节，或者二级章节，使用\subsection{}命令
\subsection{这是一个子章节}
子章节下面的内容
% 三级章节，使用\subsubsection{}命令
\subsubsection{这是一个三级章节}
三级章节下面的内容


%-----------------------------------------------------
% latex中最基础的格式化命令

% 加粗文字，使用 \textbf{}, 需要加粗的文字直接写在花括号中，bf是bold font的缩写
\textbf{这里表示加粗的文字}

% 斜体，使用 \textit{}, it代表italic (斜体)
\textit{这里表示斜体文字}

% 下划线, 使用 \underline{}
\underline{这里表示下划线文字}

% 在文章中生成一个新的段落，可以输入两个换行符来完成，单独一个换行符只会生成一个空格
这是我写的第一篇文章，我正在使用换行命令，单独一个换行符只会生成一个空格，比如
只输入一个换行符的效果。

输入两个换行符的效果。
%-----------------------------------------------------



% 图片
% 在文档中添加图片，需要先在前言中引用graphicx这个包
% \usepackage{graphicx}
% 随后在正文中使用\includegraphics{}命令在当前位置添加一张图片
% \includegraphics{head}
% 后面花括号的head是图片文件的名字，在名字中可以直接省略掉后面png的扩展名部分
% \includegraphics{图片文件名.jpg}
% 如果直接编译文档尺寸过大，甚至超出页面宽度
% 给上面命令添加可选参数
\includegraphics[width=0.5\textwidth]{图片文件名.jpg}
% \textwidth 代表当前文本区域的宽度

% 给图片添加标题，可以先将图片嵌套在一个 figure 环境中，随后
% 通过函数\caption{}命令指定图片的标题
% 同时可以通过\centering命令将图片居中显示
\begin{figure}

    \centering  % 图片居中显示
    \includegraphics[width=0.8\textwidth]{图片文件名2.jpg}
    \caption{这是图片的标题}

\end{figure}


% 列表
% 要先切换到列表环境，就是begin和end
% 无序列表 使用itemize环境，列表中的每一个元素都要以 \item 开头
\begin{itemize}
    \item 无序列表项1
    \item 无序列表项2
    \item 无序列表项3
\end{itemize}
% 有序列表，使用enumerate环境
\begin{enumerate}
    \item 有序列表1
    \item 有序列表2
    \item 有序列表3
\end{enumerate}


% 数学公式
% latex允许在段落内直接添加公式，它被称作行内公式(inline equation)
% 行内公式需要写在两个美元符号中间，$……$
爱因斯坦在1905年发现的质能守衡方程为: $E=mc^2$
% 如果希望将公式单独写在一行，则可以使用equation环境
\begin{equation}
    E=mc^2
\end{equation}

% 简写  \[……\]
\[
    E=mc^2
\]



% 表格
% 使用tabbular环境在当前位置创建一个表格
% tabular环境需要传入一个参数来定义表格的形式
\begin{tabular}{ c c c }
    %  c c c 代表表格有三列,其中每一列居中对齐
    % c(centering): 居中对齐
    % l 左对齐
    % r 右对齐
    % ⭐⭐⭐表格中每一列数据需要以&符号隔开,表格每一行都需要以\\分割
    单元格1 & 单元格2 & 单元格3 \\
    单元格4 & 单元格5 & 单元格6 \\
    单元格7 & 单元格8 & 单元格9 \\
\end{tabular}

% 可以在ccc中添加竖线，为表格添加竖直的边框
\begin{tabular}{ |c|c|c| }
    单元格1 & 单元格2 & 单元格3 \\
    单元格4 & 单元格5 & 单元格6 \\
    单元格7 & 单元格8 & 单元格9 \\
\end{tabular}


% 水平方向的边框需要通过\hline命令添加
\begin{tabular}{ |c|c|c| }
    \hline
    单元格1 & 单元格2 & 单元格3 \\
    \hline
    单元格4 & 单元格5 & 单元格6 \\
    \hline
    单元格7 & 单元格8 & 单元格9 \\
    \hline
\end{tabular}

% 添加两次\hline命令来实现添加双横线的效果
\begin{tabular}{ |c|c|c| }
    \hline
    单元格1 & 单元格2 & 单元格3 \\
    \hline\hline
    单元格4 & 单元格5 & 单元格6 \\
    \hline
    单元格7 & 单元格8 & 单元格9 \\
    \hline
\end{tabular}

% 如果需要单独制定每一列的宽度，将c改为p，并在后面的花括号里面输入列宽
% p:paragraph
\begin{tabular}{ |p{2cm}|c|c| }
    单元格1 & 单元格2 & 单元格3 \\
    单元格4 & 单元格5 & 单元格6 \\
    单元格7 & 单元格8 & 单元格9 \\
\end{tabular}


% 给表格添加表题，可以先将整个表格放在一个table环境里面
% 然后通过\caption{}命令指定表格的标题
% 并通过\center命令将表格居中显示
\begin{table}
    \center
    \begin{tabular}{ |c|c|c| }
        \hline
        单元格1 & 单元格2 & 单元格3 \\
        \hline
        单元格4 & 单元格5 & 单元格6 \\
        \hline
        单元格7 & 单元格8 & 单元格9 \\
        \hline
    \end{tabular}
    \caption[short]{这里是表格的标题}
\end{table}

% ⭐⭐⭐可能是因为论文中表格都应该有名字，所以顺序可能反了

\section{这是第二个章节}s
第二章节下面的内容

latex中所有的命令都已反斜杠开头,后面跟一个花括号,表示命令的参数.

例如: doucumentclass, 指定文档类型, 最广泛使用的文档类型有article表示普通的文章, 还有book, report……
beamer表示创建一个幻灯片格式的文档

因为文档要使用中文, 需要ctexart的文档类型


\end{document}