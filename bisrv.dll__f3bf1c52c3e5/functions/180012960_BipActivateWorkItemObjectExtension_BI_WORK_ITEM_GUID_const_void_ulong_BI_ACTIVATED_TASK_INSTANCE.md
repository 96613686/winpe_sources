# BipActivateWorkItemObjectExtension(_BI_WORK_ITEM *,_GUID const *,void *,ulong,_BI_ACTIVATED_TASK_INSTANCE *)

- ea: `0x180012960`
- end: `0x180013181`
- name: `?BipActivateWorkItemObjectExtension@@YAJPEAU_BI_WORK_ITEM@@PEBU_GUID@@PEAXKPEAU_BI_ACTIVATED_TASK_INSTANCE@@@Z`
- size: `2081`
- prototype: `__int64 __usercall@<rax>(struct _BI_WORK_ITEM *@<rcx>, const struct _GUID *@<rdx>, void *@<r8>, unsigned int@<r9d>, struct _BI_ACTIVATED_TASK_INSTANCE *)`
- caller_count: `1`
- callee_count: `34`
- tags: `loader_planting, service_task`

## callers

- `0x18005a570`

## callees

- `0x18000546c`
- `0x180005490`
- `0x18000552c`
- `0x180005640`
- `0x180005670`
- `0x18000e360`
- `0x18000e610`
- `0x18000fbd0`
- `0x180010094`
- `0x180010630`
- `0x180012960`
- `0x180013190`
- `0x180013214`
- `0x1800133d4`
- `0x1800136c4`
- `0x180013798`
- `0x180013890`
- `0x180013c70`
- `0x180013d98`
- `0x180013eb0`
- `0x180013f60`
- `0x180013ffc`
- `0x1800158e8`
- `0x18003f804`
- `0x18004c310`
- `0x18004eba4`
- `0x18005c25c`
- `0x18006a8d4`
- `0x18006d364`
- `0x180080860`
- `0x180080b90`
- `0x180094656`
- `0x18009467a`
- `0x180095010`

## import_xrefs

- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x180012ea6`
- `ntdll!RtlQueryUnbiasedInterruptTime` at `0x180012ea6`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012acd`
- `ntdll!RtlReleaseSRWLockShared` at `0x180013018`
- `ntdll!RtlReleaseSRWLockShared` at `0x180012acd`
- `ntdll!RtlReleaseSRWLockShared` at `0x180013018`
- `ntdll!RtlAcquireSRWLockShared` at `0x180012a60`
- `ntdll!RtlAcquireSRWLockShared` at `0x180012a60`
- `ntdll!RtlAllocateHeap` at `0x180012bd3`
- `ntdll!RtlAllocateHeap` at `0x180012fa0`
- `ntdll!RtlAllocateHeap` at `0x180012bd3`
- `ntdll!RtlAllocateHeap` at `0x180012fa0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180012c0b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180012c0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012fd8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012fd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800129cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012def`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800129cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012def`

## pseudocode

```c

```
