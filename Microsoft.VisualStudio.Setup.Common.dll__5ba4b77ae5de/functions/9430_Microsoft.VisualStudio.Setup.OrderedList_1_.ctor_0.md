# Microsoft.VisualStudio.Setup.OrderedList`1::.ctor_0

- ea: `0x9430`
- end: `0x9458`
- name: `Microsoft.VisualStudio.Setup.OrderedList`1::.ctor_0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9430`

## string_xrefs

- `0x943c`: `comparer`

## pseudocode

```c

```

## disassembly

```asm
0x9430  ldarg.0
0x9431  call     instance void [mscorlib]System.Object::.ctor()
0x9436  ldarg.0
0x9437  ldarg.1
0x9438  dup
0x9439  brtrue.s loc_9447
0x943b  pop
0x943c  ldstr    aComparer// "comparer"
0x9441  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9446  throw
0x9447  stfld    class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>> class Microsoft.VisualStudio.Setup.OrderedList`1<var<u1>>::comparer
0x944c  ldarg.0
0x944d  ldsfld   var<u1>[] class Microsoft.VisualStudio.Setup.EmptyArray`1<var<u1>>::Instance
0x9452  stfld    var<u1>[] class Microsoft.VisualStudio.Setup.OrderedList`1<var<u1>>::items
0x9457  ret
```
