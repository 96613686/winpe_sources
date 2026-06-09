# System.Windows.Xps.Serialization.SerializablePropertyContext::.ctor_0

- ea: `0x35f70`
- end: `0x35fa8`
- name: `System.Windows.Xps.Serialization.SerializablePropertyContext::.ctor_0`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x35e00`
- `0x361f0`

## callees

- `0x33e90`
- `0x35f70`

## string_xrefs

- `0x35f87`: `propertyCache`

## pseudocode

```c

```

## disassembly

```asm
0x35f70  ldarg.0
0x35f71  call     instance void System.Windows.Xps.Serialization.BasicContext::.ctor()
0x35f76  ldarg.1
0x35f77  brtrue.s loc_35F84
0x35f79  ldstr    aTarget// "target"
0x35f7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35f83  throw
0x35f84  ldarg.2
0x35f85  brtrue.s loc_35F92
0x35f87  ldstr    aPropertycache// "propertyCache"
0x35f8c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35f91  throw
0x35f92  ldarg.0
0x35f93  ldarg.1
0x35f94  stfld    object System.Windows.Xps.Serialization.SerializablePropertyContext::_targetObject
0x35f99  ldarg.0
0x35f9a  ldarg.2
0x35f9b  stfld    class System.Windows.Xps.Serialization.TypePropertyCache System.Windows.Xps.Serialization.SerializablePropertyContext::_propertyInfo
0x35fa0  ldarg.0
0x35fa1  ldc.i4.0
0x35fa2  stfld    bool System.Windows.Xps.Serialization.SerializablePropertyContext::_isComplex
0x35fa7  ret
```
