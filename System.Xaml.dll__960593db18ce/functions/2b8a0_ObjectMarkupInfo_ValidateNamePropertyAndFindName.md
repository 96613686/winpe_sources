# ObjectMarkupInfo::ValidateNamePropertyAndFindName

- ea: `0x2b8a0`
- end: `0x2b913`
- name: `ObjectMarkupInfo::ValidateNamePropertyAndFindName`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x2abb0`

## callees

- `0x22b0`
- `0x22d0`
- `0x8810`
- `0xa3f0`
- `0xa4c0`
- `0x11f50`
- `0x29240`
- `0x29fa0`
- `0x2b8a0`

## string_xrefs

- `0x2b8eb`: `ObjectReaderXamlNamePropertyMustBeString`

## pseudocode

```c

```

## disassembly

```asm
0x2b8a0  ldarg.0
0x2b8a1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b8a6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Count()
0x2b8ab  ldc.i4.1
0x2b8ac  bne.un.s loc_2B8DC
0x2b8ae  ldarg.0
0x2b8af  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b8b4  ldc.i4.0
0x2b8b5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Item(!!T0)
0x2b8ba  isinst   ValueMarkupInfo
0x2b8bf  stloc.1
0x2b8c0  ldloc.1
0x2b8c1  brfalse.s loc_2B8DC
0x2b8c3  ldloc.1
0x2b8c4  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2b8c9  stloc.3
0x2b8ca  ldloca.s 3
0x2b8cc  call     instance object System.Xaml.XamlNode::get_Value()
0x2b8d1  isinst   [mscorlib]System.String
0x2b8d6  stloc.2
0x2b8d7  ldloc.2
0x2b8d8  brfalse.s loc_2B8DC
0x2b8da  ldloc.2
0x2b8db  ret
0x2b8dc  ldarg.0
0x2b8dd  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2b8e2  stloc.3
0x2b8e3  ldloca.s 3
0x2b8e5  call     instance class System.Xaml.XamlMember System.Xaml.XamlNode::get_Member()
0x2b8ea  stloc.0
0x2b8eb  ldstr    aObjectreaderxa_0// "ObjectReaderXamlNamePropertyMustBeStrin"...
0x2b8f0  ldc.i4.2
0x2b8f1  newarr   [mscorlib]System.Object
0x2b8f6  dup
0x2b8f7  ldc.i4.0
0x2b8f8  ldloc.0
0x2b8f9  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2b8fe  stelem.ref
0x2b8ff  dup
0x2b900  ldc.i4.1
0x2b901  ldloc.0
0x2b902  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2b907  stelem.ref
0x2b908  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b90d  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2b912  throw
```
