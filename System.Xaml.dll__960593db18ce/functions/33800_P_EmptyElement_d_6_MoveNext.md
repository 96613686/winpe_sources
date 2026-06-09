# <P_EmptyElement>d__6::MoveNext

- ea: `0x33800`
- end: `0x33a7b`
- name: `<P_EmptyElement>d__6::MoveNext`
- size: `635`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x11f20`
- `0x25820`
- `0x25830`
- `0x25880`
- `0x258b0`
- `0x258e0`
- `0x258f0`
- `0x25df0`
- `0x25ff0`
- `0x26050`
- `0x26060`
- `0x260f0`
- `0x337c0`
- `0x33800`
- `0x33a80`
- `0x33aa0`

## pseudocode

```c

```

## disassembly

```asm
0x33800  ldarg.0
0x33801  ldfld    int32 <P_EmptyElement>d__6::<>1__state
0x33806  stloc.1
0x33807  ldarg.0
0x33808  ldfld    class MS.Internal.Xaml.Parser.XamlPullParser <P_EmptyElement>d__6::<>4__this
0x3380d  stloc.2
0x3380e  ldloc.1
0x3380f  switch   loc_3383F, loc_338A5, loc_338DC, loc_33924, loc_33973, loc_339CE, loc_33A1A, loc_33A49, loc_33A67
0x33838  ldc.i4.0
0x33839  stloc.0
0x3383a  leave    loc_33A79
0x3383f  ldarg.0
0x33840  ldc.i4.m1
0x33841  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33846  ldloc.2
0x33847  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3384c  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33851  ldc.i4.2
0x33852  beq.s    loc_33875
0x33854  ldloc.2
0x33855  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3385a  ldloc.2
0x3385b  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33860  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33865  ldstr    aEmptyelementru// "EmptyElementRuleException"
0x3386a  call     string System.Xaml.SR::Get(string id)
0x3386f  newobj   instance void MS.Internal.Xaml.Parser.XamlUnexpectedParseException::.ctor(class MS.Internal.Xaml.Parser.XamlScanner xamlScanner, valuetype MS.Internal.Xaml.Parser.ScannerNodeType nodetype, string parseRule)
0x33874  throw
0x33875  ldarg.0
0x33876  ldloc.2
0x33877  ldloc.2
0x33878  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3387d  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Parser.XamlScanner::get_Type()
0x33882  ldloc.2
0x33883  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33888  callvirt instance string MS.Internal.Xaml.Parser.XamlScanner::get_Namespace()
0x3388d  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_StartObject(class System.Xaml.XamlType xamlType, string xamlNamespace)
0x33892  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x33897  ldarg.0
0x33898  ldc.i4.1
0x33899  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x3389e  ldc.i4.1
0x3389f  stloc.0
0x338a0  leave    loc_33A79
0x338a5  ldarg.0
0x338a6  ldc.i4.m1
0x338a7  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x338ac  ldloc.2
0x338ad  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x338b2  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x338b7  ldloc.2
0x338b8  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x338bd  brfalse  loc_3397A
0x338c2  ldarg.0
0x338c3  ldloc.2
0x338c4  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x338c9  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x338ce  ldarg.0
0x338cf  ldc.i4.2
0x338d0  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x338d5  ldc.i4.1
0x338d6  stloc.0
0x338d7  leave    loc_33A79
0x338dc  ldarg.0
0x338dd  ldc.i4.m1
0x338de  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x338e3  br       loc_3397A
0x338e8  ldarg.0
0x338e9  ldloc.2
0x338ea  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::LogicStream_Attribute()
0x338ef  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x338f4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x338f9  ldarg.0
0x338fa  ldc.i4.s 0xFD
0x338fc  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33901  br.s     loc_3392C
0x33903  ldarg.0
0x33904  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x33909  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x3390e  stloc.3
0x3390f  ldarg.0
0x33910  ldloc.3
0x33911  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x33916  ldarg.0
0x33917  ldc.i4.3
0x33918  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x3391d  ldc.i4.1
0x3391e  stloc.0
0x3391f  leave    loc_33A79
0x33924  ldarg.0
0x33925  ldc.i4.s 0xFD
0x33927  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x3392c  ldarg.0
0x3392d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x33932  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33937  brtrue.s loc_33903
0x33939  ldarg.0
0x3393a  call     instance void <P_EmptyElement>d__6::<>m__Finally1()
0x3393f  ldarg.0
0x33940  ldnull
0x33941  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x33946  ldloc.2
0x33947  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x3394c  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x33951  ldloc.2
0x33952  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x33957  brfalse.s loc_3397A
0x33959  ldarg.0
0x3395a  ldloc.2
0x3395b  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x33960  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x33965  ldarg.0
0x33966  ldc.i4.4
0x33967  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x3396c  ldc.i4.1
0x3396d  stloc.0
0x3396e  leave    loc_33A79
0x33973  ldarg.0
0x33974  ldc.i4.m1
0x33975  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x3397a  ldloc.2
0x3397b  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33980  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33985  ldc.i4.4
0x33986  beq      loc_338E8
0x3398b  br       loc_33A21
0x33990  ldarg.0
0x33991  ldloc.2
0x33992  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode> MS.Internal.Xaml.Parser.XamlPullParser::LogicStream_Attribute()
0x33997  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype System.Xaml.XamlNode>::GetEnumerator()
0x3399c  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x339a1  ldarg.0
0x339a2  ldc.i4.s 0xFC
0x339a4  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x339a9  br.s     loc_339D6
0x339ab  ldarg.0
0x339ac  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x339b1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode>::get_Current()
0x339b6  stloc.s  4
0x339b8  ldarg.0
0x339b9  ldloc.s  4
0x339bb  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x339c0  ldarg.0
0x339c1  ldc.i4.5
0x339c2  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x339c7  ldc.i4.1
0x339c8  stloc.0
0x339c9  leave    loc_33A79
0x339ce  ldarg.0
0x339cf  ldc.i4.s 0xFC
0x339d1  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x339d6  ldarg.0
0x339d7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x339dc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x339e1  brtrue.s loc_339AB
0x339e3  ldarg.0
0x339e4  call     instance void <P_EmptyElement>d__6::<>m__Finally2()
0x339e9  ldarg.0
0x339ea  ldnull
0x339eb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype System.Xaml.XamlNode> <P_EmptyElement>d__6::<>7__wrap1
0x339f0  ldloc.2
0x339f1  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x339f6  callvirt instance void MS.Internal.Xaml.Parser.XamlScanner::Read()
0x339fb  ldloc.2
0x339fc  call     instance bool MS.Internal.Xaml.Parser.XamlPullParser::get_ProvideLineInfo()
0x33a01  brfalse.s loc_33A21
0x33a03  ldarg.0
0x33a04  ldloc.2
0x33a05  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_LineInfo()
0x33a0a  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x33a0f  ldarg.0
0x33a10  ldc.i4.6
0x33a11  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33a16  ldc.i4.1
0x33a17  stloc.0
0x33a18  leave.s  loc_33A79
0x33a1a  ldarg.0
0x33a1b  ldc.i4.m1
0x33a1c  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33a21  ldloc.2
0x33a22  ldfld    class MS.Internal.Xaml.Parser.XamlScanner MS.Internal.Xaml.Parser.XamlPullParser::_xamlScanner
0x33a27  callvirt instance valuetype MS.Internal.Xaml.Parser.ScannerNodeType MS.Internal.Xaml.Parser.XamlScanner::get_NodeType()
0x33a2c  ldc.i4.3
0x33a2d  beq      loc_33990
0x33a32  ldarg.0
0x33a33  ldloc.2
0x33a34  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndOfAttributes()
0x33a39  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x33a3e  ldarg.0
0x33a3f  ldc.i4.7
0x33a40  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33a45  ldc.i4.1
0x33a46  stloc.0
0x33a47  leave.s  loc_33A79
0x33a49  ldarg.0
0x33a4a  ldc.i4.m1
0x33a4b  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33a50  ldarg.0
0x33a51  ldloc.2
0x33a52  call     instance valuetype System.Xaml.XamlNode MS.Internal.Xaml.Parser.XamlPullParser::Logic_EndObject()
0x33a57  stfld    valuetype System.Xaml.XamlNode <P_EmptyElement>d__6::<>2__current
0x33a5c  ldarg.0
0x33a5d  ldc.i4.8
0x33a5e  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33a63  ldc.i4.1
0x33a64  stloc.0
0x33a65  leave.s  loc_33A79
0x33a67  ldarg.0
0x33a68  ldc.i4.m1
0x33a69  stfld    int32 <P_EmptyElement>d__6::<>1__state
0x33a6e  ldc.i4.0
0x33a6f  stloc.0
0x33a70  leave.s  loc_33A79
0x33a72  ldarg.0
0x33a73  call     instance void <P_EmptyElement>d__6::System.IDisposable.Dispose()
0x33a78  endfinally
0x33a79  ldloc.0
0x33a7a  ret
```
