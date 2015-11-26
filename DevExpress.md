# DevExpress 常用设置

## 关于主题

1.	如果想要自定义主题：添加 DefaultLookAndFeel 控件，设置LookAndFeel中的Style 为除 Skin 外的其它值。如果设置为 Skin，则使用 SkinName 来指定 Skin

1.	如果使用Skin 则设置需要DefaultLookAndFeel.LookAndFeel.SkinName设置中的Style，并且调用
	``` c#
    	SkinManager.EnableFormSkins();
    ```
1. 如果想要更多的控件，则引用'DevExpress.BonusSkins'，并调用
	``` C#
    	BonusSkins.Register();
    ```
1. 动态设置主题
	``` c#
    	UserLookAndFeel.Default.SetSkinStyle(skinName);
    ```
1. 	查找当前可用Style
	``` c#
    	SkinManager.Default.Skins
	```

1. 设置新的主题可以使用skin Editor (通过 VS 中的 DevExpress 菜单打开)
	1. 在 Skin Editor 中导入 'DevExpress.BonusSkins.15.1.dll ' 或 'DevExpress.Utils'。[相关帮助](https://documentation.devexpress.com/#SkinEditor/CustomDocument2546)
	2. 以导入的 skin 作为模板创建新的 skin 然后编译为 Dll
	3. 在代码中引用Dll，并进行调用 （启动窗口的话在其它线程中调用，所以需要使用其它方法进行调用  ）
	``` C#
		Assembly asm = typeof(DevExpress.UserSkins.SkinProject1).Assembly;
    	DevExpress.Skins.SkinManager.Default.RegisterAssembly(asm);
    ```
    4. 帮助手册 https://documentation.devexpress.com/#SkinEditor/CustomDocument2547
    5. 帮助视频 https://community.devexpress.com/blogs/the_final_cut/archive/2008/09/16/creating-custom-skins.aspx

1. Skin(https://documentation.devexpress.com/#WindowsForms/CustomDocument2399)

2. LookAndFree(https://documentation.devexpress.com/#WindowsForms/CustomDocument2397)

3. 与主题相关的几个回答
	> https://www.devexpress.com/Support/Center/Question/Details/A2952
	> https://www.devexpress.com/Support/Center/Question/Details/A488

## 其它

1. 填充菜单框(或工具栏)最后空间：
	> 添加 BarStaticItem 去掉文字，并将 AutoSize 设置为 Spring

1. [DXperience WinForms12.2帮助文档](http://www.evget.com/article/2013/1/16/18440.html)