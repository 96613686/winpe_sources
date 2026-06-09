# AslFileMappingDelete

- ea: `0x18004b934`
- end: `0x18004ba10`
- name: `AslFileMappingDelete`
- size: `220`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004b634`
- `0x1800e19ac`
- `0x1800e223c`

## callees

- `0x18004b934`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x18004b97a`
- `ntdll!ZwUnmapViewOfSection` at `0x18004b97a`
- `ntdll!ZwClose` at `0x18004b961`
- `ntdll!ZwClose` at `0x18004b98f`
- `ntdll!ZwClose` at `0x18004b961`
- `ntdll!ZwClose` at `0x18004b98f`
- `ntdll!RtlFreeHeap` at `0x18004b9bb`
- `ntdll!RtlFreeHeap` at `0x18004b9e0`
- `ntdll!RtlFreeHeap` at `0x18004b9ff`
- `ntdll!RtlFreeHeap` at `0x18004b9bb`
- `ntdll!RtlFreeHeap` at `0x18004b9e0`
- `ntdll!RtlFreeHeap` at `0x18004b9ff`

## pseudocode

```c

```
