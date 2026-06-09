# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderExcelWorkbook

- ea: `0x32310`
- end: `0x3234a`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderExcelWorkbook`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x31ed0`
- `0x32310`
- `0x38aa0`

## string_xrefs

- `0x32310`: `ReportServiceHttpHandler.RenderExcelWorkbook`

## pseudocode

```c

```

## disassembly

```asm
0x32310  ldstr    aReportserviceh_6// "ReportServiceHttpHandler.RenderExcelWor"...
0x32315  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3231a  stloc.0
0x3231b  ldarg.0
0x3231c  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::RenderExcelWorkbook()
0x32321  ldarg.0
0x32322  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x32327  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0x3232c  ldarg.0
0x3232d  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x32332  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x32337  ldc.i4.1
0x32338  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::AddContentDisposition(string fileName, class [System.Web]System.Web.HttpResponse response, valuetype Microsoft.ReportingServices.Common.ContentDisposition contentDisposition)
0x3233d  leave.s  loc_32349
0x3233f  ldloc.0
0x32340  brfalse.s loc_32348
0x32342  ldloc.0
0x32343  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32348  endfinally
0x32349  ret
```
