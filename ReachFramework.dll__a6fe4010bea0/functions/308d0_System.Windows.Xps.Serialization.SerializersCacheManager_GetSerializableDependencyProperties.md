# System.Windows.Xps.Serialization.SerializersCacheManager::GetSerializableDependencyProperties

- ea: `0x308d0`
- end: `0x309b9`
- name: `System.Windows.Xps.Serialization.SerializersCacheManager::GetSerializableDependencyProperties`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x35e90`

## callees

- `0x30610`
- `0x308d0`
- `0x30a40`
- `0x34200`
- `0x34540`
- `0x34560`
- `0x34580`
- `0x345a0`
- `0x345c0`
- `0x34600`
- `0x34610`
- `0x34630`
- `0x346f0`
- `0x347c0`
- `0x347e0`

## pseudocode

```c

```

## disassembly

```asm
0x308d0  ldnull
0x308d1  stloc.0
0x308d2  ldarg.0
0x308d3  ldarg.1
0x308d4  call     instance class System.Windows.Xps.Serialization.TypeDependencyPropertiesCacheItem System.Windows.Xps.Serialization.SerializersCacheManager::GetTypeDependencyPropertiesCacheItem(object serializableObject)
0x308d9  stloc.1
0x308da  ldloc.1
0x308db  brfalse  loc_309B7
0x308e0  ldloc.1
0x308e1  callvirt instance class System.Windows.Xps.Serialization.TypeDependencyPropertyCache[] System.Windows.Xps.Serialization.TypeDependencyPropertiesCacheItem::GetSerializableDependencyProperties()
0x308e6  stloc.2
0x308e7  ldloc.2
0x308e8  ldlen
0x308e9  conv.i4
0x308ea  newarr   [mscorlib]System.Int32
0x308ef  stloc.3
0x308f0  ldc.i4.0
0x308f1  stloc.s  4
0x308f3  ldc.i4.0
0x308f4  stloc.s  5
0x308f6  br.s     loc_30927
0x308f8  ldarg.1
0x308f9  ldloc.2
0x308fa  ldloc.s  5
0x308fc  ldelem.ref
0x308fd  call     bool System.Windows.Xps.Serialization.TypeDependencyPropertyCache::CanSerializeValue(object serializableObject, class System.Windows.Xps.Serialization.TypeDependencyPropertyCache propertyCache)
0x30902  brfalse.s loc_30921
0x30904  ldarg.0
0x30905  ldfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.SerializersCacheManager::_serializationManager
0x3090a  ldarg.1
0x3090b  ldloc.2
0x3090c  ldloc.s  5
0x3090e  ldelem.ref
0x3090f  callvirt instance bool System.Windows.Xps.Serialization.PackageSerializationManager::CanSerializeDependencyProperty(object serializableObject, class System.Windows.Xps.Serialization.TypeDependencyPropertyCache dependencyProperty)
0x30914  brfalse.s loc_30921
0x30916  ldloc.3
0x30917  ldloc.s  4
0x30919  dup
0x3091a  ldc.i4.1
0x3091b  add
0x3091c  stloc.s  4
0x3091e  ldloc.s  5
0x30920  stelem.i4
0x30921  ldloc.s  5
0x30923  ldc.i4.1
0x30924  add
0x30925  stloc.s  5
0x30927  ldloc.s  5
0x30929  ldloc.2
0x3092a  ldlen
0x3092b  conv.i4
0x3092c  blt.s    loc_308F8
0x3092e  ldloc.s  4
0x30930  newarr   System.Windows.Xps.Serialization.TypeDependencyPropertyCache
0x30935  stloc.0
0x30936  ldc.i4.0
0x30937  stloc.s  6
0x30939  br.s     loc_30995
0x3093b  ldloc.2
0x3093c  ldloc.3
0x3093d  ldloc.s  6
0x3093f  ldelem.i4
0x30940  ldelem.ref
0x30941  stloc.s  7
0x30943  ldloc.s  7
0x30945  callvirt instance class [mscorlib]System.Reflection.MemberInfo System.Windows.Xps.Serialization.TypeDependencyPropertyCache::get_MemberInfo()
0x3094a  ldloc.s  7
0x3094c  callvirt instance object System.Windows.Xps.Serialization.TypeDependencyPropertyCache::get_DependencyProperty()
0x30951  ldloc.s  7
0x30953  callvirt instance valuetype [System]System.ComponentModel.DesignerSerializationVisibility System.Windows.Xps.Serialization.TypePropertyCache::get_Visibility()
0x30958  ldloc.s  7
0x3095a  callvirt instance class [mscorlib]System.Type System.Windows.Xps.Serialization.TypePropertyCache::get_SerializerTypeForProperty()
0x3095f  ldloc.s  7
0x30961  callvirt instance class [System]System.ComponentModel.TypeConverter System.Windows.Xps.Serialization.TypePropertyCache::get_TypeConverterForProperty()
0x30966  ldloc.s  7
0x30968  callvirt instance class [System]System.ComponentModel.DefaultValueAttribute System.Windows.Xps.Serialization.TypePropertyCache::get_DefaultValueAttr()
0x3096d  ldloc.s  7
0x3096f  callvirt instance class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute System.Windows.Xps.Serialization.TypePropertyCache::get_DesignerSerializationOptionsAttr()
0x30974  newobj   instance void System.Windows.Xps.Serialization.TypeDependencyPropertyCache::.ctor(class [mscorlib]System.Reflection.MemberInfo memberInfo, object dependencyProperty, valuetype [System]System.ComponentModel.DesignerSerializationVisibility visibility, class [mscorlib]System.Type serializerTypeForProperty, class [System]System.ComponentModel.TypeConverter typeConverterForProperty, class [System]System.ComponentModel.DefaultValueAttribute defaultValueAttr, class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute designerSerializationFlagsAttr)
0x30979  stloc.s  8
0x3097b  ldloc.s  8
0x3097d  ldloc.s  7
0x3097f  callvirt instance object System.Windows.Xps.Serialization.TypePropertyCache::get_PropertyValue()
0x30984  callvirt instance void System.Windows.Xps.Serialization.TypePropertyCache::set_PropertyValue(object value)
0x30989  ldloc.0
0x3098a  ldloc.s  6
0x3098c  ldloc.s  8
0x3098e  stelem.ref
0x3098f  ldloc.s  6
0x30991  ldc.i4.1
0x30992  add
0x30993  stloc.s  6
0x30995  ldloc.s  6
0x30997  ldloc.s  4
0x30999  blt.s    loc_3093B
0x3099b  ldc.i4.0
0x3099c  stloc.s  9
0x3099e  br.s     loc_309B0
0x309a0  ldloc.2
0x309a1  ldloc.s  9
0x309a3  ldelem.ref
0x309a4  ldnull
0x309a5  callvirt instance void System.Windows.Xps.Serialization.TypePropertyCache::set_PropertyValue(object value)
0x309aa  ldloc.s  9
0x309ac  ldc.i4.1
0x309ad  add
0x309ae  stloc.s  9
0x309b0  ldloc.s  9
0x309b2  ldloc.2
0x309b3  ldlen
0x309b4  conv.i4
0x309b5  blt.s    loc_309A0
0x309b7  ldloc.0
0x309b8  ret
```
