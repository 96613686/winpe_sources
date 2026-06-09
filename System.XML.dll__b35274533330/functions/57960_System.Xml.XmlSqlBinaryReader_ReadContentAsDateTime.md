# System.Xml.XmlSqlBinaryReader::ReadContentAsDateTime

- ea: `0x57960`
- end: `0x57afa`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsDateTime`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x10b70`
- `0x126e0`
- `0x21640`
- `0x576b0`
- `0x57780`
- `0x57960`
- `0x5af50`
- `0x622f0`

## string_xrefs

- `0x57a9e`: `Xml_ReadContentAsFormatException`
- `0x57ab3`: `Xml_ReadContentAsFormatException`
- `0x57ac8`: `Xml_ReadContentAsFormatException`
- `0x57968`: `ReadContentAsDateTime`
- `0x57a5c`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x57960  ldarg.0
0x57961  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57966  stloc.0
0x57967  ldarg.0
0x57968  ldstr    aReadcontentasd// "ReadContentAsDateTime"
0x5796d  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x57972  brfalse  loc_57AE7
0x57977  ldarg.0
0x57978  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x5797d  stloc.2
0x5797e  ldloc.2
0x5797f  ldc.i4.1
0x57980  sub
0x57981  switch   loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A88, loc_57A88, loc_57A5C, loc_57A88, loc_57A88, loc_57A53, loc_57A53, loc_57A5C, loc_57A98, loc_57A88, loc_57A5C, loc_57A88, loc_57A98, loc_57A98, loc_57A5C
0x579f2  ldloc.2
0x579f3  ldc.i4.s 0x7A
0x579f5  sub
0x579f6  switch   loc_57A53, loc_57A53, loc_57A53, loc_57A53, loc_57A53, loc_57A53, loc_57A98, loc_57A53, loc_57A53, loc_57A53, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C, loc_57A5C
0x57a47  ldloc.2
0x57a48  ldc.i4   0xF7
0x57a4d  sub
0x57a4e  ldc.i4.1
0x57a4f  ble.un.s loc_57A8A
0x57a51  br.s     loc_57A98
0x57a53  ldarg.0
0x57a54  call     instance valuetype [mscorlib]System.DateTime System.Xml.XmlSqlBinaryReader::ValueAsDateTime()
0x57a59  stloc.1
0x57a5a  br.s     loc_57A9A
0x57a5c  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x57a61  ldc.i4.2
0x57a62  newarr   [mscorlib]System.Object
0x57a67  dup
0x57a68  ldc.i4.0
0x57a69  ldarg.0
0x57a6a  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57a6f  box      System.Xml.BinXmlToken
0x57a74  stelem.ref
0x57a75  dup
0x57a76  ldc.i4.1
0x57a77  ldstr    aDatetime// "DateTime"
0x57a7c  stelem.ref
0x57a7d  call     string System.Xml.Res::GetString(string name, object[] args)
0x57a82  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x57a87  throw
0x57a88  leave.s  loc_57AF1
0x57a8a  ldsfld   string [mscorlib]System.String::Empty
0x57a8f  ldc.i4.3
0x57a90  call     valuetype [mscorlib]System.DateTime System.Xml.XmlConvert::ToDateTime(string s, valuetype System.Xml.XmlDateTimeSerializationMode dateTimeOption)
0x57a95  stloc.3
0x57a96  leave.s  loc_57AF8
0x57a98  leave.s  loc_57AF1
0x57a9a  leave.s  loc_57ADB
0x57a9c  stloc.s  4
0x57a9e  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57aa3  ldstr    aDatetime// "DateTime"
0x57aa8  ldloc.s  4
0x57aaa  ldnull
0x57aab  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57ab0  throw
0x57ab1  stloc.s  5
0x57ab3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57ab8  ldstr    aDatetime// "DateTime"
0x57abd  ldloc.s  5
0x57abf  ldnull
0x57ac0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57ac5  throw
0x57ac6  stloc.s  6
0x57ac8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57acd  ldstr    aDatetime// "DateTime"
0x57ad2  ldloc.s  6
0x57ad4  ldnull
0x57ad5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57ada  throw
0x57adb  ldarg.0
0x57adc  ldloc.0
0x57add  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x57ae2  stloc.0
0x57ae3  ldloc.1
0x57ae4  stloc.3
0x57ae5  leave.s  loc_57AF8
0x57ae7  leave.s  loc_57AF1
0x57ae9  ldarg.0
0x57aea  ldloc.0
0x57aeb  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57af0  endfinally
0x57af1  ldarg.0
0x57af2  call     instance valuetype [mscorlib]System.DateTime System.Xml.XmlReader::ReadContentAsDateTime()
0x57af7  ret
0x57af8  ldloc.3
0x57af9  ret
```
