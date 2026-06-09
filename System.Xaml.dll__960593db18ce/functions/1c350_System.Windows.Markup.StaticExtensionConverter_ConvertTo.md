# System.Windows.Markup.StaticExtensionConverter::ConvertTo

- ea: `0x1c350`
- end: `0x1c3d6`
- name: `System.Windows.Markup.StaticExtensionConverter::ConvertTo`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x11f50`
- `0x1c110`
- `0x1c350`

## string_xrefs

- `0x1c382`: `StaticExtension`

## pseudocode

```c

```

## disassembly

```asm
0x1c350  ldarg.s  4
0x1c352  ldtoken  [System]System.ComponentModel.Design.Serialization.InstanceDescriptor
0x1c357  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c35c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c361  brfalse.s loc_1C3CA
0x1c363  ldarg.3
0x1c364  isinst   System.Windows.Markup.StaticExtension
0x1c369  stloc.0
0x1c36a  ldloc.0
0x1c36b  brtrue.s loc_1C393
0x1c36d  ldstr    aMustbeoftype// "MustBeOfType"
0x1c372  ldc.i4.2
0x1c373  newarr   [mscorlib]System.Object
0x1c378  dup
0x1c379  ldc.i4.0
0x1c37a  ldstr    aValue// "value"
0x1c37f  stelem.ref
0x1c380  dup
0x1c381  ldc.i4.1
0x1c382  ldstr    aStaticextensio// "StaticExtension"
0x1c387  stelem.ref
0x1c388  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c38d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1c392  throw
0x1c393  ldtoken  System.Windows.Markup.StaticExtension
0x1c398  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c39d  ldc.i4.1
0x1c39e  newarr   [mscorlib]System.Type
0x1c3a3  dup
0x1c3a4  ldc.i4.0
0x1c3a5  ldtoken  [mscorlib]System.String
0x1c3aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c3af  stelem.ref
0x1c3b0  call     instance class [mscorlib]System.Reflection.ConstructorInfo [mscorlib]System.Type::GetConstructor(class [mscorlib]System.Type[])
0x1c3b5  ldc.i4.1
0x1c3b6  newarr   [mscorlib]System.Object
0x1c3bb  dup
0x1c3bc  ldc.i4.0
0x1c3bd  ldloc.0
0x1c3be  callvirt instance string System.Windows.Markup.StaticExtension::get_Member()
0x1c3c3  stelem.ref
0x1c3c4  newobj   instance void [System]System.ComponentModel.Design.Serialization.InstanceDescriptor::.ctor(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Collections.ICollection)
0x1c3c9  ret
0x1c3ca  ldarg.0
0x1c3cb  ldarg.1
0x1c3cc  ldarg.2
0x1c3cd  ldarg.3
0x1c3ce  ldarg.s  4
0x1c3d0  call     instance object [System]System.ComponentModel.TypeConverter::ConvertTo(class [System]System.ComponentModel.ITypeDescriptorContext, class [mscorlib]System.Globalization.CultureInfo, object, class [mscorlib]System.Type)
0x1c3d5  ret
```
