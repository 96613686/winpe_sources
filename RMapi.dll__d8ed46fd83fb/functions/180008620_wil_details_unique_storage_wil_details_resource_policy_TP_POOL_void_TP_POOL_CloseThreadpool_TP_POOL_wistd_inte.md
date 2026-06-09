# wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)

- ea: `0x180008620`
- end: `0x180008637`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a470`
- `0x18000c30c`
- `0x18000cd5c`
- `0x18002570d`

## callees

- `0x180008620`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000862c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000862c`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(
        struct _TP_POOL **a1)
{
  struct _TP_POOL *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpool(v1);
}

```

## disassembly

```asm
0x180008620  sub     rsp, 28h
0x180008624  mov     rcx, [rcx]; ptpp
0x180008627  test    rcx, rcx
0x18000862a  jz      short loc_180008632
0x18000862c  call    cs:__imp_CloseThreadpool
0x180008632  add     rsp, 28h
0x180008636  retn
```
