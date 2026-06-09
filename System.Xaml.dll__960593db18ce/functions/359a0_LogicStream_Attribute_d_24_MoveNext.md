# <LogicStream_Attribute>d__24::MoveNext

- ea: `0x359a0`
- end: `0x35b1e`
- name: `<LogicStream_Attribute>d__24::MoveNext`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x20e0`
- `0x2100`
- `0x230e0`
- `0x242c0`
- `0x242d0`
- `0x25800`
- `0x25810`
- `0x26070`
- `0x26080`
- `0x26090`
- `0x27250`
- `0x27260`
- `0x273d0`
- `0x35980`
- `0x359a0`
- `0x35b20`

## pseudocode

```c

```

## disassembly

```asm
0x359a0  ldarg.0
0x359a1  ldfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x359a6  stloc.1
0x359a7  ldarg.0
0x359a8  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <LogicStream_Attribute>d__24::<>4__this
0x359ad  stloc.2
0x359ae  ldloc.1
0x359af  switch   loc_359CF, loc_35A2B, loc_35AA2, loc_35AEC, loc_35B0A
0x359c8  ldc.i4.0
0x359c9  stloc.0
0x359ca  leave    loc_35B1C
0x359cf  ldarg.0
0x359d0  ldc.i4.m1
0x359d1  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x359d6  ldloc.2
0x359d7  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x359dc  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Parser.XamlScanner::get_PropertyAttribute()
0x359e1  stloc.3
0x359e2  ldarg.0
0x359e3  ldloc.2
0x359e4  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x359e9  callvirt instance class MS.Internal.Xaml.Parser.XamlText MS.Internal.Xaml.Parser.XamlScanner::get_PropertyAttributeText()
0x359ee  stfld    class MS.Internal.Xaml.Parser.XamlText <LogicStream_Attribute>d__24::<text>5__2
0x359f3  ldloc.2
0x359f4  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x359f9  callvirt instance bool MS.Internal.Xaml.Parser.XamlScanner::get_IsCtorForcingMember()
0x359fe  brfalse.s loc_35A0C
0x35a00  ldloc.2
0x35a01  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35a06  ldc.i4.1
0x35a07  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentForcedToUseConstructor(bool value)
0x35a0c  ldloca.s 4
0x35a0e  ldc.i4.4
0x35a0f  ldloc.3
0x35a10  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x35a15  ldarg.0
0x35a16  ldloc.s  4
0x35a18  stfld    valuetype System.Xaml.XamlNode <LogicStream_Attribute>d__24::<>2__current
0x35a1d  ldarg.0
0x35a1e  ldc.i4.1
0x35a1f  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35a24  ldc.i4.1
0x35a25  stloc.0
0x35a26  leave    loc_35B1C
0x35a2b  ldarg.0
0x35a2c  ldc.i4.m1
0x35a2d  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35a32  ldarg.0
0x35a33  ldfld    class MS.Internal.Xaml.Parser.XamlText <LogicStream_Attribute>d__24::<text>5__2
0x35a38  callvirt instance bool MS.Internal.Xaml.Parser.XamlText::get_LooksLikeAMarkupExtension()
0x35a3d  brfalse  loc_35AC6
0x35a42  ldloc.2
0x35a43  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x35a48  newobj   instance void MS.Internal.Xaml.Parser.MePullParser::.ctor(class MS.Internal.Xaml.Context.XamlParserContext stack)
0x35a4d  stloc.s  5
0x35a4f  ldarg.0
0x35a50  ldloc.s  5
0x35a52  ldarg.0
0x35a53  ldfld    class MS.Internal.Xaml.Parser.XamlText <LogicStream_Attribute>d__24::<text>5__2
0x35a58  callvirt instance string MS.Internal.Xaml.Parser.XamlText::get_Text()
0x35a5d  ldloc.2
0x35a5e  call     instance int32 MS.Internal.Xaml.Parser.XamlPullParser::get_LineNumber()
0x35a63  ldloc.2
0x35a64  call     instance int32 MS.Internal.Xaml.Parser.XamlPullParser::get_LinePosition()
0x35a69  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.MePullParser::Parse(string text, int32 lineNumber, int32 linePosition)
0x35a6e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x35a73  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <LogicStream_Attribute>d__24::<>7__wrap2
0x35a78  ldarg.0
0x35a79  ldc.i4.s 0xFD
0x35a7b  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35a80  br.s     loc_35AAA
0x35a82  ldarg.0
0x35a83  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <LogicStream_Attribute>d__24::<>7__wrap2
0x35a88  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x35a8d  stloc.s  6
0x35a8f  ldarg.0
0x35a90  ldloc.s  6
0x35a92  stfld    valuetype System.Xaml.XamlNode <LogicStream_Attribute>d__24::<>2__current
0x35a97  ldarg.0
0x35a98  ldc.i4.2
0x35a99  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35a9e  ldc.i4.1
0x35a9f  stloc.0
0x35aa0  leave.s  loc_35B1C
0x35aa2  ldarg.0
0x35aa3  ldc.i4.s 0xFD
0x35aa5  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35aaa  ldarg.0
0x35aab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <LogicStream_Attribute>d__24::<>7__wrap2
0x35ab0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x35ab5  brtrue.s loc_35A82
0x35ab7  ldarg.0
0x35ab8  call     instance void <LogicStream_Attribute>d__24::<>m__Finally1()
0x35abd  ldarg.0
0x35abe  ldnull
0x35abf  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <LogicStream_Attribute>d__24::<>7__wrap2
0x35ac4  br.s     loc_35AF3
0x35ac6  ldloca.s 7
0x35ac8  ldc.i4.6
0x35ac9  ldarg.0
0x35aca  ldfld    class MS.Internal.Xaml.Parser.XamlText <LogicStream_Attribute>d__24::<text>5__2
0x35acf  callvirt instance string MS.Internal.Xaml.Parser.XamlText::get_AttributeText()
0x35ad4  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x35ad9  ldarg.0
0x35ada  ldloc.s  7
0x35adc  stfld    valuetype System.Xaml.XamlNode <LogicStream_Attribute>d__24::<>2__current
0x35ae1  ldarg.0
0x35ae2  ldc.i4.3
0x35ae3  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35ae8  ldc.i4.1
0x35ae9  stloc.0
0x35aea  leave.s  loc_35B1C
0x35aec  ldarg.0
0x35aed  ldc.i4.m1
0x35aee  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35af3  ldarg.0
0x35af4  ldc.i4.5
0x35af5  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x35afa  stfld    valuetype System.Xaml.XamlNode <LogicStream_Attribute>d__24::<>2__current
0x35aff  ldarg.0
0x35b00  ldc.i4.4
0x35b01  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35b06  ldc.i4.1
0x35b07  stloc.0
0x35b08  leave.s  loc_35B1C
0x35b0a  ldarg.0
0x35b0b  ldc.i4.m1
0x35b0c  stfld    int32 <LogicStream_Attribute>d__24::<>1__state
0x35b11  ldc.i4.0
0x35b12  stloc.0
0x35b13  leave.s  loc_35B1C
0x35b15  ldarg.0
0x35b16  call     instance void <LogicStream_Attribute>d__24::System.IDisposable.Dispose()
0x35b1b  endfinally
0x35b1c  ldloc.0
0x35b1d  ret
```
