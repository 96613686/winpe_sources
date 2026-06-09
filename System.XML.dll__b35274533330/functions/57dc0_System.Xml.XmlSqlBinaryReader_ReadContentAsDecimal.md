# System.Xml.XmlSqlBinaryReader::ReadContentAsDecimal

- ea: `0x57dc0`
- end: `0x57f59`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsDecimal`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x10370`
- `0x126e0`
- `0x21740`
- `0x576b0`
- `0x57780`
- `0x57dc0`
- `0x5ad40`
- `0x622f0`

## string_xrefs

- `0x57efd`: `Xml_ReadContentAsFormatException`
- `0x57f12`: `Xml_ReadContentAsFormatException`
- `0x57f27`: `Xml_ReadContentAsFormatException`
- `0x57dc8`: `ReadContentAsDecimal`
- `0x57ebc`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x57dc0  ldarg.0
0x57dc1  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57dc6  stloc.0
0x57dc7  ldarg.0
0x57dc8  ldstr    aReadcontentasd_2// "ReadContentAsDecimal"
0x57dcd  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x57dd2  brfalse  loc_57F46
0x57dd7  ldarg.0
0x57dd8  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57ddd  stloc.2
0x57dde  ldloc.2
0x57ddf  ldc.i4.1
0x57de0  sub
0x57de1  switch   loc_57EB3, loc_57EB3, loc_57EBC, loc_57EBC, loc_57EB3, loc_57EB3, loc_57EB3, loc_57EB3, loc_57EBC, loc_57EB3, loc_57EB3, loc_57EBC, loc_57EE8, loc_57EE8, loc_57EBC, loc_57EE8, loc_57EE8, loc_57EBC, loc_57EBC, loc_57EB3, loc_57EF7, loc_57EE8, loc_57EBC, loc_57EE8, loc_57EF7, loc_57EF7, loc_57EBC
0x57e52  ldloc.2
0x57e53  ldc.i4.s 0x7A
0x57e55  sub
0x57e56  switch   loc_57EBC, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EF7, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EBC, loc_57EB3, loc_57EB3, loc_57EB3, loc_57EB3, loc_57EB3, loc_57EBC
0x57ea7  ldloc.2
0x57ea8  ldc.i4   0xF7
0x57ead  sub
0x57eae  ldc.i4.1
0x57eaf  ble.un.s loc_57EEA
0x57eb1  br.s     loc_57EF7
0x57eb3  ldarg.0
0x57eb4  call     instance valuetype [mscorlib]System.Decimal System.Xml.XmlSqlBinaryReader::ValueAsDecimal()
0x57eb9  stloc.1
0x57eba  br.s     loc_57EF9
0x57ebc  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x57ec1  ldc.i4.2
0x57ec2  newarr   [mscorlib]System.Object
0x57ec7  dup
0x57ec8  ldc.i4.0
0x57ec9  ldarg.0
0x57eca  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57ecf  box      System.Xml.BinXmlToken
0x57ed4  stelem.ref
0x57ed5  dup
0x57ed6  ldc.i4.1
0x57ed7  ldstr    aDecimal// "Decimal"
0x57edc  stelem.ref
0x57edd  call     string System.Xml.Res::GetString(string name, object[] args)
0x57ee2  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x57ee7  throw
0x57ee8  leave.s  loc_57F50
0x57eea  ldsfld   string [mscorlib]System.String::Empty
0x57eef  call     valuetype [mscorlib]System.Decimal System.Xml.XmlConvert::ToDecimal(string s)
0x57ef4  stloc.3
0x57ef5  leave.s  loc_57F57
0x57ef7  leave.s  loc_57F50
0x57ef9  leave.s  loc_57F3A
0x57efb  stloc.s  4
0x57efd  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57f02  ldstr    aDecimal// "Decimal"
0x57f07  ldloc.s  4
0x57f09  ldnull
0x57f0a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57f0f  throw
0x57f10  stloc.s  5
0x57f12  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57f17  ldstr    aDecimal// "Decimal"
0x57f1c  ldloc.s  5
0x57f1e  ldnull
0x57f1f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57f24  throw
0x57f25  stloc.s  6
0x57f27  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57f2c  ldstr    aDecimal// "Decimal"
0x57f31  ldloc.s  6
0x57f33  ldnull
0x57f34  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57f39  throw
0x57f3a  ldarg.0
0x57f3b  ldloc.0
0x57f3c  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x57f41  stloc.0
0x57f42  ldloc.1
0x57f43  stloc.3
0x57f44  leave.s  loc_57F57
0x57f46  leave.s  loc_57F50
0x57f48  ldarg.0
0x57f49  ldloc.0
0x57f4a  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57f4f  endfinally
0x57f50  ldarg.0
0x57f51  call     instance valuetype [mscorlib]System.Decimal System.Xml.XmlReader::ReadContentAsDecimal()
0x57f56  ret
0x57f57  ldloc.3
0x57f58  ret
```
