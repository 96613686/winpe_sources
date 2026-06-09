# System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddQueryStringMapping

- ea: `0x86e0`
- end: `0x8704`
- name: `System.Net.Http.Formatting.MediaTypeFormatterExtensions::AddQueryStringMapping`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x7ec0`
- `0x86e0`
- `0x8ac0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x86e0  ldarg.0
0x86e1  brtrue.s loc_86EE
0x86e3  ldstr    aFormatter// "formatter"
0x86e8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x86ed  throw
0x86ee  ldarg.1
0x86ef  ldarg.2
0x86f0  ldarg.3
0x86f1  newobj   instance void System.Net.Http.Formatting.QueryStringMapping::.ctor(string queryStringParameterName, string queryStringParameterValue, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaType)
0x86f6  stloc.0
0x86f7  ldarg.0
0x86f8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping> System.Net.Http.Formatting.MediaTypeFormatter::get_MediaTypeMappings()
0x86fd  ldloc.0
0x86fe  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping>::Add(var<u1>)
0x8703  ret
```
