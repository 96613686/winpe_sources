# System.Xml.XmlSqlBinaryReader::ReadContentAsFloat

- ea: `0x57c60`
- end: `0x57dbe`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsFloat`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x10690`
- `0x126e0`
- `0x21700`
- `0x576b0`
- `0x57780`
- `0x57c60`
- `0x5ae80`
- `0x622f0`

## string_xrefs

- `0x57d62`: `Xml_ReadContentAsFormatException`
- `0x57d77`: `Xml_ReadContentAsFormatException`
- `0x57d8c`: `Xml_ReadContentAsFormatException`
- `0x57c68`: `ReadContentAsFloat`
- `0x57d21`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x57c60  ldarg.0
0x57c61  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57c66  stloc.0
0x57c67  ldarg.0
0x57c68  ldstr    aReadcontentasf// "ReadContentAsFloat"
0x57c6d  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x57c72  brfalse  loc_57DAB
0x57c77  ldarg.0
0x57c78  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57c7d  stloc.2
0x57c7e  ldloc.2
0x57c7f  ldc.i4.s 0x7F
0x57c81  bgt.s    loc_57D00
0x57c83  ldloc.2
0x57c84  ldc.i4.1
0x57c85  sub
0x57c86  switch   loc_57D21, loc_57D21, loc_57D17, loc_57D17, loc_57D21, loc_57D21, loc_57D21, loc_57D21, loc_57D21, loc_57D21, loc_57D21, loc_57D21, loc_57D4D, loc_57D4D, loc_57D21, loc_57D4D, loc_57D4D, loc_57D21, loc_57D21, loc_57D21, loc_57D5C, loc_57D4D, loc_57D21, loc_57D4D, loc_57D5C, loc_57D5C, loc_57D21
0x57cf7  ldloc.2
0x57cf8  ldc.i4.s 0x7A
0x57cfa  sub
0x57cfb  ldc.i4.5
0x57cfc  ble.un.s loc_57D21
0x57cfe  br.s     loc_57D5C
0x57d00  ldloc.2
0x57d01  ldc.i4   0x81
0x57d06  sub
0x57d07  ldc.i4.s 0xB
0x57d09  ble.un.s loc_57D21
0x57d0b  ldloc.2
0x57d0c  ldc.i4   0xF7
0x57d11  sub
0x57d12  ldc.i4.1
0x57d13  ble.un.s loc_57D4F
0x57d15  br.s     loc_57D5C
0x57d17  ldarg.0
0x57d18  call     instance float64 System.Xml.XmlSqlBinaryReader::ValueAsDouble()
0x57d1d  conv.r4
0x57d1e  stloc.1
0x57d1f  br.s     loc_57D5E
0x57d21  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x57d26  ldc.i4.2
0x57d27  newarr   [mscorlib]System.Object
0x57d2c  dup
0x57d2d  ldc.i4.0
0x57d2e  ldarg.0
0x57d2f  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57d34  box      System.Xml.BinXmlToken
0x57d39  stelem.ref
0x57d3a  dup
0x57d3b  ldc.i4.1
0x57d3c  ldstr    aFloat// "Float"
0x57d41  stelem.ref
0x57d42  call     string System.Xml.Res::GetString(string name, object[] args)
0x57d47  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x57d4c  throw
0x57d4d  leave.s  loc_57DB5
0x57d4f  ldsfld   string [mscorlib]System.String::Empty
0x57d54  call     float32 System.Xml.XmlConvert::ToSingle(string s)
0x57d59  stloc.3
0x57d5a  leave.s  loc_57DBC
0x57d5c  leave.s  loc_57DB5
0x57d5e  leave.s  loc_57D9F
0x57d60  stloc.s  4
0x57d62  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57d67  ldstr    aFloat// "Float"
0x57d6c  ldloc.s  4
0x57d6e  ldnull
0x57d6f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57d74  throw
0x57d75  stloc.s  5
0x57d77  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57d7c  ldstr    aFloat// "Float"
0x57d81  ldloc.s  5
0x57d83  ldnull
0x57d84  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57d89  throw
0x57d8a  stloc.s  6
0x57d8c  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57d91  ldstr    aFloat// "Float"
0x57d96  ldloc.s  6
0x57d98  ldnull
0x57d99  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57d9e  throw
0x57d9f  ldarg.0
0x57da0  ldloc.0
0x57da1  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x57da6  stloc.0
0x57da7  ldloc.1
0x57da8  stloc.3
0x57da9  leave.s  loc_57DBC
0x57dab  leave.s  loc_57DB5
0x57dad  ldarg.0
0x57dae  ldloc.0
0x57daf  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57db4  endfinally
0x57db5  ldarg.0
0x57db6  call     instance float32 System.Xml.XmlReader::ReadContentAsFloat()
0x57dbb  ret
0x57dbc  ldloc.3
0x57dbd  ret
```
