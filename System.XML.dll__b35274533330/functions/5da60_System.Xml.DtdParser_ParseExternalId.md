# System.Xml.DtdParser::ParseExternalId

- ea: `0x5da60`
- end: `0x5dc88`
- name: `System.Xml.DtdParser::ParseExternalId`
- size: `552`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x5c700`
- `0x5d520`
- `0x5d700`

## callees

- `0xe360`
- `0xf280`
- `0x15e90`
- `0x15ea0`
- `0x5da60`
- `0x5dc90`
- `0x608b0`
- `0x60d60`
- `0x60d70`
- `0x60e40`
- `0x60e90`
- `0x60ed0`
- `0x60f20`

## string_xrefs

- `0x5dbb1`: `Xml_ExpectingWhiteSpace`
- `0x5dc37`: `Xml_ExpectingWhiteSpace`
- `0x5dacd`: `Xml_FragmentId`

## pseudocode

```c

```

## disassembly

```asm
0x5da60  ldloca.s 0
0x5da62  ldarg.0
0x5da63  call     instance int32 System.Xml.DtdParser::get_LineNo()
0x5da68  ldarg.0
0x5da69  call     instance int32 System.Xml.DtdParser::get_LinePos()
0x5da6e  ldc.i4.6
0x5da6f  sub
0x5da70  call     instance void System.Xml.LineInfo::.ctor(int32 lineNo, int32 linePos)
0x5da75  ldarg.3
0x5da76  ldnull
0x5da77  stind.ref
0x5da78  ldarg.s  4
0x5da7a  ldnull
0x5da7b  stind.ref
0x5da7c  ldarg.0
0x5da7d  ldc.i4.1
0x5da7e  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5da83  ldc.i4.s 0x23
0x5da85  beq.s    loc_5DA9D
0x5da87  ldarg.0
0x5da88  ldarg.0
0x5da89  ldfld    int32 System.Xml.DtdParser::curPos
0x5da8e  ldstr    asc_12B35A// "\""
0x5da93  ldstr    asc_12B35E// "'"
0x5da98  call     instance void System.Xml.DtdParser::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x5da9d  ldarg.1
0x5da9e  ldc.i4.s 0x22
0x5daa0  bne.un   loc_5DB31
0x5daa5  ldarg.s  4
0x5daa7  ldarg.0
0x5daa8  call     instance string System.Xml.DtdParser::GetValue()
0x5daad  stind.ref
0x5daae  ldarg.s  4
0x5dab0  ldind.ref
0x5dab1  ldc.i4.s 0x23
0x5dab3  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x5dab8  ldc.i4.0
0x5dab9  blt.s    loc_5DAF8
0x5dabb  ldarg.0
0x5dabc  ldarg.0
0x5dabd  ldfld    int32 System.Xml.DtdParser::curPos
0x5dac2  ldarg.s  4
0x5dac4  ldind.ref
0x5dac5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5daca  sub
0x5dacb  ldc.i4.1
0x5dacc  sub
0x5dacd  ldstr    aXmlFragmentid// "Xml_FragmentId"
0x5dad2  ldc.i4.2
0x5dad3  newarr   [mscorlib]System.String
0x5dad8  dup
0x5dad9  ldc.i4.0
0x5dada  ldarg.s  4
0x5dadc  ldind.ref
0x5dadd  ldarg.s  4
0x5dadf  ldind.ref
0x5dae0  ldc.i4.s 0x23
0x5dae2  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x5dae7  callvirt instance string [mscorlib]System.String::Substring(int32)
0x5daec  stelem.ref
0x5daed  dup
0x5daee  ldc.i4.1
0x5daef  ldarg.s  4
0x5daf1  ldind.ref
0x5daf2  stelem.ref
0x5daf3  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string[] args)
0x5daf8  ldarg.2
0x5daf9  ldc.i4.s 0x24
0x5dafb  bne.un   loc_5DC87
0x5db00  ldarg.0
0x5db01  ldfld    bool System.Xml.DtdParser::freeFloatingDtd
0x5db06  brtrue   loc_5DC87
0x5db0b  ldarg.0
0x5db0c  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5db11  ldflda   int32 System.Xml.LineInfo::linePos
0x5db16  dup
0x5db17  ldind.i4
0x5db18  ldc.i4.1
0x5db19  add
0x5db1a  stind.i4
0x5db1b  ldarg.0
0x5db1c  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x5db21  ldarg.s  4
0x5db23  ldind.ref
0x5db24  ldloc.0
0x5db25  ldarg.0
0x5db26  ldfld    valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5db2b  callvirt instance void System.Xml.IDtdParserAdapter::OnSystemId(string systemId, valuetype System.Xml.LineInfo keywordLineInfo, valuetype System.Xml.LineInfo systemLiteralLineInfo)
0x5db30  ret
0x5db31  ldarg.3
0x5db32  ldarg.0
0x5db33  call     instance string System.Xml.DtdParser::GetValue()
0x5db38  stind.ref
0x5db39  ldarg.0
0x5db3a  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x5db3f  ldarg.3
0x5db40  ldind.ref
0x5db41  call     instance int32 System.Xml.XmlCharType::IsPublicId(string str)
0x5db46  dup
0x5db47  stloc.1
0x5db48  ldc.i4.0
0x5db49  blt.s    loc_5DB66
0x5db4b  ldarg.0
0x5db4c  ldarg.0
0x5db4d  ldfld    int32 System.Xml.DtdParser::curPos
0x5db52  ldc.i4.1
0x5db53  sub
0x5db54  ldarg.3
0x5db55  ldind.ref
0x5db56  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5db5b  sub
0x5db5c  ldloc.1
0x5db5d  add
0x5db5e  ldarg.3
0x5db5f  ldind.ref
0x5db60  ldloc.1
0x5db61  call     instance void System.Xml.DtdParser::ThrowInvalidChar(int32 pos, string data, int32 invCharPos)
0x5db66  ldarg.2
0x5db67  ldc.i4.s 0x24
0x5db69  bne.un   loc_5DC23
0x5db6e  ldarg.0
0x5db6f  ldfld    bool System.Xml.DtdParser::freeFloatingDtd
0x5db74  brtrue   loc_5DC23
0x5db79  ldarg.0
0x5db7a  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5db7f  ldflda   int32 System.Xml.LineInfo::linePos
0x5db84  dup
0x5db85  ldind.i4
0x5db86  ldc.i4.1
0x5db87  add
0x5db88  stind.i4
0x5db89  ldarg.0
0x5db8a  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x5db8f  ldarg.3
0x5db90  ldind.ref
0x5db91  ldloc.0
0x5db92  ldarg.0
0x5db93  ldfld    valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5db98  callvirt instance void System.Xml.IDtdParserAdapter::OnPublicId(string publicId, valuetype System.Xml.LineInfo keywordLineInfo, valuetype System.Xml.LineInfo publicLiteralLineInfo)
0x5db9d  ldarg.0
0x5db9e  ldc.i4.0
0x5db9f  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5dba4  ldc.i4.s 0x23
0x5dba6  bne.un.s loc_5DC0C
0x5dba8  ldarg.0
0x5dba9  ldfld    bool System.Xml.DtdParser::whitespaceSeen
0x5dbae  brtrue.s loc_5DBDD
0x5dbb0  ldarg.0
0x5dbb1  ldstr    aXmlExpectingwh// "Xml_ExpectingWhiteSpace"
0x5dbb6  ldarg.0
0x5dbb7  ldfld    char System.Xml.DtdParser::literalQuoteChar
0x5dbbc  ldc.i4.1
0x5dbbd  newobj   instance void [mscorlib]System.String::.ctor(char, int32)
0x5dbc2  ldarg.0
0x5dbc3  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5dbc8  ldfld    int32 System.Xml.LineInfo::lineNo
0x5dbcd  ldarg.0
0x5dbce  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5dbd3  ldfld    int32 System.Xml.LineInfo::linePos
0x5dbd8  call     instance void System.Xml.DtdParser::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x5dbdd  ldarg.s  4
0x5dbdf  ldarg.0
0x5dbe0  call     instance string System.Xml.DtdParser::GetValue()
0x5dbe5  stind.ref
0x5dbe6  ldarg.0
0x5dbe7  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5dbec  ldflda   int32 System.Xml.LineInfo::linePos
0x5dbf1  dup
0x5dbf2  ldind.i4
0x5dbf3  ldc.i4.1
0x5dbf4  add
0x5dbf5  stind.i4
0x5dbf6  ldarg.0
0x5dbf7  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x5dbfc  ldarg.s  4
0x5dbfe  ldind.ref
0x5dbff  ldloc.0
0x5dc00  ldarg.0
0x5dc01  ldfld    valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5dc06  callvirt instance void System.Xml.IDtdParserAdapter::OnSystemId(string systemId, valuetype System.Xml.LineInfo keywordLineInfo, valuetype System.Xml.LineInfo systemLiteralLineInfo)
0x5dc0b  ret
0x5dc0c  ldarg.0
0x5dc0d  ldarg.0
0x5dc0e  ldfld    int32 System.Xml.DtdParser::curPos
0x5dc13  ldstr    asc_12B35A// "\""
0x5dc18  ldstr    asc_12B35E// "'"
0x5dc1d  call     instance void System.Xml.DtdParser::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x5dc22  ret
0x5dc23  ldarg.0
0x5dc24  ldc.i4.0
0x5dc25  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5dc2a  ldc.i4.s 0x23
0x5dc2c  bne.un.s loc_5DC6D
0x5dc2e  ldarg.0
0x5dc2f  ldfld    bool System.Xml.DtdParser::whitespaceSeen
0x5dc34  brtrue.s loc_5DC63
0x5dc36  ldarg.0
0x5dc37  ldstr    aXmlExpectingwh// "Xml_ExpectingWhiteSpace"
0x5dc3c  ldarg.0
0x5dc3d  ldfld    char System.Xml.DtdParser::literalQuoteChar
0x5dc42  ldc.i4.1
0x5dc43  newobj   instance void [mscorlib]System.String::.ctor(char, int32)
0x5dc48  ldarg.0
0x5dc49  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5dc4e  ldfld    int32 System.Xml.LineInfo::lineNo
0x5dc53  ldarg.0
0x5dc54  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x5dc59  ldfld    int32 System.Xml.LineInfo::linePos
0x5dc5e  call     instance void System.Xml.DtdParser::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x5dc63  ldarg.s  4
0x5dc65  ldarg.0
0x5dc66  call     instance string System.Xml.DtdParser::GetValue()
0x5dc6b  stind.ref
0x5dc6c  ret
0x5dc6d  ldarg.2
0x5dc6e  ldc.i4.8
0x5dc6f  beq.s    loc_5DC87
0x5dc71  ldarg.0
0x5dc72  ldarg.0
0x5dc73  ldfld    int32 System.Xml.DtdParser::curPos
0x5dc78  ldstr    asc_12B35A// "\""
0x5dc7d  ldstr    asc_12B35E// "'"
0x5dc82  call     instance void System.Xml.DtdParser::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x5dc87  ret
```
