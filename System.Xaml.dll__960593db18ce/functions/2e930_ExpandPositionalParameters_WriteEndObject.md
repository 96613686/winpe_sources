# ExpandPositionalParameters::WriteEndObject

- ea: `0x2e930`
- end: `0x2e9a1`
- name: `ExpandPositionalParameters::WriteEndObject`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x20e0`
- `0x9ec0`
- `0xf360`
- `0x2e840`
- `0x2eb70`
- `0x2eb90`
- `0x2ebb0`
- `0x2ebc0`

## string_xrefs

- `0x2e951`: `WriteEndObject`

## pseudocode

```c

```

## disassembly

```asm
0x2e930  ldarg.1
0x2e931  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e936  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2e93b  callvirt instance void System.Xaml.XamlWriter::WriteEndObject()
0x2e940  ldarg.0
0x2e941  ldarg.1
0x2e942  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e947  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2e94c  callvirt instance bool System.Xaml.XamlMarkupExtensionWriter::get_Failed()
0x2e951  ldstr    aWriteendobject// "WriteEndObject"
0x2e956  call     instance void ExpandPositionalParameters::ThrowIfFailed(bool fail, string operation)
0x2e95b  ldloca.s 0
0x2e95d  ldc.i4.3
0x2e95e  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x2e963  ldarg.1
0x2e964  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e969  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e96e  ldarg.1
0x2e96f  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e974  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e979  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Count()
0x2e97e  ldc.i4.1
0x2e97f  sub
0x2e980  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Item(!!T0)
0x2e985  ldloc.0
0x2e986  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2e98b  ldarg.1
0x2e98c  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e991  dup
0x2e992  callvirt instance int32 PositionalParameterStateInfo::get_CurrentDepth()
0x2e997  stloc.1
0x2e998  ldloc.1
0x2e999  ldc.i4.1
0x2e99a  sub
0x2e99b  callvirt instance void PositionalParameterStateInfo::set_CurrentDepth(int32 value)
0x2e9a0  ret
```
