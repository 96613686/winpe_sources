# Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>(void)

- ea: `0x1800055ac`
- end: `0x1800055e0`
- name: `??1?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@QEAA@XZ`
- size: `52`
- prototype: `NTSTATUS __fastcall(void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800177f8`
- `0x18003209a`
- `0x180032663`
- `0x1800326b4`
- `0x180032909`
- `0x180032c06`

## callees

- `0x1800055ac`

## import_xrefs

- `ntdll!NtClose` at `0x1800055c2`
- `ntdll!NtClose` at `0x1800055c2`

## pseudocode

```c

```
