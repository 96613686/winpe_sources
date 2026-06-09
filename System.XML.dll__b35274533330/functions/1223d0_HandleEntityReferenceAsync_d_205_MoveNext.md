# <HandleEntityReferenceAsync>d__205::MoveNext

- ea: `0x1223d0`
- end: `0x12264e`
- name: `<HandleEntityReferenceAsync>d__205::MoveNext`
- size: `638`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x13320`
- `0x15f10`
- `0x5c5e0`
- `0x5c620`
- `0x60960`
- `0x609a0`
- `0x60ba0`
- `0x60de0`
- `0x60df0`
- `0xc9980`
- `0xc99e0`
- `0xc9a70`
- `0x1223d0`

## string_xrefs

- `0x12247b`: `Xml_RecursiveGenEntity`
- `0x122482`: `Xml_RecursiveParEntity`
- `0x122423`: `Xml_InvalidParEntityRef`

## pseudocode

```c

```

## disassembly

```asm
0x1223d0  ldarg.0
0x1223d1  ldfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x1223d6  stloc.0
0x1223d7  ldarg.0
0x1223d8  ldfld    class System.Xml.DtdParser <HandleEntityReferenceAsync>d__205::<>4__this
0x1223dd  stloc.1
0x1223de  ldloc.0
0x1223df  brfalse  loc_1224EC
0x1223e4  ldloc.0
0x1223e5  ldc.i4.1
0x1223e6  beq      loc_1225A0
0x1223eb  ldloc.1
0x1223ec  call     instance void System.Xml.DtdParser::SaveParsingBuffer()
0x1223f1  ldarg.0
0x1223f2  ldfld    bool <HandleEntityReferenceAsync>d__205::paramEntity
0x1223f7  brfalse.s loc_12242D
0x1223f9  ldloc.1
0x1223fa  call     instance bool System.Xml.DtdParser::get_ParsingInternalSubset()
0x1223ff  brfalse.s loc_12242D
0x122401  ldloc.1
0x122402  call     instance bool System.Xml.DtdParser::get_ParsingTopLevelMarkup()
0x122407  brtrue.s loc_12242D
0x122409  ldloc.1
0x12240a  ldloc.1
0x12240b  ldfld    int32 System.Xml.DtdParser::curPos
0x122410  ldarg.0
0x122411  ldfld    class System.Xml.XmlQualifiedName <HandleEntityReferenceAsync>d__205::entityName
0x122416  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x12241b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x122420  sub
0x122421  ldc.i4.1
0x122422  sub
0x122423  ldstr    aXmlInvalidpare// "Xml_InvalidParEntityRef"
0x122428  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x12242d  ldloc.1
0x12242e  ldarg.0
0x12242f  ldfld    class System.Xml.XmlQualifiedName <HandleEntityReferenceAsync>d__205::entityName
0x122434  ldarg.0
0x122435  ldfld    bool <HandleEntityReferenceAsync>d__205::paramEntity
0x12243a  ldc.i4.1
0x12243b  ldarg.0
0x12243c  ldfld    bool <HandleEntityReferenceAsync>d__205::inAttribute
0x122441  call     instance class System.Xml.Schema.SchemaEntity System.Xml.DtdParser::VerifyEntityReference(class System.Xml.XmlQualifiedName entityName, bool paramEntity, bool mustBeDeclared, bool inAttribute)
0x122446  stloc.3
0x122447  ldloc.3
0x122448  brtrue.s loc_122451
0x12244a  ldc.i4.0
0x12244b  stloc.2
0x12244c  leave    loc_122639
0x122451  ldloc.3
0x122452  callvirt instance bool System.Xml.Schema.SchemaEntity::get_ParsingInProgress()
0x122457  brfalse.s loc_122497
0x122459  ldloc.1
0x12245a  ldloc.1
0x12245b  ldfld    int32 System.Xml.DtdParser::curPos
0x122460  ldarg.0
0x122461  ldfld    class System.Xml.XmlQualifiedName <HandleEntityReferenceAsync>d__205::entityName
0x122466  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x12246b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x122470  sub
0x122471  ldc.i4.1
0x122472  sub
0x122473  ldarg.0
0x122474  ldfld    bool <HandleEntityReferenceAsync>d__205::paramEntity
0x122479  brtrue.s loc_122482
0x12247b  ldstr    aXmlRecursivege// "Xml_RecursiveGenEntity"
0x122480  br.s     loc_122487
0x122482  ldstr    aXmlRecursivepa// "Xml_RecursiveParEntity"
0x122487  ldarg.0
0x122488  ldfld    class System.Xml.XmlQualifiedName <HandleEntityReferenceAsync>d__205::entityName
0x12248d  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x122492  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x122497  ldloc.3
0x122498  callvirt instance bool System.Xml.Schema.SchemaEntity::get_IsExternal()
0x12249d  brfalse  loc_122542
0x1224a2  ldloc.1
0x1224a3  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x1224a8  ldloc.3
0x1224a9  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>> System.Xml.IDtdParserAdapter::PushEntityAsync(class System.Xml.IDtdEntityInfo entity)
0x1224ae  ldc.i4.0
0x1224af  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>>::ConfigureAwait(!!T0)
0x1224b4  stloc.s  8
0x1224b6  ldloca.s 8
0x1224b8  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<int32, bool>>::GetAwaiter()
0x1224bd  stloc.s  7
0x1224bf  ldloca.s 7
0x1224c1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::get_IsCompleted()
0x1224c6  brtrue.s loc_122509
0x1224c8  ldarg.0
0x1224c9  ldc.i4.0
0x1224ca  dup
0x1224cb  stloc.0
0x1224cc  stfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x1224d1  ldarg.0
0x1224d2  ldloc.s  7
0x1224d4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <HandleEntityReferenceAsync>d__205::<>u__1
0x1224d9  ldarg.0
0x1224da  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <HandleEntityReferenceAsync>d__205::<>t__builder
0x1224df  ldloca.s 7
0x1224e1  ldarg.0
0x1224e2  call     T0x2B0002DC
0x1224e7  leave    loc_12264D
0x1224ec  ldarg.0
0x1224ed  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <HandleEntityReferenceAsync>d__205::<>u__1
0x1224f2  stloc.s  7
0x1224f4  ldarg.0
0x1224f5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <HandleEntityReferenceAsync>d__205::<>u__1
0x1224fa  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>
0x122500  ldarg.0
0x122501  ldc.i4.m1
0x122502  dup
0x122503  stloc.0
0x122504  stfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x122509  ldloca.s 7
0x12250b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::GetResult()
0x122510  stloc.s  6
0x122512  ldloc.s  6
0x122514  stloc.s  5
0x122516  ldloc.s  5
0x122518  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item1()
0x12251d  stloc.s  4
0x12251f  ldloc.s  5
0x122521  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item2()
0x122526  brtrue.s loc_12252F
0x122528  ldc.i4.0
0x122529  stloc.2
0x12252a  leave    loc_122639
0x12252f  ldloc.1
0x122530  ldloc.1
0x122531  ldfld    int32 System.Xml.DtdParser::externalEntitiesDepth
0x122536  ldc.i4.1
0x122537  add
0x122538  stfld    int32 System.Xml.DtdParser::externalEntitiesDepth
0x12253d  br       loc_1225E0
0x122542  ldloc.3
0x122543  callvirt instance string System.Xml.Schema.SchemaEntity::get_Text()
0x122548  callvirt instance int32 [mscorlib]System.String::get_Length()
0x12254d  brtrue.s loc_122556
0x12254f  ldc.i4.0
0x122550  stloc.2
0x122551  leave    loc_122639
0x122556  ldloc.1
0x122557  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x12255c  ldloc.3
0x12255d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>> System.Xml.IDtdParserAdapter::PushEntityAsync(class System.Xml.IDtdEntityInfo entity)
0x122562  ldc.i4.0
0x122563  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>>::ConfigureAwait(!!T0)
0x122568  stloc.s  8
0x12256a  ldloca.s 8
0x12256c  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<int32, bool>>::GetAwaiter()
0x122571  stloc.s  0xB
0x122573  ldloca.s 0xB
0x122575  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::get_IsCompleted()
0x12257a  brtrue.s loc_1225BD
0x12257c  ldarg.0
0x12257d  ldc.i4.1
0x12257e  dup
0x12257f  stloc.0
0x122580  stfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x122585  ldarg.0
0x122586  ldloc.s  0xB
0x122588  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <HandleEntityReferenceAsync>d__205::<>u__1
0x12258d  ldarg.0
0x12258e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <HandleEntityReferenceAsync>d__205::<>t__builder
0x122593  ldloca.s 0xB
0x122595  ldarg.0
0x122596  call     T0x2B0002DC
0x12259b  leave    loc_12264D
0x1225a0  ldarg.0
0x1225a1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <HandleEntityReferenceAsync>d__205::<>u__1
0x1225a6  stloc.s  0xB
0x1225a8  ldarg.0
0x1225a9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <HandleEntityReferenceAsync>d__205::<>u__1
0x1225ae  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>
0x1225b4  ldarg.0
0x1225b5  ldc.i4.m1
0x1225b6  dup
0x1225b7  stloc.0
0x1225b8  stfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x1225bd  ldloca.s 0xB
0x1225bf  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::GetResult()
0x1225c4  stloc.s  0xA
0x1225c6  ldloc.s  0xA
0x1225c8  stloc.s  9
0x1225ca  ldloc.s  9
0x1225cc  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item1()
0x1225d1  stloc.s  4
0x1225d3  ldloc.s  9
0x1225d5  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item2()
0x1225da  brtrue.s loc_1225E0
0x1225dc  ldc.i4.0
0x1225dd  stloc.2
0x1225de  leave.s  loc_122639
0x1225e0  ldloc.1
0x1225e1  ldloc.s  4
0x1225e3  stfld    int32 System.Xml.DtdParser::currentEntityId
0x1225e8  ldarg.0
0x1225e9  ldfld    bool <HandleEntityReferenceAsync>d__205::paramEntity
0x1225ee  brfalse.s loc_122616
0x1225f0  ldarg.0
0x1225f1  ldfld    bool <HandleEntityReferenceAsync>d__205::inLiteral
0x1225f6  brtrue.s loc_122616
0x1225f8  ldloc.1
0x1225f9  ldfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x1225fe  ldc.i4.s 0x20
0x122600  beq.s    loc_122616
0x122602  ldloc.1
0x122603  ldloc.1
0x122604  ldfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x122609  stfld    valuetype ScanningFunction System.Xml.DtdParser::savedScanningFunction
0x12260e  ldloc.1
0x12260f  ldc.i4.s 0x20
0x122611  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x122616  ldloc.1
0x122617  call     instance void System.Xml.DtdParser::LoadParsingBuffer()
0x12261c  ldc.i4.1
0x12261d  stloc.2
0x12261e  leave.s  loc_122639
0x122620  stloc.s  0xC
0x122622  ldarg.0
0x122623  ldc.i4.s 0xFE
0x122625  stfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x12262a  ldarg.0
0x12262b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <HandleEntityReferenceAsync>d__205::<>t__builder
0x122630  ldloc.s  0xC
0x122632  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x122637  leave.s  loc_12264D
0x122639  ldarg.0
0x12263a  ldc.i4.s 0xFE
0x12263c  stfld    int32 <HandleEntityReferenceAsync>d__205::<>1__state
0x122641  ldarg.0
0x122642  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <HandleEntityReferenceAsync>d__205::<>t__builder
0x122647  ldloc.2
0x122648  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x12264d  ret
```
