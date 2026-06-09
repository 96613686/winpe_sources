# FseConfigurePortPolicy

- ea: `0x18028a03c`
- end: `0x18028a2b8`
- name: `FseConfigurePortPolicy`
- size: `636`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ee0e8`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005ffc4`
- `0x18028a03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028a1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028a1f5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18028a1e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18028a1e7`
- `ntdll!RtlAllocateHeap` at `0x18028a126`
- `ntdll!RtlAllocateHeap` at `0x18028a126`
- `ntdll!RtlFreeHeap` at `0x18028a288`
- `ntdll!RtlFreeHeap` at `0x18028a288`

## string_xrefs

- `0x18028a226`: `IOCTL_FSE_CONFIG_PORT_POLICY`
- `0x18028a0b5`: `FseConfigurePortPolicy`

## pseudocode

```c

```
