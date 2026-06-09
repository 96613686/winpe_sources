# AslpFileGetVersionBlock

- ea: `0x180022c04`
- end: `0x180023324`
- name: `AslpFileGetVersionBlock`
- size: `1824`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180022a00`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x180022c04`
- `0x1800244c0`
- `0x18004ee40`
- `0x180052e34`
- `0x180059920`
- `0x18005a7c0`
- `0x18005a8bc`
- `0x180070120`
- `0x18012549c`

## import_xrefs

- `ntdll!RtlVerifyVersionInfo` at `0x180022e28`
- `ntdll!RtlVerifyVersionInfo` at `0x180022e28`
- `ntdll!ZwUnmapViewOfSection` at `0x1800232dc`
- `ntdll!ZwUnmapViewOfSection` at `0x1800232dc`
- `ntdll!ZwClose` at `0x1800232bb`
- `ntdll!ZwClose` at `0x1800232f9`
- `ntdll!ZwClose` at `0x1800232bb`
- `ntdll!ZwClose` at `0x1800232f9`
- `ntdll!RtlAllocateHeap` at `0x18002307e`
- `ntdll!RtlAllocateHeap` at `0x18002307e`
- `ntdll!VerSetConditionMask` at `0x180022e06`
- `ntdll!VerSetConditionMask` at `0x180022e15`
- `ntdll!VerSetConditionMask` at `0x180022e06`
- `ntdll!VerSetConditionMask` at `0x180022e15`
- `ntdll!LdrResSearchResource` at `0x180022d87`
- `ntdll!LdrResSearchResource` at `0x180022efa`
- `ntdll!LdrResSearchResource` at `0x180022d87`
- `ntdll!LdrResSearchResource` at `0x180022efa`

## string_xrefs

- `0x18002322a`: `Version block has bad size (falls outside file)`
- `0x1800231fc`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
