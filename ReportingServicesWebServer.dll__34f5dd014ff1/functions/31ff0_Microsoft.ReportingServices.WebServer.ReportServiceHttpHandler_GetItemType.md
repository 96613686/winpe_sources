# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::GetItemType

- ea: `0x31ff0`
- end: `0x32033`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::GetItemType`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x31ff0`

## string_xrefs

- `0x31ff0`: `ReportServiceHttpHandler.GetItemType`

## pseudocode

```c

```

## disassembly

```asm
0x31ff0  ldstr    aReportserviceh_0// "ReportServiceHttpHandler.GetItemType"
0x31ff5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x31ffa  stloc.0
0x31ffb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x32000  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x32005  ldstr    aCatalogitemtyp// "CatalogItemType"
0x3200a  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3200f  stloc.2
0x32010  ldloc.2
0x32011  brfalse.s loc_3201C
0x32013  ldloc.2
0x32014  unbox.any [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType
0x32019  stloc.1
0x3201a  br.s     loc_32023
0x3201c  ldarg.0
0x3201d  call     instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::GetItemType()
0x32022  stloc.1
0x32023  ldloc.1
0x32024  stloc.3
0x32025  leave.s  loc_32031
0x32027  ldloc.0
0x32028  brfalse.s loc_32030
0x3202a  ldloc.0
0x3202b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32030  endfinally
0x32031  ldloc.3
0x32032  ret
```
