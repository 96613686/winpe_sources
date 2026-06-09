# Execution::BmHostInfoManager::ReleaseHostForApplication(void *,ushort const *)

- ea: `0x18008c244`
- end: `0x18008c330`
- name: `?ReleaseHostForApplication@BmHostInfoManager@Execution@@QEAAJPEAXPEBG@Z`
- size: `236`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, void *, LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008ab60`

## callees

- `0x18001d824`
- `0x18001ef7c`
- `0x180020788`
- `0x180020cc0`
- `0x18004a158`
- `0x18008c244`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008c264`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008c264`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008c30e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008c30e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c2c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c2c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008c2e1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008c2e1`

## pseudocode

```c

```
