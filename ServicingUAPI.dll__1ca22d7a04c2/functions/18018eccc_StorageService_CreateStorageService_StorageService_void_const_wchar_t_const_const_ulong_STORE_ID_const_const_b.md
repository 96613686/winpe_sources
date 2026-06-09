# StorageService::CreateStorageService(StorageService * *,void (*const)(wchar_t const * const),ulong,STORE_ID const * const,bool)

- ea: `0x18018eccc`
- end: `0x18018eede`
- name: `?CreateStorageService@StorageService@@SAJPEAPEAV1@Q6AXQEB_W@ZKQEBUSTORE_ID@@_N@Z`
- size: `530`
- prototype: `__int64 __fastcall(struct StorageService **, void (*const)(const wchar_t *const), unsigned int, const struct STORE_ID *const, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18018df18`

## callees

- `0x1800063ec`
- `0x18018eabc`
- `0x18018eccc`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18018ed5f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18018ed5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018ee46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018ee46`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18018ed3a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18018ed3a`

## string_xrefs

- `0x18018ee8a`: `CreateImageLogger: Failed to allocate ImageLogger.`
- `0x18018edb8`: `StorageService::CreateStorageService: This function was called with ppService set to NULL.`
- `0x18018ed89`: `CreateImageLogger: ImageLogger.Initialize failed.`
- `0x18018ee69`: `%S: StorageService allocation failed with error 0x%x.`
- `0x18018ee5e`: `StorageService::CreateStorageService`

## pseudocode

```c

```
