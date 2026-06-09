# AipRemovePolicyClientCallback(void *,uchar)

- ea: `0x180026ba0`
- end: `0x180026c4e`
- name: `?AipRemovePolicyClientCallback@@YAXPEAXE@Z`
- size: `174`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180026790`

## callees

- `0x18000dac0`
- `0x180026b7c`
- `0x180026ba0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c2f`
- `ntdll!NtClose` at `0x180026c20`
- `ntdll!NtClose` at `0x180026c20`
- `ntdll!RtlDeregisterWait` at `0x180026bce`
- `ntdll!RtlDeregisterWait` at `0x180026bce`
- `ntdll!RtlDeregisterWaitEx` at `0x180026bc0`
- `ntdll!RtlDeregisterWaitEx` at `0x180026bc0`

## pseudocode

```c

```
