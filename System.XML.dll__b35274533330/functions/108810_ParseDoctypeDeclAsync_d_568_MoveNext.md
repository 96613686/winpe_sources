# <ParseDoctypeDeclAsync>d__568::MoveNext

- ea: `0x108810`
- end: `0x108b73`
- name: `<ParseDoctypeDeclAsync>d__568::MoveNext`
- size: `867`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0xef40`
- `0x10e60`
- `0x29720`
- `0x29770`
- `0x29890`
- `0x313a0`
- `0x31500`
- `0x33200`
- `0x34cb0`
- `0x34cf0`
- `0x34dd0`
- `0xfe500`
- `0xfe510`
- `0xfeab0`
- `0x108810`

## string_xrefs

- `0x108848`: `Xml_DtdIsProhibitedEx`
- `0x1088c8`: `Xml_UnexpectedEOF`
- `0x10884f`: `Xml_DtdIsProhibited`
- `0x108988`: `Xml_MultipleDTDsProvided`
- `0x1089a8`: `Xml_DtdAfterRootElement`

## pseudocode

```c

```

## disassembly

```asm
0x108810  ldarg.0
0x108811  ldfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108816  stloc.0
0x108817  ldarg.0
0x108818  ldfld    class System.Xml.XmlTextReaderImpl <ParseDoctypeDeclAsync>d__568::<>4__this
0x10881d  stloc.1
0x10881e  ldloc.0
0x10881f  switch   loc_10889F, loc_108A07, loc_108A9D, loc_108B1D
0x108834  ldloc.1
0x108835  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x10883a  brtrue   loc_1088D7
0x10883f  ldloc.1
0x108840  ldloc.1
0x108841  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x108846  brtrue.s loc_10884F
0x108848  ldstr    aXmlDtdisprohib// "Xml_DtdIsProhibitedEx"
0x10884d  br.s     loc_108854
0x10884f  ldstr    aXmlDtdisprohib_0// "Xml_DtdIsProhibited"
0x108854  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res)
0x108859  br.s     loc_1088D7
0x10885b  ldloc.1
0x10885c  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::ReadDataAsync()
0x108861  ldc.i4.0
0x108862  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x108867  stloc.s  5
0x108869  ldloca.s 5
0x10886b  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x108870  stloc.s  4
0x108872  ldloca.s 4
0x108874  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x108879  brtrue.s loc_1088BC
0x10887b  ldarg.0
0x10887c  ldc.i4.0
0x10887d  dup
0x10887e  stloc.0
0x10887f  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108884  ldarg.0
0x108885  ldloc.s  4
0x108887  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseDoctypeDeclAsync>d__568::<>u__1
0x10888c  ldarg.0
0x10888d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseDoctypeDeclAsync>d__568::<>t__builder
0x108892  ldloca.s 4
0x108894  ldarg.0
0x108895  call     T0x2B000213
0x10889a  leave    loc_108B72
0x10889f  ldarg.0
0x1088a0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseDoctypeDeclAsync>d__568::<>u__1
0x1088a5  stloc.s  4
0x1088a7  ldarg.0
0x1088a8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseDoctypeDeclAsync>d__568::<>u__1
0x1088ad  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x1088b3  ldarg.0
0x1088b4  ldc.i4.m1
0x1088b5  dup
0x1088b6  stloc.0
0x1088b7  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x1088bc  ldloca.s 4
0x1088be  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x1088c3  stloc.3
0x1088c4  ldloc.3
0x1088c5  brtrue.s loc_1088D7
0x1088c7  ldloc.1
0x1088c8  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x1088cd  ldstr    aDoctype_0// "DOCTYPE"
0x1088d2  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x1088d7  ldloc.1
0x1088d8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1088dd  ldfld    int32 ParsingState::charsUsed
0x1088e2  ldloc.1
0x1088e3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1088e8  ldfld    int32 ParsingState::charPos
0x1088ed  sub
0x1088ee  ldc.i4.8
0x1088ef  blt      loc_10885B
0x1088f4  ldloc.1
0x1088f5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1088fa  ldfld    char[] ParsingState::chars
0x1088ff  ldloc.1
0x108900  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108905  ldfld    int32 ParsingState::charPos
0x10890a  ldc.i4.7
0x10890b  ldstr    aDoctype_0// "DOCTYPE"
0x108910  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x108915  brtrue.s loc_108939
0x108917  ldloc.1
0x108918  ldloc.1
0x108919  ldfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x10891e  brtrue.s loc_108928
0x108920  ldloc.1
0x108921  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x108926  brfalse.s loc_10892F
0x108928  ldstr    asc_12B44E// "<!--"
0x10892d  br.s     loc_108934
0x10892f  ldstr    aDoctype_0// "DOCTYPE"
0x108934  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x108939  ldloc.1
0x10893a  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x10893f  ldloc.1
0x108940  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108945  ldfld    char[] ParsingState::chars
0x10894a  ldloc.1
0x10894b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108950  ldfld    int32 ParsingState::charPos
0x108955  ldc.i4.7
0x108956  add
0x108957  ldelem.u2
0x108958  call     instance bool System.Xml.XmlCharType::IsWhiteSpace(char ch)
0x10895d  brtrue.s loc_108972
0x10895f  ldloc.1
0x108960  ldloc.1
0x108961  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108966  ldfld    int32 ParsingState::charPos
0x10896b  ldc.i4.7
0x10896c  add
0x10896d  call     instance void System.Xml.XmlTextReaderImpl::ThrowExpectingWhitespace(int32 pos)
0x108972  ldloc.1
0x108973  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x108978  brfalse.s loc_108992
0x10897a  ldloc.1
0x10897b  ldloc.1
0x10897c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108981  ldfld    int32 ParsingState::charPos
0x108986  ldc.i4.2
0x108987  sub
0x108988  ldstr    aXmlMultipledtd// "Xml_MultipleDTDsProvided"
0x10898d  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x108992  ldloc.1
0x108993  ldfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x108998  brfalse.s loc_1089B2
0x10899a  ldloc.1
0x10899b  ldloc.1
0x10899c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1089a1  ldfld    int32 ParsingState::charPos
0x1089a6  ldc.i4.2
0x1089a7  sub
0x1089a8  ldstr    aXmlDtdafterroo// "Xml_DtdAfterRootElement"
0x1089ad  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x1089b2  ldloc.1
0x1089b3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1089b8  ldflda   int32 ParsingState::charPos
0x1089bd  dup
0x1089be  ldind.i4
0x1089bf  ldc.i4.8
0x1089c0  add
0x1089c1  stind.i4
0x1089c2  ldloc.1
0x1089c3  ldnull
0x1089c4  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::EatWhitespacesAsync(class [mscorlib]System.Text.StringBuilder sb)
0x1089c9  ldc.i4.0
0x1089ca  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x1089cf  stloc.s  5
0x1089d1  ldloca.s 5
0x1089d3  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x1089d8  stloc.s  6
0x1089da  ldloca.s 6
0x1089dc  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x1089e1  brtrue.s loc_108A24
0x1089e3  ldarg.0
0x1089e4  ldc.i4.1
0x1089e5  dup
0x1089e6  stloc.0
0x1089e7  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x1089ec  ldarg.0
0x1089ed  ldloc.s  6
0x1089ef  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseDoctypeDeclAsync>d__568::<>u__1
0x1089f4  ldarg.0
0x1089f5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseDoctypeDeclAsync>d__568::<>t__builder
0x1089fa  ldloca.s 6
0x1089fc  ldarg.0
0x1089fd  call     T0x2B000213
0x108a02  leave    loc_108B72
0x108a07  ldarg.0
0x108a08  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseDoctypeDeclAsync>d__568::<>u__1
0x108a0d  stloc.s  6
0x108a0f  ldarg.0
0x108a10  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseDoctypeDeclAsync>d__568::<>u__1
0x108a15  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x108a1b  ldarg.0
0x108a1c  ldc.i4.m1
0x108a1d  dup
0x108a1e  stloc.0
0x108a1f  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108a24  ldloca.s 6
0x108a26  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x108a2b  pop
0x108a2c  ldloc.1
0x108a2d  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x108a32  ldc.i4.2
0x108a33  bne.un   loc_108ADC
0x108a38  ldloc.1
0x108a39  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x108a3e  ldloc.1
0x108a3f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108a44  call     instance int32 ParsingState::get_LineNo()
0x108a49  ldloc.1
0x108a4a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108a4f  call     instance int32 ParsingState::get_LinePos()
0x108a54  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x108a59  ldloc.1
0x108a5a  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::ParseDtdAsync()
0x108a5f  ldc.i4.0
0x108a60  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x108a65  stloc.s  8
0x108a67  ldloca.s 8
0x108a69  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x108a6e  stloc.s  7
0x108a70  ldloca.s 7
0x108a72  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x108a77  brtrue.s loc_108ABA
0x108a79  ldarg.0
0x108a7a  ldc.i4.2
0x108a7b  dup
0x108a7c  stloc.0
0x108a7d  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108a82  ldarg.0
0x108a83  ldloc.s  7
0x108a85  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseDoctypeDeclAsync>d__568::<>u__2
0x108a8a  ldarg.0
0x108a8b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseDoctypeDeclAsync>d__568::<>t__builder
0x108a90  ldloca.s 7
0x108a92  ldarg.0
0x108a93  call     T0x2B000214
0x108a98  leave    loc_108B72
0x108a9d  ldarg.0
0x108a9e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseDoctypeDeclAsync>d__568::<>u__2
0x108aa3  stloc.s  7
0x108aa5  ldarg.0
0x108aa6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseDoctypeDeclAsync>d__568::<>u__2
0x108aab  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x108ab1  ldarg.0
0x108ab2  ldc.i4.m1
0x108ab3  dup
0x108ab4  stloc.0
0x108ab5  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108aba  ldloca.s 7
0x108abc  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x108ac1  ldloc.1
0x108ac2  ldloc.1
0x108ac3  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x108ac8  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x108acd  ldloc.1
0x108ace  ldc.i4.s 9
0x108ad0  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x108ad5  ldc.i4.1
0x108ad6  stloc.2
0x108ad7  leave    loc_108B5E
0x108adc  ldloc.1
0x108add  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::SkipDtdAsync()
0x108ae2  ldc.i4.0
0x108ae3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x108ae8  stloc.s  8
0x108aea  ldloca.s 8
0x108aec  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x108af1  stloc.s  9
0x108af3  ldloca.s 9
0x108af5  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x108afa  brtrue.s loc_108B3A
0x108afc  ldarg.0
0x108afd  ldc.i4.3
0x108afe  dup
0x108aff  stloc.0
0x108b00  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108b05  ldarg.0
0x108b06  ldloc.s  9
0x108b08  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseDoctypeDeclAsync>d__568::<>u__2
0x108b0d  ldarg.0
0x108b0e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseDoctypeDeclAsync>d__568::<>t__builder
0x108b13  ldloca.s 9
0x108b15  ldarg.0
0x108b16  call     T0x2B000214
0x108b1b  leave.s  loc_108B72
0x108b1d  ldarg.0
0x108b1e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseDoctypeDeclAsync>d__568::<>u__2
0x108b23  stloc.s  9
0x108b25  ldarg.0
0x108b26  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseDoctypeDeclAsync>d__568::<>u__2
0x108b2b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x108b31  ldarg.0
0x108b32  ldc.i4.m1
0x108b33  dup
0x108b34  stloc.0
0x108b35  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108b3a  ldloca.s 9
0x108b3c  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x108b41  ldc.i4.0
0x108b42  stloc.2
0x108b43  leave.s  loc_108B5E
0x108b45  stloc.s  0xA
0x108b47  ldarg.0
0x108b48  ldc.i4.s 0xFE
0x108b4a  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108b4f  ldarg.0
0x108b50  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseDoctypeDeclAsync>d__568::<>t__builder
0x108b55  ldloc.s  0xA
0x108b57  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x108b5c  leave.s  loc_108B72
0x108b5e  ldarg.0
0x108b5f  ldc.i4.s 0xFE
0x108b61  stfld    int32 <ParseDoctypeDeclAsync>d__568::<>1__state
0x108b66  ldarg.0
  ... truncated ...
```
