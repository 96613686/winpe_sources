# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::BindThemeSelectorControls

- ea: `0x3fa0`
- end: `0x42c4`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::BindThemeSelectorControls`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3e40`

## callees

- `0x3fa0`

## string_xrefs

- `0x4119`: `TemplateGallery`
- `0x426e`: `Template`
- `0x4280`: `Template`
- `0x42a2`: `Template`
- `0x3fdf`: `<option value="{0}" CustomTemplate="{2}">{1}</option>`
- `0x4187`: `<option value="{0}" CustomTemplate="{2}">{1}</option>`
- `0x40e3`: `CP_OfficeLiveTemplates`
- `0x41c3`: `mswh_templateDescription`
- `0x421d`: `CP_MyTemplates`
- `0x424a`: `<select style="width:290px;" id="lbWebTemplate" size="20" class="MSG_StandardText" onchange="OnWebTemplateChange()">{0}</select>`

## pseudocode

```c

```

## disassembly

```asm
0x3fa0  ldarg.1
0x3fa1  call     class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType[] [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageTypeList::GetValues(class [mscorlib]System.Globalization.CultureInfo)
0x3fa6  stloc.0
0x3fa7  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3fac  stloc.1
0x3fad  ldsfld   string [mscorlib]System.String::Empty
0x3fb2  stloc.2
0x3fb3  ldsfld   string [mscorlib]System.String::Empty
0x3fb8  stloc.3
0x3fb9  ldc.i4.0
0x3fba  stloc.s  4
0x3fbc  br       loc_40C3
0x3fc1  ldloc.0
0x3fc2  ldloc.s  4
0x3fc4  ldelem.ref
0x3fc5  stloc.s  5
0x3fc7  ldloc.s  5
0x3fc9  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_Name()
0x3fce  ldstr    aInternal// "_internal_"
0x3fd3  ldc.i4.5
0x3fd4  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3fd9  brtrue   loc_40BD
0x3fde  ldloc.1
0x3fdf  ldstr    aOptionValue0Cu// "<option value=\"{0}\" CustomTemplate=\""...
0x3fe4  ldloc.s  5
0x3fe6  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_Name()
0x3feb  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0x3ff0  ldc.i4.0
0x3ff1  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x3ff6  ldloc.s  5
0x3ff8  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_Description()
0x3ffd  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::HtmlEncode(string)
0x4002  ldstr    aFalse// "false"
0x4007  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x400c  pop
0x400d  ldloc.3
0x400e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4013  brtrue.s loc_401D
0x4015  ldloc.s  5
0x4017  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_Name()
0x401c  stloc.3
0x401d  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden::.ctor()
0x4022  stloc.s  6
0x4024  ldloc.s  6
0x4026  ldstr    aHiddescription// "HidDescription"
0x402b  ldloc.s  5
0x402d  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_Name()
0x4032  call     string [mscorlib]System.String::Concat(string, string)
0x4037  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x403c  ldloc.s  6
0x403e  ldloc.s  5
0x4040  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_LongDescription()
0x4045  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x404a  ldarg.0
0x404b  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::hiddenInputsPlaceHolder
0x4050  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x4055  ldloc.s  6
0x4057  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x405c  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden::.ctor()
0x4061  stloc.s  6
0x4063  ldloc.s  6
0x4065  ldstr    aHidimage// "HidImage"
0x406a  ldloc.s  5
0x406c  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_Name()
0x4071  call     string [mscorlib]System.String::Concat(string, string)
0x4076  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x407b  ldc.i4.2
0x407c  ldloc.s  5
0x407e  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_ImageName()
0x4083  ldc.i4.1
0x4084  ldc.i4.0
0x4085  call     class [System]System.Uri [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.ResourceUtility::GetResourceUrl(valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.ResourceType, string, bool, bool)
0x408a  callvirt instance string [mscorlib]System.Object::ToString()
0x408f  stloc.s  7
0x4091  ldloc.s  6
0x4093  ldloc.s  7
0x4095  ldstr    asc_2224E// ":"
0x409a  ldloc.s  5
0x409c  callvirt instance string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageType::get_ImageClassName()
0x40a1  call     string [mscorlib]System.String::Concat(string, string, string)
0x40a6  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x40ab  ldarg.0
0x40ac  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::hiddenInputsPlaceHolder
0x40b1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x40b6  ldloc.s  6
0x40b8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x40bd  ldloc.s  4
0x40bf  ldc.i4.1
0x40c0  add
0x40c1  stloc.s  4
0x40c3  ldloc.s  4
0x40c5  ldloc.0
0x40c6  ldlen
0x40c7  conv.i4
0x40c8  blt      loc_3FC1
0x40cd  ldloc.2
0x40ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40d3  ldstr    aOptgroupLabel0// "<optgroup label=\"{0}\">{1}</optgroup>"
0x40d8  ldc.i4.2
0x40d9  newarr   [mscorlib]System.Object
0x40de  stloc.s  0xC
0x40e0  ldloc.s  0xC
0x40e2  ldc.i4.0
0x40e3  ldstr    aCpOfficelivete// "CP_OfficeLiveTemplates"
0x40e8  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x40ed  stelem.ref
0x40ee  ldloc.s  0xC
0x40f0  ldc.i4.1
0x40f1  ldloc.1
0x40f2  callvirt instance string [mscorlib]System.Object::ToString()
0x40f7  stelem.ref
0x40f8  ldloc.s  0xC
0x40fa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40ff  call     string [mscorlib]System.String::Concat(string, string)
0x4104  stloc.2
0x4105  ldloc.1
0x4106  ldc.i4.0
0x4107  ldloc.1
0x4108  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x410d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x4112  pop
0x4113  ldarg.0
0x4114  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x4119  ldstr    aTemplategaller// "TemplateGallery"
0x411e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFolder(string)
0x4123  stloc.s  8
0x4125  ldloc.s  8
0x4127  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Exists()
0x412c  brfalse  loc_423F
0x4131  ldloc.s  8
0x4133  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ItemCount()
0x4138  ldc.i4.0
0x4139  ble      loc_423F
0x413e  ldloc.s  8
0x4140  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Files()
0x4145  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x414a  stloc.s  0xD
0x414c  br       loc_41E4
0x4151  ldloc.s  0xD
0x4153  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4158  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x415d  stloc.s  9
0x415f  ldloc.s  9
0x4161  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x4166  ldstr    aAspx// ".aspx"
0x416b  ldc.i4.5
0x416c  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x4171  brfalse.s loc_41E4
0x4173  ldloc.s  9
0x4175  ldstr    aVtiTitle// "vti_title"
0x417a  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::GetPagePropertyValue(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile, string)
0x417f  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x4184  stloc.s  0xA
0x4186  ldloc.1
0x4187  ldstr    aOptionValue0Cu// "<option value=\"{0}\" CustomTemplate=\""...
0x418c  ldloc.s  9
0x418e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x4193  ldloc.s  0xA
0x4195  ldstr    aTrue// "true"
0x419a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x419f  pop
0x41a0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden::.ctor()
0x41a5  stloc.s  0xB
0x41a7  ldloc.s  0xB
0x41a9  ldstr    aHiddescription// "HidDescription"
0x41ae  ldloc.s  9
0x41b0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x41b5  call     string [mscorlib]System.String::Concat(string, string)
0x41ba  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x41bf  ldloc.s  0xB
0x41c1  ldloc.s  9
0x41c3  ldstr    aMswhTemplatede// "mswh_templateDescription"
0x41c8  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::GetPagePropertyValue(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile, string)
0x41cd  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x41d2  ldarg.0
0x41d3  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::hiddenInputsPlaceHolder
0x41d8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x41dd  ldloc.s  0xB
0x41df  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x41e4  ldloc.s  0xD
0x41e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x41eb  brtrue   loc_4151
0x41f0  leave.s  loc_4207
0x41f2  ldloc.s  0xD
0x41f4  isinst   [mscorlib]System.IDisposable
0x41f9  stloc.s  0xE
0x41fb  ldloc.s  0xE
0x41fd  brfalse.s loc_4206
0x41ff  ldloc.s  0xE
0x4201  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4206  endfinally
0x4207  ldloc.2
0x4208  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x420d  ldstr    aOptgroupLabel0// "<optgroup label=\"{0}\">{1}</optgroup>"
0x4212  ldc.i4.2
0x4213  newarr   [mscorlib]System.Object
0x4218  stloc.s  0xF
0x421a  ldloc.s  0xF
0x421c  ldc.i4.0
0x421d  ldstr    aCpMytemplates// "CP_MyTemplates"
0x4222  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x4227  stelem.ref
0x4228  ldloc.s  0xF
0x422a  ldc.i4.1
0x422b  ldloc.1
0x422c  callvirt instance string [mscorlib]System.Object::ToString()
0x4231  stelem.ref
0x4232  ldloc.s  0xF
0x4234  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4239  call     string [mscorlib]System.String::Concat(string, string)
0x423e  stloc.2
0x423f  ldarg.0
0x4240  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::webTemplatesHolder
0x4245  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x424a  ldstr    aSelectStyleWid// "<select style=\"width:290px;\" id=\"lbW"...
0x424f  ldc.i4.1
0x4250  newarr   [mscorlib]System.Object
0x4255  stloc.s  0x10
0x4257  ldloc.s  0x10
0x4259  ldc.i4.0
0x425a  ldloc.2
0x425b  stelem.ref
0x425c  ldloc.s  0x10
0x425e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4263  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x4268  ldarg.0
0x4269  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x426e  ldstr    aTemplate// "Template"
0x4273  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x4278  brfalse.s loc_42B7
0x427a  ldarg.0
0x427b  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x4280  ldstr    aTemplate// "Template"
0x4285  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x428a  castclass [mscorlib]System.String
0x428f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4294  brtrue.s loc_42B7
0x4296  ldarg.0
0x4297  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentPageType
0x429c  ldarg.0
0x429d  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x42a2  ldstr    aTemplate// "Template"
0x42a7  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x42ac  castclass [mscorlib]System.String
0x42b1  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x42b6  ret
0x42b7  ldarg.0
0x42b8  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentPageType
0x42bd  ldloc.3
0x42be  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x42c3  ret
```
