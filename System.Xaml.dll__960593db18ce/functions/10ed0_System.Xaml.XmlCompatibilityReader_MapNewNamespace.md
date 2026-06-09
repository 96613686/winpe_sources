# System.Xaml.XmlCompatibilityReader::MapNewNamespace

- ea: `0x10ed0`
- end: `0x10f6b`
- name: `System.Xaml.XmlCompatibilityReader::MapNewNamespace`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10ea0`
- `0x10ed0`

## callees

- `0x104f0`
- `0x107c0`
- `0x10ed0`
- `0x10fc0`
- `0x10fe0`
- `0x117a0`
- `0x11f20`

## string_xrefs

- `0x10f2e`: `XCRCompatCycle`

## pseudocode

```c

```

## disassembly

```asm
0x10ed0  ldarg.0
0x10ed1  ldfld    class System.Xaml.IsXmlNamespaceSupportedCallback System.Xaml.XmlCompatibilityReader::_namespaceCallback
0x10ed6  brfalse  loc_10F69
0x10edb  ldarg.0
0x10edc  ldfld    class System.Xaml.IsXmlNamespaceSupportedCallback System.Xaml.XmlCompatibilityReader::_namespaceCallback
0x10ee1  ldarg.1
0x10ee2  ldloca.s 0
0x10ee4  callvirt instance bool System.Xaml.IsXmlNamespaceSupportedCallback::Invoke(string xmlNamespace, [out] string& newXmlNamespace)
0x10ee9  stloc.1
0x10eea  ldloc.1
0x10eeb  brfalse.s loc_10F5C
0x10eed  ldarg.0
0x10eee  ldarg.1
0x10eef  call     instance void System.Xaml.XmlCompatibilityReader::AddKnownNamespace(string namespaceName)
0x10ef4  ldloc.0
0x10ef5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10efa  brtrue.s loc_10F05
0x10efc  ldarg.1
0x10efd  ldloc.0
0x10efe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10f03  brfalse.s loc_10F14
0x10f05  ldarg.0
0x10f06  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.XmlCompatibilityReader::_namespaceMap
0x10f0b  ldarg.1
0x10f0c  ldarg.1
0x10f0d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x10f12  br.s     loc_10F69
0x10f14  ldarg.0
0x10f15  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.XmlCompatibilityReader::_namespaceMap
0x10f1a  ldloc.0
0x10f1b  ldloca.s 2
0x10f1d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x10f22  brtrue.s loc_10F4F
0x10f24  ldarg.0
0x10f25  ldloc.0
0x10f26  call     instance bool System.Xaml.XmlCompatibilityReader::IsNamespaceKnown(string namespaceName)
0x10f2b  brfalse.s loc_10F47
0x10f2d  ldarg.0
0x10f2e  ldstr    aXcrcompatcycle// "XCRCompatCycle"
0x10f33  call     string System.Xaml.SR::Get(string id)
0x10f38  ldc.i4.1
0x10f39  newarr   [mscorlib]System.Object
0x10f3e  dup
0x10f3f  ldc.i4.0
0x10f40  ldloc.0
0x10f41  stelem.ref
0x10f42  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x10f47  ldarg.0
0x10f48  ldloc.0
0x10f49  call     instance string System.Xaml.XmlCompatibilityReader::MapNewNamespace(string namespaceName)
0x10f4e  stloc.2
0x10f4f  ldarg.0
0x10f50  ldloc.2
0x10f51  ldarg.1
0x10f52  call     instance void System.Xaml.XmlCompatibilityReader::DeclareNamespaceCompatibility(string newNamespace, string oldNamespace)
0x10f57  ldloc.2
0x10f58  starg.s  1
0x10f5a  br.s     loc_10F69
0x10f5c  ldarg.0
0x10f5d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.XmlCompatibilityReader::_namespaceMap
0x10f62  ldarg.1
0x10f63  ldnull
0x10f64  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x10f69  ldarg.1
0x10f6a  ret
```
