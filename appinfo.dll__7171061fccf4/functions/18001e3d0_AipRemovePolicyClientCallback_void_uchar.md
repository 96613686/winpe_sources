# AipRemovePolicyClientCallback(void *,uchar)

- ea: `0x18001e3d0`
- end: `0x18001e463`
- name: `?AipRemovePolicyClientCallback@@YAXPEAXE@Z`
- size: `147`
- prototype: `void __fastcall(PVOID, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800277b0`

## callees

- `0x18000ce00`
- `0x18001e3d0`
- `0x18001e46c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e44b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e44b`
- `ntdll!NtClose` at `0x18001e442`
- `ntdll!NtClose` at `0x18001e442`
- `ntdll!RtlDeregisterWait` at `0x18001e3f8`
- `ntdll!RtlDeregisterWait` at `0x18001e3f8`
- `ntdll!RtlDeregisterWaitEx` at `0x18001e3f0`
- `ntdll!RtlDeregisterWaitEx` at `0x18001e3f0`

## pseudocode

```c

```
