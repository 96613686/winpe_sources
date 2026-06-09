# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::ValidatePageControls

- ea: `0x43e0`
- end: `0x447d`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::ValidatePageControls`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3910`

## callees

- `0x43e0`

## pseudocode

```c

```

## disassembly

```asm
0x43e0  ldarg.0
0x43e1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::txtUrl
0x43e6  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x43eb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x43f0  ldc.i4.s 0x7B
0x43f2  ble.s    loc_4412
0x43f4  ldarg.0
0x43f5  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::txtUrl
0x43fa  ldarg.0
0x43fb  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::txtUrl
0x4400  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x4405  ldc.i4.0
0x4406  ldc.i4.s 0x7B
0x4408  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x440d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x4412  ldarg.0
0x4413  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::newPageTitle
0x4418  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x441d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4422  ldc.i4.s 0x64
0x4424  ble.s    loc_4444
0x4426  ldarg.0
0x4427  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::newPageTitle
0x442c  ldarg.0
0x442d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::newPageTitle
0x4432  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x4437  ldc.i4.0
0x4438  ldc.i4.s 0x64
0x443a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x443f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x4444  ldarg.0
0x4445  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navTitleText
0x444a  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x444f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4454  ldc.i4.s 0x19
0x4456  ble.s    loc_4476
0x4458  ldarg.0
0x4459  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navTitleText
0x445e  ldarg.0
0x445f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navTitleText
0x4464  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x4469  ldc.i4.0
0x446a  ldc.i4.s 0x19
0x446c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4471  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x4476  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ValidateFormDigest()
0x447b  pop
0x447c  ret
```
