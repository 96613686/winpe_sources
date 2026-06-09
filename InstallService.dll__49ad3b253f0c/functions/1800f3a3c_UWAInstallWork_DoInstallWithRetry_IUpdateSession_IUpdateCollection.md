# UWAInstallWork::_DoInstallWithRetry(IUpdateSession *,IUpdateCollection *)

- ea: `0x1800f3a3c`
- end: `0x1800f4165`
- name: `?_DoInstallWithRetry@UWAInstallWork@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z`
- size: `1833`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, struct IUpdateSession *, struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5020`

## callees

- `0x180009ea0`
- `0x1800116f4`
- `0x180012368`
- `0x180012394`
- `0x1800123f8`
- `0x180012428`
- `0x1800127c8`
- `0x18003e5f8`
- `0x18003f884`
- `0x180040498`
- `0x180044bc0`
- `0x180044c3c`
- `0x180046110`
- `0x1800e25c0`
- `0x1800e4208`
- `0x1800e46f4`
- `0x1800e4d48`
- `0x1800e5028`
- `0x1800e9440`
- `0x1800f3a3c`
- `0x1800f416c`
- `0x1800fa4c0`
- `0x1800fb908`
- `0x1800fd508`
- `0x1800fe6dc`
- `0x1800ff408`
- `0x1800ff460`
- `0x1801131e0`
- `0x180114564`
- `0x180117fc0`
- `0x180149adc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f3c53`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f3c53`
- `msvcp_win!_Xtime_get_ticks` at `0x1800f3b9c`
- `msvcp_win!_Xtime_get_ticks` at `0x1800f3b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f410b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3e03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f3ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f40fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f410b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3f64`

## string_xrefs

- `0x1800f3c96`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f3d89`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f4032`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f4129`: `StoreAgentInstallFailure1`
- `0x1800f4014`: `Install failed, triggering fallback to direct download`
- `0x1800f3c89`: `UWAInstallWork::_DoInstallWithRetry`
- `0x1800f3d82`: `UWAInstallWork::_DoInstallWithRetry`
- `0x1800f4025`: `UWAInstallWork::_DoInstallWithRetry`
- `0x1800f3da4`: `Immediate Retry Install Succeeded`
- `0x1800f3c79`: `Immediate Retry Install for Error`
- `0x1800f3e63`: `Immediate Retry Install failed`

## pseudocode

```c

```
