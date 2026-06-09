# RetrieveSegmentedBlob(_DEVICE_OBJECT *,_FILE_OBJECT *,char * *,char * *,_HIDP_CAPS *,_HIDP_PREPARSED_DATA *,_HIDP_VALUE_CAPS)

- ea: `0x1400da36c`
- end: `0x1400da8ab`
- name: `?RetrieveSegmentedBlob@@YAJPEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@PEAPEAD2PEAU_HIDP_CAPS@@PEAU_HIDP_PREPARSED_DATA@@U_HIDP_VALUE_CAPS@@@Z`
- size: `1343`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, struct _FILE_OBJECT *@<rdx>, char **@<r8>, char **@<r9>, struct _HIDP_CAPS *, struct _HIDP_PREPARSED_DATA *, struct _HIDP_VALUE_CAPS *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400da098`

## callees

- `0x1400718f0`
- `0x1400cb450`
- `0x1400da36c`
- `0x1400dbcdc`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400da3f9`
- `ntoskrnl!KeInitializeEvent` at `0x1400da578`
- `ntoskrnl!KeInitializeEvent` at `0x1400da3f9`
- `ntoskrnl!KeInitializeEvent` at `0x1400da578`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400da550`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400da694`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400da550`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400da694`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400da471`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400da5b7`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400da471`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400da5b7`
- `ntoskrnl!IofCallDriver` at `0x1400da49b`
- `ntoskrnl!IofCallDriver` at `0x1400da5dd`
- `ntoskrnl!IofCallDriver` at `0x1400da49b`
- `ntoskrnl!IofCallDriver` at `0x1400da5dd`
- `WIN32K!W32GetUserSessionState` at `0x1400da4f3`
- `WIN32K!W32GetUserSessionState` at `0x1400da637`
- `WIN32K!W32GetUserSessionState` at `0x1400da74a`
- `WIN32K!W32GetUserSessionState` at `0x1400da7e0`
- `WIN32K!W32GetUserSessionState` at `0x1400da842`
- `WIN32K!W32GetUserSessionState` at `0x1400da4f3`
- `WIN32K!W32GetUserSessionState` at `0x1400da637`
- `WIN32K!W32GetUserSessionState` at `0x1400da74a`
- `WIN32K!W32GetUserSessionState` at `0x1400da7e0`
- `WIN32K!W32GetUserSessionState` at `0x1400da842`
- `HIDPARSE!HidP_SetUsageValue` at `0x1400da434`
- `HIDPARSE!HidP_SetUsageValue` at `0x1400da434`
- `HIDPARSE!HidP_GetUsageValueArray` at `0x1400da6e2`
- `HIDPARSE!HidP_GetUsageValueArray` at `0x1400da6e2`

## pseudocode

```c

```
