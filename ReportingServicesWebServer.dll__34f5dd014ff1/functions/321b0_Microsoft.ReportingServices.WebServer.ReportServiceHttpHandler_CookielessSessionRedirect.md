# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::CookielessSessionRedirect

- ea: `0x321b0`
- end: `0x3227b`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::CookielessSessionRedirect`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x32480`

## callees

- `0x2dc30`
- `0x31ed0`
- `0x32040`
- `0x321b0`

## string_xrefs

- `0x321e8`: `rs:TrustedUserToken`
- `0x321b0`: `ReportServiceHttpHandler.CookielessSessionRedirect`

## pseudocode

```c

```

## disassembly

```asm
0x321b0  ldstr    aReportserviceh_4// "ReportServiceHttpHandler.CookielessSess"...
0x321b5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x321ba  stloc.0
0x321bb  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.WebServer.Global::get_RequestParameters()
0x321c0  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(class [System]System.Collections.Specialized.NameValueCollection)
0x321c5  stloc.1
0x321c6  ldloc.1
0x321c7  ldstr    aRsSessionid_0// "rs:SessionID"
0x321cc  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x321d1  ldloc.1
0x321d2  ldstr    aRsClearsession// "rs:ClearSession"
0x321d7  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x321dc  ldloc.1
0x321dd  ldstr    aRsTrustedusern// "rs:TrustedUserName"
0x321e2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x321e7  ldloc.1
0x321e8  ldstr    aRsTrustedusert// "rs:TrustedUserToken"
0x321ed  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x321f2  ldarg.0
0x321f3  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x321f8  ldarg.0
0x321f9  call     instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x321fe  ldstr    aPath_0// "Path"
0x32203  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator, string, string)
0x32208  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext)
0x3220d  stloc.2
0x3220e  ldloc.2
0x3220f  ldloc.1
0x32210  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendUnparsedParameters(class [System]System.Collections.Specialized.NameValueCollection)
0x32215  ldloc.2
0x32216  ldstr    aSessionid// "SessionID"
0x3221b  ldarg.1
0x3221c  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string, string)
0x32221  ldarg.0
0x32222  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x32227  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x3222c  ldloc.2
0x3222d  callvirt instance string [mscorlib]System.Object::ToString()
0x32232  ldc.i4.0
0x32233  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x32238  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x3223d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x32242  brfalse.s loc_3226E
0x32244  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x32249  ldc.i4.4
0x3224a  ldstr    aRedirectingRep// "Redirecting report request to '{0}'"
0x3224f  ldc.i4.1
0x32250  newarr   [mscorlib]System.Object
0x32255  dup
0x32256  ldc.i4.0
0x32257  ldarg.0
0x32258  call     instance string Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_UrlPrefix()
0x3225d  ldarg.0
0x3225e  call     instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x32263  call     string [mscorlib]System.String::Concat(string, string)
0x32268  stelem.ref
0x32269  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3226e  leave.s  loc_3227A
0x32270  ldloc.0
0x32271  brfalse.s loc_32279
0x32273  ldloc.0
0x32274  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32279  endfinally
0x3227a  ret
```
