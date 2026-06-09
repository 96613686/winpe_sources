# GetEventInfoFromRegistry(HKEY__ *,ushort const *,EventSoundInfo *)

- ea: `0x1800c87fc`
- end: `0x1800c8966`
- name: `?GetEventInfoFromRegistry@@YAJPEAUHKEY__@@PEBGPEAUEventSoundInfo@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpSubKey, struct EventSoundInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007fc28`

## callees

- `0x180087e80`
- `0x1800c87fc`
- `0x1800c896c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800c893f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800c893f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c8877`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c88d3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c892a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c8877`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c88d3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c892a`

## pseudocode

```c

```
