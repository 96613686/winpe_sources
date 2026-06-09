# Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::.ctor

- ea: `0x32e0`
- end: `0x32f8`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x32e0`

## pseudocode

```c

```

## disassembly

```asm
0x32e0  ldarg.0
0x32e1  ldarg.1
0x32e2  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x32e7  ldarg.2
0x32e8  brtrue.s loc_32F0
0x32ea  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor()
0x32ef  throw
0x32f0  ldarg.0
0x32f1  ldarg.2
0x32f2  stfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::_redirectRule
0x32f7  ret
```
