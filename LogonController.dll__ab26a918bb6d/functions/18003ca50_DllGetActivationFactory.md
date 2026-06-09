# DllGetActivationFactory

- ea: `0x18003ca50`
- end: `0x18003cd49`
- name: `DllGetActivationFactory`
- size: `761`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003ca50`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18003ca8b`
- `KERNEL32!InitOnceExecuteOnce` at `0x18003ca8b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003ccec`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003cd18`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003ccec`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003cd18`
- `KERNEL32!EncodePointer` at `0x18003cc3c`
- `KERNEL32!EncodePointer` at `0x18003cc3c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003cc82`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003cc82`
- `KERNEL32!DecodePointer` at `0x18003cc65`
- `KERNEL32!DecodePointer` at `0x18003ccb9`
- `KERNEL32!DecodePointer` at `0x18003cc65`
- `KERNEL32!DecodePointer` at `0x18003ccb9`
- `KERNEL32!AcquireSRWLockShared` at `0x18003cca7`
- `KERNEL32!AcquireSRWLockShared` at `0x18003cca7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003cc24`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003cc24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003cabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003cabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003caa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003caa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cadb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cadb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003cb8c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003cb8c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003cd01`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003cd01`

## string_xrefs

- `0x18003cb59`: `activatibleClassId`

## pseudocode

```c

```
