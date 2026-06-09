# System.Windows.Markup.TypeExtensionConverter::ConvertTo

- ea: `0x1c420`
- end: `0x1c4a6`
- name: `System.Windows.Markup.TypeExtensionConverter::ConvertTo`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x11f50`
- `0x1c2e0`
- `0x1c420`

## string_xrefs

- `0x1c452`: `TypeExtension`

## pseudocode

```c

```

## disassembly

```asm
0x1c420  ldarg.s  4
0x1c422  ldtoken  [System]System.ComponentModel.Design.Serialization.InstanceDescriptor
0x1c427  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c42c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c431  brfalse.s loc_1C49A
0x1c433  ldarg.3
0x1c434  isinst   System.Windows.Markup.TypeExtension
0x1c439  stloc.0
0x1c43a  ldloc.0
0x1c43b  brtrue.s loc_1C463
0x1c43d  ldstr    aMustbeoftype// "MustBeOfType"
0x1c442  ldc.i4.2
0x1c443  newarr   [mscorlib]System.Object
0x1c448  dup
0x1c449  ldc.i4.0
0x1c44a  ldstr    aValue// "value"
0x1c44f  stelem.ref
0x1c450  dup
0x1c451  ldc.i4.1
0x1c452  ldstr    aTypeextension// "TypeExtension"
0x1c457  stelem.ref
0x1c458  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c45d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1c462  throw
0x1c463  ldtoken  System.Windows.Markup.TypeExtension
0x1c468  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c46d  ldc.i4.1
0x1c46e  newarr   [mscorlib]System.Type
0x1c473  dup
0x1c474  ldc.i4.0
0x1c475  ldtoken  [mscorlib]System.Type
0x1c47a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c47f  stelem.ref
0x1c480  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x1c485  ldc.i4.1
0x1c486  newarr   [mscorlib]System.Object
0x1c48b  dup
0x1c48c  ldc.i4.0
0x1c48d  ldloc.0
0x1c48e  callvirt instance class [mscorlib]System.Type System.Windows.Markup.TypeExtension::get_Type()
0x1c493  stelem.ref
0x1c494  newobj   instance void [System]System.ComponentModel.Design.Serialization.InstanceDescriptor::.ctor(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Collections.ICollection)
0x1c499  ret
0x1c49a  ldarg.0
0x1c49b  ldarg.1
0x1c49c  ldarg.2
0x1c49d  ldarg.3
0x1c49e  ldarg.s  4
0x1c4a0  call     instance object [System]System.ComponentModel.TypeConverter::ConvertTo(class [System]System.ComponentModel.ITypeDescriptorContext, class [mscorlib]System.Globalization.CultureInfo, object, class [mscorlib]System.Type)
0x1c4a5  ret
```
