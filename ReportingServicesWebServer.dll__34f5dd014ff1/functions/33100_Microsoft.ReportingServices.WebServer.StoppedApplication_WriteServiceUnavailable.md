# Microsoft.ReportingServices.WebServer.StoppedApplication::WriteServiceUnavailable

- ea: `0x33100`
- end: `0x33130`
- name: `Microsoft.ReportingServices.WebServer.StoppedApplication::WriteServiceUnavailable`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c630`
- `0x330e0`

## callees

- `0x33100`
- `0x35800`
- `0x35810`

## string_xrefs

- `0x33101`: `500 - Service unavailable`

## pseudocode

```c

```

## disassembly

```asm
0x33100  ldarg.0
0x33101  ldstr    a500ServiceUnav// "500 - Service unavailable"
0x33106  callvirt instance void [System.Web]System.Web.HttpResponse::set_Status(string)
0x3310b  ldarg.0
0x3310c  ldc.i4   0x1F4
0x33111  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x33116  ldarg.0
0x33117  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::IsBiServer()
0x3311c  brtrue.s loc_33125
0x3311e  call     string Microsoft.ReportingServices.WebServer.WebServRes::get_ReportingServiceUnavailable()
0x33123  br.s     loc_3312A
0x33125  call     string Microsoft.ReportingServices.WebServer.WebServRes::get_ReportServerUnavailable()
0x3312a  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x3312f  ret
```
