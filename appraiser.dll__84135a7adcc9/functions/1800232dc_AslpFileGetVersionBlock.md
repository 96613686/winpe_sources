# AslpFileGetVersionBlock

- ea: `0x1800232dc`
- end: `0x180023a0a`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800230e8`

## callees

- `0x180008570`
- `0x1800091bc`
- `0x1800092dc`
- `0x18001a2f4`
- `0x180020954`
- `0x180020fc8`
- `0x1800232dc`
- `0x1800252a0`
- `0x1802174f0`

## import_xrefs

- `ntdll!ZwClose` at `0x1800239a1`
- `ntdll!ZwClose` at `0x1800239df`
- `ntdll!ZwClose` at `0x1800239a1`
- `ntdll!ZwClose` at `0x1800239df`
- `ntdll!RtlFreeHeap` at `0x180023984`
- `ntdll!RtlFreeHeap` at `0x180023984`
- `ntdll!RtlAllocateHeap` at `0x180023746`
- `ntdll!RtlAllocateHeap` at `0x180023746`
- `ntdll!ZwUnmapViewOfSection` at `0x1800239c2`
- `ntdll!ZwUnmapViewOfSection` at `0x1800239c2`
- `ntdll!VerSetConditionMask` at `0x1800234ce`
- `ntdll!VerSetConditionMask` at `0x1800234dd`
- `ntdll!VerSetConditionMask` at `0x1800234ce`
- `ntdll!VerSetConditionMask` at `0x1800234dd`
- `ntdll!LdrResSearchResource` at `0x18002344f`
- `ntdll!LdrResSearchResource` at `0x1800235c2`
- `ntdll!LdrResSearchResource` at `0x18002344f`
- `ntdll!LdrResSearchResource` at `0x1800235c2`
- `ntdll!RtlVerifyVersionInfo` at `0x1800234f0`
- `ntdll!RtlVerifyVersionInfo` at `0x1800234f0`

## string_xrefs

- `0x18002390d`: `Version block has bad size (falls outside file)`
- `0x1800238df`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
