# <System-Collections-IEnumerable-GetEnumerator>d__17::MoveNext_0

- ea: `0x65a0`
- end: `0x6615`
- name: `<System-Collections-IEnumerable-GetEnumerator>d__17::MoveNext_0`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x65a0`

## pseudocode

```c

```

## disassembly

```asm
0x65a0  ldarg.0
0x65a1  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x65a6  stloc.0
0x65a7  ldarg.0
0x65a8  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteArrayWrapper`1<var<u1>> class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>4__this
0x65ad  stloc.1
0x65ae  ldloc.0
0x65af  brfalse.s loc_65B7
0x65b1  ldloc.0
0x65b2  ldc.i4.1
0x65b3  beq.s    loc_65EC
0x65b5  ldc.i4.0
0x65b6  ret
0x65b7  ldarg.0
0x65b8  ldc.i4.m1
0x65b9  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x65be  ldarg.0
0x65bf  ldc.i4.0
0x65c0  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x65c5  br.s     loc_6603
0x65c7  ldarg.0
0x65c8  ldloc.1
0x65c9  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x65ce  ldarg.0
0x65cf  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x65d4  ldelem   var<u1>
0x65d9  box      var<u1>
0x65de  stfld    object class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>2__current
0x65e3  ldarg.0
0x65e4  ldc.i4.1
0x65e5  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x65ea  ldc.i4.1
0x65eb  ret
0x65ec  ldarg.0
0x65ed  ldc.i4.m1
0x65ee  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<>1__state
0x65f3  ldarg.0
0x65f4  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x65f9  ldc.i4.1
0x65fa  add
0x65fb  stloc.2
0x65fc  ldarg.0
0x65fd  ldloc.2
0x65fe  stfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6603  ldarg.0
0x6604  ldfld    int32 class <System-Collections-IEnumerable-GetEnumerator>d__17<var<u1>>::<i>5__2
0x6609  ldloc.1
0x660a  ldfld    var<u1>[] class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.RemoteArrayWrapper`1<var<u1>>::m_array
0x660f  ldlen
0x6610  conv.i4
0x6611  blt.s    loc_65C7
0x6613  ldc.i4.0
0x6614  ret
```
