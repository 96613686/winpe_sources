# <P_PropertyContent>d__13::MoveNext

- ea: `0x35420`
- end: `0x35888`
- name: `<P_PropertyContent>d__13::MoveNext`
- size: `1128`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: ``

## callees

- `0x2100`
- `0x89f0`
- `0xa5d0`
- `0xd430`
- `0x23040`
- `0x231a0`
- `0x25770`
- `0x25820`
- `0x25830`
- `0x25850`
- `0x25880`
- `0x258b0`
- `0x258f0`
- `0x25900`
- `0x25970`
- `0x259f0`
- `0x25b80`
- `0x25b90`
- `0x25ff0`
- `0x26050`
- `0x260b0`
- `0x260c0`
- `0x353e0`
- `0x35420`
- `0x35890`
- `0x358b0`

## pseudocode

```c

```

## disassembly

```asm
0x35420  ldarg.0
0x35421  ldfld    int32 <P_PropertyContent>d__13::<>1__state
0x35426  stloc.1
0x35427  ldarg.0
0x35428  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_PropertyContent>d__13::<>4__this
0x3542d  stloc.2
0x3542e  ldloc.1
0x3542f  switch   loc_3546F, loc_35534, loc_355BF, loc_35624, loc_3567B, loc_356D4, loc_3570A, loc_35731, loc_3575F, loc_3578C, loc_357AE, loc_357F1, loc_35859
0x35468  ldc.i4.0
0x35469  stloc.0
0x3546a  leave    loc_35886
0x3546f  ldarg.0
0x35470  ldc.i4.m1
0x35471  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35476  ldarg.0
0x35477  ldloc.2
0x35478  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3547d  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x35482  stfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x35487  ldarg.0
0x35488  ldnull
0x35489  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<_savedPrefixDefinitions>5__3
0x3548e  ldarg.0
0x3548f  ldsfld   string [mscorlib]System.String::Empty
0x35494  stfld    string <P_PropertyContent>d__13::<trimmed>5__4
0x35499  ldarg.0
0x3549a  ldc.i4.0
0x3549b  stfld    bool <P_PropertyContent>d__13::<isTextXML>5__5
0x354a0  ldarg.0
0x354a1  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x354a6  stloc.3
0x354a7  ldloc.3
0x354a8  ldc.i4.1
0x354a9  sub
0x354aa  ldc.i4.1
0x354ab  ble.un.s loc_354B8
0x354ad  ldloc.3
0x354ae  ldc.i4.5
0x354af  beq.s    loc_354B8
0x354b1  ldloc.3
0x354b2  ldc.i4.8
0x354b3  bne.un   loc_3587B
0x354b8  ldarg.0
0x354b9  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x354be  ldc.i4.8
0x354bf  bne.un   loc_355D7
0x354c4  ldloc.2
0x354c5  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x354ca  callvirt instance class MS.Internal.Xaml.Parser.XamlText MS.Internal.Xaml.Parser.XamlScanner::get_TextContent()
0x354cf  stloc.s  4
0x354d1  ldloc.2
0x354d2  ldloc.s  4
0x354d4  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::Logic_IsDiscardableWhitespace(class MS.Internal.Xaml.Parser.XamlText text)
0x354d9  brfalse.s loc_354E8
0x354db  ldarg.0
0x354dc  ldsfld   string [mscorlib]System.String::Empty
0x354e1  stfld    string <P_PropertyContent>d__13::<trimmed>5__4
0x354e6  br.s     loc_354F6
0x354e8  ldarg.0
0x354e9  ldloc.2
0x354ea  ldloc.s  4
0x354ec  call     instance string MS.Internal.Xaml.Parser.XamlPullParser::Logic_ApplyFinalTextTrimming(class MS.Internal.Xaml.Parser.XamlText text)
0x354f1  stfld    string <P_PropertyContent>d__13::<trimmed>5__4
0x354f6  ldarg.0
0x354f7  ldloc.2
0x354f8  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x354fd  callvirt instance bool MS.Internal.Xaml.Parser.XamlScanner::get_IsXDataText()
0x35502  stfld    bool <P_PropertyContent>d__13::<isTextXML>5__5
0x35507  ldloc.2
0x35508  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3550d  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x35512  ldloc.2
0x35513  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x35518  brfalse.s loc_3553B
0x3551a  ldarg.0
0x3551b  ldloc.2
0x3551c  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x35521  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x35526  ldarg.0
0x35527  ldc.i4.1
0x35528  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x3552d  ldc.i4.1
0x3552e  stloc.0
0x3552f  leave    loc_35886
0x35534  ldarg.0
0x35535  ldc.i4.m1
0x35536  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x3553b  ldarg.0
0x3553c  ldfld    string <P_PropertyContent>d__13::<trimmed>5__4
0x35541  ldsfld   string [mscorlib]System.String::Empty
0x35546  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3554b  brfalse  loc_355D7
0x35550  br       loc_3587B
0x35555  ldarg.0
0x35556  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<_savedPrefixDefinitions>5__3
0x3555b  brtrue.s loc_35568
0x3555d  ldarg.0
0x3555e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::.ctor()
0x35563  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<_savedPrefixDefinitions>5__3
0x35568  ldarg.0
0x35569  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<_savedPrefixDefinitions>5__3
0x3556e  ldloc.2
0x3556f  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_PrefixDefinition()
0x35574  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x35579  ldloc.2
0x3557a  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x3557f  brfalse.s loc_35592
0x35581  ldarg.0
0x35582  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<_savedPrefixDefinitions>5__3
0x35587  ldloc.2
0x35588  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x3558d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x35592  ldloc.2
0x35593  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x35598  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x3559d  ldloc.2
0x3559e  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x355a3  brfalse.s loc_355C6
0x355a5  ldarg.0
0x355a6  ldloc.2
0x355a7  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x355ac  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x355b1  ldarg.0
0x355b2  ldc.i4.2
0x355b3  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x355b8  ldc.i4.1
0x355b9  stloc.0
0x355ba  leave    loc_35886
0x355bf  ldarg.0
0x355c0  ldc.i4.m1
0x355c1  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x355c6  ldarg.0
0x355c7  ldloc.2
0x355c8  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x355cd  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x355d2  stfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x355d7  ldarg.0
0x355d8  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x355dd  ldc.i4.5
0x355de  beq      loc_35555
0x355e3  ldarg.0
0x355e4  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x355e9  ldc.i4.8
0x355ea  bne.un.s loc_35630
0x355ec  ldloc.2
0x355ed  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x355f2  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.XamlParserContext::get_CurrentMember()
0x355f7  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlMember::get_TypeConverter()
0x355fc  ldnull
0x355fd  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x35602  brfalse.s loc_35630
0x35604  ldarg.0
0x35605  ldc.i4.6
0x35606  ldarg.0
0x35607  ldfld    string <P_PropertyContent>d__13::<trimmed>5__4
0x3560c  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x35611  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x35616  ldarg.0
0x35617  ldc.i4.3
0x35618  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x3561d  ldc.i4.1
0x3561e  stloc.0
0x3561f  leave    loc_35886
0x35624  ldarg.0
0x35625  ldc.i4.m1
0x35626  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x3562b  br       loc_3587B
0x35630  ldloc.2
0x35631  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35636  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInCollectionFromMember()
0x3563b  brtrue.s loc_3569D
0x3563d  ldarg.0
0x3563e  ldloc.2
0x3563f  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::LogicStream_CheckForStartGetCollectionFromMember()
0x35644  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x35649  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<>7__wrap5
0x3564e  ldarg.0
0x3564f  ldc.i4.s 0xFD
0x35651  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35656  br.s     loc_35683
0x35658  ldarg.0
0x35659  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<>7__wrap5
0x3565e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x35663  stloc.s  5
0x35665  ldarg.0
0x35666  ldloc.s  5
0x35668  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x3566d  ldarg.0
0x3566e  ldc.i4.4
0x3566f  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35674  ldc.i4.1
0x35675  stloc.0
0x35676  leave    loc_35886
0x3567b  ldarg.0
0x3567c  ldc.i4.s 0xFD
0x3567e  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35683  ldarg.0
0x35684  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<>7__wrap5
0x35689  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3568e  brtrue.s loc_35658
0x35690  ldarg.0
0x35691  call     instance void <P_PropertyContent>d__13::<>m__Finally1()
0x35696  ldarg.0
0x35697  ldnull
0x35698  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PropertyContent>d__13::<>7__wrap5
0x3569d  ldarg.0
0x3569e  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_PropertyContent>d__13::<nodeType>5__2
0x356a3  ldc.i4.8
0x356a4  bne.un   loc_357BA
0x356a9  ldarg.0
0x356aa  ldfld    bool <P_PropertyContent>d__13::<isTextXML>5__5
0x356af  brfalse  loc_3573F
0x356b4  ldarg.0
0x356b5  ldloc.2
0x356b6  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_XData()
0x356bb  ldnull
0x356bc  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartObject(class System.Xaml.XamlType xamlType, string xamlNamespace)
0x356c1  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x356c6  ldarg.0
0x356c7  ldc.i4.5
0x356c8  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x356cd  ldc.i4.1
0x356ce  stloc.0
0x356cf  leave    loc_35886
0x356d4  ldarg.0
0x356d5  ldc.i4.m1
0x356d6  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x356db  ldarg.0
0x356dc  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_XData()
0x356e1  ldstr    aText// "Text"
0x356e6  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetMember(string name)
0x356eb  stfld    class System.Xaml.XamlMember <P_PropertyContent>d__13::<xDataTextProperty>5__7
0x356f0  ldarg.0
0x356f1  ldloc.2
0x356f2  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndOfAttributes()
0x356f7  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x356fc  ldarg.0
0x356fd  ldc.i4.6
0x356fe  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35703  ldc.i4.1
0x35704  stloc.0
0x35705  leave    loc_35886
0x3570a  ldarg.0
0x3570b  ldc.i4.m1
0x3570c  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35711  ldarg.0
0x35712  ldloc.2
0x35713  ldarg.0
0x35714  ldfld    class System.Xaml.XamlMember <P_PropertyContent>d__13::<xDataTextProperty>5__7
0x35719  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartMember(class System.Xaml.XamlMember member)
0x3571e  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x35723  ldarg.0
0x35724  ldc.i4.7
0x35725  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x3572a  ldc.i4.1
0x3572b  stloc.0
0x3572c  leave    loc_35886
0x35731  ldarg.0
0x35732  ldc.i4.m1
0x35733  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35738  ldarg.0
0x35739  ldnull
0x3573a  stfld    class System.Xaml.XamlMember <P_PropertyContent>d__13::<xDataTextProperty>5__7
0x3573f  ldarg.0
0x35740  ldc.i4.6
0x35741  ldarg.0
0x35742  ldfld    string <P_PropertyContent>d__13::<trimmed>5__4
0x35747  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x3574c  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x35751  ldarg.0
0x35752  ldc.i4.8
0x35753  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35758  ldc.i4.1
0x35759  stloc.0
0x3575a  leave    loc_35886
0x3575f  ldarg.0
0x35760  ldc.i4.m1
0x35761  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35766  ldarg.0
0x35767  ldfld    bool <P_PropertyContent>d__13::<isTextXML>5__5
0x3576c  brfalse  loc_3587B
0x35771  ldarg.0
0x35772  ldloc.2
0x35773  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x35778  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x3577d  ldarg.0
0x3577e  ldc.i4.s 9
0x35780  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35785  ldc.i4.1
0x35786  stloc.0
0x35787  leave    loc_35886
0x3578c  ldarg.0
0x3578d  ldc.i4.m1
0x3578e  stfld    int32 <P_PropertyContent>d__13::<>1__state
0x35793  ldarg.0
0x35794  ldloc.2
0x35795  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndObject()
0x3579a  stfld    valuetype System.Xaml.XamlNode <P_PropertyContent>d__13::<>2__current
0x3579f  ldarg.0
0x357a0  ldc.i4.s 0xA
  ... truncated ...
```
