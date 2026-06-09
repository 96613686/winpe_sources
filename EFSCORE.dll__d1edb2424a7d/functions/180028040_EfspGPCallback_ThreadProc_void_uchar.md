# EfspGPCallback_ThreadProc(void *,uchar)

- ea: `0x180028040`
- end: `0x1800282a7`
- name: `?EfspGPCallback_ThreadProc@@YAXPEAXE@Z`
- size: `615`
- prototype: `void __fastcall(PVOID Context, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18001f920`
- `0x180028040`
- `0x1800286f8`
- `0x180035c90`
- `0x180035d20`
- `0x180063600`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028062`
- `USERENV!LeaveCriticalPolicySection` at `0x180028118`
- `USERENV!LeaveCriticalPolicySection` at `0x180028118`
- `USERENV!EnterCriticalPolicySection` at `0x18002809a`
- `USERENV!EnterCriticalPolicySection` at `0x18002809a`
- `USERENV!UnregisterGPNotification` at `0x180028059`
- `USERENV!UnregisterGPNotification` at `0x180028059`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002807c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002807c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002828f`
- `ntdll!RtlLeaveCriticalSection` at `0x18002828f`
- `ntdll!RtlEnterCriticalSection` at `0x180028125`
- `ntdll!RtlEnterCriticalSection` at `0x180028125`
- `EFSUTIL!EfsUtilApplyGroupPolicy` at `0x18002810a`
- `EFSUTIL!EfsUtilApplyGroupPolicy` at `0x18002810a`

## pseudocode

```c

```
