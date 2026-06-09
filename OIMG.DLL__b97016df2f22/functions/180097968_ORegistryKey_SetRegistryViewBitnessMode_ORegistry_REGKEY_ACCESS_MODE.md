# ORegistryKey::SetRegistryViewBitnessMode(ORegistry::REGKEY_ACCESS_MODE)

- ea: `0x180097968`
- end: `0x180097b11`
- name: `?SetRegistryViewBitnessMode@ORegistryKey@@AEAAKW4REGKEY_ACCESS_MODE@ORegistry@@@Z`
- size: `425`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180097514`
- `0x18009784c`

## callees

- `0x180097968`
- `0x180097b58`
- `0x18056bd00`
- `0x18056dc2e`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x180097a0d`
- `KERNEL32!GetModuleHandleExW` at `0x180097a0d`
- `KERNEL32!GetLastError` at `0x180097ac7`
- `KERNEL32!GetLastError` at `0x180097aec`
- `KERNEL32!GetLastError` at `0x180097ac7`
- `KERNEL32!GetLastError` at `0x180097aec`
- `KERNEL32!GetProcAddress` at `0x180097a23`
- `KERNEL32!GetProcAddress` at `0x180097a23`
- `KERNEL32!FreeLibrary` at `0x180097a7a`
- `KERNEL32!FreeLibrary` at `0x180097a7a`
- `KERNEL32!GetCurrentProcess` at `0x1800979a0`
- `KERNEL32!GetCurrentProcess` at `0x1800979d3`
- `KERNEL32!GetCurrentProcess` at `0x180097a3b`
- `KERNEL32!GetCurrentProcess` at `0x1800979a0`
- `KERNEL32!GetCurrentProcess` at `0x1800979d3`
- `KERNEL32!GetCurrentProcess` at `0x180097a3b`
- `KERNEL32!IsWow64Process` at `0x1800979ae`
- `KERNEL32!IsWow64Process` at `0x1800979e1`
- `KERNEL32!IsWow64Process` at `0x1800979ae`
- `KERNEL32!IsWow64Process` at `0x1800979e1`

## string_xrefs

- `0x180097a04`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c

```
