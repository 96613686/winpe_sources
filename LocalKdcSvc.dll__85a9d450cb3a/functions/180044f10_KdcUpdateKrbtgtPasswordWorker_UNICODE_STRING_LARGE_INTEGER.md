# KdcUpdateKrbtgtPasswordWorker(_UNICODE_STRING *,_LARGE_INTEGER *)

- ea: `0x180044f10`
- end: `0x180045081`
- name: `?KdcUpdateKrbtgtPasswordWorker@@YA?AV?$tuple@_NJ@std@@PEAU_UNICODE_STRING@@PEAT_LARGE_INTEGER@@@Z`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180045090`

## callees

- `0x180002ad0`
- `0x1800101ec`
- `0x180044f10`
- `0x18008244c`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180044f6b`
- `ntdll!RtlAcquireResourceShared` at `0x180044f6b`
- `ntdll!RtlReleaseResource` at `0x180044f8a`
- `ntdll!RtlReleaseResource` at `0x180044f8a`
- `ntdll!NtQuerySystemTime` at `0x180044f98`
- `ntdll!NtQuerySystemTime` at `0x180044f98`
- `SAMSRV!SamIChangePasswordForeignUser` at `0x180045013`
- `SAMSRV!SamIChangePasswordForeignUser` at `0x180045013`

## pseudocode

```c

```
