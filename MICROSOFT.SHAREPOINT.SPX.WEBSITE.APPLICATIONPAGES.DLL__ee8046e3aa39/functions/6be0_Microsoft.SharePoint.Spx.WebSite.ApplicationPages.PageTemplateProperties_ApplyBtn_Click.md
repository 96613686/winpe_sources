# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::ApplyBtn_Click

- ea: `0x6be0`
- end: `0x6d7e`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::ApplyBtn_Click`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x6b80`
- `0x6be0`
- `0x6ff0`

## string_xrefs

- `0x6d41`: `mswh_templateDescription`
- `0x6d72`: `commitWindow();`

## pseudocode

```c

```

## disassembly

```asm
0x6be0  ldarg.0
0x6be1  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::ValidatePageControls()
0x6be6  ldarg.0
0x6be7  ldfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::isSaveMode
0x6bec  brfalse  loc_6D03
0x6bf1  ldarg.0
0x6bf2  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spWeb
0x6bf7  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x6bfc  stloc.0
0x6bfd  ldarg.0
0x6bfe  ldloc.0
0x6bff  ldarg.0
0x6c00  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6c05  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Url()
0x6c0a  ldarg.0
0x6c0b  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_FileName()
0x6c10  ldarg.0
0x6c11  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::chkOverwrite
0x6c16  callvirt instance bool [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::get_Checked()
0x6c1b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::AddFileAsTemplate(string, string, bool)
0x6c20  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6c25  leave    loc_6D03
0x6c2a  stloc.1
0x6c2b  ldloc.1
0x6c2c  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPException::get_ErrorCode()
0x6c31  ldc.i4   0x81020067
0x6c36  beq.s    loc_6C45
0x6c38  ldloc.1
0x6c39  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPException::get_ErrorCode()
0x6c3e  ldc.i4   0x81070902
0x6c43  bne.un.s loc_6C84
0x6c45  ldarg.0
0x6c46  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x6c4b  ldarg.0
0x6c4c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6c51  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileExistsMessageScriptGuid
0x6c56  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6c5b  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileExistsMessageScript
0x6c60  ldc.i4.1
0x6c61  newarr   [mscorlib]System.Object
0x6c66  stloc.2
0x6c67  ldloc.2
0x6c68  ldc.i4.0
0x6c69  ldstr    aCpErrfileexist// "CP_ErrFileExists"
0x6c6e  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x6c73  stelem.ref
0x6c74  ldloc.2
0x6c75  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6c7a  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string)
0x6c7f  leave    loc_6D7D
0x6c84  ldarg.0
0x6c85  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x6c8a  ldarg.0
0x6c8b  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6c90  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileExistsMessageScriptGuid
0x6c95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6c9a  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileExistsMessageScript
0x6c9f  ldc.i4.1
0x6ca0  newarr   [mscorlib]System.Object
0x6ca5  stloc.3
0x6ca6  ldloc.3
0x6ca7  ldc.i4.0
0x6ca8  ldstr    aLSavefailedRea// "L_SaveFailed_ReasonUnknown"
0x6cad  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x6cb2  stelem.ref
0x6cb3  ldloc.3
0x6cb4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6cb9  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string)
0x6cbe  leave    loc_6D7D
0x6cc3  pop
0x6cc4  ldarg.0
0x6cc5  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x6cca  ldarg.0
0x6ccb  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6cd0  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileExistsMessageScriptGuid
0x6cd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x6cda  ldsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::fileExistsMessageScript
0x6cdf  ldc.i4.1
0x6ce0  newarr   [mscorlib]System.Object
0x6ce5  stloc.s  4
0x6ce7  ldloc.s  4
0x6ce9  ldc.i4.0
0x6cea  ldstr    aLSavefailedRea// "L_SaveFailed_ReasonUnknown"
0x6cef  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x6cf4  stelem.ref
0x6cf5  ldloc.s  4
0x6cf7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6cfc  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string)
0x6d01  leave.s  loc_6D7D
0x6d03  ldarg.0
0x6d04  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templTitleBox
0x6d09  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x6d0e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6d13  ldc.i4.0
0x6d14  ble.s    loc_6D36
0x6d16  ldarg.0
0x6d17  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6d1c  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x6d21  ldstr    aVtiTitle// "vti_title"
0x6d26  ldarg.0
0x6d27  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::templTitleBox
0x6d2c  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x6d31  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x6d36  ldarg.0
0x6d37  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6d3c  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Properties()
0x6d41  ldstr    aMswhTemplatede// "mswh_templateDescription"
0x6d46  ldarg.0
0x6d47  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::tempDescArea
0x6d4c  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x6d51  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x6d56  ldarg.0
0x6d57  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6d5c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::Update()
0x6d61  ldarg.0
0x6d62  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x6d67  ldarg.0
0x6d68  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6d6d  ldstr    aClosewindow// "closeWindow"
0x6d72  ldstr    aCommitwindow// "commitWindow();"
0x6d77  ldc.i4.1
0x6d78  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string, bool)
0x6d7d  ret
```
