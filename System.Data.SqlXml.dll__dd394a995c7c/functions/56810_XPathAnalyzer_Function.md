# XPathAnalyzer::Function

- ea: `0x56810`
- end: `0x56b72`
- name: `XPathAnalyzer::Function`
- size: `866`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2320`
- `0x1c190`
- `0x2e3e0`
- `0x50af0`
- `0x56710`
- `0x56810`

## string_xrefs

- `0x5690e`: `urn:schemas-microsoft-com:xslt`
- `0x56a12`: `namespace-uri`
- `0x569bb`: `string-compare`
- `0x56a56`: `http://exslt.org/common`

## pseudocode

```c

```

## disassembly

```asm
0x56810  ldarg.0
0x56811  ldnull
0x56812  stfld    class System.Xml.Xsl.Xslt.VarPar XPathAnalyzer::typeDonor
0x56817  ldc.i4.0
0x56818  stloc.0
0x56819  ldarg.3
0x5681a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xml.Xsl.XslFlags>::GetEnumerator()
0x5681f  stloc.2
0x56820  br.s     loc_5682D
0x56822  ldloc.2
0x56823  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xml.Xsl.XslFlags>::get_Current()
0x56828  stloc.3
0x56829  ldloc.0
0x5682a  ldloc.3
0x5682b  or
0x5682c  stloc.0
0x5682d  ldloc.2
0x5682e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x56833  brtrue.s loc_56822
0x56835  leave.s  loc_56841
0x56837  ldloc.2
0x56838  brfalse.s loc_56840
0x5683a  ldloc.2
0x5683b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56840  endfinally
0x56841  ldc.i4.0
0x56842  stloc.1
0x56843  ldarg.1
0x56844  callvirt instance int32 [mscorlib]System.String::get_Length()
0x56849  brtrue   loc_56903
0x5684e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>> System.Xml.Xsl.XPath.XPathBuilder::FunctionTable
0x56853  ldarg.2
0x56854  ldloca.s 4
0x56856  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::TryGetValue(var<u1>, !!T0)
0x5685b  brfalse.s loc_568AF
0x5685d  ldloc.s  4
0x5685f  ldfld    var<u1> class FunctionInfo`1<valuetype FuncId>::id
0x56864  stloc.s  6
0x56866  ldsfld   valuetype System.Xml.Xsl.XslFlags[] XPathAnalyzer::XPathFunctionFlags
0x5686b  ldloc.s  6
0x5686d  ldelem.i4
0x5686e  stloc.1
0x5686f  ldarg.3
0x56870  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype System.Xml.Xsl.XslFlags>::get_Count()
0x56875  brtrue   loc_56B6B
0x5687a  ldloc.s  6
0x5687c  ldc.i4.3
0x5687d  beq.s    loc_568A2
0x5687f  ldloc.s  6
0x56881  ldc.i4.4
0x56882  beq.s    loc_568A2
0x56884  ldloc.s  6
0x56886  ldc.i4.5
0x56887  beq.s    loc_568A2
0x56889  ldloc.s  6
0x5688b  ldc.i4.6
0x5688c  beq.s    loc_568A2
0x5688e  ldloc.s  6
0x56890  ldc.i4.7
0x56891  beq.s    loc_568A2
0x56893  ldloc.s  6
0x56895  ldc.i4.s 0x13
0x56897  beq.s    loc_568A2
0x56899  ldloc.s  6
0x5689b  ldc.i4.s 0x14
0x5689d  bne.un   loc_56B6B
0x568a2  ldloc.1
0x568a3  ldc.i4   0x100
0x568a8  or
0x568a9  stloc.1
0x568aa  br       loc_56B6B
0x568af  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>> System.Xml.Xsl.Xslt.QilGenerator::FunctionTable
0x568b4  ldarg.2
0x568b5  ldloca.s 5
0x568b7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::TryGetValue(var<u1>, !!T0)
0x568bc  brfalse  loc_56B6B
0x568c1  ldloc.s  5
0x568c3  ldfld    var<u1> class FunctionInfo`1<valuetype FuncId>::id
0x568c8  stloc.s  7
0x568ca  ldsfld   valuetype System.Xml.Xsl.XslFlags[] XPathAnalyzer::XsltFunctionFlags
0x568cf  ldloc.s  7
0x568d1  ldelem.i4
0x568d2  stloc.1
0x568d3  ldloc.s  7
0x568d5  brtrue.s loc_568E3
0x568d7  ldarg.0
0x568d8  ldc.i4.1
0x568d9  stfld    bool XPathAnalyzer::xsltCurrentNeeded
0x568de  br       loc_56B6B
0x568e3  ldloc.s  7
0x568e5  ldc.i4.5
0x568e6  bne.un   loc_56B6B
0x568eb  ldarg.3
0x568ec  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype System.Xml.Xsl.XslFlags>::get_Count()
0x568f1  brtrue   loc_56B6B
0x568f6  ldloc.1
0x568f7  ldc.i4   0x100
0x568fc  or
0x568fd  stloc.1
0x568fe  br       loc_56B6B
0x56903  ldarg.0
0x56904  ldarg.1
0x56905  call     instance string XPathAnalyzer::ResolvePrefix(string prefix)
0x5690a  stloc.s  8
0x5690c  ldloc.s  8
0x5690e  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xslt"
0x56913  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56918  brfalse  loc_56A54
0x5691d  ldarg.2
0x5691e  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x56923  stloc.s  9
0x56925  ldloc.s  9
0x56927  ldc.i4   0x3D93DA9D
0x5692c  bgt.un.s loc_5696E
0x5692e  ldloc.s  9
0x56930  ldc.i4   0x1BD670A0
0x56935  bgt.un.s loc_56954
0x56937  ldloc.s  9
0x56939  ldc.i4   0x1363B241
0x5693e  beq      loc_569DE
0x56943  ldloc.s  9
0x56945  ldc.i4   0x1BD670A0
0x5694a  beq      loc_56A20
0x5694f  br       loc_56A85
0x56954  ldloc.s  9
0x56956  ldc.i4   0x3B8C1A3C
0x5695b  beq      loc_56A02
0x56960  ldloc.s  9
0x56962  ldc.i4   0x3D93DA9D
0x56967  beq.s    loc_569CC
0x56969  br       loc_56A85
0x5696e  ldloc.s  9
0x56970  ldc.i4   0x961D0B4F
0x56975  bgt.un.s loc_56991
0x56977  ldloc.s  9
0x56979  ldc.i4   0x7A90FACE
0x5697e  beq.s    loc_569BA
0x56980  ldloc.s  9
0x56982  ldc.i4   0x961D0B4F
0x56987  beq      loc_56A11
0x5698c  br       loc_56A85
0x56991  ldloc.s  9
0x56993  ldc.i4   0xBF452630
0x56998  beq.s    loc_569A8
0x5699a  ldloc.s  9
0x5699c  ldc.i4   0xE2C003AC
0x569a1  beq.s    loc_569F0
0x569a3  br       loc_56A85
0x569a8  ldarg.2
0x569a9  ldstr    aNodeSet// "node-set"
0x569ae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x569b3  brtrue.s loc_56A2F
0x569b5  br       loc_56A85
0x569ba  ldarg.2
0x569bb  ldstr    aStringCompare// "string-compare"
0x569c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x569c5  brtrue.s loc_56A34
0x569c7  br       loc_56A85
0x569cc  ldarg.2
0x569cd  ldstr    aUtc// "utc"
0x569d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x569d7  brtrue.s loc_56A38
0x569d9  br       loc_56A85
0x569de  ldarg.2
0x569df  ldstr    aFormatDate// "format-date"
0x569e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x569e9  brtrue.s loc_56A3C
0x569eb  br       loc_56A85
0x569f0  ldarg.2
0x569f1  ldstr    aFormatTime// "format-time"
0x569f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x569fb  brtrue.s loc_56A40
0x569fd  br       loc_56A85
0x56a02  ldarg.2
0x56a03  ldstr    aLocalName// "local-name"
0x56a08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56a0d  brtrue.s loc_56A44
0x56a0f  br.s     loc_56A85
0x56a11  ldarg.2
0x56a12  ldstr    aNamespaceUri// "namespace-uri"
0x56a17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56a1c  brtrue.s loc_56A48
0x56a1e  br.s     loc_56A85
0x56a20  ldarg.2
0x56a21  ldstr    aNumber// "number"
0x56a26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56a2b  brtrue.s loc_56A50
0x56a2d  br.s     loc_56A85
0x56a2f  ldc.i4.s 0x10
0x56a31  stloc.1
0x56a32  br.s     loc_56A85
0x56a34  ldc.i4.2
0x56a35  stloc.1
0x56a36  br.s     loc_56A85
0x56a38  ldc.i4.1
0x56a39  stloc.1
0x56a3a  br.s     loc_56A85
0x56a3c  ldc.i4.1
0x56a3d  stloc.1
0x56a3e  br.s     loc_56A85
0x56a40  ldc.i4.1
0x56a41  stloc.1
0x56a42  br.s     loc_56A85
0x56a44  ldc.i4.1
0x56a45  stloc.1
0x56a46  br.s     loc_56A85
0x56a48  ldc.i4   0x101
0x56a4d  stloc.1
0x56a4e  br.s     loc_56A85
0x56a50  ldc.i4.2
0x56a51  stloc.1
0x56a52  br.s     loc_56A85
0x56a54  ldloc.s  8
0x56a56  ldstr    aHttpExsltOrgCo// "http://exslt.org/common"
0x56a5b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56a60  brfalse.s loc_56A85
0x56a62  ldarg.2
0x56a63  ldstr    aNodeSet// "node-set"
0x56a68  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56a6d  brtrue.s loc_56A7E
0x56a6f  ldarg.2
0x56a70  ldstr    aObjectType// "object-type"
0x56a75  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56a7a  brtrue.s loc_56A83
0x56a7c  br.s     loc_56A85
0x56a7e  ldc.i4.s 0x10
0x56a80  stloc.1
0x56a81  br.s     loc_56A85
0x56a83  ldc.i4.1
0x56a84  stloc.1
0x56a85  ldloc.1
0x56a86  brtrue   loc_56B6B
0x56a8b  ldc.i4.s 0x3F
0x56a8d  stloc.1
0x56a8e  ldarg.0
0x56a8f  ldfld    class System.Xml.Xsl.Xslt.Compiler XPathAnalyzer::compiler
0x56a94  ldfld    class [System.Xml]System.Xml.Xsl.XsltSettings System.Xml.Xsl.Xslt.Compiler::Settings
0x56a99  callvirt instance bool [System.Xml]System.Xml.Xsl.XsltSettings::get_EnableScript()
0x56a9e  brfalse  loc_56B63
0x56aa3  ldloc.s  8
0x56aa5  brfalse  loc_56B63
0x56aaa  ldarg.0
0x56aab  ldfld    class System.Xml.Xsl.Xslt.Compiler XPathAnalyzer::compiler
0x56ab0  ldfld    class System.Xml.Xsl.Xslt.Scripts System.Xml.Xsl.Xslt.Compiler::Scripts
0x56ab5  ldarg.2
0x56ab6  ldloc.s  8
0x56ab8  ldarg.3
0x56ab9  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype System.Xml.Xsl.XslFlags>::get_Count()
0x56abe  ldloca.s 0xB
0x56ac0  initobj  NullErrorHelper
0x56ac6  ldloc.s  0xB
0x56ac8  box      NullErrorHelper
0x56acd  callvirt instance class System.Xml.Xsl.Runtime.XmlExtensionFunction System.Xml.Xsl.Xslt.Scripts::ResolveFunction(string name, string ns, int32 numArgs, class System.Xml.Xsl.IErrorHelper errorHelper)
0x56ad2  stloc.s  0xA
0x56ad4  ldloc.s  0xA
0x56ad6  brfalse  loc_56B63
0x56adb  ldloc.s  0xA
0x56add  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Runtime.XmlExtensionFunction::get_XmlReturnType()
0x56ae2  stloc.s  0xC
0x56ae4  ldloc.s  0xC
0x56ae6  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x56aeb  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x56af0  brfalse.s loc_56AF6
0x56af2  ldc.i4.1
0x56af3  stloc.1
0x56af4  br.s     loc_56B63
0x56af6  ldloc.s  0xC
0x56af8  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x56afd  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x56b02  brfalse.s loc_56B08
0x56b04  ldc.i4.2
0x56b05  stloc.1
0x56b06  br.s     loc_56B63
0x56b08  ldloc.s  0xC
0x56b0a  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::BooleanX
0x56b0f  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x56b14  brfalse.s loc_56B1A
0x56b16  ldc.i4.4
0x56b17  stloc.1
0x56b18  br.s     loc_56B63
0x56b1a  ldloc.s  0xC
0x56b1c  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeNotRtf
0x56b21  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x56b26  brfalse.s loc_56B2C
0x56b28  ldc.i4.8
0x56b29  stloc.1
0x56b2a  br.s     loc_56B63
0x56b2c  ldloc.s  0xC
0x56b2e  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeSDod
0x56b33  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x56b38  brfalse.s loc_56B3F
0x56b3a  ldc.i4.s 0x10
0x56b3c  stloc.1
0x56b3d  br.s     loc_56B63
0x56b3f  ldloc.s  0xC
0x56b41  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::ItemS
0x56b46  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x56b4b  brfalse.s loc_56B52
0x56b4d  ldc.i4.s 0x3F
0x56b4f  stloc.1
  ... truncated ...
```
