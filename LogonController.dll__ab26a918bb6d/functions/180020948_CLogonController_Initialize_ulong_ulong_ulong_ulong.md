# CLogonController::_Initialize(ulong,ulong,ulong,ulong)

- ea: `0x180020948`
- end: `0x180020d34`
- name: `?_Initialize@CLogonController@@AEAAJKKKK@Z`
- size: `1004`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x18001fec0`

## callees

- `0x180008094`
- `0x18000d098`
- `0x18000d2c8`
- `0x18000df10`
- `0x1800128e8`
- `0x180015774`
- `0x180020948`
- `0x180023f60`
- `0x180026e70`
- `0x1800314f8`
- `0x180031a38`
- `0x180042c18`
- `0x18005d488`
- `0x180060138`
- `0x18006c000`
- `0x18006f0d8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x180020c14`
- `KERNEL32!HeapSetInformation` at `0x180020c14`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180020c64`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180020c64`
- `ntdll!NtQueryWnfStateData` at `0x1800209b0`
- `ntdll!NtQueryWnfStateData` at `0x1800209b0`
- `UxTheme!__imp_EnableServiceConnection` at `0x180020c02`
- `UxTheme!__imp_EnableServiceConnection` at `0x180020c02`

## pseudocode

```c

```
