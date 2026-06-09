# <Parse>d__6::MoveNext

- ea: `0x31b50`
- end: `0x31c97`
- name: `<Parse>d__6::MoveNext`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x84e0`
- `0x11f20`
- `0x24370`
- `0x24430`
- `0x245e0`
- `0x24660`
- `0x246c0`
- `0x31af0`
- `0x31b30`
- `0x31b50`
- `0x31ca0`

## string_xrefs

- `0x31c57`: `UnexpectedTokenAfterME`

## pseudocode

```c

```

## disassembly

```asm
0x31b50  ldarg.0
0x31b51  ldfld    int32 <Parse>d__6::<>1__state
0x31b56  stloc.1
0x31b57  ldarg.0
0x31b58  ldfld    class MS.Internal.Xaml.Parser.MePullParser <Parse>d__6::<>4__this
0x31b5d  stloc.2
0x31b5e  ldloc.1
0x31b5f  brfalse.s loc_31B6F
0x31b61  ldloc.1
0x31b62  ldc.i4.1
0x31b63  beq      loc_31BF8
0x31b68  ldc.i4.0
0x31b69  stloc.0
0x31b6a  leave    loc_31C95
0x31b6f  ldarg.0
0x31b70  ldc.i4.m1
0x31b71  stfld    int32 <Parse>d__6::<>1__state
0x31b76  ldloc.2
0x31b77  ldloc.2
0x31b78  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x31b7d  ldarg.0
0x31b7e  ldfld    string <Parse>d__6::text
0x31b83  ldarg.0
0x31b84  ldfld    int32 <Parse>d__6::lineNumber
0x31b89  ldarg.0
0x31b8a  ldfld    int32 <Parse>d__6::linePosition
0x31b8f  newobj   instance void MS.Internal.Xaml.Parser.MeScanner::.ctor(class MS.Internal.Xaml.Context.XamlParserContext context, string text, int32 lineNumber, int32 linePosition)
0x31b94  stfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31b99  ldloc.2
0x31b9a  ldarg.0
0x31b9b  ldfld    string <Parse>d__6::text
0x31ba0  stfld    string MS.Internal.Xaml.Parser.MePullParser::_originalText
0x31ba5  ldarg.0
0x31ba6  newobj   instance void Found::.ctor()
0x31bab  stfld    class Found <Parse>d__6::<f>5__2
0x31bb0  ldloc.2
0x31bb1  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x31bb6  ldarg.0
0x31bb7  ldloc.2
0x31bb8  ldarg.0
0x31bb9  ldfld    class Found <Parse>d__6::<f>5__2
0x31bbe  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_MarkupExtension(class Found f)
0x31bc3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x31bc8  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <Parse>d__6::<>7__wrap2
0x31bcd  ldarg.0
0x31bce  ldc.i4.s 0xFD
0x31bd0  stfld    int32 <Parse>d__6::<>1__state
0x31bd5  br.s     loc_31C00
0x31bd7  ldarg.0
0x31bd8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <Parse>d__6::<>7__wrap2
0x31bdd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x31be2  stloc.3
0x31be3  ldarg.0
0x31be4  ldloc.3
0x31be5  stfld    valuetype System.Xaml.XamlNode <Parse>d__6::<>2__current
0x31bea  ldarg.0
0x31beb  ldc.i4.1
0x31bec  stfld    int32 <Parse>d__6::<>1__state
0x31bf1  ldc.i4.1
0x31bf2  stloc.0
0x31bf3  leave    loc_31C95
0x31bf8  ldarg.0
0x31bf9  ldc.i4.s 0xFD
0x31bfb  stfld    int32 <Parse>d__6::<>1__state
0x31c00  ldarg.0
0x31c01  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <Parse>d__6::<>7__wrap2
0x31c06  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31c0b  brtrue.s loc_31BD7
0x31c0d  ldarg.0
0x31c0e  call     instance void <Parse>d__6::<>m__Finally1()
0x31c13  ldarg.0
0x31c14  ldnull
0x31c15  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <Parse>d__6::<>7__wrap2
0x31c1a  ldarg.0
0x31c1b  ldfld    class Found <Parse>d__6::<f>5__2
0x31c20  ldfld    bool Found::found
0x31c25  brtrue.s loc_31C44
0x31c27  ldloc.2
0x31c28  ldfld    string MS.Internal.Xaml.Parser.MePullParser::_brokenRule
0x31c2d  stloc.s  4
0x31c2f  ldloc.2
0x31c30  ldnull
0x31c31  stfld    string MS.Internal.Xaml.Parser.MePullParser::_brokenRule
0x31c36  ldloc.2
0x31c37  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31c3c  ldloc.s  4
0x31c3e  newobj   instance void System.Xaml.XamlParseException::.ctor(class MS.Internal.Xaml.Parser.MeScanner meScanner, string message)
0x31c43  throw
0x31c44  ldloc.2
0x31c45  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31c4a  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x31c4f  brfalse.s loc_31C67
0x31c51  ldloc.2
0x31c52  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31c57  ldstr    aUnexpectedtoke_0// "UnexpectedTokenAfterME"
0x31c5c  call     string System.Xaml.SR::Get(string id)
0x31c61  newobj   instance void System.Xaml.XamlParseException::.ctor(class MS.Internal.Xaml.Parser.MeScanner meScanner, string message)
0x31c66  throw
0x31c67  ldloc.2
0x31c68  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31c6d  callvirt instance bool MS.Internal.Xaml.Parser.MeScanner::get_HasTrailingWhitespace()
0x31c72  brfalse.s loc_31C8A
0x31c74  ldloc.2
0x31c75  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31c7a  ldstr    aWhitespaceafte// "WhitespaceAfterME"
0x31c7f  call     string System.Xaml.SR::Get(string id)
0x31c84  newobj   instance void System.Xaml.XamlParseException::.ctor(class MS.Internal.Xaml.Parser.MeScanner meScanner, string message)
0x31c89  throw
0x31c8a  ldc.i4.0
0x31c8b  stloc.0
0x31c8c  leave.s  loc_31C95
0x31c8e  ldarg.0
0x31c8f  call     instance void <Parse>d__6::System.IDisposable.Dispose()
0x31c94  endfinally
0x31c95  ldloc.0
0x31c96  ret
```
