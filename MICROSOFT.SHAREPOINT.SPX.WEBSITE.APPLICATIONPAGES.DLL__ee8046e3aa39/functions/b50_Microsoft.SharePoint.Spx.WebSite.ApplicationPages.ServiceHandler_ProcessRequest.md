# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::ProcessRequest

- ea: `0xb50`
- end: `0x150a`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::ProcessRequest`
- size: `2490`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x60`
- `0x1b0`
- `0x210`
- `0xb10`
- `0xb50`
- `0x1510`
- `0x1540`
- `0x1580`
- `0x16f0`
- `0x1770`
- `0x1920`
- `0x1bf0`
- `0xd170`
- `0x147c0`
- `0x15620`

## string_xrefs

- `0xb50`: `SiteDesigner_ServiceHandlerProcessRequest`
- `0xba6`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0xbfb`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0xcb9`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0xd2a`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0xea6`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0x14ba`: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler`
- `0xda2`: `ReadSiteData`
- `0xf3c`: `ReadSiteData`
- `0xdae`: `WriteSiteData`
- `0xf48`: `WriteSiteData`
- `0xdba`: `DeletePage`
- `0xf54`: `DeletePage`
- `0xdea`: `CreateHeader`
- `0xfc2`: `CreateHeader`
- `0x10df`: `CultureName`
- `0x1122`: `CultureName`
- `0x121f`: `<?xml version="1.0"?><CustomColorXMLVerify xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="CustomColorXMLVerify.xsd">{0}</CustomColorXMLVerify>`
- `0x130d`: `<?xml version="1.0"?><CustomColorXMLVerify xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="CustomColorXMLVerify.xsd">{0}</CustomColorXMLVerify>`
- `0x1389`: `<?xml version="1.0"?><CustomColorXMLVerify xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="CustomColorXMLVerify.xsd">{0}</CustomColorXMLVerify>`
- `0x12cc`: `imgPath`
- `0x12f1`: `imgPath`
- `0x1472`: `filePath`

## pseudocode

```c

```

## disassembly

```asm
0xb50  ldstr    aSitedesignerSe// "SiteDesigner_ServiceHandlerProcessReque"...
0xb55  ldnull
0xb56  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0xb5b  ldarg.1
0xb5c  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xb61  stloc.0
0xb62  ldarg.1
0xb63  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xb68  stloc.1
0xb69  ldc.i4.0
0xb6a  stloc.2
0xb6b  ldloc.1
0xb6c  callvirt instance string [System.Web]System.Web.HttpRequest::get_HttpMethod()
0xb71  ldstr    aPost// "POST"
0xb76  ldc.i4.5
0xb77  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xb7c  brtrue   loc_C38
0xb81  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ValidateFormDigest()
0xb86  stloc.2
0xb87  leave.s  loc_BE1
0xb89  stloc.3
0xb8a  ldc.i4   0x68656330
0xb8f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xb94  ldc.i4.s 0x32
0xb96  ldstr    a0123// "{0},{1}. {2}. {3}"
0xb9b  ldc.i4.4
0xb9c  newarr   [mscorlib]System.Object
0xba1  stloc.s  0x10
0xba3  ldloc.s  0x10
0xba5  ldc.i4.0
0xba6  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0xbab  stelem.ref
0xbac  ldloc.s  0x10
0xbae  ldc.i4.1
0xbaf  ldstr    aProcessrequest// "ProcessRequest"
0xbb4  stelem.ref
0xbb5  ldloc.s  0x10
0xbb7  ldc.i4.2
0xbb8  ldstr    aValidateformdi// "ValidateFormDigest failed for this requ"...
0xbbd  ldloc.1
0xbbe  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xbc3  callvirt instance string [mscorlib]System.Object::ToString()
0xbc8  call     string [mscorlib]System.String::Concat(string, string)
0xbcd  stelem.ref
0xbce  ldloc.s  0x10
0xbd0  ldc.i4.3
0xbd1  ldloc.3
0xbd2  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetExceptionString(class [mscorlib]System.Exception)
0xbd7  stelem.ref
0xbd8  ldloc.s  0x10
0xbda  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xbdf  leave.s  loc_BE1
0xbe1  ldloc.2
0xbe2  brtrue.s loc_C38
0xbe4  ldloc.0
0xbe5  ldc.i4   0x191
0xbea  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0xbef  ldc.i4   0x68656331
0xbf4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xbf9  ldc.i4.s 0x32
0xbfb  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0xc00  ldstr    aProcessrequest// "ProcessRequest"
0xc05  ldstr    aValidateformdi// "ValidateFormDigest failed for this requ"...
0xc0a  ldloc.1
0xc0b  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xc10  callvirt instance string [mscorlib]System.Object::ToString()
0xc15  call     string [mscorlib]System.String::Concat(string, string)
0xc1a  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xc1f  ldc.i4.1
0xc20  newarr   [mscorlib]System.Object
0xc25  stloc.s  0x11
0xc27  ldloc.s  0x11
0xc29  ldc.i4.0
0xc2a  ldsfld   string [mscorlib]System.String::Empty
0xc2f  stelem.ref
0xc30  ldloc.s  0x11
0xc32  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xc37  ret
0xc38  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xc3d  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0xc42  ldstr    asc_20240// "/"
0xc47  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0xc4c  ldstr    aWhEditor// "/WH/Editor/"
0xc51  call     string [mscorlib]System.String::Concat(string, string, string)
0xc56  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0xc5b  stloc.s  4
0xc5d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xc62  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0xc67  call     string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::get_CustomColorsXsdUrlRelative()
0xc6c  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0xc71  stloc.s  5
0xc73  ldloc.0
0xc74  ldstr    aXRequestdigest// "X-RequestDigest"
0xc79  call     string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Common::GetUpdatedFormDigest()
0xc7e  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0xc83  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0xc88  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0xc8d  stloc.s  6
0xc8f  ldloc.s  6
0xc91  brfalse.s loc_CA2
0xc93  ldloc.s  6
0xc95  ldc.i4   0x40000
0xc9a  conv.i8
0xc9b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurableObject::DoesUserHavePermissions(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions)
0xca0  brtrue.s loc_CF6
0xca2  ldloc.0
0xca3  ldc.i4   0x193
0xca8  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0xcad  ldc.i4   0x67363932
0xcb2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xcb7  ldc.i4.s 0x32
0xcb9  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0xcbe  ldstr    aProcessrequest// "ProcessRequest"
0xcc3  ldstr    aUserDoesNotHav// "User does not have permission to edit t"...
0xcc8  ldloc.1
0xcc9  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xcce  callvirt instance string [mscorlib]System.Object::ToString()
0xcd3  call     string [mscorlib]System.String::Concat(string, string)
0xcd8  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xcdd  ldc.i4.1
0xcde  newarr   [mscorlib]System.Object
0xce3  stloc.s  0x12
0xce5  ldloc.s  0x12
0xce7  ldc.i4.0
0xce8  ldsfld   string [mscorlib]System.String::Empty
0xced  stelem.ref
0xcee  ldloc.s  0x12
0xcf0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcf5  ret
0xcf6  ldloc.1
0xcf7  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_UrlReferrer()
0xcfc  callvirt instance string [System]System.Uri::get_Host()
0xd01  ldloc.1
0xd02  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xd07  callvirt instance string [System]System.Uri::get_Host()
0xd0c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xd11  brfalse.s loc_D77
0xd13  ldloc.0
0xd14  ldc.i4   0x193
0xd19  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0xd1e  ldc.i4   0x67363933
0xd23  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xd28  ldc.i4.s 0x32
0xd2a  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0xd2f  ldstr    aProcessrequest// "ProcessRequest"
0xd34  ldstr    aExternalReferr// "External referrer("
0xd39  ldloc.1
0xd3a  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_UrlReferrer()
0xd3f  callvirt instance string [mscorlib]System.Object::ToString()
0xd44  ldstr    aNotAllowedUrl// ") not allowed.  Url:"
0xd49  ldloc.1
0xd4a  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xd4f  callvirt instance string [mscorlib]System.Object::ToString()
0xd54  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xd59  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xd5e  ldc.i4.1
0xd5f  newarr   [mscorlib]System.Object
0xd64  stloc.s  0x13
0xd66  ldloc.s  0x13
0xd68  ldc.i4.0
0xd69  ldsfld   string [mscorlib]System.String::Empty
0xd6e  stelem.ref
0xd6f  ldloc.s  0x13
0xd71  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xd76  ret
0xd77  ldloc.1
0xd78  ldstr    aMethodname// "methodName"
0xd7d  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0xd82  stloc.s  7
0xd84  ldloc.s  7
0xd86  dup
0xd87  stloc.s  0x14
0xd89  brfalse  loc_EE3
0xd8e  volatile.
0xd90  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{5EB88833-D16A-416F-B1F1-66D18A8B1199}::$$method0x6000046-1
0xd95  brtrue   loc_E2E
0xd9a  ldc.i4.s 0xB
0xd9c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xda1  dup
0xda2  ldstr    aReadsitedata// "ReadSiteData"
0xda7  ldc.i4.0
0xda8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdad  dup
0xdae  ldstr    aWritesitedata// "WriteSiteData"
0xdb3  ldc.i4.1
0xdb4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb9  dup
0xdba  ldstr    aDeletepage// "DeletePage"
0xdbf  ldc.i4.2
0xdc0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdc5  dup
0xdc6  ldstr    aGetpagecontent// "GetPageContent"
0xdcb  ldc.i4.3
0xdcc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdd1  dup
0xdd2  ldstr    aGetdesigntimeh// "GetDesignTimeHtml"
0xdd7  ldc.i4.4
0xdd8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xddd  dup
0xdde  ldstr    aGeneratesiteba// "GenerateSiteBackground"
0xde3  ldc.i4.5
0xde4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xde9  dup
0xdea  ldstr    aCreateheader// "CreateHeader"
0xdef  ldc.i4.6
0xdf0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdf5  dup
0xdf6  ldstr    aChangepattern// "ChangePattern"
0xdfb  ldc.i4.7
0xdfc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe01  dup
0xe02  ldstr    aGeneratezoneba// "GenerateZoneBackground"
0xe07  ldc.i4.8
0xe08  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe0d  dup
0xe0e  ldstr    aGeneratebackgr// "GenerateBackgroundImageFromFile"
0xe13  ldc.i4.s 9
0xe15  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe1a  dup
0xe1b  ldstr    aCancelsave// "CancelSave"
0xe20  ldc.i4.s 0xA
0xe22  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe27  volatile.
0xe29  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{5EB88833-D16A-416F-B1F1-66D18A8B1199}::$$method0x6000046-1
0xe2e  volatile.
0xe30  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{5EB88833-D16A-416F-B1F1-66D18A8B1199}::$$method0x6000046-1
0xe35  ldloc.s  0x14
0xe37  ldloca.s 0x15
0xe39  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xe3e  brfalse  loc_EE3
0xe43  ldloc.s  0x15
0xe45  switch   loc_E78, loc_E78, loc_E78, loc_E78, loc_E78, loc_E78, loc_E78, loc_E78, loc_E78, loc_E78, loc_E78
0xe76  br.s     loc_EE3
0xe78  ldloc.1
0xe79  ldstr    aWebkey// "webKey"
0xe7e  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0xe83  call     string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Common::GetClientKey()
0xe88  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xe8d  brfalse.s loc_EE3
0xe8f  ldloc.0
0xe90  ldc.i4   0x193
0xe95  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0xe9a  ldc.i4   0x67363934
0xe9f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_spx_website()
0xea4  ldc.i4.s 0x32
0xea6  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Spx.WebSite.Applic"...
0xeab  ldstr    aProcessrequest// "ProcessRequest"
0xeb0  ldstr    aWebkeyMismatch// "webKey mismatch.  Url:"
0xeb5  ldloc.1
0xeb6  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xebb  callvirt instance string [mscorlib]System.Object::ToString()
0xec0  call     string [mscorlib]System.String::Concat(string, string)
0xec5  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.SPXDiagnosticCategory::GetLogFormatString(string, string, string)
0xeca  ldc.i4.1
0xecb  newarr   [mscorlib]System.Object
0xed0  stloc.s  0x16
0xed2  ldloc.s  0x16
0xed4  ldc.i4.0
0xed5  ldsfld   string [mscorlib]System.String::Empty
0xeda  stelem.ref
0xedb  ldloc.s  0x16
0xedd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xee2  ret
0xee3  ldloc.s  6
0xee5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::SetThreadCulture(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0xeea  ldloc.0
0xeeb  ldstr    aTextPlain// "text/plain"
0xef0  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0xef5  ldloc.0
0xef6  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xefb  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0xf00  ldloc.0
0xf01  ldstr    aUtf8// "utf-8"
0xf06  callvirt instance void [System.Web]System.Web.HttpResponse::set_Charset(string)
0xf0b  ldloc.0
0xf0c  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0xf11  ldc.i4.1
0xf12  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0xf17  ldsfld   string [mscorlib]System.String::Empty
0xf1c  stloc.s  8
0xf1e  ldloc.s  7
0xf20  dup
0xf21  stloc.s  0x17
0xf23  brfalse  loc_14AA
0xf28  volatile.
0xf2a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{5EB88833-D16A-416F-B1F1-66D18A8B1199}::$$method0x6000046-2
0xf2f  brtrue   loc_1009
0xf34  ldc.i4.s 0x10
0xf36  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xf3b  dup
0xf3c  ldstr    aReadsitedata// "ReadSiteData"
0xf41  ldc.i4.0
0xf42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf47  dup
0xf48  ldstr    aWritesitedata// "WriteSiteData"
0xf4d  ldc.i4.1
0xf4e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf53  dup
0xf54  ldstr    aDeletepage// "DeletePage"
0xf59  ldc.i4.2
  ... truncated ...
```
