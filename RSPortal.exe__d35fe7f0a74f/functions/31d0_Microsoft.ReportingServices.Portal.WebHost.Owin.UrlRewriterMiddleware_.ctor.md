# Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRewriterMiddleware::.ctor

- ea: `0x31d0`
- end: `0x31e8`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRewriterMiddleware::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x31d0`

## pseudocode

```c

```

## disassembly

```asm
0x31d0  ldarg.0
0x31d1  ldarg.1
0x31d2  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x31d7  ldarg.2
0x31d8  brtrue.s loc_31E0
0x31da  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor()
0x31df  throw
0x31e0  ldarg.0
0x31e1  ldarg.2
0x31e2  stfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRewritingRule Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRewriterMiddleware::_rewritingRules
0x31e7  ret
```
