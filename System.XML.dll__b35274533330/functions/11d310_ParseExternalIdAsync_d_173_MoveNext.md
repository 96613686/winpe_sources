# <ParseExternalIdAsync>d__173::MoveNext

- ea: `0x11d310`
- end: `0x11d759`
- name: `<ParseExternalIdAsync>d__173::MoveNext`
- size: `1097`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0xe360`
- `0xf280`
- `0x15e90`
- `0x15ea0`
- `0x608b0`
- `0x60d60`
- `0x60d70`
- `0x60e40`
- `0x60e90`
- `0x60ed0`
- `0x60f20`
- `0x61650`
- `0x11d310`

## string_xrefs

- `0x11d5a1`: `Xml_ExpectingWhiteSpace`
- `0x11d6a0`: `Xml_ExpectingWhiteSpace`
- `0x11d41c`: `Xml_FragmentId`

## pseudocode

```c

```

## disassembly

```asm
0x11d310  ldarg.0
0x11d311  ldfld    int32 <ParseExternalIdAsync>d__173::<>1__state
0x11d316  stloc.0
0x11d317  ldarg.0
0x11d318  ldfld    class System.Xml.DtdParser <ParseExternalIdAsync>d__173::<>4__this
0x11d31d  stloc.1
0x11d31e  ldloc.0
0x11d31f  switch   loc_11D39C, loc_11D56C, loc_11D66B
0x11d330  ldarg.0
0x11d331  ldloc.1
0x11d332  call     instance int32 System.Xml.DtdParser::get_LineNo()
0x11d337  ldloc.1
0x11d338  call     instance int32 System.Xml.DtdParser::get_LinePos()
0x11d33d  ldc.i4.6
0x11d33e  sub
0x11d33f  newobj   instance void System.Xml.LineInfo::.ctor(int32 lineNo, int32 linePos)
0x11d344  stfld    valuetype System.Xml.LineInfo <ParseExternalIdAsync>d__173::<keywordLineInfo>5__4
0x11d349  ldarg.0
0x11d34a  ldnull
0x11d34b  stfld    string <ParseExternalIdAsync>d__173::<publicId>5__2
0x11d350  ldarg.0
0x11d351  ldnull
0x11d352  stfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d357  ldloc.1
0x11d358  ldc.i4.1
0x11d359  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::GetTokenAsync(bool needWhiteSpace)
0x11d35e  ldc.i4.0
0x11d35f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11d364  stloc.s  6
0x11d366  ldloca.s 6
0x11d368  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11d36d  stloc.s  5
0x11d36f  ldloca.s 5
0x11d371  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11d376  brtrue.s loc_11D3B9
0x11d378  ldarg.0
0x11d379  ldc.i4.0
0x11d37a  dup
0x11d37b  stloc.0
0x11d37c  stfld    int32 <ParseExternalIdAsync>d__173::<>1__state
0x11d381  ldarg.0
0x11d382  ldloc.s  5
0x11d384  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d389  ldarg.0
0x11d38a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<string, string>> <ParseExternalIdAsync>d__173::<>t__builder
0x11d38f  ldloca.s 5
0x11d391  ldarg.0
0x11d392  call     T0x2B0002BA
0x11d397  leave    loc_11D758
0x11d39c  ldarg.0
0x11d39d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d3a2  stloc.s  5
0x11d3a4  ldarg.0
0x11d3a5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d3aa  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11d3b0  ldarg.0
0x11d3b1  ldc.i4.m1
0x11d3b2  dup
0x11d3b3  stloc.0
0x11d3b4  stfld    int32 <ParseExternalIdAsync>d__173::<>1__state
0x11d3b9  ldloca.s 5
0x11d3bb  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11d3c0  stloc.s  4
0x11d3c2  ldloc.s  4
0x11d3c4  ldc.i4.s 0x23
0x11d3c6  beq.s    loc_11D3DE
0x11d3c8  ldloc.1
0x11d3c9  ldloc.1
0x11d3ca  ldfld    int32 System.Xml.DtdParser::curPos
0x11d3cf  ldstr    asc_12B35A// "\""
0x11d3d4  ldstr    asc_12B35E// "'"
0x11d3d9  call     instance void System.Xml.DtdParser::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x11d3de  ldarg.0
0x11d3df  ldfld    valuetype Token <ParseExternalIdAsync>d__173::idTokenType
0x11d3e4  ldc.i4.s 0x22
0x11d3e6  bne.un   loc_11D49A
0x11d3eb  ldarg.0
0x11d3ec  ldloc.1
0x11d3ed  call     instance string System.Xml.DtdParser::GetValue()
0x11d3f2  stfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d3f7  ldarg.0
0x11d3f8  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d3fd  ldc.i4.s 0x23
0x11d3ff  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x11d404  ldc.i4.0
0x11d405  blt.s    loc_11D450
0x11d407  ldloc.1
0x11d408  ldloc.1
0x11d409  ldfld    int32 System.Xml.DtdParser::curPos
0x11d40e  ldarg.0
0x11d40f  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d414  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11d419  sub
0x11d41a  ldc.i4.1
0x11d41b  sub
0x11d41c  ldstr    aXmlFragmentid// "Xml_FragmentId"
0x11d421  ldc.i4.2
0x11d422  newarr   [mscorlib]System.String
0x11d427  dup
0x11d428  ldc.i4.0
0x11d429  ldarg.0
0x11d42a  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d42f  ldarg.0
0x11d430  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d435  ldc.i4.s 0x23
0x11d437  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x11d43c  callvirt instance string [mscorlib]System.String::Substring(int32)
0x11d441  stelem.ref
0x11d442  dup
0x11d443  ldc.i4.1
0x11d444  ldarg.0
0x11d445  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d44a  stelem.ref
0x11d44b  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string[] args)
0x11d450  ldarg.0
0x11d451  ldfld    valuetype Token <ParseExternalIdAsync>d__173::declType
0x11d456  ldc.i4.s 0x24
0x11d458  bne.un   loc_11D6F9
0x11d45d  ldloc.1
0x11d45e  ldfld    bool System.Xml.DtdParser::freeFloatingDtd
0x11d463  brtrue   loc_11D6F9
0x11d468  ldloc.1
0x11d469  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d46e  ldflda   int32 System.Xml.LineInfo::linePos
0x11d473  dup
0x11d474  ldind.i4
0x11d475  ldc.i4.1
0x11d476  add
0x11d477  stind.i4
0x11d478  ldloc.1
0x11d479  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d47e  ldarg.0
0x11d47f  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d484  ldarg.0
0x11d485  ldfld    valuetype System.Xml.LineInfo <ParseExternalIdAsync>d__173::<keywordLineInfo>5__4
0x11d48a  ldloc.1
0x11d48b  ldfld    valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d490  callvirt instance void System.Xml.IDtdParserAdapter::OnSystemId(string systemId, valuetype System.Xml.LineInfo keywordLineInfo, valuetype System.Xml.LineInfo systemLiteralLineInfo)
0x11d495  br       loc_11D6F9
0x11d49a  ldarg.0
0x11d49b  ldloc.1
0x11d49c  call     instance string System.Xml.DtdParser::GetValue()
0x11d4a1  stfld    string <ParseExternalIdAsync>d__173::<publicId>5__2
0x11d4a6  ldloc.1
0x11d4a7  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x11d4ac  ldarg.0
0x11d4ad  ldfld    string <ParseExternalIdAsync>d__173::<publicId>5__2
0x11d4b2  call     instance int32 System.Xml.XmlCharType::IsPublicId(string str)
0x11d4b7  dup
0x11d4b8  stloc.s  7
0x11d4ba  ldc.i4.0
0x11d4bb  blt.s    loc_11D4E2
0x11d4bd  ldloc.1
0x11d4be  ldloc.1
0x11d4bf  ldfld    int32 System.Xml.DtdParser::curPos
0x11d4c4  ldc.i4.1
0x11d4c5  sub
0x11d4c6  ldarg.0
0x11d4c7  ldfld    string <ParseExternalIdAsync>d__173::<publicId>5__2
0x11d4cc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11d4d1  sub
0x11d4d2  ldloc.s  7
0x11d4d4  add
0x11d4d5  ldarg.0
0x11d4d6  ldfld    string <ParseExternalIdAsync>d__173::<publicId>5__2
0x11d4db  ldloc.s  7
0x11d4dd  call     instance void System.Xml.DtdParser::ThrowInvalidChar(int32 pos, string data, int32 invCharPos)
0x11d4e2  ldarg.0
0x11d4e3  ldfld    valuetype Token <ParseExternalIdAsync>d__173::declType
0x11d4e8  ldc.i4.s 0x24
0x11d4ea  bne.un   loc_11D626
0x11d4ef  ldloc.1
0x11d4f0  ldfld    bool System.Xml.DtdParser::freeFloatingDtd
0x11d4f5  brtrue   loc_11D626
0x11d4fa  ldloc.1
0x11d4fb  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d500  ldflda   int32 System.Xml.LineInfo::linePos
0x11d505  dup
0x11d506  ldind.i4
0x11d507  ldc.i4.1
0x11d508  add
0x11d509  stind.i4
0x11d50a  ldloc.1
0x11d50b  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d510  ldarg.0
0x11d511  ldfld    string <ParseExternalIdAsync>d__173::<publicId>5__2
0x11d516  ldarg.0
0x11d517  ldfld    valuetype System.Xml.LineInfo <ParseExternalIdAsync>d__173::<keywordLineInfo>5__4
0x11d51c  ldloc.1
0x11d51d  ldfld    valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d522  callvirt instance void System.Xml.IDtdParserAdapter::OnPublicId(string publicId, valuetype System.Xml.LineInfo keywordLineInfo, valuetype System.Xml.LineInfo publicLiteralLineInfo)
0x11d527  ldloc.1
0x11d528  ldc.i4.0
0x11d529  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::GetTokenAsync(bool needWhiteSpace)
0x11d52e  ldc.i4.0
0x11d52f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11d534  stloc.s  6
0x11d536  ldloca.s 6
0x11d538  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11d53d  stloc.s  9
0x11d53f  ldloca.s 9
0x11d541  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11d546  brtrue.s loc_11D589
0x11d548  ldarg.0
0x11d549  ldc.i4.1
0x11d54a  dup
0x11d54b  stloc.0
0x11d54c  stfld    int32 <ParseExternalIdAsync>d__173::<>1__state
0x11d551  ldarg.0
0x11d552  ldloc.s  9
0x11d554  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d559  ldarg.0
0x11d55a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<string, string>> <ParseExternalIdAsync>d__173::<>t__builder
0x11d55f  ldloca.s 9
0x11d561  ldarg.0
0x11d562  call     T0x2B0002BA
0x11d567  leave    loc_11D758
0x11d56c  ldarg.0
0x11d56d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d572  stloc.s  9
0x11d574  ldarg.0
0x11d575  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d57a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11d580  ldarg.0
0x11d581  ldc.i4.m1
0x11d582  dup
0x11d583  stloc.0
0x11d584  stfld    int32 <ParseExternalIdAsync>d__173::<>1__state
0x11d589  ldloca.s 9
0x11d58b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11d590  stloc.s  8
0x11d592  ldloc.s  8
0x11d594  ldc.i4.s 0x23
0x11d596  bne.un.s loc_11D60B
0x11d598  ldloc.1
0x11d599  ldfld    bool System.Xml.DtdParser::whitespaceSeen
0x11d59e  brtrue.s loc_11D5CD
0x11d5a0  ldloc.1
0x11d5a1  ldstr    aXmlExpectingwh// "Xml_ExpectingWhiteSpace"
0x11d5a6  ldloc.1
0x11d5a7  ldfld    char System.Xml.DtdParser::literalQuoteChar
0x11d5ac  ldc.i4.1
0x11d5ad  newobj   instance void [mscorlib]System.String::.ctor(char, int32)
0x11d5b2  ldloc.1
0x11d5b3  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d5b8  ldfld    int32 System.Xml.LineInfo::lineNo
0x11d5bd  ldloc.1
0x11d5be  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d5c3  ldfld    int32 System.Xml.LineInfo::linePos
0x11d5c8  call     instance void System.Xml.DtdParser::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x11d5cd  ldarg.0
0x11d5ce  ldloc.1
0x11d5cf  call     instance string System.Xml.DtdParser::GetValue()
0x11d5d4  stfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d5d9  ldloc.1
0x11d5da  ldflda   valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d5df  ldflda   int32 System.Xml.LineInfo::linePos
0x11d5e4  dup
0x11d5e5  ldind.i4
0x11d5e6  ldc.i4.1
0x11d5e7  add
0x11d5e8  stind.i4
0x11d5e9  ldloc.1
0x11d5ea  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d5ef  ldarg.0
0x11d5f0  ldfld    string <ParseExternalIdAsync>d__173::<systemId>5__3
0x11d5f5  ldarg.0
0x11d5f6  ldfld    valuetype System.Xml.LineInfo <ParseExternalIdAsync>d__173::<keywordLineInfo>5__4
0x11d5fb  ldloc.1
0x11d5fc  ldfld    valuetype System.Xml.LineInfo System.Xml.DtdParser::literalLineInfo
0x11d601  callvirt instance void System.Xml.IDtdParserAdapter::OnSystemId(string systemId, valuetype System.Xml.LineInfo keywordLineInfo, valuetype System.Xml.LineInfo systemLiteralLineInfo)
0x11d606  br       loc_11D6F9
0x11d60b  ldloc.1
0x11d60c  ldloc.1
0x11d60d  ldfld    int32 System.Xml.DtdParser::curPos
0x11d612  ldstr    asc_12B35A// "\""
0x11d617  ldstr    asc_12B35E// "'"
0x11d61c  call     instance void System.Xml.DtdParser::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x11d621  br       loc_11D6F9
0x11d626  ldloc.1
0x11d627  ldc.i4.0
0x11d628  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::GetTokenAsync(bool needWhiteSpace)
0x11d62d  ldc.i4.0
0x11d62e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11d633  stloc.s  6
0x11d635  ldloca.s 6
0x11d637  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11d63c  stloc.s  0xB
0x11d63e  ldloca.s 0xB
0x11d640  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11d645  brtrue.s loc_11D688
0x11d647  ldarg.0
0x11d648  ldc.i4.2
0x11d649  dup
0x11d64a  stloc.0
0x11d64b  stfld    int32 <ParseExternalIdAsync>d__173::<>1__state
0x11d650  ldarg.0
0x11d651  ldloc.s  0xB
0x11d653  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseExternalIdAsync>d__173::<>u__1
0x11d658  ldarg.0
  ... truncated ...
```
