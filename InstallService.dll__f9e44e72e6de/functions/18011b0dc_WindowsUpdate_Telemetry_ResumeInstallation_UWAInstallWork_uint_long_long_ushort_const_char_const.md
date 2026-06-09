# WindowsUpdate::Telemetry::ResumeInstallation(UWAInstallWork *,uint,long,long,ushort const *,char const *)

- ea: `0x18011b0dc`
- end: `0x18011b7f1`
- name: `?ResumeInstallation@Telemetry@WindowsUpdate@@YAXPEAVUWAInstallWork@@IJJPEBGPEBD@Z`
- size: `1813`
- prototype: `void __usercall(WindowsUpdate::Telemetry *__hidden this@<rcx>, struct UWAInstallWork *@<rdx>, unsigned int@<r8d>, int@<r9d>, int, const unsigned __int16 *, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ec640`

## callees

- `0x180001b88`
- `0x1800049fc`
- `0x180009ea0`
- `0x180020868`
- `0x180022298`
- `0x180042b9c`
- `0x1800e7f50`
- `0x180107a28`
- `0x18011317c`
- `0x18011b0dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b17c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b18f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b1c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b4a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b5f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b17c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b18f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b1c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b422`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b4a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011b5f8`

## string_xrefs

- `0x18011b4f7`: `AttemptNumber`
- `0x18011b4d5`: `UserAttemptNumber`
- `0x18011b4e9`: `SystemAttemptNumber`
- `0x18011b575`: `IsUpdate`
- `0x18011b65c`: `onecoreuap\enduser\winstore\installservice\lib\telemetry.cpp`
- `0x18011b3f0`: `PreviousInstallState`
- `0x18011b62f`: `ResumeInstallation`
- `0x18011b648`: `WindowsUpdate::Telemetry::ResumeInstallation`

## pseudocode

```c

```
