# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::SubmitBtn_ServerClick

- ea: `0x3910`
- end: `0x3c6a`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::SubmitBtn_ServerClick`
- size: `858`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x3910`
- `0x43e0`

## string_xrefs

- `0x394a`: `TemplateGallery`
- `0x3965`: `Invalid file template specified`
- `0x3b18`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage`
- `0x3ba5`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage`
- `0x3b4e`: ` overwrite=`
- `0x3bdb`: ` overwrite=`
- `0x3bfc`: ` templateName=`

## pseudocode

```c

```

## disassembly

```asm
0x3910  ldarg.0
0x3911  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::ValidatePageControls()
0x3916  ldarg.0
0x3917  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::newPageTitle
0x391c  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3921  stloc.0
0x3922  ldarg.0
0x3923  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::txtUrl
0x3928  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x392d  stloc.1
0x392e  ldarg.0
0x392f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentPageType
0x3934  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3939  stloc.2
0x393a  ldarg.0
0x393b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navTitleText
0x3940  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3945  stloc.3
0x3946  ldnull
0x3947  stloc.s  4
0x3949  ldloc.2
0x394a  ldstr    aTemplategaller// "TemplateGallery"
0x394f  ldc.i4.5
0x3950  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3955  brfalse.s loc_39AE
0x3957  ldloc.2
0x3958  ldstr    aAspx// ".aspx"
0x395d  ldc.i4.5
0x395e  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x3963  brtrue.s loc_3970
0x3965  ldstr    aInvalidFileTem// "Invalid file template specified"
0x396a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x396f  throw
0x3970  ldarg.0
0x3971  ldfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileManager
0x3976  ldloc.2
0x3977  ldloc.1
0x3978  ldloc.0
0x3979  ldarg.0
0x397a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::chkOverwrite
0x397f  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x3984  ldloc.3
0x3985  ldarg.0
0x3986  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentItemParent
0x398b  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x3990  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3995  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x399a  ldarg.0
0x399b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::needNav
0x39a0  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x39a5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::AddPageFromCustomTemplate(string, string, string, bool, string, int32, bool)
0x39aa  stloc.s  4
0x39ac  br.s     loc_39EF
0x39ae  ldarg.0
0x39af  ldfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileManager
0x39b4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::get_Culture()
0x39b9  ldloc.1
0x39ba  ldloc.0
0x39bb  ldloc.3
0x39bc  ldarg.0
0x39bd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentItemParent
0x39c2  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x39c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39cc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x39d1  ldloc.2
0x39d2  ldarg.0
0x39d3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::chkOverwrite
0x39d8  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x39dd  ldarg.0
0x39de  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::needNav
0x39e3  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x39e8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::AddStandardPage(class [mscorlib]System.Globalization.CultureInfo, string, string, string, int32, string, bool, bool)
0x39ed  stloc.s  4
0x39ef  ldloc.s  4
0x39f1  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x39f6  ldstr    aMswhHeaderenab// "mswh_HeaderEnabled"
0x39fb  ldarg.0
0x39fc  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::headerCheck
0x3a01  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x3a06  stloc.s  7
0x3a08  ldloca.s 7
0x3a0a  call     instance string [mscorlib]System.Boolean::ToString()
0x3a0f  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x3a14  ldloc.s  4
0x3a16  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x3a1b  ldstr    aMswhFooterenab// "mswh_FooterEnabled"
0x3a20  ldarg.0
0x3a21  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::footerCheck
0x3a26  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x3a2b  stloc.s  8
0x3a2d  ldloca.s 8
0x3a2f  call     instance string [mscorlib]System.Boolean::ToString()
0x3a34  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x3a39  ldloc.s  4
0x3a3b  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x3a40  ldstr    aMswhNavenabled// "mswh_NavEnabled"
0x3a45  ldarg.0
0x3a46  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::navigationCheck
0x3a4b  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x3a50  stloc.s  9
0x3a52  ldloca.s 9
0x3a54  call     instance string [mscorlib]System.Boolean::ToString()
0x3a59  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x3a5e  ldloc.s  4
0x3a60  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::Update()
0x3a65  leave    loc_3C2F
0x3a6a  stloc.s  5
0x3a6c  ldloc.s  5
0x3a6e  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPException::get_ErrorCode()
0x3a73  ldc.i4   0x81020067
0x3a78  bne.un.s loc_3ABC
0x3a7a  ldarg.0
0x3a7b  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x3a80  ldarg.0
0x3a81  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3a86  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileExistsMessageScriptGuid
0x3a8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a90  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileExistsMessageScript
0x3a95  ldc.i4.1
0x3a96  newarr   [mscorlib]System.Object
0x3a9b  stloc.s  0xA
0x3a9d  ldloc.s  0xA
0x3a9f  ldc.i4.0
0x3aa0  ldstr    aCpErrfileexist// "CP_ErrFileExists"
0x3aa5  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x3aaa  stelem.ref
0x3aab  ldloc.s  0xA
0x3aad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ab2  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string)
0x3ab7  leave    loc_3C69
0x3abc  ldloc.s  5
0x3abe  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPException::get_ErrorCode()
0x3ac3  ldc.i4   0x80070718
0x3ac8  bne.un.s loc_3B0C
0x3aca  ldarg.0
0x3acb  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x3ad0  ldarg.0
0x3ad1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ad6  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileExistsMessageScriptGuid
0x3adb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ae0  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileExistsMessageScript
0x3ae5  ldc.i4.1
0x3ae6  newarr   [mscorlib]System.Object
0x3aeb  stloc.s  0xB
0x3aed  ldloc.s  0xB
0x3aef  ldc.i4.0
0x3af0  ldstr    aCpSitequotaexc// "CP_SiteQuotaExceeded"
0x3af5  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x3afa  stelem.ref
0x3afb  ldloc.s  0xB
0x3afd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b02  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string)
0x3b07  leave    loc_3C69
0x3b0c  ldc.i4   0x67363937
0x3b11  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x3b16  ldc.i4.s 0x32
0x3b18  ldstr    aMicrosoftShare_1// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0x3b1d  ldstr    aSubmitbtnServe// "SubmitBtn_ServerClick"
0x3b22  ldc.i4.6
0x3b23  newarr   [mscorlib]System.Object
0x3b28  stloc.s  0xC
0x3b2a  ldloc.s  0xC
0x3b2c  ldc.i4.0
0x3b2d  ldstr    aFilename// " fileName="
0x3b32  stelem.ref
0x3b33  ldloc.s  0xC
0x3b35  ldc.i4.1
0x3b36  ldloc.1
0x3b37  stelem.ref
0x3b38  ldloc.s  0xC
0x3b3a  ldc.i4.2
0x3b3b  ldstr    aNewpagetitle// " newPageTitle="
0x3b40  stelem.ref
0x3b41  ldloc.s  0xC
0x3b43  ldc.i4.3
0x3b44  ldarg.0
0x3b45  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::newPageTitle
0x3b4a  stelem.ref
0x3b4b  ldloc.s  0xC
0x3b4d  ldc.i4.4
0x3b4e  ldstr    aOverwrite// " overwrite="
0x3b53  stelem.ref
0x3b54  ldloc.s  0xC
0x3b56  ldc.i4.5
0x3b57  ldarg.0
0x3b58  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::chkOverwrite
0x3b5d  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x3b62  stloc.s  0xD
0x3b64  ldloca.s 0xD
0x3b66  call     instance string [mscorlib]System.Boolean::ToString()
0x3b6b  stelem.ref
0x3b6c  ldloc.s  0xC
0x3b6e  call     string [mscorlib]System.String::Concat(object[])
0x3b73  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x3b78  ldc.i4.1
0x3b79  newarr   [mscorlib]System.Object
0x3b7e  stloc.s  0xE
0x3b80  ldloc.s  0xE
0x3b82  ldc.i4.0
0x3b83  ldloc.s  5
0x3b85  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x3b8a  stelem.ref
0x3b8b  ldloc.s  0xE
0x3b8d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3b92  leave    loc_3C2F
0x3b97  stloc.s  6
0x3b99  ldc.i4   0x67363938
0x3b9e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x3ba3  ldc.i4.s 0x32
0x3ba5  ldstr    aMicrosoftShare_1// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0x3baa  ldstr    aSubmitbtnServe// "SubmitBtn_ServerClick"
0x3baf  ldc.i4.8
0x3bb0  newarr   [mscorlib]System.Object
0x3bb5  stloc.s  0xF
0x3bb7  ldloc.s  0xF
0x3bb9  ldc.i4.0
0x3bba  ldstr    aFilename// " fileName="
0x3bbf  stelem.ref
0x3bc0  ldloc.s  0xF
0x3bc2  ldc.i4.1
0x3bc3  ldloc.1
0x3bc4  stelem.ref
0x3bc5  ldloc.s  0xF
0x3bc7  ldc.i4.2
0x3bc8  ldstr    aNewpagetitle// " newPageTitle="
0x3bcd  stelem.ref
0x3bce  ldloc.s  0xF
0x3bd0  ldc.i4.3
0x3bd1  ldarg.0
0x3bd2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::newPageTitle
0x3bd7  stelem.ref
0x3bd8  ldloc.s  0xF
0x3bda  ldc.i4.4
0x3bdb  ldstr    aOverwrite// " overwrite="
0x3be0  stelem.ref
0x3be1  ldloc.s  0xF
0x3be3  ldc.i4.5
0x3be4  ldarg.0
0x3be5  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::chkOverwrite
0x3bea  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x3bef  stloc.s  0x10
0x3bf1  ldloca.s 0x10
0x3bf3  call     instance string [mscorlib]System.Boolean::ToString()
0x3bf8  stelem.ref
0x3bf9  ldloc.s  0xF
0x3bfb  ldc.i4.6
0x3bfc  ldstr    aTemplatename// " templateName="
0x3c01  stelem.ref
0x3c02  ldloc.s  0xF
0x3c04  ldc.i4.7
0x3c05  ldloc.2
0x3c06  stelem.ref
0x3c07  ldloc.s  0xF
0x3c09  call     string [mscorlib]System.String::Concat(object[])
0x3c0e  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x3c13  ldc.i4.1
0x3c14  newarr   [mscorlib]System.Object
0x3c19  stloc.s  0x11
0x3c1b  ldloc.s  0x11
0x3c1d  ldc.i4.0
0x3c1e  ldloc.s  6
0x3c20  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x3c25  stelem.ref
0x3c26  ldloc.s  0x11
0x3c28  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3c2d  leave.s  loc_3C69
0x3c2f  ldarg.0
0x3c30  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x3c35  ldarg.0
0x3c36  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c3b  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileCreationSuccessScriptGuid
0x3c40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c45  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileCreationSuccessScript
0x3c4a  ldc.i4.1
0x3c4b  newarr   [mscorlib]System.Object
0x3c50  stloc.s  0x12
0x3c52  ldloc.s  0x12
0x3c54  ldc.i4.0
0x3c55  ldloc.s  4
0x3c57  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ServerRelativeUrl()
0x3c5c  stelem.ref
0x3c5d  ldloc.s  0x12
0x3c5f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c64  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string)
0x3c69  ret
```
