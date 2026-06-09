# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderResource

- ea: `0x32290`
- end: `0x32305`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderResource`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x31ed0`
- `0x32290`
- `0x38aa0`

## string_xrefs

- `0x32290`: `ReportServiceHttpHandler.RenderResource`

## pseudocode

```c

```

## disassembly

```asm
0x32290  ldstr    aReportserviceh_5// "ReportServiceHttpHandler.RenderResource"
0x32295  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3229a  stloc.0
0x3229b  ldarg.0
0x3229c  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::RenderResource()
0x322a1  ldarg.0
0x322a2  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x322a7  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x322ac  callvirt instance string [System.Web]System.Web.HttpResponse::get_ContentType()
0x322b1  ldstr    aApplicationOct// "application/octet-stream"
0x322b6  ldc.i4.5
0x322b7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x322bc  brtrue.s loc_322DC
0x322be  ldarg.0
0x322bf  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x322c4  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0x322c9  ldarg.0
0x322ca  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x322cf  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x322d4  ldc.i4.1
0x322d5  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::AddContentDisposition(string fileName, class [System.Web]System.Web.HttpResponse response, valuetype Microsoft.ReportingServices.Common.ContentDisposition contentDisposition)
0x322da  leave.s  loc_32304
0x322dc  ldarg.0
0x322dd  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x322e2  callvirt instance string class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0x322e7  ldarg.0
0x322e8  call     instance class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::get_Context()
0x322ed  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x322f2  ldc.i4.0
0x322f3  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::AddContentDisposition(string fileName, class [System.Web]System.Web.HttpResponse response, valuetype Microsoft.ReportingServices.Common.ContentDisposition contentDisposition)
0x322f8  leave.s  loc_32304
0x322fa  ldloc.0
0x322fb  brfalse.s loc_32303
0x322fd  ldloc.0
0x322fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32303  endfinally
0x32304  ret
```
