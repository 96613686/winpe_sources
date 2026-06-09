# System.Xaml.MS.Impl.XmlNsInfo::LoadPrefixesHelper

- ea: `0x135c0`
- end: `0x13613`
- name: `System.Xaml.MS.Impl.XmlNsInfo::LoadPrefixesHelper`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x134b0`

## callees

- `0x87c0`
- `0x11f50`
- `0x12f20`
- `0x135c0`

## string_xrefs

- `0x135d0`: `BadXmlnsPrefix`

## pseudocode

```c

```

## disassembly

```asm
0x135c0  ldarg.3
0x135c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x135c6  brtrue.s loc_135D0
0x135c8  ldarg.2
0x135c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x135ce  brfalse.s loc_135F0
0x135d0  ldstr    aBadxmlnsprefix// "BadXmlnsPrefix"
0x135d5  ldc.i4.1
0x135d6  newarr   [mscorlib]System.Object
0x135db  dup
0x135dc  ldc.i4.0
0x135dd  ldarg.s  4
0x135df  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x135e4  stelem.ref
0x135e5  call     string System.Xaml.SR::Get(string id, object[] args)
0x135ea  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0x135ef  throw
0x135f0  ldarg.1
0x135f1  ldarg.2
0x135f2  ldloca.s 0
0x135f4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x135f9  brfalse.s loc_1360A
0x135fb  ldloc.0
0x135fc  ldarg.3
0x135fd  call     string System.Xaml.MS.Impl.XmlNsInfo::GetPreferredPrefix(string prefix1, string prefix2)
0x13602  ldarg.3
0x13603  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13608  brfalse.s loc_13612
0x1360a  ldarg.1
0x1360b  ldarg.2
0x1360c  ldarg.3
0x1360d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x13612  ret
```
