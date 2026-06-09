# System.Net.Http.Formatting.JsonMediaTypeFormatter::.ctor_0

- ea: `0x77a0`
- end: `0x77d6`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::.ctor_0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1310`
- `0x54d0`
- `0x77f0`
- `0x7800`
- `0x7810`
- `0x7820`

## pseudocode

```c

```

## disassembly

```asm
0x77a0  ldarg.0
0x77a1  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer>::.ctor()
0x77a6  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer> System.Net.Http.Formatting.JsonMediaTypeFormatter::_dataContractSerializerCache
0x77ab  ldarg.0
0x77ac  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.FormattingUtilities::CreateDefaultReaderQuotas()
0x77b1  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.JsonMediaTypeFormatter::_readerQuotas
0x77b6  ldarg.0
0x77b7  ldarg.1
0x77b8  call     instance void System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::.ctor(class System.Net.Http.Formatting.BaseJsonMediaTypeFormatter formatter)
0x77bd  ldarg.0
0x77be  ldarg.1
0x77bf  callvirt instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_UseDataContractJsonSerializer()
0x77c4  call     instance void System.Net.Http.Formatting.JsonMediaTypeFormatter::set_UseDataContractJsonSerializer(bool value)
0x77c9  ldarg.0
0x77ca  ldarg.1
0x77cb  callvirt instance bool System.Net.Http.Formatting.JsonMediaTypeFormatter::get_Indent()
0x77d0  call     instance void System.Net.Http.Formatting.JsonMediaTypeFormatter::set_Indent(bool value)
0x77d5  ret
```
