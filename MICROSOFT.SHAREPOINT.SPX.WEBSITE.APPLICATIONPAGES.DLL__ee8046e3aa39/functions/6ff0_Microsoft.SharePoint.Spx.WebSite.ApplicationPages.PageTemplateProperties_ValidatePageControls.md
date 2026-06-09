# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::ValidatePageControls

- ea: `0x6ff0`
- end: `0x70a3`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::ValidatePageControls`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6be0`

## callees

- `0x6b90`
- `0x6ff0`

## pseudocode

```c

```

## disassembly

```asm
0x6ff0  ldarg.0
0x6ff1  ldfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::isSaveMode
0x6ff6  brfalse.s loc_7032
0x6ff8  ldarg.0
0x6ff9  ldarg.0
0x6ffa  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templFilenameBox
0x6fff  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x7004  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7009  ldc.i4.s 0x7B
0x700b  bgt.s    loc_701A
0x700d  ldarg.0
0x700e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templFilenameBox
0x7013  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x7018  br.s     loc_702D
0x701a  ldarg.0
0x701b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templFilenameBox
0x7020  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x7025  ldc.i4.0
0x7026  ldc.i4.s 0x7B
0x7028  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x702d  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::set_FileName(string value)
0x7032  ldarg.0
0x7033  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templTitleBox
0x7038  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x703d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7042  ldc.i4.s 0x64
0x7044  ble.s    loc_7064
0x7046  ldarg.0
0x7047  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templTitleBox
0x704c  ldarg.0
0x704d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templTitleBox
0x7052  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x7057  ldc.i4.0
0x7058  ldc.i4.s 0x64
0x705a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x705f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x7064  ldarg.0
0x7065  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::tempDescArea
0x706a  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x706f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7074  ldc.i4   0xFA
0x7079  ble.s    loc_709C
0x707b  ldarg.0
0x707c  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::tempDescArea
0x7081  ldarg.0
0x7082  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::tempDescArea
0x7087  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x708c  ldc.i4.0
0x708d  ldc.i4   0xFA
0x7092  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7097  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x709c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ValidateFormDigest()
0x70a1  pop
0x70a2  ret
```
