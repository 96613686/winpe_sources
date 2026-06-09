# DsMessageBox_GetHookAPIs

- ea: `0x18001bb20`
- end: `0x18001bdc0`
- name: `DsMessageBox_GetHookAPIs`
- size: `672`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000f114`
- `0x18001bb20`
- `0x18001bfe8`
- `0x180039b60`
- `0x180059175`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001bb8c`
- `ntdll!RtlAllocateHeap` at `0x18001bb8c`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18001bb36`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18001bb36`

## string_xrefs

- `0x18001bbc7`: `USER32.DLL`
- `0x18001bd33`: `GetWindowThreadProcessId`

## pseudocode

```c

```
