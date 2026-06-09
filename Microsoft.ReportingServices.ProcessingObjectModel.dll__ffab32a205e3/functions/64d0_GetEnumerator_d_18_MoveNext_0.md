# <GetEnumerator>d__18::MoveNext_0

- ea: `0x64d0`
- end: `0x6540`
- name: `<GetEnumerator>d__18::MoveNext_0`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x64d0`

## pseudocode

```c

```

## disassembly

```asm
0x64d0  ldarg.0
0x64d1  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x64d6  stloc.0
0x64d7  ldarg.0
0x64d8  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteArrayWrapper`1<var<u1>> class <GetEnumerator>d__18<var<u1>>::<>4__this
0x64dd  stloc.1
0x64de  ldloc.0
0x64df  brfalse.s loc_64E7
0x64e1  ldloc.0
0x64e2  ldc.i4.1
0x64e3  beq.s    loc_6517
0x64e5  ldc.i4.0
0x64e6  ret
0x64e7  ldarg.0
0x64e8  ldc.i4.m1
0x64e9  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x64ee  ldarg.0
0x64ef  ldc.i4.0
0x64f0  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x64f5  br.s     loc_652E
0x64f7  ldarg.0
0x64f8  ldloc.1
0x64f9  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x64fe  ldarg.0
0x64ff  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6504  ldelem   var<u1>
0x6509  stfld    var<u1> class <GetEnumerator>d__18<var<u1>>::<>2__current
0x650e  ldarg.0
0x650f  ldc.i4.1
0x6510  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x6515  ldc.i4.1
0x6516  ret
0x6517  ldarg.0
0x6518  ldc.i4.m1
0x6519  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x651e  ldarg.0
0x651f  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6524  ldc.i4.1
0x6525  add
0x6526  stloc.2
0x6527  ldarg.0
0x6528  ldloc.2
0x6529  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x652e  ldarg.0
0x652f  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6534  ldloc.1
0x6535  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x653a  ldlen
0x653b  conv.i4
0x653c  blt.s    loc_64F7
0x653e  ldc.i4.0
0x653f  ret
```
