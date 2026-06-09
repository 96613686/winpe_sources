# MbpDetectText

- ea: `0x180054650`
- end: `0x180054aaa`
- name: `MbpDetectText`
- size: `1114`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180054280`
- `0x180054310`
- `0x1800543b0`
- `0x180054450`
- `0x1800544d0`
- `0x180054550`

## callees

- `0x180009e94`
- `0x18000f114`
- `0x18001c320`
- `0x18002606c`
- `0x18002c358`
- `0x180054238`
- `0x180054650`
- `0x1800560b4`
- `0x1800561fc`
- `0x1800562d4`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180054a7e`
- `ntdll!RtlFreeHeap` at `0x180054a9f`
- `ntdll!RtlFreeHeap` at `0x180054a7e`
- `ntdll!RtlFreeHeap` at `0x180054a9f`
- `ntdll!RtlAllocateHeap` at `0x1800547ed`
- `ntdll!RtlAllocateHeap` at `0x1800547ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054a1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054a46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054a1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054a46`

## string_xrefs

- `0x180054837`: `Failed to copy string [%d]`
- `0x180054a22`: `Privilege MessageBox detected`

## pseudocode

```c

```
