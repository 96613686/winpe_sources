# System.Xaml.MS.Impl.XmlNsInfo::LoadNsDefHelper

- ea: `0x13070`
- end: `0x130b5`
- name: `System.Xaml.MS.Impl.XmlNsInfo::LoadNsDefHelper`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x12f60`

## callees

- `0x87c0`
- `0x11f50`
- `0x13070`
- `0x2f9b0`
- `0x2f9d0`
- `0x2f9e0`

## string_xrefs

- `0x1307b`: `BadXmlnsDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x13070  ldarg.2
0x13071  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13076  brtrue.s loc_1307B
0x13078  ldarg.3
0x13079  brtrue.s loc_1309B
0x1307b  ldstr    aBadxmlnsdefini// "BadXmlnsDefinition"
0x13080  ldc.i4.1
0x13081  newarr   [mscorlib]System.Object
0x13086  dup
0x13087  ldc.i4.0
0x13088  ldarg.s  4
0x1308a  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1308f  stelem.ref
0x13090  call     string System.Xaml.SR::Get(string id, object[] args)
0x13095  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0x1309a  throw
0x1309b  ldarg.1
0x1309c  newobj   instance void XmlNsDefinition::.ctor()
0x130a1  dup
0x130a2  ldarg.3
0x130a3  callvirt instance void XmlNsDefinition::set_ClrNamespace(string value)
0x130a8  dup
0x130a9  ldarg.2
0x130aa  callvirt instance void XmlNsDefinition::set_XmlNamespace(string value)
0x130af  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class XmlNsDefinition>::Add(var<u1>)
0x130b4  ret
```
