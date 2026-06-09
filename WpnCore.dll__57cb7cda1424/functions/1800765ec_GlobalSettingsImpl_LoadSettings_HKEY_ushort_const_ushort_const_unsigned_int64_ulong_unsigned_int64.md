# GlobalSettingsImpl::LoadSettings(HKEY__ *,ushort const *,ushort const * *,unsigned __int64,ulong * *,unsigned __int64)

- ea: `0x1800765ec`
- end: `0x18007698a`
- name: `?LoadSettings@GlobalSettingsImpl@@AEAAXPEAUHKEY__@@PEBGPEAPEBG_KPEAPEAK3@Z`
- size: `926`
- prototype: `void(GlobalSettingsImpl *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 **, unsigned __int64, unsigned int **, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180076324`
- `0x180076488`
- `0x180076518`

## callees

- `0x18002ee38`
- `0x1800765ec`
- `0x1800a0b2c`
- `0x1800af0a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800768fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800768fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007680d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007680d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800767fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800767fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076826`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076834`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076834`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007665a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007665a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180076883`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180076883`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800766fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800766fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800766ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800766ab`

## pseudocode

```c

```
