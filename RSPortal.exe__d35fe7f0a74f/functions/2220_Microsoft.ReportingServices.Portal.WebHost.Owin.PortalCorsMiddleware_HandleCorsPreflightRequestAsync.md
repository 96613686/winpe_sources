# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::HandleCorsPreflightRequestAsync

- ea: `0x2220`
- end: `0x22bc`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::HandleCorsPreflightRequestAsync`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x41f0`

## callees

- `0x2220`
- `0x22c0`
- `0x22e0`

## pseudocode

```c

```

## disassembly

```asm
0x2220  ldnull
0x2221  stloc.0
0x2222  ldarg.3
0x2223  callvirt instance string [System.Web.Cors]System.Web.Cors.CorsRequestContext::get_AccessControlRequestMethod()
0x2228  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x222d  brtrue.s loc_2254
0x222f  ldarg.0
0x2230  ldarg.2
0x2231  ldarg.3
0x2232  ldloca.s 0
0x2234  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::TryEvaluateCorsPolicy(class [System.Web.Cors]System.Web.Cors.CorsPolicy policy, class [System.Web.Cors]System.Web.Cors.CorsRequestContext corsRequestContext, [out] class [System.Web.Cors]System.Web.Cors.CorsResult& result)
0x2239  brfalse.s loc_2254
0x223b  ldarg.1
0x223c  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2241  ldc.i4   0xC8
0x2246  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x224b  ldarg.1
0x224c  ldloc.0
0x224d  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::WriteCorsHeaders(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, class [System.Web.Cors]System.Web.Cors.CorsResult result)
0x2252  br.s     loc_22B5
0x2254  ldloc.0
0x2255  brfalse.s loc_22A5
0x2257  ldloc.0
0x2258  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsResult::get_ErrorMessages()
0x225d  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x2262  ldc.i4.0
0x2263  ble.s    loc_22A5
0x2265  ldloc.0
0x2266  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsResult::get_ErrorMessages()
0x226b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x2270  stloc.1
0x2271  br.s     loc_2291
0x2273  ldloc.1
0x2274  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2279  stloc.2
0x227a  ldarg.0
0x227b  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_logger
0x2280  ldc.i4.2
0x2281  ldstr    aCorsPreflightR// "CORS Preflight request failed: {0}"
0x2286  ldloc.2
0x2287  call     string [mscorlib]System.String::Format(string, object)
0x228c  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2291  ldloc.1
0x2292  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2297  brtrue.s loc_2273
0x2299  leave.s  loc_22A5
0x229b  ldloc.1
0x229c  brfalse.s loc_22A4
0x229e  ldloc.1
0x229f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22a4  endfinally
0x22a5  ldarg.1
0x22a6  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x22ab  ldc.i4   0x190
0x22b0  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x22b5  ldc.i4.0
0x22b6  call     T0x2B000008
0x22bb  ret
```
