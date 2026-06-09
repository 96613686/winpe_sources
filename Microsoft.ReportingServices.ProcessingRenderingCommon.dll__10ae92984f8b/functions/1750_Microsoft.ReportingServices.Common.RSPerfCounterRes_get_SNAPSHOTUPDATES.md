# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SNAPSHOTUPDATES

- ea: `0x1750`
- end: `0x175b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SNAPSHOTUPDATES`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2050`

## callees

- `0x15520`

## string_xrefs

- `0x1750`: `SNAPSHOTUPDATES`

## pseudocode

```c

```

## disassembly

```asm
0x1750  ldstr    aSnapshotupdate// "SNAPSHOTUPDATES"
0x1755  call     string Keys::GetString(string key)
0x175a  ret
```
