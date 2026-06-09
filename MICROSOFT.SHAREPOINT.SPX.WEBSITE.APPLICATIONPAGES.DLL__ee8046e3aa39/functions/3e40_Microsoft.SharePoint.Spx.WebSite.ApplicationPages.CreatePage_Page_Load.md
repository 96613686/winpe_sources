# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::Page_Load

- ea: `0x3e40`
- end: `0x3f97`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::Page_Load`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3e40`
- `0x3fa0`
- `0x42d0`

## string_xrefs

- `0x3ed7`: `Template`
- `0x3e40`: `SiteDesigner_CreatePageAspxPageLoad`

## pseudocode

```c

```

## disassembly

```asm
0x3e40  ldstr    aSitedesignerCr// "SiteDesigner_CreatePageAspxPageLoad"
0x3e45  ldnull
0x3e46  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x3e4b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::get_Culture()
0x3e50  stloc.0
0x3e51  ldarg.0
0x3e52  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::btnCancel
0x3e57  ldstr    aCancel// "Cancel"
0x3e5c  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x3e61  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x3e66  ldarg.0
0x3e67  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::btnSubmit
0x3e6c  ldstr    aFinish// "Finish"
0x3e71  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x3e76  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x3e7b  ldarg.0
0x3e7c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::prevBtn
0x3e81  ldstr    aBackanglebkt// "BackAngleBkt"
0x3e86  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x3e8b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x3e90  ldarg.0
0x3e91  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::nextBtn
0x3e96  ldstr    aNextanglebkt// "NextAngleBkt"
0x3e9b  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x3ea0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x3ea5  ldarg.0
0x3ea6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x3eab  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x3eb0  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x3eb5  ldarg.0
0x3eb6  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x3ebb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::EnsureAuthentication(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x3ec0  ldarg.0
0x3ec1  ldarg.0
0x3ec2  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x3ec7  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x3ecc  stfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileManager
0x3ed1  ldarg.0
0x3ed2  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x3ed7  ldstr    aTemplate// "Template"
0x3edc  ldarg.0
0x3edd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentPageType
0x3ee2  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3ee7  callvirt instance void [System.Web]System.Web.UI.StateBag::set_Item(string, object)
0x3eec  ldarg.0
0x3eed  ldloc.0
0x3eee  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::BindThemeSelectorControls(class [mscorlib]System.Globalization.CultureInfo culture)
0x3ef3  ldarg.0
0x3ef4  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3ef9  callvirt instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x3efe  brtrue   loc_3F96
0x3f03  ldarg.0
0x3f04  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::headerCheck
0x3f09  ldarg.0
0x3f0a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::footerCheck
0x3f0f  ldarg.0
0x3f10  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navigationCheck
0x3f15  ldc.i4.1
0x3f16  dup
0x3f17  stloc.1
0x3f18  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x3f1d  ldloc.1
0x3f1e  dup
0x3f1f  stloc.2
0x3f20  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x3f25  ldloc.2
0x3f26  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x3f2b  ldarg.0
0x3f2c  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::BindNavigationControls()
0x3f31  ldarg.0
0x3f32  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::litUrl
0x3f37  ldarg.0
0x3f38  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x3f3d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x3f42  ldstr    asc_20240// "/"
0x3f47  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::get_PublicSitePathValue()
0x3f4c  ldstr    asc_20240// "/"
0x3f51  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x3f56  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0x3f5b  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x3f60  ldarg.0
0x3f61  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::pagePropDiv
0x3f66  ldarg.0
0x3f67  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::btnSubmit
0x3f6c  ldc.i4.0
0x3f6d  dup
0x3f6e  stloc.3
0x3f6f  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3f74  ldloc.3
0x3f75  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3f7a  ldarg.0
0x3f7b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::pageTempDiv
0x3f80  ldarg.0
0x3f81  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputButton Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::nextBtn
0x3f86  ldc.i4.1
0x3f87  dup
0x3f88  stloc.s  4
0x3f8a  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3f8f  ldloc.s  4
0x3f91  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3f96  ret
```
