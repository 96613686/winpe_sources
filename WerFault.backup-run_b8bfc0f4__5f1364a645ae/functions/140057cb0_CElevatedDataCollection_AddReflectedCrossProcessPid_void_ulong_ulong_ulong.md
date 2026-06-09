# CElevatedDataCollection::AddReflectedCrossProcessPid(void *,ulong,ulong,ulong)

- ea: `0x140057cb0`
- end: `0x140057f51`
- name: `?AddReflectedCrossProcessPid@CElevatedDataCollection@@QEAAJPEAXKKK@Z`
- size: `673`
- prototype: `__int64 __fastcall(CElevatedDataCollection *__hidden this, void *, DWORD dwProcessId, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140023204`

## callees

- `0x1400032ef`
- `0x140003307`
- `0x140003343`
- `0x14001444c`
- `0x140014474`
- `0x140016b70`
- `0x140057238`
- `0x140057cb0`
- `0x14005a074`
- `0x14005a16c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057e1a`

## string_xrefs

- `0x140057ce1`: `Attempting to reflect reporting process!`
- `0x140057dd4`: `Reflection attempt failed: 0X%X`
- `0x140057ef0`: `Reflection/ReserveMachineQueueDirectory attempt failed: 0X%X`

## pseudocode

```c

```
