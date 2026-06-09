# System.Windows.StaticResourceExtension::FindTheResourceDictionary

- ea: `0x1c500`
- end: `0x1c717`
- name: `System.Windows.StaticResourceExtension::FindTheResourceDictionary`
- size: `535`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1c720`
- `0x1c790`

## callees

- `0x1a6e0`
- `0x1c370`
- `0x1c500`
- `0x1db20`
- `0x38c70`

## string_xrefs

- `0x1c519`: `MarkupExtensionNoContext`
- `0x1c55e`: `MarkupExtensionNoContext`

## pseudocode

```c

```

## disassembly

```asm
0x1c500  ldarg.1
0x1c501  ldtoken  [System.Xaml]System.Xaml.IXamlSchemaContextProvider
0x1c506  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c50b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1c510  isinst   [System.Xaml]System.Xaml.IXamlSchemaContextProvider
0x1c515  stloc.0
0x1c516  ldloc.0
0x1c517  brtrue.s loc_1C545
0x1c519  ldstr    aMarkupextensio_0// "MarkupExtensionNoContext"
0x1c51e  ldc.i4.2
0x1c51f  newarr   [mscorlib]System.Object
0x1c524  dup
0x1c525  ldc.i4.0
0x1c526  ldarg.0
0x1c527  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c52c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1c531  stelem.ref
0x1c532  dup
0x1c533  ldc.i4.1
0x1c534  ldstr    aIxamlschemacon// "IXamlSchemaContextProvider"
0x1c539  stelem.ref
0x1c53a  call     string System.Windows.SR::Get(string id, object[] args)
0x1c53f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c544  throw
0x1c545  ldarg.1
0x1c546  ldtoken  [System.Xaml]System.Xaml.IAmbientProvider
0x1c54b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c550  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1c555  isinst   [System.Xaml]System.Xaml.IAmbientProvider
0x1c55a  stloc.1
0x1c55b  ldloc.1
0x1c55c  brtrue.s loc_1C58A
0x1c55e  ldstr    aMarkupextensio_0// "MarkupExtensionNoContext"
0x1c563  ldc.i4.2
0x1c564  newarr   [mscorlib]System.Object
0x1c569  dup
0x1c56a  ldc.i4.0
0x1c56b  ldarg.0
0x1c56c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c571  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1c576  stelem.ref
0x1c577  dup
0x1c578  ldc.i4.1
0x1c579  ldstr    aIambientprovid// "IAmbientProvider"
0x1c57e  stelem.ref
0x1c57f  call     string System.Windows.SR::Get(string id, object[] args)
0x1c584  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c589  throw
0x1c58a  ldloc.0
0x1c58b  callvirt instance class [System.Xaml]System.Xaml.XamlSchemaContext [System.Xaml]System.Xaml.IXamlSchemaContextProvider::get_SchemaContext()
0x1c590  stloc.2
0x1c591  ldloc.2
0x1c592  ldtoken  System.Windows.FrameworkElement
0x1c597  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c59c  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type)
0x1c5a1  stloc.3
0x1c5a2  ldloc.2
0x1c5a3  ldtoken  System.Windows.Style
0x1c5a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c5ad  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type)
0x1c5b2  stloc.s  4
0x1c5b4  ldloc.2
0x1c5b5  ldtoken  System.Windows.FrameworkTemplate
0x1c5ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c5bf  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type)
0x1c5c4  stloc.s  5
0x1c5c6  ldloc.2
0x1c5c7  ldtoken  System.Windows.Application
0x1c5cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c5d1  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type)
0x1c5d6  stloc.s  6
0x1c5d8  ldloc.2
0x1c5d9  ldtoken  System.Windows.FrameworkContentElement
0x1c5de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c5e3  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type)
0x1c5e8  stloc.s  7
0x1c5ea  ldloc.s  7
0x1c5ec  ldstr    aResources// "Resources"
0x1c5f1  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlType::GetMember(string)
0x1c5f6  stloc.s  8
0x1c5f8  ldloc.3
0x1c5f9  ldstr    aResources// "Resources"
0x1c5fe  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlType::GetMember(string)
0x1c603  stloc.s  9
0x1c605  ldloc.s  4
0x1c607  ldstr    aResources// "Resources"
0x1c60c  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlType::GetMember(string)
0x1c611  stloc.s  0xA
0x1c613  ldloc.s  4
0x1c615  ldstr    aBasedon// "BasedOn"
0x1c61a  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlType::GetMember(string)
0x1c61f  stloc.s  0xB
0x1c621  ldloc.s  5
0x1c623  ldstr    aResources// "Resources"
0x1c628  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlType::GetMember(string)
0x1c62d  stloc.s  0xC
0x1c62f  ldloc.s  6
0x1c631  ldstr    aResources// "Resources"
0x1c636  callvirt instance class [System.Xaml]System.Xaml.XamlMember [System.Xaml]System.Xaml.XamlType::GetMember(string)
0x1c63b  stloc.s  0xD
0x1c63d  ldc.i4.1
0x1c63e  newarr   [System.Xaml]System.Xaml.XamlType
0x1c643  dup
0x1c644  ldc.i4.0
0x1c645  ldloc.2
0x1c646  ldtoken  System.Windows.ResourceDictionary
0x1c64b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c650  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type)
0x1c655  stelem.ref
0x1c656  stloc.s  0xE
0x1c658  ldnull
0x1c659  stloc.s  0xF
0x1c65b  ldloc.1
0x1c65c  ldnull
0x1c65d  ldarg.2
0x1c65e  ldloc.s  0xE
0x1c660  ldc.i4.6
0x1c661  newarr   [System.Xaml]System.Xaml.XamlMember
0x1c666  dup
0x1c667  ldc.i4.0
0x1c668  ldloc.s  8
0x1c66a  stelem.ref
0x1c66b  dup
0x1c66c  ldc.i4.1
0x1c66d  ldloc.s  9
0x1c66f  stelem.ref
0x1c670  dup
0x1c671  ldc.i4.2
0x1c672  ldloc.s  0xA
0x1c674  stelem.ref
0x1c675  dup
0x1c676  ldc.i4.3
0x1c677  ldloc.s  0xB
0x1c679  stelem.ref
0x1c67a  dup
0x1c67b  ldc.i4.4
0x1c67c  ldloc.s  0xC
0x1c67e  stelem.ref
0x1c67f  dup
0x1c680  ldc.i4.5
0x1c681  ldloc.s  0xD
0x1c683  stelem.ref
0x1c684  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xaml]System.Xaml.AmbientPropertyValue> [System.Xaml]System.Xaml.IAmbientProvider::GetAllAmbientValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xaml]System.Xaml.XamlType>, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xaml]System.Xaml.XamlType>, class [System.Xaml]System.Xaml.XamlMember[])
0x1c689  stloc.s  0xF
0x1c68b  ldloc.s  0xF
0x1c68d  isinst   class [mscorlib]System.Collections.Generic.List`1<class [System.Xaml]System.Xaml.AmbientPropertyValue>
0x1c692  stloc.s  0x10
0x1c694  ldc.i4.0
0x1c695  stloc.s  0x11
0x1c697  br.s     loc_1C70A
0x1c699  ldloc.s  0x10
0x1c69b  ldloc.s  0x11
0x1c69d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [System.Xaml]System.Xaml.AmbientPropertyValue>::get_Item(!!T0)
0x1c6a2  stloc.s  0x12
0x1c6a4  ldloc.s  0x12
0x1c6a6  callvirt instance object [System.Xaml]System.Xaml.AmbientPropertyValue::get_Value()
0x1c6ab  isinst   System.Windows.ResourceDictionary
0x1c6b0  brfalse.s loc_1C6D2
0x1c6b2  ldloc.s  0x12
0x1c6b4  callvirt instance object [System.Xaml]System.Xaml.AmbientPropertyValue::get_Value()
0x1c6b9  castclass System.Windows.ResourceDictionary
0x1c6be  stloc.s  0x13
0x1c6c0  ldloc.s  0x13
0x1c6c2  ldarg.0
0x1c6c3  call     instance object System.Windows.StaticResourceExtension::get_ResourceKey()
0x1c6c8  callvirt instance bool System.Windows.ResourceDictionary::Contains(object key)
0x1c6cd  brfalse.s loc_1C6D2
0x1c6cf  ldloc.s  0x13
0x1c6d1  ret
0x1c6d2  ldloc.s  0x12
0x1c6d4  callvirt instance object [System.Xaml]System.Xaml.AmbientPropertyValue::get_Value()
0x1c6d9  isinst   System.Windows.Style
0x1c6de  brfalse.s loc_1C704
0x1c6e0  ldloc.s  0x12
0x1c6e2  callvirt instance object [System.Xaml]System.Xaml.AmbientPropertyValue::get_Value()
0x1c6e7  castclass System.Windows.Style
0x1c6ec  stloc.s  0x14
0x1c6ee  ldloc.s  0x14
0x1c6f0  ldarg.0
0x1c6f1  call     instance object System.Windows.StaticResourceExtension::get_ResourceKey()
0x1c6f6  callvirt instance class System.Windows.ResourceDictionary System.Windows.Style::FindResourceDictionary(object resourceKey)
0x1c6fb  stloc.s  0x15
0x1c6fd  ldloc.s  0x15
0x1c6ff  brfalse.s loc_1C704
0x1c701  ldloc.s  0x15
0x1c703  ret
0x1c704  ldloc.s  0x11
0x1c706  ldc.i4.1
0x1c707  add
0x1c708  stloc.s  0x11
0x1c70a  ldloc.s  0x11
0x1c70c  ldloc.s  0x10
0x1c70e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [System.Xaml]System.Xaml.AmbientPropertyValue>::get_Count()
0x1c713  blt.s    loc_1C699
0x1c715  ldnull
0x1c716  ret
```
