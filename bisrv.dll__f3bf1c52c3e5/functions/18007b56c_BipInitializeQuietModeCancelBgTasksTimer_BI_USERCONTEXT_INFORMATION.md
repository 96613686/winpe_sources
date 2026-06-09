# BipInitializeQuietModeCancelBgTasksTimer(_BI_USERCONTEXT_INFORMATION *)

- ea: `0x18007b56c`
- end: `0x18007b61a`
- name: `?BipInitializeQuietModeCancelBgTasksTimer@@YAJPEAU_BI_USERCONTEXT_INFORMATION@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(struct _BI_USERCONTEXT_INFORMATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18007b6dc`

## callees

- `0x18007b56c`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x18007b5db`
- `ntdll!TpAllocTimer` at `0x18007b5db`
- `ntdll!RtlFreeHeap` at `0x18007b602`
- `ntdll!RtlFreeHeap` at `0x18007b602`
- `ntdll!RtlAllocateHeap` at `0x18007b594`
- `ntdll!RtlAllocateHeap` at `0x18007b594`
- `ntdll!RtlCopySid` at `0x18007b5c3`
- `ntdll!RtlCopySid` at `0x18007b5c3`

## pseudocode

```c

```
