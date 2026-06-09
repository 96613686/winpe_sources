# System.Printing.IndexedProperties.PrintThreadPriorityProperty::.ctor_0

- ea: `0x15480`
- end: `0x154a5`
- name: `System.Printing.IndexedProperties.PrintThreadPriorityProperty::.ctor_0`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x155c0`

## callees

- `0x14610`
- `0x14670`
- `0x146a0`
- `0x15480`

## pseudocode

```c

```

## disassembly

```asm
0x15480  ldarg.0
0x15481  ldarg.2
0x15482  castclass ThreadPriorityValueChanged
0x15487  stfld    class ThreadPriorityValueChanged System.Printing.IndexedProperties.PrintThreadPriorityProperty::changeHandler
0x1548c  ldarg.0
0x1548d  ldarg.1
0x1548e  call     instance void System.Printing.IndexedProperties.PrintProperty::.ctor(string attributeName)
0x15493  ldarg.0
0x15494  ldc.i4.1
0x15495  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsLinked([hasfieldmarshal] bool setLinked)
0x1549a  leave.s  loc_154A4
0x1549c  ldarg.0
0x1549d  ldc.i4.1
0x1549e  call     instance void System.Printing.IndexedProperties.PrintProperty::Dispose([hasfieldmarshal] bool A_0)
0x154a3  endfinally
0x154a4  ret
```
