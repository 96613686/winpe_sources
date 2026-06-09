# CRegUtilT<unsigned __int64,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 *)

- ea: `0x1800678b0`
- end: `0x180067a7f`
- name: `?GetValue@?$CRegUtilT@_KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEA_K@Z`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18003c960`
- `0x180064610`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x1800678b0`
- `0x180077664`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800678ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800678ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006797d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006797d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800679a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067a2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800679a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067a2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067a43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067a43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800679b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800679b5`

## string_xrefs

- `0x18006796e`: `InstallTime`

## pseudocode

```c

```
