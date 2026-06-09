# System.Windows.Xps.Serialization.XpsTokenContext::.ctor

- ea: `0x2b880`
- end: `0x2b8d3`
- name: `System.Windows.Xps.Serialization.XpsTokenContext::.ctor`
- size: `83`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x28520`
- `0x2b400`
- `0x2b790`
- `0x2c420`
- `0x2c800`
- `0x2d760`
- `0x2d9e0`

## callees

- `0x2b880`
- `0x36070`
- `0x36080`
- `0x361a0`
- `0x36330`

## pseudocode

```c

```

## disassembly

```asm
0x2b880  ldarg.0
0x2b881  call     instance void [mscorlib]System.Object::.ctor()
0x2b886  ldarg.0
0x2b887  ldarg.1
0x2b888  stfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.XpsTokenContext::serializationManager
0x2b88d  ldarg.0
0x2b88e  ldarg.2
0x2b88f  callvirt instance object System.Windows.Xps.Serialization.SerializablePropertyContext::get_TargetObject()
0x2b894  stfld    object System.Windows.Xps.Serialization.XpsTokenContext::targetObject
0x2b899  ldarg.0
0x2b89a  ldarg.2
0x2b89b  callvirt instance object System.Windows.Xps.Serialization.SerializablePropertyContext::get_Value()
0x2b8a0  stfld    object System.Windows.Xps.Serialization.XpsTokenContext::objectValue
0x2b8a5  ldarg.0
0x2b8a6  ldarg.2
0x2b8a7  callvirt instance class [mscorlib]System.Reflection.PropertyInfo System.Windows.Xps.Serialization.SerializablePropertyContext::get_PropertyInfo()
0x2b8ac  stfld    class [mscorlib]System.Reflection.PropertyInfo System.Windows.Xps.Serialization.XpsTokenContext::propertyInfo
0x2b8b1  ldarg.0
0x2b8b2  ldarg.2
0x2b8b3  isinst   System.Windows.Xps.Serialization.SerializableDependencyPropertyContext
0x2b8b8  brtrue.s loc_2B8BD
0x2b8ba  ldnull
0x2b8bb  br.s     loc_2B8CD
0x2b8bd  ldarg.2
0x2b8be  castclass System.Windows.Xps.Serialization.SerializableDependencyPropertyContext
0x2b8c3  callvirt instance object System.Windows.Xps.Serialization.SerializableDependencyPropertyContext::get_DependencyProperty()
0x2b8c8  castclass [WindowsBase]System.Windows.DependencyProperty
0x2b8cd  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Xps.Serialization.XpsTokenContext::dependencyProperty
0x2b8d2  ret
```
