# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WinService

- ea: `0x1560`
- end: `0x156b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WinService`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2500`

## callees

- `0x15520`

## string_xrefs

- `0x1560`: `WinService`

## pseudocode

```c

```

## disassembly

```asm
0x1560  ldstr    aWinservice// "WinService"
0x1565  call     string Keys::GetString(string key)
0x156a  ret
```
