# AipRemovePolicyClientCallback(void *,uchar)

- ea: `0x1800252b0`
- end: `0x18002535e`
- name: `?AipRemovePolicyClientCallback@@YAXPEAXE@Z`
- size: `174`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180024e9c`

## callees

- `0x18000da00`
- `0x180025288`
- `0x1800252b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002533f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002533f`
- `ntdll!NtClose` at `0x180025330`
- `ntdll!NtClose` at `0x180025330`
- `ntdll!RtlDeregisterWait` at `0x1800252de`
- `ntdll!RtlDeregisterWait` at `0x1800252de`
- `ntdll!RtlDeregisterWaitEx` at `0x1800252d0`
- `ntdll!RtlDeregisterWaitEx` at `0x1800252d0`

## pseudocode

```c

```
