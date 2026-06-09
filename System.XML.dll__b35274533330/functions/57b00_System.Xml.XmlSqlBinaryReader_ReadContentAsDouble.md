# System.Xml.XmlSqlBinaryReader::ReadContentAsDouble

- ea: `0x57b00`
- end: `0x57c5d`
- name: `System.Xml.XmlSqlBinaryReader::ReadContentAsDouble`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x10780`
- `0x126e0`
- `0x216c0`
- `0x576b0`
- `0x57780`
- `0x57b00`
- `0x5ae80`
- `0x622f0`

## string_xrefs

- `0x57c01`: `Xml_ReadContentAsFormatException`
- `0x57c16`: `Xml_ReadContentAsFormatException`
- `0x57c2b`: `Xml_ReadContentAsFormatException`
- `0x57b08`: `ReadContentAsDouble`
- `0x57bc0`: `XmlBinary_CastNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x57b00  ldarg.0
0x57b01  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57b06  stloc.0
0x57b07  ldarg.0
0x57b08  ldstr    aReadcontentasd_1// "ReadContentAsDouble"
0x57b0d  call     instance bool System.Xml.XmlSqlBinaryReader::SetupContentAsXXX(string name)
0x57b12  brfalse  loc_57C4A
0x57b17  ldarg.0
0x57b18  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57b1d  stloc.2
0x57b1e  ldloc.2
0x57b1f  ldc.i4.s 0x7F
0x57b21  bgt.s    loc_57BA0
0x57b23  ldloc.2
0x57b24  ldc.i4.1
0x57b25  sub
0x57b26  switch   loc_57BC0, loc_57BC0, loc_57BB7, loc_57BB7, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BEC, loc_57BEC, loc_57BC0, loc_57BEC, loc_57BEC, loc_57BC0, loc_57BC0, loc_57BC0, loc_57BFB, loc_57BEC, loc_57BC0, loc_57BEC, loc_57BFB, loc_57BFB, loc_57BC0
0x57b97  ldloc.2
0x57b98  ldc.i4.s 0x7A
0x57b9a  sub
0x57b9b  ldc.i4.5
0x57b9c  ble.un.s loc_57BC0
0x57b9e  br.s     loc_57BFB
0x57ba0  ldloc.2
0x57ba1  ldc.i4   0x81
0x57ba6  sub
0x57ba7  ldc.i4.s 0xB
0x57ba9  ble.un.s loc_57BC0
0x57bab  ldloc.2
0x57bac  ldc.i4   0xF7
0x57bb1  sub
0x57bb2  ldc.i4.1
0x57bb3  ble.un.s loc_57BEE
0x57bb5  br.s     loc_57BFB
0x57bb7  ldarg.0
0x57bb8  call     instance float64 System.Xml.XmlSqlBinaryReader::ValueAsDouble()
0x57bbd  stloc.1
0x57bbe  br.s     loc_57BFD
0x57bc0  ldstr    aXmlbinaryCastn// "XmlBinary_CastNotSupported"
0x57bc5  ldc.i4.2
0x57bc6  newarr   [mscorlib]System.Object
0x57bcb  dup
0x57bcc  ldc.i4.0
0x57bcd  ldarg.0
0x57bce  ldfld    valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::token
0x57bd3  box      System.Xml.BinXmlToken
0x57bd8  stelem.ref
0x57bd9  dup
0x57bda  ldc.i4.1
0x57bdb  ldstr    aDouble// "Double"
0x57be0  stelem.ref
0x57be1  call     string System.Xml.Res::GetString(string name, object[] args)
0x57be6  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string)
0x57beb  throw
0x57bec  leave.s  loc_57C54
0x57bee  ldsfld   string [mscorlib]System.String::Empty
0x57bf3  call     float64 System.Xml.XmlConvert::ToDouble(string s)
0x57bf8  stloc.3
0x57bf9  leave.s  loc_57C5B
0x57bfb  leave.s  loc_57C54
0x57bfd  leave.s  loc_57C3E
0x57bff  stloc.s  4
0x57c01  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57c06  ldstr    aDouble// "Double"
0x57c0b  ldloc.s  4
0x57c0d  ldnull
0x57c0e  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57c13  throw
0x57c14  stloc.s  5
0x57c16  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57c1b  ldstr    aDouble// "Double"
0x57c20  ldloc.s  5
0x57c22  ldnull
0x57c23  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57c28  throw
0x57c29  stloc.s  6
0x57c2b  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x57c30  ldstr    aDouble// "Double"
0x57c35  ldloc.s  6
0x57c37  ldnull
0x57c38  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x57c3d  throw
0x57c3e  ldarg.0
0x57c3f  ldloc.0
0x57c40  call     instance int32 System.Xml.XmlSqlBinaryReader::FinishContentAsXXX(int32 origPos)
0x57c45  stloc.0
0x57c46  ldloc.1
0x57c47  stloc.3
0x57c48  leave.s  loc_57C5B
0x57c4a  leave.s  loc_57C54
0x57c4c  ldarg.0
0x57c4d  ldloc.0
0x57c4e  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x57c53  endfinally
0x57c54  ldarg.0
0x57c55  call     instance float64 System.Xml.XmlReader::ReadContentAsDouble()
0x57c5a  ret
0x57c5b  ldloc.3
0x57c5c  ret
```
