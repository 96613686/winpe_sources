# MVHelper::GetDwordValue(ushort const * const,ulong,ushort const * const,ulong &,bool)

- ea: `0x180024e38`
- end: `0x180024fae`
- name: `?GetDwordValue@MVHelper@@QEAAJQEBGK0AEAK_N@Z`
- size: `374`
- prototype: `int(MVHelper *__hidden this, const unsigned __int16 *const, unsigned int, const unsigned __int16 *const, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004c950`
- `0x18004c9d4`

## callees

- `0x18000ad20`
- `0x18000bde0`
- `0x180014fec`
- `0x1800191d0`
- `0x180024e38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024ef2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024ef2`

## string_xrefs

- `0x180024f78`: `GetDwordValue Error. readLocation=%d, wszName=%ls, dwReadingRule=%d, HRESULT=%d`
- `0x180024f46`: `GetDwordValue Succeeded. readLocation=%d, wszName=%ls, dwValue=%d`

## pseudocode

```c

```
