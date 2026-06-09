# Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::IsRedirectNeeded

- ea: `0x1c20`
- end: `0x1c45`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::IsRedirectNeeded`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x41b0`

## pseudocode

```c

```

## disassembly

```asm
0x1c20  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x1c25  stloc.0
0x1c26  ldloc.0
0x1c27  ldarg.1
0x1c28  stfld    class [System]System.Uri <>c__DisplayClass3_0::uri
0x1c2d  ldarg.0
0x1c2e  ldfld    string[] Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::KnownAsmxFilePaths
0x1c33  ldloc.0
0x1c34  ldftn    instance bool <>c__DisplayClass3_0::<IsRedirectNeeded>b__0(string p)
0x1c3a  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x1c3f  call     T0x2B000006
0x1c44  ret
```
