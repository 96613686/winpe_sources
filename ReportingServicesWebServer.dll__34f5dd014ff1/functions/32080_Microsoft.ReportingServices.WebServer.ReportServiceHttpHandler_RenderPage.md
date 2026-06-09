# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderPage

- ea: `0x32080`
- end: `0x3216e`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderPage`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x31ee0`

## callees

- `0x31ed0`
- `0x32080`
- `0x326d0`
- `0x32a90`
- `0x388d0`

## string_xrefs

- `0x32080`: `ReportServiceHttpHandler.RenderPage`
- `0x320ca`: `Reporting Services error `
- `0x32102`: `Reporting Services Error`

## pseudocode

```c

```

## disassembly

```asm
0x32080  ldstr    aReportserviceh_1// "ReportServiceHttpHandler.RenderPage"
0x32085  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3208a  stloc.0
0x3208b  ldc.i4.3
0x3208c  call     void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::EnsureHttpsLevel(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.HttpsLevel level)
0x32091  ldarg.0
0x32092  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::ExecuteCommand()
0x32097  ldarg.0
0x32098  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x3209d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x320a2  ldarg.0
0x320a3  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x320a8  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x320ad  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyCacheControlHeaders(class [System.Web]System.Web.HttpRequest request, class [System.Web]System.Web.HttpResponse response)
0x320b2  leave    loc_3216D
0x320b7  stloc.1
0x320b8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x320bd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x320c2  brfalse.s loc_320DF
0x320c4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x320c9  ldc.i4.1
0x320ca  ldstr    aReportingServi// "Reporting Services error "
0x320cf  ldloc.1
0x320d0  callvirt instance string [mscorlib]System.Object::ToString()
0x320d5  call     string [mscorlib]System.String::Concat(string, string)
0x320da  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x320df  ldloc.1
0x320e0  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x320e5  ldc.i4.s 0x59
0x320e7  bne.un.s loc_320FC
0x320e9  ldarg.0
0x320ea  ldc.i4   0x193
0x320ef  ldstr    aForbidden// "Forbidden"
0x320f4  ldloc.1
0x320f5  call     instance void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderError(int32 code, string shortHttpDescription, class [mscorlib]System.Exception e)
0x320fa  leave.s  loc_3216D
0x320fc  ldarg.0
0x320fd  ldc.i4   0x1F4
0x32102  ldstr    aReportingServi_0// "Reporting Services Error"
0x32107  ldloc.1
0x32108  call     instance void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderError(int32 code, string shortHttpDescription, class [mscorlib]System.Exception e)
0x3210d  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_RecycleOnSevereErrors()
0x32112  brfalse.s loc_3211A
0x32114  ldloc.1
0x32115  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utils.NativeMethodsGeneral::RecycleOnSevereException(class [mscorlib]System.Exception)
0x3211a  leave.s  loc_3216D
0x3211c  stloc.2
0x3211d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x32122  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x32127  brfalse.s loc_32143
0x32129  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x3212e  ldc.i4.1
0x3212f  ldstr    aInternalError0// "Internal error: {0}"
0x32134  ldc.i4.1
0x32135  newarr   [mscorlib]System.Object
0x3213a  dup
0x3213b  ldc.i4.0
0x3213c  ldloc.2
0x3213d  stelem.ref
0x3213e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x32143  ldarg.0
0x32144  ldc.i4   0x1F4
0x32149  ldstr    aInternalError// "Internal Error"
0x3214e  ldloc.2
0x3214f  call     instance void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderError(int32 code, string shortHttpDescription, class [mscorlib]System.Exception e)
0x32154  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_RecycleOnSevereErrors()
0x32159  brfalse.s loc_32161
0x3215b  ldloc.2
0x3215c  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Utils.NativeMethodsGeneral::RecycleOnSevereException(class [mscorlib]System.Exception)
0x32161  leave.s  loc_3216D
0x32163  ldloc.0
0x32164  brfalse.s loc_3216C
0x32166  ldloc.0
0x32167  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3216c  endfinally
0x3216d  ret
```
