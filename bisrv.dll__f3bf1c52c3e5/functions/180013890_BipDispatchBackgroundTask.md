# BipDispatchBackgroundTask

- ea: `0x180013890`
- end: `0x180013c5f`
- name: `BipDispatchBackgroundTask`
- size: `975`
- prototype: `__int64 __usercall@<rax>(struct _BI_ACTIVATED_TASK_INSTANCE *@<rcx>, void *@<rdx>, SIZE_T)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012960`

## callees

- `0x180001008`
- `0x180005670`
- `0x180006300`
- `0x18000a9f0`
- `0x1800121b0`
- `0x180013890`
- `0x18002ede0`
- `0x180033110`
- `0x18003e82c`
- `0x180053100`
- `0x18006a58c`
- `0x18006d364`
- `0x180075020`
- `0x18009467a`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180013c2c`
- `ntdll!RtlFreeHeap` at `0x180013c2c`
- `ntdll!TpPostWork` at `0x180013b56`
- `ntdll!TpPostWork` at `0x180013b56`
- `ntdll!RtlAllocateHeap` at `0x180013a01`
- `ntdll!RtlAllocateHeap` at `0x180013a01`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180013a6e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180013a6e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800139d3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800139d3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013c37`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180013c37`

## pseudocode

```c

```
