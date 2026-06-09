# Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::RedirectToUri

- ea: `0x3390`
- end: `0x33b3`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::RedirectToUri`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3300`

## pseudocode

```c

```

## disassembly

```asm
0x3390  ldarg.1
0x3391  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x3396  ldarg.3
0x3397  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x339c  ldarg.1
0x339d  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x33a2  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_Headers()
0x33a7  ldstr    aLocation// "Location"
0x33ac  ldarg.2
0x33ad  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::Set(string, string)
0x33b2  ret
```
