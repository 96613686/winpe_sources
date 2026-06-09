# MemberMarkupInfo::ForReadWriteProperty

- ea: `0x29920`
- end: `0x299aa`
- name: `MemberMarkupInfo::ForReadWriteProperty`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x296e0`

## callees

- `0x2100`
- `0x8c00`
- `0xa3f0`
- `0xb280`
- `0xd500`
- `0x202a0`
- `0x29240`
- `0x29920`
- `0x299b0`
- `0x29d10`
- `0x29f70`
- `0x29fb0`
- `0x2bc60`

## pseudocode

```c

```

## disassembly

```asm
0x29920  ldarg.2
0x29921  callvirt instance class MS.Internal.Xaml.Runtime.ClrObjectRuntime SerializerContext::get_Runtime()
0x29926  ldarg.0
0x29927  ldarg.1
0x29928  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::GetValue(object obj, class System.Xaml.XamlMember property)
0x2992d  stloc.0
0x2992e  ldarg.1
0x2992f  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x29934  stloc.1
0x29935  ldarg.1
0x29936  ldloc.1
0x29937  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Lang()
0x2993c  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetAliasedProperty(class System.Xaml.XamlDirective directive)
0x29941  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x29946  brfalse.s loc_2997C
0x29948  ldloc.0
0x29949  isinst   [mscorlib]System.String
0x2994e  brfalse.s loc_2997C
0x29950  newobj   instance void MemberMarkupInfo::.ctor()
0x29955  dup
0x29956  ldc.i4.4
0x29957  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Lang()
0x2995c  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x29961  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x29966  dup
0x29967  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2996c  ldloc.0
0x2996d  ldarg.1
0x2996e  ldarg.2
0x2996f  call     class ObjectOrValueMarkupInfo MemberMarkupInfo::GetPropertyValueInfo(object propertyValue, class System.Xaml.XamlMember xamlProperty, class SerializerContext context)
0x29974  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x29979  stloc.2
0x2997a  br.s     loc_299A2
0x2997c  newobj   instance void MemberMarkupInfo::.ctor()
0x29981  dup
0x29982  ldc.i4.4
0x29983  ldarg.1
0x29984  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x29989  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2998e  dup
0x2998f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x29994  ldloc.0
0x29995  ldarg.1
0x29996  ldarg.2
0x29997  call     class ObjectOrValueMarkupInfo MemberMarkupInfo::GetPropertyValueInfo(object propertyValue, class System.Xaml.XamlMember xamlProperty, class SerializerContext context)
0x2999c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x299a1  stloc.2
0x299a2  ldloc.2
0x299a3  call     void MemberMarkupInfo::RemoveObjectNodesForCollectionOrDictionary(class MemberMarkupInfo memberInfo)
0x299a8  ldloc.2
0x299a9  ret
```
