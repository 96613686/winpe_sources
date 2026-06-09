# Microsoft.ReportingServices.Diagnostics.Sku::IsLocalValue

- ea: `0xc990`
- end: `0xc9e0`
- name: `Microsoft.ReportingServices.Diagnostics.Sku::IsLocalValue`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xda0`
- `0xc990`
- `0x10d10`
- `0x10d30`

## pseudocode

```c

```

## disassembly

```asm
0xc990  newobj   instance void <>c__DisplayClass11_0::.ctor()
0xc995  stloc.0
0xc996  ldloc.0
0xc997  ldarg.0
0xc998  stfld    string <>c__DisplayClass11_0::value
0xc99d  ldloc.0
0xc99e  ldfld    string <>c__DisplayClass11_0::value
0xc9a3  call     bool Microsoft.ReportingServices.Diagnostics.WebUtil::IsWellKnownLocalServer(string server)
0xc9a8  brfalse.s loc_C9AC
0xc9aa  ldc.i4.1
0xc9ab  ret
0xc9ac  nop
0xc9ad  newobj   instance void <>c__DisplayClass11_1::.ctor()
0xc9b2  dup
0xc9b3  ldloc.0
0xc9b4  stfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0xc9b9  dup
0xc9ba  ldc.i4.0
0xc9bb  stfld    bool <>c__DisplayClass11_1::result
0xc9c0  dup
0xc9c1  ldftn    instance void <>c__DisplayClass11_1::<IsLocalValue>b__0()
0xc9c7  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object, native int)
0xc9cc  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody)
0xc9d1  ldfld    bool <>c__DisplayClass11_1::result
0xc9d6  stloc.1
0xc9d7  leave.s  loc_C9DE
0xc9d9  pop
0xc9da  ldc.i4.0
0xc9db  stloc.1
0xc9dc  leave.s  loc_C9DE
0xc9de  ldloc.1
0xc9df  ret
```
