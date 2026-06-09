# CLogonController::_EnsureSystemCredentialManager(Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential * *)

- ea: `0x180044558`
- end: `0x1800446b4`
- name: `?_EnsureSystemCredentialManager@CLogonController@@AEAAJPEAPEAUISystemManagedAccountCredential@Logon@SystemManagedAccount@Internal@Windows@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180017400`
- `0x180021730`
- `0x18007c2e4`

## callees

- `0x180044558`
- `0x18005d488`
- `0x180061470`
- `0x1800661c8`
- `0x18006c000`
- `0x18009d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180044662`
- `KERNEL32!RaiseException` at `0x180044662`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800445af`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800446a7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800445af`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800446a7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004458b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18004458b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044611`

## pseudocode

```c

```
