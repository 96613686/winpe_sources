# DllGetActivationFactory

- ea: `0x180002870`
- end: `0x180002b76`
- name: `DllGetActivationFactory`
- size: `774`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002870`
- `0x18001a540`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800028a9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800028a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002b0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002b0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002a86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002a86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002a09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002b01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002a09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002b01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800029c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800029c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800028f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800028f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800028c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800028c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800028da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800028da`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800029d9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002adb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800029d9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002adb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180002aa0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180002aa0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002b1f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002b1f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002b65`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002b65`

## string_xrefs

- `0x180002b30`: `activatibleClassId`

## pseudocode

```c

```
