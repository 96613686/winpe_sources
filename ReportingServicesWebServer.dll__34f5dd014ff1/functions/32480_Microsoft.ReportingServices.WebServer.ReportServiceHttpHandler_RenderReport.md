# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderReport

- ea: `0x32480`
- end: `0x32626`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderReport`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x2bbd0`
- `0x2bcc0`
- `0x31ed0`
- `0x31fb0`
- `0x321b0`
- `0x32280`
- `0x32480`
- `0x329a0`
- `0x32a90`
- `0x3cc00`

## string_xrefs

- `0x32480`: `ReportServiceHttpHandler.RenderReport`

## pseudocode

```c

```

## disassembly

```asm
0x32480  ldstr    aReportserviceh_9// "ReportServiceHttpHandler.RenderReport"
0x32485  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3248a  stloc.0
0x3248b  ldc.i4.2
0x3248c  call     void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::EnsureHttpsLevel(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.HttpsLevel level)
0x32491  ldarg.0
0x32492  ldstr    aResetsession// "ResetSession"
0x32497  ldc.i4.0
0x32498  call     instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::GetBoolRequestParam(string, bool)
0x3249d  ldarg.1
0x3249e  ldarg.0
0x3249f  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x324a4  ldarg.0
0x324a5  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x324aa  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x324af  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionfulClientRequest::InitForRequest(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x324b4  ldarg.1
0x324b5  isinst   Microsoft.ReportingServices.WebServer.HttpClientRequest
0x324ba  stloc.1
0x324bb  ldarg.0
0x324bc  call     instance class Microsoft.ReportingServices.WebServer.HttpResponseStreamFactory Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_ResponseStreamFactory()
0x324c1  callvirt instance class Microsoft.ReportingServices.WebServer.ResponseHeaderData Microsoft.ReportingServices.WebServer.HttpResponseStreamFactory::get_ResponseHeaderData()
0x324c6  ldloc.1
0x324c7  callvirt instance void Microsoft.ReportingServices.WebServer.ResponseHeaderData::set_SessionManager(class Microsoft.ReportingServices.WebServer.HttpClientRequest value)
0x324cc  ldarg.0
0x324cd  call     instance class HttpResponseWrapper Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_HttpResponseWriter()
0x324d2  ldloc.1
0x324d3  callvirt instance void HttpResponseWrapper::set_SessionManager(class Microsoft.ReportingServices.WebServer.HttpClientRequest value)
0x324d8  ldarg.0
0x324d9  call     instance bool Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_UseCookieSession()
0x324de  brtrue.s loc_3251A
0x324e0  ldarg.0
0x324e1  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x324e6  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x324eb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x324f0  ldstr    aSessionid// "SessionID"
0x324f5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x324fa  ldarg.0
0x324fb  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x32500  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x32505  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x3250a  ldstr    aSessionid// "SessionID"
0x3250f  ldarg.1
0x32510  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_SessionID()
0x32515  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x3251a  brfalse.s loc_3252D
0x3251c  ldarg.1
0x3251d  ldarg.0
0x3251e  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x32523  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ResetExecutionAction::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x32528  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ResetExecutionAction::Save()
0x3252d  ldarg.0
0x3252e  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x32533  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x32538  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x3253d  ldstr    aIfModifiedSinc// "If-Modified-Since"
0x32542  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x32547  stloc.2
0x32548  ldarg.1
0x32549  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_IsNew()
0x3254e  brtrue.s loc_325A4
0x32550  ldarg.1
0x32551  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_DontCache()
0x32556  brtrue.s loc_325A4
0x32558  ldloc.2
0x32559  brfalse.s loc_325A4
0x3255b  ldloc.2
0x3255c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x32561  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x32566  ldarg.1
0x32567  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionReportItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x3256c  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionReportItem::get_SessionCreationTime()
0x32571  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x32576  brfalse.s loc_3259F
0x32578  ldarg.1
0x32579  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionReportItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x3257e  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionReportItem::get_AwaitingFirstExecution()
0x32583  brtrue.s loc_3259F
0x32585  ldarg.0
0x32586  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x3258b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x32590  ldc.i4   0x130
0x32595  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x3259a  leave    loc_32625
0x3259f  leave.s  loc_325A4
0x325a1  pop
0x325a2  leave.s  loc_325A4
0x325a4  ldarg.0
0x325a5  ldstr    aGetnextstream// "GetNextStream"
0x325aa  ldc.i4.0
0x325ab  call     instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::GetBoolRequestParam(string, bool)
0x325b0  stloc.3
0x325b1  ldarg.0
0x325b2  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x325b7  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x325bc  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_ImageIDParamValue()
0x325c1  stloc.s  4
0x325c3  ldarg.1
0x325c4  ldloc.s  4
0x325c6  ldloc.3
0x325c7  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::IsFirstRequest(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionfulClientRequest, string, bool)
0x325cc  pop
0x325cd  ldarg.1
0x325ce  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_RedirectRequired()
0x325d3  brfalse.s loc_32612
0x325d5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x325da  ldarg.1
0x325db  isinst   Microsoft.ReportingServices.WebServer.CookielessClientRequest
0x325e0  ldnull
0x325e1  cgt.un
0x325e3  ldstr    aSessionmanager// "sessionManager is CookieLessClientReque"...
0x325e8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x325ed  ldarg.1
0x325ee  ldarg.0
0x325ef  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x325f4  ldarg.0
0x325f5  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x325fa  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateNewSessionAction::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext)
0x325ff  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateNewSessionAction::Save()
0x32604  ldarg.0
0x32605  ldarg.1
0x32606  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ClientRequest::get_SessionID()
0x3260b  call     instance void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::CookielessSessionRedirect(string sessionId)
0x32610  leave.s  loc_32625
0x32612  ldarg.0
0x32613  ldarg.1
0x32614  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::RenderReport(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionfulClientRequest)
0x32619  leave.s  loc_32625
0x3261b  ldloc.0
0x3261c  brfalse.s loc_32624
0x3261e  ldloc.0
0x3261f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32624  endfinally
0x32625  ret
```
