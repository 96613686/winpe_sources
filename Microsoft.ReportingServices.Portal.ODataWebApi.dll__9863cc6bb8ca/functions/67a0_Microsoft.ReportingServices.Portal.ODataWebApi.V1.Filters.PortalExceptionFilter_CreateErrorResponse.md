# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::CreateErrorResponse

- ea: `0x67a0`
- end: `0x6804`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::CreateErrorResponse`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1810`
- `0x6490`

## callees

- `0x67a0`
- `0x6970`

## pseudocode

```c

```

## disassembly

```asm
0x67a0  ldarg.0
0x67a1  brtrue.s loc_67C0
0x67a3  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::.ctor()
0x67a8  dup
0x67a9  ldc.i4.0
0x67aa  box      [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode
0x67af  ldstr    aD// "D"
0x67b4  call     instance string [mscorlib]System.Enum::ToString(string)
0x67b9  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataError::set_ErrorCode(string)
0x67be  starg.s  0
0x67c0  ldarg.1
0x67c1  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::get_Exception()
0x67c6  ldarga.s 2
0x67c8  ldarga.s 0
0x67ca  call     void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::OverrideErrorDetails(class [mscorlib]System.Exception e, valuetype [System]System.Net.HttpStatusCode& statusCode, class [Microsoft.OData.Core]Microsoft.OData.ODataError& odataError)
0x67cf  ldarg.3
0x67d0  brfalse.s loc_67F6
0x67d2  ldarg.2
0x67d3  ldc.i4   0x1F4
0x67d8  bge.s    loc_67DD
0x67da  ldc.i4.4
0x67db  br.s     loc_67DE
0x67dd  ldc.i4.1
0x67de  stloc.0
0x67df  ldarg.3
0x67e0  ldloc.0
0x67e1  ldstr    aOdataException// "OData exception occurred: {0}."
0x67e6  ldarg.1
0x67e7  callvirt instance class [mscorlib]System.Exception [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::get_Exception()
0x67ec  call     string [mscorlib]System.String::Format(string, object)
0x67f1  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x67f6  ldarg.1
0x67f7  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Filters.HttpActionExecutedContext::get_Request()
0x67fc  ldarg.2
0x67fd  ldarg.0
0x67fe  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpRequestMessageExtensions::CreateErrorResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode, class [Microsoft.OData.Core]Microsoft.OData.ODataError)
0x6803  ret
```
