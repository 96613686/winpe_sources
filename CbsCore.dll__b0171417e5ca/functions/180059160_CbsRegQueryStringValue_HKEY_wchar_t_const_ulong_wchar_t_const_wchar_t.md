# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x180059160`
- end: `0x180059678`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1304`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const wchar_t *@<r9>, wchar_t **)`
- caller_count: `20`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18005b7e4`
- `0x1800a603c`
- `0x1800ae584`
- `0x1800d90fc`
- `0x1800e1354`
- `0x1800f3f0c`
- `0x1801080a0`
- `0x18010ca80`
- `0x18010cfe0`
- `0x180126880`
- `0x18014a418`
- `0x18014aaac`
- `0x180197ea0`
- `0x180198924`
- `0x180199014`
- `0x180199ad8`
- `0x1801ca0a4`
- `0x1801ee0b0`
- `0x1801efae0`
- `0x18029c6cc`

## callees

- `0x180010cc0`
- `0x18003330c`
- `0x180033d50`
- `0x1800441fc`
- `0x18004a658`
- `0x180059160`
- `0x18005ad5c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800593a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800594ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800595b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800593a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800594ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800595b0`

## string_xrefs

- `0x18005928c`: `Failed to open the registry root: n/a, key: {}.`
- `0x180059507`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x1800593d9`: `Registry value is not a string type.`
- `0x180059453`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x1800595d5`: `Failed to query registry value: {}`

## pseudocode

```c

```
