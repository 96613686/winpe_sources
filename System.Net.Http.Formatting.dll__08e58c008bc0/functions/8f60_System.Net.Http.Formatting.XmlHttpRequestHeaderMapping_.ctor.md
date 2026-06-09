# System.Net.Http.Formatting.XmlHttpRequestHeaderMapping::.ctor

- ea: `0x8f60`
- end: `0x8f78`
- name: `System.Net.Http.Formatting.XmlHttpRequestHeaderMapping::.ctor`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x7740`

## callees

- `0x7c60`
- `0x8c60`

## string_xrefs

- `0x8f66`: `XMLHttpRequest`

## pseudocode

```c

```

## disassembly

```asm
0x8f60  ldarg.0
0x8f61  ldstr    aXRequestedWith// "x-requested-with"
0x8f66  ldstr    aXmlhttprequest// "XMLHttpRequest"
0x8f6b  ldc.i4.5
0x8f6c  ldc.i4.1
0x8f6d  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::get_ApplicationJsonMediaType()
0x8f72  call     instance void System.Net.Http.Formatting.RequestHeaderMapping::.ctor(string headerName, string headerValue, valuetype [mscorlib]System.StringComparison valueComparison, bool isValueSubstring, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType)
0x8f77  ret
```
