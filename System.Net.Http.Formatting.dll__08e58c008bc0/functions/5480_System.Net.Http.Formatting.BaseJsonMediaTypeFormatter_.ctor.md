# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::.ctor

- ea: `0x5480`
- end: `0x54cf`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::.ctor`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x5900`
- `0x7740`

## callees

- `0x5570`
- `0x6950`
- `0x7d40`
- `0x7e90`

## pseudocode

```c

```

## disassembly

```asm
0x5480  ldarg.0
0x5481  ldc.i4   0x100
0x5486  stfld    int32 System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_maxDepth
0x548b  ldarg.0
0x548c  call     instance void System.Net.Http.Formatting.MediaTypeFormatter::.ctor()
0x5491  ldarg.0
0x5492  ldarg.0
0x5493  newobj   instance void System.Net.Http.Formatting.JsonContractResolver::.ctor(class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x5498  stfld    class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_defaultContractResolver
0x549d  ldarg.0
0x549e  ldarg.0
0x549f  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CreateDefaultSerializerSettings()
0x54a4  stfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::_jsonSerializerSettings
0x54a9  ldarg.0
0x54aa  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedEncodings()
0x54af  ldc.i4.0
0x54b0  ldc.i4.1
0x54b1  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool, bool)
0x54b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding>::Add(var<u1>)
0x54bb  ldarg.0
0x54bc  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedEncodings()
0x54c1  ldc.i4.0
0x54c2  ldc.i4.1
0x54c3  ldc.i4.1
0x54c4  newobj   instance void [mscorlib]System.Text.UnicodeEncoding::.ctor(bool, bool, bool)
0x54c9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding>::Add(var<u1>)
0x54ce  ret
```
