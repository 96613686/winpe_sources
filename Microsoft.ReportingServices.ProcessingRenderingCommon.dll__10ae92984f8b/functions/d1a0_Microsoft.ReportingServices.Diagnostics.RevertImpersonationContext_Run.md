# Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run

- ea: `0xd1a0`
- end: `0xd1c5`
- name: `Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run`
- size: `37`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3590`
- `0x6ab0`
- `0x7530`
- `0x12450`
- `0x16b80`
- `0x16c20`
- `0x17160`
- `0x17470`

## callees

- `0x15d80`

## pseudocode

```c

```

## disassembly

```asm
0xd1a0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0xd1a5  stloc.0
0xd1a6  ldloc.0
0xd1a7  ldarg.0
0xd1a8  stfld    class Microsoft.ReportingServices.Diagnostics.ContextBody <>c__DisplayClass1_0::callback
0xd1ad  call     class [mscorlib]System.Security.SecurityContext [mscorlib]System.Security.SecurityContext::Capture()
0xd1b2  ldloc.0
0xd1b3  ldftn    instance void <>c__DisplayClass1_0::<Run>b__0(object state)
0xd1b9  newobj   instance void [mscorlib]System.Threading.ContextCallback::.ctor(object, native int)
0xd1be  ldnull
0xd1bf  call     void [mscorlib]System.Security.SecurityContext::Run(class [mscorlib]System.Security.SecurityContext, class [mscorlib]System.Threading.ContextCallback, object)
0xd1c4  ret
```
