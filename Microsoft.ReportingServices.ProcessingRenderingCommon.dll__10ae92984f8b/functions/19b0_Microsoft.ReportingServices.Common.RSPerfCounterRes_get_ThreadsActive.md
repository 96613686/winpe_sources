# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ThreadsActive

- ea: `0x19b0`
- end: `0x19bb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_ThreadsActive`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1180`

## callees

- `0x15520`

## string_xrefs

- `0x19b0`: `ThreadsActive`

## pseudocode

```c

```

## disassembly

```asm
0x19b0  ldstr    aThreadsactive// "ThreadsActive"
0x19b5  call     string Keys::GetString(string key)
0x19ba  ret
```
