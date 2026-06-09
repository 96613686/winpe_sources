# CUpdateDeploymentJob::OnUpdateFailure(ulong,long,ulong,ulong *)

- ea: `0x18002a674`
- end: `0x18002a862`
- name: `?OnUpdateFailure@CUpdateDeploymentJob@@AEAAJKJKPEAK@Z`
- size: `494`
- prototype: `__int64 __usercall@<rax>(CUpdateDeploymentJob *__hidden this@<rcx>, unsigned int@<edx>, int@<r8d>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ac0c`
- `0x18002bfd4`
- `0x18002d25c`
- `0x18002d3d0`
- `0x180030988`
- `0x180035ca0`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180011b44`
- `0x180028304`
- `0x1800294e4`
- `0x18002a674`
- `0x1800330b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a73a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a73a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a846`

## string_xrefs

- `0x18002a6b4`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002a6fd`: `Deployment job Id %ws : Update %ws.%d failure delegate invoked.`

## pseudocode

```c

```
