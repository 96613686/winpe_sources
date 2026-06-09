# System.Xml.XmlSqlBinaryReader::ReadContentAsLong

- ea: `0x58100`
- end: `0x58299`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsLong`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x10500`
- `0x126e0`
- `0x217c0`
- `0x576b0`
- `0x57780`
- `0x58100`
- `0x5abe0`
- `0x622f0`

## string_xrefs

- `0x5823d`: `Xml_ReadContentAsFormatException`
- `0x58252`: `Xml_ReadContentAsFormatException`
- `0x58267`: `Xml_ReadContentAsFormatException`
- `0x58108`: `ReadContentAsLong`
- `0x581fc`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x58100  ldarg.0
0x58101  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x58106  stloc.0
0x58107  ldarg.0
0x58108  ldstr    aReadcontentasl// "ReadContentAsLong"
0x5810d  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x58112  brfalse  loc_58286
0x58117  ldarg.0
0x58118  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x5811d  stloc.2
0x5811e  ldloc.2
0x5811f  ldc.i4.1
0x58120  sub
0x58121  switch   loc_581F3, loc_581F3, loc_581FC, loc_581FC, loc_581F3, loc_581F3, loc_581F3, loc_581F3, loc_581FC, loc_581F3, loc_581F3, loc_581FC, loc_58228, loc_58228, loc_581FC, loc_58228, loc_58228, loc_581FC, loc_581FC, loc_581F3, loc_58237, loc_58228, loc_581FC, loc_58228, loc_58237, loc_58237, loc_581FC
0x58192  ldloc.2
0x58193  ldc.i4.s 0x7A
0x58195  sub
0x58196  switch   loc_581FC, loc_581FC, loc_581FC, loc_581FC, loc_581FC, loc_581FC, loc_58237, loc_581FC, loc_581FC, loc_581FC, loc_581FC, loc_581FC, loc_581FC, loc_581F3, loc_581F3, loc_581F3, loc_581F3, loc_581F3, loc_581FC
0x581e7  ldloc.2
0x581e8  ldc.i4   0xF7
0x581ed  sub
0x581ee  ldc.i4.1
0x581ef  ble.un.s loc_5822A
0x581f1  br.s     loc_58237
0x581f3  ldarg.0
0x581f4  call     instance int64 System.Xml.XmlSqlBinaryReader::ValueAsLong()
0x581f9  stloc.1
0x581fa  br.s     loc_58239
0x581fc  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x58201  ldc.i4.2
0x58202  newarr   [mscorlib]System.Object
0x58207  dup
0x58208  ldc.i4.0
0x58209  ldarg.0
0x5820a  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x5820f  box      System.Xml.BinXmlToken
0x58214  stelem.ref
0x58215  dup
0x58216  ldc.i4.1
0x58217  ldstr    aInt64// "Int64"
0x5821c  stelem.ref
0x5821d  call     string System.Xml.Res::GetString(string name, object[] args)
0x58222  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x58227  throw
0x58228  leave.s  loc_58290
0x5822a  ldsfld   string [mscorlib]System.String::Empty
0x5822f  call     int64 System.Xml.XmlConvert::ToInt64(string s)
0x58234  stloc.3
0x58235  leave.s  loc_58297
0x58237  leave.s  loc_58290
0x58239  leave.s  loc_5827A
0x5823b  stloc.s  4
0x5823d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x58242  ldstr    aInt64// "Int64"
0x58247  ldloc.s  4
0x58249  ldnull
0x5824a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x5824f  throw
0x58250  stloc.s  5
0x58252  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x58257  ldstr    aInt64// "Int64"
0x5825c  ldloc.s  5
0x5825e  ldnull
0x5825f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x58264  throw
0x58265  stloc.s  6
0x58267  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x5826c  ldstr    aInt64// "Int64"
0x58271  ldloc.s  6
0x58273  ldnull
0x58274  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x58279  throw
0x5827a  ldarg.0
0x5827b  ldloc.0
0x5827c  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x58281  stloc.0
0x58282  ldloc.1
0x58283  stloc.3
0x58284  leave.s  loc_58297
0x58286  leave.s  loc_58290
0x58288  ldarg.0
0x58289  ldloc.0
0x5828a  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x5828f  endfinally
0x58290  ldarg.0
0x58291  call     instance int64 System.Xml.XmlReader::ReadContentAsLong()
0x58296  ret
0x58297  ldloc.3
0x58298  ret
```
