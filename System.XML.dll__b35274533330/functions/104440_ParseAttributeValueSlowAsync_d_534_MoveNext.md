# <ParseAttributeValueSlowAsync>d__534::MoveNext

- ea: `0x104440`
- end: `0x104ed4`
- name: `<ParseAttributeValueSlowAsync>d__534::MoveNext`
- size: `2708`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config`

## callees

- `0xe360`
- `0xe370`
- `0xf0f0`
- `0xf110`
- `0x12940`
- `0x15c10`
- `0x29700`
- `0x29740`
- `0x298f0`
- `0x2d210`
- `0x2e0a0`
- `0x2e0b0`
- `0x2ff90`
- `0x33200`
- `0x34a60`
- `0x34f90`
- `0xfe500`
- `0xfe510`
- `0xfe920`
- `0xfead0`
- `0xfeb20`
- `0xfeb70`
- `0x104440`

## string_xrefs

- `0x104d74`: `Xml_InternalError`
- `0x104d60`: `Xml_UnclosedQuote`
- `0x104d19`: `Xml_UnexpectedEOF1`
- `0x104736`: `Xml_BadAttributeChar`
- `0x104d50`: `Xml_EntityRefNesting`

## pseudocode

```c

```

## disassembly

```asm
0x104440  ldarg.0
0x104441  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<>1__state
0x104446  stloc.0
0x104447  ldarg.0
0x104448  ldfld    class System.Xml.XmlTextReaderImpl <ParseAttributeValueSlowAsync>d__534::<>4__this
0x10444d  stloc.1
0x10444e  ldloc.0
0x10444f  switch   loc_104817, loc_104968, loc_104A91, loc_104CB3
0x104464  ldarg.0
0x104465  ldarg.0
0x104466  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::curPos
0x10446b  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104470  ldloc.1
0x104471  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104476  ldfld    char[] ParsingState::chars
0x10447b  stloc.2
0x10447c  ldarg.0
0x10447d  ldloc.1
0x10447e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104483  ldfld    int32 ParsingState::entityId
0x104488  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<attributeBaseEntityId>5__3
0x10448d  ldarg.0
0x10448e  ldc.i4.0
0x10448f  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<valueChunkStartPos>5__4
0x104494  ldarg.0
0x104495  ldloc.1
0x104496  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10449b  ldfld    int32 ParsingState::lineNo
0x1044a0  ldloc.1
0x1044a1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1044a6  call     instance int32 ParsingState::get_LinePos()
0x1044ab  newobj   instance void System.Xml.LineInfo::.ctor(int32 lineNo, int32 linePos)
0x1044b0  stfld    valuetype System.Xml.LineInfo <ParseAttributeValueSlowAsync>d__534::<valueChunkLineInfo>5__5
0x1044b5  ldarg.0
0x1044b6  ldnull
0x1044b7  stfld    class NodeData <ParseAttributeValueSlowAsync>d__534::<lastChunk>5__6
0x1044bc  br.s     loc_1044CE
0x1044be  ldarg.0
0x1044bf  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1044c4  stloc.3
0x1044c5  ldarg.0
0x1044c6  ldloc.3
0x1044c7  ldc.i4.1
0x1044c8  add
0x1044c9  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1044ce  ldloc.1
0x1044cf  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x1044d4  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x1044d9  ldloc.2
0x1044da  ldarg.0
0x1044db  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1044e0  ldelem.u2
0x1044e1  add
0x1044e2  ldind.u1
0x1044e3  ldc.i4   0x80
0x1044e8  and
0x1044e9  brtrue.s loc_1044BE
0x1044eb  ldarg.0
0x1044ec  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1044f1  ldloc.1
0x1044f2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1044f7  ldfld    int32 ParsingState::charPos
0x1044fc  sub
0x1044fd  ldc.i4.0
0x1044fe  ble.s    loc_10453B
0x104500  ldloc.1
0x104501  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x104506  ldloc.2
0x104507  ldloc.1
0x104508  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10450d  ldfld    int32 ParsingState::charPos
0x104512  ldarg.0
0x104513  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104518  ldloc.1
0x104519  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10451e  ldfld    int32 ParsingState::charPos
0x104523  sub
0x104524  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x104529  pop
0x10452a  ldloc.1
0x10452b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104530  ldarg.0
0x104531  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104536  stfld    int32 ParsingState::charPos
0x10453b  ldloc.2
0x10453c  ldarg.0
0x10453d  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104542  ldelem.u2
0x104543  ldarg.0
0x104544  ldfld    char <ParseAttributeValueSlowAsync>d__534::quoteChar
0x104549  bne.un.s loc_104561
0x10454b  ldarg.0
0x10454c  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<attributeBaseEntityId>5__3
0x104551  ldloc.1
0x104552  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104557  ldfld    int32 ParsingState::entityId
0x10455c  beq      loc_104DE5
0x104561  ldloc.2
0x104562  ldarg.0
0x104563  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104568  ldelem.u2
0x104569  stloc.s  5
0x10456b  ldloc.s  5
0x10456d  ldc.i4.s 0x26
0x10456f  bgt.un.s loc_1045A6
0x104571  ldloc.s  5
0x104573  ldc.i4.s 9
0x104575  sub
0x104576  switch   loc_1046DC, loc_1045C6, loc_104BE8, loc_104BE8, loc_104610
0x10458f  ldloc.s  5
0x104591  ldc.i4.s 0x22
0x104593  beq      loc_10471A
0x104598  ldloc.s  5
0x10459a  ldc.i4.s 0x26
0x10459c  beq      loc_10474D
0x1045a1  br       loc_104BE8
0x1045a6  ldloc.s  5
0x1045a8  ldc.i4.s 0x27
0x1045aa  beq      loc_10471A
0x1045af  ldloc.s  5
0x1045b1  ldc.i4.s 0x3C
0x1045b3  beq      loc_10472F
0x1045b8  ldloc.s  5
0x1045ba  ldc.i4.s 0x3E
0x1045bc  beq      loc_10471A
0x1045c1  br       loc_104BE8
0x1045c6  ldarg.0
0x1045c7  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1045cc  stloc.3
0x1045cd  ldarg.0
0x1045ce  ldloc.3
0x1045cf  ldc.i4.1
0x1045d0  add
0x1045d1  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1045d6  ldloc.1
0x1045d7  ldarg.0
0x1045d8  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1045dd  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x1045e2  ldloc.1
0x1045e3  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x1045e8  brfalse  loc_1044CE
0x1045ed  ldloc.1
0x1045ee  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x1045f3  ldc.i4.s 0x20
0x1045f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1045fa  pop
0x1045fb  ldloc.1
0x1045fc  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104601  ldflda   int32 ParsingState::charPos
0x104606  dup
0x104607  ldind.i4
0x104608  ldc.i4.1
0x104609  add
0x10460a  stind.i4
0x10460b  br       loc_1044CE
0x104610  ldloc.2
0x104611  ldarg.0
0x104612  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104617  ldc.i4.1
0x104618  add
0x104619  ldelem.u2
0x10461a  ldc.i4.s 0xA
0x10461c  bne.un.s loc_10466F
0x10461e  ldarg.0
0x10461f  ldarg.0
0x104620  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104625  ldc.i4.2
0x104626  add
0x104627  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x10462c  ldloc.1
0x10462d  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x104632  brfalse  loc_1046CB
0x104637  ldloc.1
0x104638  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x10463d  ldloc.1
0x10463e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104643  ldfld    bool ParsingState::eolNormalized
0x104648  brtrue.s loc_104651
0x10464a  ldstr    asc_129382// " "
0x10464f  br.s     loc_104656
0x104651  ldstr    asc_129468// "  "
0x104656  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10465b  pop
0x10465c  ldloc.1
0x10465d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104662  ldarg.0
0x104663  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104668  stfld    int32 ParsingState::charPos
0x10466d  br.s     loc_1046CB
0x10466f  ldarg.0
0x104670  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104675  ldc.i4.1
0x104676  add
0x104677  ldloc.1
0x104678  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10467d  ldfld    int32 ParsingState::charsUsed
0x104682  blt.s    loc_104694
0x104684  ldloc.1
0x104685  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10468a  ldfld    bool ParsingState::isEof
0x10468f  brfalse  loc_104C6F
0x104694  ldarg.0
0x104695  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x10469a  stloc.3
0x10469b  ldarg.0
0x10469c  ldloc.3
0x10469d  ldc.i4.1
0x10469e  add
0x10469f  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1046a4  ldloc.1
0x1046a5  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x1046aa  brfalse.s loc_1046CB
0x1046ac  ldloc.1
0x1046ad  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x1046b2  ldc.i4.s 0x20
0x1046b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1046b9  pop
0x1046ba  ldloc.1
0x1046bb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1046c0  ldarg.0
0x1046c1  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1046c6  stfld    int32 ParsingState::charPos
0x1046cb  ldloc.1
0x1046cc  ldarg.0
0x1046cd  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1046d2  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x1046d7  br       loc_1044CE
0x1046dc  ldarg.0
0x1046dd  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1046e2  stloc.3
0x1046e3  ldarg.0
0x1046e4  ldloc.3
0x1046e5  ldc.i4.1
0x1046e6  add
0x1046e7  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x1046ec  ldloc.1
0x1046ed  ldfld    bool System.Xml.XmlTextReaderImpl::normalize
0x1046f2  brfalse  loc_1044CE
0x1046f7  ldloc.1
0x1046f8  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x1046fd  ldc.i4.s 0x20
0x1046ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x104704  pop
0x104705  ldloc.1
0x104706  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10470b  ldflda   int32 ParsingState::charPos
0x104710  dup
0x104711  ldind.i4
0x104712  ldc.i4.1
0x104713  add
0x104714  stind.i4
0x104715  br       loc_1044CE
0x10471a  ldarg.0
0x10471b  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104720  stloc.3
0x104721  ldarg.0
0x104722  ldloc.3
0x104723  ldc.i4.1
0x104724  add
0x104725  stfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x10472a  br       loc_1044CE
0x10472f  ldloc.1
0x104730  ldarg.0
0x104731  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104736  ldstr    aXmlBadattribut// "Xml_BadAttributeChar"
0x10473b  ldc.i4.s 0x3C
0x10473d  ldc.i4.0
0x10473e  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x104743  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x104748  br       loc_104C6F
0x10474d  ldarg.0
0x10474e  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104753  ldloc.1
0x104754  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104759  ldfld    int32 ParsingState::charPos
0x10475e  sub
0x10475f  ldc.i4.0
0x104760  ble.s    loc_10478C
0x104762  ldloc.1
0x104763  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x104768  ldloc.2
0x104769  ldloc.1
0x10476a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10476f  ldfld    int32 ParsingState::charPos
0x104774  ldarg.0
0x104775  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x10477a  ldloc.1
0x10477b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104780  ldfld    int32 ParsingState::charPos
0x104785  sub
0x104786  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char[], int32, int32)
0x10478b  pop
0x10478c  ldloc.1
0x10478d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x104792  ldarg.0
0x104793  ldfld    int32 <ParseAttributeValueSlowAsync>d__534::<pos>5__2
0x104798  stfld    int32 ParsingState::charPos
0x10479d  ldarg.0
0x10479e  ldloc.1
0x10479f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
  ... truncated ...
```
