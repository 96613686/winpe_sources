# System.Xml.DtdParser::ScanQName_0

- ea: `0x603d0`
- end: `0x6055b`
- name: `System.Xml.DtdParser::ScanQName_0`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x603b0`
- `0x603c0`

## callees

- `0x12920`
- `0x12940`
- `0x603d0`
- `0x60560`
- `0x60df0`
- `0x60e40`

## string_xrefs

- `0x60454`: `Xml_BadStartNameChar`
- `0x604c2`: `Xml_BadNameChar`
- `0x6043c`: `Xml_UnexpectedEOF`
- `0x60536`: `Xml_UnexpectedEOF`

## pseudocode

```c

```

## disassembly

```asm
0x603d0  ldarg.0
0x603d1  ldarg.0
0x603d2  ldfld    int32 System.Xml.DtdParser::curPos
0x603d7  stfld    int32 System.Xml.DtdParser::tokenStartPos
0x603dc  ldc.i4.m1
0x603dd  stloc.0
0x603de  ldarg.0
0x603df  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x603e4  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x603e9  ldarg.0
0x603ea  ldfld    char[] System.Xml.DtdParser::chars
0x603ef  ldarg.0
0x603f0  ldfld    int32 System.Xml.DtdParser::curPos
0x603f5  ldelem.u2
0x603f6  add
0x603f7  ldind.u1
0x603f8  ldc.i4.4
0x603f9  and
0x603fa  brtrue.s loc_6040D
0x603fc  ldarg.0
0x603fd  ldfld    char[] System.Xml.DtdParser::chars
0x60402  ldarg.0
0x60403  ldfld    int32 System.Xml.DtdParser::curPos
0x60408  ldelem.u2
0x60409  ldc.i4.s 0x3A
0x6040b  bne.un.s loc_6041D
0x6040d  ldarg.0
0x6040e  ldarg.0
0x6040f  ldfld    int32 System.Xml.DtdParser::curPos
0x60414  ldc.i4.1
0x60415  add
0x60416  stfld    int32 System.Xml.DtdParser::curPos
0x6041b  br.s     loc_60475
0x6041d  ldarg.0
0x6041e  ldfld    int32 System.Xml.DtdParser::curPos
0x60423  ldc.i4.1
0x60424  add
0x60425  ldarg.0
0x60426  ldfld    int32 System.Xml.DtdParser::charsUsed
0x6042b  blt.s    loc_6044D
0x6042d  ldarg.0
0x6042e  call     instance bool System.Xml.DtdParser::ReadDataInName()
0x60433  brtrue.s loc_603DE
0x60435  ldarg.0
0x60436  ldarg.0
0x60437  ldfld    int32 System.Xml.DtdParser::curPos
0x6043c  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x60441  ldstr    aName_0// "Name"
0x60446  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x6044b  br.s     loc_60475
0x6044d  ldarg.0
0x6044e  ldarg.0
0x6044f  ldfld    int32 System.Xml.DtdParser::curPos
0x60454  ldstr    aXmlBadstartnam// "Xml_BadStartNameChar"
0x60459  ldarg.0
0x6045a  ldfld    char[] System.Xml.DtdParser::chars
0x6045f  ldarg.0
0x60460  ldfld    int32 System.Xml.DtdParser::charsUsed
0x60465  ldarg.0
0x60466  ldfld    int32 System.Xml.DtdParser::curPos
0x6046b  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x60470  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string[] args)
0x60475  ldarg.0
0x60476  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x6047b  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x60480  ldarg.0
0x60481  ldfld    char[] System.Xml.DtdParser::chars
0x60486  ldarg.0
0x60487  ldfld    int32 System.Xml.DtdParser::curPos
0x6048c  ldelem.u2
0x6048d  add
0x6048e  ldind.u1
0x6048f  ldc.i4.8
0x60490  and
0x60491  brfalse.s loc_604A3
0x60493  ldarg.0
0x60494  ldarg.0
0x60495  ldfld    int32 System.Xml.DtdParser::curPos
0x6049a  ldc.i4.1
0x6049b  add
0x6049c  stfld    int32 System.Xml.DtdParser::curPos
0x604a1  br.s     loc_60475
0x604a3  ldarg.0
0x604a4  ldfld    char[] System.Xml.DtdParser::chars
0x604a9  ldarg.0
0x604aa  ldfld    int32 System.Xml.DtdParser::curPos
0x604af  ldelem.u2
0x604b0  ldc.i4.s 0x3A
0x604b2  bne.un.s loc_60508
0x604b4  ldarg.1
0x604b5  brfalse.s loc_604F5
0x604b7  ldloc.0
0x604b8  ldc.i4.m1
0x604b9  beq.s    loc_604D4
0x604bb  ldarg.0
0x604bc  ldarg.0
0x604bd  ldfld    int32 System.Xml.DtdParser::curPos
0x604c2  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x604c7  ldc.i4.s 0x3A
0x604c9  ldc.i4.0
0x604ca  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x604cf  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string[] args)
0x604d4  ldarg.0
0x604d5  ldfld    int32 System.Xml.DtdParser::curPos
0x604da  ldarg.0
0x604db  ldfld    int32 System.Xml.DtdParser::tokenStartPos
0x604e0  sub
0x604e1  stloc.0
0x604e2  ldarg.0
0x604e3  ldarg.0
0x604e4  ldfld    int32 System.Xml.DtdParser::curPos
0x604e9  ldc.i4.1
0x604ea  add
0x604eb  stfld    int32 System.Xml.DtdParser::curPos
0x604f0  br       loc_603DE
0x604f5  ldarg.0
0x604f6  ldarg.0
0x604f7  ldfld    int32 System.Xml.DtdParser::curPos
0x604fc  ldc.i4.1
0x604fd  add
0x604fe  stfld    int32 System.Xml.DtdParser::curPos
0x60503  br       loc_60475
0x60508  ldarg.0
0x60509  ldfld    int32 System.Xml.DtdParser::curPos
0x6050e  ldarg.0
0x6050f  ldfld    int32 System.Xml.DtdParser::charsUsed
0x60514  bne.un.s loc_60545
0x60516  ldarg.0
0x60517  call     instance bool System.Xml.DtdParser::ReadDataInName()
0x6051c  brtrue   loc_60475
0x60521  ldarg.0
0x60522  ldfld    int32 System.Xml.DtdParser::tokenStartPos
0x60527  ldarg.0
0x60528  ldfld    int32 System.Xml.DtdParser::curPos
0x6052d  bne.un.s loc_60545
0x6052f  ldarg.0
0x60530  ldarg.0
0x60531  ldfld    int32 System.Xml.DtdParser::curPos
0x60536  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x6053b  ldstr    aName_0// "Name"
0x60540  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x60545  ldarg.0
0x60546  ldloc.0
0x60547  ldc.i4.m1
0x60548  beq.s    loc_60554
0x6054a  ldarg.0
0x6054b  ldfld    int32 System.Xml.DtdParser::tokenStartPos
0x60550  ldloc.0
0x60551  add
0x60552  br.s     loc_60555
0x60554  ldc.i4.m1
0x60555  stfld    int32 System.Xml.DtdParser::colonPos
0x6055a  ret
```
