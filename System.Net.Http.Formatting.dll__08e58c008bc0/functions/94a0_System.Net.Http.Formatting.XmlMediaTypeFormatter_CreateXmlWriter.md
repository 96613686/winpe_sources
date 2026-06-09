# System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlWriter

- ea: `0x94a0`
- end: `0x94ce`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlWriter`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x9400`
- `0x9500`

## callees

- `0x8020`
- `0x9130`
- `0x94a0`

## pseudocode

```c

```

## disassembly

```asm
0x94a0  ldarg.0
0x94a1  ldarg.2
0x94a2  brtrue.s loc_94A7
0x94a4  ldnull
0x94a5  br.s     loc_94AD
0x94a7  ldarg.2
0x94a8  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x94ad  call     instance class [mscorlib]System.Text.Encoding System.Net.Http.Formatting.MediaTypeFormatter::SelectCharacterEncoding(class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders contentHeaders)
0x94b2  stloc.0
0x94b3  ldarg.0
0x94b4  call     instance class [System.Xml]System.Xml.XmlWriterSettings System.Net.Http.Formatting.XmlMediaTypeFormatter::get_WriterSettings()
0x94b9  callvirt instance class [System.Xml]System.Xml.XmlWriterSettings [System.Xml]System.Xml.XmlWriterSettings::Clone()
0x94be  stloc.1
0x94bf  ldloc.1
0x94c0  ldloc.0
0x94c1  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Encoding(class [mscorlib]System.Text.Encoding)
0x94c6  ldarg.1
0x94c7  ldloc.1
0x94c8  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlWriterSettings)
0x94cd  ret
```
