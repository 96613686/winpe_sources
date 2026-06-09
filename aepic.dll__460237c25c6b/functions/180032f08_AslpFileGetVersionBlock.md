# AslpFileGetVersionBlock

- ea: `0x180032f08`
- end: `0x18003354d`
- name: `AslpFileGetVersionBlock`
- size: `1605`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180032e1c`

## callees

- `0x180005890`
- `0x180006884`
- `0x18000692c`
- `0x180006938`
- `0x1800295dc`
- `0x18002979c`
- `0x1800304a4`
- `0x180030bd0`
- `0x180030d18`
- `0x180032f08`
- `0x180034c10`
- `0x180034c58`
- `0x180034cc8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180033336`
- `ntdll!RtlAllocateHeap` at `0x180033336`
- `ntdll!VerSetConditionMask` at `0x1800330eb`
- `ntdll!VerSetConditionMask` at `0x1800330fa`
- `ntdll!VerSetConditionMask` at `0x1800330eb`
- `ntdll!VerSetConditionMask` at `0x1800330fa`
- `ntdll!LdrResSearchResource` at `0x18003306f`
- `ntdll!LdrResSearchResource` at `0x1800331df`
- `ntdll!LdrResSearchResource` at `0x18003306f`
- `ntdll!LdrResSearchResource` at `0x1800331df`
- `ntdll!RtlVerifyVersionInfo` at `0x18003310e`
- `ntdll!RtlVerifyVersionInfo` at `0x18003310e`

## string_xrefs

- `0x18003330f`: `Version block has bad size (falls outside file)`
- `0x180033492`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
