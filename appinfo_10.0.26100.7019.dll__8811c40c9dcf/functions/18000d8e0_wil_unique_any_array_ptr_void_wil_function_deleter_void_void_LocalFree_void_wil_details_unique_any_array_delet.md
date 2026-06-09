# wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>::reset(void)

- ea: `0x18000d8e0`
- end: `0x18000d98b`
- name: `?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@@wil@@QEAAXXZ`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002a750`
- `0x1800334c8`

## callees

- `0x18000d8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d923`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d934`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d964`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d934`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d964`

## pseudocode

```c

```
