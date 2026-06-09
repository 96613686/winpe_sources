# <P_MarkupExtension>d__9::MoveNext

- ea: `0x31db0`
- end: `0x31f93`
- name: `<P_MarkupExtension>d__9::MoveNext`
- size: `483`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x24300`
- `0x24350`
- `0x24390`
- `0x24430`
- `0x24460`
- `0x244c0`
- `0x24650`
- `0x24660`
- `0x24670`
- `0x31af0`
- `0x31d90`
- `0x31db0`
- `0x31fa0`

## string_xrefs

- `0x31de9`: `MarkupExtension ::= @'{' Expr '}'`
- `0x31f1c`: `MarkupExtension ::= '{' TYPENAME @(Arguments)? '}'`
- `0x31f36`: `MarkupExtension ::= '{' TYPENAME (Arguments)? @'}'`
- `0x31f7c`: `MarkupExtension ::= '{' @TYPENAME (Arguments)? '}'`

## pseudocode

```c

```

## disassembly

```asm
0x31db0  ldarg.0
0x31db1  ldfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31db6  stloc.1
0x31db7  ldarg.0
0x31db8  ldfld    class MS.Internal.Xaml.Parser.MePullParser <P_MarkupExtension>d__9::<>4__this
0x31dbd  stloc.2
0x31dbe  ldloc.1
0x31dbf  switch   loc_31DDF, loc_31E42, loc_31E98, loc_31EF7, loc_31F59
0x31dd8  ldc.i4.0
0x31dd9  stloc.0
0x31dda  leave    loc_31F91
0x31ddf  ldarg.0
0x31de0  ldc.i4.m1
0x31de1  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31de6  ldloc.2
0x31de7  ldc.i4.s 0x7B
0x31de9  ldstr    aMarkupextensio_7// "MarkupExtension ::= @'{' Expr '}'"
0x31dee  call     instance bool MS.Internal.Xaml.Parser.MePullParser::Expect(valuetype MS.Internal.Xaml.Parser.MeTokenType token, string ruleString)
0x31df3  brfalse  loc_31F86
0x31df8  ldloc.2
0x31df9  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x31dfe  ldloc.2
0x31dff  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31e04  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x31e09  ldc.i4.s 0x2D
0x31e0b  bne.un   loc_31F7B
0x31e10  ldloc.2
0x31e11  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31e16  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.MeScanner::get_TokenType()
0x31e1b  stloc.3
0x31e1c  ldarg.0
0x31e1d  ldloc.2
0x31e1e  ldloc.3
0x31e1f  ldloc.2
0x31e20  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31e25  callvirt instance string MS.Internal.Xaml.Parser.MeScanner::get_Namespace()
0x31e2a  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_StartElement(class System.Xaml.XamlType xamlType, string xamlNamespace)
0x31e2f  stfld    valuetype System.Xaml.XamlNode <P_MarkupExtension>d__9::<>2__current
0x31e34  ldarg.0
0x31e35  ldc.i4.1
0x31e36  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31e3b  ldc.i4.1
0x31e3c  stloc.0
0x31e3d  leave    loc_31F91
0x31e42  ldarg.0
0x31e43  ldc.i4.m1
0x31e44  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31e49  ldloc.2
0x31e4a  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x31e4f  ldarg.0
0x31e50  newobj   instance void Found::.ctor()
0x31e55  stfld    class Found <P_MarkupExtension>d__9::<f2>5__2
0x31e5a  ldloc.2
0x31e5b  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x31e60  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x31e65  stloc.s  4
0x31e67  ldloc.s  4
0x31e69  ldc.i4.s 0x2E
0x31e6b  sub
0x31e6c  ldc.i4.2
0x31e6d  ble.un.s loc_31EB3
0x31e6f  ldloc.s  4
0x31e71  ldc.i4.s 0x7B
0x31e73  beq.s    loc_31EB3
0x31e75  ldloc.s  4
0x31e77  ldc.i4.s 0x7D
0x31e79  bne.un   loc_31F1B
0x31e7e  ldarg.0
0x31e7f  ldloc.2
0x31e80  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_EndObject()
0x31e85  stfld    valuetype System.Xaml.XamlNode <P_MarkupExtension>d__9::<>2__current
0x31e8a  ldarg.0
0x31e8b  ldc.i4.2
0x31e8c  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31e91  ldc.i4.1
0x31e92  stloc.0
0x31e93  leave    loc_31F91
0x31e98  ldarg.0
0x31e99  ldc.i4.m1
0x31e9a  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31e9f  ldloc.2
0x31ea0  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x31ea5  ldarg.0
0x31ea6  ldfld    class Found <P_MarkupExtension>d__9::f
0x31eab  ldc.i4.1
0x31eac  stfld    bool Found::found
0x31eb1  br.s     loc_31F26
0x31eb3  ldarg.0
0x31eb4  ldloc.2
0x31eb5  ldarg.0
0x31eb6  ldfld    class Found <P_MarkupExtension>d__9::<f2>5__2
0x31ebb  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_Arguments(class Found f)
0x31ec0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x31ec5  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_MarkupExtension>d__9::<>7__wrap2
0x31eca  ldarg.0
0x31ecb  ldc.i4.s 0xFD
0x31ecd  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31ed2  br.s     loc_31EFF
0x31ed4  ldarg.0
0x31ed5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_MarkupExtension>d__9::<>7__wrap2
0x31eda  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x31edf  stloc.s  5
0x31ee1  ldarg.0
0x31ee2  ldloc.s  5
0x31ee4  stfld    valuetype System.Xaml.XamlNode <P_MarkupExtension>d__9::<>2__current
0x31ee9  ldarg.0
0x31eea  ldc.i4.3
0x31eeb  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31ef0  ldc.i4.1
0x31ef1  stloc.0
0x31ef2  leave    loc_31F91
0x31ef7  ldarg.0
0x31ef8  ldc.i4.s 0xFD
0x31efa  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31eff  ldarg.0
0x31f00  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_MarkupExtension>d__9::<>7__wrap2
0x31f05  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31f0a  brtrue.s loc_31ED4
0x31f0c  ldarg.0
0x31f0d  call     instance void <P_MarkupExtension>d__9::<>m__Finally1()
0x31f12  ldarg.0
0x31f13  ldnull
0x31f14  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_MarkupExtension>d__9::<>7__wrap2
0x31f19  br.s     loc_31F26
0x31f1b  ldloc.2
0x31f1c  ldstr    aMarkupextensio_8// "MarkupExtension ::= '{' TYPENAME @(Argu"...
0x31f21  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x31f26  ldarg.0
0x31f27  ldfld    class Found <P_MarkupExtension>d__9::<f2>5__2
0x31f2c  ldfld    bool Found::found
0x31f31  brfalse.s loc_31F72
0x31f33  ldloc.2
0x31f34  ldc.i4.s 0x7D
0x31f36  ldstr    aMarkupextensio_9// "MarkupExtension ::= '{' TYPENAME (Argum"...
0x31f3b  call     instance bool MS.Internal.Xaml.Parser.MePullParser::Expect(valuetype MS.Internal.Xaml.Parser.MeTokenType token, string ruleString)
0x31f40  brfalse.s loc_31F72
0x31f42  ldarg.0
0x31f43  ldloc.2
0x31f44  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_EndObject()
0x31f49  stfld    valuetype System.Xaml.XamlNode <P_MarkupExtension>d__9::<>2__current
0x31f4e  ldarg.0
0x31f4f  ldc.i4.4
0x31f50  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31f55  ldc.i4.1
0x31f56  stloc.0
0x31f57  leave.s  loc_31F91
0x31f59  ldarg.0
0x31f5a  ldc.i4.m1
0x31f5b  stfld    int32 <P_MarkupExtension>d__9::<>1__state
0x31f60  ldarg.0
0x31f61  ldfld    class Found <P_MarkupExtension>d__9::f
0x31f66  ldc.i4.1
0x31f67  stfld    bool Found::found
0x31f6c  ldloc.2
0x31f6d  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x31f72  ldarg.0
0x31f73  ldnull
0x31f74  stfld    class Found <P_MarkupExtension>d__9::<f2>5__2
0x31f79  br.s     loc_31F86
0x31f7b  ldloc.2
0x31f7c  ldstr    aMarkupextensio_10// "MarkupExtension ::= '{' @TYPENAME (Argu"...
0x31f81  call     instance void MS.Internal.Xaml.Parser.MePullParser::SetBrokenRuleString(string ruleString)
0x31f86  ldc.i4.0
0x31f87  stloc.0
0x31f88  leave.s  loc_31F91
0x31f8a  ldarg.0
0x31f8b  call     instance void <P_MarkupExtension>d__9::System.IDisposable.Dispose()
0x31f90  endfinally
0x31f91  ldloc.0
0x31f92  ret
```
