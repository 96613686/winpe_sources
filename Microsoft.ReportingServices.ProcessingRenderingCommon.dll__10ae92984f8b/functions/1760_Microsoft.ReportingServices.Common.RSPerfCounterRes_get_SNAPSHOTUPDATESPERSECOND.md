# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SNAPSHOTUPDATESPERSECOND

- ea: `0x1760`
- end: `0x176b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SNAPSHOTUPDATESPERSECOND`
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

- `0x1760`: `SNAPSHOTUPDATESPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldstr    aSnapshotupdate_0// "SNAPSHOTUPDATESPERSECOND"
0x1765  call     string Keys::GetString(string key)
0x176a  ret
```
