# System.Windows.Xps.Serialization.TypeDependencyPropertyCache::.ctor

- ea: `0x34630`
- end: `0x3467f`
- name: `System.Windows.Xps.Serialization.TypeDependencyPropertyCache::.ctor`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x308d0`
- `0x30a40`

## callees

- `0x34490`
- `0x34550`
- `0x34570`
- `0x34590`
- `0x345b0`
- `0x345d0`
- `0x345f0`
- `0x34610`
- `0x347d0`
- `0x347f0`

## pseudocode

```c

```

## disassembly

```asm
0x34630  ldarg.0
0x34631  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::.ctor()
0x34636  ldarg.0
0x34637  ldarg.1
0x34638  call     instance void System.Windows.Xps.Serialization.TypeDependencyPropertyCache::set_MemberInfo(class [mscorlib]System.Reflection.MemberInfo value)
0x3463d  ldarg.0
0x3463e  ldarg.2
0x3463f  call     instance void System.Windows.Xps.Serialization.TypeDependencyPropertyCache::set_DependencyProperty(object value)
0x34644  ldarg.0
0x34645  ldarg.1
0x34646  isinst   [mscorlib]System.Reflection.PropertyInfo
0x3464b  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_PropertyInfo(class [mscorlib]System.Reflection.PropertyInfo value)
0x34650  ldarg.0
0x34651  ldarg.3
0x34652  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_Visibility(valuetype [System]System.ComponentModel.DesignerSerializationVisibility value)
0x34657  ldarg.0
0x34658  ldarg.s  4
0x3465a  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_SerializerTypeForProperty(class [mscorlib]System.Type value)
0x3465f  ldarg.0
0x34660  ldarg.s  5
0x34662  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_TypeConverterForProperty(class [System]System.ComponentModel.TypeConverter value)
0x34667  ldarg.0
0x34668  ldarg.s  6
0x3466a  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_DefaultValueAttr(class [System]System.ComponentModel.DefaultValueAttribute value)
0x3466f  ldarg.0
0x34670  ldarg.s  7
0x34672  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_DesignerSerializationOptionsAttr(class [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute value)
0x34677  ldarg.0
0x34678  ldnull
0x34679  call     instance void System.Windows.Xps.Serialization.TypePropertyCache::set_PropertyValue(object value)
0x3467e  ret
```
