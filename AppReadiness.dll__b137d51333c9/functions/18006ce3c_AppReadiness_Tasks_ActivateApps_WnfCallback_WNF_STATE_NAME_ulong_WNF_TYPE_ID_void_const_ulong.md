# AppReadiness::Tasks::ActivateApps::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void const *,ulong)

- ea: `0x18006ce3c`
- end: `0x18006d063`
- name: `?WnfCallback@ActivateApps@Tasks@AppReadiness@@AEAAXU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEBXK@Z`
- size: `551`
- prototype: `void __usercall(AppReadiness::Tasks::ActivateApps *__hidden this@<rcx>, struct _WNF_STATE_NAME@<rdx>, unsigned int@<r8d>, struct _WNF_TYPE_ID *@<r9>, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006d150`

## callees

- `0x180002958`
- `0x180002a60`
- `0x180005270`
- `0x180008bb0`
- `0x18000a470`
- `0x1800148b0`
- `0x180019260`
- `0x18001a8c0`
- `0x18002b63c`
- `0x1800465f8`
- `0x18006ce3c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d026`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d026`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ced8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ced8`

## string_xrefs

- `0x18006cfcf`: `Completed`

## pseudocode

```c

```
