# Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PreSendRequestHeaders

- ea: `0x414a90`
- end: `0x415046`
- name: `Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PreSendRequestHeaders`
- size: `1462`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, broker_com_uri`

## callers

- `0x416cc0`

## callees

- `0x194c60`
- `0x194d30`
- `0x1a3c20`
- `0x1c89e0`
- `0x223ba0`
- `0x231e20`
- `0x232000`
- `0x232550`
- `0x26d6d0`
- `0x26d8d0`
- `0x29ced0`
- `0x29d070`
- `0x29d0f0`
- `0x29dcf0`
- `0x3e5530`
- `0x3e5560`
- `0x3e5950`
- `0x412080`
- `0x414920`
- `0x414a60`
- `0x414a90`
- `0x41aac0`
- `0x472c20`
- `0x4cd8e0`
- `0x4cd940`
- `0x4cde40`
- `0x5c24f0`
- `0x6696d0`
- `0x669860`
- `0x79d5f0`
- `0x7c23f0`
- `0x7c89c0`
- `0x7cbec0`
- `0x93dab0`
- `0x93dae0`
- `0x9574d0`
- `0x9577d0`
- `0x957d10`

## string_xrefs

- `0x414bc9`: `Access-Denied`
- `0x414c0e`: `Access-Denied`
- `0x414be0`: `REQUEST_ACCESS_DENIED_RESPONSE`
- `0x414bf9`: `Access Denied: PreSendRequestHeaders, insufficient permission.`
- `0x414cff`: ` teams.microsoft.com *.teams.microsoft.com *.skype.com *.teams.microsoft.us local.teams.office.com`
- `0x414d0c`: ` *.powerapps.com`
- `0x414d19`: ` *.yammer.com`
- `0x414d26`: ` *.officeapps.live.com`
- `0x414d33`: ` *.office.com`
- `0x414d40`: ` *.stream.azure-test.net *.microsoftstream.com`
- `0x414d4d`: ` *.dynamics.com`
- `0x414d5a`: ` *.microsoft.com`
- `0x414d67`: ` onedrive.live.com *.onedrive.live.com`
- `0x414e14`: `Content-Security-Policy`

## pseudocode

```c

```

## disassembly

```asm
0x414a90  ldc.i4   0x5561DE
0x414a95  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
0x414a9a  ldc.i4.s 0x64
0x414a9c  ldstr    aSprequestmodul_23// "SPRequestModule.PreSendRequestHeaders B"...
0x414aa1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x414aa6  ldarg.0
0x414aa7  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isAnonymousStaticRequest
0x414aac  brtrue.s loc_414AB6
0x414aae  ldarg.0
0x414aaf  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isPingRequest
0x414ab4  brfalse.s loc_414AB7
0x414ab6  ret
0x414ab7  ldarg.1
0x414ab8  isinst   [System.Web]System.Web.HttpApplication
0x414abd  stloc.0
0x414abe  ldloc.0
0x414abf  brfalse.s loc_414AC9
0x414ac1  ldloc.0
0x414ac2  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x414ac7  br.s     loc_414ACA
0x414ac9  ldnull
0x414aca  stloc.1
0x414acb  ldloc.1
0x414acc  brfalse.s loc_414ADB
0x414ace  ldloc.1
0x414acf  callvirt instance class [System.Web]System.Web.IHttpHandler [System.Web]System.Web.HttpContext::get_Handler()
0x414ad4  isinst   [System.Web]System.Web.UI.Page
0x414ad9  br.s     loc_414ADC
0x414adb  ldnull
0x414adc  stloc.2
0x414add  ldloc.1
0x414ade  brfalse.s loc_414AF2
0x414ae0  ldloc.1
0x414ae1  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x414ae6  ldstr    aSprequestheade// "SPRequestHeadersAdded"
0x414aeb  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x414af0  brfalse.s loc_414AF3
0x414af2  ret
0x414af3  ldloc.1
0x414af4  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x414af9  ldstr    aSprequestmanag_3// "SPRequestManagementRouted"
0x414afe  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x414b03  brfalse.s loc_414B06
0x414b05  ret
0x414b06  ldloc.1
0x414b07  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x414b0c  ldstr    aSprequestheade// "SPRequestHeadersAdded"
0x414b11  ldc.i4.1
0x414b12  box      [mscorlib]System.Boolean
0x414b17  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x414b1c  ldstr    aPresendrequest// "PreSendRequestHeaders"
0x414b21  ldc.i4.s 0x64
0x414b23  ldc.i4.1
0x414b24  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x414b29  stloc.s  0x10
0x414b2b  ldloc.s  0x10
0x414b2d  ldc.i4.0
0x414b2e  ldc.i4.0
0x414b2f  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor(int32 maxAllowedQueries)
0x414b34  stelem.ref
0x414b35  ldloc.s  0x10
0x414b37  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, unsigned int32 maximumExecutionTime, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x414b3c  stloc.s  0x11
0x414b3e  call     class Microsoft.SharePoint.Utilities.SPMonitoredScope Microsoft.SharePoint.Utilities.SPMonitoredScope::get_Current()
0x414b43  stloc.3
0x414b44  ldloc.3
0x414b45  brfalse.s loc_414B84
0x414b47  ldloc.3
0x414b48  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPMonitoredScope::get_Id()
0x414b4d  stloc.s  0x12
0x414b4f  ldloca.s 0x12
0x414b51  constrained. [mscorlib]System.Guid
0x414b57  callvirt instance string [mscorlib]System.Object::ToString()
0x414b5c  stloc.s  4
0x414b5e  ldloc.1
0x414b5f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414b64  ldstr    aSprequestguid// "SPRequestGuid"
0x414b69  ldloc.s  4
0x414b6b  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x414b70  ldloc.1
0x414b71  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414b76  ldstr    aRequestId// "request-id"
0x414b7b  ldloc.s  4
0x414b7d  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x414b82  br.s     loc_414B9A
0x414b84  ldc.i4   0x18C2A3
0x414b89  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Monitoring()
0x414b8e  ldc.i4.s 0xF
0x414b90  ldstr    aCannotGetSpreq// "Cannot get SPRequestUsageMonitoredScope"
0x414b95  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x414b9a  ldloc.1
0x414b9b  call     class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebControls.SPControl::TryGetContextWeb(class [System.Web]System.Web.HttpContext context)
0x414ba0  stloc.s  5
0x414ba2  ldloc.s  5
0x414ba4  brfalse.s loc_414BBE
0x414ba6  ldarg.0
0x414ba7  ldloc.1
0x414ba8  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414bad  ldloc.s  5
0x414baf  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x414bb4  callvirt instance valuetype Microsoft.SharePoint.SPMoveState Microsoft.SharePoint.SPSite::get_MoveState()
0x414bb9  call     instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::EnsureXMoveHeader(class [System.Web]System.Web.HttpResponse response, valuetype Microsoft.SharePoint.SPMoveState moveState)
0x414bbe  ldloc.1
0x414bbf  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414bc4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x414bc9  ldstr    aAccessDenied_0// "Access-Denied"
0x414bce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x414bd3  stloc.s  6
0x414bd5  ldloc.s  6
0x414bd7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x414bdc  brtrue.s loc_414C20
0x414bde  ldloc.s  6
0x414be0  ldstr    aRequestAccessD// "REQUEST_ACCESS_DENIED_RESPONSE"
0x414be5  ldc.i4.5
0x414be6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x414beb  brfalse.s loc_414C20
0x414bed  ldc.i4   0x66746339
0x414bf2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x414bf7  ldc.i4.s 0x32
0x414bf9  ldstr    aAccessDeniedPr// "Access Denied: PreSendRequestHeaders, i"...
0x414bfe  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x414c03  ldloc.1
0x414c04  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414c09  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x414c0e  ldstr    aAccessDenied_0// "Access-Denied"
0x414c13  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x414c18  ldloc.1
0x414c19  ldc.i4.0
0x414c1a  call     bool Microsoft.SharePoint.Utilities.SPUtility::HandleAccessDenied(class [System.Web]System.Web.HttpContext context, [opt] bool allowCompleteRequest)
0x414c1f  pop
0x414c20  ldarg.0
0x414c21  ldfld    class Microsoft.SharePoint.ApplicationRuntime.SPRequestModuleData Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_SPRequestModuleData
0x414c26  brfalse.s loc_414C49
0x414c28  ldarg.0
0x414c29  ldfld    class Microsoft.SharePoint.ApplicationRuntime.SPRequestModuleData Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_SPRequestModuleData
0x414c2e  callvirt instance class Microsoft.SharePoint.ApplicationRuntime.SPDatabaseFile Microsoft.SharePoint.ApplicationRuntime.SPRequestModuleData::get_RequestedFile()
0x414c33  brfalse.s loc_414C49
0x414c35  ldloc.1
0x414c36  call     class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebControls.SPControl::GetContextWeb(class [System.Web]System.Web.HttpContext context)
0x414c3b  stloc.s  5
0x414c3d  ldloc.s  5
0x414c3f  brfalse.s loc_414C49
0x414c41  ldloc.1
0x414c42  ldloc.s  5
0x414c44  call     void Microsoft.SharePoint.WebControls.SPControl::SetResponseCookies(class [System.Web]System.Web.HttpContext context, class Microsoft.SharePoint.SPWeb web)
0x414c49  ldloc.2
0x414c4a  brfalse.s loc_414C68
0x414c4c  ldarg.0
0x414c4d  ldfld    class Microsoft.SharePoint.ApplicationRuntime.SPRequestModuleData Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_SPRequestModuleData
0x414c52  brfalse.s loc_414C68
0x414c54  ldarg.0
0x414c55  ldfld    class Microsoft.SharePoint.ApplicationRuntime.SPRequestModuleData Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_SPRequestModuleData
0x414c5a  callvirt instance class Microsoft.SharePoint.ApplicationRuntime.SPDatabaseFile Microsoft.SharePoint.ApplicationRuntime.SPRequestModuleData::get_RequestedFile()
0x414c5f  brfalse.s loc_414C68
0x414c61  ldloc.2
0x414c62  ldloc.1
0x414c63  call     void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::SetBrowserCacheHeaders(class [System.Web]System.Web.UI.Page page, class [System.Web]System.Web.HttpContext context)
0x414c68  ldloc.1
0x414c69  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x414c6e  ldstr    aCanaryvalidati// "CanaryValidationFailure"
0x414c73  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x414c78  brfalse.s loc_414C9A
0x414c7a  ldloc.1
0x414c7b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414c80  ldc.i4   0x193
0x414c85  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x414c8a  ldloc.1
0x414c8b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414c90  ldstr    aForbidden// "FORBIDDEN"
0x414c95  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusDescription(string)
0x414c9a  ldloc.1
0x414c9b  call     void Microsoft.SharePoint.Utilities.SPUtility::AddCanaryHeaderToResponse(class [System.Web]System.Web.HttpContext context)
0x414ca0  ldloc.1
0x414ca1  call     void Microsoft.SharePoint.Utilities.SPUtility::AddHstsHeaderToResponse(class [System.Web]System.Web.HttpContext context)
0x414ca6  ldloc.1
0x414ca7  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x414cac  ldsfld   string Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::AllowFramingFlag
0x414cb1  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x414cb6  brtrue   loc_414E25
0x414cbb  call     int32 Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_ContextCompatibilityLevel()
0x414cc0  ldc.i4.s 0xE
0x414cc2  beq      loc_414E25
0x414cc7  ldloc.1
0x414cc8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x414ccd  call     bool Microsoft.SharePoint.Utilities.SharePointDesktopUtilities::IsSharePointDesktop(class [System.Web]System.Web.HttpRequest request)
0x414cd2  brtrue   loc_414E25
0x414cd7  ldloc.1
0x414cd8  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414cdd  ldstr    aXFrameOptions// "X-FRAME-OPTIONS"
0x414ce2  ldstr    aSameorigin// "SAMEORIGIN"
0x414ce7  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x414cec  ldstr    aFrameAncestors// "frame-ancestors 'self'"
0x414cf1  ldc.i4   0x400
0x414cf6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string, int32)
0x414cfb  stloc.s  7
0x414cfd  ldloc.s  7
0x414cff  ldstr    aTeamsMicrosoft// " teams.microsoft.com *.teams.microsoft."...
0x414d04  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d09  pop
0x414d0a  ldloc.s  7
0x414d0c  ldstr    aPowerappsCom// " *.powerapps.com"
0x414d11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d16  pop
0x414d17  ldloc.s  7
0x414d19  ldstr    aYammerCom// " *.yammer.com"
0x414d1e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d23  pop
0x414d24  ldloc.s  7
0x414d26  ldstr    aOfficeappsLive// " *.officeapps.live.com"
0x414d2b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d30  pop
0x414d31  ldloc.s  7
0x414d33  ldstr    aOfficeCom// " *.office.com"
0x414d38  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d3d  pop
0x414d3e  ldloc.s  7
0x414d40  ldstr    aStreamAzureTes// " *.stream.azure-test.net *.microsoftstr"...
0x414d45  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d4a  pop
0x414d4b  ldloc.s  7
0x414d4d  ldstr    aDynamicsCom// " *.dynamics.com"
0x414d52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d57  pop
0x414d58  ldloc.s  7
0x414d5a  ldstr    aMicrosoftCom// " *.microsoft.com"
0x414d5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d64  pop
0x414d65  ldloc.s  7
0x414d67  ldstr    aOnedriveLiveCo// " onedrive.live.com *.onedrive.live.com"
0x414d6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414d71  pop
0x414d72  ldnull
0x414d73  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x414d78  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x414d7d  brfalse.s loc_414DE8
0x414d7f  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x414d84  ldsfld   string Microsoft.SharePoint.Administration.SPFarm::AllowIframeAppAuthorizePageDomainsListName
0x414d89  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.SharePoint.Administration.SPFarm::GetGenericAllowedListValues(string allowedListName)
0x414d8e  stloc.s  8
0x414d90  ldloc.s  8
0x414d92  brtrue.s loc_414DA5
0x414d94  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x414d99  ldstr    aAllowiframeapp_0// "AllowIframeAppAuthorizePageDomains2"
0x414d9e  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.SharePoint.Administration.SPFarm::GetGenericAllowedListValues(string allowedListName)
0x414da3  stloc.s  8
0x414da5  ldloc.s  8
0x414da7  brfalse.s loc_414DE8
0x414da9  ldloc.s  8
0x414dab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::GetEnumerator()
0x414db0  stloc.s  0x13
0x414db2  br.s     loc_414DD1
0x414db4  ldloc.s  0x13
0x414db6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x414dbb  stloc.s  9
0x414dbd  ldloc.s  7
0x414dbf  ldstr    asc_C68BFA// " "
0x414dc4  ldloc.s  9
0x414dc6  call     string [mscorlib]System.String::Concat(string, string)
0x414dcb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414dd0  pop
0x414dd1  ldloc.s  0x13
0x414dd3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x414dd8  brtrue.s loc_414DB4
0x414dda  leave.s  loc_414DE8
0x414ddc  ldloc.s  0x13
0x414dde  brfalse.s loc_414DE7
0x414de0  ldloc.s  0x13
0x414de2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x414de7  endfinally
0x414de8  ldloc.s  7
0x414dea  ldstr    asc_C76744// ";"
0x414def  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x414df4  pop
0x414df5  ldnull
0x414df6  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x414dfb  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x414e00  brfalse.s loc_414E25
0x414e02  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x414e07  callvirt instance bool Microsoft.SharePoint.Administration.SPFarm::get_EnableCSPHeaderForPage()
0x414e0c  brfalse.s loc_414E25
0x414e0e  ldloc.1
0x414e0f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414e14  ldstr    aContentSecurit// "Content-Security-Policy"
0x414e19  ldloc.s  7
0x414e1b  callvirt instance string [mscorlib]System.Object::ToString()
0x414e20  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0x414e25  ldloc.1
0x414e26  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x414e2b  ldstr    aClientRequestI// "client-request-id"
0x414e30  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x414e35  isinst   [mscorlib]System.String
0x414e3a  stloc.s  0xA
0x414e3c  ldloc.s  0xA
0x414e3e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x414e43  brtrue.s loc_414E57
0x414e45  ldloc.1
0x414e46  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x414e4b  ldstr    aClientRequestI// "client-request-id"
0x414e50  ldloc.s  0xA
0x414e52  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
  ... truncated ...
```
