# OpenInstalledProductInstallPropertiesKeyPacked(ushort const *,ushort const *,CRegHandle &,bool)

- ea: `0x1800204ec`
- end: `0x18002092d`
- name: `?OpenInstalledProductInstallPropertiesKeyPacked@@YAKPEBG0AEAVCRegHandle@@_N@Z`
- size: `1089`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct CRegHandle *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800eab40`
- `0x180191114`

## callees

- `0x180013fe4`
- `0x1800204ec`
- `0x180022120`
- `0x1800250d4`
- `0x1800561c0`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180020632`
- `ADVAPI32!RegCloseKey` at `0x18002070b`
- `ADVAPI32!RegCloseKey` at `0x180020632`
- `ADVAPI32!RegCloseKey` at `0x18002070b`
- `KERNEL32!LeaveCriticalSection` at `0x18002064b`
- `KERNEL32!LeaveCriticalSection` at `0x180020724`
- `KERNEL32!LeaveCriticalSection` at `0x18002064b`
- `KERNEL32!LeaveCriticalSection` at `0x180020724`
- `KERNEL32!EnterCriticalSection` at `0x180020624`
- `KERNEL32!EnterCriticalSection` at `0x1800206fd`
- `KERNEL32!EnterCriticalSection` at `0x180020624`
- `KERNEL32!EnterCriticalSection` at `0x1800206fd`
- `KERNEL32!GlobalFree` at `0x1800206d4`
- `KERNEL32!GlobalFree` at `0x180020826`
- `KERNEL32!GlobalFree` at `0x1800208b2`
- `KERNEL32!GlobalFree` at `0x1800208f8`
- `KERNEL32!GlobalFree` at `0x180020904`
- `KERNEL32!GlobalFree` at `0x180020913`
- `KERNEL32!GlobalFree` at `0x180020922`
- `KERNEL32!GlobalFree` at `0x1800206d4`
- `KERNEL32!GlobalFree` at `0x180020826`
- `KERNEL32!GlobalFree` at `0x1800208b2`
- `KERNEL32!GlobalFree` at `0x1800208f8`
- `KERNEL32!GlobalFree` at `0x180020904`
- `KERNEL32!GlobalFree` at `0x180020913`
- `KERNEL32!GlobalFree` at `0x180020922`

## string_xrefs

- `0x1800205a2`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800207f8`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x18002052d`: `InstallProperties`

## pseudocode

```c

```
