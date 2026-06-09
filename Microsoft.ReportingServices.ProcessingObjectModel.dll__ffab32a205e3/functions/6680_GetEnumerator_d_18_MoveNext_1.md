# <GetEnumerator>d__18::MoveNext_1

- ea: `0x6680`
- end: `0x66f5`
- name: `<GetEnumerator>d__18::MoveNext_1`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x6680`

## pseudocode

```c

```

## disassembly

```asm
0x6680  ldarg.0
0x6681  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x6686  stloc.0
0x6687  ldarg.0
0x6688  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteMemberArrayWrapper`1<var<u1>> class <GetEnumerator>d__18<var<u1>>::<>4__this
0x668d  stloc.1
0x668e  ldloc.0
0x668f  brfalse.s loc_6697
0x6691  ldloc.0
0x6692  ldc.i4.1
0x6693  beq.s    loc_66CC
0x6695  ldc.i4.0
0x6696  ret
0x6697  ldarg.0
0x6698  ldc.i4.m1
0x6699  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x669e  ldarg.0
0x669f  ldc.i4.0
0x66a0  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x66a5  br.s     loc_66E3
0x66a7  ldarg.0
0x66a8  ldloc.1
0x66a9  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteMemberArrayWrapper`1<var<u1>>::m_array
0x66ae  ldarg.0
0x66af  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x66b4  ldelem   var<u1>
0x66b9  box      var<u1>
0x66be  stfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.IMemberNode class <GetEnumerator>d__18<var<u1>>::<>2__current
0x66c3  ldarg.0
0x66c4  ldc.i4.1
0x66c5  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x66ca  ldc.i4.1
0x66cb  ret
0x66cc  ldarg.0
0x66cd  ldc.i4.m1
0x66ce  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<>1__state
0x66d3  ldarg.0
0x66d4  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x66d9  ldc.i4.1
0x66da  add
0x66db  stloc.2
0x66dc  ldarg.0
0x66dd  ldloc.2
0x66de  stfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x66e3  ldarg.0
0x66e4  ldfld    int32 class <GetEnumerator>d__18<var<u1>>::<i>5__2
0x66e9  ldloc.1
0x66ea  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteMemberArrayWrapper`1<var<u1>>::m_array
0x66ef  ldlen
0x66f0  conv.i4
0x66f1  blt.s    loc_66A7
0x66f3  ldc.i4.0
0x66f4  ret
```
