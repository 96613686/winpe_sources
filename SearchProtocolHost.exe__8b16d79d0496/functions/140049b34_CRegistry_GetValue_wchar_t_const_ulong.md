# CRegistry::GetValue(wchar_t const *,ulong *)

- ea: `0x140049b34`
- end: `0x140049bd6`
- name: `?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z`
- size: `162`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001cad4`
- `0x14001d314`
- `0x14001d6ac`
- `0x14003a8e8`

## callees

- `0x140049b34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049b9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140049b9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049b4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049bbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049b4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049bbe`

## pseudocode

```c

```
