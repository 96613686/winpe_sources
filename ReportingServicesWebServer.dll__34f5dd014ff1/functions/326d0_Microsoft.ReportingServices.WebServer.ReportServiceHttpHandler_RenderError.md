# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderError

- ea: `0x326d0`
- end: `0x32722`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderError`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x32080`

## callees

- `0x326d0`
- `0x32730`
- `0x39120`

## string_xrefs

- `0x326e6`: `rs:Command`
- `0x326d0`: `ReportServiceHttpHandler.RenderError`
- `0x326fb`: `rs:ErrorResponseAsXml`

## pseudocode

```c

```

## disassembly

```asm
0x326d0  ldstr    aReportserviceh_10// "ReportServiceHttpHandler.RenderError"
0x326d5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x326da  stloc.0
0x326db  ldarg.0
0x326dc  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IStreamRequest [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Request()
0x326e1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IStreamRequest::get_RequestParameters()
0x326e6  ldstr    aRsCommand// "rs:Command"
0x326eb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x326f0  ldarg.0
0x326f1  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IStreamRequest [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Request()
0x326f6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IStreamRequest::get_RequestParameters()
0x326fb  ldstr    aRsErrorrespons// "rs:ErrorResponseAsXml"
0x32700  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x32705  call     bool Microsoft.ReportingServices.Common.ErrorResponseWriter::ShouldWriteErrorAsXml(string commandValue, string writeErrorAsXmlValue)
0x3270a  stloc.1
0x3270b  ldarg.1
0x3270c  ldarg.2
0x3270d  ldarg.3
0x3270e  ldloc.1
0x3270f  ldnull
0x32710  call     void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::WriteErrorResponse(int32 code, string shortHttpDescription, class [mscorlib]System.Exception exception, bool errorResponseAsXml, [opt] class [System]System.Collections.Specialized.NameValueCollection additionalHeaders)
0x32715  leave.s  loc_32721
0x32717  ldloc.0
0x32718  brfalse.s loc_32720
0x3271a  ldloc.0
0x3271b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32720  endfinally
0x32721  ret
```
