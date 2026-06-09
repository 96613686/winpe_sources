# System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddRequestHeaderMapping_0

- ea: `0x8770`
- end: `0x8798`
- name: `System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddRequestHeaderMapping_0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x7ec0`
- `0x8770`
- `0x8c40`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x8770  ldarg.0
0x8771  brtrue.s loc_877E
0x8773  ldstr    aFormatter// "formatter"
0x8778  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x877d  throw
0x877e  ldarg.1
0x877f  ldarg.2
0x8780  ldarg.3
0x8781  ldarg.s  4
0x8783  ldarg.s  5
0x8785  newobj   instance void System.Net.Http.Formatting.RequestHeaderMapping::.ctor(string headerName, string headerValue, valuetype [mscorlib]System.StringComparison valueComparison, bool isValueSubstring, string mediaType)
0x878a  stloc.0
0x878b  ldarg.0
0x878c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping> System.Net.Http.Formatting.MediaTypeFormatter::get_MediaTypeMappings()
0x8791  ldloc.0
0x8792  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping>::Add(var<u1>)
0x8797  ret
```
