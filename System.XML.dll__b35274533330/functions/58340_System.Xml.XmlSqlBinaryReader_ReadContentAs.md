# System.Xml.XmlSqlBinaryReader::ReadContentAs

- ea: `0x58340`
- end: `0x58414`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAs`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x215d0`
- `0x21820`
- `0x576b0`
- `0x57780`
- `0x58340`
- `0x5b630`
- `0x5ba10`

## string_xrefs

- `0x583b4`: `Xml_ReadContentAsFormatException`
- `0x583c8`: `Xml_ReadContentAsFormatException`
- `0x583dd`: `Xml_ReadContentAsFormatException`
- `0x58348`: `ReadContentAs`

## pseudocode

```c

```

## disassembly

```asm
0x58340  ldarg.0
0x58341  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x58346  stloc.0
0x58347  ldarg.0
0x58348  ldstr    aReadcontentas// "ReadContentAs"
0x5834d  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x58352  brfalse  loc_583FE
0x58357  ldarg.0
0x58358  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x5835d  ldc.i4.1
0x5835e  beq.s    loc_5836A
0x58360  ldarg.0
0x58361  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x58366  ldc.i4.s 0xF
0x58368  bne.un.s loc_58372
0x5836a  ldsfld   string [mscorlib]System.String::Empty
0x5836f  stloc.1
0x58370  br.s     loc_583B1
0x58372  ldarg.1
0x58373  ldarg.0
0x58374  callvirt instance class [mscorlib]System.Type System.Xml.XmlReader::get_ValueType()
0x58379  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5837e  brtrue.s loc_58392
0x58380  ldarg.1
0x58381  ldtoken  [mscorlib]System.Object
0x58386  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5838b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x58390  brfalse.s loc_583A2
0x58392  ldarg.0
0x58393  ldarg.0
0x58394  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x58399  ldc.i4.0
0x5839a  call     instance object System.Xml.XmlSqlBinaryReader::ValueAsObject(valuetype System.Xml.BinXmlToken token, bool returnInternalTypes)
0x5839f  stloc.1
0x583a0  br.s     loc_583B1
0x583a2  ldarg.0
0x583a3  ldarg.0
0x583a4  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x583a9  ldarg.1
0x583aa  ldarg.2
0x583ab  call     instance object System.Xml.XmlSqlBinaryReader::ValueAs(valuetype System.Xml.BinXmlToken token, class [mscorlib]System.Type returnType, class System.Xml.IXmlNamespaceResolver namespaceResolver)
0x583b0  stloc.1
0x583b1  leave.s  loc_583F1
0x583b3  stloc.2
0x583b4  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x583b9  ldarg.1
0x583ba  callvirt instance string [mscorlib]System.Object::ToString()
0x583bf  ldloc.2
0x583c0  ldnull
0x583c1  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x583c6  throw
0x583c7  stloc.3
0x583c8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x583cd  ldarg.1
0x583ce  callvirt instance string [mscorlib]System.Object::ToString()
0x583d3  ldloc.3
0x583d4  ldnull
0x583d5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x583da  throw
0x583db  stloc.s  4
0x583dd  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x583e2  ldarg.1
0x583e3  callvirt instance string [mscorlib]System.Object::ToString()
0x583e8  ldloc.s  4
0x583ea  ldnull
0x583eb  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x583f0  throw
0x583f1  ldarg.0
0x583f2  ldloc.0
0x583f3  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x583f8  stloc.0
0x583f9  ldloc.1
0x583fa  stloc.s  5
0x583fc  leave.s  loc_58411
0x583fe  leave.s  loc_58408
0x58400  ldarg.0
0x58401  ldloc.0
0x58402  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x58407  endfinally
0x58408  ldarg.0
0x58409  ldarg.1
0x5840a  ldarg.2
0x5840b  call     instance object System.Xml.XmlReader::ReadContentAs(class [mscorlib]System.Type returnType, class System.Xml.IXmlNamespaceResolver namespaceResolver)
0x58410  ret
0x58411  ldloc.s  5
0x58413  ret
```
