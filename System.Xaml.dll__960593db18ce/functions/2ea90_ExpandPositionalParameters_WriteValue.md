# ExpandPositionalParameters::WriteValue

- ea: `0x2ea90`
- end: `0x2eb18`
- name: `ExpandPositionalParameters::WriteValue`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x2100`
- `0x9ec0`
- `0xf390`
- `0x2e840`
- `0x2ea90`
- `0x2eb70`
- `0x2eb90`
- `0x2ebb0`

## string_xrefs

- `0x2eab2`: `WriteValue`

## pseudocode

```c

```

## disassembly

```asm
0x2ea90  ldarg.1
0x2ea91  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ea96  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2ea9b  ldarg.2
0x2ea9c  callvirt instance void System.Xaml.XamlWriter::WriteValue(object value)
0x2eaa1  ldarg.0
0x2eaa2  ldarg.1
0x2eaa3  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2eaa8  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2eaad  callvirt instance bool System.Xaml.XamlMarkupExtensionWriter::get_Failed()
0x2eab2  ldstr    aWritevalue// "WriteValue"
0x2eab7  call     instance void ExpandPositionalParameters::ThrowIfFailed(bool fail, string operation)
0x2eabc  ldloca.s 0
0x2eabe  ldc.i4.6
0x2eabf  ldarg.2
0x2eac0  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2eac5  ldarg.1
0x2eac6  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2eacb  callvirt instance int32 PositionalParameterStateInfo::get_CurrentDepth()
0x2ead0  brtrue.s loc_2EAEF
0x2ead2  ldarg.1
0x2ead3  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ead8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2eadd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::.ctor()
0x2eae2  dup
0x2eae3  ldloc.0
0x2eae4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2eae9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::Add(var<u1>)
0x2eaee  ret
0x2eaef  ldarg.1
0x2eaf0  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2eaf5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2eafa  ldarg.1
0x2eafb  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2eb00  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2eb05  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Count()
0x2eb0a  ldc.i4.1
0x2eb0b  sub
0x2eb0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Item(!!T0)
0x2eb11  ldloc.0
0x2eb12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2eb17  ret
```
