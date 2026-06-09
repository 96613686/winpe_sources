# Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)

- ea: `0x18003d708`
- end: `0x18003d90e`
- name: `?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z`
- size: `518`
- prototype: `__int64 __usercall@<rax>(DWORD dwMilliseconds@<ecx>, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009d60`
- `0x18007fe88`
- `0x1800808b0`
- `0x180081080`

## callees

- `0x180011328`
- `0x18003d708`
- `0x18005b37c`
- `0x1800637e8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d80a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d80a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003d745`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003d745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d8c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d8c1`

## pseudocode

```c

```
