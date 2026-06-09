# Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)

- ea: `0x18002e930`
- end: `0x18002eb5e`
- name: `?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z`
- size: `558`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052400`

## callees

- `0x18001ef7c`
- `0x18002e930`
- `0x18006fec8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ea77`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ea77`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e969`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eace`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eace`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb2b`

## pseudocode

```c

```
