# System.Net.Http.Formatting.XmlMediaTypeFormatter::.ctor_0

- ea: `0x9090`
- end: `0x90d2`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::.ctor_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1310`
- `0x7da0`
- `0x90f0`
- `0x9100`
- `0x9130`
- `0x9140`
- `0x9150`
- `0x9160`

## pseudocode

```c

```

## disassembly

```asm
0x9090  ldarg.0
0x9091  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object>::.ctor()
0x9096  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object> System.Net.Http.Formatting.XmlMediaTypeFormatter::_serializerCache
0x909b  ldarg.0
0x909c  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.FormattingUtilities::CreateDefaultReaderQuotas()
0x90a1  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.XmlMediaTypeFormatter::_readerQuotas
0x90a6  ldarg.0
0x90a7  ldarg.1
0x90a8  call     instance void System.Net.Http.Formatting.MediaTypeFormatter::.ctor(class System.Net.Http.Formatting.MediaTypeFormatter formatter)
0x90ad  ldarg.0
0x90ae  ldarg.1
0x90af  callvirt instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x90b4  call     instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::set_UseXmlSerializer(bool value)
0x90b9  ldarg.0
0x90ba  ldarg.1
0x90bb  callvirt instance class [System.Xml]System.Xml.XmlWriterSettings System.Net.Http.Formatting.XmlMediaTypeFormatter::get_WriterSettings()
0x90c0  call     instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::set_WriterSettings(class [System.Xml]System.Xml.XmlWriterSettings value)
0x90c5  ldarg.0
0x90c6  ldarg.1
0x90c7  callvirt instance int32 System.Net.Http.Formatting.XmlMediaTypeFormatter::get_MaxDepth()
0x90cc  call     instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::set_MaxDepth(int32 value)
0x90d1  ret
```
