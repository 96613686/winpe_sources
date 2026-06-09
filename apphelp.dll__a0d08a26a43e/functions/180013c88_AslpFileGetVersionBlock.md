# AslpFileGetVersionBlock

- ea: `0x180013c88`
- end: `0x180014339`
- name: `AslpFileGetVersionBlock`
- size: `1713`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001445c`

## callees

- `0x18000f114`
- `0x180013364`
- `0x180013c88`
- `0x180018f20`
- `0x180035468`
- `0x180036a14`
- `0x180039a5a`
- `0x18003f3d4`
- `0x180059169`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlVerifyVersionInfo` at `0x180013ea3`
- `ntdll!RtlVerifyVersionInfo` at `0x180013ea3`
- `ntdll!ZwUnmapViewOfSection` at `0x1800142f1`
- `ntdll!ZwUnmapViewOfSection` at `0x1800142f1`
- `ntdll!ZwClose` at `0x1800142d0`
- `ntdll!ZwClose` at `0x18001430e`
- `ntdll!ZwClose` at `0x1800142d0`
- `ntdll!ZwClose` at `0x18001430e`
- `ntdll!LdrResSearchResource` at `0x180013e02`
- `ntdll!LdrResSearchResource` at `0x180013f75`
- `ntdll!LdrResSearchResource` at `0x180013e02`
- `ntdll!LdrResSearchResource` at `0x180013f75`
- `ntdll!VerSetConditionMask` at `0x180013e81`
- `ntdll!VerSetConditionMask` at `0x180013e90`
- `ntdll!VerSetConditionMask` at `0x180013e81`
- `ntdll!VerSetConditionMask` at `0x180013e90`
- `ntdll!RtlAllocateHeap` at `0x1800140d2`
- `ntdll!RtlAllocateHeap` at `0x1800140d2`

## string_xrefs

- `0x1800140ab`: `Version block has bad size (falls outside file)`
- `0x18001422e`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
