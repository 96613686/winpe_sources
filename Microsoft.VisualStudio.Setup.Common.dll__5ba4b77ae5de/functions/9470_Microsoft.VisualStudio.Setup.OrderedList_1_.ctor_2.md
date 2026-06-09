# Microsoft.VisualStudio.Setup.OrderedList`1::.ctor_2

- ea: `0x9470`
- end: `0x94a8`
- name: `Microsoft.VisualStudio.Setup.OrderedList`1::.ctor_2`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9470`

## string_xrefs

- `0x948b`: `comparer`

## pseudocode

```c

```

## disassembly

```asm
0x9470  ldarg.0
0x9471  call     instance void [mscorlib]System.Object::.ctor()
0x9476  ldarg.1
0x9477  ldc.i4.0
0x9478  bge.s    loc_9485
0x947a  ldstr    aCapacity// "capacity"
0x947f  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x9484  throw
0x9485  ldarg.0
0x9486  ldarg.2
0x9487  dup
0x9488  brtrue.s loc_9496
0x948a  pop
0x948b  ldstr    aComparer// "comparer"
0x9490  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9495  throw
0x9496  stfld    class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>> class Microsoft.VisualStudio.Setup.OrderedList`1<var<u1>>::comparer
0x949b  ldarg.0
0x949c  ldarg.1
0x949d  newarr   var<u1>
0x94a2  stfld    var<u1>[] class Microsoft.VisualStudio.Setup.OrderedList`1<var<u1>>::items
0x94a7  ret
```
