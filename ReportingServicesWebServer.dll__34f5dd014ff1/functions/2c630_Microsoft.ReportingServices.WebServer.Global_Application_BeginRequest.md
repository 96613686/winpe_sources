# Microsoft.ReportingServices.WebServer.Global::Application_BeginRequest

- ea: `0x2c630`
- end: `0x2c6dd`
- name: `Microsoft.ReportingServices.WebServer.Global::Application_BeginRequest`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2c4a0`
- `0x2c630`
- `0x2da10`
- `0x2e0d0`
- `0x2e0f0`
- `0x33100`
- `0x38a80`

## string_xrefs

- `0x2c6a1`: `Configuration/IsWebServiceEnabled is false in RSReportServer.config but global.asax doesn't point to Microsoft.ReportingServices.WebServer.StoppedApplication application.`

## pseudocode

```c

```

## disassembly

```asm
0x2c630  ldarg.0
0x2c631  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2c636  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::ApplySecurityHeaders(class [System.Web]System.Web.HttpResponse response)
0x2c63b  ldarg.0
0x2c63c  ldstr    aNewRequestUrl// "New request - URL = "
0x2c641  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2c646  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2c64b  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x2c650  call     string [mscorlib]System.String::Concat(string, string)
0x2c655  stfld    string Microsoft.ReportingServices.WebServer.Global::scope
0x2c65a  ldarg.0
0x2c65b  ldfld    string Microsoft.ReportingServices.WebServer.Global::scope
0x2c660  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x2c665  pop
0x2c666  ldstr    aGlobalApplicat_3// "Global.Application_BeginRequest"
0x2c66b  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x2c670  stloc.0
0x2c671  call     void Microsoft.ReportingServices.WebServer.Global::MarkExecutingInRs()
0x2c676  call     void Microsoft.ReportingServices.WebServer.Global::StartApp()
0x2c67b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x2c680  ldsfld   bool Microsoft.ReportingServices.WebServer.Global::m_appStarted
0x2c685  ldstr    aMAppstarted// "m_appStarted"
0x2c68a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2c68f  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2c694  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_IsWebServiceEnabled()
0x2c699  brtrue.s loc_2C6BC
0x2c69b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x2c6a0  ldc.i4.1
0x2c6a1  ldstr    aConfigurationI// "Configuration/IsWebServiceEnabled is fa"...
0x2c6a6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2c6ab  ldarg.0
0x2c6ac  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x2c6b1  call     void Microsoft.ReportingServices.WebServer.StoppedApplication::WriteServiceUnavailable(class [System.Web]System.Web.HttpResponse response)
0x2c6b6  ldarg.0
0x2c6b7  call     instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x2c6bc  leave.s  loc_2C6CB
0x2c6be  call     void Microsoft.ReportingServices.WebServer.Global::WriteServerError(class [mscorlib]System.Exception e)
0x2c6c3  ldarg.0
0x2c6c4  call     instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x2c6c9  leave.s  loc_2C6CB
0x2c6cb  call     void Microsoft.ReportingServices.WebServer.Global::UnmarkExecutingInRs()
0x2c6d0  leave.s  loc_2C6DC
0x2c6d2  ldloc.0
0x2c6d3  brfalse.s loc_2C6DB
0x2c6d5  ldloc.0
0x2c6d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c6db  endfinally
0x2c6dc  ret
```
