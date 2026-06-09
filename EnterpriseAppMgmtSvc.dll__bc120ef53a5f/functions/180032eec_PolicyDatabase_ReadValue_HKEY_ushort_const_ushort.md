# PolicyDatabase::ReadValue(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180032eec`
- end: `0x18003300b`
- name: `?ReadValue@PolicyDatabase@@IEAAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `287`
- prototype: `int(PolicyDatabase *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180032860`

## callees

- `0x180032eec`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180032f90`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180032f90`
- `OLEAUT32!__imp_SysFreeString` at `0x180032fef`
- `OLEAUT32!__imp_SysFreeString` at `0x180032fef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032f56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032fc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032f56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032fc8`

## pseudocode

```c

```
