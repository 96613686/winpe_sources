# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x1802414e8`
- end: `0x180241843`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x180240ee0`

## callees

- `0x180240e8c`
- `0x1802414e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241546`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241734`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802417bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802417fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241546`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180241734`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802417bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802417fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802415c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024160f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802416a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180241715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024179c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802415c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024160f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802416a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180241715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024179c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024178b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024178b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024155f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18024155f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1802415fa`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1802415fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180241666`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180241700`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180241666`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180241700`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180241768`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180241768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024161f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802416b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024177a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024161f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802416b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241725`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024177a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802415af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802415af`

## string_xrefs

- `0x180241761`: `SymbolicLinkValue`

## pseudocode

```c

```
