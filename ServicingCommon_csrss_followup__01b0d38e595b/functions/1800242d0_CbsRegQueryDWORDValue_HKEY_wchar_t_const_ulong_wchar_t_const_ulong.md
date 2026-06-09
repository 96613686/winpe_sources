# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x1800242d0`
- end: `0x1800245f8`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `808`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180047e20`
- `0x1800519ac`
- `0x180051a6c`

## callees

- `0x180020440`
- `0x1800242d0`
- `0x18002d2b0`
- `0x180046650`
- `0x180046bb4`
- `0x180046ca4`
- `0x1800473a8`
- `0x180047c5c`
- `0x18005126c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800244d4`
- `ADVAPI32!RegQueryValueExW` at `0x1800244d4`

## string_xrefs

- `0x180024431`: `Failed to open the registry root: n/a, key: {}.`
- `0x180024505`: `Failed to query registry value: {}`
- `0x180024574`: `Registry value is not a DWORD type.`

## pseudocode

```c

```
