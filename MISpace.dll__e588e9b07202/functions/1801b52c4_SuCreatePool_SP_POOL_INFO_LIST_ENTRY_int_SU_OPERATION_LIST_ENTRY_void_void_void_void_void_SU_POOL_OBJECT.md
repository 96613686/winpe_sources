# SuCreatePool(_SP_POOL_INFO *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *,_SU_POOL_OBJECT * *)

- ea: `0x1801b52c4`
- end: `0x1801b570d`
- name: `?SuCreatePool@@YAHPEAU_SP_POOL_INFO@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@Z3PEAPEAU_SU_POOL_OBJECT@@@Z`
- size: `1097`
- prototype: `__int64 __usercall@<rax>(struct _SP_POOL_INFO *@<rcx>, struct _LIST_ENTRY *@<rdx>, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *)@<r8>, void *@<r9>, struct _SU_POOL_OBJECT **)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18002c430`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x180079eec`
- `0x180195a90`
- `0x1801b0d44`
- `0x1801b1ddc`
- `0x1801b1ed4`
- `0x1801b4e9c`
- `0x1801b5148`
- `0x1801b52c4`
- `0x1801b6220`
- `0x1801b640c`
- `0x1801b657c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5514`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b5365`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b53d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b56e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b5365`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b53d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b56e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b5349`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b552a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b5349`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b552a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b56d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b56d7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b54de`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b54de`

## string_xrefs

- `0x1801b54ea`: `DeviceIoControl - IOCTL_SPACEPORT_CREATE_POOL`

## pseudocode

```c

```
