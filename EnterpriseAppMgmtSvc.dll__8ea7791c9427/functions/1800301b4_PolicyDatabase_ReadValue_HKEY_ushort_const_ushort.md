# PolicyDatabase::ReadValue(HKEY__ *,ushort const *,ushort * *)

- ea: `0x1800301b4`
- end: `0x1800302ba`
- name: `?ReadValue@PolicyDatabase@@IEAAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `262`
- prototype: `int(PolicyDatabase *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002fb74`

## callees

- `0x1800301b4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180030252`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180030252`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800302a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003021e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030284`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003021e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030284`

## pseudocode

```c

```
