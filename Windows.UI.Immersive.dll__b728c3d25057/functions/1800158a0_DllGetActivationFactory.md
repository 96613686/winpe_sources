# DllGetActivationFactory

- ea: `0x1800158a0`
- end: `0x180015bc5`
- name: `DllGetActivationFactory`
- size: `805`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800158a0`
- `0x180050ba0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800158d6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800158d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015a03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015a03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015a49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015a49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015b09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015b09`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180015a19`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180015b4a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180015a19`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180015b4a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180015b23`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180015b23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800158f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800158f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180015907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180015907`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015ab2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015ab2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015b8e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015b8e`

## string_xrefs

- `0x180015a7d`: `activatibleClassId`

## pseudocode

```c

```
