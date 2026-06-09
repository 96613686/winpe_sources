# Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::IsUPNFormat

- ea: `0x2990`
- end: `0x2999`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::IsUPNFormat`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x29d0`

## callees

- `0x29b0`

## pseudocode

```c

```

## disassembly

```asm
0x2990  ldarg.0
0x2991  ldc.i4.s 0x40
0x2993  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::StringContainsChar(string str, char c)
0x2998  ret
```
