---
layout: article
title:  "Tableau使用笔记04"
date:   2018-01-03 
categories: infovis
image:
  teaser: tableau-note.jpg
---
步骤 4：通过地理方式浏览您的数据

您已经生成了一个出色的视图，它允许您按产品查看 2014 年至 2017 年的销售额和利润。在查看南部的产品销售额和盈利能力之后，您决定寻找该区域的趋势或模式。

由于要查看地理数据（“区域”字段），因此您可以选择生成地图视图。地图视图非常适用于显示和分析这种信息。另外，它们简直太酷了！

对于此示例，Tableau 已经为“国家/地区”、“州/省/市/自治区”、“城市”和“邮政编码”字段分配了适当的地理角色。这是因为它认识到这些字段中的每个字段都包含地理数据。您可以开始工作，并立即创建您的地图视图。

Closed了解更多信息： 满足地理角色要求。
生成地图视图
重新开始一个新工作表。

在工作区的底部，单击“新建工作表”图标。



Tableau 将保留您以前的工作表并创建一个新工作表，以便您可以继续浏览您的数据而不会丢失您所做的工作。

在“数据”窗格中，双击“State”（州/省/市/自治区）并将其添加至“标记”卡上的“详细信息”。

哇！您有了地图视图。

单击图像可重播 


Closed了解更多信息：双击以添加地理区域字段。
因为 Tableau 已经知道州/省/市/自治区名称是地理数据，并且为“State”（州/省/市/自治区）维度分配了州/省/市/自治区地理角色，所以 Tableau 会自动创建一个地图视图。

数据源中 48 个州/省/市/自治区中的每一个都具有一个标记。（糟糕的是，阿拉斯加和夏威夷未包含在您的数据源中，所以它们被遗漏了）。

请注意，“国家/地区”字段也添加到了此视图中。之所以发生这种情况，是因为“Sample - Superstore”中的地理字段是分层结构的一部分。分层结构中的每个级别会添加为详细级别，如洋葱层。

此外，还会将“经度”和“纬度”字段添加到“列”和“行”功能区中。您可以将这些看作 X 和 Y 字段。无论何时想要创建地图视图，它们都是必不可少的，因为为数据中的每个位置都分配了横向值和纵向值。有时，“经度”和“纬度”字段由 Tableau 生成。平常，您可能必须手动将它们包括在您的数据中。您可以在学习资料库中查找资源以详细了解这方面的内容。

现在，拥有一个聚焦 48 个州/省/市/自治区的优秀地图是一回事，但是想要查看南部发生的情况又是另外一回事，记得吗？

将“Region”（区域）拖到“筛选器”功能区，然后仅向下筛选到“南部”。地图视图会放大到“南部”区域，并且每个州/省/市/自治区（共 11 个）都具有标记。

现在，您想要实际了解如何显示此区域的数据趋势，因此您开始将其他字段拖到“标记”卡：

将“Sales”（销售额）度量拖到“标记”卡的“颜色”上。

单击图像可重播 


此视图会自动更新为填充地图，并且会根据每个州/省/市/自治区的总销售额为每个州/省/市/自治区着色。

无论何时将包含正数（如销售额）的连续度量添加到“标记”卡上的“颜色”时，您的填充地图都是蓝色。为负值分配的颜色为橙色。

有时您可能不希望地图是蓝色。也许您喜欢绿色，或者您的数据不应该用蓝色来表示，如野火或交通堵塞。这只会令人感到困惑！

不用担心，就像以前那样，您可以更改调色板。

在“标记”卡上单击“颜色”，然后选择“编辑颜色”。

对于此示例，您想要知道销售业绩好的州/省/市/自治区以及销售业绩不好的州/省/市/自治区。

在“调色板”下拉列表中，选择“红色-绿色发散”并单击“确定”。这样，您应该可以快速查看业绩低和业绩高的州/省/市/自治区。

视图将更新为如下所示：



但是，稍等。刚才一切都变为红色了！发生了什么事？

数据是准确的，并且从技术上讲，您可以比较业绩低和业绩高的州/省/市/自治区，但这真的是整个故事吗？

这些州/省/市/自治区中某些州/省/市/自治区的销售额真的那么糟糕吗，或者佛罗里达州中是否就有更多人想买您的产品？或许您在显示为红色的州/省/市/自治区中有更小或更少的库存。或者也许显示为绿色的州/省/市/自治区中具有较高的人口密度，所以就会有更多的人买您的东西。

无论是哪种情况，您都休想向您的上司显示此视图，因为您不确信数据讲述的故事是否有用。

单击工具栏中的“撤消”图标  以恢复为那个合适的蓝色视图。

这里还有一个颜色问题。一切看起来都太好了 - 这也是个问题！

乍一看，佛罗里达州的业绩似乎最好。如果将光标悬停在其标记上，则会显示销售总额为 89,474 美元，例如，与南卡罗莱纳州相比，其销售额仅有 8,482 美元。然而，南部中是否有任何州/省/市/自治区已经盈利？

将“Profit”（利润）拖到“标记”卡的“颜色”上，以查看是否可以回答此问题。



现在，这还差不多！由于利润往往包括正值和负值，所有 Tableau 将自动选择橙色-蓝色发散调色板，以快速显示具有负利润的州/省/市/自治区和具有正利润的州/省/市/自治区。

现在清楚了，尽管田纳西州、北卡罗来纳州和佛罗里达州的销售额似乎还可以，甚至是很不错，但是它们具有负利润。但是原因是什么呢？您将在下一步中回答这个问题。

检查您的工作！注意操作中的“生成地图视图”的实际运行效果。