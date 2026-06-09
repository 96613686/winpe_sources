# Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::Register

- ea: `0x3120`
- end: `0x314c`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::Register`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x3120`
- `0x3150`
- `0x3180`

## pseudocode

```c

```

## disassembly

```asm
0x3120  ldarg.1
0x3121  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_WebAppUrls()
0x3126  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::UrlPrefixes(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> urls)
0x312b  ldarg.1
0x312c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerUrls()
0x3131  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::UrlPrefixes(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> urls)
0x3136  stloc.0
0x3137  ldloc.0
0x3138  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::PrefixMatch(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> webAppPrefixes, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> reportServerPrefixes)
0x313d  brtrue.s loc_314B
0x313f  ldarg.0
0x3140  call     T0x2B000001
0x3145  call     T0x2B00000E
0x314a  pop
0x314b  ret
```
