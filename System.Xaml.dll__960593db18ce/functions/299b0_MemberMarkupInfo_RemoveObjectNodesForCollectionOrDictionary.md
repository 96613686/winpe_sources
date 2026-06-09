# MemberMarkupInfo::RemoveObjectNodesForCollectionOrDictionary

- ea: `0x299b0`
- end: `0x29ac3`
- name: `MemberMarkupInfo::RemoveObjectNodesForCollectionOrDictionary`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x29920`

## callees

- `0x20e0`
- `0x2290`
- `0x22d0`
- `0x8b20`
- `0xa590`
- `0xb280`
- `0xd110`
- `0xd130`
- `0xd150`
- `0xef20`
- `0x29240`
- `0x299b0`
- `0x29fa0`
- `0x29fb0`
- `0x2a0f0`

## pseudocode

```c

```

## disassembly

```asm
0x299b0  ldarg.0
0x299b1  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x299b6  stloc.1
0x299b7  ldloca.s 1
0x299b9  call     instance class System.Xaml.XamlMember System.Xaml.XamlNode::get_Member()
0x299be  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x299c3  stloc.0
0x299c4  ldloc.0
0x299c5  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x299ca  brtrue.s loc_299D7
0x299cc  ldloc.0
0x299cd  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x299d2  brfalse  loc_29AC2
0x299d7  ldarg.0
0x299d8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x299dd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Count()
0x299e2  ldc.i4.1
0x299e3  bne.un   loc_29AC2
0x299e8  ldarg.0
0x299e9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x299ee  ldc.i4.0
0x299ef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Item(!!T0)
0x299f4  isinst   ObjectMarkupInfo
0x299f9  stloc.2
0x299fa  ldloc.2
0x299fb  brfalse  loc_29AC2
0x29a00  ldloc.2
0x29a01  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x29a06  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Count()
0x29a0b  ldc.i4.1
0x29a0c  bne.un   loc_29AC2
0x29a11  ldloc.0
0x29a12  ldloc.2
0x29a13  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x29a18  stloc.1
0x29a19  ldloca.s 1
0x29a1b  call     instance class System.Xaml.XamlType System.Xaml.XamlNode::get_XamlType()
0x29a20  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x29a25  brfalse  loc_29AC2
0x29a2a  ldloc.2
0x29a2b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x29a30  ldc.i4.0
0x29a31  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Item(!!T0)
0x29a36  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x29a3b  stloc.1
0x29a3c  ldloca.s 1
0x29a3e  call     instance class System.Xaml.XamlMember System.Xaml.XamlNode::get_Member()
0x29a43  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x29a48  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x29a4d  brfalse.s loc_29AC2
0x29a4f  ldloc.2
0x29a50  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x29a55  ldc.i4.0
0x29a56  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Item(!!T0)
0x29a5b  isinst   MemberMarkupInfo
0x29a60  stloc.3
0x29a61  ldloc.3
0x29a62  brfalse.s loc_29AC2
0x29a64  ldloc.3
0x29a65  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x29a6a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Count()
0x29a6f  ldc.i4.0
0x29a70  ble.s    loc_29AC2
0x29a72  ldloc.3
0x29a73  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x29a78  ldc.i4.0
0x29a79  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Item(!!T0)
0x29a7e  isinst   ObjectMarkupInfo
0x29a83  stloc.s  4
0x29a85  ldloc.s  4
0x29a87  brfalse.s loc_29AB6
0x29a89  ldloc.s  4
0x29a8b  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x29a90  stloc.1
0x29a91  ldloca.s 1
0x29a93  call     instance class System.Xaml.XamlType System.Xaml.XamlNode::get_XamlType()
0x29a98  ldnull
0x29a99  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x29a9e  brtrue.s loc_29AB6
0x29aa0  ldloc.s  4
0x29aa2  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x29aa7  stloc.1
0x29aa8  ldloca.s 1
0x29aaa  call     instance class System.Xaml.XamlType System.Xaml.XamlNode::get_XamlType()
0x29aaf  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x29ab4  brtrue.s loc_29AC2
0x29ab6  ldloc.2
0x29ab7  ldc.i4.2
0x29ab8  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x29abd  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x29ac2  ret
```
