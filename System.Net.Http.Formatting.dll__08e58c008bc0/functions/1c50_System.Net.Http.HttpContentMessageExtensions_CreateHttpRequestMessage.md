# System.Net.Http.HttpContentMessageExtensions::CreateHttpRequestMessage

- ea: `0x1c50`
- end: `0x1c96`
- name: `System.Net.Http.HttpContentMessageExtensions::CreateHttpRequestMessage`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0xc370`

## callees

- `0x1b00`
- `0x1ba0`
- `0x2690`
- `0x26d0`
- `0x26f0`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  newobj   instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::.ctor()
0x1c55  stloc.0
0x1c56  ldloc.0
0x1c57  ldarg.1
0x1c58  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod System.Net.Http.HttpUnsortedRequest::get_Method()
0x1c5d  callvirt instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::set_Method(class [System.Net.Http]System.Net.Http.HttpMethod)
0x1c62  ldloc.0
0x1c63  ldarg.0
0x1c64  ldarg.1
0x1c65  call     class [System]System.Uri System.Net.Http.HttpContentMessageExtensions::CreateRequestUri(string uriScheme, class System.Net.Http.HttpUnsortedRequest httpRequest)
0x1c6a  callvirt instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::set_RequestUri(class [System]System.Uri)
0x1c6f  ldloc.0
0x1c70  ldarg.1
0x1c71  callvirt instance class [mscorlib]System.Version System.Net.Http.HttpUnsortedRequest::get_Version()
0x1c76  callvirt instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::set_Version(class [mscorlib]System.Version)
0x1c7b  ldloc.0
0x1c7c  ldarg.1
0x1c7d  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaders System.Net.Http.HttpUnsortedRequest::get_HttpHeaders()
0x1c82  ldloc.0
0x1c83  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x1c88  ldarg.2
0x1c89  ldarg.3
0x1c8a  call     class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.HttpContentMessageExtensions::CreateHeaderFields(class [System.Net.Http]System.Net.Http.Headers.HttpHeaders source, class [System.Net.Http]System.Net.Http.Headers.HttpHeaders destination, class [mscorlib]System.IO.Stream contentStream, int32 rewind)
0x1c8f  callvirt instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x1c94  ldloc.0
0x1c95  ret
```
