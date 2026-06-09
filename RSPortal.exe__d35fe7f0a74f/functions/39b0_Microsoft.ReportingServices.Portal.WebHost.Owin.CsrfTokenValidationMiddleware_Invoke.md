# Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::Invoke

- ea: `0x39b0`
- end: `0x39d8`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::Invoke`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2b30`
- `0x39b0`

## pseudocode

```c

```

## disassembly

```asm
0x39b0  ldarg.1
0x39b1  ldarg.0
0x39b2  ldftn    instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::TestCsrf(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0x39b8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Owin]Microsoft.Owin.IOwinContext, bool>::.ctor(object, native int)
0x39bd  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.DbExceptionFormatter::DbInvoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, class [mscorlib]System.Func`2<class [Microsoft.Owin]Microsoft.Owin.IOwinContext, bool> dbAction)
0x39c2  brfalse.s loc_39D1
0x39c4  ldarg.0
0x39c5  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x39ca  ldarg.1
0x39cb  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x39d0  ret
0x39d1  ldc.i4.0
0x39d2  call     T0x2B000008
0x39d7  ret
```
