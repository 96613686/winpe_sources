# System.Xml.XmlTextReaderImpl::ParseNumericCharRefInline

- ea: `0x2f650`
- end: `0x2f8b9`
- name: `System.Xml.XmlTextReaderImpl::ParseNumericCharRefInline`
- size: `617`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x2f5d0`
- `0x2f600`
- `0x109db0`

## callees

- `0xefc0`
- `0xf0f0`
- `0xf110`
- `0xf170`
- `0x12940`
- `0x29700`
- `0x29720`
- `0x297f0`
- `0x2f650`

## string_xrefs

- `0x2f7cc`: `Xml_InvalidCharacter`
- `0x2f85d`: `Xml_InvalidCharacter`
- `0x2f679`: `Xml_BadHexEntity`
- `0x2f6f0`: `Xml_BadDecimalEntity`
- `0x2f73e`: `Xml_CharEntityOverflow`

## pseudocode

```c

```

## disassembly

```asm
0x2f650  ldc.i4.0
0x2f651  stloc.0
0x2f652  ldnull
0x2f653  stloc.3
0x2f654  ldarg.0
0x2f655  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f65a  ldfld    char[] ParsingState::chars
0x2f65f  stloc.2
0x2f660  ldarg.1
0x2f661  ldc.i4.2
0x2f662  add
0x2f663  stloc.1
0x2f664  ldarg.s  4
0x2f666  ldc.i4.0
0x2f667  stind.i4
0x2f668  ldc.i4.0
0x2f669  stloc.s  4
0x2f66b  ldloc.2
0x2f66c  ldloc.1
0x2f66d  ldelem.u2
0x2f66e  ldc.i4.s 0x78
0x2f670  bne.un.s loc_2F6DF
0x2f672  ldloc.1
0x2f673  ldc.i4.1
0x2f674  add
0x2f675  stloc.1
0x2f676  ldloc.1
0x2f677  stloc.s  4
0x2f679  ldstr    aXmlBadhexentit// "Xml_BadHexEntity"
0x2f67e  stloc.3
0x2f67f  ldloc.2
0x2f680  ldloc.1
0x2f681  ldelem.u2
0x2f682  stloc.s  5
0x2f684  ldloc.s  5
0x2f686  ldc.i4.s 0x30
0x2f688  blt.s    loc_2F69D
0x2f68a  ldloc.s  5
0x2f68c  ldc.i4.s 0x39
0x2f68e  bgt.s    loc_2F69D
0x2f690  ldloc.0
0x2f691  ldc.i4.s 0x10
0x2f693  mul.ovf
0x2f694  ldloc.s  5
0x2f696  add.ovf
0x2f697  ldc.i4.s 0x30
0x2f699  sub.ovf
0x2f69a  stloc.0
0x2f69b  br.s     loc_2F6D3
0x2f69d  ldloc.s  5
0x2f69f  ldc.i4.s 0x61
0x2f6a1  blt.s    loc_2F6B9
0x2f6a3  ldloc.s  5
0x2f6a5  ldc.i4.s 0x66
0x2f6a7  bgt.s    loc_2F6B9
0x2f6a9  ldloc.0
0x2f6aa  ldc.i4.s 0x10
0x2f6ac  mul.ovf
0x2f6ad  ldc.i4.s 0xA
0x2f6af  add.ovf
0x2f6b0  ldloc.s  5
0x2f6b2  add.ovf
0x2f6b3  ldc.i4.s 0x61
0x2f6b5  sub.ovf
0x2f6b6  stloc.0
0x2f6b7  br.s     loc_2F6D3
0x2f6b9  ldloc.s  5
0x2f6bb  ldc.i4.s 0x41
0x2f6bd  blt.s    loc_2F6D9
0x2f6bf  ldloc.s  5
0x2f6c1  ldc.i4.s 0x46
0x2f6c3  bgt.s    loc_2F6D9
0x2f6c5  ldloc.0
0x2f6c6  ldc.i4.s 0x10
0x2f6c8  mul.ovf
0x2f6c9  ldc.i4.s 0xA
0x2f6cb  add.ovf
0x2f6cc  ldloc.s  5
0x2f6ce  add.ovf
0x2f6cf  ldc.i4.s 0x41
0x2f6d1  sub.ovf
0x2f6d2  stloc.0
0x2f6d3  ldloc.1
0x2f6d4  ldc.i4.1
0x2f6d5  add
0x2f6d6  stloc.1
0x2f6d7  br.s     loc_2F67F
0x2f6d9  ldarg.s  5
0x2f6db  ldc.i4.1
0x2f6dc  stind.i4
0x2f6dd  br.s     loc_2F729
0x2f6df  ldloc.1
0x2f6e0  ldarg.0
0x2f6e1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f6e6  ldfld    int32 ParsingState::charsUsed
0x2f6eb  bge.s    loc_2F71C
0x2f6ed  ldloc.1
0x2f6ee  stloc.s  4
0x2f6f0  ldstr    aXmlBaddecimale// "Xml_BadDecimalEntity"
0x2f6f5  stloc.3
0x2f6f6  br.s     loc_2F708
0x2f6f8  ldloc.0
0x2f6f9  ldc.i4.s 0xA
0x2f6fb  mul.ovf
0x2f6fc  ldloc.2
0x2f6fd  ldloc.1
0x2f6fe  ldelem.u2
0x2f6ff  add.ovf
0x2f700  ldc.i4.s 0x30
0x2f702  sub.ovf
0x2f703  stloc.0
0x2f704  ldloc.1
0x2f705  ldc.i4.1
0x2f706  add
0x2f707  stloc.1
0x2f708  ldloc.2
0x2f709  ldloc.1
0x2f70a  ldelem.u2
0x2f70b  ldc.i4.s 0x30
0x2f70d  blt.s    loc_2F716
0x2f70f  ldloc.2
0x2f710  ldloc.1
0x2f711  ldelem.u2
0x2f712  ldc.i4.s 0x39
0x2f714  ble.s    loc_2F6F8
0x2f716  ldarg.s  5
0x2f718  ldc.i4.0
0x2f719  stind.i4
0x2f71a  br.s     loc_2F729
0x2f71c  ldarg.s  5
0x2f71e  ldc.i4.4
0x2f71f  stind.i4
0x2f720  ldc.i4.s 0xFE
0x2f722  stloc.s  6
0x2f724  leave    loc_2F8B6
0x2f729  leave.s  loc_2F74D
0x2f72b  stloc.s  7
0x2f72d  ldarg.0
0x2f72e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f733  ldloc.1
0x2f734  stfld    int32 ParsingState::charPos
0x2f739  ldarg.s  5
0x2f73b  ldc.i4.4
0x2f73c  stind.i4
0x2f73d  ldarg.0
0x2f73e  ldstr    aXmlCharentityo// "Xml_CharEntityOverflow"
0x2f743  ldnull
0x2f744  ldloc.s  7
0x2f746  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, class [mscorlib]System.Exception innerException)
0x2f74b  leave.s  loc_2F74D
0x2f74d  ldloc.2
0x2f74e  ldloc.1
0x2f74f  ldelem.u2
0x2f750  ldc.i4.s 0x3B
0x2f752  bne.un.s loc_2F759
0x2f754  ldloc.s  4
0x2f756  ldloc.1
0x2f757  bne.un.s loc_2F772
0x2f759  ldloc.1
0x2f75a  ldarg.0
0x2f75b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f760  ldfld    int32 ParsingState::charsUsed
0x2f765  bne.un.s loc_2F76A
0x2f767  ldc.i4.s 0xFE
0x2f769  ret
0x2f76a  ldarg.0
0x2f76b  ldloc.1
0x2f76c  ldloc.3
0x2f76d  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x2f772  ldloc.0
0x2f773  ldc.i4   0xFFFF
0x2f778  bgt      loc_2F81D
0x2f77d  ldloc.0
0x2f77e  conv.u2
0x2f77f  stloc.s  8
0x2f781  ldarg.0
0x2f782  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x2f787  ldloc.s  8
0x2f789  call     instance bool System.Xml.XmlCharType::IsCharData(char ch)
0x2f78e  brtrue.s loc_2F7DE
0x2f790  ldarg.0
0x2f791  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x2f796  brfalse.s loc_2F7A0
0x2f798  ldarg.0
0x2f799  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x2f79e  brtrue.s loc_2F7B0
0x2f7a0  ldarg.0
0x2f7a1  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x2f7a6  brtrue.s loc_2F7DE
0x2f7a8  ldarg.0
0x2f7a9  ldfld    bool System.Xml.XmlTextReaderImpl::checkCharacters
0x2f7ae  brfalse.s loc_2F7DE
0x2f7b0  ldarg.0
0x2f7b1  ldarg.0
0x2f7b2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f7b7  ldfld    char[] ParsingState::chars
0x2f7bc  ldarg.1
0x2f7bd  ldc.i4.2
0x2f7be  add
0x2f7bf  ldelem.u2
0x2f7c0  ldc.i4.s 0x78
0x2f7c2  beq.s    loc_2F7C9
0x2f7c4  ldarg.1
0x2f7c5  ldc.i4.2
0x2f7c6  add
0x2f7c7  br.s     loc_2F7CC
0x2f7c9  ldarg.1
0x2f7ca  ldc.i4.3
0x2f7cb  add
0x2f7cc  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x2f7d1  ldloc.s  8
0x2f7d3  ldc.i4.0
0x2f7d4  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x2f7d9  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2f7de  ldarg.2
0x2f7df  brfalse.s loc_2F815
0x2f7e1  ldarg.3
0x2f7e2  brfalse.s loc_2F810
0x2f7e4  ldarg.3
0x2f7e5  ldarg.0
0x2f7e6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f7eb  ldfld    char[] ParsingState::chars
0x2f7f0  ldarg.0
0x2f7f1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f7f6  ldfld    int32 ParsingState::charPos
0x2f7fb  ldloc.1
0x2f7fc  ldarg.0
0x2f7fd  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f802  ldfld    int32 ParsingState::charPos
0x2f807  sub
0x2f808  ldc.i4.1
0x2f809  add
0x2f80a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2f80f  pop
0x2f810  ldloc.2
0x2f811  ldloc.1
0x2f812  ldloc.s  8
0x2f814  stelem.i2
0x2f815  ldarg.s  4
0x2f817  ldc.i4.1
0x2f818  stind.i4
0x2f819  ldloc.1
0x2f81a  ldc.i4.1
0x2f81b  add
0x2f81c  ret
0x2f81d  ldloc.0
0x2f81e  ldloca.s 9
0x2f820  ldloca.s 0xA
0x2f822  call     void System.Xml.XmlCharType::SplitSurrogateChar(int32 combinedChar, [out] char& lowChar, [out] char& highChar)
0x2f827  ldarg.0
0x2f828  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x2f82d  brfalse.s loc_2F870
0x2f82f  ldloc.s  0xA
0x2f831  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x2f836  brfalse.s loc_2F841
0x2f838  ldloc.s  9
0x2f83a  call     bool System.Xml.XmlCharType::IsLowSurrogate(int32 ch)
0x2f83f  brtrue.s loc_2F870
0x2f841  ldarg.0
0x2f842  ldarg.0
0x2f843  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f848  ldfld    char[] ParsingState::chars
0x2f84d  ldarg.1
0x2f84e  ldc.i4.2
0x2f84f  add
0x2f850  ldelem.u2
0x2f851  ldc.i4.s 0x78
0x2f853  beq.s    loc_2F85A
0x2f855  ldarg.1
0x2f856  ldc.i4.2
0x2f857  add
0x2f858  br.s     loc_2F85D
0x2f85a  ldarg.1
0x2f85b  ldc.i4.3
0x2f85c  add
0x2f85d  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x2f862  ldloc.s  0xA
0x2f864  ldloc.s  9
0x2f866  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x2f86b  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x2f870  ldarg.2
0x2f871  brfalse.s loc_2F8AE
0x2f873  ldarg.3
0x2f874  brfalse.s loc_2F8A2
0x2f876  ldarg.3
0x2f877  ldarg.0
0x2f878  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f87d  ldfld    char[] ParsingState::chars
0x2f882  ldarg.0
0x2f883  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f888  ldfld    int32 ParsingState::charPos
0x2f88d  ldloc.1
0x2f88e  ldarg.0
0x2f88f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2f894  ldfld    int32 ParsingState::charPos
0x2f899  sub
0x2f89a  ldc.i4.1
0x2f89b  add
0x2f89c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x2f8a1  pop
  ... truncated ...
```
