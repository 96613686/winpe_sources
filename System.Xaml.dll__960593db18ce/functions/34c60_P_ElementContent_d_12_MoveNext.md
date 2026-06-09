# <P_ElementContent>d__12::MoveNext

- ea: `0x34c60`
- end: `0x352e4`
- name: `<P_ElementContent>d__12::MoveNext`
- size: `1668`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: ``

## callees

- `0x2100`
- `0x89f0`
- `0xa0b0`
- `0xa4c0`
- `0xb2f0`
- `0xd110`
- `0xd130`
- `0xd310`
- `0xd370`
- `0xd430`
- `0x1d630`
- `0x22ec0`
- `0x230c0`
- `0x23100`
- `0x23140`
- `0x23260`
- `0x25770`
- `0x25820`
- `0x25830`
- `0x25850`
- `0x25880`
- `0x258b0`
- `0x258f0`
- `0x25900`
- `0x25970`
- `0x259a0`
- `0x259d0`
- `0x259f0`
- `0x25aa0`
- `0x25b80`
- `0x25b90`
- `0x25d40`
- `0x25ff0`
- `0x26050`
- `0x260b0`
- `0x260c0`
- `0x27240`
- `0x34c20`
- `0x34c60`
- `0x352f0`
- `0x35310`

## pseudocode

```c

```

## disassembly

```asm
0x34c60  ldarg.0
0x34c61  ldfld    int32 <P_ElementContent>d__12::<>1__state
0x34c66  stloc.1
0x34c67  ldarg.0
0x34c68  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_ElementContent>d__12::<>4__this
0x34c6d  stloc.2
0x34c6e  ldloc.1
0x34c6f  switch   loc_34CC3, loc_34D61, loc_34DD7, loc_34EE3, loc_34F84, loc_34FC9, loc_35024, loc_35072, loc_350DE, loc_35123, loc_35156, loc_3518D, loc_351B5, loc_351E4, loc_3520E, loc_35230, loc_3527C, loc_352D0
0x34cbc  ldc.i4.0
0x34cbd  stloc.0
0x34cbe  leave    loc_352E2
0x34cc3  ldarg.0
0x34cc4  ldc.i4.m1
0x34cc5  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34cca  ldarg.0
0x34ccb  ldloc.2
0x34ccc  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34cd1  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlParserContext::get_CurrentType()
0x34cd6  stfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34cdb  ldarg.0
0x34cdc  ldnull
0x34cdd  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
0x34ce2  ldarg.0
0x34ce3  ldloc.2
0x34ce4  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34ce9  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x34cee  stfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_ElementContent>d__12::<nodeType>5__4
0x34cf3  ldarg.0
0x34cf4  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_ElementContent>d__12::<nodeType>5__4
0x34cf9  stloc.3
0x34cfa  ldloc.3
0x34cfb  ldc.i4.1
0x34cfc  sub
0x34cfd  ldc.i4.1
0x34cfe  ble.un.s loc_34D0B
0x34d00  ldloc.3
0x34d01  ldc.i4.5
0x34d02  beq.s    loc_34D0B
0x34d04  ldloc.3
0x34d05  ldc.i4.8
0x34d06  bne.un   loc_352D7
0x34d0b  ldarg.0
0x34d0c  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_ElementContent>d__12::<nodeType>5__4
0x34d11  ldc.i4.8
0x34d12  bne.un   loc_34DEF
0x34d17  ldloc.2
0x34d18  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34d1d  callvirt instance class MS.Internal.Xaml.Parser.XamlText MS.Internal.Xaml.Parser.XamlScanner::get_TextContent()
0x34d22  stloc.s  4
0x34d24  ldloc.2
0x34d25  ldloc.s  4
0x34d27  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::Logic_IsDiscardableWhitespace(class MS.Internal.Xaml.Parser.XamlText text)
0x34d2c  brfalse  loc_34DEF
0x34d31  ldloc.2
0x34d32  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34d37  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x34d3c  ldloc.2
0x34d3d  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x34d42  brfalse  loc_352D7
0x34d47  ldarg.0
0x34d48  ldloc.2
0x34d49  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x34d4e  stfld    valuetype System.Xaml.XamlNode <P_ElementContent>d__12::<>2__current
0x34d53  ldarg.0
0x34d54  ldc.i4.1
0x34d55  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34d5a  ldc.i4.1
0x34d5b  stloc.0
0x34d5c  leave    loc_352E2
0x34d61  ldarg.0
0x34d62  ldc.i4.m1
0x34d63  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34d68  br       loc_352D7
0x34d6d  ldarg.0
0x34d6e  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
0x34d73  brtrue.s loc_34D80
0x34d75  ldarg.0
0x34d76  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::.ctor()
0x34d7b  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
0x34d80  ldloc.2
0x34d81  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x34d86  brfalse.s loc_34D99
0x34d88  ldarg.0
0x34d89  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
0x34d8e  ldloc.2
0x34d8f  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x34d94  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x34d99  ldarg.0
0x34d9a  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
0x34d9f  ldloc.2
0x34da0  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_PrefixDefinition()
0x34da5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x34daa  ldloc.2
0x34dab  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34db0  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x34db5  ldloc.2
0x34db6  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x34dbb  brfalse.s loc_34DDE
0x34dbd  ldarg.0
0x34dbe  ldloc.2
0x34dbf  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x34dc4  stfld    valuetype System.Xaml.XamlNode <P_ElementContent>d__12::<>2__current
0x34dc9  ldarg.0
0x34dca  ldc.i4.2
0x34dcb  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34dd0  ldc.i4.1
0x34dd1  stloc.0
0x34dd2  leave    loc_352E2
0x34dd7  ldarg.0
0x34dd8  ldc.i4.m1
0x34dd9  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34dde  ldarg.0
0x34ddf  ldloc.2
0x34de0  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34de5  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x34dea  stfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_ElementContent>d__12::<nodeType>5__4
0x34def  ldarg.0
0x34df0  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_ElementContent>d__12::<nodeType>5__4
0x34df5  ldc.i4.5
0x34df6  beq      loc_34D6D
0x34dfb  ldarg.0
0x34dfc  ldc.i4.0
0x34dfd  stfld    bool <P_ElementContent>d__12::<isTextInitialization>5__5
0x34e02  ldloc.2
0x34e03  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34e08  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInItemsProperty()
0x34e0d  brtrue   loc_34FEB
0x34e12  ldloc.2
0x34e13  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34e18  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInUnknownContent()
0x34e1d  brtrue   loc_34FEB
0x34e22  ldarg.0
0x34e23  ldc.i4.0
0x34e24  stfld    bool <P_ElementContent>d__12::<isContentProperty>5__6
0x34e29  ldarg.0
0x34e2a  ldfld    valuetype MS.Internal.Xaml.Parser.ScannerNodeType <P_ElementContent>d__12::<nodeType>5__4
0x34e2f  ldc.i4.8
0x34e30  bne.un.s loc_34E99
0x34e32  ldarg.0
0x34e33  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34e38  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::get_ContentProperty()
0x34e3d  ldnull
0x34e3e  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x34e43  brfalse.s loc_34E60
0x34e45  ldarg.0
0x34e46  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34e4b  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::get_ContentProperty()
0x34e50  call     bool MS.Internal.Xaml.Parser.XamlPullParser::CanAcceptString(class System.Xaml.XamlMember property)
0x34e55  brfalse.s loc_34E60
0x34e57  ldarg.0
0x34e58  ldc.i4.1
0x34e59  stfld    bool <P_ElementContent>d__12::<isContentProperty>5__6
0x34e5e  br.s     loc_34E99
0x34e60  ldloc.2
0x34e61  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34e66  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentForcedToUseConstructor()
0x34e6b  brtrue.s loc_34E99
0x34e6d  ldloc.2
0x34e6e  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34e73  callvirt instance class MS.Internal.Xaml.Parser.XamlText MS.Internal.Xaml.Parser.XamlScanner::get_TextContent()
0x34e78  callvirt instance bool MS.Internal.Xaml.Parser.XamlText::get_IsEmpty()
0x34e7d  brtrue.s loc_34E99
0x34e7f  ldarg.0
0x34e80  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34e85  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlType::get_TypeConverter()
0x34e8a  ldnull
0x34e8b  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x34e90  brfalse.s loc_34E99
0x34e92  ldarg.0
0x34e93  ldc.i4.1
0x34e94  stfld    bool <P_ElementContent>d__12::<isTextInitialization>5__5
0x34e99  ldarg.0
0x34e9a  ldfld    bool <P_ElementContent>d__12::<isTextInitialization>5__5
0x34e9f  brtrue.s loc_34EF3
0x34ea1  ldarg.0
0x34ea2  ldfld    bool <P_ElementContent>d__12::<isContentProperty>5__6
0x34ea7  brtrue.s loc_34EF3
0x34ea9  ldarg.0
0x34eaa  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34eaf  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x34eb4  brtrue.s loc_34EC3
0x34eb6  ldarg.0
0x34eb7  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34ebc  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x34ec1  brfalse.s loc_34EEC
0x34ec3  ldarg.0
0x34ec4  ldloc.2
0x34ec5  ldarg.0
0x34ec6  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34ecb  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartItemsProperty(class System.Xaml.XamlType collectionType)
0x34ed0  stfld    valuetype System.Xaml.XamlNode <P_ElementContent>d__12::<>2__current
0x34ed5  ldarg.0
0x34ed6  ldc.i4.3
0x34ed7  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34edc  ldc.i4.1
0x34edd  stloc.0
0x34ede  leave    loc_352E2
0x34ee3  ldarg.0
0x34ee4  ldc.i4.m1
0x34ee5  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34eea  br.s     loc_34EF3
0x34eec  ldarg.0
0x34eed  ldc.i4.1
0x34eee  stfld    bool <P_ElementContent>d__12::<isContentProperty>5__6
0x34ef3  ldarg.0
0x34ef4  ldfld    bool <P_ElementContent>d__12::<isContentProperty>5__6
0x34ef9  brfalse  loc_34FEB
0x34efe  ldloc.2
0x34eff  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34f04  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInUnknownContent()
0x34f09  brtrue   loc_34FEB
0x34f0e  ldarg.0
0x34f0f  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34f14  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::get_ContentProperty()
0x34f19  stloc.s  5
0x34f1b  ldloc.s  5
0x34f1d  ldnull
0x34f1e  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x34f23  brfalse.s loc_34F68
0x34f25  ldloc.2
0x34f26  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34f2b  ldloc.s  5
0x34f2d  ldloc.2
0x34f2e  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34f33  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentTypeIsRoot()
0x34f38  brtrue.s loc_34F3D
0x34f3a  ldnull
0x34f3b  br.s     loc_34F48
0x34f3d  ldloc.2
0x34f3e  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34f43  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlParserContext::get_CurrentType()
0x34f48  callvirt instance bool MS.Internal.Xaml.XamlContext::IsVisible(class System.Xaml.XamlMember member, class System.Xaml.XamlType rootObjectType)
0x34f4d  stloc.s  6
0x34f4f  ldloc.s  6
0x34f51  brtrue.s loc_34F68
0x34f53  ldloc.s  5
0x34f55  callvirt instance string System.Xaml.XamlMember::get_Name()
0x34f5a  ldarg.0
0x34f5b  ldfld    class System.Xaml.XamlType <P_ElementContent>d__12::<currentType>5__2
0x34f60  ldc.i4.0
0x34f61  newobj   instance void System.Xaml.XamlMember::.ctor(string name, class System.Xaml.XamlType declaringType, bool isAttachable)
0x34f66  stloc.s  5
0x34f68  ldarg.0
0x34f69  ldloc.2
0x34f6a  ldloc.s  5
0x34f6c  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartContentProperty(class System.Xaml.XamlMember property)
0x34f71  stfld    valuetype System.Xaml.XamlNode <P_ElementContent>d__12::<>2__current
0x34f76  ldarg.0
0x34f77  ldc.i4.4
0x34f78  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34f7d  ldc.i4.1
0x34f7e  stloc.0
0x34f7f  leave    loc_352E2
0x34f84  ldarg.0
0x34f85  ldc.i4.m1
0x34f86  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34f8b  ldarg.0
0x34f8c  ldloc.2
0x34f8d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::LogicStream_CheckForStartGetCollectionFromMember()
0x34f92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x34f97  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<>7__wrap6
0x34f9c  ldarg.0
0x34f9d  ldc.i4.s 0xFD
0x34f9f  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34fa4  br.s     loc_34FD1
0x34fa6  ldarg.0
0x34fa7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<>7__wrap6
0x34fac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x34fb1  stloc.s  7
0x34fb3  ldarg.0
0x34fb4  ldloc.s  7
0x34fb6  stfld    valuetype System.Xaml.XamlNode <P_ElementContent>d__12::<>2__current
0x34fbb  ldarg.0
0x34fbc  ldc.i4.5
0x34fbd  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34fc2  ldc.i4.1
0x34fc3  stloc.0
0x34fc4  leave    loc_352E2
0x34fc9  ldarg.0
0x34fca  ldc.i4.s 0xFD
0x34fcc  stfld    int32 <P_ElementContent>d__12::<>1__state
0x34fd1  ldarg.0
0x34fd2  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<>7__wrap6
0x34fd7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34fdc  brtrue.s loc_34FA6
0x34fde  ldarg.0
0x34fdf  call     instance void <P_ElementContent>d__12::<>m__Finally1()
0x34fe4  ldarg.0
0x34fe5  ldnull
0x34fe6  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<>7__wrap6
0x34feb  ldarg.0
0x34fec  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
0x34ff1  brfalse  loc_35079
0x34ff6  ldarg.0
0x34ff7  ldc.i4.0
0x34ff8  stfld    int32 <P_ElementContent>d__12::<i>5__8
0x34ffd  br.s     loc_3503D
0x34fff  ldarg.0
0x35000  ldarg.0
0x35001  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> <P_ElementContent>d__12::<savedPrefixDefinitions>5__3
  ... truncated ...
```
