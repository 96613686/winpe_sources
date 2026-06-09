# SystemSettings::WorkAccess::IsDesktopSKU(void)

- ea: `0x1800433e8`
- end: `0x180043442`
- name: `?IsDesktopSKU@WorkAccess@SystemSettings@@YA_NXZ`
- size: `90`
- prototype: `bool __fastcall(SystemSettings::WorkAccess *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180026be8`
- `0x180029400`
- `0x1800297d0`
- `0x1800318c0`
- `0x18003a340`
- `0x180040fa0`
- `0x1800416c0`
- `0x180042e1c`
- `0x180043030`

## callees

- `0x1800433e8`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18004341d`
- `ntdll!RtlIsMultiSessionSku` at `0x18004341d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800433fe`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800433fe`

## pseudocode

```c

```
