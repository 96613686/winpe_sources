# GetComponentClientState(ushort const *,ushort const *,ushort const *,CAPITempBufferRef<ushort> &,ulong &,iaaAppAssignment *)

- ea: `0x180014288`
- end: `0x180014840`
- name: `?GetComponentClientState@@YA?AW4tagINSTALLSTATE@@PEBG00AEAV?$CAPITempBufferRef@G@@AEAKPEAW4iaaAppAssignment@@@Z`
- size: `1464`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800138e4`
- `0x180014848`
- `0x18001c420`
- `0x180212884`

## callees

- `0x180014288`
- `0x180015950`
- `0x1800159d4`
- `0x180022120`
- `0x1800250d4`
- `0x180071fdc`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800144ca`
- `ADVAPI32!RegQueryValueExW` at `0x1800146c5`
- `ADVAPI32!RegQueryValueExW` at `0x1800144ca`
- `ADVAPI32!RegQueryValueExW` at `0x1800146c5`
- `ADVAPI32!RegCloseKey` at `0x180014407`
- `ADVAPI32!RegCloseKey` at `0x180014588`
- `ADVAPI32!RegCloseKey` at `0x180014407`
- `ADVAPI32!RegCloseKey` at `0x180014588`
- `KERNEL32!InitializeCriticalSection` at `0x1800142f6`
- `KERNEL32!InitializeCriticalSection` at `0x1800142f6`
- `KERNEL32!DeleteCriticalSection` at `0x1800145ac`
- `KERNEL32!DeleteCriticalSection` at `0x1800145ac`
- `KERNEL32!LeaveCriticalSection` at `0x180014420`
- `KERNEL32!LeaveCriticalSection` at `0x1800145a1`
- `KERNEL32!LeaveCriticalSection` at `0x180014420`
- `KERNEL32!LeaveCriticalSection` at `0x1800145a1`
- `KERNEL32!EnterCriticalSection` at `0x1800143f7`
- `KERNEL32!EnterCriticalSection` at `0x180014578`
- `KERNEL32!EnterCriticalSection` at `0x1800143f7`
- `KERNEL32!EnterCriticalSection` at `0x180014578`
- `KERNEL32!GlobalAlloc` at `0x1800146d9`
- `KERNEL32!GlobalAlloc` at `0x1800146d9`
- `KERNEL32!GlobalFree` at `0x18001439d`
- `KERNEL32!GlobalFree` at `0x1800145be`
- `KERNEL32!GlobalFree` at `0x18001472c`
- `KERNEL32!GlobalFree` at `0x1800147f3`
- `KERNEL32!GlobalFree` at `0x180014805`
- `KERNEL32!GlobalFree` at `0x180014814`
- `KERNEL32!GlobalFree` at `0x180014826`
- `KERNEL32!GlobalFree` at `0x180014835`
- `KERNEL32!GlobalFree` at `0x18001439d`
- `KERNEL32!GlobalFree` at `0x1800145be`
- `KERNEL32!GlobalFree` at `0x18001472c`
- `KERNEL32!GlobalFree` at `0x1800147f3`
- `KERNEL32!GlobalFree` at `0x180014805`
- `KERNEL32!GlobalFree` at `0x180014814`
- `KERNEL32!GlobalFree` at `0x180014826`
- `KERNEL32!GlobalFree` at `0x180014835`

## string_xrefs

- `0x1800143b2`: `Components`
- `0x180014375`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
