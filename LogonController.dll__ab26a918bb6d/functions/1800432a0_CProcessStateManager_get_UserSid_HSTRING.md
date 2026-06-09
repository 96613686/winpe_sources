# CProcessStateManager::get_UserSid(HSTRING__ * *)

- ea: `0x1800432a0`
- end: `0x180043332`
- name: `?get_UserSid@CProcessStateManager@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `146`
- prototype: `int(CProcessStateManager *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800432a0`
- `0x18005d488`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x1800432ef`
- `KERNEL32!ReleaseSRWLockShared` at `0x180043328`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800432ef`
- `KERNEL32!ReleaseSRWLockShared` at `0x180043328`
- `KERNEL32!AcquireSRWLockShared` at `0x1800432c6`
- `KERNEL32!AcquireSRWLockShared` at `0x1800432c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800432db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800432db`

## pseudocode

```c

```
