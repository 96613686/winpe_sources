# <System-Collections-IEnumerable-GetEnumerator>d__17::MoveNext_1

- ea: `0x6760`
- end: `0x67d5`
- name: `<System-Collections-IEnumerable-GetEnumerator>d__17::MoveNext_1`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x6760`

## pseudocode

```c

```

## disassembly

```asm
0x6760  ldarg.0
0x6761  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x6766  stloc.0
0x6767  ldarg.0
0x6768  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteMemberArrayWrapper`1<var<u1>> class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>4__this
0x676d  stloc.1
0x676e  ldloc.0
0x676f  brfalse.s loc_6777
0x6771  ldloc.0
0x6772  ldc.i4.1
0x6773  beq.s    loc_67AC
0x6775  ldc.i4.0
0x6776  ret
0x6777  ldarg.0
0x6778  ldc.i4.m1
0x6779  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x677e  ldarg.0
0x677f  ldc.i4.0
0x6780  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6785  br.s     loc_67C3
0x6787  ldarg.0
0x6788  ldloc.1
0x6789  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteMemberArrayWrapper`1<var<u1>>::m_array
0x678e  ldarg.0
0x678f  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6794  ldelem   var<u1>
0x6799  box      var<u1>
0x679e  stfld    object class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>2__current
0x67a3  ldarg.0
0x67a4  ldc.i4.1
0x67a5  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x67aa  ldc.i4.1
0x67ab  ret
0x67ac  ldarg.0
0x67ad  ldc.i4.m1
0x67ae  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x67b3  ldarg.0
0x67b4  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x67b9  ldc.i4.1
0x67ba  add
0x67bb  stloc.2
0x67bc  ldarg.0
0x67bd  ldloc.2
0x67be  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x67c3  ldarg.0
0x67c4  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x67c9  ldloc.1
0x67ca  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteMemberArrayWrapper`1<var<u1>>::m_array
0x67cf  ldlen
0x67d0  conv.i4
0x67d1  blt.s    loc_6787
0x67d3  ldc.i4.0
0x67d4  ret
```
