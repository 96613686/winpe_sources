# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x18039f6f4`
- end: `0x18039fa4f`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x18039f0ec`

## callees

- `0x18039f098`
- `0x18039f6f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f752`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f940`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f9cb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039fa08`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f752`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f940`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039f9cb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18039fa08`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18039f76b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18039f76b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18039f997`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18039f997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039f77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039f77f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f7d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f81b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f8b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f9a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f7d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f81b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f8b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039f9a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18039f974`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18039f974`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18039f806`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18039f806`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18039f872`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18039f90c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18039f872`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18039f90c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f82b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f8c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f931`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f82b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f8c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f931`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039f986`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18039f7bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18039f7bb`

## string_xrefs

- `0x18039f96d`: `SymbolicLinkValue`

## pseudocode

```c

```
