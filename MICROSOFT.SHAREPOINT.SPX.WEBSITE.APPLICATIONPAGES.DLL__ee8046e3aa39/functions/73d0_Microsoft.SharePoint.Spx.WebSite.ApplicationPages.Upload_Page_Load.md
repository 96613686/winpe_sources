# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::Page_Load

- ea: `0x73d0`
- end: `0x7596`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::Page_Load`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x73d0`
- `0x75a0`
- `0x75c0`
- `0x7670`
- `0x7f50`

## string_xrefs

- `0x748a`: `overwriteImage`

## pseudocode

```c

```

## disassembly

```asm
0x73d0  ldarg.0
0x73d1  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x73d6  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x73db  ldarg.0
0x73dc  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x73e1  ldstr    aTrickform1// "trickForm1"
0x73e6  ldstr    aDocumentForm1D// "document.form1 = document.getElementByI"...
0x73eb  ldc.i4.1
0x73ec  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterStartupScript(class [mscorlib]System.Type, string, string, bool)
0x73f1  ldarg.0
0x73f2  ldsfld   string [mscorlib]System.String::Empty
0x73f7  stfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::uploadResult
0x73fc  ldarg.0
0x73fd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x7402  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x7407  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::site
0x740c  ldarg.0
0x740d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x7412  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x7417  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::web
0x741c  ldarg.0
0x741d  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::web
0x7422  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::EnsureAuthentication(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x7427  ldarg.0
0x7428  call     instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x742d  brfalse  loc_7502
0x7432  ldarg.0
0x7433  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7438  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x743d  brfalse.s loc_7452
0x743f  ldarg.0
0x7440  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7445  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x744a  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x744f  ldc.i4.1
0x7450  bge.s    loc_745D
0x7452  ldstr    aNoFileToUpload// "No file to upload."
0x7457  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.WebSiteException::.ctor(string message)
0x745c  throw
0x745d  ldarg.0
0x745e  ldarg.0
0x745f  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::web
0x7464  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x7469  stfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::fileManager
0x746e  ldarg.0
0x746f  ldarg.0
0x7470  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::site
0x7475  call     valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.StorageData [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Utilities::GetStorage(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite)
0x747a  stfld    valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.StorageData Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::storageData
0x747f  ldarg.0
0x7480  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7485  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x748a  ldstr    aOverwriteimage// "overwriteImage"
0x748f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7494  stloc.0
0x7495  ldloc.0
0x7496  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x749b  brtrue.s loc_74B2
0x749d  ldloc.0
0x749e  ldstr    aTrue// "true"
0x74a3  ldc.i4.5
0x74a4  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x74a9  brtrue.s loc_74B2
0x74ab  ldarg.0
0x74ac  ldc.i4.1
0x74ad  stfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::isDuplicateFileAllowed
0x74b2  ldarg.0
0x74b3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x74b8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x74bd  ldstr    aOptimizeimage// "optimizeImage"
0x74c2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x74c7  stloc.1
0x74c8  ldloc.1
0x74c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x74ce  brtrue.s loc_74E5
0x74d0  ldloc.1
0x74d1  ldstr    aTrue// "true"
0x74d6  ldc.i4.5
0x74d7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x74dc  brtrue.s loc_74E5
0x74de  ldarg.0
0x74df  ldc.i4.1
0x74e0  stfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::optimizeImage
0x74e5  ldarg.0
0x74e6  ldarg.0
0x74e7  ldarg.0
0x74e8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x74ed  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x74f2  ldc.i4.0
0x74f3  callvirt instance class [System.Web]System.Web.HttpPostedFile [System.Web]System.Web.HttpFileCollection::get_Item(int32)
0x74f8  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::ProcessUpload(class [System.Web]System.Web.HttpPostedFile uploadFile)
0x74fd  stfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::uploadResult
0x7502  leave    loc_7595
0x7507  stloc.2
0x7508  ldarg.0
0x7509  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x750e  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x7513  brfalse.s loc_7540
0x7515  ldarg.0
0x7516  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x751b  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x7520  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x7525  ldc.i4.1
0x7526  blt.s    loc_7540
0x7528  ldarg.0
0x7529  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x752e  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0x7533  ldc.i4.0
0x7534  callvirt instance class [System.Web]System.Web.HttpPostedFile [System.Web]System.Web.HttpFileCollection::get_Item(int32)
0x7539  call     string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::GetFileName(class [System.Web]System.Web.HttpPostedFile uploadFile)
0x753e  br.s     loc_7545
0x7540  ldsfld   string [mscorlib]System.String::Empty
0x7545  stloc.3
0x7546  ldc.i4   0x67363961
0x754b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0x7550  ldc.i4.s 0x32
0x7552  ldstr    aUpload// "Upload"
0x7557  ldstr    aPageLoad// "Page_Load"
0x755c  ldstr    aExceptionThrow_1// "Exception thrown when processing file: "
0x7561  ldloc.3
0x7562  call     string [mscorlib]System.String::Concat(string, string)
0x7567  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0x756c  ldc.i4.1
0x756d  newarr   [mscorlib]System.Object
0x7572  stloc.s  4
0x7574  ldloc.s  4
0x7576  ldc.i4.0
0x7577  ldloc.2
0x7578  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0x757d  stelem.ref
0x757e  ldloc.s  4
0x7580  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x7585  ldarg.0
0x7586  ldarg.0
0x7587  ldc.i4.5
0x7588  ldloc.3
0x7589  call     instance string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::ComposeResponseMessage(valuetype FileUploadStatus result, string fileName)
0x758e  stfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::uploadResult
0x7593  leave.s  loc_7595
0x7595  ret
```
