# <P_ElementBody>d__8::MoveNext

- ea: `0x33e50`
- end: `0x34329`
- name: `<P_ElementBody>d__8::MoveNext`
- size: `1241`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: ``

## callees

- `0x2100`
- `0xd0f0`
- `0xd120`
- `0xd310`
- `0x11f20`
- `0x22ec0`
- `0x23100`
- `0x23120`
- `0x23140`
- `0x23160`
- `0x23180`
- `0x231a0`
- `0x231c0`
- `0x257b0`
- `0x257e0`
- `0x25820`
- `0x25830`
- `0x258b0`
- `0x258e0`
- `0x258f0`
- `0x25970`
- `0x259d0`
- `0x25df0`
- `0x25ff0`
- `0x26050`
- `0x33df0`
- `0x33e50`
- `0x34330`
- `0x34350`
- `0x34370`

## pseudocode

```c

```

## disassembly

```asm
0x33e50  ldarg.0
0x33e51  ldfld    int32 <P_ElementBody>d__8::<>1__state
0x33e56  stloc.1
0x33e57  ldarg.0
0x33e58  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_ElementBody>d__8::<>4__this
0x33e5d  stloc.2
0x33e5e  ldloc.1
0x33e5f  switch   loc_33EAB, loc_33EF3, loc_33F42, loc_33F74, loc_3400D, loc_34079, loc_34103, loc_34134, loc_34155, loc_3419F, loc_341C1, loc_34230, loc_34257, loc_34279, loc_342E3, loc_34315
0x33ea4  ldc.i4.0
0x33ea5  stloc.0
0x33ea6  leave    loc_34327
0x33eab  ldarg.0
0x33eac  ldc.i4.m1
0x33ead  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33eb2  br       loc_33F49
0x33eb7  ldarg.0
0x33eb8  ldloc.2
0x33eb9  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::LogicStream_Attribute()
0x33ebe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x33ec3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x33ec8  ldarg.0
0x33ec9  ldc.i4.s 0xFD
0x33ecb  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33ed0  br.s     loc_33EFB
0x33ed2  ldarg.0
0x33ed3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x33ed8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x33edd  stloc.3
0x33ede  ldarg.0
0x33edf  ldloc.3
0x33ee0  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x33ee5  ldarg.0
0x33ee6  ldc.i4.1
0x33ee7  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33eec  ldc.i4.1
0x33eed  stloc.0
0x33eee  leave    loc_34327
0x33ef3  ldarg.0
0x33ef4  ldc.i4.s 0xFD
0x33ef6  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33efb  ldarg.0
0x33efc  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x33f01  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33f06  brtrue.s loc_33ED2
0x33f08  ldarg.0
0x33f09  call     instance void <P_ElementBody>d__8::<>m__Finally1()
0x33f0e  ldarg.0
0x33f0f  ldnull
0x33f10  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x33f15  ldloc.2
0x33f16  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33f1b  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x33f20  ldloc.2
0x33f21  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x33f26  brfalse.s loc_33F49
0x33f28  ldarg.0
0x33f29  ldloc.2
0x33f2a  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x33f2f  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x33f34  ldarg.0
0x33f35  ldc.i4.2
0x33f36  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33f3b  ldc.i4.1
0x33f3c  stloc.0
0x33f3d  leave    loc_34327
0x33f42  ldarg.0
0x33f43  ldc.i4.m1
0x33f44  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33f49  ldloc.2
0x33f4a  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33f4f  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33f54  ldc.i4.3
0x33f55  beq      loc_33EB7
0x33f5a  ldarg.0
0x33f5b  ldloc.2
0x33f5c  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndOfAttributes()
0x33f61  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x33f66  ldarg.0
0x33f67  ldc.i4.3
0x33f68  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33f6d  ldc.i4.1
0x33f6e  stloc.0
0x33f6f  leave    loc_34327
0x33f74  ldarg.0
0x33f75  ldc.i4.m1
0x33f76  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33f7b  ldarg.0
0x33f7c  ldc.i4.0
0x33f7d  stfld    bool <P_ElementBody>d__8::<doneWithElementContent>5__2
0x33f82  ldarg.0
0x33f83  ldc.i4.0
0x33f84  stfld    bool <P_ElementBody>d__8::<hasContent>5__3
0x33f89  ldloc.2
0x33f8a  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33f8f  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33f94  stloc.s  4
0x33f96  ldloc.s  4
0x33f98  ldc.i4.1
0x33f99  sub
0x33f9a  switch   loc_34034, loc_34034, loc_34289, loc_34289, loc_34034, loc_33FC8, loc_33FC8, loc_34034, loc_341CD
0x33fc3  br       loc_34289
0x33fc8  ldarg.0
0x33fc9  ldc.i4.1
0x33fca  stfld    bool <P_ElementBody>d__8::<hasContent>5__3
0x33fcf  ldarg.0
0x33fd0  ldloc.2
0x33fd1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::P_PropertyElement()
0x33fd6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x33fdb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x33fe0  ldarg.0
0x33fe1  ldc.i4.s 0xFC
0x33fe3  stfld    int32 <P_ElementBody>d__8::<>1__state
0x33fe8  br.s     loc_34015
0x33fea  ldarg.0
0x33feb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x33ff0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x33ff5  stloc.s  8
0x33ff7  ldarg.0
0x33ff8  ldloc.s  8
0x33ffa  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x33fff  ldarg.0
0x34000  ldc.i4.4
0x34001  stfld    int32 <P_ElementBody>d__8::<>1__state
0x34006  ldc.i4.1
0x34007  stloc.0
0x34008  leave    loc_34327
0x3400d  ldarg.0
0x3400e  ldc.i4.s 0xFC
0x34010  stfld    int32 <P_ElementBody>d__8::<>1__state
0x34015  ldarg.0
0x34016  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x3401b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34020  brtrue.s loc_33FEA
0x34022  ldarg.0
0x34023  call     instance void <P_ElementBody>d__8::<>m__Finally2()
0x34028  ldarg.0
0x34029  ldnull
0x3402a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x3402f  br       loc_34290
0x34034  ldarg.0
0x34035  ldc.i4.1
0x34036  stfld    bool <P_ElementBody>d__8::<hasContent>5__3
0x3403b  ldarg.0
0x3403c  ldloc.2
0x3403d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::P_ElementContent()
0x34042  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x34047  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x3404c  ldarg.0
0x3404d  ldc.i4.s 0xFB
0x3404f  stfld    int32 <P_ElementBody>d__8::<>1__state
0x34054  br.s     loc_34081
0x34056  ldarg.0
0x34057  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x3405c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x34061  stloc.s  9
0x34063  ldarg.0
0x34064  ldloc.s  9
0x34066  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x3406b  ldarg.0
0x3406c  ldc.i4.5
0x3406d  stfld    int32 <P_ElementBody>d__8::<>1__state
0x34072  ldc.i4.1
0x34073  stloc.0
0x34074  leave    loc_34327
0x34079  ldarg.0
0x3407a  ldc.i4.s 0xFB
0x3407c  stfld    int32 <P_ElementBody>d__8::<>1__state
0x34081  ldarg.0
0x34082  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x34087  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3408c  brtrue.s loc_34056
0x3408e  ldarg.0
0x3408f  call     instance void <P_ElementBody>d__8::<>m__Finally3()
0x34094  ldarg.0
0x34095  ldnull
0x34096  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementBody>d__8::<>7__wrap3
0x3409b  ldloc.2
0x3409c  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x340a1  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x340a6  stloc.s  4
0x340a8  ldloc.s  4
0x340aa  ldc.i4.5
0x340ab  beq.s    loc_3403B
0x340ad  ldloc.s  4
0x340af  ldc.i4.1
0x340b0  beq.s    loc_3403B
0x340b2  ldloc.s  4
0x340b4  ldc.i4.2
0x340b5  beq.s    loc_3403B
0x340b7  ldloc.s  4
0x340b9  ldc.i4.8
0x340ba  beq      loc_3403B
0x340bf  ldloc.2
0x340c0  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x340c5  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInItemsProperty()
0x340ca  brtrue.s loc_340E9
0x340cc  ldloc.2
0x340cd  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x340d2  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInInitProperty()
0x340d7  brtrue.s loc_340E9
0x340d9  ldloc.2
0x340da  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x340df  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInUnknownContent()
0x340e4  brfalse  loc_34290
0x340e9  ldarg.0
0x340ea  ldloc.2
0x340eb  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x340f0  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x340f5  ldarg.0
0x340f6  ldc.i4.6
0x340f7  stfld    int32 <P_ElementBody>d__8::<>1__state
0x340fc  ldc.i4.1
0x340fd  stloc.0
0x340fe  leave    loc_34327
0x34103  ldarg.0
0x34104  ldc.i4.m1
0x34105  stfld    int32 <P_ElementBody>d__8::<>1__state
0x3410a  ldloc.2
0x3410b  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34110  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInCollectionFromMember()
0x34115  brfalse  loc_34290
0x3411a  ldarg.0
0x3411b  ldloc.2
0x3411c  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndObject()
0x34121  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x34126  ldarg.0
0x34127  ldc.i4.7
0x34128  stfld    int32 <P_ElementBody>d__8::<>1__state
0x3412d  ldc.i4.1
0x3412e  stloc.0
0x3412f  leave    loc_34327
0x34134  ldarg.0
0x34135  ldc.i4.m1
0x34136  stfld    int32 <P_ElementBody>d__8::<>1__state
0x3413b  ldarg.0
0x3413c  ldloc.2
0x3413d  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x34142  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x34147  ldarg.0
0x34148  ldc.i4.8
0x34149  stfld    int32 <P_ElementBody>d__8::<>1__state
0x3414e  ldc.i4.1
0x3414f  stloc.0
0x34150  leave    loc_34327
0x34155  ldarg.0
0x34156  ldc.i4.m1
0x34157  stfld    int32 <P_ElementBody>d__8::<>1__state
0x3415c  ldloc.2
0x3415d  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34162  ldc.i4.0
0x34163  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentInCollectionFromMember(bool value)
0x34168  ldloc.2
0x34169  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x3416e  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInImplicitArray()
0x34173  brfalse  loc_34290
0x34178  ldloc.2
0x34179  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x3417e  ldc.i4.0
0x3417f  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentInImplicitArray(bool value)
0x34184  ldarg.0
0x34185  ldloc.2
0x34186  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndObject()
0x3418b  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x34190  ldarg.0
0x34191  ldc.i4.s 9
0x34193  stfld    int32 <P_ElementBody>d__8::<>1__state
0x34198  ldc.i4.1
0x34199  stloc.0
0x3419a  leave    loc_34327
0x3419f  ldarg.0
0x341a0  ldc.i4.m1
0x341a1  stfld    int32 <P_ElementBody>d__8::<>1__state
0x341a6  ldarg.0
0x341a7  ldloc.2
0x341a8  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x341ad  stfld    valuetype System.Xaml.XamlNode <P_ElementBody>d__8::<>2__current
0x341b2  ldarg.0
0x341b3  ldc.i4.s 0xA
0x341b5  stfld    int32 <P_ElementBody>d__8::<>1__state
0x341ba  ldc.i4.1
0x341bb  stloc.0
0x341bc  leave    loc_34327
0x341c1  ldarg.0
0x341c2  ldc.i4.m1
0x341c3  stfld    int32 <P_ElementBody>d__8::<>1__state
0x341c8  br       loc_34290
0x341cd  ldloc.2
0x341ce  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x341d3  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlParserContext::get_CurrentType()
0x341d8  stloc.s  5
0x341da  ldloc.s  5
0x341dc  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlType::get_TypeConverter()
0x341e1  ldnull
0x341e2  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x341e7  stloc.s  6
0x341e9  ldloc.s  5
0x341eb  callvirt instance bool System.Xaml.XamlType::get_IsConstructible()
0x341f0  brfalse.s loc_341FE
0x341f2  ldloc.s  5
0x341f4  callvirt instance bool System.Xaml.XamlType::get_ConstructionRequiresArguments()
  ... truncated ...
```
