# CElevatedDataCollection::AddReflectedCrossProcessPid(void *,ulong,ulong,ulong)

- ea: `0x14005ba44`
- end: `0x14005bcf2`
- name: `?AddReflectedCrossProcessPid@CElevatedDataCollection@@QEAAJPEAXKKK@Z`
- size: `686`
- prototype: `__int64 __fastcall(CElevatedDataCollection *__hidden this, void *, DWORD dwProcessId, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140024924`

## callees

- `0x14000333f`
- `0x140003357`
- `0x140003393`
- `0x140014ee4`
- `0x140014f14`
- `0x140017840`
- `0x14005afa4`
- `0x14005ba44`
- `0x14005de78`
- `0x14005df70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005bb24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005bbb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005bb24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005bbb4`

## string_xrefs

- `0x14005bc90`: `Reflection/ReserveMachineQueueDirectory attempt failed: 0X%X`
- `0x14005ba75`: `Attempting to reflect reporting process!`
- `0x14005bb6e`: `Reflection attempt failed: 0X%X`

## pseudocode

```c

```
