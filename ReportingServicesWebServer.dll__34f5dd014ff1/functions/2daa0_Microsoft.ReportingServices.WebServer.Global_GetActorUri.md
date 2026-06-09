# Microsoft.ReportingServices.WebServer.Global::GetActorUri

- ea: `0x2daa0`
- end: `0x2db0e`
- name: `Microsoft.ReportingServices.WebServer.Global::GetActorUri`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2bfd0`
- `0x2c040`
- `0x2daa0`

## string_xrefs

- `0x2dac8`: `Trying to generate ActorUri when HttpContext.Current == null.`

## pseudocode

```c

```

## disassembly

```asm
0x2daa0  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x2daa5  isinst   Microsoft.ReportingServices.WebServer.HttpRequestContext
0x2daaa  stloc.0
0x2daab  ldloc.0
0x2daac  brtrue.s loc_2DAD4
0x2daae  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2dab3  brfalse.s loc_2DAC2
0x2dab5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2daba  newobj   instance void Microsoft.ReportingServices.WebServer.HttpRequestContext::.ctor(class [System.Web]System.Web.HttpContext context)
0x2dabf  stloc.0
0x2dac0  br.s     loc_2DAD4
0x2dac2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x2dac7  ldc.i4.4
0x2dac8  ldstr    aTryingToGenera// "Trying to generate ActorUri when HttpCo"...
0x2dacd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2dad2  ldnull
0x2dad3  ret
0x2dad4  ldloc.0
0x2dad5  brfalse.s loc_2DB0C
0x2dad7  ldloc.0
0x2dad8  callvirt instance class [System]System.Uri Microsoft.ReportingServices.WebServer.HttpRequestContext::get_HostUri()
0x2dadd  callvirt instance string [mscorlib]System.Object::ToString()
0x2dae2  ldc.i4.1
0x2dae3  newarr   [mscorlib]System.Char
0x2dae8  dup
0x2dae9  ldc.i4.0
0x2daea  ldc.i4.s 0x2F
0x2daec  stelem.i2
0x2daed  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2daf2  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2daf7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2dafc  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2db01  callvirt instance string [System]System.Uri::get_PathAndQuery()
0x2db06  call     string [mscorlib]System.String::Concat(string, string)
0x2db0b  ret
0x2db0c  ldnull
0x2db0d  ret
```
