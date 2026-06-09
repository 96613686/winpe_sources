# wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18003f290`
- end: `0x18003f2a7`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18003f22c`
- `0x18003f728`
- `0x18004ba18`

## callees

- `0x18003f290`

## import_xrefs

- `WS2_32!WSALookupServiceEnd` at `0x18003f29c`
- `WS2_32!WSALookupServiceEnd` at `0x18003f29c`

## pseudocode

```c
INT __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  INT result; // eax

  v1 = *a1;
  if ( v1 )
    return WSALookupServiceEnd(v1);
  return result;
}

```

## disassembly

```asm
0x18003f290  sub     rsp, 28h
0x18003f294  mov     rcx, [rcx]; hLookup
0x18003f297  test    rcx, rcx
0x18003f29a  jz      short loc_18003F2A2
0x18003f29c  call    cs:__imp_WSALookupServiceEnd
0x18003f2a2  add     rsp, 28h
0x18003f2a6  retn
```
