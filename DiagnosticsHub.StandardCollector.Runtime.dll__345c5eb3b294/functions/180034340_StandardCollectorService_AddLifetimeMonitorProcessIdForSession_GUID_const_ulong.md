# StandardCollectorService::AddLifetimeMonitorProcessIdForSession(_GUID const &,ulong)

- ea: `0x180034340`
- end: `0x1800344a3`
- name: `?AddLifetimeMonitorProcessIdForSession@StandardCollectorService@@UEAAJAEBU_GUID@@K@Z`
- size: `355`
- prototype: `int(StandardCollectorService *__hidden this, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callees

- `0x180010540`
- `0x180031db0`
- `0x18003223c`
- `0x180034340`
- `0x1800352ec`
- `0x18004b640`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18003439a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800343d6`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003439a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800343d6`
- `KERNEL32!AcquireSRWLockShared` at `0x180034370`
- `KERNEL32!AcquireSRWLockShared` at `0x180034370`
- `KERNEL32!CloseHandle` at `0x18003443a`
- `KERNEL32!CloseHandle` at `0x18003443a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180034444`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180034444`

## pseudocode

```c

```
