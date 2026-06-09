# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CreateByteArrayHttpOkResponseMessage

- ea: `0x99b0`
- end: `0x9a0f`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CreateByteArrayHttpOkResponseMessage`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x98d0`

## callees

- `0x99b0`

## pseudocode

```c

```

## disassembly

```asm
0x99b0  ldarg.1
0x99b1  dup
0x99b2  brtrue.s loc_99BB
0x99b4  pop
0x99b5  ldc.i4.0
0x99b6  newarr   [mscorlib]System.Byte
0x99bb  newobj   instance void [System.Net.Http]System.Net.Http.ByteArrayContent::.ctor(unsigned int8[])
0x99c0  stloc.0
0x99c1  ldloc.0
0x99c2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x99c7  ldstr    aInline// "inline"
0x99cc  newobj   instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::.ctor(string)
0x99d1  dup
0x99d2  ldarg.3
0x99d3  callvirt instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::set_FileName(string)
0x99d8  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentDisposition(class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue)
0x99dd  ldloc.0
0x99de  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x99e3  ldarg.2
0x99e4  dup
0x99e5  brtrue.s loc_99F2
0x99e7  pop
0x99e8  ldstr    aApplicationOct// "application/octet-stream"
0x99ed  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x99f2  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x99f7  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x99fc  dup
0x99fd  ldc.i4   0xC8
0x9a02  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x9a07  dup
0x9a08  ldloc.0
0x9a09  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x9a0e  ret
```
