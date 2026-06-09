# System.Xml.XmlSqlBinaryReader::ReadContentAsBoolean

- ea: `0x577d0`
- end: `0x57960`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsBoolean`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x10230`
- `0x126e0`
- `0x21600`
- `0x576b0`
- `0x57780`
- `0x577d0`
- `0x622f0`

## string_xrefs

- `0x577da`: `ReadContentAsBoolean`
- `0x57919`: `Xml_ReadContentAsFormatException`
- `0x5792e`: `Xml_ReadContentAsFormatException`
- `0x578d8`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x577d0  ldarg.0
0x577d1  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x577d6  stloc.0
0x577d7  ldc.i4.0
0x577d8  stloc.1
0x577d9  ldarg.0
0x577da  ldstr    aReadcontentasb_1// "ReadContentAsBoolean"
0x577df  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x577e4  brfalse  loc_5794D
0x577e9  ldarg.0
0x577ea  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x577ef  stloc.2
0x577f0  ldloc.2
0x577f1  ldc.i4.1
0x577f2  sub
0x577f3  switch   loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_57904, loc_57904, loc_578D8, loc_57904, loc_57904, loc_578D8, loc_578D8, loc_578D8, loc_57913, loc_57904, loc_578D8, loc_57904, loc_57913, loc_57913, loc_578D8
0x57864  ldloc.2
0x57865  ldc.i4.s 0x7A
0x57867  sub
0x57868  switch   loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_57913, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578C5, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8, loc_578D8
0x578b9  ldloc.2
0x578ba  ldc.i4   0xF7
0x578bf  sub
0x578c0  ldc.i4.1
0x578c1  ble.un.s loc_57906
0x578c3  br.s     loc_57913
0x578c5  ldarg.0
0x578c6  ldfld    unsigned int8[] System.Xml.XmlSqlBinaryReader::data
0x578cb  ldarg.0
0x578cc  ldfld    int32 System.Xml.XmlSqlBinaryReader::tokDataPos
0x578d1  ldelem.u1
0x578d2  ldc.i4.0
0x578d3  cgt.un
0x578d5  stloc.1
0x578d6  br.s     loc_57915
0x578d8  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x578dd  ldc.i4.2
0x578de  newarr   [mscorlib]System.Object
0x578e3  dup
0x578e4  ldc.i4.0
0x578e5  ldarg.0
0x578e6  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x578eb  box      System.Xml.BinXmlToken
0x578f0  stelem.ref
0x578f1  dup
0x578f2  ldc.i4.1
0x578f3  ldstr    aBoolean_0// "Boolean"
0x578f8  stelem.ref
0x578f9  call     string System.Xml.Res::GetString(string name, object[] args)
0x578fe  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x57903  throw
0x57904  leave.s  loc_57957
0x57906  ldsfld   string [mscorlib]System.String::Empty
0x5790b  call     bool System.Xml.XmlConvert::ToBoolean(string s)
0x57910  stloc.3
0x57911  leave.s  loc_5795E
0x57913  leave.s  loc_57957
0x57915  leave.s  loc_57941
0x57917  stloc.s  4
0x57919  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x5791e  ldstr    aBoolean_0// "Boolean"
0x57923  ldloc.s  4
0x57925  ldnull
0x57926  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x5792b  throw
0x5792c  stloc.s  5
0x5792e  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57933  ldstr    aBoolean_0// "Boolean"
0x57938  ldloc.s  5
0x5793a  ldnull
0x5793b  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57940  throw
0x57941  ldarg.0
0x57942  ldloc.0
0x57943  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x57948  stloc.0
0x57949  ldloc.1
0x5794a  stloc.3
0x5794b  leave.s  loc_5795E
0x5794d  leave.s  loc_57957
0x5794f  ldarg.0
0x57950  ldloc.0
0x57951  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57956  endfinally
0x57957  ldarg.0
0x57958  call     instance bool System.Xml.XmlReader::ReadContentAsBoolean()
0x5795d  ret
0x5795e  ldloc.3
0x5795f  ret
```
