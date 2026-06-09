# CLogonController::_EnsureLockHost(void)

- ea: `0x18001a324`
- end: `0x18001a4c4`
- name: `?_EnsureLockHost@CLogonController@@AEAAJXZ`
- size: `416`
- prototype: `__int64 __fastcall(CLogonController *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180019520`
- `0x18005a4a0`
- `0x18005e2b8`

## callees

- `0x18000df10`
- `0x18001a324`
- `0x180044f68`
- `0x18004ad98`
- `0x18005d488`
- `0x180061470`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18001a391`
- `KERNEL32!RaiseException` at `0x18001a391`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a43b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a47c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a43b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a47c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a350`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a37c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a37c`

## pseudocode

```c

```
