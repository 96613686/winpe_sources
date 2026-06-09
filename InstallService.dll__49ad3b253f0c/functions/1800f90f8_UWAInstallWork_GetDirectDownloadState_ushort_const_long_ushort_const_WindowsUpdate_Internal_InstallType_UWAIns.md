# UWAInstallWork::_GetDirectDownloadState(ushort const *,long,ushort const *,WindowsUpdate::Internal::InstallType,UWAInstallWork::ErrorStage)

- ea: `0x1800f90f8`
- end: `0x1800f95f5`
- name: `?_GetDirectDownloadState@UWAInstallWork@@AEAA?AW4DirectDownloadEnablementState@@PEBGJ0W4InstallType@Internal@WindowsUpdate@@W4ErrorStage@1@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, installer_update`

## callers

- `0x1800e5fc0`
- `0x1800fb908`

## callees

- `0x180009ea0`
- `0x18000ad9c`
- `0x180012394`
- `0x180012428`
- `0x1800127c8`
- `0x18001c108`
- `0x18001c414`
- `0x18001c964`
- `0x18003d9a8`
- `0x18003da40`
- `0x18003da90`
- `0x180044a90`
- `0x18006d154`
- `0x18006d6e8`
- `0x18006d840`
- `0x1800f90f8`
- `0x1800f95fc`
- `0x1800f9cb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f91cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f92f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f945a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f958f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f95b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f91cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f92f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f945a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f9501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f958f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f95b5`

## string_xrefs

- `0x1800f91a0`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f9352`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f9234`: `Install`
- `0x1800f9173`: `DirectDownloadState determined: Disabled (InstallForAllUsers flag is set and is not supported for direct workflow)`
- `0x1800f932f`: `DirectDownloadState check parameters: clientId=%s, hresult=%s, product=%s, region=%s, arch=%s, installType=%s, errorStage=%s`
- `0x1800f9191`: `UWAInstallWork::_GetDirectDownloadState`
- `0x1800f9342`: `UWAInstallWork::_GetDirectDownloadState`
- `0x1800f91d8`: `DirectDownloadState determined: Disabled (from cached state)`

## pseudocode

```c

```
