# CProcessStateManager::UpdateLockScreenState(bool,bool,Windows::Internal::UI::Logon::Controller::LockActivity)

- ea: `0x1800117c4`
- end: `0x180011a69`
- name: `?UpdateLockScreenState@CProcessStateManager@@QEAAJ_N0W4LockActivity@Controller@Logon@UI@Internal@Windows@@@Z`
- size: `677`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180019520`
- `0x18005e2b8`

## callees

- `0x18000e840`
- `0x18000f730`
- `0x18000fff0`
- `0x180010348`
- `0x1800117c4`
- `0x18005d488`
- `0x180062064`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x180011865`
- `KERNEL32!ReleaseSRWLockShared` at `0x180011865`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800119b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011a01`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800119b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011a01`
- `KERNEL32!AcquireSRWLockShared` at `0x180011830`
- `KERNEL32!AcquireSRWLockShared` at `0x180011830`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800117f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800119df`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800117f0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800119df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011848`
- `ntdll!NtQueryWnfStateData` at `0x1800118ea`
- `ntdll!NtQueryWnfStateData` at `0x1800118ea`

## pseudocode

```c

```
