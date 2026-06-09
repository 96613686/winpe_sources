# CRegistry::GetValue(wchar_t const *,uchar *,ulong *)

- ea: `0x18002aca4`
- end: `0x18002ad21`
- name: `?GetValue@CRegistry@@QEAAHPEB_WPEAEPEAK@Z`
- size: `125`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038164`

## callees

- `0x18002aca4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002acbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002acda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002acbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002acda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002acf9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002acf9`

## pseudocode

```c

```
