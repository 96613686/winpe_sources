# System.Xml.Xsl.XslLoadException::AppendLineInfoMessage

- ea: `0x3b40`
- end: `0x3bee`
- name: `System.Xml.Xsl.XslLoadException::AppendLineInfoMessage`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x3bf0`
- `0x3c00`

## callees

- `0x290`
- `0x2b0`
- `0x3b0`
- `0x3c0`
- `0x510`
- `0x3790`
- `0x3b40`

## string_xrefs

- `0x3b52`: `Xml_ErrorFilePosition`

## pseudocode

```c

```

## disassembly

```asm
0x3b40  ldarg.1
0x3b41  brfalse  loc_3BEC
0x3b46  ldarg.1
0x3b47  callvirt instance string System.Xml.Xsl.ISourceLineInfo::get_Uri()
0x3b4c  call     string System.Xml.Xsl.SourceLineInfo::GetFileName(string uriString)
0x3b51  stloc.0
0x3b52  ldstr    aXmlErrorfilepo// "Xml_ErrorFilePosition"
0x3b57  ldc.i4.3
0x3b58  newarr   [mscorlib]System.String
0x3b5d  dup
0x3b5e  ldc.i4.0
0x3b5f  ldloc.0
0x3b60  stelem.ref
0x3b61  dup
0x3b62  ldc.i4.1
0x3b63  ldarg.1
0x3b64  callvirt instance valuetype System.Xml.Xsl.Location System.Xml.Xsl.ISourceLineInfo::get_Start()
0x3b69  stloc.2
0x3b6a  ldloca.s 2
0x3b6c  call     instance int32 System.Xml.Xsl.Location::get_Line()
0x3b71  stloc.3
0x3b72  ldloca.s 3
0x3b74  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b79  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3b7e  stelem.ref
0x3b7f  dup
0x3b80  ldc.i4.2
0x3b81  ldarg.1
0x3b82  callvirt instance valuetype System.Xml.Xsl.Location System.Xml.Xsl.ISourceLineInfo::get_Start()
0x3b87  stloc.2
0x3b88  ldloca.s 2
0x3b8a  call     instance int32 System.Xml.Xsl.Location::get_Pos()
0x3b8f  stloc.3
0x3b90  ldloca.s 3
0x3b92  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b97  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3b9c  stelem.ref
0x3b9d  call     string System.Xml.Xsl.XslTransformException::CreateMessage(string res, string[] args)
0x3ba2  stloc.1
0x3ba3  ldloc.1
0x3ba4  brfalse.s loc_3BEC
0x3ba6  ldloc.1
0x3ba7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3bac  ldc.i4.0
0x3bad  ble.s    loc_3BEC
0x3baf  ldarg.0
0x3bb0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3bb5  ldc.i4.0
0x3bb6  ble.s    loc_3BE3
0x3bb8  call     valuetype [System.Xml]System.Xml.XmlCharType [System.Xml]System.Xml.XmlCharType::get_Instance()
0x3bbd  stloc.s  4
0x3bbf  ldloca.s 4
0x3bc1  ldarg.0
0x3bc2  ldarg.0
0x3bc3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3bc8  ldc.i4.1
0x3bc9  sub
0x3bca  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3bcf  call     instance bool [System.Xml]System.Xml.XmlCharType::IsWhiteSpace(char)
0x3bd4  brtrue.s loc_3BE3
0x3bd6  ldarg.0
0x3bd7  ldstr    asc_58940// " "
0x3bdc  call     string [mscorlib]System.String::Concat(string, string)
0x3be1  starg.s  0
0x3be3  ldarg.0
0x3be4  ldloc.1
0x3be5  call     string [mscorlib]System.String::Concat(string, string)
0x3bea  starg.s  0
0x3bec  ldarg.0
0x3bed  ret
```
