# Microsoft.BIServer.HostingEnvironment.Request.RequestContext::PassOnCurrentRequestContext

- ea: `0x3260`
- end: `0x3296`
- name: `Microsoft.BIServer.HostingEnvironment.Request.RequestContext::PassOnCurrentRequestContext`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x68c0`
- `0x6c10`

## callees

- `0x3140`
- `0x3160`
- `0x3250`
- `0x3260`

## pseudocode

```c

```

## disassembly

```asm
0x3260  call     class Microsoft.BIServer.HostingEnvironment.Request.RequestContext Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext()
0x3265  stloc.0
0x3266  ldloc.0
0x3267  brfalse.s loc_3295
0x3269  ldarg.0
0x326a  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpClient::get_DefaultRequestHeaders()
0x326f  ldstr    aRequestid// "RequestId"
0x3274  ldloc.0
0x3275  callvirt instance string Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_RequestID()
0x327a  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x327f  ldarg.0
0x3280  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpClient::get_DefaultRequestHeaders()
0x3285  ldstr    aXSsrsClientses// "X-SSRS-ClientSessionId"
0x328a  ldloc.0
0x328b  callvirt instance string Microsoft.BIServer.HostingEnvironment.Request.RequestContext::get_ClientSessionID()
0x3290  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x3295  ret
```
