# CDlpManager::Initialize(ushort const *,WINDLP_CREATION_DISPOSITION,ulong,IDlpDiagnostics *,IDlpRegistrar *,IDlpRegistrar *)

- ea: `0x140040e70`
- end: `0x140041ac7`
- name: `?Initialize@CDlpManager@@UEAAJPEBGW4WINDLP_CREATION_DISPOSITION@@KPEAVIDlpDiagnostics@@PEAVIDlpRegistrar@@3@Z`
- size: `3159`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x140005e4c`
- `0x1400076c8`
- `0x14000f4a4`
- `0x1400111f0`
- `0x1400135b8`
- `0x14002f4d0`
- `0x14002f6e0`
- `0x1400323e4`
- `0x140034ab4`
- `0x140038e64`
- `0x140040e70`
- `0x140041ad0`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140041a95`
- `KERNEL32!HeapFree` at `0x140041a95`
- `KERNEL32!GetProcessHeap` at `0x140041a81`
- `KERNEL32!GetProcessHeap` at `0x140041a81`
- `KERNEL32!GetFileAttributesW` at `0x140041306`
- `KERNEL32!GetFileAttributesW` at `0x140041306`
- `KERNEL32!LeaveCriticalSection` at `0x1400417d4`
- `KERNEL32!LeaveCriticalSection` at `0x1400417d4`
- `KERNEL32!EnterCriticalSection` at `0x14004173d`
- `KERNEL32!EnterCriticalSection` at `0x14004173d`

## string_xrefs

- `0x1400413d4`: `Create`
- `0x140041422`: `DlpMgrInit: WorkingPath = [%s], Disposition = [%s], Flags = [0x%X], Diagnostics = [%s], StockRegistrar = [%s], UserRegistrar = [%s]`

## pseudocode

```c

```
