# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)

- ea: `0x180106fd8`
- end: `0x18010704c`
- name: `?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180105edc`
- `0x180106c38`

## callees

- `0x180053020`
- `0x180106fd8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180107012`
- `KERNEL32!GetProcessHeap` at `0x180107012`
- `KERNEL32!HeapFree` at `0x180107020`
- `KERNEL32!HeapFree` at `0x180107020`

## pseudocode

```c

```
