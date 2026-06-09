# Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::IsDomainUserFormat

- ea: `0x29a0`
- end: `0x29a9`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::IsDomainUserFormat`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x29b0`

## pseudocode

```c

```

## disassembly

```asm
0x29a0  ldarg.0
0x29a1  ldc.i4.s 0x5C
0x29a3  call     bool Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::StringContainsChar(string str, char c)
0x29a8  ret
```
