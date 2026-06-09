# System.Xaml.XmlCompatibilityReader::Error

- ea: `0x117a0`
- end: `0x117d7`
- name: `System.Xaml.XmlCompatibilityReader::Error`
- size: `55`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10900`
- `0x10a40`
- `0x10ed0`
- `0x110b0`
- `0x111f0`
- `0x11280`
- `0x11450`
- `0x11620`
- `0x2efd0`
- `0x2f170`
- `0x2f2a0`
- `0x2f3b0`
- `0x2f5f0`

## callees

- `0x117a0`
- `0x11d80`

## pseudocode

```c

```

## disassembly

```asm
0x117a0  ldarg.0
0x117a1  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x117a6  isinst   [System.Xml]System.Xml.IXmlLineInfo
0x117ab  stloc.0
0x117ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x117b1  ldarg.1
0x117b2  ldarg.2
0x117b3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x117b8  ldnull
0x117b9  ldloc.0
0x117ba  brfalse.s loc_117C4
0x117bc  ldloc.0
0x117bd  callvirt instance int32 [System.Xml]System.Xml.IXmlLineInfo::get_LineNumber()
0x117c2  br.s     loc_117C5
0x117c4  ldc.i4.1
0x117c5  ldloc.0
0x117c6  brfalse.s loc_117D0
0x117c8  ldloc.0
0x117c9  callvirt instance int32 [System.Xml]System.Xml.IXmlLineInfo::get_LinePosition()
0x117ce  br.s     loc_117D1
0x117d0  ldc.i4.1
0x117d1  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string, class [mscorlib]System.Exception, int32, int32)
0x117d6  throw
```
