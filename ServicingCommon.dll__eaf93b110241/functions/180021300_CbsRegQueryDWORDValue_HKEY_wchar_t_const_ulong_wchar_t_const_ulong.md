# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x180021300`
- end: `0x180021628`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `808`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180044c90`
- `0x18004e878`
- `0x18004e938`

## callees

- `0x18001e51c`
- `0x180021300`
- `0x1800293a0`
- `0x18003d7d4`
- `0x180041a74`
- `0x180041de8`
- `0x180043c00`
- `0x180044274`
- `0x18004e134`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180021504`
- `ADVAPI32!RegQueryValueExW` at `0x180021504`

## string_xrefs

- `0x180021461`: `Failed to open the registry root: n/a, key: {}.`
- `0x180021535`: `Failed to query registry value: {}`
- `0x1800215a4`: `Registry value is not a DWORD type.`

## pseudocode

```c

```
