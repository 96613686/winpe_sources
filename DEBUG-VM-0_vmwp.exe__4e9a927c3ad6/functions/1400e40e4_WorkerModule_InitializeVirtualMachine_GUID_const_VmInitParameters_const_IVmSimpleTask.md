# WorkerModule::InitializeVirtualMachine(_GUID const &,VmInitParameters const *,IVmSimpleTask *)

- ea: `0x1400e40e4`
- end: `0x1400e44e6`
- name: `?InitializeVirtualMachine@WorkerModule@@QEAAXAEBU_GUID@@PEBUVmInitParameters@@PEAUIVmSimpleTask@@@Z`
- size: `1026`
- prototype: `void(WorkerModule *__hidden this, const struct _GUID *, const struct VmInitParameters *, struct IVmSimpleTask *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update`

## callers

- `0x140149920`

## callees

- `0x14003364c`
- `0x140042240`
- `0x1400450b8`
- `0x14004579c`
- `0x140047b70`
- `0x140054af0`
- `0x14006af38`
- `0x140092e38`
- `0x14009d7ac`
- `0x1400d6ed0`
- `0x1400e40e4`
- `0x1400e44ec`
- `0x1400e457c`
- `0x1400e4ca4`
- `0x1400e4d64`
- `0x1400e4d8c`
- `0x1400e7cec`
- `0x1400e7d18`
- `0x1400ee314`
- `0x140111070`
- `0x140132cec`
- `0x1401335fc`
- `0x140135929`
- `0x14013d108`
- `0x14013efa4`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400e4317`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400e4317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400e4347`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400e4347`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400e44a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400e44a5`
- `vmprox!GetVmErrInfo` at `0x1400e445b`
- `vmprox!GetVmErrInfo` at `0x1400e445b`

## pseudocode

```c

```
