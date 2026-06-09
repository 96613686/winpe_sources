# <P_Value>d__13::MoveNext

- ea: `0x32b90`
- end: `0x32d49`
- name: `<P_Value>d__13::MoveNext`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x242c0`
- `0x242d0`
- `0x24370`
- `0x24430`
- `0x24440`
- `0x24450`
- `0x24580`
- `0x24660`
- `0x24690`
- `0x31af0`
- `0x32b50`
- `0x32b90`
- `0x32d50`
- `0x32d70`

## pseudocode

```c

```

## disassembly

```asm
0x32b90  ldarg.0
0x32b91  ldfld    int32 <P_Value>d__13::<>1__state
0x32b96  stloc.1
0x32b97  ldarg.0
0x32b98  ldfld    class MS.Internal.Xaml.Parser.MePullParser <P_Value>d__13::<>4__this
0x32b9d  stloc.2
0x32b9e  ldloc.1
0x32b9f  switch   loc_32BBB, loc_32C0E, loc_32C8D, loc_32D04
0x32bb4  ldc.i4.0
0x32bb5  stloc.0
0x32bb6  leave    loc_32D47
0x32bbb  ldarg.0
0x32bbc  ldc.i4.m1
0x32bbd  stfld    int32 <P_Value>d__13::<>1__state
0x32bc2  ldarg.0
0x32bc3  newobj   instance void Found::.ctor()
0x32bc8  stfld    class Found <P_Value>d__13::<f2>5__2
0x32bcd  ldloc.2
0x32bce  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32bd3  callvirt instance valuetype MS.Internal.Xaml.Parser.MeTokenType MS.Internal.Xaml.Parser.MeScanner::get_Token()
0x32bd8  stloc.s  4
0x32bda  ldloc.s  4
0x32bdc  ldc.i4.s 0x2F
0x32bde  beq.s    loc_32BF4
0x32be0  ldloc.s  4
0x32be2  ldc.i4.s 0x30
0x32be4  beq.s    loc_32C2C
0x32be6  ldloc.s  4
0x32be8  ldc.i4.s 0x7B
0x32bea  beq      loc_32CC3
0x32bef  br       loc_32D3C
0x32bf4  ldarg.0
0x32bf5  ldloc.2
0x32bf6  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.MePullParser::Logic_Text()
0x32bfb  stfld    valuetype System.Xaml.XamlNode <P_Value>d__13::<>2__current
0x32c00  ldarg.0
0x32c01  ldc.i4.1
0x32c02  stfld    int32 <P_Value>d__13::<>1__state
0x32c07  ldc.i4.1
0x32c08  stloc.0
0x32c09  leave    loc_32D47
0x32c0e  ldarg.0
0x32c0f  ldc.i4.m1
0x32c10  stfld    int32 <P_Value>d__13::<>1__state
0x32c15  ldarg.0
0x32c16  ldfld    class Found <P_Value>d__13::f
0x32c1b  ldc.i4.1
0x32c1c  stfld    bool Found::found
0x32c21  ldloc.2
0x32c22  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x32c27  br       loc_32D3C
0x32c2c  ldloc.2
0x32c2d  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.MePullParser::_context
0x32c32  newobj   instance void MS.Internal.Xaml.Parser.MePullParser::.ctor(class MS.Internal.Xaml.Context.XamlParserContext stack)
0x32c37  stloc.3
0x32c38  ldarg.0
0x32c39  ldloc.3
0x32c3a  ldloc.2
0x32c3b  ldfld    class MS.Internal.Xaml.Parser.MeScanner MS.Internal.Xaml.Parser.MePullParser::_tokenizer
0x32c40  callvirt instance string MS.Internal.Xaml.Parser.MeScanner::get_TokenText()
0x32c45  ldloc.2
0x32c46  call     instance int32 MS.Internal.Xaml.Parser.MePullParser::get_LineNumber()
0x32c4b  ldloc.2
0x32c4c  call     instance int32 MS.Internal.Xaml.Parser.MePullParser::get_LinePosition()
0x32c51  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::Parse(string text, int32 lineNumber, int32 linePosition)
0x32c56  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x32c5b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32c60  ldarg.0
0x32c61  ldc.i4.s 0xFD
0x32c63  stfld    int32 <P_Value>d__13::<>1__state
0x32c68  br.s     loc_32C95
0x32c6a  ldarg.0
0x32c6b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32c70  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x32c75  stloc.s  5
0x32c77  ldarg.0
0x32c78  ldloc.s  5
0x32c7a  stfld    valuetype System.Xaml.XamlNode <P_Value>d__13::<>2__current
0x32c7f  ldarg.0
0x32c80  ldc.i4.2
0x32c81  stfld    int32 <P_Value>d__13::<>1__state
0x32c86  ldc.i4.1
0x32c87  stloc.0
0x32c88  leave    loc_32D47
0x32c8d  ldarg.0
0x32c8e  ldc.i4.s 0xFD
0x32c90  stfld    int32 <P_Value>d__13::<>1__state
0x32c95  ldarg.0
0x32c96  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32c9b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32ca0  brtrue.s loc_32C6A
0x32ca2  ldarg.0
0x32ca3  call     instance void <P_Value>d__13::<>m__Finally1()
0x32ca8  ldarg.0
0x32ca9  ldnull
0x32caa  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32caf  ldarg.0
0x32cb0  ldfld    class Found <P_Value>d__13::f
0x32cb5  ldc.i4.1
0x32cb6  stfld    bool Found::found
0x32cbb  ldloc.2
0x32cbc  call     instance void MS.Internal.Xaml.Parser.MePullParser::NextToken()
0x32cc1  br.s     loc_32D3C
0x32cc3  ldarg.0
0x32cc4  ldloc.2
0x32cc5  ldarg.0
0x32cc6  ldfld    class Found <P_Value>d__13::<f2>5__2
0x32ccb  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::P_MarkupExtension(class Found f)
0x32cd0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x32cd5  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32cda  ldarg.0
0x32cdb  ldc.i4.s 0xFC
0x32cdd  stfld    int32 <P_Value>d__13::<>1__state
0x32ce2  br.s     loc_32D0C
0x32ce4  ldarg.0
0x32ce5  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32cea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x32cef  stloc.s  6
0x32cf1  ldarg.0
0x32cf2  ldloc.s  6
0x32cf4  stfld    valuetype System.Xaml.XamlNode <P_Value>d__13::<>2__current
0x32cf9  ldarg.0
0x32cfa  ldc.i4.3
0x32cfb  stfld    int32 <P_Value>d__13::<>1__state
0x32d00  ldc.i4.1
0x32d01  stloc.0
0x32d02  leave.s  loc_32D47
0x32d04  ldarg.0
0x32d05  ldc.i4.s 0xFC
0x32d07  stfld    int32 <P_Value>d__13::<>1__state
0x32d0c  ldarg.0
0x32d0d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32d12  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32d17  brtrue.s loc_32CE4
0x32d19  ldarg.0
0x32d1a  call     instance void <P_Value>d__13::<>m__Finally2()
0x32d1f  ldarg.0
0x32d20  ldnull
0x32d21  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_Value>d__13::<>7__wrap2
0x32d26  ldarg.0
0x32d27  ldfld    class Found <P_Value>d__13::f
0x32d2c  ldarg.0
0x32d2d  ldfld    class Found <P_Value>d__13::<f2>5__2
0x32d32  ldfld    bool Found::found
0x32d37  stfld    bool Found::found
0x32d3c  ldc.i4.0
0x32d3d  stloc.0
0x32d3e  leave.s  loc_32D47
0x32d40  ldarg.0
0x32d41  call     instance void <P_Value>d__13::System.IDisposable.Dispose()
0x32d46  endfinally
0x32d47  ldloc.0
0x32d48  ret
```
