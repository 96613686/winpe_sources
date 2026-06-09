# Microsoft.ReportingServices.WebServer.HttpResponseStream::WriteFile

- ea: `0x2be30`
- end: `0x2beac`
- name: `Microsoft.ReportingServices.WebServer.HttpResponseStream::WriteFile`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x2bbe0`
- `0x2be30`
- `0x3c590`

## string_xrefs

- `0x2be90`: `Cannot write response file to the client. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2be30  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x2be35  stloc.0
0x2be36  ldloc.0
0x2be37  ldarg.0
0x2be38  stfld    class Microsoft.ReportingServices.WebServer.HttpResponseStream <>c__DisplayClass18_0::<>4__this
0x2be3d  ldloc.0
0x2be3e  ldarg.1
0x2be3f  stfld    string <>c__DisplayClass18_0::name
0x2be44  ldarg.0
0x2be45  ldfld    class Microsoft.ReportingServices.WebServer.ResponseHeaderData Microsoft.ReportingServices.WebServer.HttpResponseStream::m_respHeaderData
0x2be4a  callvirt instance void Microsoft.ReportingServices.WebServer.ResponseHeaderData::ReturnResponseHeaders()
0x2be4f  leave.s  loc_2BE6C
0x2be51  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2be56  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x2be5b  ldstr    aHeadersset// "HeadersSet"
0x2be60  ldc.i4.1
0x2be61  box      [mscorlib]System.Boolean
0x2be66  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x2be6b  endfinally
0x2be6c  ldloc.0
0x2be6d  ldftn    instance void <>c__DisplayClass18_0::<WriteFile>b__0()
0x2be73  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object, native int)
0x2be78  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::RunFromRestrictedCasContext(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody)
0x2be7d  leave.s  loc_2BE87
0x2be7f  ldarg.0
0x2be80  ldc.i4.0
0x2be81  stfld    bool Microsoft.ReportingServices.WebServer.HttpResponseStream::m_isFirstFlush
0x2be86  endfinally
0x2be87  leave.s  loc_2BEAB
0x2be89  stloc.1
0x2be8a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferedResponseTracer()
0x2be8f  ldc.i4.2
0x2be90  ldstr    aCannotWriteRes// "Cannot write response file to the clien"...
0x2be95  ldc.i4.1
0x2be96  newarr   [mscorlib]System.Object
0x2be9b  dup
0x2be9c  ldc.i4.0
0x2be9d  ldloc.1
0x2be9e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2bea3  stelem.ref
0x2bea4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x2bea9  leave.s  loc_2BEAB
0x2beab  ret
```
