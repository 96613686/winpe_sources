# System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync

- ea: `0x33280`
- end: `0x33528`
- name: `System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync`
- size: `680`
- prototype: ``
- caller_count: `6`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x326a0`
- `0x33280`
- `0x33590`
- `0x102960`
- `0x102c70`
- `0x102de0`

## callees

- `0xc9f0`
- `0xcab0`
- `0xcb10`
- `0x10e60`
- `0x29720`
- `0x29740`
- `0x31390`
- `0x313b0`
- `0x31420`
- `0x33280`
- `0x33550`
- `0x33590`
- `0x33620`
- `0x338a0`
- `0x349e0`
- `0x34b10`
- `0x34ba0`
- `0x34be0`
- `0x34c70`

## string_xrefs

- `0x333e8`: `Xml_InvalidRootData`
- `0x33449`: `Xml_BadDTDLocation`
- `0x33472`: `Xml_UnexpectedEndTag`
- `0x33495`: `Xml_MultipleRoots`

## pseudocode

```c

```

## disassembly

```asm
0x33280  ldc.i4.0
0x33281  stloc.0
0x33282  ldarg.0
0x33283  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x33288  ldfld    int32 ParsingState::charPos
0x3328d  stloc.1
0x3328e  ldarg.0
0x3328f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x33294  ldfld    char[] ParsingState::chars
0x33299  stloc.2
0x3329a  ldloc.2
0x3329b  ldloc.1
0x3329c  ldelem.u2
0x3329d  ldc.i4.s 0x3C
0x3329f  bne.un   loc_334CE
0x332a4  ldc.i4.1
0x332a5  stloc.0
0x332a6  ldarg.0
0x332a7  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x332ac  ldfld    int32 ParsingState::charsUsed
0x332b1  ldloc.1
0x332b2  sub
0x332b3  ldc.i4.4
0x332b4  bge.s    loc_332BE
0x332b6  ldarg.0
0x332b7  ldloc.0
0x332b8  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_ReadData(bool needMoreChars)
0x332bd  ret
0x332be  ldloc.1
0x332bf  ldc.i4.1
0x332c0  add
0x332c1  stloc.1
0x332c2  ldloc.2
0x332c3  ldloc.1
0x332c4  ldelem.u2
0x332c5  stloc.3
0x332c6  ldloc.3
0x332c7  ldc.i4.s 0x21
0x332c9  beq.s    loc_33301
0x332cb  ldloc.3
0x332cc  ldc.i4.s 0x2F
0x332ce  beq      loc_3346E
0x332d3  ldloc.3
0x332d4  ldc.i4.s 0x3F
0x332d6  bne.un   loc_33481
0x332db  ldarg.0
0x332dc  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x332e1  ldloc.1
0x332e2  ldc.i4.1
0x332e3  add
0x332e4  stfld    int32 ParsingState::charPos
0x332e9  ldarg.0
0x332ea  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParsePIAsync()
0x332ef  ldarg.0
0x332f0  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync()
0x332f6  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x332fb  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.AsyncHelper::ContinueBoolTaskFuncWhenFalse(class [mscorlib]System.Threading.Tasks.Task`1<bool> task, class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> func)
0x33300  ret
0x33301  ldloc.1
0x33302  ldc.i4.1
0x33303  add
0x33304  stloc.1
0x33305  ldarg.0
0x33306  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x3330b  ldfld    int32 ParsingState::charsUsed
0x33310  ldloc.1
0x33311  sub
0x33312  ldc.i4.2
0x33313  bge.s    loc_3331D
0x33315  ldarg.0
0x33316  ldloc.0
0x33317  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_ReadData(bool needMoreChars)
0x3331c  ret
0x3331d  ldloc.2
0x3331e  ldloc.1
0x3331f  ldelem.u2
0x33320  ldc.i4.s 0x2D
0x33322  bne.un.s loc_33366
0x33324  ldloc.2
0x33325  ldloc.1
0x33326  ldc.i4.1
0x33327  add
0x33328  ldelem.u2
0x33329  ldc.i4.s 0x2D
0x3332b  bne.un.s loc_33353
0x3332d  ldarg.0
0x3332e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x33333  ldloc.1
0x33334  ldc.i4.2
0x33335  add
0x33336  stfld    int32 ParsingState::charPos
0x3333b  ldarg.0
0x3333c  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseCommentAsync()
0x33341  ldarg.0
0x33342  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync()
0x33348  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x3334d  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.AsyncHelper::ContinueBoolTaskFuncWhenFalse(class [mscorlib]System.Threading.Tasks.Task`1<bool> task, class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> func)
0x33352  ret
0x33353  ldarg.0
0x33354  ldloc.1
0x33355  ldc.i4.1
0x33356  add
0x33357  ldstr    asc_12B3DE// "-"
0x3335c  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken)
0x33361  br       System.Xml.XmlTextReaderImpl__ParseDocumentContentAsync
0x33366  ldloc.2
0x33367  ldloc.1
0x33368  ldelem.u2
0x33369  ldc.i4.s 0x5B
0x3336b  bne.un   loc_333F7
0x33370  ldarg.0
0x33371  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x33376  ldc.i4.s 9
0x33378  beq.s    loc_333DC
0x3337a  ldloc.1
0x3337b  ldc.i4.1
0x3337c  add
0x3337d  stloc.1
0x3337e  ldarg.0
0x3337f  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x33384  ldfld    int32 ParsingState::charsUsed
0x33389  ldloc.1
0x3338a  sub
0x3338b  ldc.i4.6
0x3338c  bge.s    loc_33396
0x3338e  ldarg.0
0x3338f  ldloc.0
0x33390  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_ReadData(bool needMoreChars)
0x33395  ret
0x33396  ldloc.2
0x33397  ldloc.1
0x33398  ldc.i4.6
0x33399  ldstr    aCdata// "CDATA["
0x3339e  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x333a3  brfalse.s loc_333CB
0x333a5  ldarg.0
0x333a6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x333ab  ldloc.1
0x333ac  ldc.i4.6
0x333ad  add
0x333ae  stfld    int32 ParsingState::charPos
0x333b3  ldarg.0
0x333b4  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::ParseCDataAsync()
0x333b9  ldarg.0
0x333ba  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_CData()
0x333c0  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x333c5  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.AsyncHelper::CallBoolTaskFuncWhenFinish(class [mscorlib]System.Threading.Tasks.Task task, class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> func)
0x333ca  ret
0x333cb  ldarg.0
0x333cc  ldloc.1
0x333cd  ldstr    aCdata// "CDATA["
0x333d2  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken)
0x333d7  br       System.Xml.XmlTextReaderImpl__ParseDocumentContentAsync
0x333dc  ldarg.0
0x333dd  ldarg.0
0x333de  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x333e3  ldfld    int32 ParsingState::charPos
0x333e8  ldstr    aXmlInvalidroot// "Xml_InvalidRootData"
0x333ed  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x333f2  br       System.Xml.XmlTextReaderImpl__ParseDocumentContentAsync
0x333f7  ldarg.0
0x333f8  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x333fd  ldc.i4.s 9
0x333ff  beq.s    loc_33409
0x33401  ldarg.0
0x33402  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x33407  brtrue.s loc_33435
0x33409  ldarg.0
0x3340a  ldc.i4.s 9
0x3340c  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x33411  ldarg.0
0x33412  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x33417  ldloc.1
0x33418  stfld    int32 ParsingState::charPos
0x3341d  ldarg.0
0x3341e  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDoctypeDeclAsync()
0x33423  ldarg.0
0x33424  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync()
0x3342a  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x3342f  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.AsyncHelper::ContinueBoolTaskFuncWhenFalse(class [mscorlib]System.Threading.Tasks.Task`1<bool> task, class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> func)
0x33434  ret
0x33435  ldarg.0
0x33436  ldloc.1
0x33437  call     instance string System.Xml.XmlTextReaderImpl::ParseUnexpectedToken(int32 pos)
0x3343c  ldstr    aDoctype_0// "DOCTYPE"
0x33441  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33446  brfalse.s loc_33458
0x33448  ldarg.0
0x33449  ldstr    aXmlBaddtdlocat// "Xml_BadDTDLocation"
0x3344e  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x33453  br       System.Xml.XmlTextReaderImpl__ParseDocumentContentAsync
0x33458  ldarg.0
0x33459  ldloc.1
0x3345a  ldstr    asc_12B44E// "<!--"
0x3345f  ldstr    aCdata_0// "<[CDATA["
0x33464  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(int32 pos, string expectedToken1, string expectedToken2)
0x33469  br       System.Xml.XmlTextReaderImpl__ParseDocumentContentAsync
0x3346e  ldarg.0
0x3346f  ldloc.1
0x33470  ldc.i4.1
0x33471  add
0x33472  ldstr    aXmlUnexpectede_1// "Xml_UnexpectedEndTag"
0x33477  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x3347c  br       System.Xml.XmlTextReaderImpl__ParseDocumentContentAsync
0x33481  ldarg.0
0x33482  ldfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x33487  brfalse.s loc_334AE
0x33489  ldarg.0
0x3348a  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x3348f  ldc.i4.s 9
0x33491  bne.un.s loc_3349F
0x33493  ldarg.0
0x33494  ldloc.1
0x33495  ldstr    aXmlMultipleroo// "Xml_MultipleRoots"
0x3349a  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x3349f  ldarg.0
0x334a0  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x334a5  brtrue.s loc_334AE
0x334a7  ldarg.0
0x334a8  ldc.i4.1
0x334a9  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x334ae  ldarg.0
0x334af  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x334b4  ldloc.1
0x334b5  stfld    int32 ParsingState::charPos
0x334ba  ldarg.0
0x334bb  ldc.i4.1
0x334bc  stfld    bool System.Xml.XmlTextReaderImpl::rootElementParsed
0x334c1  ldarg.0
0x334c2  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::ParseElementAsync()
0x334c7  ldc.i4.1
0x334c8  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.AsyncHelper::ReturnTaskBoolWhenFinish(class [mscorlib]System.Threading.Tasks.Task task, bool ret)
0x334cd  ret
0x334ce  ldloc.2
0x334cf  ldloc.1
0x334d0  ldelem.u2
0x334d1  ldc.i4.s 0x26
0x334d3  bne.un.s loc_334DC
0x334d5  ldarg.0
0x334d6  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_ParseEntity()
0x334db  ret
0x334dc  ldloc.1
0x334dd  ldarg.0
0x334de  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x334e3  ldfld    int32 ParsingState::charsUsed
0x334e8  beq.s    loc_334F7
0x334ea  ldarg.0
0x334eb  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x334f0  brfalse.s loc_334FF
0x334f2  ldloc.2
0x334f3  ldloc.1
0x334f4  ldelem.u2
0x334f5  brtrue.s loc_334FF
0x334f7  ldarg.0
0x334f8  ldloc.0
0x334f9  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_ReadData(bool needMoreChars)
0x334fe  ret
0x334ff  ldarg.0
0x33500  ldfld    valuetype System.Xml.XmlNodeType System.Xml.XmlTextReaderImpl::fragmentType
0x33505  ldc.i4.s 9
0x33507  bne.un.s loc_33521
0x33509  ldarg.0
0x3350a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseRootLevelWhitespaceAsync()
0x3350f  ldarg.0
0x33510  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync()
0x33516  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x3351b  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.AsyncHelper::ContinueBoolTaskFuncWhenFalse(class [mscorlib]System.Threading.Tasks.Task`1<bool> task, class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> func)
0x33520  ret
0x33521  ldarg.0
0x33522  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::ParseDocumentContentAsync_WhiteSpace()
0x33527  ret
```
