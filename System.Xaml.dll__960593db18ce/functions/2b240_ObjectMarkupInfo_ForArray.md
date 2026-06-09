# ObjectMarkupInfo::ForArray

- ea: `0x2b240`
- end: `0x2b3a5`
- name: `ObjectMarkupInfo::ForArray`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x2b4a0`

## callees

- `0x20e0`
- `0x2100`
- `0x8810`
- `0x8940`
- `0x8b20`
- `0xd230`
- `0xd370`
- `0xd430`
- `0x11f20`
- `0x291e0`
- `0x29240`
- `0x29f70`
- `0x29fb0`
- `0x2a0f0`
- `0x2a130`
- `0x2b240`
- `0x2b3b0`
- `0x2b4a0`
- `0x2b9a0`
- `0x2bf40`
- `0x2c140`

## string_xrefs

- `0x2b249`: `ObjectReaderMultidimensionalArrayNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x2b240  ldarg.0
0x2b241  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x2b246  ldc.i4.1
0x2b247  ble.s    loc_2B259
0x2b249  ldstr    aObjectreadermu// "ObjectReaderMultidimensionalArrayNotSup"...
0x2b24e  call     string System.Xaml.SR::Get(string id)
0x2b253  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2b258  throw
0x2b259  ldarg.1
0x2b25a  ldarg.0
0x2b25b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b260  callvirt instance class System.Xaml.XamlType SerializerContext::LocalAssemblyAwareGetXamlType(class [mscorlib]System.Type clrType)
0x2b265  stloc.0
0x2b266  ldloc.0
0x2b267  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_ItemType()
0x2b26c  stloc.1
0x2b26d  newobj   instance void MemberMarkupInfo::.ctor()
0x2b272  dup
0x2b273  ldc.i4.4
0x2b274  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x2b279  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2b27e  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2b283  stloc.2
0x2b284  ldarg.0
0x2b285  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Array::GetEnumerator()
0x2b28a  stloc.s  4
0x2b28c  br.s     loc_2B2AC
0x2b28e  ldloc.s  4
0x2b290  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2b295  stloc.s  5
0x2b297  ldloc.2
0x2b298  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b29d  ldloc.s  5
0x2b29f  ldarg.1
0x2b2a0  ldnull
0x2b2a1  ldc.i4.0
0x2b2a2  call     class ObjectMarkupInfo ObjectMarkupInfo::ForObject(object value, class SerializerContext context, [opt] class [System]System.ComponentModel.TypeConverter instanceConverter, [opt] bool isRoot)
0x2b2a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b2ac  ldloc.s  4
0x2b2ae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b2b3  brtrue.s loc_2B28E
0x2b2b5  leave.s  loc_2B2CC
0x2b2b7  ldloc.s  4
0x2b2b9  isinst   [mscorlib]System.IDisposable
0x2b2be  stloc.s  6
0x2b2c0  ldloc.s  6
0x2b2c2  brfalse.s loc_2B2CB
0x2b2c4  ldloc.s  6
0x2b2c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b2cb  endfinally
0x2b2cc  newobj   instance void ObjectMarkupInfo::.ctor()
0x2b2d1  dup
0x2b2d2  ldc.i4.1
0x2b2d3  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Array()
0x2b2d8  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2b2dd  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2b2e2  dup
0x2b2e3  ldarg.0
0x2b2e4  callvirt instance void ObjectMarkupInfo::set_Object(object value)
0x2b2e9  dup
0x2b2ea  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2b2ef  newobj   instance void MemberMarkupInfo::.ctor()
0x2b2f4  dup
0x2b2f5  ldc.i4.4
0x2b2f6  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Array()
0x2b2fb  ldstr    aType_0// "Type"
0x2b300  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetMember(string name)
0x2b305  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2b30a  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2b30f  dup
0x2b310  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b315  newobj   instance void ValueMarkupInfo::.ctor()
0x2b31a  dup
0x2b31b  ldc.i4.6
0x2b31c  ldarg.1
0x2b31d  ldloc.1
0x2b31e  callvirt instance string SerializerContext::ConvertXamlTypeToString(class System.Xaml.XamlType type)
0x2b323  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2b328  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2b32d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b332  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b337  stloc.3
0x2b338  ldloc.2
0x2b339  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b33e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Count()
0x2b343  brfalse.s loc_2B39B
0x2b345  newobj   instance void ObjectMarkupInfo::.ctor()
0x2b34a  dup
0x2b34b  ldc.i4.2
0x2b34c  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x2b351  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2b356  dup
0x2b357  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2b35c  ldloc.2
0x2b35d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b362  stloc.s  7
0x2b364  newobj   instance void MemberMarkupInfo::.ctor()
0x2b369  dup
0x2b36a  ldc.i4.4
0x2b36b  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Array()
0x2b370  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::get_ContentProperty()
0x2b375  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2b37a  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2b37f  dup
0x2b380  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b385  ldloc.s  7
0x2b387  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b38c  stloc.s  8
0x2b38e  ldloc.3
0x2b38f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2b394  ldloc.s  8
0x2b396  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b39b  ldarg.0
0x2b39c  ldloc.3
0x2b39d  ldarg.1
0x2b39e  call     void ObjectMarkupInfo::AddAttachedProperties(object value, class ObjectMarkupInfo objectInfo, class SerializerContext context)
0x2b3a3  ldloc.3
0x2b3a4  ret
```
