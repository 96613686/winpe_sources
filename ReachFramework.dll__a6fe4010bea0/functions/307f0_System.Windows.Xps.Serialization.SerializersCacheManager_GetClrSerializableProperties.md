# System.Windows.Xps.Serialization.SerializersCacheManager::GetClrSerializableProperties

- ea: `0x307f0`
- end: `0x308ca`
- name: `System.Windows.Xps.Serialization.SerializersCacheManager::GetClrSerializableProperties`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x35e00`

## callees

- `0x30620`
- `0x307f0`
- `0x309c0`
- `0x30d40`
- `0x342b0`
- `0x344f0`
- `0x34540`
- `0x34560`
- `0x34580`
- `0x345a0`
- `0x345c0`
- `0x345e0`
- `0x34600`
- `0x34610`

## pseudocode

```c

```

## disassembly

```asm
0x307f0  ldarg.0
0x307f1  ldarg.1
0x307f2  call     instance class System.Windows.Xps.Serialization.TypeCacheItem System.Windows.Xps.Serialization.SerializersCacheManager::GetTypeCacheItem(object serializableObject)
0x307f7  stloc.0
0x307f8  ldloc.0
0x307f9  ldarg.0
0x307fa  callvirt instance class System.Windows.Xps.Serialization.TypePropertyCache[] System.Windows.Xps.Serialization.TypeCacheItem::GetClrSerializableProperties(class System.Windows.Xps.Serialization.SerializersCacheManager serializersCacheManager)
0x307ff  stloc.1
0x30800  ldloc.1
0x30801  ldlen
0x30802  conv.i4
0x30803  newarr   [mscorlib]System.Int32
0x30808  stloc.2
0x30809  ldc.i4.0
0x3080a  stloc.3
0x3080b  ldc.i4.0
0x3080c  stloc.s  5
0x3080e  br.s     loc_3083E
0x30810  ldarg.0
0x30811  ldarg.1
0x30812  ldloc.1
0x30813  ldloc.s  5
0x30815  ldelem.ref
0x30816  call     instance bool System.Windows.Xps.Serialization.SerializersCacheManager::CanSerializeValue(object serializableObject, class System.Windows.Xps.Serialization.TypePropertyCache propertyCache)
0x3081b  brfalse.s loc_30838
0x3081d  ldarg.0
0x3081e  ldfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.SerializersCacheManager::_serializationManager
0x30823  ldarg.1
0x30824  ldloc.1
0x30825  ldloc.s  5
0x30827  ldelem.ref
0x30828  callvirt instance bool System.Windows.Xps.Serialization.PackageSerializationManager::CanSerializeClrProperty(object serializableObject, class System.Windows.Xps.Serialization.TypePropertyCache property)
0x3082d  brfalse.s loc_30838
0x3082f  ldloc.2
0x30830  ldloc.3
0x30831  dup
0x30832  ldc.i4.1
0x30833  add
0x30834  stloc.3
0x30835  ldloc.s  5
0x30837  stelem.i4
0x30838  ldloc.s  5
0x3083a  ldc.i4.1
0x3083b  add
0x3083c  stloc.s  5
0x3083e  ldloc.s  5
0x30840  ldloc.1
0x30841  ldlen
0x30842  conv.i4
0x30843  blt.s    loc_30810
0x30845  ldloc.3
0x30846  newarr   System.Windows.Xps.Serialization.TypePropertyCache
0x3084b  stloc.s  4
0x3084d  ldc.i4.0
0x3084e  stloc.s  6
0x30850  br.s     loc_308A6
0x30852  ldloc.1
0x30853  ldloc.2
0x30854  ldloc.s  6
0x30856  ldelem.i4
0x30857  ldelem.ref
0x30858  stloc.s  7
0x3085a  ldloc.s  7
0x3085c  callvirt instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.Xps.Serialization.TypePropertyCache::get_PropertyInfo()
0x30861  ldloc.s  7
0x30863  callvirt instance valuetype [System]System.ComponentModel.DesignerSerializationVisibility System.Windows.Xps.Serialization.TypePropertyCache::get_Visibility()
0x30868  ldloc.s  7
0x3086a  callvirt instance class [mscorlib]System.Type System.Windows.Xps.Serialization.TypePropertyCache::get_SerializerTypeForProperty()
0x3086f  ldloc.s  7
0x30871  callvirt instance class [System]System.ComponentModel.TypeConverter System.Windows.Xps.Serialization.TypePropertyCache::get_TypeConverterForProperty()
0x30876  ldloc.s  7
0x30878  callvirt instance class [System]System.ComponentModel.DefaultValueAttribute System.Windows.Xps.Serialization.TypePropertyCache::get_DefaultValueAttr()
0x3087d  ldloc.s  7
0x3087f  callvirt instance class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute System.Windows.Xps.Serialization.TypePropertyCache::get_DesignerSerializationOptionsAttr()
0x30884  newobj   instance void System.Windows.Xps.Serialization.TypePropertyCache::.ctor(class [mscorlib]System.Reflection.PropertyInfo propertyInfo, valuetype [System]System.ComponentModel.DesignerSerializationVisibility visibility, class [mscorlib]System.Type serializerTypeForProperty, class [System]System.ComponentModel.TypeConverter typeConverterForProperty, class [System]System.ComponentModel.DefaultValueAttribute defaultValueAttr, class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute designerSerializationFlagsAttr)
0x30889  stloc.s  8
0x3088b  ldloc.s  8
0x3088d  ldloc.s  7
0x3088f  callvirt instance object System.Windows.Xps.Serialization.TypePropertyCache::get_PropertyValue()
0x30894  callvirt instance void System.Windows.Xps.Serialization.TypePropertyCache::set_PropertyValue(object value)
0x30899  ldloc.s  4
0x3089b  ldloc.s  6
0x3089d  ldloc.s  8
0x3089f  stelem.ref
0x308a0  ldloc.s  6
0x308a2  ldc.i4.1
0x308a3  add
0x308a4  stloc.s  6
0x308a6  ldloc.s  6
0x308a8  ldloc.3
0x308a9  blt.s    loc_30852
0x308ab  ldc.i4.0
0x308ac  stloc.s  9
0x308ae  br.s     loc_308C0
0x308b0  ldloc.1
0x308b1  ldloc.s  9
0x308b3  ldelem.ref
0x308b4  ldnull
0x308b5  callvirt instance void System.Windows.Xps.Serialization.TypePropertyCache::set_PropertyValue(object value)
0x308ba  ldloc.s  9
0x308bc  ldc.i4.1
0x308bd  add
0x308be  stloc.s  9
0x308c0  ldloc.s  9
0x308c2  ldloc.1
0x308c3  ldlen
0x308c4  conv.i4
0x308c5  blt.s    loc_308B0
0x308c7  ldloc.s  4
0x308c9  ret
```
