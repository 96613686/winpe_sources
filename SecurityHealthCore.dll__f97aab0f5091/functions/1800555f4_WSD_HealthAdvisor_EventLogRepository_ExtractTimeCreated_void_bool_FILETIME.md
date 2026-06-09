# WSD::HealthAdvisor::EventLogRepository::ExtractTimeCreated(void *,bool *,_FILETIME *)

- ea: `0x1800555f4`
- end: `0x1800558ab`
- name: `?ExtractTimeCreated@EventLogRepository@HealthAdvisor@WSD@@CAJPEAXPEA_NPEAU_FILETIME@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(EVT_HANDLE Fragment, bool *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18005592c`

## callees

- `0x180004ae0`
- `0x180004b1c`
- `0x18000d7fc`
- `0x180010ff0`
- `0x1800555f4`
- `0x1800d65d0`
- `0x1800d668c`
- `0x1800d692c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800556db`
- `KERNEL32!GetLastError` at `0x180055763`
- `KERNEL32!GetLastError` at `0x1800557d5`
- `KERNEL32!GetLastError` at `0x1800556db`
- `KERNEL32!GetLastError` at `0x180055763`
- `KERNEL32!GetLastError` at `0x1800557d5`

## string_xrefs

- `0x1800556a5`: `Event/System/TimeCreated/@SystemTime`

## pseudocode

```c

```
