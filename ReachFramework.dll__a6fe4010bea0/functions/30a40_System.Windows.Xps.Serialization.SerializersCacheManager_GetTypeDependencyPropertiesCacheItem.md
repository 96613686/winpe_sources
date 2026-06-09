# System.Windows.Xps.Serialization.SerializersCacheManager::GetTypeDependencyPropertiesCacheItem

- ea: `0x30a40`
- end: `0x30cb0`
- name: `System.Windows.Xps.Serialization.SerializersCacheManager::GetTypeDependencyPropertiesCacheItem`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x308d0`

## callees

- `0x1fd00`
- `0x30a40`
- `0x30cb0`
- `0x341e0`
- `0x34390`
- `0x343a0`
- `0x34630`
- `0x34680`
- `0x34810`
- `0x348a0`

## pseudocode

```c

```

## disassembly

```asm
0x30a40  ldarg.1
0x30a41  brtrue.s loc_30A4E
0x30a43  ldstr    aSerializableob_1// "serializableObject"
0x30a48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30a4d  throw
0x30a4e  ldarg.1
0x30a4f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x30a54  stloc.0
0x30a55  ldarg.0
0x30a56  ldfld    class [mscorlib]System.Collections.IDictionary System.Windows.Xps.Serialization.SerializersCacheManager::_typesDependencyPropertiesCacheTable
0x30a5b  ldloc.0
0x30a5c  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x30a61  castclass System.Windows.Xps.Serialization.TypeDependencyPropertiesCacheItem
0x30a66  stloc.1
0x30a67  ldloc.1
0x30a68  brtrue   loc_30CAE
0x30a6d  ldarg.1
0x30a6e  isinst   [WindowsBase]System.Windows.DependencyObject
0x30a73  stloc.2
0x30a74  ldloc.2
0x30a75  brfalse  loc_30CAE
0x30a7a  ldloca.s 3
0x30a7c  ldc.i4.1
0x30a7d  call     instance void System.Windows.Xps.Serialization.DependencyPropertyList::.ctor(int32 capacity)
0x30a82  ldloc.2
0x30a83  callvirt instance valuetype [WindowsBase]System.Windows.LocalValueEnumerator [WindowsBase]System.Windows.DependencyObject::GetLocalValueEnumerator()
0x30a88  stloc.s  4
0x30a8a  br.s     loc_30AA7
0x30a8c  ldloca.s 4
0x30a8e  call     instance valuetype [WindowsBase]System.Windows.LocalValueEntry [WindowsBase]System.Windows.LocalValueEnumerator::get_Current()
0x30a93  stloc.s  6
0x30a95  ldloca.s 6
0x30a97  call     instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.LocalValueEntry::get_Property()
0x30a9c  stloc.s  5
0x30a9e  ldloca.s 3
0x30aa0  ldloc.s  5
0x30aa2  call     instance void System.Windows.Xps.Serialization.DependencyPropertyList::Add(class [WindowsBase]System.Windows.DependencyProperty item)
0x30aa7  ldloca.s 4
0x30aa9  call     instance bool [WindowsBase]System.Windows.LocalValueEnumerator::MoveNext()
0x30aae  brtrue.s loc_30A8C
0x30ab0  ldloc.3
0x30ab1  ldfld    int32 System.Windows.Xps.Serialization.DependencyPropertyList::Count
0x30ab6  ldc.i4.0
0x30ab7  ble      loc_30CAE
0x30abc  ldc.i4.0
0x30abd  stloc.s  7
0x30abf  ldloc.3
0x30ac0  ldfld    int32 System.Windows.Xps.Serialization.DependencyPropertyList::Count
0x30ac5  newarr   System.Windows.Xps.Serialization.TypeDependencyPropertyCache
0x30aca  stloc.s  8
0x30acc  ldc.i4.0
0x30acd  stloc.s  9
0x30acf  br       loc_30C62
0x30ad4  ldloc.3
0x30ad5  ldfld    class [WindowsBase]System.Windows.DependencyProperty[] System.Windows.Xps.Serialization.DependencyPropertyList::List
0x30ada  ldloc.s  9
0x30adc  ldelem.ref
0x30add  stloc.s  0xA
0x30adf  ldc.i4.1
0x30ae0  stloc.s  0xB
0x30ae2  ldnull
0x30ae3  stloc.s  0xC
0x30ae5  ldnull
0x30ae6  stloc.s  0xD
0x30ae8  ldnull
0x30ae9  stloc.s  0xE
0x30aeb  ldnull
0x30aec  stloc.s  0xF
0x30aee  ldloc.s  0xA
0x30af0  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_PropertyType()
0x30af5  stloc.s  0x10
0x30af7  ldloc.s  0xA
0x30af9  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x30afe  ldstr    aGet// "Get"
0x30b03  ldloc.s  0xA
0x30b05  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x30b0a  call     string [mscorlib]System.String::Concat(string, string)
0x30b0f  ldc.i4.s 0x78
0x30b11  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x30b16  stloc.s  0x11
0x30b18  ldloc.s  0x11
0x30b1a  ldnull
0x30b1b  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0x30b20  brfalse  loc_30BEB
0x30b25  ldnull
0x30b26  stloc.s  0x12
0x30b28  ldloc.s  0xA
0x30b2a  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x30b2f  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x30b34  stloc.s  0x13
0x30b36  ldloc.s  0xA
0x30b38  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x30b3d  stloc.s  0x14
0x30b3f  ldc.i4.0
0x30b40  stloc.s  0x15
0x30b42  br.s     loc_30B64
0x30b44  ldloc.s  0x13
0x30b46  ldloc.s  0x15
0x30b48  ldelem.ref
0x30b49  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x30b4e  ldloc.s  0x14
0x30b50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x30b55  brfalse.s loc_30B5E
0x30b57  ldloc.s  0x13
0x30b59  ldloc.s  0x15
0x30b5b  ldelem.ref
0x30b5c  stloc.s  0x12
0x30b5e  ldloc.s  0x15
0x30b60  ldc.i4.1
0x30b61  add
0x30b62  stloc.s  0x15
0x30b64  ldloc.s  0x15
0x30b66  ldloc.s  0x13
0x30b68  ldlen
0x30b69  conv.i4
0x30b6a  bge.s    loc_30B76
0x30b6c  ldloc.s  0x12
0x30b6e  ldnull
0x30b6f  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Equality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x30b74  brtrue.s loc_30B44
0x30b76  ldloc.s  0x12
0x30b78  ldnull
0x30b79  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x30b7e  brfalse.s loc_30BEB
0x30b80  ldloc.s  0x12
0x30b82  stloc.s  0x11
0x30b84  ldloc.s  0x12
0x30b86  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x30b8b  call     string System.Windows.Xps.Packaging.XpsNamedProperties::get_PrintTicketProperty()
0x30b90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x30b95  brfalse.s loc_30BEB
0x30b97  ldloc.s  0xA
0x30b99  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x30b9e  ldtoken  [PresentationFramework]System.Windows.Documents.FixedPage
0x30ba3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30ba8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x30bad  brtrue.s loc_30BDF
0x30baf  ldloc.s  0xA
0x30bb1  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x30bb6  ldtoken  [PresentationFramework]System.Windows.Documents.FixedDocument
0x30bbb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30bc0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x30bc5  brtrue.s loc_30BDF
0x30bc7  ldloc.s  0xA
0x30bc9  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x30bce  ldtoken  [PresentationFramework]System.Windows.Documents.FixedDocumentSequence
0x30bd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30bd8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x30bdd  brfalse.s loc_30BEB
0x30bdf  ldtoken  System.Printing.PrintTicket
0x30be4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30be9  stloc.s  0x10
0x30beb  ldloc.s  0x11
0x30bed  ldnull
0x30bee  call     bool [mscorlib]System.Reflection.MemberInfo::op_Inequality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0x30bf3  brfalse.s loc_30C5C
0x30bf5  ldloc.s  0x11
0x30bf7  ldarg.0
0x30bf8  ldloca.s 0xB
0x30bfa  ldloca.s 0xC
0x30bfc  ldloca.s 0xD
0x30bfe  ldloca.s 0xE
0x30c00  ldloca.s 0xF
0x30c02  call     bool System.Windows.Xps.Serialization.TypeDependencyPropertyCache::CanSerializeProperty(class [mscorlib]System.Reflection.MemberInfo memberInfo, class System.Windows.Xps.Serialization.SerializersCacheManager serializersCacheManager, [out] valuetype [System]System.ComponentModel.DesignerSerializationVisibility& visibility, [out] class [mscorlib]System.Type& serializerTypeForProperty, [out] class [System]System.ComponentModel.TypeConverter& typeConverterForProperty, [out] class [System]System.ComponentModel.DefaultValueAttribute& defaultValueAttr, [out] class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute& designerSerializationFlagsAttr)
0x30c07  brfalse.s loc_30C5C
0x30c09  ldarg.0
0x30c0a  ldloc.s  0x10
0x30c0c  call     instance class System.Windows.Xps.Serialization.TypeCacheItem System.Windows.Xps.Serialization.SerializersCacheManager::GetTypeCacheItem(class [mscorlib]System.Type serializableObjectType)
0x30c11  stloc.s  0x16
0x30c13  ldloc.s  0xC
0x30c15  ldnull
0x30c16  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x30c1b  brtrue.s loc_30C21
0x30c1d  ldloc.s  0xC
0x30c1f  br.s     loc_30C28
0x30c21  ldloc.s  0x16
0x30c23  callvirt instance class [mscorlib]System.Type System.Windows.Xps.Serialization.TypeCacheItem::get_SerializerType()
0x30c28  stloc.s  0xC
0x30c2a  ldloc.s  0xD
0x30c2c  brfalse.s loc_30C32
0x30c2e  ldloc.s  0xD
0x30c30  br.s     loc_30C39
0x30c32  ldloc.s  0x16
0x30c34  callvirt instance class [System]System.ComponentModel.TypeConverter System.Windows.Xps.Serialization.TypeCacheItem::get_TypeConverter()
0x30c39  stloc.s  0xD
0x30c3b  ldloc.s  0x11
0x30c3d  ldloc.s  0xA
0x30c3f  ldloc.s  0xB
0x30c41  ldloc.s  0xC
0x30c43  ldloc.s  0xD
0x30c45  ldloc.s  0xE
0x30c47  ldloc.s  0xF
0x30c49  newobj   instance void System.Windows.Xps.Serialization.TypeDependencyPropertyCache::.ctor(class [mscorlib]System.Reflection.MemberInfo memberInfo, object dependencyProperty, valuetype [System]System.ComponentModel.DesignerSerializationVisibility visibility, class [mscorlib]System.Type serializerTypeForProperty, class [System]System.ComponentModel.TypeConverter typeConverterForProperty, class [System]System.ComponentModel.DefaultValueAttribute defaultValueAttr, class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute designerSerializationFlagsAttr)
0x30c4e  stloc.s  0x17
0x30c50  ldloc.s  8
0x30c52  ldloc.s  7
0x30c54  dup
0x30c55  ldc.i4.1
0x30c56  add
0x30c57  stloc.s  7
0x30c59  ldloc.s  0x17
0x30c5b  stelem.ref
0x30c5c  ldloc.s  9
0x30c5e  ldc.i4.1
0x30c5f  add
0x30c60  stloc.s  9
0x30c62  ldloc.s  9
0x30c64  ldloc.3
0x30c65  ldfld    int32 System.Windows.Xps.Serialization.DependencyPropertyList::Count
0x30c6a  blt      loc_30AD4
0x30c6f  ldloc.s  7
0x30c71  ldc.i4.0
0x30c72  ble.s    loc_30CAE
0x30c74  ldloc.s  7
0x30c76  newarr   System.Windows.Xps.Serialization.TypeDependencyPropertyCache
0x30c7b  stloc.s  0x18
0x30c7d  ldc.i4.0
0x30c7e  stloc.s  0x19
0x30c80  br.s     loc_30C92
0x30c82  ldloc.s  0x18
0x30c84  ldloc.s  0x19
0x30c86  ldloc.s  8
0x30c88  ldloc.s  0x19
0x30c8a  ldelem.ref
0x30c8b  stelem.ref
0x30c8c  ldloc.s  0x19
0x30c8e  ldc.i4.1
0x30c8f  add
0x30c90  stloc.s  0x19
0x30c92  ldloc.s  0x19
0x30c94  ldloc.s  7
0x30c96  blt.s    loc_30C82
0x30c98  ldloc.0
0x30c99  ldloc.s  0x18
0x30c9b  newobj   instance void System.Windows.Xps.Serialization.TypeDependencyPropertiesCacheItem::.ctor(class [mscorlib]System.Type type, class System.Windows.Xps.Serialization.TypeDependencyPropertyCache[] properties)
0x30ca0  stloc.1
0x30ca1  ldarg.0
0x30ca2  ldfld    class [mscorlib]System.Collections.IDictionary System.Windows.Xps.Serialization.SerializersCacheManager::_typesDependencyPropertiesCacheTable
0x30ca7  ldloc.0
0x30ca8  ldloc.1
0x30ca9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x30cae  ldloc.1
0x30caf  ret
```
