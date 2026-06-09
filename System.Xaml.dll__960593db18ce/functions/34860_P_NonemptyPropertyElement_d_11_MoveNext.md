# <P_NonemptyPropertyElement>d__11::MoveNext

- ea: `0x34860`
- end: `0x34b50`
- name: `<P_NonemptyPropertyElement>d__11::MoveNext`
- size: `752`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x11f20`
- `0x23100`
- `0x23120`
- `0x23160`
- `0x23180`
- `0x231a0`
- `0x231c0`
- `0x257f0`
- `0x25820`
- `0x25830`
- `0x258b0`
- `0x25900`
- `0x25970`
- `0x25df0`
- `0x25ff0`
- `0x26050`
- `0x260a0`
- `0x34840`
- `0x34860`
- `0x34b50`

## pseudocode

```c

```

## disassembly

```asm
0x34860  ldarg.0
0x34861  ldfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34866  stloc.1
0x34867  ldarg.0
0x34868  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_NonemptyPropertyElement>d__11::<>4__this
0x3486d  stloc.2
0x3486e  ldloc.1
0x3486f  switch   loc_348A3, loc_348FE, loc_34932, loc_3499B, loc_34A10, loc_34A41, loc_34A87, loc_34AA8, loc_34B0A, loc_34B3C
0x3489c  ldc.i4.0
0x3489d  stloc.0
0x3489e  leave    loc_34B4E
0x348a3  ldarg.0
0x348a4  ldc.i4.m1
0x348a5  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x348aa  ldloc.2
0x348ab  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x348b0  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x348b5  ldc.i4.6
0x348b6  beq.s    loc_348D9
0x348b8  ldloc.2
0x348b9  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x348be  ldloc.2
0x348bf  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x348c4  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x348c9  ldstr    aNonemptyproper// "NonemptyPropertyElementRuleException"
0x348ce  call     string System.Xaml.SR::Get(string id)
0x348d3  newobj   instance void MS.Internal.Xaml.Parser.XamlUnexpectedParseException::.ctor(class MS.Internal.Xaml.Parser.XamlScanner xamlScanner, valuetype MS.Internal.Xaml.Parser.ScannerNodeType nodetype, string parseRule)
0x348d8  throw
0x348d9  ldarg.0
0x348da  ldloc.2
0x348db  ldloc.2
0x348dc  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x348e1  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Parser.XamlScanner::get_PropertyElement()
0x348e6  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartMember(class System.Xaml.XamlMember member)
0x348eb  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x348f0  ldarg.0
0x348f1  ldc.i4.1
0x348f2  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x348f7  ldc.i4.1
0x348f8  stloc.0
0x348f9  leave    loc_34B4E
0x348fe  ldarg.0
0x348ff  ldc.i4.m1
0x34900  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34905  ldloc.2
0x34906  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3490b  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x34910  ldloc.2
0x34911  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x34916  brfalse.s loc_34939
0x34918  ldarg.0
0x34919  ldloc.2
0x3491a  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x3491f  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34924  ldarg.0
0x34925  ldc.i4.2
0x34926  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x3492b  ldc.i4.1
0x3492c  stloc.0
0x3492d  leave    loc_34B4E
0x34932  ldarg.0
0x34933  ldc.i4.m1
0x34934  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34939  ldarg.0
0x3493a  ldc.i4.1
0x3493b  stfld    bool <P_NonemptyPropertyElement>d__11::<doingPropertyContent>5__2
0x34940  ldloc.2
0x34941  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34946  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x3494b  stloc.3
0x3494c  ldloc.3
0x3494d  ldc.i4.1
0x3494e  sub
0x3494f  ldc.i4.1
0x34950  ble.un.s loc_3495D
0x34952  ldloc.3
0x34953  ldc.i4.5
0x34954  beq.s    loc_3495D
0x34956  ldloc.3
0x34957  ldc.i4.8
0x34958  bne.un   loc_34AB1
0x3495d  ldarg.0
0x3495e  ldloc.2
0x3495f  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::P_PropertyContent()
0x34964  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x34969  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NonemptyPropertyElement>d__11::<>7__wrap2
0x3496e  ldarg.0
0x3496f  ldc.i4.s 0xFD
0x34971  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34976  br.s     loc_349A3
0x34978  ldarg.0
0x34979  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NonemptyPropertyElement>d__11::<>7__wrap2
0x3497e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x34983  stloc.s  4
0x34985  ldarg.0
0x34986  ldloc.s  4
0x34988  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x3498d  ldarg.0
0x3498e  ldc.i4.3
0x3498f  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34994  ldc.i4.1
0x34995  stloc.0
0x34996  leave    loc_34B4E
0x3499b  ldarg.0
0x3499c  ldc.i4.s 0xFD
0x3499e  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x349a3  ldarg.0
0x349a4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NonemptyPropertyElement>d__11::<>7__wrap2
0x349a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x349ae  brtrue.s loc_34978
0x349b0  ldarg.0
0x349b1  call     instance void <P_NonemptyPropertyElement>d__11::<>m__Finally1()
0x349b6  ldarg.0
0x349b7  ldnull
0x349b8  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_NonemptyPropertyElement>d__11::<>7__wrap2
0x349bd  ldloc.2
0x349be  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x349c3  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x349c8  stloc.3
0x349c9  ldloc.3
0x349ca  ldc.i4.5
0x349cb  beq.s    loc_3495D
0x349cd  ldloc.3
0x349ce  ldc.i4.1
0x349cf  beq.s    loc_3495D
0x349d1  ldloc.3
0x349d2  ldc.i4.2
0x349d3  beq.s    loc_3495D
0x349d5  ldloc.3
0x349d6  ldc.i4.8
0x349d7  beq.s    loc_3495D
0x349d9  ldloc.2
0x349da  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x349df  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInItemsProperty()
0x349e4  brtrue.s loc_349F6
0x349e6  ldloc.2
0x349e7  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x349ec  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInInitProperty()
0x349f1  brfalse  loc_34AB8
0x349f6  ldarg.0
0x349f7  ldloc.2
0x349f8  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x349fd  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34a02  ldarg.0
0x34a03  ldc.i4.4
0x34a04  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34a09  ldc.i4.1
0x34a0a  stloc.0
0x34a0b  leave    loc_34B4E
0x34a10  ldarg.0
0x34a11  ldc.i4.m1
0x34a12  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34a17  ldloc.2
0x34a18  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34a1d  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInCollectionFromMember()
0x34a22  brfalse  loc_34AB8
0x34a27  ldarg.0
0x34a28  ldloc.2
0x34a29  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndObject()
0x34a2e  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34a33  ldarg.0
0x34a34  ldc.i4.5
0x34a35  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34a3a  ldc.i4.1
0x34a3b  stloc.0
0x34a3c  leave    loc_34B4E
0x34a41  ldarg.0
0x34a42  ldc.i4.m1
0x34a43  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34a48  ldloc.2
0x34a49  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34a4e  ldc.i4.0
0x34a4f  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentInCollectionFromMember(bool value)
0x34a54  ldloc.2
0x34a55  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34a5a  callvirt instance bool MS.Internal.Xaml.Context.XamlParserContext::get_CurrentInImplicitArray()
0x34a5f  brfalse.s loc_34AB8
0x34a61  ldloc.2
0x34a62  ldfld    class MS.Internal.Xaml.Context.XamlParserContext MS.Internal.Xaml.Parser.XamlPullParser::_context
0x34a67  ldc.i4.0
0x34a68  callvirt instance void MS.Internal.Xaml.Context.XamlParserContext::set_CurrentInImplicitArray(bool value)
0x34a6d  ldarg.0
0x34a6e  ldloc.2
0x34a6f  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x34a74  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34a79  ldarg.0
0x34a7a  ldc.i4.6
0x34a7b  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34a80  ldc.i4.1
0x34a81  stloc.0
0x34a82  leave    loc_34B4E
0x34a87  ldarg.0
0x34a88  ldc.i4.m1
0x34a89  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34a8e  ldarg.0
0x34a8f  ldloc.2
0x34a90  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndObject()
0x34a95  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34a9a  ldarg.0
0x34a9b  ldc.i4.7
0x34a9c  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34aa1  ldc.i4.1
0x34aa2  stloc.0
0x34aa3  leave    loc_34B4E
0x34aa8  ldarg.0
0x34aa9  ldc.i4.m1
0x34aaa  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34aaf  br.s     loc_34AB8
0x34ab1  ldarg.0
0x34ab2  ldc.i4.0
0x34ab3  stfld    bool <P_NonemptyPropertyElement>d__11::<doingPropertyContent>5__2
0x34ab8  ldarg.0
0x34ab9  ldfld    bool <P_NonemptyPropertyElement>d__11::<doingPropertyContent>5__2
0x34abe  brtrue   loc_34940
0x34ac3  ldloc.2
0x34ac4  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34ac9  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x34ace  ldc.i4.s 9
0x34ad0  beq.s    loc_34AF3
0x34ad2  ldloc.2
0x34ad3  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34ad8  ldloc.2
0x34ad9  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34ade  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x34ae3  ldstr    aNonemptyproper// "NonemptyPropertyElementRuleException"
0x34ae8  call     string System.Xaml.SR::Get(string id)
0x34aed  newobj   instance void MS.Internal.Xaml.Parser.XamlUnexpectedParseException::.ctor(class MS.Internal.Xaml.Parser.XamlScanner xamlScanner, valuetype MS.Internal.Xaml.Parser.ScannerNodeType nodetype, string parseRule)
0x34af2  throw
0x34af3  ldarg.0
0x34af4  ldloc.2
0x34af5  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndMember()
0x34afa  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34aff  ldarg.0
0x34b00  ldc.i4.8
0x34b01  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34b06  ldc.i4.1
0x34b07  stloc.0
0x34b08  leave.s  loc_34B4E
0x34b0a  ldarg.0
0x34b0b  ldc.i4.m1
0x34b0c  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34b11  ldloc.2
0x34b12  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x34b17  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x34b1c  ldloc.2
0x34b1d  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x34b22  brfalse.s loc_34B43
0x34b24  ldarg.0
0x34b25  ldloc.2
0x34b26  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x34b2b  stfld    valuetype System.Xaml.XamlNode <P_NonemptyPropertyElement>d__11::<>2__current
0x34b30  ldarg.0
0x34b31  ldc.i4.s 9
0x34b33  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34b38  ldc.i4.1
0x34b39  stloc.0
0x34b3a  leave.s  loc_34B4E
0x34b3c  ldarg.0
0x34b3d  ldc.i4.m1
0x34b3e  stfld    int32 <P_NonemptyPropertyElement>d__11::<>1__state
0x34b43  ldc.i4.0
0x34b44  stloc.0
0x34b45  leave.s  loc_34B4E
0x34b47  ldarg.0
0x34b48  call     instance void <P_NonemptyPropertyElement>d__11::System.IDisposable.Dispose()
0x34b4d  endfinally
0x34b4e  ldloc.0
0x34b4f  ret
```
