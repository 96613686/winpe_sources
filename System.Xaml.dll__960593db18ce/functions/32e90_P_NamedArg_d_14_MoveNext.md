# <P_NamedArg>d__14::MoveNext

- ea: `0x32e90`
- end: `0x33160`
- name: `<P_NamedArg>d__14::MoveNext`
- size: `720`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x84e0`
- `0xa4c0`
- `0xb280`
- `0x11f50`
- `0x23040`
- `0x242c0`
- `0x242d0`
- `0x24300`
- `0x24350`
- `0x243f0`
- `0x24430`
- `0x24440`
- `0x24450`
- `0x244e0`
- `0x24510`
- `0x24580`
- `0x24660`
- `0x24680`
- `0x24690`
- `0x31af0`
- `0x32e50`
- `0x32e90`
- `0x33160`
- `0x33180`

## string_xrefs

- `0x330c7`: `MissingComma1`
- `0x330e9`: `MissingComma2`
- `0x3312b`: `NamedArg ::= PROPERTYNAME '=' @(STRING | QUOTEDMARKUPEXTENSION | MarkupExtension)`

## pseudocode

```c

```

## disassembly

```asm
0x32e90  ldarg.0
0x32e91  ldfld    int32 <P_NamedArg>d__14::<>1__state
0x32e96  stloc.1
0x32e97  ldarg.0
0x32e98  ldfld    class MS.Internal.Xaml.Parser.MePullParser <P_NamedArg>d__14::<>4__this
0x32e9d  stloc.2
0x32e9e  ldloc.1
0x32e9f  switch   loc_32EC3, loc_32F0D, loc_32F79, loc_32FFA, loc_33077, loc_3314C
0x32ebc  ldc.i4.0
0x32ebd  stloc.0
0x32ebe  leave    loc_3315E
0x32ec3  ldarg.0
0x32ec4  ldc.i4.m1
0x32ec5  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32eca  ldarg.0
0x32ecb  newobj   instance void Found::.ctor()
0x32ed0  stfld    class Found <P_NamedArg>d__14::<f2>5__2
0x32ed5  ldloc.2
0x32ed6  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32edb  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x32ee0  ldc.i4.s 0x2E
0x32ee2  bne.un   loc_33153
0x32ee7  ldloc.2
0x32ee8  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32eed  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Parser.MeScanner::get_TokenProperty()
0x32ef2  stloc.3
0x32ef3  ldarg.0
0x32ef4  ldloc.2
0x32ef5  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_StartMember()
0x32efa  stfld    valuetype System.Xaml.XamlNode <P_NamedArg>d__14::<>2__current
0x32eff  ldarg.0
0x32f00  ldc.i4.1
0x32f01  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32f06  ldc.i4.1
0x32f07  stloc.0
0x32f08  leave    loc_3315E
0x32f0d  ldarg.0
0x32f0e  ldc.i4.m1
0x32f0f  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32f14  ldloc.2
0x32f15  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x32f1a  ldloc.2
0x32f1b  ldc.i4.s 0x3D
0x32f1d  ldstr    aNamedargProper// "NamedArg ::= PROPERTYNAME @'=' Value"
0x32f22  call     instance bool MS.Internal.Xaml.Parser.MePullParser::Expect(valuetype MS.Internal.Xaml.Parser.MeTokenType token, string ruleString)
0x32f27  pop
0x32f28  ldloc.2
0x32f29  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x32f2e  ldloc.2
0x32f2f  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32f34  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x32f39  stloc.s  5
0x32f3b  ldloc.s  5
0x32f3d  ldc.i4.s 0x2E
0x32f3f  sub
0x32f40  switch   loc_330B4, loc_32F5F, loc_32F97
0x32f51  ldloc.s  5
0x32f53  ldc.i4.s 0x7B
0x32f55  beq      loc_33033
0x32f5a  br       loc_3312A
0x32f5f  ldarg.0
0x32f60  ldloc.2
0x32f61  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_Text()
0x32f66  stfld    valuetype System.Xaml.XamlNode <P_NamedArg>d__14::<>2__current
0x32f6b  ldarg.0
0x32f6c  ldc.i4.2
0x32f6d  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32f72  ldc.i4.1
0x32f73  stloc.0
0x32f74  leave    loc_3315E
0x32f79  ldarg.0
0x32f7a  ldc.i4.m1
0x32f7b  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32f80  ldarg.0
0x32f81  ldfld    class Found <P_NamedArg>d__14::f
0x32f86  ldc.i4.1
0x32f87  stfld    bool Found::found
0x32f8c  ldloc.2
0x32f8d  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x32f92  br       loc_33135
0x32f97  ldloc.2
0x32f98  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x32f9d  newobj   instance void MS.Internal.Xaml.Parser.MePullParser::.ctor(class MS.Internal.Xaml.Context.XamlParserContext stack)
0x32fa2  stloc.s  4
0x32fa4  ldarg.0
0x32fa5  ldloc.s  4
0x32fa7  ldloc.2
0x32fa8  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32fad  callvirt instance string MS.Internal.Xaml.Parser.MeScanner::get_TokenText()
0x32fb2  ldloc.2
0x32fb3  call     instance int32 MS.Internal.Xaml.Parser.MePullParser::get_LineNumber()
0x32fb8  ldloc.2
0x32fb9  call     instance int32 MS.Internal.Xaml.Parser.MePullParser::get_LinePosition()
0x32fbe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::Parse(string text, int32 lineNumber, int32 linePosition)
0x32fc3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x32fc8  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x32fcd  ldarg.0
0x32fce  ldc.i4.s 0xFD
0x32fd0  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32fd5  br.s     loc_33002
0x32fd7  ldarg.0
0x32fd8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x32fdd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x32fe2  stloc.s  6
0x32fe4  ldarg.0
0x32fe5  ldloc.s  6
0x32fe7  stfld    valuetype System.Xaml.XamlNode <P_NamedArg>d__14::<>2__current
0x32fec  ldarg.0
0x32fed  ldc.i4.3
0x32fee  stfld    int32 <P_NamedArg>d__14::<>1__state
0x32ff3  ldc.i4.1
0x32ff4  stloc.0
0x32ff5  leave    loc_3315E
0x32ffa  ldarg.0
0x32ffb  ldc.i4.s 0xFD
0x32ffd  stfld    int32 <P_NamedArg>d__14::<>1__state
0x33002  ldarg.0
0x33003  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x33008  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3300d  brtrue.s loc_32FD7
0x3300f  ldarg.0
0x33010  call     instance void <P_NamedArg>d__14::<>m__Finally1()
0x33015  ldarg.0
0x33016  ldnull
0x33017  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x3301c  ldarg.0
0x3301d  ldfld    class Found <P_NamedArg>d__14::f
0x33022  ldc.i4.1
0x33023  stfld    bool Found::found
0x33028  ldloc.2
0x33029  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x3302e  br       loc_33135
0x33033  ldarg.0
0x33034  ldloc.2
0x33035  ldarg.0
0x33036  ldfld    class Found <P_NamedArg>d__14::<f2>5__2
0x3303b  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_Value(class Found f)
0x33040  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x33045  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x3304a  ldarg.0
0x3304b  ldc.i4.s 0xFC
0x3304d  stfld    int32 <P_NamedArg>d__14::<>1__state
0x33052  br.s     loc_3307F
0x33054  ldarg.0
0x33055  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x3305a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x3305f  stloc.s  7
0x33061  ldarg.0
0x33062  ldloc.s  7
0x33064  stfld    valuetype System.Xaml.XamlNode <P_NamedArg>d__14::<>2__current
0x33069  ldarg.0
0x3306a  ldc.i4.4
0x3306b  stfld    int32 <P_NamedArg>d__14::<>1__state
0x33070  ldc.i4.1
0x33071  stloc.0
0x33072  leave    loc_3315E
0x33077  ldarg.0
0x33078  ldc.i4.s 0xFC
0x3307a  stfld    int32 <P_NamedArg>d__14::<>1__state
0x3307f  ldarg.0
0x33080  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x33085  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3308a  brtrue.s loc_33054
0x3308c  ldarg.0
0x3308d  call     instance void <P_NamedArg>d__14::<>m__Finally2()
0x33092  ldarg.0
0x33093  ldnull
0x33094  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NamedArg>d__14::<>7__wrap2
0x33099  ldarg.0
0x3309a  ldfld    class Found <P_NamedArg>d__14::f
0x3309f  ldarg.0
0x330a0  ldfld    class Found <P_NamedArg>d__14::<f2>5__2
0x330a5  ldfld    bool Found::found
0x330aa  stfld    bool Found::found
0x330af  br       loc_33135
0x330b4  ldloc.2
0x330b5  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x330ba  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.XamlParserContext::get_CurrentMember()
0x330bf  ldnull
0x330c0  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x330c5  brfalse.s loc_330E9
0x330c7  ldstr    aMissingcomma1// "MissingComma1"
0x330cc  ldc.i4.1
0x330cd  newarr   [mscorlib]System.Object
0x330d2  dup
0x330d3  ldc.i4.0
0x330d4  ldloc.2
0x330d5  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x330da  callvirt instance string MS.Internal.Xaml.Parser.MeScanner::get_TokenText()
0x330df  stelem.ref
0x330e0  call     string System.Xaml.SR::Get(string id, object[] args)
0x330e5  stloc.s  8
0x330e7  br.s     loc_3311C
0x330e9  ldstr    aMissingcomma2// "MissingComma2"
0x330ee  ldc.i4.2
0x330ef  newarr   [mscorlib]System.Object
0x330f4  dup
0x330f5  ldc.i4.0
0x330f6  ldloc.2
0x330f7  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x330fc  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.XamlParserContext::get_CurrentMember()
0x33101  callvirt instance string System.Xaml.XamlMember::get_Name()
0x33106  stelem.ref
0x33107  dup
0x33108  ldc.i4.1
0x33109  ldloc.2
0x3310a  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x3310f  callvirt instance string MS.Internal.Xaml.Parser.MeScanner::get_TokenText()
0x33114  stelem.ref
0x33115  call     string System.Xaml.SR::Get(string id, object[] args)
0x3311a  stloc.s  8
0x3311c  ldloc.2
0x3311d  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x33122  ldloc.s  8
0x33124  newobj   instance void System.Xaml.XamlParseException::.ctor(class MS.Internal.Xaml.Parser.MeScanner meScanner, string message)
0x33129  throw
0x3312a  ldloc.2
0x3312b  ldstr    aNamedargProper_0// "NamedArg ::= PROPERTYNAME '=' @(STRING "...
0x33130  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x33135  ldarg.0
0x33136  ldloc.2
0x33137  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_EndMember()
0x3313c  stfld    valuetype System.Xaml.XamlNode <P_NamedArg>d__14::<>2__current
0x33141  ldarg.0
0x33142  ldc.i4.5
0x33143  stfld    int32 <P_NamedArg>d__14::<>1__state
0x33148  ldc.i4.1
0x33149  stloc.0
0x3314a  leave.s  loc_3315E
0x3314c  ldarg.0
0x3314d  ldc.i4.m1
0x3314e  stfld    int32 <P_NamedArg>d__14::<>1__state
0x33153  ldc.i4.0
0x33154  stloc.0
0x33155  leave.s  loc_3315E
0x33157  ldarg.0
0x33158  call     instance void <P_NamedArg>d__14::System.IDisposable.Dispose()
0x3315d  endfinally
0x3315e  ldloc.0
0x3315f  ret
```
