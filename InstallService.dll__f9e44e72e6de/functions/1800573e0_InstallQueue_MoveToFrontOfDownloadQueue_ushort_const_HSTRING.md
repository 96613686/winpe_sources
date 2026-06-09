# InstallQueue::MoveToFrontOfDownloadQueue(ushort const *,HSTRING__ *)

- ea: `0x1800573e0`
- end: `0x1800577dc`
- name: `?MoveToFrontOfDownloadQueue@InstallQueue@@QEAAJPEBGPEAUHSTRING__@@@Z`
- size: `1020`
- prototype: `int(InstallQueue *__hidden this, const unsigned __int16 *, HSTRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180029320`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x18001cce0`
- `0x1800252e8`
- `0x18004d680`
- `0x1800573e0`
- `0x180057fbc`
- `0x180059418`
- `0x18005cf90`
- `0x18005d2ac`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005767c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005767c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800575d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057738`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800575d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057738`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057562`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800576ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057562`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800576ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800574bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800574bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180057475`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180057475`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180057607`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180057607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005741c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005765a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057759`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005741c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005765a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180057759`

## string_xrefs

- `0x18005745a`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180057798`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005744d`: `InstallQueue::MoveToFrontOfDownloadQueue`
- `0x18005778b`: `InstallQueue::MoveToFrontOfDownloadQueue`
- `0x180057526`: `MoveToFrontOfDownloadQueue_Interactive`
- `0x1800576b2`: `MoveToFrontOfDownloadQueue_NonInteractive`
- `0x18005777b`: `MoveDownloadToTop: productId = %s, CV = %s`

## pseudocode

```c

```
