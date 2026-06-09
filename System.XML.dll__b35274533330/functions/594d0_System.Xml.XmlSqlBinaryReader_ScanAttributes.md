# System.Xml.XmlSqlBinaryReader::ScanAttributes

- ea: `0x594d0`
- end: `0x59768`
- name: `System.Xml.XmlSqlBinaryReader::ScanAttributes`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x59e10`

## callees

- `0xe6c0`
- `0x12680`
- `0x13200`
- `0x58810`
- `0x58d00`
- `0x58ef0`
- `0x59070`
- `0x590b0`
- `0x594d0`
- `0x59770`
- `0x597f0`
- `0x5a680`
- `0x5b280`
- `0x5c160`
- `0x5c180`
- `0x119410`

## string_xrefs

- `0x595c4`: `xmlns`
- `0x595f4`: `Xml_PrefixForEmptyNs`
- `0x59665`: `XmlBinary_ListsOfValuesNotSupported`
- `0x5962a`: `XmlBinary_AttrWithNsNoPrefix`

## pseudocode

```c

```

## disassembly

```asm
0x594d0  ldc.i4.m1
0x594d1  stloc.1
0x594d2  ldc.i4.m1
0x594d3  stloc.2
0x594d4  ldarg.0
0x594d5  ldarg.0
0x594d6  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x594db  stfld    int32 System.Xml.XmlSqlBinaryReader::mark
0x594e0  ldnull
0x594e1  stloc.3
0x594e2  ldc.i4.0
0x594e3  stloc.s  4
0x594e5  br       loc_596C3
0x594ea  ldc.i4   0xF6
0x594ef  ldloc.0
0x594f0  bne.un   loc_59656
0x594f5  ldloc.3
0x594f6  brfalse.s loc_59507
0x594f8  ldarg.0
0x594f9  ldloc.3
0x594fa  ldsfld   string [mscorlib]System.String::Empty
0x594ff  ldc.i4.0
0x59500  call     instance void System.Xml.XmlSqlBinaryReader::PushNamespace(string prefix, string ns, bool implied)
0x59505  ldnull
0x59506  stloc.3
0x59507  ldarg.0
0x59508  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x5950d  ldarg.0
0x5950e  ldfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x59513  ldlen
0x59514  conv.i4
0x59515  bne.un.s loc_5951D
0x59517  ldarg.0
0x59518  call     instance void System.Xml.XmlSqlBinaryReader::GrowAttributes()
0x5951d  ldarg.0
0x5951e  ldflda   valuetype SymbolTables System.Xml.XmlSqlBinaryReader::symbolTables
0x59523  ldfld    valuetype QName[] SymbolTables::qnametable
0x59528  ldarg.0
0x59529  call     instance int32 System.Xml.XmlSqlBinaryReader::ReadQNameRef()
0x5952e  ldelem   QName
0x59533  stloc.s  5
0x59535  ldarg.0
0x59536  ldfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x5953b  ldarg.0
0x5953c  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59541  ldelema  AttrInfo
0x59546  ldloc.s  5
0x59548  ldarg.0
0x59549  ldfld    int32 System.Xml.XmlSqlBinaryReader::pos
0x5954e  call     instance void AttrInfo::Set(valuetype QName n, int32 pos)
0x59553  ldloc.s  5
0x59555  ldfld    string QName::prefix
0x5955a  ldstr    aXml// "xml"
0x5955f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59564  brfalse.s loc_595A7
0x59566  ldloc.s  5
0x59568  ldfld    string QName::localname
0x5956d  ldstr    aLang// "lang"
0x59572  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59577  brfalse.s loc_59585
0x59579  ldarg.0
0x5957a  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x5957f  stloc.2
0x59580  br       loc_59643
0x59585  ldloc.s  5
0x59587  ldfld    string QName::localname
0x5958c  ldstr    aSpace// "space"
0x59591  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59596  brfalse  loc_59643
0x5959b  ldarg.0
0x5959c  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x595a1  stloc.1
0x595a2  br       loc_59643
0x595a7  ldloc.s  5
0x595a9  ldfld    string QName::namespaceUri
0x595ae  ldarg.0
0x595af  ldfld    string System.Xml.XmlSqlBinaryReader::nsxmlns
0x595b4  call     bool System.Xml.Ref::Equal(string strA, string strB)
0x595b9  brfalse.s loc_595D8
0x595bb  ldloc.s  5
0x595bd  ldfld    string QName::localname
0x595c2  stloc.3
0x595c3  ldloc.3
0x595c4  ldstr    aXmlns// "xmlns"
0x595c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x595ce  brfalse.s loc_59643
0x595d0  ldsfld   string [mscorlib]System.String::Empty
0x595d5  stloc.3
0x595d6  br.s     loc_59643
0x595d8  ldloc.s  5
0x595da  ldfld    string QName::prefix
0x595df  callvirt instance int32 [mscorlib]System.String::get_Length()
0x595e4  brfalse.s loc_5961B
0x595e6  ldloc.s  5
0x595e8  ldfld    string QName::namespaceUri
0x595ed  callvirt instance int32 [mscorlib]System.String::get_Length()
0x595f2  brtrue.s loc_59604
0x595f4  ldstr    aXmlPrefixforem// "Xml_PrefixForEmptyNs"
0x595f9  ldsfld   string [mscorlib]System.String::Empty
0x595fe  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg)
0x59603  throw
0x59604  ldarg.0
0x59605  ldloc.s  5
0x59607  ldfld    string QName::prefix
0x5960c  ldloc.s  5
0x5960e  ldfld    string QName::namespaceUri
0x59613  ldc.i4.1
0x59614  call     instance void System.Xml.XmlSqlBinaryReader::PushNamespace(string prefix, string ns, bool implied)
0x59619  br.s     loc_59643
0x5961b  ldloc.s  5
0x5961d  ldfld    string QName::namespaceUri
0x59622  callvirt instance int32 [mscorlib]System.String::get_Length()
0x59627  brfalse.s loc_59643
0x59629  ldarg.0
0x5962a  ldstr    aXmlbinaryAttrw// "XmlBinary_AttrWithNsNoPrefix"
0x5962f  ldloc.s  5
0x59631  ldfld    string QName::localname
0x59636  ldloc.s  5
0x59638  ldfld    string QName::namespaceUri
0x5963d  call     instance class [mscorlib]System.Exception System.Xml.XmlSqlBinaryReader::ThrowXmlException(string res, string arg1, string arg2)
0x59642  throw
0x59643  ldarg.0
0x59644  ldarg.0
0x59645  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x5964a  ldc.i4.1
0x5964b  add
0x5964c  stfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59651  ldc.i4.0
0x59652  stloc.s  4
0x59654  br.s     loc_596C3
0x59656  ldarg.0
0x59657  ldloc.0
0x59658  ldc.i4.1
0x59659  ldc.i4.1
0x5965a  call     instance valuetype System.Xml.XmlNodeType System.Xml.XmlSqlBinaryReader::ScanOverValue(valuetype System.Xml.BinXmlToken token, bool attr, bool checkChars)
0x5965f  pop
0x59660  ldloc.s  4
0x59662  brfalse.s loc_59670
0x59664  ldarg.0
0x59665  ldstr    aXmlbinaryLists// "XmlBinary_ListsOfValuesNotSupported"
0x5966a  call     instance class [mscorlib]System.Exception System.Xml.XmlSqlBinaryReader::ThrowNotSupported(string res)
0x5966f  throw
0x59670  ldarg.0
0x59671  ldfld    string System.Xml.XmlSqlBinaryReader::stringValue
0x59676  stloc.s  6
0x59678  ldloc.s  6
0x5967a  brfalse.s loc_5969D
0x5967c  ldarg.0
0x5967d  ldfld    valuetype AttrInfo[] System.Xml.XmlSqlBinaryReader::attributes
0x59682  ldarg.0
0x59683  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59688  ldc.i4.1
0x59689  sub
0x5968a  ldelema  AttrInfo
0x5968f  ldloc.s  6
0x59691  stfld    string AttrInfo::val
0x59696  ldarg.0
0x59697  ldnull
0x59698  stfld    string System.Xml.XmlSqlBinaryReader::stringValue
0x5969d  ldloc.3
0x5969e  brfalse.s loc_596C0
0x596a0  ldarg.0
0x596a1  ldfld    class System.Xml.XmlNameTable System.Xml.XmlSqlBinaryReader::xnt
0x596a6  ldarg.0
0x596a7  ldloc.0
0x596a8  call     instance string System.Xml.XmlSqlBinaryReader::ValueAsString(valuetype System.Xml.BinXmlToken token)
0x596ad  callvirt instance string System.Xml.XmlNameTable::Add(string array)
0x596b2  stloc.s  7
0x596b4  ldarg.0
0x596b5  ldloc.3
0x596b6  ldloc.s  7
0x596b8  ldc.i4.0
0x596b9  call     instance void System.Xml.XmlSqlBinaryReader::PushNamespace(string prefix, string ns, bool implied)
0x596be  ldnull
0x596bf  stloc.3
0x596c0  ldc.i4.1
0x596c1  stloc.s  4
0x596c3  ldc.i4   0xF5
0x596c8  ldarg.0
0x596c9  call     instance valuetype System.Xml.BinXmlToken System.Xml.XmlSqlBinaryReader::NextToken()
0x596ce  dup
0x596cf  stloc.0
0x596d0  bne.un   loc_594EA
0x596d5  ldloc.1
0x596d6  ldc.i4.m1
0x596d7  beq.s    loc_5972C
0x596d9  ldarg.0
0x596da  ldloc.1
0x596db  call     instance string System.Xml.XmlSqlBinaryReader::GetAttributeText(int32 i)
0x596e0  stloc.s  8
0x596e2  ldc.i4.0
0x596e3  stloc.s  9
0x596e5  ldloc.s  8
0x596e7  ldstr    aPreserve// "preserve"
0x596ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x596f1  brfalse.s loc_596F8
0x596f3  ldc.i4.2
0x596f4  stloc.s  9
0x596f6  br.s     loc_59709
0x596f8  ldloc.s  8
0x596fa  ldstr    aDefault// "default"
0x596ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59704  brfalse.s loc_59709
0x59706  ldc.i4.1
0x59707  stloc.s  9
0x59709  ldarg.0
0x5970a  ldfld    valuetype ElemInfo[] System.Xml.XmlSqlBinaryReader::elementStack
0x5970f  ldarg.0
0x59710  ldfld    int32 System.Xml.XmlSqlBinaryReader::elemDepth
0x59715  ldelema  ElemInfo
0x5971a  ldloc.s  9
0x5971c  stfld    valuetype System.Xml.XmlSpace ElemInfo::xmlSpace
0x59721  ldarg.0
0x59722  ldc.i4.2
0x59723  ldloc.s  9
0x59725  ceq
0x59727  stfld    bool System.Xml.XmlSqlBinaryReader::xmlspacePreserve
0x5972c  ldloc.2
0x5972d  ldc.i4.m1
0x5972e  beq.s    loc_5974D
0x59730  ldarg.0
0x59731  ldfld    valuetype ElemInfo[] System.Xml.XmlSqlBinaryReader::elementStack
0x59736  ldarg.0
0x59737  ldfld    int32 System.Xml.XmlSqlBinaryReader::elemDepth
0x5973c  ldelema  ElemInfo
0x59741  ldarg.0
0x59742  ldloc.2
0x59743  call     instance string System.Xml.XmlSqlBinaryReader::GetAttributeText(int32 i)
0x59748  stfld    string ElemInfo::xmlLang
0x5974d  ldarg.0
0x5974e  ldfld    int32 System.Xml.XmlSqlBinaryReader::attrCount
0x59753  ldc.i4   0xC8
0x59758  bge.s    loc_59761
0x5975a  ldarg.0
0x5975b  call     instance void System.Xml.XmlSqlBinaryReader::SimpleCheckForDuplicateAttributes()
0x59760  ret
0x59761  ldarg.0
0x59762  call     instance void System.Xml.XmlSqlBinaryReader::HashCheckForDuplicateAttributes()
0x59767  ret
```
