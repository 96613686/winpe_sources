# System.Printing.IndexedProperties.PrintThreadPriorityProperty::.ctor

- ea: `0x15450`
- end: `0x1547c`
- name: `System.Printing.IndexedProperties.PrintThreadPriorityProperty::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x155b0`

## callees

- `0x14610`
- `0x14670`
- `0x146a0`
- `0x15450`
- `0x154f0`

## pseudocode

```c

```

## disassembly

```asm
0x15450  ldarg.0
0x15451  ldarg.3
0x15452  castclass ThreadPriorityValueChanged
0x15457  stfld    class ThreadPriorityValueChanged System.Printing.IndexedProperties.PrintThreadPriorityProperty::changeHandler
0x1545c  ldarg.0
0x1545d  ldarg.1
0x1545e  call     instance void System.Printing.IndexedProperties.PrintProperty::.ctor(string attributeName)
0x15463  ldarg.0
0x15464  ldarg.2
0x15465  callvirt instance void System.Printing.IndexedProperties.PrintThreadPriorityProperty::set_Value(object objValue)
0x1546a  ldarg.0
0x1546b  ldc.i4.1
0x1546c  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsLinked([hasfieldmarshal] bool setLinked)
0x15471  leave.s  loc_1547B
0x15473  ldarg.0
0x15474  ldc.i4.1
0x15475  call     instance void System.Printing.IndexedProperties.PrintProperty::Dispose([hasfieldmarshal] bool A_0)
0x1547a  endfinally
0x1547b  ret
```
