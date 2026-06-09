# System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddQueryStringMapping_0

- ea: `0x8710`
- end: `0x8734`
- name: `System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddQueryStringMapping_0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x7ec0`
- `0x8710`
- `0x8ab0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x8710  ldarg.0
0x8711  brtrue.s loc_871E
0x8713  ldstr    aFormatter// "formatter"
0x8718  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x871d  throw
0x871e  ldarg.1
0x871f  ldarg.2
0x8720  ldarg.3
0x8721  newobj   instance void System.Net.Http.Formatting.QueryStringMapping::.ctor(string queryStringParameterName, string queryStringParameterValue, string mediaType)
0x8726  stloc.0
0x8727  ldarg.0
0x8728  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping> System.Net.Http.Formatting.MediaTypeFormatter::get_MediaTypeMappings()
0x872d  ldloc.0
0x872e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping>::Add(var<u1>)
0x8733  ret
```
