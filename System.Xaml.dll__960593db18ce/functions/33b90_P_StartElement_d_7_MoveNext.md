# <P_StartElement>d__7::MoveNext

- ea: `0x33b90`
- end: `0x33d12`
- name: `<P_StartElement>d__7::MoveNext`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x11f20`
- `0x25820`
- `0x25830`
- `0x25880`
- `0x258e0`
- `0x25df0`
- `0x25ff0`
- `0x26050`
- `0x26060`
- `0x260f0`
- `0x33b70`
- `0x33b90`
- `0x33d20`

## pseudocode

```c

```

## disassembly

```asm
0x33b90  ldarg.0
0x33b91  ldfld    int32 <P_StartElement>d__7::<>1__state
0x33b96  stloc.1
0x33b97  ldarg.0
0x33b98  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_StartElement>d__7::<>4__this
0x33b9d  stloc.2
0x33b9e  ldloc.1
0x33b9f  switch   loc_33BBF, loc_33C25, loc_33C5C, loc_33CA1, loc_33CED
0x33bb8  ldc.i4.0
0x33bb9  stloc.0
0x33bba  leave    loc_33D10
0x33bbf  ldarg.0
0x33bc0  ldc.i4.m1
0x33bc1  stfld    int32 <P_StartElement>d__7::<>1__state
0x33bc6  ldloc.2
0x33bc7  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33bcc  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33bd1  ldc.i4.1
0x33bd2  beq.s    loc_33BF5
0x33bd4  ldloc.2
0x33bd5  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33bda  ldloc.2
0x33bdb  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33be0  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33be5  ldstr    aStartelementru// "StartElementRuleException"
0x33bea  call     string System.Xaml.SR::Get(string id)
0x33bef  newobj   instance void MS.Internal.Xaml.Parser.XamlUnexpectedParseException::.ctor(class MS.Internal.Xaml.Parser.XamlScanner xamlScanner, valuetype MS.Internal.Xaml.Parser.ScannerNodeType nodetype, string parseRule)
0x33bf4  throw
0x33bf5  ldarg.0
0x33bf6  ldloc.2
0x33bf7  ldloc.2
0x33bf8  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33bfd  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.XamlScanner::get_Type()
0x33c02  ldloc.2
0x33c03  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33c08  callvirt instance string MS.Internal.Xaml.Parser.XamlScanner::get_Namespace()
0x33c0d  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartObject(class System.Xaml.XamlType xamlType, string xamlNamespace)
0x33c12  stfld    valuetype System.Xaml.XamlNode <P_StartElement>d__7::<>2__current
0x33c17  ldarg.0
0x33c18  ldc.i4.1
0x33c19  stfld    int32 <P_StartElement>d__7::<>1__state
0x33c1e  ldc.i4.1
0x33c1f  stloc.0
0x33c20  leave    loc_33D10
0x33c25  ldarg.0
0x33c26  ldc.i4.m1
0x33c27  stfld    int32 <P_StartElement>d__7::<>1__state
0x33c2c  ldloc.2
0x33c2d  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33c32  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x33c37  ldloc.2
0x33c38  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x33c3d  brfalse  loc_33CF4
0x33c42  ldarg.0
0x33c43  ldloc.2
0x33c44  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x33c49  stfld    valuetype System.Xaml.XamlNode <P_StartElement>d__7::<>2__current
0x33c4e  ldarg.0
0x33c4f  ldc.i4.2
0x33c50  stfld    int32 <P_StartElement>d__7::<>1__state
0x33c55  ldc.i4.1
0x33c56  stloc.0
0x33c57  leave    loc_33D10
0x33c5c  ldarg.0
0x33c5d  ldc.i4.m1
0x33c5e  stfld    int32 <P_StartElement>d__7::<>1__state
0x33c63  br       loc_33CF4
0x33c68  ldarg.0
0x33c69  ldloc.2
0x33c6a  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::LogicStream_Attribute()
0x33c6f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x33c74  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_StartElement>d__7::<>7__wrap1
0x33c79  ldarg.0
0x33c7a  ldc.i4.s 0xFD
0x33c7c  stfld    int32 <P_StartElement>d__7::<>1__state
0x33c81  br.s     loc_33CA9
0x33c83  ldarg.0
0x33c84  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_StartElement>d__7::<>7__wrap1
0x33c89  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x33c8e  stloc.3
0x33c8f  ldarg.0
0x33c90  ldloc.3
0x33c91  stfld    valuetype System.Xaml.XamlNode <P_StartElement>d__7::<>2__current
0x33c96  ldarg.0
0x33c97  ldc.i4.3
0x33c98  stfld    int32 <P_StartElement>d__7::<>1__state
0x33c9d  ldc.i4.1
0x33c9e  stloc.0
0x33c9f  leave.s  loc_33D10
0x33ca1  ldarg.0
0x33ca2  ldc.i4.s 0xFD
0x33ca4  stfld    int32 <P_StartElement>d__7::<>1__state
0x33ca9  ldarg.0
0x33caa  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_StartElement>d__7::<>7__wrap1
0x33caf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33cb4  brtrue.s loc_33C83
0x33cb6  ldarg.0
0x33cb7  call     instance void <P_StartElement>d__7::<>m__Finally1()
0x33cbc  ldarg.0
0x33cbd  ldnull
0x33cbe  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_StartElement>d__7::<>7__wrap1
0x33cc3  ldloc.2
0x33cc4  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33cc9  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x33cce  ldloc.2
0x33ccf  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x33cd4  brfalse.s loc_33CF4
0x33cd6  ldarg.0
0x33cd7  ldloc.2
0x33cd8  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x33cdd  stfld    valuetype System.Xaml.XamlNode <P_StartElement>d__7::<>2__current
0x33ce2  ldarg.0
0x33ce3  ldc.i4.4
0x33ce4  stfld    int32 <P_StartElement>d__7::<>1__state
0x33ce9  ldc.i4.1
0x33cea  stloc.0
0x33ceb  leave.s  loc_33D10
0x33ced  ldarg.0
0x33cee  ldc.i4.m1
0x33cef  stfld    int32 <P_StartElement>d__7::<>1__state
0x33cf4  ldloc.2
0x33cf5  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33cfa  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33cff  ldc.i4.4
0x33d00  beq      loc_33C68
0x33d05  ldc.i4.0
0x33d06  stloc.0
0x33d07  leave.s  loc_33D10
0x33d09  ldarg.0
0x33d0a  call     instance void <P_StartElement>d__7::System.IDisposable.Dispose()
0x33d0f  endfinally
0x33d10  ldloc.0
0x33d11  ret
```
