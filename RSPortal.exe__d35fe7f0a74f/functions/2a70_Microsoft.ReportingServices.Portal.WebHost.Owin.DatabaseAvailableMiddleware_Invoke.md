# Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::Invoke

- ea: `0x2a70`
- end: `0x2a98`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::Invoke`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2a70`
- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2a70  ldarg.1
0x2a71  ldarg.0
0x2a72  ldftn    instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::TestAvailable(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0x2a78  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Owin]Microsoft.Owin.IOwinContext, bool>::.ctor(object, native int)
0x2a7d  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::DbInvoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, class [mscorlib]System.Func`2<class [Microsoft.Owin]Microsoft.Owin.IOwinContext, bool> dbAction)
0x2a82  brfalse.s loc_2A91
0x2a84  ldarg.0
0x2a85  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x2a8a  ldarg.1
0x2a8b  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x2a90  ret
0x2a91  ldc.i4.0
0x2a92  call     T0x2B000008
0x2a97  ret
```
