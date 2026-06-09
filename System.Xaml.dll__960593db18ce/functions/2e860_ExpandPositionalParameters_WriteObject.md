# ExpandPositionalParameters::WriteObject

- ea: `0x2e860`
- end: `0x2e922`
- name: `ExpandPositionalParameters::WriteObject`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x2100`
- `0x9ec0`
- `0xf350`
- `0x11f50`
- `0x2e840`
- `0x2e860`
- `0x2eb70`
- `0x2eb90`
- `0x2ebb0`
- `0x2ebc0`

## string_xrefs

- `0x2e911`: `WriteGetObject`
- `0x2e888`: `WriteStartObject`
- `0x2e904`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2e860  ldarg.3
0x2e861  brtrue   loc_2E904
0x2e866  ldarg.1
0x2e867  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e86c  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2e871  ldarg.2
0x2e872  callvirt instance void System.Xaml.XamlWriter::WriteStartObject(class System.Xaml.XamlType type)
0x2e877  ldarg.0
0x2e878  ldarg.1
0x2e879  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e87e  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2e883  callvirt instance bool System.Xaml.XamlMarkupExtensionWriter::get_Failed()
0x2e888  ldstr    aWritestartobje// "WriteStartObject"
0x2e88d  call     instance void ExpandPositionalParameters::ThrowIfFailed(bool fail, string operation)
0x2e892  ldloca.s 0
0x2e894  ldc.i4.1
0x2e895  ldarg.2
0x2e896  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2e89b  ldarg.1
0x2e89c  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e8a1  callvirt instance int32 PositionalParameterStateInfo::get_CurrentDepth()
0x2e8a6  brtrue.s loc_2E8C6
0x2e8a8  ldarg.1
0x2e8a9  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e8ae  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e8b3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::.ctor()
0x2e8b8  dup
0x2e8b9  ldloc.0
0x2e8ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2e8bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::Add(var<u1>)
0x2e8c4  br.s     loc_2E8EE
0x2e8c6  ldarg.1
0x2e8c7  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e8cc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e8d1  ldarg.1
0x2e8d2  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e8d7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>> PositionalParameterStateInfo::get_NodesList()
0x2e8dc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Count()
0x2e8e1  ldc.i4.1
0x2e8e2  sub
0x2e8e3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>>::get_Item(!!T0)
0x2e8e8  ldloc.0
0x2e8e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x2e8ee  ldarg.1
0x2e8ef  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2e8f4  dup
0x2e8f5  callvirt instance int32 PositionalParameterStateInfo::get_CurrentDepth()
0x2e8fa  stloc.1
0x2e8fb  ldloc.1
0x2e8fc  ldc.i4.1
0x2e8fd  add
0x2e8fe  callvirt instance void PositionalParameterStateInfo::set_CurrentDepth(int32 value)
0x2e903  ret
0x2e904  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2e909  ldc.i4.1
0x2e90a  newarr   [mscorlib]System.Object
0x2e90f  dup
0x2e910  ldc.i4.0
0x2e911  ldstr    aWritegetobject// "WriteGetObject"
0x2e916  stelem.ref
0x2e917  call     string System.Xaml.SR::Get(string id, object[] args)
0x2e91c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e921  throw
```
