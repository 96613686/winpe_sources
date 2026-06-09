# Execution::BmHostInfoManager::RemoveHostForPackage(void *,ushort const *)

- ea: `0x18004a040`
- end: `0x18004a14f`
- name: `?RemoveHostForPackage@BmHostInfoManager@Execution@@QEAAJPEAXPEBG@Z`
- size: `271`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, void *, LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180066ec0`

## callees

- `0x180020cc0`
- `0x18004a040`
- `0x18004a158`
- `0x18004a188`
- `0x18004f99c`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a06e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a06e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a0ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a0ad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a0d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a0d7`

## pseudocode

```c

```
