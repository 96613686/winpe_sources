# ObjectMarkupInfo::AddAttachedProperties

- ea: `0x2b3b0`
- end: `0x2b47b`
- name: `ObjectMarkupInfo::AddAttachedProperties`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x2abb0`
- `0x2b240`
- `0x2b740`

## callees

- `0x1360`
- `0x1370`
- `0x8810`
- `0xb280`
- `0xd530`
- `0xd8f0`
- `0x11f50`
- `0x20340`
- `0x29490`
- `0x2a0f0`
- `0x2b3b0`
- `0x2b920`
- `0x2bc60`
- `0x2bd50`
- `0x2bf00`

## string_xrefs

- `0x2b416`: `ObjectReaderAttachedPropertyNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x2b3b0  ldarg.2
0x2b3b1  callvirt instance class MS.Internal.Xaml.Runtime.ClrObjectRuntime SerializerContext::get_Runtime()
0x2b3b6  ldarg.0
0x2b3b7  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Xaml.AttachableMemberIdentifier, object>[] MS.Internal.Xaml.Runtime.XamlRuntime::GetAttachedProperties(object instance)
0x2b3bc  stloc.0
0x2b3bd  ldloc.0
0x2b3be  brfalse  loc_2B47A
0x2b3c3  ldloc.0
0x2b3c4  stloc.1
0x2b3c5  ldc.i4.0
0x2b3c6  stloc.2
0x2b3c7  br       loc_2B471
0x2b3cc  ldloc.1
0x2b3cd  ldloc.2
0x2b3ce  ldelem   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Xaml.AttachableMemberIdentifier, object>
0x2b3d3  stloc.3
0x2b3d4  ldarg.2
0x2b3d5  ldloca.s 3
0x2b3d7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Xaml.AttachableMemberIdentifier, object>::get_Key()
0x2b3dc  callvirt instance class [mscorlib]System.Type System.Xaml.AttachableMemberIdentifier::get_DeclaringType()
0x2b3e1  callvirt instance class System.Xaml.XamlType SerializerContext::GetXamlType(class [mscorlib]System.Type clrType)
0x2b3e6  stloc.s  4
0x2b3e8  ldloc.s  4
0x2b3ea  ldarg.2
0x2b3eb  callvirt instance class [mscorlib]System.Reflection.Assembly SerializerContext::get_LocalAssembly()
0x2b3f0  callvirt instance bool System.Xaml.XamlType::IsVisibleTo(class [mscorlib]System.Reflection.Assembly accessingAssembly)
0x2b3f5  brfalse.s loc_2B46D
0x2b3f7  ldloc.s  4
0x2b3f9  ldloca.s 3
0x2b3fb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Xaml.AttachableMemberIdentifier, object>::get_Key()
0x2b400  callvirt instance string System.Xaml.AttachableMemberIdentifier::get_MemberName()
0x2b405  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetAttachableMember(string name)
0x2b40a  stloc.s  5
0x2b40c  ldloc.s  5
0x2b40e  ldnull
0x2b40f  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2b414  brfalse.s loc_2B440
0x2b416  ldstr    aObjectreaderat// "ObjectReaderAttachedPropertyNotFound"
0x2b41b  ldc.i4.2
0x2b41c  newarr   [mscorlib]System.Object
0x2b421  dup
0x2b422  ldc.i4.0
0x2b423  ldloc.s  4
0x2b425  stelem.ref
0x2b426  dup
0x2b427  ldc.i4.1
0x2b428  ldloca.s 3
0x2b42a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Xaml.AttachableMemberIdentifier, object>::get_Key()
0x2b42f  callvirt instance string System.Xaml.AttachableMemberIdentifier::get_MemberName()
0x2b434  stelem.ref
0x2b435  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b43a  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2b43f  throw
0x2b440  ldloc.s  5
0x2b442  ldarg.2
0x2b443  call     bool ObjectMarkupInfo::CanPropertyXamlRoundtrip(class System.Xaml.XamlMember property, class SerializerContext context)
0x2b448  brfalse.s loc_2B46D
0x2b44a  ldarg.0
0x2b44b  ldloc.s  5
0x2b44d  ldloca.s 3
0x2b44f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Xaml.AttachableMemberIdentifier, object>::get_Value()
0x2b454  ldarg.2
0x2b455  call     class MemberMarkupInfo MemberMarkupInfo::ForAttachedProperty(object source, class System.Xaml.XamlMember attachedProperty, object value, class SerializerContext context)
0x2b45a  stloc.s  6
0x2b45c  ldloc.s  6
0x2b45e  brfalse.s loc_2B46D
0x2b460  ldarg.1
0x2b461  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2b466  ldloc.s  6
0x2b468  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2b46d  ldloc.2
0x2b46e  ldc.i4.1
0x2b46f  add
0x2b470  stloc.2
0x2b471  ldloc.2
0x2b472  ldloc.1
0x2b473  ldlen
0x2b474  conv.i4
0x2b475  blt      loc_2B3CC
0x2b47a  ret
```
