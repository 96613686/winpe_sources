# GenerateCimFromContainer(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong,TurboContainerLoader *,TurboStackLoader *)

- ea: `0x18021c4a4`
- end: `0x18021dd47`
- name: `?GenerateCimFromContainer@@YAJAEBV?$basic_zstring_view@_W@wil@@000KPEAVTurboContainerLoader@@PEAVTurboStackLoader@@@Z`
- size: `6307`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18021e3a8`

## callees

- `0x1800059d0`
- `0x180005cf0`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18000d2fc`
- `0x180012ca0`
- `0x180012d94`
- `0x1800143a4`
- `0x1800152f4`
- `0x180020360`
- `0x180023384`
- `0x180023ab0`
- `0x180023b20`
- `0x18008b360`
- `0x18008b38c`
- `0x18009b860`
- `0x18009bcc8`
- `0x1800a57c0`
- `0x1801dd538`
- `0x1801dd86c`
- `0x1801de458`
- `0x1801def30`
- `0x1801e1000`
- `0x1801e4b84`
- `0x1801efdc0`
- `0x1801f8f3c`
- `0x18021888c`
- `0x180218cd0`
- `0x180219028`
- `0x18021c4a4`
- `0x180220914`
- `0x180226b0c`
- `0x1802534c0`
- `0x180253a04`
- `0x180254354`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18021ca52`
- `ntdll!RtlRaiseStatus` at `0x18021ca98`
- `ntdll!RtlRaiseStatus` at `0x18021cbb9`
- `ntdll!RtlRaiseStatus` at `0x18021ca52`
- `ntdll!RtlRaiseStatus` at `0x18021ca98`
- `ntdll!RtlRaiseStatus` at `0x18021cbb9`
- `ntdll!RtlLeaveCriticalSection` at `0x18021ca37`
- `ntdll!RtlLeaveCriticalSection` at `0x18021ca7d`
- `ntdll!RtlLeaveCriticalSection` at `0x18021cb0b`
- `ntdll!RtlLeaveCriticalSection` at `0x18021ca37`
- `ntdll!RtlLeaveCriticalSection` at `0x18021ca7d`
- `ntdll!RtlLeaveCriticalSection` at `0x18021cb0b`
- `ntdll!RtlEnterCriticalSection` at `0x18021c9ca`
- `ntdll!RtlEnterCriticalSection` at `0x18021c9ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d51a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d5ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d7e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021db23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021dc33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d51a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d5ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d7e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021d976`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021db23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18021dc33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d52e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d601`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d7f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d98a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021db37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021dc47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d52e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d601`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d7f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021d98a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021db37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18021dc47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021c7a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021c835`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021cb9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021d6ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021d8a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021c7a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021c835`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021cb9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021d6ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18021d8a5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18021dac5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18021dac5`

## string_xrefs

- `0x18021c695`: `update.mum`
- `0x18021c880`: `update.mum`
- `0x18021d770`: `Failed to create cim file {}`
- `0x18021cc16`: `Failed comparing supplied identity {} to found identity {}`

## pseudocode

```c

```
