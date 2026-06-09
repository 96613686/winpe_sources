# Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap::AddWorkloadId(HSTRING__ *)

- ea: `0x1800f7c74`
- end: `0x1800f7de2`
- name: `?AddWorkloadId@DeploymentWorkloadIdUniquenessMap@Setup@Management@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `366`
- prototype: `int(Windows::Management::Setup::DeploymentWorkloadIdUniquenessMap *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800f814c`

## callees

- `0x180068958`
- `0x18006e0a8`
- `0x1800b2220`
- `0x1800f77f0`
- `0x1800f7a38`
- `0x1800f7c74`
- `0x1800f810c`
- `0x1800f87a0`
- `0x1800f93a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7c90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f7c90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7d36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f7d36`

## string_xrefs

- `0x1800f7cd1`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f7d78`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\deploymentworkload.cpp`
- `0x1800f7d66`: `Workload ID was already present in map: %ls`

## pseudocode

```c

```
