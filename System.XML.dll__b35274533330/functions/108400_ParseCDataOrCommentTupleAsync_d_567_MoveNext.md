# <ParseCDataOrCommentTupleAsync>d__567::MoveNext

- ea: `0x108400`
- end: `0x1087e2`
- name: `<ParseCDataOrCommentTupleAsync>d__567::MoveNext`
- size: `994`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf0f0`
- `0xf110`
- `0x29720`
- `0x29770`
- `0x298f0`
- `0x2ab40`
- `0x2ff90`
- `0x33200`
- `0x108400`

## string_xrefs

- `0x10849d`: `Xml_UnexpectedEOF`
- `0x1084b2`: `Comment`
- `0x1085ab`: `Xml_InvalidCommentChars`

## pseudocode

```c

```

## disassembly

```asm
0x108400  ldarg.0
0x108401  ldfld    int32 <ParseCDataOrCommentTupleAsync>d__567::<>1__state
0x108406  stloc.0
0x108407  ldarg.0
0x108408  ldfld    class System.Xml.XmlTextReaderImpl <ParseCDataOrCommentTupleAsync>d__567::<>4__this
0x10840d  stloc.1
0x10840e  ldloc.0
0x10840f  brfalse.s loc_108472
0x108411  ldloc.1
0x108412  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108417  ldfld    int32 ParsingState::charsUsed
0x10841c  ldloc.1
0x10841d  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108422  ldfld    int32 ParsingState::charPos
0x108427  sub
0x108428  ldc.i4.3
0x108429  bge      loc_1084BC
0x10842e  ldloc.1
0x10842f  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::ReadDataAsync()
0x108434  ldc.i4.0
0x108435  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x10843a  stloc.s  0xC
0x10843c  ldloca.s 0xC
0x10843e  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x108443  stloc.s  0xB
0x108445  ldloca.s 0xB
0x108447  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x10844c  brtrue.s loc_10848F
0x10844e  ldarg.0
0x10844f  ldc.i4.0
0x108450  dup
0x108451  stloc.0
0x108452  stfld    int32 <ParseCDataOrCommentTupleAsync>d__567::<>1__state
0x108457  ldarg.0
0x108458  ldloc.s  0xB
0x10845a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseCDataOrCommentTupleAsync>d__567::<>u__1
0x10845f  ldarg.0
0x108460  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`3<int32, int32, bool>> <ParseCDataOrCommentTupleAsync>d__567::<>t__builder
0x108465  ldloca.s 0xB
0x108467  ldarg.0
0x108468  call     T0x2B000212
0x10846d  leave    loc_1087E1
0x108472  ldarg.0
0x108473  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseCDataOrCommentTupleAsync>d__567::<>u__1
0x108478  stloc.s  0xB
0x10847a  ldarg.0
0x10847b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseCDataOrCommentTupleAsync>d__567::<>u__1
0x108480  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x108486  ldarg.0
0x108487  ldc.i4.m1
0x108488  dup
0x108489  stloc.0
0x10848a  stfld    int32 <ParseCDataOrCommentTupleAsync>d__567::<>1__state
0x10848f  ldloca.s 0xB
0x108491  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x108496  stloc.s  0xA
0x108498  ldloc.s  0xA
0x10849a  brtrue.s loc_1084BC
0x10849c  ldloc.1
0x10849d  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x1084a2  ldarg.0
0x1084a3  ldfld    valuetype System.Xml.XmlNodeType <ParseCDataOrCommentTupleAsync>d__567::type
0x1084a8  ldc.i4.8
0x1084a9  beq.s    loc_1084B2
0x1084ab  ldstr    aCdata_1// "CDATA"
0x1084b0  br.s     loc_1084B7
0x1084b2  ldstr    aComment_0// "Comment"
0x1084b7  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x1084bc  ldloc.1
0x1084bd  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1084c2  ldfld    int32 ParsingState::charPos
0x1084c7  stloc.s  5
0x1084c9  ldloc.1
0x1084ca  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1084cf  ldfld    char[] ParsingState::chars
0x1084d4  stloc.s  6
0x1084d6  ldc.i4.0
0x1084d7  stloc.s  7
0x1084d9  ldc.i4.m1
0x1084da  stloc.s  8
0x1084dc  ldarg.0
0x1084dd  ldfld    valuetype System.Xml.XmlNodeType <ParseCDataOrCommentTupleAsync>d__567::type
0x1084e2  ldc.i4.8
0x1084e3  beq.s    loc_1084E9
0x1084e5  ldc.i4.s 0x5D
0x1084e7  br.s     loc_1084EB
0x1084e9  ldc.i4.s 0x2D
0x1084eb  stloc.s  9
0x1084ed  br.s     loc_1084F5
0x1084ef  ldloc.s  5
0x1084f1  ldc.i4.1
0x1084f2  add
0x1084f3  stloc.s  5
0x1084f5  ldloc.1
0x1084f6  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x1084fb  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x108500  ldloc.s  6
0x108502  ldloc.s  5
0x108504  ldelem.u2
0x108505  dup
0x108506  stloc.s  0xD
0x108508  add
0x108509  ldind.u1
0x10850a  ldc.i4.s 0x40
0x10850c  and
0x10850d  brfalse.s loc_108515
0x10850f  ldloc.s  0xD
0x108511  ldloc.s  9
0x108513  bne.un.s loc_1084EF
0x108515  ldloc.s  6
0x108517  ldloc.s  5
0x108519  ldelem.u2
0x10851a  ldloc.s  9
0x10851c  bne.un   loc_1085D6
0x108521  ldloc.s  6
0x108523  ldloc.s  5
0x108525  ldc.i4.1
0x108526  add
0x108527  ldelem.u2
0x108528  ldloc.s  9
0x10852a  bne.un   loc_1085B7
0x10852f  ldloc.s  6
0x108531  ldloc.s  5
0x108533  ldc.i4.2
0x108534  add
0x108535  ldelem.u2
0x108536  ldc.i4.s 0x3E
0x108538  bne.un.s loc_10858B
0x10853a  ldloc.s  7
0x10853c  ldc.i4.0
0x10853d  ble.s    loc_10855D
0x10853f  ldloc.1
0x108540  ldloc.s  8
0x108542  ldloc.s  7
0x108544  add
0x108545  ldloc.s  8
0x108547  ldloc.s  5
0x108549  ldloc.s  8
0x10854b  sub
0x10854c  ldloc.s  7
0x10854e  sub
0x10854f  call     instance void System.Xml.XmlTextReaderImpl::ShiftBuffer(int32 sourcePos, int32 destPos, int32 count)
0x108554  ldloc.s  5
0x108556  ldloc.s  7
0x108558  sub
0x108559  stloc.s  4
0x10855b  br.s     loc_108561
0x10855d  ldloc.s  5
0x10855f  stloc.s  4
0x108561  ldloc.1
0x108562  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108567  ldfld    int32 ParsingState::charPos
0x10856c  stloc.3
0x10856d  ldloc.1
0x10856e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108573  ldloc.s  5
0x108575  ldc.i4.3
0x108576  add
0x108577  stfld    int32 ParsingState::charPos
0x10857c  ldloc.3
0x10857d  ldloc.s  4
0x10857f  ldc.i4.1
0x108580  newobj   instance void class [mscorlib]System.Tuple`3<int32, int32, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x108585  stloc.2
0x108586  leave    loc_1087CD
0x10858b  ldloc.s  5
0x10858d  ldc.i4.2
0x10858e  add
0x10858f  ldloc.1
0x108590  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108595  ldfld    int32 ParsingState::charsUsed
0x10859a  beq      loc_108768
0x10859f  ldarg.0
0x1085a0  ldfld    valuetype System.Xml.XmlNodeType <ParseCDataOrCommentTupleAsync>d__567::type
0x1085a5  ldc.i4.8
0x1085a6  bne.un.s loc_1085CB
0x1085a8  ldloc.1
0x1085a9  ldloc.s  5
0x1085ab  ldstr    aXmlInvalidcomm// "Xml_InvalidCommentChars"
0x1085b0  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res)
0x1085b5  br.s     loc_1085CB
0x1085b7  ldloc.s  5
0x1085b9  ldc.i4.1
0x1085ba  add
0x1085bb  ldloc.1
0x1085bc  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1085c1  ldfld    int32 ParsingState::charsUsed
0x1085c6  beq      loc_108768
0x1085cb  ldloc.s  5
0x1085cd  ldc.i4.1
0x1085ce  add
0x1085cf  stloc.s  5
0x1085d1  br       loc_1084F5
0x1085d6  ldloc.s  6
0x1085d8  ldloc.s  5
0x1085da  ldelem.u2
0x1085db  stloc.s  0xF
0x1085dd  ldloc.s  0xF
0x1085df  ldc.i4.s 0x26
0x1085e1  bgt.un.s loc_10860F
0x1085e3  ldloc.s  0xF
0x1085e5  ldc.i4.s 9
0x1085e7  sub
0x1085e8  switch   loc_1086FB, loc_108626, loc_108706, loc_108706, loc_108639
0x108601  ldloc.s  0xF
0x108603  ldc.i4.s 0x26
0x108605  beq      loc_1086FB
0x10860a  br       loc_108706
0x10860f  ldloc.s  0xF
0x108611  ldc.i4.s 0x3C
0x108613  beq      loc_1086FB
0x108618  ldloc.s  0xF
0x10861a  ldc.i4.s 0x5D
0x10861c  beq      loc_1086FB
0x108621  br       loc_108706
0x108626  ldloc.s  5
0x108628  ldc.i4.1
0x108629  add
0x10862a  stloc.s  5
0x10862c  ldloc.1
0x10862d  ldloc.s  5
0x10862f  call     instance void System.Xml.XmlTextReaderImpl::OnNewLine(int32 pos)
0x108634  br       loc_1084F5
0x108639  ldloc.s  6
0x10863b  ldloc.s  5
0x10863d  ldc.i4.1
0x10863e  add
0x10863f  ldelem.u2
0x108640  ldc.i4.s 0xA
0x108642  bne.un.s loc_1086B3
0x108644  ldloc.1
0x108645  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10864a  ldfld    bool ParsingState::eolNormalized
0x10864f  brtrue.s loc_1086AB
0x108651  ldloc.1
0x108652  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x108657  brtrue.s loc_1086AB
0x108659  ldloc.s  5
0x10865b  ldloc.1
0x10865c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108661  ldfld    int32 ParsingState::charPos
0x108666  sub
0x108667  ldc.i4.0
0x108668  ble.s    loc_10869B
0x10866a  ldloc.s  7
0x10866c  brtrue.s loc_108677
0x10866e  ldc.i4.1
0x10866f  stloc.s  7
0x108671  ldloc.s  5
0x108673  stloc.s  8
0x108675  br.s     loc_1086AB
0x108677  ldloc.1
0x108678  ldloc.s  8
0x10867a  ldloc.s  7
0x10867c  add
0x10867d  ldloc.s  8
0x10867f  ldloc.s  5
0x108681  ldloc.s  8
0x108683  sub
0x108684  ldloc.s  7
0x108686  sub
0x108687  call     instance void System.Xml.XmlTextReaderImpl::ShiftBuffer(int32 sourcePos, int32 destPos, int32 count)
0x10868c  ldloc.s  5
0x10868e  ldloc.s  7
0x108690  sub
0x108691  stloc.s  8
0x108693  ldloc.s  7
0x108695  ldc.i4.1
0x108696  add
0x108697  stloc.s  7
0x108699  br.s     loc_1086AB
0x10869b  ldloc.1
0x10869c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1086a1  ldflda   int32 ParsingState::charPos
0x1086a6  dup
0x1086a7  ldind.i4
0x1086a8  ldc.i4.1
0x1086a9  add
0x1086aa  stind.i4
0x1086ab  ldloc.s  5
0x1086ad  ldc.i4.2
0x1086ae  add
0x1086af  stloc.s  5
0x1086b1  br.s     loc_1086EE
0x1086b3  ldloc.s  5
0x1086b5  ldc.i4.1
0x1086b6  add
0x1086b7  ldloc.1
0x1086b8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1086bd  ldfld    int32 ParsingState::charsUsed
0x1086c2  blt.s    loc_1086D4
0x1086c4  ldloc.1
0x1086c5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1086ca  ldfld    bool ParsingState::isEof
0x1086cf  brfalse  loc_108768
0x1086d4  ldloc.1
0x1086d5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1086da  ldfld    bool ParsingState::eolNormalized
0x1086df  brtrue.s loc_1086E8
0x1086e1  ldloc.s  6
  ... truncated ...
```
