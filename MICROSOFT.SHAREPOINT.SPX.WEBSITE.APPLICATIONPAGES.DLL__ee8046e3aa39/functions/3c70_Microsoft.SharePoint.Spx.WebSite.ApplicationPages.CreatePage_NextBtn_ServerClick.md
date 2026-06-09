# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::NextBtn_ServerClick

- ea: `0x3c70`
- end: `0x3daf`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::NextBtn_ServerClick`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3c70`

## string_xrefs

- `0x3cf8`: `TemplateGallery`
- `0x3c76`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x3c70  ldarg.0
0x3c71  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x3c76  ldstr    aTemplate// "Template"
0x3c7b  ldarg.0
0x3c7c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentPageType
0x3c81  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3c86  callvirt instance void [System.Web]System.Web.UI.StateBag::set_Item(string, object)
0x3c8b  ldarg.0
0x3c8c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::pagePropDiv
0x3c91  ldc.i4.1
0x3c92  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3c97  ldarg.0
0x3c98  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::pageTempDiv
0x3c9d  ldc.i4.0
0x3c9e  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3ca3  ldarg.0
0x3ca4  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::btnSubmit
0x3ca9  ldarg.0
0x3caa  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::nextBtn
0x3caf  ldc.i4.1
0x3cb0  dup
0x3cb1  stloc.s  5
0x3cb3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x3cb8  ldloc.s  5
0x3cba  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3cbf  ldarg.0
0x3cc0  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::nextBtn
0x3cc5  ldarg.0
0x3cc6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::prevBtn
0x3ccb  ldarg.0
0x3ccc  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::btnSubmit
0x3cd1  ldc.i4.0
0x3cd2  dup
0x3cd3  stloc.s  6
0x3cd5  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x3cda  ldloc.s  6
0x3cdc  dup
0x3cdd  stloc.s  7
0x3cdf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x3ce4  ldloc.s  7
0x3ce6  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3ceb  ldarg.0
0x3cec  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentPageType
0x3cf1  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3cf6  stloc.0
0x3cf7  ldloc.0
0x3cf8  ldstr    aTemplategaller// "TemplateGallery"
0x3cfd  ldc.i4.5
0x3cfe  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3d03  brfalse  loc_3DAE
0x3d08  ldarg.0
0x3d09  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x3d0e  ldloc.0
0x3d0f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFile(string)
0x3d14  stloc.1
0x3d15  ldloc.1
0x3d16  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x3d1b  ldstr    aMswhHeaderenab// "mswh_HeaderEnabled"
0x3d20  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3d25  isinst   [mscorlib]System.String
0x3d2a  stloc.2
0x3d2b  ldloc.1
0x3d2c  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x3d31  ldstr    aMswhFooterenab// "mswh_FooterEnabled"
0x3d36  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3d3b  isinst   [mscorlib]System.String
0x3d40  stloc.3
0x3d41  ldloc.1
0x3d42  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x3d47  ldstr    aMswhNavenabled// "mswh_NavEnabled"
0x3d4c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3d51  isinst   [mscorlib]System.String
0x3d56  stloc.s  4
0x3d58  ldarg.0
0x3d59  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::headerCheck
0x3d5e  ldloc.2
0x3d5f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d64  brtrue.s loc_3D6E
0x3d66  ldloc.2
0x3d67  call     bool [mscorlib]System.Boolean::Parse(string)
0x3d6c  br.s     loc_3D6F
0x3d6e  ldc.i4.1
0x3d6f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x3d74  ldarg.0
0x3d75  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::footerCheck
0x3d7a  ldloc.3
0x3d7b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d80  brtrue.s loc_3D8A
0x3d82  ldloc.3
0x3d83  call     bool [mscorlib]System.Boolean::Parse(string)
0x3d88  br.s     loc_3D8B
0x3d8a  ldc.i4.1
0x3d8b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x3d90  ldarg.0
0x3d91  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navigationCheck
0x3d96  ldloc.s  4
0x3d98  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d9d  brtrue.s loc_3DA8
0x3d9f  ldloc.s  4
0x3da1  call     bool [mscorlib]System.Boolean::Parse(string)
0x3da6  br.s     loc_3DA9
0x3da8  ldc.i4.1
0x3da9  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x3dae  ret
```
