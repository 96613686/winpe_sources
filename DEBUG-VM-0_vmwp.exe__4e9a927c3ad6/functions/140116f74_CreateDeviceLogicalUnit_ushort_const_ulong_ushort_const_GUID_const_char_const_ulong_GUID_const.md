# CreateDeviceLogicalUnit(ushort const *,ulong,ushort const *,_GUID const *,char const *,ulong,_GUID const *)

- ea: `0x140116f74`
- end: `0x1401171d2`
- name: `?CreateDeviceLogicalUnit@@YAPEAXPEBGK0PEBU_GUID@@PEBDK1@Z`
- size: `606`
- prototype: `void *__fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const struct _GUID *, const char *, unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140084c1c`

## callees

- `0x1400042d8`
- `0x14005611c`
- `0x140086dec`
- `0x140087488`
- `0x140116f74`
- `0x140132940`
- `0x1401335fc`
- `0x140133768`
- `0x1401b6b40`
- `0x1401b6cd0`
- `0x1401b7490`
- `0x1401b7628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140117191`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140117191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140117160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140117160`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140117059`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140117059`

## string_xrefs

- `0x140116fbd`: `VstorCreateDeviceLogicalUnit`
- `0x140116feb`: `VhdSetUtilities::OpenStorageLogicalUnit`
- `0x140117123`: `VhdSetUtilities::OpenStorageLogicalUnit`

## pseudocode

```c

```
