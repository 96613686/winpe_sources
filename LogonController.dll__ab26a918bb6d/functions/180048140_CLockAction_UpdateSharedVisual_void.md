# CLockAction::UpdateSharedVisual(void *)

- ea: `0x180048140`
- end: `0x180048231`
- name: `?UpdateSharedVisual@CLockAction@@UEAAJPEAX@Z`
- size: `241`
- prototype: `int(CLockAction *__hidden this, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001def0`
- `0x180048140`
- `0x18008b294`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1800481a2`
- `KERNEL32!DuplicateHandle` at `0x1800481a2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180048201`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180048201`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180048162`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180048162`
- `KERNEL32!CloseHandle` at `0x1800481db`
- `KERNEL32!CloseHandle` at `0x1800481db`
- `KERNEL32!GetLastError` at `0x1800481ac`
- `KERNEL32!GetLastError` at `0x1800481ac`
- `KERNEL32!GetCurrentProcess` at `0x180048171`
- `KERNEL32!GetCurrentProcess` at `0x180048171`

## pseudocode

```c

```
