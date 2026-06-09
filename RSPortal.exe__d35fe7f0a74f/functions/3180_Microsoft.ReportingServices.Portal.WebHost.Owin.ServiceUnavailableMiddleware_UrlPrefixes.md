# Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::UrlPrefixes

- ea: `0x3180`
- end: `0x3193`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::UrlPrefixes`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3120`

## pseudocode

```c

```

## disassembly

```asm
0x3180  ldarg.0
0x3181  ldnull
0x3182  ldftn    string Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::ParseUrlPrefix(string url)
0x3188  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x318d  call     T0x2B000002
0x3192  ret
```
