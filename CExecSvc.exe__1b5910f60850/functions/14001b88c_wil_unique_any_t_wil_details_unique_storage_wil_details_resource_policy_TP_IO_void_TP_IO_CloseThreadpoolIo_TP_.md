# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>(void)

- ea: `0x14001b88c`
- end: `0x14001b8a3`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?CloseThreadpoolIo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_IO **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400231e5`

## callees

- `0x14001b88c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14001b898`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14001b898`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>(
        struct _TP_IO **a1)
{
  struct _TP_IO *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolIo(v1);
}

```

## disassembly

```asm
0x14001b88c  sub     rsp, 28h
0x14001b890  mov     rcx, [rcx]; pio
0x14001b893  test    rcx, rcx
0x14001b896  jz      short loc_14001B89E
0x14001b898  call    cs:__imp_CloseThreadpoolIo
0x14001b89e  add     rsp, 28h
0x14001b8a2  retn
```
