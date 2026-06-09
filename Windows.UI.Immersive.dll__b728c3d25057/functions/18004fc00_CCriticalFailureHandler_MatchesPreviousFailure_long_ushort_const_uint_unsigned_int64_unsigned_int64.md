# CCriticalFailureHandler::_MatchesPreviousFailure(long,ushort const *,uint,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18004fc00`
- end: `0x18004fdfd`
- name: `?_MatchesPreviousFailure@CCriticalFailureHandler@@AEBA_NJPEBGIPEA_K1@Z`
- size: `509`
- prototype: `bool(CCriticalFailureHandler *__hidden this, int, const unsigned __int16 *, unsigned int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800d2194`

## callees

- `0x180030674`
- `0x18004fc00`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fdce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fdce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fc62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fc62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004fd05`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004fd05`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004fd32`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004fd32`

## pseudocode

```c

```
