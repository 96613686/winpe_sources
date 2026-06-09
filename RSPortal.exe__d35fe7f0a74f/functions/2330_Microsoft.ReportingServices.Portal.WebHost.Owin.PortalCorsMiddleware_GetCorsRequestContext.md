# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::GetCorsRequestContext

- ea: `0x2330`
- end: `0x2406`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::GetCorsRequestContext`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x41f0`

## callees

- `0x2330`

## pseudocode

```c

```

## disassembly

```asm
0x2330  ldarg.0
0x2331  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x2336  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x233b  ldsfld   string [System.Web.Cors]System.Web.Cors.CorsConstants::Origin
0x2340  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection::Get(string)
0x2345  stloc.0
0x2346  ldloc.0
0x2347  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x234c  brfalse.s loc_2350
0x234e  ldnull
0x234f  ret
0x2350  newobj   instance void [System.Web.Cors]System.Web.Cors.CorsRequestContext::.ctor()
0x2355  dup
0x2356  ldarg.0
0x2357  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x235c  callvirt instance class [System]System.Uri [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Uri()
0x2361  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsRequestContext::set_RequestUri(class [System]System.Uri)
0x2366  dup
0x2367  ldarg.0
0x2368  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x236d  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Method()
0x2372  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsRequestContext::set_HttpMethod(string)
0x2377  dup
0x2378  ldarg.0
0x2379  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x237e  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.HostString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Host()
0x2383  stloc.3
0x2384  ldloca.s 3
0x2386  call     instance string [Microsoft.Owin]Microsoft.Owin.HostString::get_Value()
0x238b  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsRequestContext::set_Host(string)
0x2390  dup
0x2391  ldloc.0
0x2392  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsRequestContext::set_Origin(string)
0x2397  dup
0x2398  ldarg.0
0x2399  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x239e  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x23a3  ldsfld   string [System.Web.Cors]System.Web.Cors.CorsConstants::AccessControlRequestMethod
0x23a8  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection::Get(string)
0x23ad  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsRequestContext::set_AccessControlRequestMethod(string)
0x23b2  stloc.1
0x23b3  ldarg.0
0x23b4  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x23b9  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x23be  ldsfld   string [System.Web.Cors]System.Web.Cors.CorsConstants::AccessControlRequestHeaders
0x23c3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::GetCommaSeparatedValues(string)
0x23c8  stloc.2
0x23c9  ldloc.2
0x23ca  brfalse.s loc_2404
0x23cc  ldloc.2
0x23cd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x23d2  stloc.s  4
0x23d4  br.s     loc_23ED
0x23d6  ldloc.s  4
0x23d8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x23dd  stloc.s  5
0x23df  ldloc.1
0x23e0  callvirt instance class [System]System.Collections.Generic.ISet`1<string> [System.Web.Cors]System.Web.Cors.CorsRequestContext::get_AccessControlRequestHeaders()
0x23e5  ldloc.s  5
0x23e7  callvirt instance bool class [System]System.Collections.Generic.ISet`1<string>::Add(var<u1>)
0x23ec  pop
0x23ed  ldloc.s  4
0x23ef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23f4  brtrue.s loc_23D6
0x23f6  leave.s  loc_2404
0x23f8  ldloc.s  4
0x23fa  brfalse.s loc_2403
0x23fc  ldloc.s  4
0x23fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2403  endfinally
0x2404  ldloc.1
0x2405  ret
```
