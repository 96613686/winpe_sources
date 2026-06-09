# <P_Arguments>d__10::MoveNext

- ea: `0x320e0`
- end: `0x3232b`
- name: `<P_Arguments>d__10::MoveNext`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x23080`
- `0x24300`
- `0x243b0`
- `0x243d0`
- `0x24430`
- `0x24550`
- `0x24660`
- `0x31af0`
- `0x32080`
- `0x320e0`
- `0x32330`
- `0x32350`
- `0x32370`

## pseudocode

```c

```

## disassembly

```asm
0x320e0  ldarg.0
0x320e1  ldfld    int32 <P_Arguments>d__10::<>1__state
0x320e6  stloc.1
0x320e7  ldarg.0
0x320e8  ldfld    class MS.Internal.Xaml.Parser.MePullParser <P_Arguments>d__10::<>4__this
0x320ed  stloc.2
0x320ee  ldloc.1
0x320ef  switch   loc_3210F, loc_3219C, loc_3220F, loc_32262, loc_322D9
0x32108  ldc.i4.0
0x32109  stloc.0
0x3210a  leave    loc_32329
0x3210f  ldarg.0
0x32110  ldc.i4.m1
0x32111  stfld    int32 <P_Arguments>d__10::<>1__state
0x32116  ldarg.0
0x32117  newobj   instance void Found::.ctor()
0x3211c  stfld    class Found <P_Arguments>d__10::<f2>5__2
0x32121  ldloc.2
0x32122  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32127  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x3212c  stloc.3
0x3212d  ldloc.3
0x3212e  ldc.i4.s 0x30
0x32130  bgt.s    loc_32146
0x32132  ldloc.3
0x32133  ldc.i4.s 0x2E
0x32135  beq      loc_32298
0x3213a  ldloc.3
0x3213b  ldc.i4.s 0x2F
0x3213d  sub
0x3213e  ldc.i4.1
0x3213f  ble.un.s loc_32158
0x32141  br       loc_32313
0x32146  ldloc.3
0x32147  ldc.i4.s 0x7B
0x32149  beq.s    loc_32158
0x3214b  ldloc.3
0x3214c  ldc.i4.s 0x7D
0x3214e  beq      loc_3231E
0x32153  br       loc_32313
0x32158  ldarg.0
0x32159  ldloc.2
0x3215a  ldarg.0
0x3215b  ldfld    class Found <P_Arguments>d__10::<f2>5__2
0x32160  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_PositionalArgs(class Found f)
0x32165  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x3216a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x3216f  ldarg.0
0x32170  ldc.i4.s 0xFD
0x32172  stfld    int32 <P_Arguments>d__10::<>1__state
0x32177  br.s     loc_321A4
0x32179  ldarg.0
0x3217a  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x3217f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x32184  stloc.s  4
0x32186  ldarg.0
0x32187  ldloc.s  4
0x32189  stfld    valuetype System.Xaml.XamlNode <P_Arguments>d__10::<>2__current
0x3218e  ldarg.0
0x3218f  ldc.i4.1
0x32190  stfld    int32 <P_Arguments>d__10::<>1__state
0x32195  ldc.i4.1
0x32196  stloc.0
0x32197  leave    loc_32329
0x3219c  ldarg.0
0x3219d  ldc.i4.s 0xFD
0x3219f  stfld    int32 <P_Arguments>d__10::<>1__state
0x321a4  ldarg.0
0x321a5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x321aa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x321af  brtrue.s loc_32179
0x321b1  ldarg.0
0x321b2  call     instance void <P_Arguments>d__10::<>m__Finally1()
0x321b7  ldarg.0
0x321b8  ldnull
0x321b9  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x321be  ldarg.0
0x321bf  ldfld    class Found <P_Arguments>d__10::f
0x321c4  ldarg.0
0x321c5  ldfld    class Found <P_Arguments>d__10::<f2>5__2
0x321ca  ldfld    bool Found::found
0x321cf  stfld    bool Found::found
0x321d4  ldarg.0
0x321d5  ldfld    class Found <P_Arguments>d__10::f
0x321da  ldfld    bool Found::found
0x321df  brfalse  loc_32284
0x321e4  ldloc.2
0x321e5  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x321ea  callvirt instance int32 MS.Internal.Xaml.Context.XamlParserContext::get_CurrentArgCount()
0x321ef  ldc.i4.0
0x321f0  ble      loc_32284
0x321f5  ldarg.0
0x321f6  ldloc.2
0x321f7  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_EndPositionalParameters()
0x321fc  stfld    valuetype System.Xaml.XamlNode <P_Arguments>d__10::<>2__current
0x32201  ldarg.0
0x32202  ldc.i4.2
0x32203  stfld    int32 <P_Arguments>d__10::<>1__state
0x32208  ldc.i4.1
0x32209  stloc.0
0x3220a  leave    loc_32329
0x3220f  ldarg.0
0x32210  ldc.i4.m1
0x32211  stfld    int32 <P_Arguments>d__10::<>1__state
0x32216  br.s     loc_32284
0x32218  ldloc.2
0x32219  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x3221e  ldarg.0
0x3221f  ldloc.2
0x32220  ldarg.0
0x32221  ldfld    class Found <P_Arguments>d__10::<f2>5__2
0x32226  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_NamedArgs(class Found f)
0x3222b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x32230  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x32235  ldarg.0
0x32236  ldc.i4.s 0xFC
0x32238  stfld    int32 <P_Arguments>d__10::<>1__state
0x3223d  br.s     loc_3226A
0x3223f  ldarg.0
0x32240  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x32245  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x3224a  stloc.s  5
0x3224c  ldarg.0
0x3224d  ldloc.s  5
0x3224f  stfld    valuetype System.Xaml.XamlNode <P_Arguments>d__10::<>2__current
0x32254  ldarg.0
0x32255  ldc.i4.3
0x32256  stfld    int32 <P_Arguments>d__10::<>1__state
0x3225b  ldc.i4.1
0x3225c  stloc.0
0x3225d  leave    loc_32329
0x32262  ldarg.0
0x32263  ldc.i4.s 0xFC
0x32265  stfld    int32 <P_Arguments>d__10::<>1__state
0x3226a  ldarg.0
0x3226b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x32270  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32275  brtrue.s loc_3223F
0x32277  ldarg.0
0x32278  call     instance void <P_Arguments>d__10::<>m__Finally2()
0x3227d  ldarg.0
0x3227e  ldnull
0x3227f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x32284  ldloc.2
0x32285  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x3228a  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x3228f  ldc.i4.s 0x2C
0x32291  beq.s    loc_32218
0x32293  br       loc_3231E
0x32298  ldarg.0
0x32299  ldloc.2
0x3229a  ldarg.0
0x3229b  ldfld    class Found <P_Arguments>d__10::<f2>5__2
0x322a0  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_NamedArgs(class Found f)
0x322a5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x322aa  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x322af  ldarg.0
0x322b0  ldc.i4.s 0xFB
0x322b2  stfld    int32 <P_Arguments>d__10::<>1__state
0x322b7  br.s     loc_322E1
0x322b9  ldarg.0
0x322ba  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x322bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x322c4  stloc.s  6
0x322c6  ldarg.0
0x322c7  ldloc.s  6
0x322c9  stfld    valuetype System.Xaml.XamlNode <P_Arguments>d__10::<>2__current
0x322ce  ldarg.0
0x322cf  ldc.i4.4
0x322d0  stfld    int32 <P_Arguments>d__10::<>1__state
0x322d5  ldc.i4.1
0x322d6  stloc.0
0x322d7  leave.s  loc_32329
0x322d9  ldarg.0
0x322da  ldc.i4.s 0xFB
0x322dc  stfld    int32 <P_Arguments>d__10::<>1__state
0x322e1  ldarg.0
0x322e2  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x322e7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x322ec  brtrue.s loc_322B9
0x322ee  ldarg.0
0x322ef  call     instance void <P_Arguments>d__10::<>m__Finally3()
0x322f4  ldarg.0
0x322f5  ldnull
0x322f6  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Arguments>d__10::<>7__wrap2
0x322fb  ldarg.0
0x322fc  ldfld    class Found <P_Arguments>d__10::f
0x32301  ldarg.0
0x32302  ldfld    class Found <P_Arguments>d__10::<f2>5__2
0x32307  ldfld    bool Found::found
0x3230c  stfld    bool Found::found
0x32311  br.s     loc_3231E
0x32313  ldloc.2
0x32314  ldstr    aArgumentsPosit// "Arguments ::= @ (PositionalArgs ( ',' N"...
0x32319  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x3231e  ldc.i4.0
0x3231f  stloc.0
0x32320  leave.s  loc_32329
0x32322  ldarg.0
0x32323  call     instance void <P_Arguments>d__10::System.IDisposable.Dispose()
0x32328  endfinally
0x32329  ldloc.0
0x3232a  ret
```
