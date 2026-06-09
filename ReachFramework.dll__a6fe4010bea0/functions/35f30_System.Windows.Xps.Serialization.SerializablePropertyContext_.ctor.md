# System.Windows.Xps.Serialization.SerializablePropertyContext::.ctor

- ea: `0x35f30`
- end: `0x35f6c`
- name: `System.Windows.Xps.Serialization.SerializablePropertyContext::.ctor`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x361e0`

## callees

- `0x33e70`
- `0x35f30`

## string_xrefs

- `0x35f4a`: `propertyCache`

## pseudocode

```c

```

## disassembly

```asm
0x35f30  ldarg.0
0x35f31  ldarg.1
0x35f32  ldarg.2
0x35f33  call     instance void System.Windows.Xps.Serialization.BasicContext::.ctor(string name, string prefix)
0x35f38  ldarg.3
0x35f39  brtrue.s loc_35F46
0x35f3b  ldstr    aTarget// "target"
0x35f40  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35f45  throw
0x35f46  ldarg.s  4
0x35f48  brtrue.s loc_35F55
0x35f4a  ldstr    aPropertycache// "propertyCache"
0x35f4f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35f54  throw
0x35f55  ldarg.0
0x35f56  ldarg.3
0x35f57  stfld    object System.Windows.Xps.Serialization.SerializablePropertyContext::_targetObject
0x35f5c  ldarg.0
0x35f5d  ldarg.s  4
0x35f5f  stfld    class System.Windows.Xps.Serialization.TypePropertyCache System.Windows.Xps.Serialization.SerializablePropertyContext::_propertyInfo
0x35f64  ldarg.0
0x35f65  ldc.i4.0
0x35f66  stfld    bool System.Windows.Xps.Serialization.SerializablePropertyContext::_isComplex
0x35f6b  ret
```
