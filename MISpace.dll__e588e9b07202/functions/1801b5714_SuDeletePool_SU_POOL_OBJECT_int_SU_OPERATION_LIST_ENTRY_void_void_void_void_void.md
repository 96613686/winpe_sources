# SuDeletePool(_SU_POOL_OBJECT *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *)

- ea: `0x1801b5714`
- end: `0x1801b5903`
- name: `?SuDeletePool@@YAHPEAU_SU_POOL_OBJECT@@P6AHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX333@Z3@Z`
- size: `495`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *), void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002cb80`

## callees

- `0x180028fc0`
- `0x180195a90`
- `0x1801b065c`
- `0x1801b419c`
- `0x1801b4958`
- `0x1801b5714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5826`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b58ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b58ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b5749`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b5832`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b5749`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b5832`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b58d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b58d9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b57b9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b57b9`

## string_xrefs

- `0x1801b57c5`: `DeviceIoControl - IOCTL_SPACEPORT_DELETE_POOL`
- `0x1801b5866`: `SuDeletePool`
- `0x1801b588b`: `SuDeletePool`

## pseudocode

```c

```
