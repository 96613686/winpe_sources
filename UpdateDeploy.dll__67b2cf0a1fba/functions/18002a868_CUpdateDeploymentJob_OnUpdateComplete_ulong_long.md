# CUpdateDeploymentJob::OnUpdateComplete(ulong,long)

- ea: `0x18002a868`
- end: `0x18002aa8f`
- name: `?OnUpdateComplete@CUpdateDeploymentJob@@AEAAJKJ@Z`
- size: `551`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, unsigned int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ac0c`
- `0x18002d25c`
- `0x180030988`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180011b44`
- `0x180028304`
- `0x1800294e4`
- `0x18002a868`
- `0x1800330b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a922`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a922`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa70`

## string_xrefs

- `0x18002a89c`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002a8e5`: `Deployment job Id %ws : Update %ws.%d complete delegate invoked.`

## pseudocode

```c

```
