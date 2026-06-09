# System.Xml.XmlSqlBinaryReader::ReadInit

- ea: `0x592d0`
- end: `0x594c5`
- name: `System.Xml.XmlSqlBinaryReader::ReadInit`
- size: `501`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x57610`
- `0x59a70`

## callees

- `0x12660`
- `0x13200`
- `0x58a20`
- `0x58a40`
- `0x58bd0`
- `0x58de0`
- `0x592d0`
- `0x59a70`
- `0x1191d0`
- `0x1193e0`

## string_xrefs

- `0x592e9`: `XmlBinary_InvalidSignature`
- `0x59312`: `XmlBinary_InvalidProtocolVersion`
- `0x5932a`: `XmlBinary_UnsupportedCodePage`
- `0x5945b`: `XmlBinary_InvalidStandalone`

## pseudocode

```c

```

## disassembly

```asm
0x592d0  ldnull
0x592d1  stloc.0
0x592d2  ldarg.0
0x592d3  ldfld    bool System.Xml.XmlSqlBinaryReader::sniffed
0x592d8  brtrue.s loc_592F4
0x592da  ldarg.0
0x592db  call     instance unsigned int16 System.Xml.XmlSqlBinaryReader::ReadUShort()
0x592e0  stloc.1
0x592e1  ldloc.1
0x592e2  ldc.i4   0xFFDF
0x592e7  beq.s    loc_592F4
0x592e9  ldstr    aXmlbinaryInval_0// "XmlBinary_InvalidSignature"
0x592ee  stloc.0
0x592ef  br       loc_594B6
0x592f4  ldarg.0
0x592f5  ldarg.0
0x592f6  call     instance unsigned int8 System.Xml.XmlSqlBinaryReader::ReadByte()
0x592fb  stfld    unsigned int8 System.Xml.XmlSqlBinaryReader::version
0x59300  ldarg.0
0x59301  ldfld    unsigned int8 System.Xml.XmlSqlBinaryReader::version
0x59306  ldc.i4.1
0x59307  beq.s    loc_5931D
0x59309  ldarg.0
0x5930a  ldfld    unsigned int8 System.Xml.XmlSqlBinaryReader::version
0x5930f  ldc.i4.2
0x59310  beq.s    loc_5931D
0x59312  ldstr    aXmlbinaryInval_1// "XmlBinary_InvalidProtocolVersion"
0x59317  stloc.0
0x59318  br       loc_594B6
0x5931d  ldc.i4   0x4B0
0x59322  ldarg.0
0x59323  call     instance unsigned int16 System.Xml.XmlSqlBinaryReader::ReadUShort()
0x59328  beq.s    loc_59335
0x5932a  ldstr    aXmlbinaryUnsup// "XmlBinary_UnsupportedCodePage"
0x5932f  stloc.0
0x59330  br       loc_594B6
0x59335  ldarg.0
0x59336  ldc.i4.0
0x59337  stfld    valuetype ScanState System.Xml.XmlSqlBinaryReader::state
0x5933c  ldc.i4   0xFE
0x59341  ldarg.0
0x59342  call     instance valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::PeekToken()
0x59347  bne.un   loc_594AF
0x5934c  ldarg.0
0x5934d  ldarg.0
0x5934e  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x59353  ldc.i4.1
0x59354  add
0x59355  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x5935a  ldarg.0
0x5935b  ldfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x59360  ldc.i4.0
0x59361  ldelema  AttrInfo
0x59366  ldsfld   string [mscorlib]System.String::Empty
0x5936b  ldarg.0
0x5936c  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x59371  ldstr    aVersion_0// "version"
0x59376  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x5937b  ldsfld   string [mscorlib]System.String::Empty
0x59380  newobj   instance void QName::.ctor(string prefix, string lname, string nsUri)
0x59385  ldarg.0
0x59386  call     instance string System.Xml.XmlSqlBinaryReader::ParseText()
0x5938b  call     instance void AttrInfo::Set(valuetype QName n, string v)
0x59390  ldarg.0
0x59391  ldc.i4.1
0x59392  stfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59397  ldc.i4   0xFD
0x5939c  ldarg.0
0x5939d  call     instance valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::PeekToken()
0x593a2  bne.un.s loc_593F6
0x593a4  ldarg.0
0x593a5  ldarg.0
0x593a6  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x593ab  ldc.i4.1
0x593ac  add
0x593ad  stfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x593b2  ldarg.0
0x593b3  ldfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x593b8  ldc.i4.1
0x593b9  ldelema  AttrInfo
0x593be  ldsfld   string [mscorlib]System.String::Empty
0x593c3  ldarg.0
0x593c4  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x593c9  ldstr    aEncoding_0// "encoding"
0x593ce  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x593d3  ldsfld   string [mscorlib]System.String::Empty
0x593d8  newobj   instance void QName::.ctor(string prefix, string lname, string nsUri)
0x593dd  ldarg.0
0x593de  call     instance string System.Xml.XmlSqlBinaryReader::ParseText()
0x593e3  call     instance void AttrInfo::Set(valuetype QName n, string v)
0x593e8  ldarg.0
0x593e9  ldarg.0
0x593ea  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x593ef  ldc.i4.1
0x593f0  add
0x593f1  stfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x593f6  ldarg.0
0x593f7  call     instance unsigned int8 System.Xml.XmlSqlBinaryReader::ReadByte()
0x593fc  stloc.2
0x593fd  ldloc.2
0x593fe  brfalse.s loc_59463
0x59400  ldloc.2
0x59401  ldc.i4.1
0x59402  sub
0x59403  ldc.i4.1
0x59404  bgt.un.s loc_5945B
0x59406  ldarg.0
0x59407  ldfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x5940c  ldarg.0
0x5940d  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59412  ldelema  AttrInfo
0x59417  ldsfld   string [mscorlib]System.String::Empty
0x5941c  ldarg.0
0x5941d  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x59422  ldstr    aStandalone_0// "standalone"
0x59427  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x5942c  ldsfld   string [mscorlib]System.String::Empty
0x59431  newobj   instance void QName::.ctor(string prefix, string lname, string nsUri)
0x59436  ldloc.2
0x59437  ldc.i4.1
0x59438  beq.s    loc_59441
0x5943a  ldstr    aNo// "no"
0x5943f  br.s     loc_59446
0x59441  ldstr    aYes// "yes"
0x59446  call     instance void AttrInfo::Set(valuetype QName n, string v)
0x5944b  ldarg.0
0x5944c  ldarg.0
0x5944d  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59452  ldc.i4.1
0x59453  add
0x59454  stfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59459  br.s     loc_59463
0x5945b  ldstr    aXmlbinaryInval_2// "XmlBinary_InvalidStandalone"
0x59460  stloc.0
0x59461  br.s     loc_594B6
0x59463  ldarg.1
0x59464  brtrue.s loc_594AF
0x59466  ldloca.s 3
0x59468  ldsfld   string [mscorlib]System.String::Empty
0x5946d  ldarg.0
0x5946e  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x59473  ldstr    aXml// "xml"
0x59478  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x5947d  ldsfld   string [mscorlib]System.String::Empty
0x59482  call     instance void QName::.ctor(string prefix, string lname, string nsUri)
0x59487  ldarg.0
0x59488  ldarg.0
0x59489  ldloc.3
0x5948a  dup
0x5948b  stloc.s  4
0x5948d  stfld    valuetype QName System.Xml.XmlSqlBinaryReader::qnameElement
0x59492  ldloc.s  4
0x59494  stfld    valuetype QName System.Xml.XmlSqlBinaryReader::qnameOther
0x59499  ldarg.0
0x5949a  ldc.i4.s 0x11
0x5949c  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlSqlBinaryReader::nodetype
0x594a1  ldarg.0
0x594a2  ldarg.0
0x594a3  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x594a8  stfld    int32 System.Xml.XmlSqlBinaryReader::posAfterAttrs
0x594ad  ldc.i4.1
0x594ae  ret
0x594af  ldarg.0
0x594b0  call     instance bool System.Xml.XmlSqlBinaryReader::ReadDoc()
0x594b5  ret
0x594b6  ldarg.0
0x594b7  ldc.i4.6
0x594b8  stfld    valuetype ScanState System.Xml.XmlSqlBinaryReader::state
0x594bd  ldloc.0
0x594be  ldnull
0x594bf  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args)
0x594c4  throw
```
