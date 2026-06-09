# Microsoft.Reporting.WebForms.HttpHandler::ProcessRequest

- ea: `0x7eb0`
- end: `0x7f93`
- name: `Microsoft.Reporting.WebForms.HttpHandler::ProcessRequest`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x7eb0`
- `0x7fa0`
- `0x7fb0`
- `0x7fc0`
- `0x80a0`
- `0x80c0`
- `0x81b0`

## string_xrefs

- `0x7f5a`: `SERVER_PROTOCOL`

## pseudocode

```c

```

## disassembly

```asm
0x7eb0  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.Reporting.WebForms.HttpHandler::get_RequestParameters()
0x7eb5  ldstr    aOptype// "OpType"
0x7eba  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7ebf  stloc.0
0x7ec0  ldarg.0
0x7ec1  callvirt instance class Microsoft.Reporting.WebForms.IReportServerConnectionProvider Microsoft.Reporting.WebForms.HttpHandler::GetConnectionProvider()
0x7ec6  dup
0x7ec7  brtrue.s loc_7ECF
0x7ec9  pop
0x7eca  newobj   instance void Microsoft.Reporting.WebForms.DefaultReportServerConnectionProvider::.ctor()
0x7ecf  stloc.1
0x7ed0  ldstr    aWebformHttphan// "WebForm::HttpHandler.ProcessRequest - o"...
0x7ed5  ldloc.0
0x7ed6  ldarg.1
0x7ed7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7edc  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x7ee1  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::NewFormat(string, object, object)
0x7ee6  stloc.2
0x7ee7  ldarg.0
0x7ee8  ldloc.0
0x7ee9  ldloc.1
0x7eea  callvirt instance class Microsoft.Reporting.WebForms.HandlerOperation Microsoft.Reporting.WebForms.HttpHandler::GetHandler(string operationType, class Microsoft.Reporting.WebForms.IReportServerConnectionProvider connectionProvider)
0x7eef  stloc.3
0x7ef0  ldloc.3
0x7ef1  brtrue.s loc_7F08
0x7ef3  ldarg.1
0x7ef4  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7ef9  ldc.i4   0x194
0x7efe  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x7f03  leave    loc_7F92
0x7f08  ldarg.1
0x7f09  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7f0e  ldc.i4   0xC8
0x7f13  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x7f18  ldloc.3
0x7f19  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.Reporting.WebForms.HttpHandler::get_RequestParameters()
0x7f1e  ldarg.1
0x7f1f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7f24  callvirt instance void Microsoft.Reporting.WebForms.HandlerOperation::PerformOperation(class [System]System.Collections.Specialized.NameValueCollection urlQuery, class [System.Web]System.Web.HttpResponse response)
0x7f29  ldloc.3
0x7f2a  callvirt instance bool Microsoft.Reporting.WebForms.HandlerOperation::get_IsCacheable()
0x7f2f  brfalse.s loc_7F42
0x7f31  ldarg.1
0x7f32  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7f37  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x7f3c  ldc.i4.4
0x7f3d  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x7f42  ldarg.1
0x7f43  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7f48  callvirt instance bool [System.Web]System.Web.HttpResponse::get_BufferOutput()
0x7f4d  brtrue.s loc_7F7C
0x7f4f  ldarg.1
0x7f50  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7f55  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x7f5a  ldstr    aServerProtocol// "SERVER_PROTOCOL"
0x7f5f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7f64  ldstr    aHttp10// "HTTP/1.0"
0x7f69  ldc.i4.5
0x7f6a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x7f6f  brfalse.s loc_7F7C
0x7f71  ldarg.1
0x7f72  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x7f77  callvirt instance void [System.Web]System.Web.HttpResponse::Close()
0x7f7c  leave.s  loc_7F92
0x7f7e  ldloc.3
0x7f7f  brfalse.s loc_7F87
0x7f81  ldloc.3
0x7f82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f87  endfinally
0x7f88  ldloc.2
0x7f89  brfalse.s loc_7F91
0x7f8b  ldloc.2
0x7f8c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f91  endfinally
0x7f92  ret
```
