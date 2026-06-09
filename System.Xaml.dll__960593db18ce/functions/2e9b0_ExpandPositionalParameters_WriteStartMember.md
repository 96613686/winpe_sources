# ExpandPositionalParameters::WriteStartMember

- ea: `0x2e9b0`
- end: `0x2ea38`
- name: `ExpandPositionalParameters::WriteStartMember`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x2100`
- `0x9ec0`
- `0xf370`
- `0x2e840`
- `0x2e9b0`
- `0x2eb70`
- `0x2eb90`
- `0x2ebb0`

## string_xrefs

- `0x2e9d2`: `WriteStartMember`

## pseudocode

```c

```

## disassembly

```asm
0x2e9b0  ldarg.1
0x2e9b1  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e9b6  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2e9bb  ldarg.2
0x2e9bc  callvirt instance void System.Xaml.XamlWriter::WriteStartMember(class System.Xaml.XamlMember xamlMember)
0x2e9c1  ldarg.0
0x2e9c2  ldarg.1
0x2e9c3  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e9c8  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2e9cd  callvirt instance bool System.Xaml.XamlMarkupExtensionWriter::get_Failed()
0x2e9d2  ldstr    aWritestartmemb// "WriteStartMember"
0x2e9d7  call     instance void ExpandPositionalParameters::ThrowIfFailed(bool fail, string operation)
0x2e9dc  ldloca.s 0
0x2e9de  ldc.i4.4
0x2e9df  ldarg.2
0x2e9e0  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2e9e5  ldarg.1
0x2e9e6  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e9eb  callvirt instance int32 PositionalParameterStateInfo::get_CurrentDepth()
0x2e9f0  brtrue.s loc_2EA0F
0x2e9f2  ldarg.1
0x2e9f3  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e9f8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e9fd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::.ctor()
0x2ea02  dup
0x2ea03  ldloc.0
0x2ea04  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2ea09  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::Add(var<u1>)
0x2ea0e  ret
0x2ea0f  ldarg.1
0x2ea10  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ea15  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2ea1a  ldarg.1
0x2ea1b  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ea20  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2ea25  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Count()
0x2ea2a  ldc.i4.1
0x2ea2b  sub
0x2ea2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Item(!!T0)
0x2ea31  ldloc.0
0x2ea32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2ea37  ret
```
