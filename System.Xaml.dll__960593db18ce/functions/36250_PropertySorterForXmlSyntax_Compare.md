# PropertySorterForXmlSyntax::Compare

- ea: `0x36250`
- end: `0x363f0`
- name: `PropertySorterForXmlSyntax::Compare`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x22d0`
- `0x8aa0`
- `0x8b20`
- `0x8b30`
- `0xa4c0`
- `0xa6e0`
- `0xb280`
- `0x29200`
- `0x29220`
- `0x29270`
- `0x292a0`
- `0x29fa0`
- `0x36250`

## pseudocode

```c

```

## disassembly

```asm
0x36250  ldarg.1
0x36251  castclass MemberMarkupInfo
0x36256  stloc.0
0x36257  ldarg.2
0x36258  castclass MemberMarkupInfo
0x3625d  stloc.1
0x3625e  ldarg.1
0x3625f  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x36264  stloc.s  0x14
0x36266  ldloca.s 0x14
0x36268  call     instance class System.Xaml.XamlMember System.Xaml.XamlNode::get_Member()
0x3626d  stloc.2
0x3626e  ldarg.2
0x3626f  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x36274  stloc.s  0x14
0x36276  ldloca.s 0x14
0x36278  call     instance class System.Xaml.XamlMember System.Xaml.XamlNode::get_Member()
0x3627d  stloc.3
0x3627e  ldloc.0
0x3627f  callvirt instance bool MemberMarkupInfo::get_IsFactoryMethod()
0x36284  stloc.s  4
0x36286  ldloc.1
0x36287  callvirt instance bool MemberMarkupInfo::get_IsFactoryMethod()
0x3628c  stloc.s  5
0x3628e  ldloc.s  4
0x36290  brfalse.s loc_36298
0x36292  ldloc.s  5
0x36294  brtrue.s loc_36298
0x36296  ldc.i4.m1
0x36297  ret
0x36298  ldloc.s  5
0x3629a  brfalse.s loc_362A2
0x3629c  ldloc.s  4
0x3629e  brtrue.s loc_362A2
0x362a0  ldc.i4.1
0x362a1  ret
0x362a2  ldloc.0
0x362a3  callvirt instance bool MemberMarkupInfo::get_IsContent()
0x362a8  brtrue.s loc_362B7
0x362aa  ldloc.2
0x362ab  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x362b0  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x362b5  br.s     loc_362B8
0x362b7  ldc.i4.1
0x362b8  stloc.s  6
0x362ba  ldloc.1
0x362bb  callvirt instance bool MemberMarkupInfo::get_IsContent()
0x362c0  brtrue.s loc_362CF
0x362c2  ldloc.3
0x362c3  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x362c8  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x362cd  br.s     loc_362D0
0x362cf  ldc.i4.1
0x362d0  stloc.s  7
0x362d2  ldloc.s  6
0x362d4  brfalse.s loc_362DC
0x362d6  ldloc.s  7
0x362d8  brtrue.s loc_362DC
0x362da  ldc.i4.1
0x362db  ret
0x362dc  ldloc.s  7
0x362de  brfalse.s loc_362E6
0x362e0  ldloc.s  6
0x362e2  brtrue.s loc_362E6
0x362e4  ldc.i4.m1
0x362e5  ret
0x362e6  ldloc.0
0x362e7  callvirt instance bool MemberMarkupInfo::get_IsAttributableMarkupExtension()
0x362ec  stloc.s  8
0x362ee  ldloc.1
0x362ef  callvirt instance bool MemberMarkupInfo::get_IsAttributableMarkupExtension()
0x362f4  stloc.s  9
0x362f6  ldloc.s  8
0x362f8  brfalse.s loc_36300
0x362fa  ldloc.s  9
0x362fc  brtrue.s loc_36300
0x362fe  ldc.i4.m1
0x362ff  ret
0x36300  ldloc.s  9
0x36302  brfalse.s loc_3630A
0x36304  ldloc.s  8
0x36306  brtrue.s loc_3630A
0x36308  ldc.i4.1
0x36309  ret
0x3630a  ldloc.0
0x3630b  callvirt instance bool MemberMarkupInfo::get_IsAtomic()
0x36310  stloc.s  0xA
0x36312  ldloc.1
0x36313  callvirt instance bool MemberMarkupInfo::get_IsAtomic()
0x36318  stloc.s  0xB
0x3631a  ldloc.2
0x3631b  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Initialization()
0x36320  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x36325  stloc.s  0xC
0x36327  ldloc.3
0x36328  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Initialization()
0x3632d  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x36332  stloc.s  0xD
0x36334  ldloc.s  0xA
0x36336  brfalse.s loc_3633F
0x36338  ldloc.s  0xC
0x3633a  ldc.i4.0
0x3633b  ceq
0x3633d  br.s     loc_36340
0x3633f  ldc.i4.0
0x36340  stloc.s  0xE
0x36342  ldloc.s  0xB
0x36344  brfalse.s loc_3634D
0x36346  ldloc.s  0xD
0x36348  ldc.i4.0
0x36349  ceq
0x3634b  br.s     loc_3634E
0x3634d  ldc.i4.0
0x3634e  stloc.s  0xF
0x36350  ldloc.s  0xE
0x36352  brfalse.s loc_3635A
0x36354  ldloc.s  0xF
0x36356  brtrue.s loc_3635A
0x36358  ldc.i4.m1
0x36359  ret
0x3635a  ldloc.s  0xF
0x3635c  brfalse.s loc_36364
0x3635e  ldloc.s  0xE
0x36360  brtrue.s loc_36364
0x36362  ldc.i4.1
0x36363  ret
0x36364  ldloc.s  0xA
0x36366  brfalse.s loc_3636E
0x36368  ldloc.s  0xB
0x3636a  brtrue.s loc_3636E
0x3636c  ldc.i4.m1
0x3636d  ret
0x3636e  ldloc.s  0xB
0x36370  brfalse.s loc_36378
0x36372  ldloc.s  0xA
0x36374  brtrue.s loc_36378
0x36376  ldc.i4.1
0x36377  ret
0x36378  ldloc.s  0xC
0x3637a  brfalse.s loc_36382
0x3637c  ldloc.s  0xD
0x3637e  brtrue.s loc_36382
0x36380  ldc.i4.m1
0x36381  ret
0x36382  ldloc.s  0xD
0x36384  brfalse.s loc_3638C
0x36386  ldloc.s  0xC
0x36388  brtrue.s loc_3638C
0x3638a  ldc.i4.1
0x3638b  ret
0x3638c  ldloc.2
0x3638d  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Arguments()
0x36392  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x36397  stloc.s  0x10
0x36399  ldloc.3
0x3639a  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Arguments()
0x3639f  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x363a4  stloc.s  0x11
0x363a6  ldloc.s  0x10
0x363a8  brfalse.s loc_363B0
0x363aa  ldloc.s  0x11
0x363ac  brtrue.s loc_363B0
0x363ae  ldc.i4.m1
0x363af  ret
0x363b0  ldloc.s  0x11
0x363b2  brfalse.s loc_363BA
0x363b4  ldloc.s  0x10
0x363b6  brtrue.s loc_363BA
0x363b8  ldc.i4.1
0x363b9  ret
0x363ba  ldloc.2
0x363bb  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x363c0  stloc.s  0x12
0x363c2  ldloc.3
0x363c3  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x363c8  stloc.s  0x13
0x363ca  ldloc.s  0x12
0x363cc  brfalse.s loc_363D4
0x363ce  ldloc.s  0x13
0x363d0  brtrue.s loc_363D4
0x363d2  ldc.i4.m1
0x363d3  ret
0x363d4  ldloc.s  0x13
0x363d6  brfalse.s loc_363DE
0x363d8  ldloc.s  0x12
0x363da  brtrue.s loc_363DE
0x363dc  ldc.i4.1
0x363dd  ret
0x363de  ldloc.2
0x363df  callvirt instance string System.Xaml.XamlMember::get_Name()
0x363e4  ldloc.3
0x363e5  callvirt instance string System.Xaml.XamlMember::get_Name()
0x363ea  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x363ef  ret
```
