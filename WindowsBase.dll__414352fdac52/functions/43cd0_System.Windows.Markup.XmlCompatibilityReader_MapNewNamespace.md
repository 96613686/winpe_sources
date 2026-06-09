# System.Windows.Markup.XmlCompatibilityReader::MapNewNamespace

- ea: `0x43cd0`
- end: `0x43d6b`
- name: `System.Windows.Markup.XmlCompatibilityReader::MapNewNamespace`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43ca0`
- `0x43cd0`

## callees

- `0x2c100`
- `0x432f0`
- `0x435c0`
- `0x43cd0`
- `0x43dc0`
- `0x43de0`
- `0x445a0`

## string_xrefs

- `0x43d2e`: `XCRCompatCycle`

## pseudocode

```c

```

## disassembly

```asm
0x43cd0  ldarg.0
0x43cd1  ldfld    class System.Windows.Markup.IsXmlNamespaceSupportedCallback System.Windows.Markup.XmlCompatibilityReader::_namespaceCallback
0x43cd6  brfalse  loc_43D69
0x43cdb  ldarg.0
0x43cdc  ldfld    class System.Windows.Markup.IsXmlNamespaceSupportedCallback System.Windows.Markup.XmlCompatibilityReader::_namespaceCallback
0x43ce1  ldarg.1
0x43ce2  ldloca.s 0
0x43ce4  callvirt instance bool System.Windows.Markup.IsXmlNamespaceSupportedCallback::Invoke(string xmlNamespace, [out] string& newXmlNamespace)
0x43ce9  stloc.1
0x43cea  ldloc.1
0x43ceb  brfalse.s loc_43D5C
0x43ced  ldarg.0
0x43cee  ldarg.1
0x43cef  call     instance void System.Windows.Markup.XmlCompatibilityReader::AddKnownNamespace(string namespaceName)
0x43cf4  ldloc.0
0x43cf5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x43cfa  brtrue.s loc_43D05
0x43cfc  ldarg.1
0x43cfd  ldloc.0
0x43cfe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43d03  brfalse.s loc_43D14
0x43d05  ldarg.0
0x43d06  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlCompatibilityReader::_namespaceMap
0x43d0b  ldarg.1
0x43d0c  ldarg.1
0x43d0d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x43d12  br.s     loc_43D69
0x43d14  ldarg.0
0x43d15  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlCompatibilityReader::_namespaceMap
0x43d1a  ldloc.0
0x43d1b  ldloca.s 2
0x43d1d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x43d22  brtrue.s loc_43D4F
0x43d24  ldarg.0
0x43d25  ldloc.0
0x43d26  call     instance bool System.Windows.Markup.XmlCompatibilityReader::IsNamespaceKnown(string namespaceName)
0x43d2b  brfalse.s loc_43D47
0x43d2d  ldarg.0
0x43d2e  ldstr    aXcrcompatcycle// "XCRCompatCycle"
0x43d33  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x43d38  ldc.i4.1
0x43d39  newarr   [mscorlib]System.Object
0x43d3e  dup
0x43d3f  ldc.i4.0
0x43d40  ldloc.0
0x43d41  stelem.ref
0x43d42  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x43d47  ldarg.0
0x43d48  ldloc.0
0x43d49  call     instance string System.Windows.Markup.XmlCompatibilityReader::MapNewNamespace(string namespaceName)
0x43d4e  stloc.2
0x43d4f  ldarg.0
0x43d50  ldloc.2
0x43d51  ldarg.1
0x43d52  call     instance void System.Windows.Markup.XmlCompatibilityReader::DeclareNamespaceCompatibility(string newNamespace, string oldNamespace)
0x43d57  ldloc.2
0x43d58  starg.s  1
0x43d5a  br.s     loc_43D69
0x43d5c  ldarg.0
0x43d5d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlCompatibilityReader::_namespaceMap
0x43d62  ldarg.1
0x43d63  ldnull
0x43d64  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x43d69  ldarg.1
0x43d6a  ret
```
