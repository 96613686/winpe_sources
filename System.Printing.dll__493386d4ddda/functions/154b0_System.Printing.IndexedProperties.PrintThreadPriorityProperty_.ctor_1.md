# System.Printing.IndexedProperties.PrintThreadPriorityProperty::.ctor_1

- ea: `0x154b0`
- end: `0x154d0`
- name: `System.Printing.IndexedProperties.PrintThreadPriorityProperty::.ctor_1`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x155d0`

## callees

- `0x14670`
- `0x146a0`
- `0x154b0`
- `0x154f0`

## pseudocode

```c

```

## disassembly

```asm
0x154b0  ldarg.0
0x154b1  ldnull
0x154b2  stfld    class ThreadPriorityValueChanged System.Printing.IndexedProperties.PrintThreadPriorityProperty::changeHandler
0x154b7  ldarg.0
0x154b8  ldarg.1
0x154b9  call     instance void System.Printing.IndexedProperties.PrintProperty::.ctor(string attributeName)
0x154be  ldarg.0
0x154bf  ldarg.2
0x154c0  callvirt instance void System.Printing.IndexedProperties.PrintThreadPriorityProperty::set_Value(object objValue)
0x154c5  leave.s  loc_154CF
0x154c7  ldarg.0
0x154c8  ldc.i4.1
0x154c9  call     instance void System.Printing.IndexedProperties.PrintProperty::Dispose([hasfieldmarshal] bool A_0)
0x154ce  endfinally
0x154cf  ret
```
