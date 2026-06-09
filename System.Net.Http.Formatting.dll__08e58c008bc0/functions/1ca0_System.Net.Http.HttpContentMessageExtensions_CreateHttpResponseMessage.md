# System.Net.Http.HttpContentMessageExtensions::CreateHttpResponseMessage

- ea: `0x1ca0`
- end: `0x1ce5`
- name: `System.Net.Http.HttpContentMessageExtensions::CreateHttpResponseMessage`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0xc5a0`

## callees

- `0x1ba0`
- `0x2740`
- `0x2760`
- `0x2780`
- `0x27a0`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x1ca5  stloc.0
0x1ca6  ldloc.0
0x1ca7  ldarg.0
0x1ca8  callvirt instance class [mscorlib]System.Version System.Net.Http.HttpUnsortedResponse::get_Version()
0x1cad  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Version(class [mscorlib]System.Version)
0x1cb2  ldloc.0
0x1cb3  ldarg.0
0x1cb4  callvirt instance valuetype [System]System.Net.HttpStatusCode System.Net.Http.HttpUnsortedResponse::get_StatusCode()
0x1cb9  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x1cbe  ldloc.0
0x1cbf  ldarg.0
0x1cc0  callvirt instance string System.Net.Http.HttpUnsortedResponse::get_ReasonPhrase()
0x1cc5  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_ReasonPhrase(string)
0x1cca  ldloc.0
0x1ccb  ldarg.0
0x1ccc  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaders System.Net.Http.HttpUnsortedResponse::get_HttpHeaders()
0x1cd1  ldloc.0
0x1cd2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x1cd7  ldarg.1
0x1cd8  ldarg.2
0x1cd9  call     class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.HttpContentMessageExtensions::CreateHeaderFields(class [System.Net.Http]System.Net.Http.Headers.HttpHeaders source, class [System.Net.Http]System.Net.Http.Headers.HttpHeaders destination, class [mscorlib]System.IO.Stream contentStream, int32 rewind)
0x1cde  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x1ce3  ldloc.0
0x1ce4  ret
```
