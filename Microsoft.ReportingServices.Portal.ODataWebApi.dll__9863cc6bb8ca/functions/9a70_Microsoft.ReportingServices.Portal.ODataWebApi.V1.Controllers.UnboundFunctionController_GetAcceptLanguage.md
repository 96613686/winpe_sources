# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetAcceptLanguage

- ea: `0x9a70`
- end: `0x9a95`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetAcceptLanguage`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6130`
- `0x97a0`

## callees

- `0x9a70`

## pseudocode

```c

```

## disassembly

```asm
0x9a70  ldarg.0
0x9a71  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x9a76  brfalse.s loc_9A93
0x9a78  ldarg.0
0x9a79  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x9a7e  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x9a83  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_AcceptLanguage()
0x9a88  stloc.0
0x9a89  ldloc.0
0x9a8a  brfalse.s loc_9A93
0x9a8c  ldloc.0
0x9a8d  callvirt instance string [mscorlib]System.Object::ToString()
0x9a92  ret
0x9a93  ldnull
0x9a94  ret
```
