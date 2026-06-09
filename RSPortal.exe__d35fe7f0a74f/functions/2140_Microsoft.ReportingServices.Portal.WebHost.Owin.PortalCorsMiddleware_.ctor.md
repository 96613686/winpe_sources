# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::.ctor

- ea: `0x2140`
- end: `0x219b`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::.ctor`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2140`

## pseudocode

```c

```

## disassembly

```asm
0x2140  ldarg.0
0x2141  call     instance void [mscorlib]System.Object::.ctor()
0x2146  ldarg.1
0x2147  brtrue.s loc_2154
0x2149  ldstr    aNext// "next"
0x214e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2153  throw
0x2154  ldarg.2
0x2155  brtrue.s loc_2162
0x2157  ldstr    aOptions// "options"
0x215c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2161  throw
0x2162  ldarg.0
0x2163  ldarg.1
0x2164  stfld    class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Threading.Tasks.Task> Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_next
0x2169  ldarg.0
0x216a  ldarg.2
0x216b  callvirt instance class [Microsoft.Owin.Cors]Microsoft.Owin.Cors.ICorsPolicyProvider [Microsoft.Owin.Cors]Microsoft.Owin.Cors.CorsOptions::get_PolicyProvider()
0x2170  dup
0x2171  brtrue.s loc_2179
0x2173  pop
0x2174  newobj   instance void [Microsoft.Owin.Cors]Microsoft.Owin.Cors.CorsPolicyProvider::.ctor()
0x2179  stfld    class [Microsoft.Owin.Cors]Microsoft.Owin.Cors.ICorsPolicyProvider Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_corsPolicyProvider
0x217e  ldarg.0
0x217f  ldarg.2
0x2180  callvirt instance class [System.Web.Cors]System.Web.Cors.ICorsEngine [Microsoft.Owin.Cors]Microsoft.Owin.Cors.CorsOptions::get_CorsEngine()
0x2185  dup
0x2186  brtrue.s loc_218E
0x2188  pop
0x2189  newobj   instance void [System.Web.Cors]System.Web.Cors.CorsEngine::.ctor()
0x218e  stfld    class [System.Web.Cors]System.Web.Cors.ICorsEngine Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_corsEngine
0x2193  ldarg.0
0x2194  ldarg.3
0x2195  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_logger
0x219a  ret
```
