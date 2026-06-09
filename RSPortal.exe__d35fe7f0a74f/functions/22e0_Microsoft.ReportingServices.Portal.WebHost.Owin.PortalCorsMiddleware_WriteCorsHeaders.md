# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::WriteCorsHeaders

- ea: `0x22e0`
- end: `0x232e`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::WriteCorsHeaders`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21f0`
- `0x2220`

## callees

- `0x22e0`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  ldarg.1
0x22e1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [System.Web.Cors]System.Web.Cors.CorsResult::ToResponseHeaders()
0x22e6  stloc.0
0x22e7  ldloc.0
0x22e8  brtrue.s loc_22EB
0x22ea  ret
0x22eb  ldloc.0
0x22ec  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x22f1  stloc.1
0x22f2  br.s     loc_2319
0x22f4  ldloc.1
0x22f5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x22fa  stloc.2
0x22fb  ldarg.0
0x22fc  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x2301  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Headers()
0x2306  ldloca.s 2
0x2308  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x230d  ldloca.s 2
0x230f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2314  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::Set(string, string)
0x2319  ldloc.1
0x231a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x231f  brtrue.s loc_22F4
0x2321  leave.s  loc_232D
0x2323  ldloc.1
0x2324  brfalse.s loc_232C
0x2326  ldloc.1
0x2327  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x232c  endfinally
0x232d  ret
```
