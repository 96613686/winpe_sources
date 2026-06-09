# CLogonController::_IsSystemManagedAutologonSet(bool *)

- ea: `0x180023f60`
- end: `0x18002427b`
- name: `?_IsSystemManagedAutologonSet@CLogonController@@AEAAJPEA_N@Z`
- size: `795`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, bool *)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180020948`
- `0x180023c60`
- `0x180024320`
- `0x180024690`
- `0x18005e2b8`
- `0x1800752b0`

## callees

- `0x18000df10`
- `0x180023f60`
- `0x18005d488`
- `0x180061470`
- `0x1800661c8`
- `0x18006c000`
- `0x180073500`
- `0x18009d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18002413a`
- `KERNEL32!RaiseException` at `0x18002413a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180024080`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800241c1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180024080`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800241c1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002405c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002405c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800240e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800240e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023ffd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023ffd`

## pseudocode

```c

```
