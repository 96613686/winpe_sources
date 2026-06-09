# OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)

- ea: `0x1800a2f00`
- end: `0x1800a31d2`
- name: `?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `722`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800a20bc`

## callees

- `0x180008570`
- `0x180011d94`
- `0x180013f90`
- `0x18001a558`
- `0x1800a2f00`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800a3059`
- `KERNEL32!GetProcessHeap` at `0x1800a30ce`
- `KERNEL32!GetProcessHeap` at `0x1800a3199`
- `KERNEL32!GetProcessHeap` at `0x1800a3059`
- `KERNEL32!GetProcessHeap` at `0x1800a30ce`
- `KERNEL32!GetProcessHeap` at `0x1800a3199`
- `KERNEL32!HeapAlloc` at `0x1800a30dd`
- `KERNEL32!HeapAlloc` at `0x1800a30dd`
- `KERNEL32!HeapFree` at `0x1800a3024`
- `KERNEL32!HeapFree` at `0x1800a3045`
- `KERNEL32!HeapFree` at `0x1800a31a7`
- `KERNEL32!HeapFree` at `0x1800a3024`
- `KERNEL32!HeapFree` at `0x1800a3045`
- `KERNEL32!HeapFree` at `0x1800a31a7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800a30ba`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800a30ba`
- `ADVAPI32!RegEnumValueW` at `0x1800a3162`
- `ADVAPI32!RegEnumValueW` at `0x1800a3162`
- `ADVAPI32!RegCloseKey` at `0x1800a318e`
- `ADVAPI32!RegCloseKey` at `0x1800a318e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a2fe7`
- `ADVAPI32!RegOpenKeyExW` at `0x1800a2fe7`

## pseudocode

```c

```
