# <HandleGeneralEntityReferenceAsync>d__560::MoveNext

- ea: `0x107210`
- end: `0x1075f2`
- name: `<HandleGeneralEntityReferenceAsync>d__560::MoveNext`
- size: `994`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x132d0`
- `0x15ab0`
- `0x15c10`
- `0x15c20`
- `0x15c30`
- `0x15c40`
- `0x20e90`
- `0x294b0`
- `0x297a0`
- `0x30480`
- `0x35070`
- `0x350f0`
- `0xc9800`
- `0xc99f0`
- `0xfe500`
- `0x107210`

## string_xrefs

- `0x10731d`: `Xml_UndeclaredEntity`
- `0x10737d`: `Xml_UnparsedEntityRef`
- `0x1073b4`: `Xml_ExternalEntityInStandAloneDocument`
- `0x1073f3`: `Xml_ExternalEntityInAttValue`

## pseudocode

```c

```

## disassembly

```asm
0x107210  ldarg.0
0x107211  ldfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x107216  stloc.0
0x107217  ldarg.0
0x107218  ldfld    class System.Xml.XmlTextReaderImpl <HandleGeneralEntityReferenceAsync>d__560::<>4__this
0x10721d  stloc.1
0x10721e  ldloc.0
0x10721f  switch   loc_1072A2, loc_10748B, loc_10751E
0x107230  ldarg.0
0x107231  ldnull
0x107232  stfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x107237  ldloc.1
0x107238  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x10723d  brtrue   loc_1072C5
0x107242  ldloc.1
0x107243  ldfld    class System.Xml.XmlParserContext System.Xml.XmlTextReaderImpl::fragmentParserContext
0x107248  brfalse.s loc_1072C5
0x10724a  ldloc.1
0x10724b  ldfld    class System.Xml.XmlParserContext System.Xml.XmlTextReaderImpl::fragmentParserContext
0x107250  callvirt instance bool System.Xml.XmlParserContext::get_HasDtdInfo()
0x107255  brfalse.s loc_1072C5
0x107257  ldloc.1
0x107258  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x10725d  ldc.i4.2
0x10725e  bne.un.s loc_1072C5
0x107260  ldloc.1
0x107261  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::ParseDtdFromParserContextAsync()
0x107266  ldc.i4.0
0x107267  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x10726c  stloc.s  4
0x10726e  ldloca.s 4
0x107270  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x107275  stloc.3
0x107276  ldloca.s 3
0x107278  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x10727d  brtrue.s loc_1072BE
0x10727f  ldarg.0
0x107280  ldc.i4.0
0x107281  dup
0x107282  stloc.0
0x107283  stfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x107288  ldarg.0
0x107289  ldloc.3
0x10728a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleGeneralEntityReferenceAsync>d__560::<>u__1
0x10728f  ldarg.0
0x107290  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype EntityType> <HandleGeneralEntityReferenceAsync>d__560::<>t__builder
0x107295  ldloca.s 3
0x107297  ldarg.0
0x107298  call     T0x2B00020B
0x10729d  leave    loc_1075F1
0x1072a2  ldarg.0
0x1072a3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleGeneralEntityReferenceAsync>d__560::<>u__1
0x1072a8  stloc.3
0x1072a9  ldarg.0
0x1072aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleGeneralEntityReferenceAsync>d__560::<>u__1
0x1072af  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x1072b5  ldarg.0
0x1072b6  ldc.i4.m1
0x1072b7  dup
0x1072b8  stloc.0
0x1072b9  stfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x1072be  ldloca.s 3
0x1072c0  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x1072c5  ldloc.1
0x1072c6  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x1072cb  brfalse.s loc_1072EB
0x1072cd  ldarg.0
0x1072ce  ldloc.1
0x1072cf  ldfld    class System.Xml.IDtdInfo System.Xml.XmlTextReaderImpl::dtdInfo
0x1072d4  ldarg.0
0x1072d5  ldfld    string <HandleGeneralEntityReferenceAsync>d__560::name
0x1072da  callvirt instance class System.Xml.IDtdEntityInfo System.Xml.IDtdInfo::LookupEntity(string name)
0x1072df  dup
0x1072e0  stloc.s  5
0x1072e2  stfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x1072e7  ldloc.s  5
0x1072e9  brtrue.s loc_10733E
0x1072eb  ldloc.1
0x1072ec  ldfld    bool System.Xml.XmlTextReaderImpl::disableUndeclaredEntityCheck
0x1072f1  brfalse.s loc_10731C
0x1072f3  ldarg.0
0x1072f4  ldfld    string <HandleGeneralEntityReferenceAsync>d__560::name
0x1072f9  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0x1072fe  ldc.i4.0
0x1072ff  newobj   instance void System.Xml.Schema.SchemaEntity::.ctor(class System.Xml.XmlQualifiedName qname, bool isParameter)
0x107304  stloc.s  6
0x107306  ldloc.s  6
0x107308  ldsfld   string [mscorlib]System.String::Empty
0x10730d  callvirt instance void System.Xml.Schema.SchemaEntity::set_Text(string value)
0x107312  ldarg.0
0x107313  ldloc.s  6
0x107315  stfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x10731a  br.s     loc_10733E
0x10731c  ldloc.1
0x10731d  ldstr    aXmlUndeclarede// "Xml_UndeclaredEntity"
0x107322  ldarg.0
0x107323  ldfld    string <HandleGeneralEntityReferenceAsync>d__560::name
0x107328  ldloc.1
0x107329  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10732e  call     instance int32 ParsingState::get_LineNo()
0x107333  ldarg.0
0x107334  ldfld    int32 <HandleGeneralEntityReferenceAsync>d__560::entityStartLinePos
0x107339  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x10733e  ldarg.0
0x10733f  ldfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x107344  callvirt instance bool System.Xml.IDtdEntityInfo::get_IsUnparsedEntity()
0x107349  brfalse.s loc_10739E
0x10734b  ldloc.1
0x10734c  ldfld    bool System.Xml.XmlTextReaderImpl::disableUndeclaredEntityCheck
0x107351  brfalse.s loc_10737C
0x107353  ldarg.0
0x107354  ldfld    string <HandleGeneralEntityReferenceAsync>d__560::name
0x107359  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name)
0x10735e  ldc.i4.0
0x10735f  newobj   instance void System.Xml.Schema.SchemaEntity::.ctor(class System.Xml.XmlQualifiedName qname, bool isParameter)
0x107364  stloc.s  7
0x107366  ldloc.s  7
0x107368  ldsfld   string [mscorlib]System.String::Empty
0x10736d  callvirt instance void System.Xml.Schema.SchemaEntity::set_Text(string value)
0x107372  ldarg.0
0x107373  ldloc.s  7
0x107375  stfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x10737a  br.s     loc_10739E
0x10737c  ldloc.1
0x10737d  ldstr    aXmlUnparsedent// "Xml_UnparsedEntityRef"
0x107382  ldarg.0
0x107383  ldfld    string <HandleGeneralEntityReferenceAsync>d__560::name
0x107388  ldloc.1
0x107389  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10738e  call     instance int32 ParsingState::get_LineNo()
0x107393  ldarg.0
0x107394  ldfld    int32 <HandleGeneralEntityReferenceAsync>d__560::entityStartLinePos
0x107399  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x10739e  ldloc.1
0x10739f  ldfld    bool System.Xml.XmlTextReaderImpl::standalone
0x1073a4  brfalse.s loc_1073DA
0x1073a6  ldarg.0
0x1073a7  ldfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x1073ac  callvirt instance bool System.Xml.IDtdEntityInfo::get_IsDeclaredInExternal()
0x1073b1  brfalse.s loc_1073DA
0x1073b3  ldloc.1
0x1073b4  ldstr    aXmlExternalent// "Xml_ExternalEntityInStandAloneDocument"
0x1073b9  ldarg.0
0x1073ba  ldfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x1073bf  callvirt instance string System.Xml.IDtdEntityInfo::get_Name()
0x1073c4  ldloc.1
0x1073c5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1073ca  call     instance int32 ParsingState::get_LineNo()
0x1073cf  ldarg.0
0x1073d0  ldfld    int32 <HandleGeneralEntityReferenceAsync>d__560::entityStartLinePos
0x1073d5  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x1073da  ldarg.0
0x1073db  ldfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x1073e0  callvirt instance bool System.Xml.IDtdEntityInfo::get_IsExternal()
0x1073e5  brfalse  loc_107570
0x1073ea  ldarg.0
0x1073eb  ldfld    bool <HandleGeneralEntityReferenceAsync>d__560::isInAttributeValue
0x1073f0  brfalse.s loc_10741B
0x1073f2  ldloc.1
0x1073f3  ldstr    aXmlExternalent_0// "Xml_ExternalEntityInAttValue"
0x1073f8  ldarg.0
0x1073f9  ldfld    string <HandleGeneralEntityReferenceAsync>d__560::name
0x1073fe  ldloc.1
0x1073ff  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x107404  call     instance int32 ParsingState::get_LineNo()
0x107409  ldarg.0
0x10740a  ldfld    int32 <HandleGeneralEntityReferenceAsync>d__560::entityStartLinePos
0x10740f  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, int32 lineNo, int32 linePos)
0x107414  ldc.i4.4
0x107415  stloc.2
0x107416  leave    loc_1075D6
0x10741b  ldloc.1
0x10741c  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x107421  ldc.i4.2
0x107422  bne.un.s loc_10742B
0x107424  ldc.i4.4
0x107425  stloc.2
0x107426  leave    loc_1075D6
0x10742b  ldloc.1
0x10742c  call     instance bool System.Xml.XmlTextReaderImpl::get_IsResolverNull()
0x107431  brfalse  loc_1074D4
0x107436  ldarg.0
0x107437  ldfld    bool <HandleGeneralEntityReferenceAsync>d__560::pushFakeEntityIfNullResolver
0x10743c  brfalse  loc_1074CD
0x107441  ldloc.1
0x107442  ldarg.0
0x107443  ldfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x107448  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::PushExternalEntityAsync(class System.Xml.IDtdEntityInfo entity)
0x10744d  ldc.i4.0
0x10744e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x107453  stloc.s  9
0x107455  ldloca.s 9
0x107457  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x10745c  stloc.s  8
0x10745e  ldloca.s 8
0x107460  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x107465  brtrue.s loc_1074A8
0x107467  ldarg.0
0x107468  ldc.i4.1
0x107469  dup
0x10746a  stloc.0
0x10746b  stfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x107470  ldarg.0
0x107471  ldloc.s  8
0x107473  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleGeneralEntityReferenceAsync>d__560::<>u__2
0x107478  ldarg.0
0x107479  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype EntityType> <HandleGeneralEntityReferenceAsync>d__560::<>t__builder
0x10747e  ldloca.s 8
0x107480  ldarg.0
0x107481  call     T0x2B00020C
0x107486  leave    loc_1075F1
0x10748b  ldarg.0
0x10748c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleGeneralEntityReferenceAsync>d__560::<>u__2
0x107491  stloc.s  8
0x107493  ldarg.0
0x107494  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleGeneralEntityReferenceAsync>d__560::<>u__2
0x107499  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x10749f  ldarg.0
0x1074a0  ldc.i4.m1
0x1074a1  dup
0x1074a2  stloc.0
0x1074a3  stfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x1074a8  ldloca.s 8
0x1074aa  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x1074af  pop
0x1074b0  ldloc.1
0x1074b1  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x1074b6  ldloc.1
0x1074b7  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1074bc  ldfld    int32 ParsingState::entityId
0x1074c1  stfld    int32 NodeData::entityId
0x1074c6  ldc.i4.5
0x1074c7  stloc.2
0x1074c8  leave    loc_1075D6
0x1074cd  ldc.i4.4
0x1074ce  stloc.2
0x1074cf  leave    loc_1075D6
0x1074d4  ldloc.1
0x1074d5  ldarg.0
0x1074d6  ldfld    class System.Xml.IDtdEntityInfo <HandleGeneralEntityReferenceAsync>d__560::<entity>5__2
0x1074db  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::PushExternalEntityAsync(class System.Xml.IDtdEntityInfo entity)
0x1074e0  ldc.i4.0
0x1074e1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x1074e6  stloc.s  9
0x1074e8  ldloca.s 9
0x1074ea  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x1074ef  stloc.s  0xA
0x1074f1  ldloca.s 0xA
0x1074f3  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x1074f8  brtrue.s loc_10753B
0x1074fa  ldarg.0
0x1074fb  ldc.i4.2
0x1074fc  dup
0x1074fd  stloc.0
0x1074fe  stfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x107503  ldarg.0
0x107504  ldloc.s  0xA
0x107506  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleGeneralEntityReferenceAsync>d__560::<>u__2
0x10750b  ldarg.0
0x10750c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype EntityType> <HandleGeneralEntityReferenceAsync>d__560::<>t__builder
0x107511  ldloca.s 0xA
0x107513  ldarg.0
0x107514  call     T0x2B00020C
0x107519  leave    loc_1075F1
0x10751e  ldarg.0
0x10751f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleGeneralEntityReferenceAsync>d__560::<>u__2
0x107524  stloc.s  0xA
0x107526  ldarg.0
0x107527  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleGeneralEntityReferenceAsync>d__560::<>u__2
0x10752c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x107532  ldarg.0
0x107533  ldc.i4.m1
0x107534  dup
0x107535  stloc.0
0x107536  stfld    int32 <HandleGeneralEntityReferenceAsync>d__560::<>1__state
0x10753b  ldloca.s 0xA
0x10753d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x107542  pop
0x107543  ldloc.1
0x107544  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x107549  ldloc.1
0x10754a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10754f  ldfld    int32 ParsingState::entityId
0x107554  stfld    int32 NodeData::entityId
0x107559  ldarg.0
0x10755a  ldfld    bool <HandleGeneralEntityReferenceAsync>d__560::isInAttributeValue
0x10755f  brfalse.s loc_107569
0x107561  ldloc.1
0x107562  ldfld    bool System.Xml.XmlTextReaderImpl::validatingReaderCompatFlag
0x107567  brtrue.s loc_10756C
0x107569  ldc.i4.3
0x10756a  br.s     loc_10756D
0x10756c  ldc.i4.7
0x10756d  stloc.2
0x10756e  leave.s  loc_1075D6
0x107570  ldloc.1
0x107571  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x107576  ldc.i4.2
0x107577  bne.un.s loc_10757D
0x107579  ldc.i4.4
  ... truncated ...
```
