# CUsnMonitorNotifier::Thread(void)

- ea: `0x18006081c`
- end: `0x1800614a6`
- name: `?Thread@CUsnMonitorNotifier@@AEAAJXZ`
- size: `3210`
- prototype: `__int64 __fastcall(CUsnMonitorNotifier *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: ``

## callers

- `0x18021b9c0`

## callees

- `0x18000bf8c`
- `0x18000ee60`
- `0x18000f880`
- `0x180013d40`
- `0x180014ff0`
- `0x180019bb0`
- `0x18002751c`
- `0x18004e5d8`
- `0x180052460`
- `0x18006028c`
- `0x1800604a0`
- `0x18006081c`
- `0x1800614ac`
- `0x180061f78`
- `0x18006a618`
- `0x180079d34`
- `0x18009ba64`
- `0x1800bb804`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800cf768`
- `0x18010859c`
- `0x1801244c0`
- `0x1801244f0`
- `0x1801249b0`
- `0x1801249ec`
- `0x18021af5c`
- `0x18021b35c`
- `0x18021bd38`
- `0x18021c274`
- `0x18021c2f8`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800613bd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800613bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060bd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060bd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180060b36`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061279`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180060b36`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180061279`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180060b0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180060df2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180060b0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180060df2`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180060bc8`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180060bc8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060ba5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060d2b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060ba5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180060d2b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800609ef`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800609ef`

## string_xrefs

- `0x180060a05`: `[SrchGatherDirMon] Exit USN Monitor Thread Signal Received`
- `0x180060b28`: `CUsnMonitorNotifier - delay reading USN journal for %d ms`
- `0x180060fb3`: `[SrchGatherDirMon] USN Thread: WaitForMultObj list fell out of sync with volume list`
- `0x1800611a2`: `[SrchGatherDirMon] USN Event - Cannot read USN data - DeviceIoControl failed with 0x%x`
- `0x180060a3a`: `[SrchGatherDirMon] USN Monitoring Thread stopping`
- `0x18006084c`: `[SrchGatherDirMon] USN Monitoring Thread starting`
- `0x180061391`: `[SrchGatherDirMon] New volume being added or existing volume removed`
- `0x1800613df`: `CUsnMonitorNotifier - USNBatching Disabled - read journal records without waiting for the next read time`

## pseudocode

```c

```
