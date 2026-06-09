# PITR::GetSettingsInterface(PITR::IPITRBase *,PITR::IPITRSettings * *)

- ea: `0x140075ef4`
- end: `0x14007619e`
- name: `?GetSettingsInterface@PITR@@YAJPEAUIPITRBase@1@PEAPEAUIPITRSettings@1@@Z`
- size: `682`
- prototype: `__int64 __fastcall(PITR *__hidden this, struct PITR::IPITRBase *, struct PITR::IPITRSettings **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400752bc`

## callees

- `0x14007528c`
- `0x140075ef4`
- `0x1400761a4`
- `0x1400761e4`
- `0x14007640c`
- `0x140076544`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140075f11`
- `KERNEL32!GetTickCount` at `0x140076153`
- `KERNEL32!GetTickCount` at `0x140076171`
- `KERNEL32!GetTickCount` at `0x140075f11`
- `KERNEL32!GetTickCount` at `0x140076153`
- `KERNEL32!GetTickCount` at `0x140076171`
- `KERNEL32!LeaveCriticalSection` at `0x140076167`
- `KERNEL32!LeaveCriticalSection` at `0x140076167`
- `KERNEL32!EnterCriticalSection` at `0x140075f36`
- `KERNEL32!EnterCriticalSection` at `0x140075f36`
- `KERNEL32!GetProcAddress` at `0x140076007`
- `KERNEL32!GetProcAddress` at `0x140076007`
- `KERNEL32!GetLastError` at `0x140075f6b`
- `KERNEL32!GetLastError` at `0x140076019`
- `KERNEL32!GetLastError` at `0x140076031`
- `KERNEL32!GetLastError` at `0x140076049`
- `KERNEL32!GetLastError` at `0x1400760df`
- `KERNEL32!GetLastError` at `0x140075f6b`
- `KERNEL32!GetLastError` at `0x140076019`
- `KERNEL32!GetLastError` at `0x140076031`
- `KERNEL32!GetLastError` at `0x140076049`
- `KERNEL32!GetLastError` at `0x1400760df`
- `WDSCORE!WdsSetupLogMessageW` at `0x140075fd6`
- `WDSCORE!WdsSetupLogMessageW` at `0x14007614d`
- `WDSCORE!WdsSetupLogMessageW` at `0x140075fd6`
- `WDSCORE!WdsSetupLogMessageW` at `0x14007614d`
- `WDSCORE!CurrentIP` at `0x140075f73`
- `WDSCORE!CurrentIP` at `0x140076051`
- `WDSCORE!CurrentIP` at `0x1400760e7`
- `WDSCORE!CurrentIP` at `0x140075f73`
- `WDSCORE!CurrentIP` at `0x140076051`
- `WDSCORE!CurrentIP` at `0x1400760e7`

## string_xrefs

- `0x140075f79`: `PITR::GetSettingsInterface: Failed to find loaded PITR DLL`

## pseudocode

```c

```
