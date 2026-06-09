# Microsoft.ReportingServices.WebServer.Global::DispatchRequest

- ea: `0x2d120`
- end: `0x2d58f`
- name: `Microsoft.ReportingServices.WebServer.Global::DispatchRequest`
- size: `1135`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x2c6e0`

## callees

- `0x2c9d0`
- `0x2ca30`
- `0x2ccb0`
- `0x2cdf0`
- `0x2d000`
- `0x2d120`
- `0x2d590`
- `0x2d5c0`
- `0x2d610`
- `0x2d630`
- `0x2d660`
- `0x2d6b0`
- `0x2d7e0`
- `0x2d8a0`
- `0x2d930`
- `0x2da70`
- `0x2db50`
- `0x2e110`

## string_xrefs

- `0x2d393`: `localredirect has been rejected as redirect URL does not point to registered local directory! URL: {0}`
- `0x2d45f`: `/LoginComplete.aspx`
- `0x2d476`: `/DeliveryExtensionUI.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x2d120  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.WebConfigUtil::get_UsingFormsAuth()
0x2d125  stloc.0
0x2d126  ldloc.0
0x2d127  brfalse.s loc_2D170
0x2d129  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d12e  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x2d133  brtrue.s loc_2D170
0x2d135  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d13a  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2d13f  ldstr    aRsnotauthentic// "RSNotAuthenticated"
0x2d144  ldc.i4.1
0x2d145  stloc.2
0x2d146  ldloca.s 2
0x2d148  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d14d  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x2d152  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x2d157  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d15c  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2d161  ldstr    aRsauthenticati// "RSAuthenticationHeader"
0x2d166  call     string [System.Web]System.Web.Security.FormsAuthentication::get_FormsCookieName()
0x2d16b  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x2d170  ldarg.0
0x2d171  call     instance void Microsoft.ReportingServices.WebServer.Global::SetCustomHeadersIfNeeded()
0x2d176  ldarg.0
0x2d177  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d17c  call     instance bool Microsoft.ReportingServices.WebServer.Global::HandleCorsRequest(class [System.Web]System.Web.HttpContext context)
0x2d181  brfalse.s loc_2D185
0x2d183  ldc.i4.1
0x2d184  ret
0x2d185  call     bool Microsoft.ReportingServices.WebServer.Global::get_IsGetRequest()
0x2d18a  brtrue.s loc_2D193
0x2d18c  call     bool Microsoft.ReportingServices.WebServer.Global::get_IsSharepointClientGetRequest()
0x2d191  brfalse.s loc_2D1B6
0x2d193  ldarg.0
0x2d194  ldloca.s 3
0x2d196  call     instance bool Microsoft.ReportingServices.WebServer.Global::HandleWsdlRequest([out] bool& autogenerateWsdl)
0x2d19b  brfalse.s loc_2D1A2
0x2d19d  ldloc.3
0x2d19e  ldc.i4.0
0x2d19f  ceq
0x2d1a1  ret
0x2d1a2  ldarg.0
0x2d1a3  call     instance bool Microsoft.ReportingServices.WebServer.Global::HandleRequestForXsdResource()
0x2d1a8  brfalse.s loc_2D1AC
0x2d1aa  ldc.i4.1
0x2d1ab  ret
0x2d1ac  ldarg.0
0x2d1ad  call     instance bool Microsoft.ReportingServices.WebServer.Global::get_IsRequestForAspNetResource()
0x2d1b2  brfalse.s loc_2D1B6
0x2d1b4  ldc.i4.0
0x2d1b5  ret
0x2d1b6  ldarg.0
0x2d1b7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d1bc  call     instance string Microsoft.ReportingServices.WebServer.Global::GetSoapActionHeader(class [System.Web]System.Web.HttpContext context)
0x2d1c1  stloc.1
0x2d1c2  ldloc.1
0x2d1c3  brfalse  loc_2D249
0x2d1c8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d1cd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x2d1d2  brfalse.s loc_2D1EE
0x2d1d4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d1d9  ldc.i4.4
0x2d1da  ldstr    aSoapaction0// "SoapAction: {0}"
0x2d1df  ldc.i4.1
0x2d1e0  newarr   [mscorlib]System.Object
0x2d1e5  dup
0x2d1e6  ldc.i4.0
0x2d1e7  ldloc.1
0x2d1e8  stelem.ref
0x2d1e9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2d1ee  ldarg.0
0x2d1ef  call     instance bool Microsoft.ReportingServices.WebServer.Global::IsReportServerAsmx()
0x2d1f4  brfalse.s loc_2D203
0x2d1f6  ldc.i4.0
0x2d1f7  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.Global::GetRSService(bool checkSharePointAccess)
0x2d1fc  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::ImpersonateClient()
0x2d201  ldc.i4.0
0x2d202  ret
0x2d203  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d208  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x2d20d  brfalse.s loc_2D247
0x2d20f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d214  ldc.i4.4
0x2d215  ldstr    aSoapRequest// "SOAP request "
0x2d21a  ldc.i4.1
0x2d21b  newarr   [mscorlib]System.Object
0x2d220  dup
0x2d221  ldc.i4.0
0x2d222  ldloc.1
0x2d223  ldstr    aForUnknownUrl// " for unknown URL"
0x2d228  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d22d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d232  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2d237  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x2d23c  call     string [mscorlib]System.String::Concat(string, string, string)
0x2d241  stelem.ref
0x2d242  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2d247  ldc.i4.1
0x2d248  ret
0x2d249  ldloc.0
0x2d24a  brfalse  loc_2D454
0x2d24f  call     string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.WebConfigUtil::get_LoginUrl()
0x2d254  stloc.s  4
0x2d256  ldloc.s  4
0x2d258  ldstr    asc_424FC// "/"
0x2d25d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2d262  brfalse.s loc_2D271
0x2d264  ldloc.s  4
0x2d266  ldc.i4.s 0x2F
0x2d268  ldc.i4.s 0x5C
0x2d26a  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x2d26f  stloc.s  4
0x2d271  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d276  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d27b  callvirt instance string [System.Web]System.Web.HttpRequest::get_PhysicalPath()
0x2d280  ldloc.s  4
0x2d282  ldc.i4.5
0x2d283  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2d288  brfalse.s loc_2D28C
0x2d28a  ldc.i4.0
0x2d28b  ret
0x2d28c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d291  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d296  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2d29b  callvirt instance string [System]System.Uri::get_LocalPath()
0x2d2a0  ldc.i4.1
0x2d2a1  newarr   [mscorlib]System.Char
0x2d2a6  dup
0x2d2a7  ldc.i4.0
0x2d2a8  ldc.i4.s 0x2F
0x2d2aa  stelem.i2
0x2d2ab  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2d2b0  ldstr    aLocalredirect// "localredirect"
0x2d2b5  ldc.i4.5
0x2d2b6  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2d2bb  brfalse  loc_2D3CF
0x2d2c0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d2c5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d2ca  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2d2cf  callvirt instance string [System]System.Uri::get_Query()
0x2d2d4  ldstr    aUrl// "?url"
0x2d2d9  call     instance int32 [mscorlib]System.String::get_Length()
0x2d2de  ldc.i4.1
0x2d2df  add
0x2d2e0  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2d2e5  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.UrlUtil::UrlDecode(string)
0x2d2ea  stloc.s  5
0x2d2ec  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x2d2f1  ldc.i4.8
0x2d2f2  stloc.s  6
0x2d2f4  ldloca.s 6
0x2d2f6  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches
0x2d2fc  callvirt instance string [mscorlib]System.Object::ToString()
0x2d301  ldc.i4.1
0x2d302  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, bool)
0x2d307  brfalse  loc_2D3B1
0x2d30c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d311  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x2d316  brfalse.s loc_2D32F
0x2d318  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d31d  ldc.i4.4
0x2d31e  ldstr    aValidatingLoca// "Validating localredirect URL: {0}"
0x2d323  ldloc.s  5
0x2d325  call     string [mscorlib]System.String::Format(string, object)
0x2d32a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2d32f  ldc.i4.1
0x2d330  stloc.s  7
0x2d332  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2d337  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x2d33c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::get_Values()
0x2d341  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::GetEnumerator()
0x2d346  stloc.s  8
0x2d348  br.s     loc_2D370
0x2d34a  ldloca.s 8
0x2d34c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::get_Current()
0x2d351  stloc.s  9
0x2d353  ldloc.s  5
0x2d355  callvirt instance string [mscorlib]System.String::ToLower()
0x2d35a  ldloc.s  9
0x2d35c  ldfld    string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration::VirtualRoot
0x2d361  callvirt instance string [mscorlib]System.String::ToLower()
0x2d366  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2d36b  brfalse.s loc_2D370
0x2d36d  ldc.i4.0
0x2d36e  stloc.s  7
0x2d370  ldloca.s 8
0x2d372  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::MoveNext()
0x2d377  brtrue.s loc_2D34A
0x2d379  leave.s  loc_2D389
0x2d37b  ldloca.s 8
0x2d37d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>
0x2d383  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d388  endfinally
0x2d389  ldloc.s  7
0x2d38b  brfalse.s loc_2D3B1
0x2d38d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningRequestsTracer()
0x2d392  ldc.i4.2
0x2d393  ldstr    aLocalredirectH// "localredirect has been rejected as redi"...
0x2d398  ldloc.s  5
0x2d39a  call     string [mscorlib]System.String::Format(string, object)
0x2d39f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2d3a4  ldarg.0
0x2d3a5  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2d3aa  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x2d3af  ldc.i4.0
0x2d3b0  ret
0x2d3b1  ldloc.s  5
0x2d3b3  ldstr    asc_424FC// "/"
0x2d3b8  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x2d3bd  brfalse.s loc_2D3CD
0x2d3bf  ldarg.0
0x2d3c0  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2d3c5  ldloc.s  5
0x2d3c7  ldc.i4.0
0x2d3c8  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x2d3cd  ldc.i4.0
0x2d3ce  ret
0x2d3cf  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d3d4  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x2d3d9  brtrue.s loc_2D454
0x2d3db  ldc.i4.5
0x2d3dc  newarr   [mscorlib]System.String
0x2d3e1  dup
0x2d3e2  ldc.i4.0
0x2d3e3  call     string [System.Web]System.Web.Security.FormsAuthentication::get_LoginUrl()
0x2d3e8  stelem.ref
0x2d3e9  dup
0x2d3ea  ldc.i4.1
0x2d3eb  ldstr    aReturnurl// "?ReturnUrl="
0x2d3f0  stelem.ref
0x2d3f1  dup
0x2d3f2  ldc.i4.2
0x2d3f3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d3f8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d3fd  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x2d402  stelem.ref
0x2d403  dup
0x2d404  ldc.i4.3
0x2d405  ldstr    aLocalredirectU// "/localredirect?url="
0x2d40a  stelem.ref
0x2d40b  dup
0x2d40c  ldc.i4.4
0x2d40d  ldarg.0
0x2d40e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d413  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2d418  callvirt instance string [System]System.Uri::get_LocalPath()
0x2d41d  ldarg.0
0x2d41e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d423  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2d428  callvirt instance string [System]System.Uri::get_Query()
0x2d42d  call     string [mscorlib]System.String::Concat(string, string)
0x2d432  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.UrlUtil::UrlEncode(string)
0x2d437  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.UrlUtil::UrlEncode(string)
0x2d43c  stelem.ref
0x2d43d  call     string [mscorlib]System.String::Concat(string[])
0x2d442  stloc.s  0xA
0x2d444  ldarg.0
0x2d445  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2d44a  ldloc.s  0xA
0x2d44c  ldc.i4.0
0x2d44d  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x2d452  ldc.i4.0
0x2d453  ret
0x2d454  ldarg.0
0x2d455  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d45a  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d45f  ldstr    aLogincompleteA// "/LoginComplete.aspx"
0x2d464  call     bool Microsoft.ReportingServices.WebServer.Global::IsRequestToPage(string path, string pageName)
0x2d469  brtrue.s loc_2D482
0x2d46b  ldarg.0
0x2d46c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d471  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d476  ldstr    aDeliveryextens// "/DeliveryExtensionUI.aspx"
0x2d47b  call     bool Microsoft.ReportingServices.WebServer.Global::IsRequestToPage(string path, string pageName)
0x2d480  brfalse.s loc_2D484
0x2d482  ldc.i4.0
0x2d483  ret
0x2d484  ldarg.0
0x2d485  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d48a  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d48f  call     bool Microsoft.ReportingServices.WebServer.Global::IsRequestToImage(string path)
0x2d494  brfalse.s loc_2D49D
0x2d496  ldarg.0
0x2d497  call     instance bool Microsoft.ReportingServices.WebServer.Global::HandleServerImages()
0x2d49c  ret
0x2d49d  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2d4a2  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_EnablePowerBIFeatures()
0x2d4a7  brfalse.s loc_2D4DC
0x2d4a9  ldarg.0
0x2d4aa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x2d4af  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x2d4b4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2d4b9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2d4be  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x2d4c3  ldstr    aPagesLogintopo// "/Pages/LoginToPowerBI.aspx"
0x2d4c8  call     string [mscorlib]System.String::Concat(string, string)
0x2d4cd  ldc.i4.1
0x2d4ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d4d3  callvirt instance bool [mscorlib]System.String::StartsWith(string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x2d4d8  brfalse.s loc_2D4DC
  ... truncated ...
```
