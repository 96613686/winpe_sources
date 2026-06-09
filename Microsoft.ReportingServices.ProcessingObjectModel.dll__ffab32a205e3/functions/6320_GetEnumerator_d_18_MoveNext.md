# <GetEnumerator>d__18::MoveNext

- ea: `0x6320`
- end: `0x6390`
- name: `<GetEnumerator>d__18::MoveNext`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x6320`

## pseudocode

```c

```

## disassembly

```asm
0x6320  ldarg.0
0x6321  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x6326  stloc.0
0x6327  ldarg.0
0x6328  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<var<u1>> class <GetEnumerator>d__18<var<u1>>::<>4__this
0x632d  stloc.1
0x632e  ldloc.0
0x632f  brfalse.s loc_6337
0x6331  ldloc.0
0x6332  ldc.i4.1
0x6333  beq.s    loc_6367
0x6335  ldc.i4.0
0x6336  ret
0x6337  ldarg.0
0x6338  ldc.i4.m1
0x6339  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x633e  ldarg.0
0x633f  ldc.i4.0
0x6340  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6345  br.s     loc_637E
0x6347  ldarg.0
0x6348  ldloc.1
0x6349  ldfld    var<u1>[] class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x634e  ldarg.0
0x634f  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6354  ldelem   var<u1>
0x6359  stfld    var<u1> class <GetEnumerator>d__18<var<u1>>::<>2__current
0x635e  ldarg.0
0x635f  ldc.i4.1
0x6360  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x6365  ldc.i4.1
0x6366  ret
0x6367  ldarg.0
0x6368  ldc.i4.m1
0x6369  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x636e  ldarg.0
0x636f  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6374  ldc.i4.1
0x6375  add
0x6376  stloc.2
0x6377  ldarg.0
0x6378  ldloc.2
0x6379  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x637e  ldarg.0
0x637f  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x6384  ldloc.1
0x6385  ldfld    var<u1>[] class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x638a  ldlen
0x638b  conv.i4
0x638c  blt.s    loc_6347
0x638e  ldc.i4.0
0x638f  ret
```
