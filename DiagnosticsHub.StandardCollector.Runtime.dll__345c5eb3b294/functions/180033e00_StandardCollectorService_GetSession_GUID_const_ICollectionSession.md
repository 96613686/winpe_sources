# StandardCollectorService::GetSession(_GUID const &,ICollectionSession * *)

- ea: `0x180033e00`
- end: `0x180033f49`
- name: `?GetSession@StandardCollectorService@@UEAAJAEBU_GUID@@PEAPEAUICollectionSession@@@Z`
- size: `329`
- prototype: `int(StandardCollectorService *__hidden this, const struct _GUID *, struct ICollectionSession **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180010540`
- `0x180031db0`
- `0x18003223c`
- `0x180033e00`
- `0x18004b640`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x180033e5f`
- `KERNEL32!ReleaseSRWLockShared` at `0x180033e9b`
- `KERNEL32!ReleaseSRWLockShared` at `0x180033e5f`
- `KERNEL32!ReleaseSRWLockShared` at `0x180033e9b`
- `KERNEL32!AcquireSRWLockShared` at `0x180033e35`
- `KERNEL32!AcquireSRWLockShared` at `0x180033e35`
- `KERNEL32!CloseHandle` at `0x180033f11`
- `KERNEL32!CloseHandle` at `0x180033f11`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033f1b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033f1b`

## pseudocode

```c

```
