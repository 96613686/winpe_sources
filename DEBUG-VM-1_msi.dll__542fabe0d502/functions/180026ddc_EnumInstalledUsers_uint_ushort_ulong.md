# EnumInstalledUsers(uint,ushort *,ulong)

- ea: `0x180026ddc`
- end: `0x180026ff3`
- name: `?EnumInstalledUsers@@YAKIPEAGK@Z`
- size: `535`
- prototype: `unsigned int __fastcall(DWORD dwIndex, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026c34`

## callees

- `0x180015950`
- `0x180025560`
- `0x180026ddc`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180026f40`
- `ADVAPI32!RegEnumKeyExW` at `0x180026f40`
- `ADVAPI32!RegCloseKey` at `0x180026e53`
- `ADVAPI32!RegCloseKey` at `0x180026e53`
- `KERNEL32!InitializeCriticalSection` at `0x180026e38`
- `KERNEL32!InitializeCriticalSection` at `0x180026e38`
- `KERNEL32!LeaveCriticalSection` at `0x180026e71`
- `KERNEL32!LeaveCriticalSection` at `0x180026e71`
- `KERNEL32!EnterCriticalSection` at `0x180026e43`
- `KERNEL32!EnterCriticalSection` at `0x180026e43`
- `KERNEL32!GlobalFree` at `0x180026f87`
- `KERNEL32!GlobalFree` at `0x180026fd0`
- `KERNEL32!GlobalFree` at `0x180026fdc`
- `KERNEL32!GlobalFree` at `0x180026fe8`
- `KERNEL32!GlobalFree` at `0x180026f87`
- `KERNEL32!GlobalFree` at `0x180026fd0`
- `KERNEL32!GlobalFree` at `0x180026fdc`
- `KERNEL32!GlobalFree` at `0x180026fe8`

## string_xrefs

- `0x180026e98`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
