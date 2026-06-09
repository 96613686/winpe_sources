# WamObjectStoreImplementation::SetEntry(IUnknown *,HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IBuffer *)

- ea: `0x180008130`
- end: `0x1800086b6`
- name: `?SetEntry@WamObjectStoreImplementation@@QEAAJPEAUIUnknown@@PEAUHSTRING__@@1PEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `1414`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, struct IUnknown *, HSTRING, HSTRING, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007770`

## callees

- `0x1800077e0`
- `0x18000794c`
- `0x180007cec`
- `0x180008030`
- `0x180008130`
- `0x180009e80`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001a510`
- `0x18001ffdc`
- `0x18007ad10`
- `0x18008e690`
- `0x18009a6fc`
- `0x18009a8a0`
- `0x1800d71d0`
- `0x1800d81d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008227`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008227`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008549`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000858b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008647`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008549`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000858b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008647`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800085f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800081c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800081c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800081a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800081a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800083c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000849b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800083c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000849b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008502`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008578`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008502`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008578`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800085f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083f2`

## string_xrefs

- `0x18000852b`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000859d`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000860d`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x18000862d`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`
- `0x180008681`: `onecore\ds\security\tokenbroker\broker\lib\wamobjectstore.cpp`

## pseudocode

```c

```
