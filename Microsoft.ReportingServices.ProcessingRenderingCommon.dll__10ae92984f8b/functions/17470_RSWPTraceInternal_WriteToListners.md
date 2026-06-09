# RSWPTraceInternal::WriteToListners

- ea: `0x17470`
- end: `0x174b8`
- name: `RSWPTraceInternal::WriteToListners`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x16a10`
- `0x17260`

## callees

- `0xd150`
- `0xd1a0`
- `0x17470`
- `0x18470`

## pseudocode

```c

```

## disassembly

```asm
0x17470  newobj   instance void <>c__DisplayClass78_0::.ctor()
0x17475  stloc.0
0x17476  ldloc.0
0x17477  ldarg.0
0x17478  stfld    class RSWPTraceInternal <>c__DisplayClass78_0::<>4__this
0x1747d  ldloc.0
0x1747e  ldarg.1
0x1747f  stfld    string <>c__DisplayClass78_0::text
0x17484  ldloc.0
0x17485  ldfld    string <>c__DisplayClass78_0::text
0x1748a  brfalse.s loc_174A6
0x1748c  ldarg.0
0x1748d  ldarg.0
0x1748e  ldfld    int32 RSWPTraceInternal::m_sizeSoFar
0x17493  ldloc.0
0x17494  ldfld    string <>c__DisplayClass78_0::text
0x17499  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1749e  ldc.i4.2
0x1749f  mul
0x174a0  add
0x174a1  stfld    int32 RSWPTraceInternal::m_sizeSoFar
0x174a6  ldloc.0
0x174a7  ldftn    instance void <>c__DisplayClass78_0::<WriteToListners>b__0()
0x174ad  newobj   instance void Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object object, native int method)
0x174b2  call     void Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class Microsoft.ReportingServices.Diagnostics.ContextBody callback)
0x174b7  ret
```
