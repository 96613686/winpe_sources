# Windows::Compat::AvTracking::DailyUpdateAvStatus(ulong,bool)

- ea: `0x1800263dc`
- end: `0x180026782`
- name: `?DailyUpdateAvStatus@AvTracking@Compat@Windows@@YAJK_N@Z`
- size: `934`
- prototype: `__int64 __fastcall(Windows::Compat::AvTracking *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015490`
- `0x180046708`

## callees

- `0x18001a2f4`
- `0x1800261bc`
- `0x18002630c`
- `0x1800263dc`
- `0x18002690c`
- `0x180026b58`
- `0x180027058`
- `0x1800270e0`
- `0x180027260`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002640f`
- `KERNEL32!GetProcessHeap` at `0x180026652`
- `KERNEL32!GetProcessHeap` at `0x1800266cd`
- `KERNEL32!GetProcessHeap` at `0x18002640f`
- `KERNEL32!GetProcessHeap` at `0x180026652`
- `KERNEL32!GetProcessHeap` at `0x1800266cd`
- `KERNEL32!HeapFree` at `0x180026660`
- `KERNEL32!HeapFree` at `0x1800266db`
- `KERNEL32!HeapFree` at `0x18002671c`
- `KERNEL32!HeapFree` at `0x180026660`
- `KERNEL32!HeapFree` at `0x1800266db`
- `KERNEL32!HeapFree` at `0x18002671c`
- `OLE32!CoUninitialize` at `0x1800265f9`
- `OLE32!CoUninitialize` at `0x1800265f9`
- `OLE32!CoInitializeEx` at `0x18002644b`
- `OLE32!CoInitializeEx` at `0x18002644b`

## string_xrefs

- `0x1800264d4`: `Failed to clear registry keys: [0x%x].`
- `0x180026481`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\AvTracking\ExpiredExe`
- `0x18002649b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\AvTracking\ExpiredExeUnconditional`
- `0x1800264cd`: `Windows::Compat::AvTracking::CleanRegistryKeys`
- `0x1800264b5`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\WicaAvPathsExpiredTemp`
- `0x180026468`: `Windows::Compat::AvTracking::DailyUpdateAvStatus`
- `0x1800264fa`: `Windows::Compat::AvTracking::DailyUpdateAvStatus`
- `0x18002653d`: `Windows::Compat::AvTracking::DailyUpdateAvStatus`
- `0x180026768`: `Windows::Compat::AvTracking::DailyUpdateAvStatus`
- `0x1800264ed`: `Failed to clean registry: [0x%x].`
- `0x180026757`: `Failed to update history : [0x%x].`
- `0x180026739`: `Failed to write Registry keys: [0x%x].`

## pseudocode

```c

```
