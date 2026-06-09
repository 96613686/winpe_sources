# Microsoft.ReportingServices.WebServer.ResponseHeaderData::ReturnResponseHeaders

- ea: `0x2bbe0`
- end: `0x2bc22`
- name: `Microsoft.ReportingServices.WebServer.ResponseHeaderData::ReturnResponseHeaders`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2be30`
- `0x2bf10`

## callees

- `0x2bbe0`
- `0x32630`

## string_xrefs

- `0x2bc06`: `Cannot write headers to the client. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2bbe0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2bbe5  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x2bbea  stloc.0
0x2bbeb  ldarg.0
0x2bbec  ldfld    class Microsoft.ReportingServices.WebServer.HttpClientRequest Microsoft.ReportingServices.WebServer.ResponseHeaderData::m_sessionManager
0x2bbf1  ldarg.0
0x2bbf2  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSStream Microsoft.ReportingServices.WebServer.ResponseHeaderData::m_resultStream
0x2bbf7  ldloc.0
0x2bbf8  call     void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::ReturnResponseHeaders(class Microsoft.ReportingServices.WebServer.HttpClientRequest sessionManager, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSStream result, class [System.Web]System.Web.HttpResponse resp)
0x2bbfd  leave.s  loc_2BC21
0x2bbff  stloc.1
0x2bc00  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferedResponseTracer()
0x2bc05  ldc.i4.2
0x2bc06  ldstr    aCannotWriteHea// "Cannot write headers to the client. {0}"
0x2bc0b  ldc.i4.1
0x2bc0c  newarr   [mscorlib]System.Object
0x2bc11  dup
0x2bc12  ldc.i4.0
0x2bc13  ldloc.1
0x2bc14  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2bc19  stelem.ref
0x2bc1a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2bc1f  leave.s  loc_2BC21
0x2bc21  ret
```
