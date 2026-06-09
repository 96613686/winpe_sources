# CStorageFileProxyBase::s_GetStreamFromPropertyStore(IPropertyStore *,Windows::Storage::FileAccessMode,TransactionType,Windows::Storage::StorageOpenOptions,Windows::System::IUser *,_GUID const &,void * *)

- ea: `0x1800c4850`
- end: `0x1800c4bc0`
- name: `?s_GetStreamFromPropertyStore@CStorageFileProxyBase@@KAJPEAUIPropertyStore@@W4FileAccessMode@Storage@Windows@@W4TransactionType@@W4StorageOpenOptions@45@PEAUIUser@System@5@AEBU_GUID@@PEAPEAX@Z`
- size: `880`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006e1e4`
- `0x1800753b4`
- `0x18026bfd4`
- `0x1802c1664`

## callees

- `0x18000d354`
- `0x18000d6cc`
- `0x18000e1e4`
- `0x18000ee68`
- `0x18000ee84`
- `0x1800432f0`
- `0x180060a10`
- `0x1800c4850`
- `0x1800c5e30`
- `0x1803a4cb0`
- `0x1803b0554`
- `0x1803c5200`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180643b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180643b21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180643b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180643b21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4b39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c4b39`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180643b46`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180643b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4ba3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4ab8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c492e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c49b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c492e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c49b6`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800c4a45`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800c4a45`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c4b77`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c4b77`

## pseudocode

```c

```
