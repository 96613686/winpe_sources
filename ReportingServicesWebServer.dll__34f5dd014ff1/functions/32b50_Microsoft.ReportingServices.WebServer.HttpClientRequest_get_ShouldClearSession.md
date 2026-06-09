# Microsoft.ReportingServices.WebServer.HttpClientRequest::get_ShouldClearSession

- ea: `0x32b50`
- end: `0x32baf`
- name: `Microsoft.ReportingServices.WebServer.HttpClientRequest::get_ShouldClearSession`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x32b50`

## string_xrefs

- `0x32b86`: `Cache-control`
- `0x32b9f`: `NO-CACHE`

## pseudocode

```c

```

## disassembly

```asm
0x32b50  ldarg.0
0x32b51  ldfld    bool Microsoft.ReportingServices.WebServer.HttpClientRequest::m_forceNoDeleteSession
0x32b56  brfalse.s loc_32B5A
0x32b58  ldc.i4.0
0x32b59  ret
0x32b5a  ldarg.0
0x32b5b  call     instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionfulClientRequest::get_ImageName()
0x32b60  brfalse.s loc_32B64
0x32b62  ldc.i4.0
0x32b63  ret
0x32b64  ldarg.0
0x32b65  call     instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SessionfulClientRequest::get_ClearSession()
0x32b6a  brfalse.s loc_32B6E
0x32b6c  ldc.i4.1
0x32b6d  ret
0x32b6e  ldarg.0
0x32b6f  ldfld    bool Microsoft.ReportingServices.WebServer.HttpClientRequest::m_ignoreRefreshHeader
0x32b74  brtrue.s loc_32BAD
0x32b76  ldarg.0
0x32b77  ldfld    class [System.Web]System.Web.HttpContext Microsoft.ReportingServices.WebServer.HttpClientRequest::m_ctx
0x32b7c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x32b81  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x32b86  ldstr    aCacheControl// "Cache-control"
0x32b8b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x32b90  stloc.0
0x32b91  ldloc.0
0x32b92  brfalse.s loc_32BAD
0x32b94  ldloc.0
0x32b95  castclass [mscorlib]System.String
0x32b9a  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x32b9f  ldstr    aNoCache// "NO-CACHE"
0x32ba4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32ba9  brfalse.s loc_32BAD
0x32bab  ldc.i4.1
0x32bac  ret
0x32bad  ldc.i4.0
0x32bae  ret
```
