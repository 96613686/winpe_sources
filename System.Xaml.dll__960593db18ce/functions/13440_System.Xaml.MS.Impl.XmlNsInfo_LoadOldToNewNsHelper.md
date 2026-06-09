# System.Xaml.MS.Impl.XmlNsInfo::LoadOldToNewNsHelper

- ea: `0x13440`
- end: `0x134a6`
- name: `System.Xaml.MS.Impl.XmlNsInfo::LoadOldToNewNsHelper`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13330`

## callees

- `0x87c0`
- `0x11f50`
- `0x13440`

## string_xrefs

- `0x13450`: `BadXmlnsCompat`
- `0x13479`: `DuplicateXmlnsCompat`

## pseudocode

```c

```

## disassembly

```asm
0x13440  ldarg.3
0x13441  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13446  brtrue.s loc_13450
0x13448  ldarg.2
0x13449  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1344e  brfalse.s loc_13470
0x13450  ldstr    aBadxmlnscompat// "BadXmlnsCompat"
0x13455  ldc.i4.1
0x13456  newarr   [mscorlib]System.Object
0x1345b  dup
0x1345c  ldc.i4.0
0x1345d  ldarg.s  4
0x1345f  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x13464  stelem.ref
0x13465  call     string System.Xaml.SR::Get(string id, object[] args)
0x1346a  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0x1346f  throw
0x13470  ldarg.1
0x13471  ldarg.2
0x13472  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x13477  brfalse.s loc_1349D
0x13479  ldstr    aDuplicatexmlns_0// "DuplicateXmlnsCompat"
0x1347e  ldc.i4.2
0x1347f  newarr   [mscorlib]System.Object
0x13484  dup
0x13485  ldc.i4.0
0x13486  ldarg.s  4
0x13488  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1348d  stelem.ref
0x1348e  dup
0x1348f  ldc.i4.1
0x13490  ldarg.2
0x13491  stelem.ref
0x13492  call     string System.Xaml.SR::Get(string id, object[] args)
0x13497  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0x1349c  throw
0x1349d  ldarg.1
0x1349e  ldarg.2
0x1349f  ldarg.3
0x134a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x134a5  ret
```
