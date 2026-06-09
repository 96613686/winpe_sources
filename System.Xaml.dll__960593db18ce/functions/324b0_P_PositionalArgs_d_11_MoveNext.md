# <P_PositionalArgs>d__11::MoveNext

- ea: `0x324b0`
- end: `0x32779`
- name: `<P_PositionalArgs>d__11::MoveNext`
- size: `713`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x23080`
- `0x230a0`
- `0x24300`
- `0x243b0`
- `0x243f0`
- `0x24410`
- `0x24430`
- `0x24530`
- `0x24550`
- `0x24660`
- `0x31af0`
- `0x32450`
- `0x324b0`
- `0x32780`
- `0x327a0`
- `0x327c0`

## pseudocode

```c

```

## disassembly

```asm
0x324b0  ldarg.0
0x324b1  ldfld    int32 <P_PositionalArgs>d__11::<>1__state
0x324b6  stloc.1
0x324b7  ldarg.0
0x324b8  ldfld    class MS.Internal.Xaml.Parser.MePullParser <P_PositionalArgs>d__11::<>4__this
0x324bd  stloc.2
0x324be  ldloc.1
0x324bf  switch   loc_324E3, loc_3254D, loc_32598, loc_32654, loc_326C7, loc_3270F
0x324dc  ldc.i4.0
0x324dd  stloc.0
0x324de  leave    loc_32777
0x324e3  ldarg.0
0x324e4  ldc.i4.m1
0x324e5  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x324ea  ldarg.0
0x324eb  newobj   instance void Found::.ctor()
0x324f0  stfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x324f5  ldloc.2
0x324f6  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x324fb  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x32500  stloc.3
0x32501  ldloc.3
0x32502  ldc.i4.s 0x2E
0x32504  beq      loc_3269F
0x32509  ldloc.3
0x3250a  ldc.i4.s 0x2F
0x3250c  sub
0x3250d  ldc.i4.1
0x3250e  ble.un.s loc_32518
0x32510  ldloc.3
0x32511  ldc.i4.s 0x7B
0x32513  bne.un   loc_32761
0x32518  ldloc.2
0x32519  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x3251e  dup
0x3251f  callvirt instance int32 MS.Internal.Xaml.Context.XamlParserContext::get_CurrentArgCount()
0x32524  stloc.s  4
0x32526  ldloc.s  4
0x32528  ldc.i4.1
0x32529  add
0x3252a  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentArgCount(int32 value)
0x3252f  ldloc.s  4
0x32531  brtrue.s loc_32554
0x32533  ldarg.0
0x32534  ldloc.2
0x32535  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_StartPositionalParameters()
0x3253a  stfld    valuetype System.Xaml.XamlNode <P_PositionalArgs>d__11::<>2__current
0x3253f  ldarg.0
0x32540  ldc.i4.1
0x32541  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x32546  ldc.i4.1
0x32547  stloc.0
0x32548  leave    loc_32777
0x3254d  ldarg.0
0x3254e  ldc.i4.m1
0x3254f  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x32554  ldarg.0
0x32555  ldloc.2
0x32556  ldarg.0
0x32557  ldfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x3255c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_Value(class Found f)
0x32561  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x32566  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x3256b  ldarg.0
0x3256c  ldc.i4.s 0xFD
0x3256e  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x32573  br.s     loc_325A0
0x32575  ldarg.0
0x32576  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x3257b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x32580  stloc.s  5
0x32582  ldarg.0
0x32583  ldloc.s  5
0x32585  stfld    valuetype System.Xaml.XamlNode <P_PositionalArgs>d__11::<>2__current
0x3258a  ldarg.0
0x3258b  ldc.i4.2
0x3258c  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x32591  ldc.i4.1
0x32592  stloc.0
0x32593  leave    loc_32777
0x32598  ldarg.0
0x32599  ldc.i4.s 0xFD
0x3259b  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x325a0  ldarg.0
0x325a1  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x325a6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x325ab  brtrue.s loc_32575
0x325ad  ldarg.0
0x325ae  call     instance void <P_PositionalArgs>d__11::<>m__Finally1()
0x325b3  ldarg.0
0x325b4  ldnull
0x325b5  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x325ba  ldarg.0
0x325bb  ldfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x325c0  ldfld    bool Found::found
0x325c5  brtrue.s loc_325D7
0x325c7  ldloc.2
0x325c8  ldstr    aPositionalargs// "PositionalArgs ::= (NamedArg | (@Value "...
0x325cd  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x325d2  br       loc_3276C
0x325d7  ldarg.0
0x325d8  ldfld    class Found <P_PositionalArgs>d__11::f
0x325dd  ldarg.0
0x325de  ldfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x325e3  ldfld    bool Found::found
0x325e8  stfld    bool Found::found
0x325ed  ldloc.2
0x325ee  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x325f3  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x325f8  ldc.i4.s 0x2C
0x325fa  bne.un   loc_3276C
0x325ff  ldarg.0
0x32600  newobj   instance void Found::.ctor()
0x32605  stfld    class Found <P_PositionalArgs>d__11::<f3>5__4
0x3260a  ldloc.2
0x3260b  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x32610  ldarg.0
0x32611  ldloc.2
0x32612  ldarg.0
0x32613  ldfld    class Found <P_PositionalArgs>d__11::<f3>5__4
0x32618  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_PositionalArgs(class Found f)
0x3261d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x32622  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x32627  ldarg.0
0x32628  ldc.i4.s 0xFC
0x3262a  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x3262f  br.s     loc_3265C
0x32631  ldarg.0
0x32632  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x32637  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x3263c  stloc.s  6
0x3263e  ldarg.0
0x3263f  ldloc.s  6
0x32641  stfld    valuetype System.Xaml.XamlNode <P_PositionalArgs>d__11::<>2__current
0x32646  ldarg.0
0x32647  ldc.i4.3
0x32648  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x3264d  ldc.i4.1
0x3264e  stloc.0
0x3264f  leave    loc_32777
0x32654  ldarg.0
0x32655  ldc.i4.s 0xFC
0x32657  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x3265c  ldarg.0
0x3265d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x32662  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32667  brtrue.s loc_32631
0x32669  ldarg.0
0x3266a  call     instance void <P_PositionalArgs>d__11::<>m__Finally2()
0x3266f  ldarg.0
0x32670  ldnull
0x32671  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x32676  ldarg.0
0x32677  ldfld    class Found <P_PositionalArgs>d__11::<f3>5__4
0x3267c  ldfld    bool Found::found
0x32681  brtrue.s loc_32693
0x32683  ldloc.2
0x32684  ldstr    aPositionalargs_0// "PositionalArgs ::= (Value (',' @ Positi"...
0x32689  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x3268e  br       loc_3276C
0x32693  ldarg.0
0x32694  ldnull
0x32695  stfld    class Found <P_PositionalArgs>d__11::<f3>5__4
0x3269a  br       loc_3276C
0x3269f  ldloc.2
0x326a0  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x326a5  callvirt instance int32 MS.Internal.Xaml.Context.XamlParserContext::get_CurrentArgCount()
0x326aa  ldc.i4.0
0x326ab  ble.s    loc_326CE
0x326ad  ldarg.0
0x326ae  ldloc.2
0x326af  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_EndPositionalParameters()
0x326b4  stfld    valuetype System.Xaml.XamlNode <P_PositionalArgs>d__11::<>2__current
0x326b9  ldarg.0
0x326ba  ldc.i4.4
0x326bb  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x326c0  ldc.i4.1
0x326c1  stloc.0
0x326c2  leave    loc_32777
0x326c7  ldarg.0
0x326c8  ldc.i4.m1
0x326c9  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x326ce  ldarg.0
0x326cf  ldloc.2
0x326d0  ldarg.0
0x326d1  ldfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x326d6  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_NamedArg(class Found f)
0x326db  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x326e0  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x326e5  ldarg.0
0x326e6  ldc.i4.s 0xFB
0x326e8  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x326ed  br.s     loc_32717
0x326ef  ldarg.0
0x326f0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x326f5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x326fa  stloc.s  7
0x326fc  ldarg.0
0x326fd  ldloc.s  7
0x326ff  stfld    valuetype System.Xaml.XamlNode <P_PositionalArgs>d__11::<>2__current
0x32704  ldarg.0
0x32705  ldc.i4.5
0x32706  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x3270b  ldc.i4.1
0x3270c  stloc.0
0x3270d  leave.s  loc_32777
0x3270f  ldarg.0
0x32710  ldc.i4.s 0xFB
0x32712  stfld    int32 <P_PositionalArgs>d__11::<>1__state
0x32717  ldarg.0
0x32718  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x3271d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32722  brtrue.s loc_326EF
0x32724  ldarg.0
0x32725  call     instance void <P_PositionalArgs>d__11::<>m__Finally3()
0x3272a  ldarg.0
0x3272b  ldnull
0x3272c  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_PositionalArgs>d__11::<>7__wrap2
0x32731  ldarg.0
0x32732  ldfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x32737  ldfld    bool Found::found
0x3273c  brtrue.s loc_32749
0x3273e  ldloc.2
0x3273f  ldstr    aPositionalargs_1// "PositionalArgs ::= (Value (',' Position"...
0x32744  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x32749  ldarg.0
0x3274a  ldfld    class Found <P_PositionalArgs>d__11::f
0x3274f  ldarg.0
0x32750  ldfld    class Found <P_PositionalArgs>d__11::<f2>5__2
0x32755  ldfld    bool Found::found
0x3275a  stfld    bool Found::found
0x3275f  br.s     loc_3276C
0x32761  ldloc.2
0x32762  ldstr    aPositionalargs_2// "PositionalArgs ::= @ (Value (',' Positi"...
0x32767  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x3276c  ldc.i4.0
0x3276d  stloc.0
0x3276e  leave.s  loc_32777
0x32770  ldarg.0
0x32771  call     instance void <P_PositionalArgs>d__11::System.IDisposable.Dispose()
0x32776  endfinally
0x32777  ldloc.0
0x32778  ret
```
