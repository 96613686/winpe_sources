# System.Net.Http.Formatting.JsonMediaTypeFormatter::.ctor

- ea: `0x7740`
- end: `0x7799`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::.ctor`
- size: `89`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0xf10`
- `0xf30`
- `0x10b0`
- `0x10d0`
- `0x8640`

## callees

- `0x1310`
- `0x5480`
- `0x7c60`
- `0x7c80`
- `0x7e60`
- `0x7ec0`
- `0x8f60`

## pseudocode

```c

```

## disassembly

```asm
0x7740  ldarg.0
0x7741  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::.ctor()
0x7746  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer> System.Net.Http.Formatting.JsonMediaTypeFormatter::_dataContractSerializerCache
0x774b  ldarg.0
0x774c  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.FormattingUtilities::CreateDefaultReaderQuotas()
0x7751  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.JsonMediaTypeFormatter::_readerQuotas
0x7756  ldarg.0
0x7757  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::.ctor()
0x775c  ldarg.0
0x775d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x7762  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::get_ApplicationJsonMediaType()
0x7767  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::Add(var<u1>)
0x776c  ldarg.0
0x776d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x7772  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::get_TextJsonMediaType()
0x7777  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::Add(var<u1>)
0x777c  ldarg.0
0x777d  newobj   instance void System.Net.Http.Formatting.XmlHttpRequestHeaderMapping::.ctor()
0x7782  stfld    class System.Net.Http.Formatting.RequestHeaderMapping System.Net.Http.Formatting.JsonMediaTypeFormatter::_requestHeaderMapping
0x7787  ldarg.0
0x7788  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping> System.Net.Http.Formatting.MediaTypeFormatter::get_MediaTypeMappings()
0x778d  ldarg.0
0x778e  ldfld    class System.Net.Http.Formatting.RequestHeaderMapping System.Net.Http.Formatting.JsonMediaTypeFormatter::_requestHeaderMapping
0x7793  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.Formatting.MediaTypeMapping>::Add(var<u1>)
0x7798  ret
```
