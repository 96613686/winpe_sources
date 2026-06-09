# System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlReader

- ea: `0x9380`
- end: `0x93a7`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlReader`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x92c0`
- `0x94f0`

## callees

- `0x5220`
- `0x8020`
- `0x9380`

## pseudocode

```c

```

## disassembly

```asm
0x9380  ldarg.0
0x9381  ldarg.2
0x9382  brfalse.s loc_938C
0x9384  ldarg.2
0x9385  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x938a  br.s     loc_938D
0x938c  ldnull
0x938d  call     instance class [mscorlib]System.Text.Encoding System.Net.Http.Formatting.MediaTypeFormatter::SelectCharacterEncoding(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders contentHeaders)
0x9392  stloc.0
0x9393  ldarg.1
0x9394  newobj   instance void System.Net.Http.Internal.NonClosingDelegatingStream::.ctor(class [mscorlib]System.IO.Stream innerStream)
0x9399  ldloc.0
0x939a  ldarg.0
0x939b  ldfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.XmlMediaTypeFormatter::_readerQuotas
0x93a0  ldnull
0x93a1  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::CreateTextReader(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding, class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas, class [System.Runtime.Serialization]System.Xml.OnXmlDictionaryReaderClose)
0x93a6  ret
```
