# ObjectMarkupInfo::get_IsAttributableMarkupExtension

- ea: `0x2a3f0`
- end: `0x2a4aa`
- name: `ObjectMarkupInfo::get_IsAttributableMarkupExtension`
- size: `186`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x292a0`
- `0x292d0`
- `0x2a160`
- `0x2a8b0`

## callees

- `0x20d0`
- `0x2290`
- `0xd150`
- `0x292d0`
- `0x29fa0`
- `0x2a0f0`
- `0x2a3f0`

## pseudocode

```c

```

## disassembly

```asm
0x2a3f0  ldarg.0
0x2a3f1  ldflda   valuetype [mscorlib]System.Nullable`1<bool> ObjectMarkupInfo::isAttributableMarkupExtension
0x2a3f6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2a3fb  brfalse.s loc_2A409
0x2a3fd  ldarg.0
0x2a3fe  ldflda   valuetype [mscorlib]System.Nullable`1<bool> ObjectMarkupInfo::isAttributableMarkupExtension
0x2a403  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2a408  ret
0x2a409  ldarg.0
0x2a40a  call     instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2a40f  stloc.0
0x2a410  ldloca.s 0
0x2a412  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x2a417  ldc.i4.1
0x2a418  bne.un.s loc_2A42F
0x2a41a  ldarg.0
0x2a41b  call     instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2a420  stloc.0
0x2a421  ldloca.s 0
0x2a423  call     instance class System.Xaml.XamlType System.Xaml.XamlNode::get_XamlType()
0x2a428  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x2a42d  brfalse.s loc_2A440
0x2a42f  ldarg.0
0x2a430  call     instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2a435  stloc.0
0x2a436  ldloca.s 0
0x2a438  call     instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlNode::get_NodeType()
0x2a43d  ldc.i4.2
0x2a43e  bne.un.s loc_2A44E
0x2a440  ldarg.0
0x2a441  ldc.i4.0
0x2a442  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2a447  stfld    valuetype [mscorlib]System.Nullable`1<bool> ObjectMarkupInfo::isAttributableMarkupExtension
0x2a44c  ldc.i4.0
0x2a44d  ret
0x2a44e  ldarg.0
0x2a44f  call     instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2a454  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::GetEnumerator()
0x2a459  stloc.1
0x2a45a  br.s     loc_2A481
0x2a45c  ldloca.s 1
0x2a45e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::get_Current()
0x2a463  stloc.2
0x2a464  ldloc.2
0x2a465  castclass MemberMarkupInfo
0x2a46a  callvirt instance bool MemberMarkupInfo::get_IsAttributable()
0x2a46f  brtrue.s loc_2A481
0x2a471  ldarg.0
0x2a472  ldc.i4.0
0x2a473  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2a478  stfld    valuetype [mscorlib]System.Nullable`1<bool> ObjectMarkupInfo::isAttributableMarkupExtension
0x2a47d  ldc.i4.0
0x2a47e  stloc.3
0x2a47f  leave.s  loc_2A4A8
0x2a481  ldloca.s 1
0x2a483  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::MoveNext()
0x2a488  brtrue.s loc_2A45C
0x2a48a  leave.s  loc_2A49A
0x2a48c  ldloca.s 1
0x2a48e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>
0x2a494  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a499  endfinally
0x2a49a  ldarg.0
0x2a49b  ldc.i4.1
0x2a49c  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2a4a1  stfld    valuetype [mscorlib]System.Nullable`1<bool> ObjectMarkupInfo::isAttributableMarkupExtension
0x2a4a6  ldc.i4.1
0x2a4a7  ret
0x2a4a8  ldloc.3
0x2a4a9  ret
```
