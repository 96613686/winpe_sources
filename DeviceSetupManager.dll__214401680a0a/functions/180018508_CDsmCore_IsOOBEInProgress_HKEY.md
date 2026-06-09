# CDsmCore::_IsOOBEInProgress(HKEY__ *)

- ea: `0x180018508`
- end: `0x18001859f`
- name: `?_IsOOBEInProgress@CDsmCore@@AEAA_NPEAUHKEY__@@@Z`
- size: `151`
- prototype: `bool __fastcall(CDsmCore *this, HKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18001a774`
- `0x180023e70`

## callees

- `0x180018508`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018547`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018583`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018547`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018583`

## string_xrefs

- `0x180018569`: `OOBEInProgressDriverUpdatesPostponed`

## pseudocode

```c

```
