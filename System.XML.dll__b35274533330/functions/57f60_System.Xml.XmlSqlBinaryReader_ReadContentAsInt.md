# System.Xml.XmlSqlBinaryReader::ReadContentAsInt

- ea: `0x57f60`
- end: `0x580fa`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsInt`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x104b0`
- `0x126e0`
- `0x21780`
- `0x576b0`
- `0x57780`
- `0x57f60`
- `0x5abe0`
- `0x622f0`

## string_xrefs

- `0x5809e`: `Xml_ReadContentAsFormatException`
- `0x580b3`: `Xml_ReadContentAsFormatException`
- `0x580c8`: `Xml_ReadContentAsFormatException`
- `0x57f68`: `ReadContentAsInt`
- `0x5805d`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x57f60  ldarg.0
0x57f61  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57f66  stloc.0
0x57f67  ldarg.0
0x57f68  ldstr    aReadcontentasi// "ReadContentAsInt"
0x57f6d  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x57f72  brfalse  loc_580E7
0x57f77  ldarg.0
0x57f78  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57f7d  stloc.2
0x57f7e  ldloc.2
0x57f7f  ldc.i4.1
0x57f80  sub
0x57f81  switch   loc_58053, loc_58053, loc_5805D, loc_5805D, loc_58053, loc_58053, loc_58053, loc_58053, loc_5805D, loc_58053, loc_58053, loc_5805D, loc_58089, loc_58089, loc_5805D, loc_58089, loc_58089, loc_5805D, loc_5805D, loc_58053, loc_58098, loc_58089, loc_5805D, loc_58089, loc_58098, loc_58098, loc_5805D
0x57ff2  ldloc.2
0x57ff3  ldc.i4.s 0x7A
0x57ff5  sub
0x57ff6  switch   loc_5805D, loc_5805D, loc_5805D, loc_5805D, loc_5805D, loc_5805D, loc_58098, loc_5805D, loc_5805D, loc_5805D, loc_5805D, loc_5805D, loc_5805D, loc_58053, loc_58053, loc_58053, loc_58053, loc_58053, loc_5805D
0x58047  ldloc.2
0x58048  ldc.i4   0xF7
0x5804d  sub
0x5804e  ldc.i4.1
0x5804f  ble.un.s loc_5808B
0x58051  br.s     loc_58098
0x58053  ldarg.0
0x58054  call     instance int64 System.Xml.XmlSqlBinaryReader::ValueAsLong()
0x58059  conv.ovf.i2.un
0x5805a  stloc.1
0x5805b  br.s     loc_5809A
0x5805d  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x58062  ldc.i4.2
0x58063  newarr   [mscorlib]System.Object
0x58068  dup
0x58069  ldc.i4.0
0x5806a  ldarg.0
0x5806b  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x58070  box      System.Xml.BinXmlToken
0x58075  stelem.ref
0x58076  dup
0x58077  ldc.i4.1
0x58078  ldstr    aInt32// "Int32"
0x5807d  stelem.ref
0x5807e  call     string System.Xml.Res::GetString(string name, object[] args)
0x58083  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x58088  throw
0x58089  leave.s  loc_580F1
0x5808b  ldsfld   string [mscorlib]System.String::Empty
0x58090  call     int32 System.Xml.XmlConvert::ToInt32(string s)
0x58095  stloc.3
0x58096  leave.s  loc_580F8
0x58098  leave.s  loc_580F1
0x5809a  leave.s  loc_580DB
0x5809c  stloc.s  4
0x5809e  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x580a3  ldstr    aInt32// "Int32"
0x580a8  ldloc.s  4
0x580aa  ldnull
0x580ab  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x580b0  throw
0x580b1  stloc.s  5
0x580b3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x580b8  ldstr    aInt32// "Int32"
0x580bd  ldloc.s  5
0x580bf  ldnull
0x580c0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x580c5  throw
0x580c6  stloc.s  6
0x580c8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x580cd  ldstr    aInt32// "Int32"
0x580d2  ldloc.s  6
0x580d4  ldnull
0x580d5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x580da  throw
0x580db  ldarg.0
0x580dc  ldloc.0
0x580dd  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x580e2  stloc.0
0x580e3  ldloc.1
0x580e4  stloc.3
0x580e5  leave.s  loc_580F8
0x580e7  leave.s  loc_580F1
0x580e9  ldarg.0
0x580ea  ldloc.0
0x580eb  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x580f0  endfinally
0x580f1  ldarg.0
0x580f2  call     instance int32 System.Xml.XmlReader::ReadContentAsInt()
0x580f7  ret
0x580f8  ldloc.3
0x580f9  ret
```
