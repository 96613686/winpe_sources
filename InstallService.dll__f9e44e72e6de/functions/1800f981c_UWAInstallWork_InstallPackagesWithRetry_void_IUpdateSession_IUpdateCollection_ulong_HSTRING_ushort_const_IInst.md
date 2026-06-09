# UWAInstallWork::_InstallPackagesWithRetry(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IInstallationProgressChangedCallback *,IInstallationCompletedCallback *,char const *,IUpdateInstaller * *,IInstallationJob * *)

- ea: `0x1800f981c`
- end: `0x1800f9cad`
- name: `?_InstallPackagesWithRetry@UWAInstallWork@@AEAAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIInstallationProgressChangedCallback@@PEAUIInstallationCompletedCallback@@PEBDPEAPEAUIUpdateInstaller@@PEAPEAUIInstallationJob@@@Z`
- size: `1169`
- prototype: `int(UWAInstallWork *__hidden this, void *, struct IUpdateSession *, struct IUpdateCollection *, unsigned int, HSTRING, const unsigned __int16 *, struct IInstallationProgressChangedCallback *, struct IInstallationCompletedCallback *, const char *, struct IUpdateInstaller **, struct IInstallationJob **)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1ff0`
- `0x1800f29b4`

## callees

- `0x1800116f4`
- `0x1800127c8`
- `0x18003e5f8`
- `0x180040498`
- `0x180044c3c`
- `0x180046110`
- `0x180075608`
- `0x1800e25c0`
- `0x1800e4208`
- `0x1800e46f4`
- `0x1800e4d48`
- `0x1800e5028`
- `0x1800f981c`
- `0x1800fd508`
- `0x1800fe6dc`
- `0x1800ff408`
- `0x180149adc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f990f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f990f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f991e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f996a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f997c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f998e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9af9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9baf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f991e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f996a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f997c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f998e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9af9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f9c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f9c3b`

## string_xrefs

- `0x1800f9953`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f9a70`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f9a8c`: `Immediate Retry Install Succeeded`
- `0x1800f9935`: `Immediate Retry Install for Error`
- `0x1800f9946`: `UWAInstallWork::_InstallPackagesWithRetry`
- `0x1800f9a69`: `UWAInstallWork::_InstallPackagesWithRetry`
- `0x1800f9b44`: `Immediate Retry Install failed`

## pseudocode

```c

```
