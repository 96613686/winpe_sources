# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180054bc0`
- end: `0x180054bd7`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004dc40`
- `0x180054bb4`
- `0x18005c484`
- `0x180072d44`
- `0x180073ff0`
- `0x18007626c`
- `0x180076548`
- `0x180076870`
- `0x180076d68`
- `0x180077670`
- `0x1800982d8`
- `0x180098460`

## callees

- `0x180054bc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054bcc`

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
0x180054bc0  sub     rsp, 28h
0x180054bc4  mov     rcx, [rcx]; pv
0x180054bc7  test    rcx, rcx
0x180054bca  jz      short loc_180054BD2
0x180054bcc  call    cs:__imp_CoTaskMemFree
0x180054bd2  add     rsp, 28h
0x180054bd6  retn
```
