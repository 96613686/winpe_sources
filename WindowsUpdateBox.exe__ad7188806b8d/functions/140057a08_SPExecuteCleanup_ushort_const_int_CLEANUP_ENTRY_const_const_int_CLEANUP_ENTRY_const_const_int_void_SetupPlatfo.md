# SPExecuteCleanup(ushort const *,int,CLEANUP_ENTRY const * const,int,CLEANUP_ENTRY const * const,int,void *,SetupPlatform::IGenericProgress *)

- ea: `0x140057a08`
- end: `0x14005840a`
- name: `?SPExecuteCleanup@@YAJPEBGHQEBUCLEANUP_ENTRY@@H1HPEAXPEAUIGenericProgress@SetupPlatform@@@Z`
- size: `2562`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, int@<edx>, const struct CLEANUP_ENTRY *const@<r8>, int@<r9d>, const struct CLEANUP_ENTRY *const, int, void *, struct SetupPlatform::IGenericProgress *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1400570e0`

## callees

- `0x140021d5c`
- `0x140023dcc`
- `0x140024510`
- `0x1400245e4`
- `0x140026104`
- `0x140026684`
- `0x140055c70`
- `0x140055d10`
- `0x140055ef8`
- `0x140056328`
- `0x140057a08`
- `0x140058410`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140057b29`
- `KERNEL32!HeapFree` at `0x140057bfc`
- `KERNEL32!HeapFree` at `0x140057d4f`
- `KERNEL32!HeapFree` at `0x140057e29`
- `KERNEL32!HeapFree` at `0x140057b29`
- `KERNEL32!HeapFree` at `0x140057bfc`
- `KERNEL32!HeapFree` at `0x140057d4f`
- `KERNEL32!HeapFree` at `0x140057e29`
- `KERNEL32!GetProcessHeap` at `0x140057b11`
- `KERNEL32!GetProcessHeap` at `0x140057be8`
- `KERNEL32!GetProcessHeap` at `0x140057d3b`
- `KERNEL32!GetProcessHeap` at `0x140057e15`
- `KERNEL32!GetProcessHeap` at `0x140057b11`
- `KERNEL32!GetProcessHeap` at `0x140057be8`
- `KERNEL32!GetProcessHeap` at `0x140057d3b`
- `KERNEL32!GetProcessHeap` at `0x140057e15`
- `KERNEL32!GetLastError` at `0x140057c85`
- `KERNEL32!GetLastError` at `0x140057d65`
- `KERNEL32!GetLastError` at `0x140057ec1`
- `KERNEL32!GetLastError` at `0x140057ed9`
- `KERNEL32!GetLastError` at `0x140057fef`
- `KERNEL32!GetLastError` at `0x1400580a8`
- `KERNEL32!GetLastError` at `0x1400580c3`
- `KERNEL32!GetLastError` at `0x1400581d1`
- `KERNEL32!GetLastError` at `0x140058272`
- `KERNEL32!GetLastError` at `0x14005828d`
- `KERNEL32!GetLastError` at `0x140058351`
- `KERNEL32!GetLastError` at `0x140057c85`
- `KERNEL32!GetLastError` at `0x140057d65`
- `KERNEL32!GetLastError` at `0x140057ec1`
- `KERNEL32!GetLastError` at `0x140057ed9`
- `KERNEL32!GetLastError` at `0x140057fef`
- `KERNEL32!GetLastError` at `0x1400580a8`
- `KERNEL32!GetLastError` at `0x1400580c3`
- `KERNEL32!GetLastError` at `0x1400581d1`
- `KERNEL32!GetLastError` at `0x140058272`
- `KERNEL32!GetLastError` at `0x14005828d`
- `KERNEL32!GetLastError` at `0x140058351`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057d14`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057dee`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057f73`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005815b`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005831b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400583c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057d14`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057dee`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057f73`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005815b`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005831b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400583c8`
- `WDSCORE!CurrentIP` at `0x140057c93`
- `WDSCORE!CurrentIP` at `0x140057d73`
- `WDSCORE!CurrentIP` at `0x140057ee8`
- `WDSCORE!CurrentIP` at `0x140057ffd`
- `WDSCORE!CurrentIP` at `0x1400580d1`
- `WDSCORE!CurrentIP` at `0x1400581df`
- `WDSCORE!CurrentIP` at `0x14005829b`
- `WDSCORE!CurrentIP` at `0x14005835f`
- `WDSCORE!CurrentIP` at `0x140057c93`
- `WDSCORE!CurrentIP` at `0x140057d73`
- `WDSCORE!CurrentIP` at `0x140057ee8`
- `WDSCORE!CurrentIP` at `0x140057ffd`
- `WDSCORE!CurrentIP` at `0x1400580d1`
- `WDSCORE!CurrentIP` at `0x1400581df`
- `WDSCORE!CurrentIP` at `0x14005829b`
- `WDSCORE!CurrentIP` at `0x14005835f`

## string_xrefs

- `0x140057cbe`: `SPExecuteCleanup: Failure while building path to clean up file %s. Error: 0x%08X`
- `0x140057d9b`: `SPExecuteCleanup: Failure while building path to clean up folder %s. Error: 0x%08X`

## pseudocode

```c

```
