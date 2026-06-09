# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::HandleCorsRequestAsync

- ea: `0x21f0`
- end: `0x2215`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::HandleCorsRequestAsync`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x41f0`

## callees

- `0x21f0`
- `0x22c0`
- `0x22e0`

## pseudocode

```c

```

## disassembly

```asm
0x21f0  ldarg.0
0x21f1  ldarg.2
0x21f2  ldarg.3
0x21f3  ldloca.s 0
0x21f5  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::TryEvaluateCorsPolicy(class [System.Web.Cors]System.Web.Cors.CorsPolicy policy, class [System.Web.Cors]System.Web.Cors.CorsRequestContext corsRequestContext, [out] class [System.Web.Cors]System.Web.Cors.CorsResult& result)
0x21fa  brfalse.s loc_2203
0x21fc  ldarg.1
0x21fd  ldloc.0
0x21fe  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::WriteCorsHeaders(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, class [System.Web.Cors]System.Web.Cors.CorsResult result)
0x2203  ldarg.0
0x2204  ldfld    class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Threading.Tasks.Task> Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_next
0x2209  ldarg.1
0x220a  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Environment()
0x220f  callvirt instance var<u1> class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Threading.Tasks.Task>::Invoke(void)
0x2214  ret
```
