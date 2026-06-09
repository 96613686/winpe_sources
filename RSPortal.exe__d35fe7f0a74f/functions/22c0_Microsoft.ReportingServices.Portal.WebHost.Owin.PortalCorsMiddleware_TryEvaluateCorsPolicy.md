# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::TryEvaluateCorsPolicy

- ea: `0x22c0`
- end: `0x22dd`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::TryEvaluateCorsPolicy`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21f0`
- `0x2220`

## callees

- `0x22c0`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldarg.3
0x22c1  ldarg.0
0x22c2  ldfld    class [System.Web.Cors]System.Web.Cors.ICorsEngine Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_corsEngine
0x22c7  ldarg.2
0x22c8  ldarg.1
0x22c9  callvirt instance class [System.Web.Cors]System.Web.Cors.CorsResult [System.Web.Cors]System.Web.Cors.ICorsEngine::EvaluatePolicy(class [System.Web.Cors]System.Web.Cors.CorsRequestContext, class [System.Web.Cors]System.Web.Cors.CorsPolicy)
0x22ce  stind.ref
0x22cf  ldarg.3
0x22d0  ldind.ref
0x22d1  brfalse.s loc_22DB
0x22d3  ldarg.3
0x22d4  ldind.ref
0x22d5  callvirt instance bool [System.Web.Cors]System.Web.Cors.CorsResult::get_IsValid()
0x22da  ret
0x22db  ldc.i4.0
0x22dc  ret
```
