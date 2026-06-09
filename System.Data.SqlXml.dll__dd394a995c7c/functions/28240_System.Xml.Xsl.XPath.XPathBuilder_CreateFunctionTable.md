# System.Xml.Xsl.XPath.XPathBuilder::CreateFunctionTable

- ea: `0x28240`
- end: `0x284d4`
- name: `System.Xml.Xsl.XPath.XPathBuilder::CreateFunctionTable`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x28500`

## string_xrefs

- `0x28289`: `namespace-uri`

## pseudocode

```c

```

## disassembly

```asm
0x28240  ldc.i4.s 0x24
0x28242  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::.ctor(int32)
0x28247  stloc.0
0x28248  ldloc.0
0x28249  ldstr    aLast// "last"
0x2824e  ldc.i4.0
0x2824f  ldc.i4.0
0x28250  ldc.i4.0
0x28251  ldnull
0x28252  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28257  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x2825c  ldloc.0
0x2825d  ldstr    aPosition// "position"
0x28262  ldc.i4.1
0x28263  ldc.i4.0
0x28264  ldc.i4.0
0x28265  ldnull
0x28266  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x2826b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28270  ldloc.0
0x28271  ldstr    aName// "name"
0x28276  ldc.i4.5
0x28277  ldc.i4.0
0x28278  ldc.i4.1
0x28279  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argNodeSet
0x2827e  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28283  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28288  ldloc.0
0x28289  ldstr    aNamespaceUri// "namespace-uri"
0x2828e  ldc.i4.4
0x2828f  ldc.i4.0
0x28290  ldc.i4.1
0x28291  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argNodeSet
0x28296  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x2829b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x282a0  ldloc.0
0x282a1  ldstr    aLocalName// "local-name"
0x282a6  ldc.i4.3
0x282a7  ldc.i4.0
0x282a8  ldc.i4.1
0x282a9  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argNodeSet
0x282ae  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x282b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x282b8  ldloc.0
0x282b9  ldstr    aCount// "count"
0x282be  ldc.i4.2
0x282bf  ldc.i4.1
0x282c0  ldc.i4.1
0x282c1  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argNodeSet
0x282c6  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x282cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x282d0  ldloc.0
0x282d1  ldstr    aId// "id"
0x282d6  ldc.i4.s 0xC
0x282d8  ldc.i4.1
0x282d9  ldc.i4.1
0x282da  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argAny
0x282df  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x282e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x282e9  ldloc.0
0x282ea  ldstr    aString_0// "string"
0x282ef  ldc.i4.6
0x282f0  ldc.i4.0
0x282f1  ldc.i4.1
0x282f2  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argAny
0x282f7  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x282fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28301  ldloc.0
0x28302  ldstr    aConcat// "concat"
0x28307  ldc.i4.s 0xD
0x28309  ldc.i4.2
0x2830a  ldc.i4   0x7FFFFFFF
0x2830f  ldnull
0x28310  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28315  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x2831a  ldloc.0
0x2831b  ldstr    aStartsWith// "starts-with"
0x28320  ldc.i4.s 0xE
0x28322  ldc.i4.2
0x28323  ldc.i4.2
0x28324  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString2
0x28329  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x2832e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28333  ldloc.0
0x28334  ldstr    aContains// "contains"
0x28339  ldc.i4.s 0xF
0x2833b  ldc.i4.2
0x2833c  ldc.i4.2
0x2833d  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString2
0x28342  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28347  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x2834c  ldloc.0
0x2834d  ldstr    aSubstringBefor// "substring-before"
0x28352  ldc.i4.s 0x10
0x28354  ldc.i4.2
0x28355  ldc.i4.2
0x28356  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString2
0x2835b  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28360  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28365  ldloc.0
0x28366  ldstr    aSubstringAfter// "substring-after"
0x2836b  ldc.i4.s 0x11
0x2836d  ldc.i4.2
0x2836e  ldc.i4.2
0x2836f  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString2
0x28374  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28379  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x2837e  ldloc.0
0x2837f  ldstr    aSubstring// "substring"
0x28384  ldc.i4.s 0x12
0x28386  ldc.i4.2
0x28387  ldc.i4.3
0x28388  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argFnSubstr
0x2838d  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28392  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28397  ldloc.0
0x28398  ldstr    aStringLength// "string-length"
0x2839d  ldc.i4.s 0x13
0x2839f  ldc.i4.0
0x283a0  ldc.i4.1
0x283a1  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x283a6  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x283ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x283b0  ldloc.0
0x283b1  ldstr    aNormalizeSpace// "normalize-space"
0x283b6  ldc.i4.s 0x14
0x283b8  ldc.i4.0
0x283b9  ldc.i4.1
0x283ba  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x283bf  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x283c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x283c9  ldloc.0
0x283ca  ldstr    aTranslate// "translate"
0x283cf  ldc.i4.s 0x15
0x283d1  ldc.i4.3
0x283d2  ldc.i4.3
0x283d3  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString3
0x283d8  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x283dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x283e2  ldloc.0
0x283e3  ldstr    aBoolean_0// "boolean"
0x283e8  ldc.i4.8
0x283e9  ldc.i4.1
0x283ea  ldc.i4.1
0x283eb  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argAny
0x283f0  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x283f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x283fa  ldloc.0
0x283fb  ldstr    aNot// "not"
0x28400  ldc.i4.s 0xB
0x28402  ldc.i4.1
0x28403  ldc.i4.1
0x28404  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argBoolean
0x28409  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x2840e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28413  ldloc.0
0x28414  ldstr    aTrue// "true"
0x28419  ldc.i4.s 9
0x2841b  ldc.i4.0
0x2841c  ldc.i4.0
0x2841d  ldnull
0x2841e  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28423  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28428  ldloc.0
0x28429  ldstr    aFalse// "false"
0x2842e  ldc.i4.s 0xA
0x28430  ldc.i4.0
0x28431  ldc.i4.0
0x28432  ldnull
0x28433  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28438  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x2843d  ldloc.0
0x2843e  ldstr    aLang// "lang"
0x28443  ldc.i4.s 0x16
0x28445  ldc.i4.1
0x28446  ldc.i4.1
0x28447  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argString
0x2844c  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28451  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28456  ldloc.0
0x28457  ldstr    aNumber// "number"
0x2845c  ldc.i4.7
0x2845d  ldc.i4.0
0x2845e  ldc.i4.1
0x2845f  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argAny
0x28464  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28469  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x2846e  ldloc.0
0x2846f  ldstr    aSum// "sum"
0x28474  ldc.i4.s 0x17
0x28476  ldc.i4.1
0x28477  ldc.i4.1
0x28478  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argNodeSet
0x2847d  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x28482  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x28487  ldloc.0
0x28488  ldstr    aFloor// "floor"
0x2848d  ldc.i4.s 0x18
0x2848f  ldc.i4.1
0x28490  ldc.i4.1
0x28491  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argDouble
0x28496  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x2849b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x284a0  ldloc.0
0x284a1  ldstr    aCeiling// "ceiling"
0x284a6  ldc.i4.s 0x19
0x284a8  ldc.i4.1
0x284a9  ldc.i4.1
0x284aa  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argDouble
0x284af  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x284b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x284b9  ldloc.0
0x284ba  ldstr    aRound// "round"
0x284bf  ldc.i4.s 0x1A
0x284c1  ldc.i4.1
0x284c2  ldc.i4.1
0x284c3  ldsfld   valuetype [System.Xml]System.Xml.Schema.XmlTypeCode[] System.Xml.Xsl.XPath.XPathBuilder::argDouble
0x284c8  newobj   instance void class FunctionInfo`1<valuetype FuncId>::.ctor(var<u1>, !!T0, int32, int32)
0x284cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class FunctionInfo`1<valuetype FuncId>>::Add(var<u1>, !!T0)
0x284d2  ldloc.0
0x284d3  ret
```
