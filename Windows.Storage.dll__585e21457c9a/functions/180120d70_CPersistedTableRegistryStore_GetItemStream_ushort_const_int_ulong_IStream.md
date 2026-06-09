# CPersistedTableRegistryStore::GetItemStream(ushort const *,int,ulong,IStream * *)

- ea: `0x180120d70`
- end: `0x18012116f`
- name: `?GetItemStream@CPersistedTableRegistryStore@@UEAAJPEBGHKPEAPEAUIStream@@@Z`
- size: `1023`
- prototype: `__int64 __usercall@<rax>(CPersistedTableRegistryStore *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, unsigned int@<r9d>, struct IStream **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x180058950`
- `0x180120030`

## callees

- `0x18000cf04`
- `0x180010110`
- `0x180010220`
- `0x180023240`
- `0x1800432f0`
- `0x18004a030`
- `0x18006c2e4`
- `0x18006d038`
- `0x18006e10c`
- `0x18006e148`
- `0x18006e168`
- `0x180120d70`
- `0x18033b5a8`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180120ff3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180120ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180121107`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180120f8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180121107`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180120e77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180120e77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801210d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801210d2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180120fc6`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180120fc6`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x180120eab`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x180120eab`

## string_xrefs

- `0x180120fe7`: `LastUpdatedTime`
- `0x180120ecc`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180120fa2`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180121061`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801210ea`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180121127`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x180121158`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`

## pseudocode

```c

```
