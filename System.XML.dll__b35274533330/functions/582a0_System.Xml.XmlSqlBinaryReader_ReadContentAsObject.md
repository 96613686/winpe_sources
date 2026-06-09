# System.Xml.XmlSqlBinaryReader::ReadContentAsObject

- ea: `0x582a0`
- end: `0x5833b`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsObject`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x215e0`
- `0x576b0`
- `0x57780`
- `0x582a0`
- `0x5b630`

## string_xrefs

- `0x582a8`: `ReadContentAsObject`
- `0x582e0`: `Xml_ReadContentAsFormatException`
- `0x582f3`: `Xml_ReadContentAsFormatException`
- `0x58307`: `Xml_ReadContentAsFormatException`

## pseudocode

```c

```

## disassembly

```asm
0x582a0  ldarg.0
0x582a1  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x582a6  stloc.0
0x582a7  ldarg.0
0x582a8  ldstr    aReadcontentaso// "ReadContentAsObject"
0x582ad  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x582b2  brfalse.s loc_58327
0x582b4  ldarg.0
0x582b5  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x582ba  ldc.i4.1
0x582bb  beq.s    loc_582C7
0x582bd  ldarg.0
0x582be  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x582c3  ldc.i4.s 0xF
0x582c5  bne.un.s loc_582CF
0x582c7  ldsfld   string [mscorlib]System.String::Empty
0x582cc  stloc.1
0x582cd  br.s     loc_582DD
0x582cf  ldarg.0
0x582d0  ldarg.0
0x582d1  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x582d6  ldc.i4.0
0x582d7  call     instance object System.Xml.XmlSqlBinaryReader::ValueAsObject(valuetype System.Xml.BinXmlToken token, bool returnInternalTypes)
0x582dc  stloc.1
0x582dd  leave.s  loc_5831A
0x582df  stloc.2
0x582e0  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x582e5  ldstr    aObject// "Object"
0x582ea  ldloc.2
0x582eb  ldnull
0x582ec  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x582f1  throw
0x582f2  stloc.3
0x582f3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x582f8  ldstr    aObject// "Object"
0x582fd  ldloc.3
0x582fe  ldnull
0x582ff  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x58304  throw
0x58305  stloc.s  4
0x58307  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x5830c  ldstr    aObject// "Object"
0x58311  ldloc.s  4
0x58313  ldnull
0x58314  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x58319  throw
0x5831a  ldarg.0
0x5831b  ldloc.0
0x5831c  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x58321  stloc.0
0x58322  ldloc.1
0x58323  stloc.s  5
0x58325  leave.s  loc_58338
0x58327  leave.s  loc_58331
0x58329  ldarg.0
0x5832a  ldloc.0
0x5832b  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x58330  endfinally
0x58331  ldarg.0
0x58332  call     instance object System.Xml.XmlReader::ReadContentAsObject()
0x58337  ret
0x58338  ldloc.s  5
0x5833a  ret
```
