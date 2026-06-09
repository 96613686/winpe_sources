# System.Net.Http.Formatting.XmlMediaTypeFormatter::.ctor

- ea: `0x9000`
- end: `0x9082`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::.ctor`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0xf50`
- `0xf70`
- `0x10f0`
- `0x1110`
- `0x8640`

## callees

- `0x1310`
- `0x7c50`
- `0x7c70`
- `0x7d40`
- `0x7e60`
- `0x7e90`
- `0x9140`

## pseudocode

```c

```

## disassembly

```asm
0x9000  ldarg.0
0x9001  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object>::.ctor()
0x9006  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object> System.Net.Http.Formatting.XmlMediaTypeFormatter::_serializerCache
0x900b  ldarg.0
0x900c  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.FormattingUtilities::CreateDefaultReaderQuotas()
0x9011  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas System.Net.Http.Formatting.XmlMediaTypeFormatter::_readerQuotas
0x9016  ldarg.0
0x9017  call     instance void System.Net.Http.Formatting.MediaTypeFormatter::.ctor()
0x901c  ldarg.0
0x901d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x9022  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::get_ApplicationXmlMediaType()
0x9027  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::Add(var<u1>)
0x902c  ldarg.0
0x902d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedMediaTypes()
0x9032  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::get_TextXmlMediaType()
0x9037  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue>::Add(var<u1>)
0x903c  ldarg.0
0x903d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedEncodings()
0x9042  ldc.i4.0
0x9043  ldc.i4.1
0x9044  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool, bool)
0x9049  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding>::Add(var<u1>)
0x904e  ldarg.0
0x904f  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding> System.Net.Http.Formatting.MediaTypeFormatter::get_SupportedEncodings()
0x9054  ldc.i4.0
0x9055  ldc.i4.1
0x9056  ldc.i4.1
0x9057  newobj   instance void [mscorlib]System.Text.UnicodeEncoding::.ctor(bool, bool, bool)
0x905c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Text.Encoding>::Add(var<u1>)
0x9061  ldarg.0
0x9062  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x9067  dup
0x9068  ldc.i4.1
0x9069  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x906e  dup
0x906f  ldc.i4.0
0x9070  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_CloseOutput(bool)
0x9075  dup
0x9076  ldc.i4.0
0x9077  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_CheckCharacters(bool)
0x907c  call     instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::set_WriterSettings(class [System.Xml]System.Xml.XmlWriterSettings value)
0x9081  ret
```
