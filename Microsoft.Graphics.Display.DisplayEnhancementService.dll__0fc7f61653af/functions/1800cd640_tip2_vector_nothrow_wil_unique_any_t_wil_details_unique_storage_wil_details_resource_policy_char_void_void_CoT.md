# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)

- ea: `0x1800cd640`
- end: `0x1800cd6da`
- name: `?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800c8c00`

## callees

- `0x18006cecc`
- `0x1800cd640`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cd66c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cd66c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cd6c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cd6c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cd65e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cd6b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cd65e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cd6b3`

## pseudocode

```c

```
