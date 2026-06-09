# <System-Collections-IEnumerable-GetEnumerator>d__17::MoveNext

- ea: `0x63f0`
- end: `0x6465`
- name: `<System-Collections-IEnumerable-GetEnumerator>d__17::MoveNext`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x63f0`

## pseudocode

```c

```

## disassembly

```asm
0x63f0  ldarg.0
0x63f1  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x63f6  stloc.0
0x63f7  ldarg.0
0x63f8  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<var<u1>> class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>4__this
0x63fd  stloc.1
0x63fe  ldloc.0
0x63ff  brfalse.s loc_6407
0x6401  ldloc.0
0x6402  ldc.i4.1
0x6403  beq.s    loc_643C
0x6405  ldc.i4.0
0x6406  ret
0x6407  ldarg.0
0x6408  ldc.i4.m1
0x6409  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x640e  ldarg.0
0x640f  ldc.i4.0
0x6410  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6415  br.s     loc_6453
0x6417  ldarg.0
0x6418  ldloc.1
0x6419  ldfld    var<u1>[] class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x641e  ldarg.0
0x641f  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6424  ldelem   var<u1>
0x6429  box      var<u1>
0x642e  stfld    object class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>2__current
0x6433  ldarg.0
0x6434  ldc.i4.1
0x6435  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x643a  ldc.i4.1
0x643b  ret
0x643c  ldarg.0
0x643d  ldc.i4.m1
0x643e  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x6443  ldarg.0
0x6444  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6449  ldc.i4.1
0x644a  add
0x644b  stloc.2
0x644c  ldarg.0
0x644d  ldloc.2
0x644e  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6453  ldarg.0
0x6454  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6459  ldloc.1
0x645a  ldfld    var<u1>[] class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x645f  ldlen
0x6460  conv.i4
0x6461  blt.s    loc_6417
0x6463  ldc.i4.0
0x6464  ret
```
