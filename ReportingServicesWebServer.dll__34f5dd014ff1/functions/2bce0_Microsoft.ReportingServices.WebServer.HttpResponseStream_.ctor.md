# Microsoft.ReportingServices.WebServer.HttpResponseStream::.ctor

- ea: `0x2bce0`
- end: `0x2bd37`
- name: `Microsoft.ReportingServices.WebServer.HttpResponseStream::.ctor`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bc60`

## callees

- `0x2bce0`

## string_xrefs

- `0x2bd2c`: `Created HttpResponseStream`

## pseudocode

```c

```

## disassembly

```asm
0x2bce0  ldarg.0
0x2bce1  ldc.i4.1
0x2bce2  stfld    bool Microsoft.ReportingServices.WebServer.HttpResponseStream::m_isFirstFlush
0x2bce7  ldarg.0
0x2bce8  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CanWriteFileStream::.ctor()
0x2bced  ldarg.0
0x2bcee  ldarg.1
0x2bcef  stfld    int32 Microsoft.ReportingServices.WebServer.HttpResponseStream::m_sizeToFlush
0x2bcf4  ldarg.0
0x2bcf5  ldarg.2
0x2bcf6  stfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.WebServer.HttpResponseStream::m_httpResponse
0x2bcfb  ldarg.0
0x2bcfc  ldarg.2
0x2bcfd  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_OutputStream()
0x2bd02  stfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.WebServer.HttpResponseStream::m_httpResponseStream
0x2bd07  ldarg.0
0x2bd08  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.WebServer.HttpResponseStream::m_httpResponse
0x2bd0d  ldc.i4.1
0x2bd0e  callvirt instance void [System.Web]System.Web.HttpResponse::set_BufferOutput(bool)
0x2bd13  ldarg.0
0x2bd14  ldarg.3
0x2bd15  stfld    class Microsoft.ReportingServices.WebServer.ResponseHeaderData Microsoft.ReportingServices.WebServer.HttpResponseStream::m_respHeaderData
0x2bd1a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferedResponseTracer()
0x2bd1f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x2bd24  brfalse.s loc_2BD36
0x2bd26  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferedResponseTracer()
0x2bd2b  ldc.i4.4
0x2bd2c  ldstr    aCreatedHttpres// "Created HttpResponseStream"
0x2bd31  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2bd36  ret
```
