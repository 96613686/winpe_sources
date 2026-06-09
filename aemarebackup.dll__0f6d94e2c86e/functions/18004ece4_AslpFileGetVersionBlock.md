# AslpFileGetVersionBlock

- ea: `0x18004ece4`
- end: `0x18004f412`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004eaf0`

## callees

- `0x180004ea0`
- `0x180005884`
- `0x180005914`
- `0x18000712e`
- `0x18004ba18`
- `0x18004c020`
- `0x18004ece4`
- `0x1800515b0`
- `0x1800515f4`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x18004ee57`
- `ntdll!LdrResSearchResource` at `0x18004efca`
- `ntdll!LdrResSearchResource` at `0x18004ee57`
- `ntdll!LdrResSearchResource` at `0x18004efca`
- `ntdll!RtlVerifyVersionInfo` at `0x18004eef8`
- `ntdll!RtlVerifyVersionInfo` at `0x18004eef8`
- `ntdll!RtlAllocateHeap` at `0x18004f14e`
- `ntdll!RtlAllocateHeap` at `0x18004f14e`
- `ntdll!ZwUnmapViewOfSection` at `0x18004f3ca`
- `ntdll!ZwUnmapViewOfSection` at `0x18004f3ca`
- `ntdll!ZwClose` at `0x18004f3a9`
- `ntdll!ZwClose` at `0x18004f3e7`
- `ntdll!ZwClose` at `0x18004f3a9`
- `ntdll!ZwClose` at `0x18004f3e7`
- `ntdll!RtlFreeHeap` at `0x18004f38c`
- `ntdll!RtlFreeHeap` at `0x18004f38c`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18004eed6`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18004eee5`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18004eed6`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18004eee5`

## string_xrefs

- `0x18004f315`: `Version block has bad size (falls outside file)`
- `0x18004f2e7`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
