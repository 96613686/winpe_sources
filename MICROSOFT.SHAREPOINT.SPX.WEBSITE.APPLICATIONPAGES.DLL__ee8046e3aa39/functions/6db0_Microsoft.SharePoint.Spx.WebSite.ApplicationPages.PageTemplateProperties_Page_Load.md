# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::Page_Load

- ea: `0x6db0`
- end: `0x6fe3`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::Page_Load`
- size: `563`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x6b80`
- `0x6b90`
- `0x6db0`

## string_xrefs

- `0x6ec6`: `mswh_templateDescription`
- `0x6fbb`: `PageTemplates_PropertiesTitleHeader`
- `0x6fcd`: `PageTemplates_SaveTitle`

## pseudocode

```c

```

## disassembly

```asm
0x6db0  ldarg.0
0x6db1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6db6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x6dbb  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spWeb
0x6dc0  ldarg.0
0x6dc1  ldarg.0
0x6dc2  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x6dc7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x6dcc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6dd1  ldstr    aPbe// "PBE"
0x6dd6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6ddb  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::set_FileName(string value)
0x6de0  ldarg.0
0x6de1  ldarg.0
0x6de2  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6de7  ldstr    asc_20240// "/"
0x6dec  ldc.i4.4
0x6ded  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x6df2  brtrue.s loc_6E06
0x6df4  ldstr    asc_20240// "/"
0x6df9  ldarg.0
0x6dfa  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6dff  call     string [mscorlib]System.String::Concat(string, string)
0x6e04  br.s     loc_6E0C
0x6e06  ldarg.0
0x6e07  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6e0c  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::set_FileName(string value)
0x6e11  ldarg.0
0x6e12  ldarg.0
0x6e13  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spWeb
0x6e18  ldarg.0
0x6e19  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6e1e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFile(string)
0x6e23  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6e28  ldarg.0
0x6e29  ldarg.0
0x6e2a  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6e2f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x6e34  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::set_FileName(string value)
0x6e39  ldarg.0
0x6e3a  ldarg.0
0x6e3b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6e40  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6e45  ldstr    aMode_0// "mode"
0x6e4a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6e4f  brfalse.s loc_6E79
0x6e51  ldarg.0
0x6e52  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6e57  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6e5c  ldstr    aMode_0// "mode"
0x6e61  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6e66  ldstr    aProps// "props"
0x6e6b  ldc.i4.5
0x6e6c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6e71  ldc.i4.0
0x6e72  ceq
0x6e74  ldc.i4.0
0x6e75  ceq
0x6e77  br.s     loc_6E7A
0x6e79  ldc.i4.1
0x6e7a  stfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::isSaveMode
0x6e7f  ldarg.0
0x6e80  call     instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x6e85  brtrue.s loc_6F01
0x6e87  ldarg.0
0x6e88  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6e8d  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Exists()
0x6e92  brfalse.s loc_6ED5
0x6e94  ldarg.0
0x6e95  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templTitleBox
0x6e9a  ldarg.0
0x6e9b  call     instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.UI.Page::get_Server()
0x6ea0  ldarg.0
0x6ea1  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6ea6  ldstr    aVtiTitle// "vti_title"
0x6eab  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::GetPagePropertyValue(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile, string)
0x6eb0  callvirt instance string [System.Web]System.Web.HttpServerUtility::HtmlDecode(string)
0x6eb5  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x6eba  ldarg.0
0x6ebb  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::tempDescArea
0x6ec0  ldarg.0
0x6ec1  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6ec6  ldstr    aMswhTemplatede// "mswh_templateDescription"
0x6ecb  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::GetPagePropertyValue(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile, string)
0x6ed0  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x6ed5  ldarg.0
0x6ed6  ldfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::isSaveMode
0x6edb  brfalse.s loc_6F01
0x6edd  ldarg.0
0x6ede  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templFilenameBox
0x6ee3  ldarg.0
0x6ee4  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6ee9  ldc.i4.0
0x6eea  ldarg.0
0x6eeb  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6ef0  ldc.i4.s 0x2E
0x6ef2  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x6ef7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6efc  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x6f01  ldarg.0
0x6f02  ldfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::isSaveMode
0x6f07  brtrue   loc_6FCC
0x6f0c  ldarg.0
0x6f0d  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spWeb
0x6f12  ldarg.0
0x6f13  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6f18  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x6f1d  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb, string)
0x6f22  stloc.0
0x6f23  ldarg.0
0x6f24  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::dateTimeCreated
0x6f29  ldloc.0
0x6f2a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::get_SpFile()
0x6f2f  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_TimeCreated()
0x6f34  stloc.1
0x6f35  ldloca.s 1
0x6f37  ldstr    aD// "D"
0x6f3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6f41  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x6f46  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::HtmlEncode(string)
0x6f4b  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6f50  ldarg.0
0x6f51  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::dateTimeModified
0x6f56  ldloc.0
0x6f57  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::get_SpFile()
0x6f5c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_TimeLastModified()
0x6f61  stloc.2
0x6f62  ldloca.s 2
0x6f64  ldstr    aD// "D"
0x6f69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6f6e  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x6f73  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::HtmlEncode(string)
0x6f78  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6f7d  ldarg.0
0x6f7e  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileSize
0x6f83  ldloc.0
0x6f84  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::get_SpFile()
0x6f89  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_TotalLength()
0x6f8e  conv.r8
0x6f8f  ldc.r8   1000.0
0x6f98  div
0x6f99  stloc.3
0x6f9a  ldloca.s 3
0x6f9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6fa1  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x6fa6  ldstr    aK_0// "K"
0x6fab  call     string [mscorlib]System.String::Concat(string, string)
0x6fb0  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::HtmlEncode(string)
0x6fb5  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x6fba  ldarg.0
0x6fbb  ldstr    aPagetemplatesP// "PageTemplates_PropertiesTitleHeader"
0x6fc0  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x6fc5  stfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::dialogTitle
0x6fca  br.s     loc_6FDC
0x6fcc  ldarg.0
0x6fcd  ldstr    aPagetemplatesS_0// "PageTemplates_SaveTitle"
0x6fd2  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x6fd7  stfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::dialogTitle
0x6fdc  ldarg.0
0x6fdd  callvirt instance void [System.Web]System.Web.UI.Control::DataBind()
0x6fe2  ret
```
