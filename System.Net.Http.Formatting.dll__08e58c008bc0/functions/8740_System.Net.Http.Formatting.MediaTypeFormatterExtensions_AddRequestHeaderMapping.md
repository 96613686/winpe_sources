# System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddRequestHeaderMapping

- ea: `0x8740`
- end: `0x8768`
- name: `System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddRequestHeaderMapping`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x7ec0`
- `0x8740`
- `0x8c60`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x8740  ldarg.0
0x8741  brtrue.s loc_874E
0x8743  ldstr    aFormatter// "formatter"
0x8748  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x874d  throw
0x874e  ldarg.1
0x874f  ldarg.2
0x8750  ldarg.3
0x8751  ldarg.s  4
0x8753  ldarg.s  5
0x8755  newobj   instance void System.Net.Http.Formatting.RequestHeaderMapping::.ctor(string headerName, string headerValue, valuetype [mscorlib]System.StringComparison valueComparison, bool isValueSubstring, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType)
0x875a  stloc.0
0x875b  ldarg.0
0x875c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping> System.Net.Http.Formatting.MediaTypeFormatter::get_MediaTypeMappings()
0x8761  ldloc.0
0x8762  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping>::Add(var<u1>)
0x8767  ret
```
