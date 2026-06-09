# Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::ReturnResult

- ea: `0x30f0`
- end: `0x311d`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::ReturnResult`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30e0`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  ldarg.1
0x30f1  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x30f6  ldc.i4   0x1F7
0x30fb  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::set_StatusCode(int32)
0x3100  ldarg.1
0x3101  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x3106  ldarg.2
0x3107  newobj   instance void class <>f__AnonymousType1`1<int32>::.ctor(var<u1>)
0x310c  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x3111  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinResponse::Write(string)
0x3116  ldc.i4.0
0x3117  call     T0x2B000008
0x311c  ret
```
