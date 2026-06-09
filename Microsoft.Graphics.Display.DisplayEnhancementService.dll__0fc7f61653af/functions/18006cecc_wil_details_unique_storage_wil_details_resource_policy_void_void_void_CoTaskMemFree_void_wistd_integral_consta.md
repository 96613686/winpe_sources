# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18006cecc`
- end: `0x18006cee3`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006d1b4`
- `0x1800725f8`
- `0x180072918`
- `0x180072c4c`
- `0x180073d58`
- `0x1800c6fe4`
- `0x1800c71ac`
- `0x1800c73f8`
- `0x1800c7d1c`
- `0x1800c8c00`
- `0x1800cd0cc`
- `0x1800cd640`
- `0x1800cd814`

## callees

- `0x18006cecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ced8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ced8`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18006cecc  sub     rsp, 28h
0x18006ced0  mov     rcx, [rcx]; pv
0x18006ced3  test    rcx, rcx
0x18006ced6  jz      short loc_18006CEDE
0x18006ced8  call    cs:__imp_CoTaskMemFree
0x18006cede  add     rsp, 28h
0x18006cee2  retn
```
