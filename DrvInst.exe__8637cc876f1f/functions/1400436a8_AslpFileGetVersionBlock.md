# AslpFileGetVersionBlock

- ea: `0x1400436a8`
- end: `0x140043ced`
- name: `AslpFileGetVersionBlock`
- size: `1605`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400435bc`

## callees

- `0x140001b64`
- `0x14003bf18`
- `0x14003c368`
- `0x14003ce80`
- `0x14003d508`
- `0x14003d65c`
- `0x1400436a8`
- `0x140045488`
- `0x1400454d0`
- `0x140045540`
- `0x140045ede`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140043ad6`
- `ntdll!RtlAllocateHeap` at `0x140043ad6`
- `ntdll!VerSetConditionMask` at `0x14004388b`
- `ntdll!VerSetConditionMask` at `0x14004389a`
- `ntdll!VerSetConditionMask` at `0x14004388b`
- `ntdll!VerSetConditionMask` at `0x14004389a`
- `ntdll!RtlVerifyVersionInfo` at `0x1400438ae`
- `ntdll!RtlVerifyVersionInfo` at `0x1400438ae`
- `ntdll!LdrResSearchResource` at `0x14004380f`
- `ntdll!LdrResSearchResource` at `0x14004397f`
- `ntdll!LdrResSearchResource` at `0x14004380f`
- `ntdll!LdrResSearchResource` at `0x14004397f`

## string_xrefs

- `0x140043aaf`: `Version block has bad size (falls outside file)`
- `0x140043c32`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
