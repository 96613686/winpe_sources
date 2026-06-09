# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180027fd8`
- end: `0x180028025`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025944`
- `0x180025a10`
- `0x180029c4c`
- `0x180029e90`
- `0x18002d414`
- `0x18004cfc4`
- `0x18004d518`

## callees

- `0x1800097bc`
- `0x18000a64c`
- `0x180027fd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028002`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180027fd8  mov     [rsp+arg_8], rbx
0x180027fdd  mov     [rsp+arg_10], rsi
0x180027fe2  push    rdi
0x180027fe3  sub     rsp, 20h
0x180027fe7  mov     rdi, [rcx]
0x180027fea  mov     rsi, rdx
0x180027fed  mov     rbx, rcx
0x180027ff0  test    rdi, rdi
0x180027ff3  jz      short loc_180028012
0x180027ff5  lea     rcx, [rsp+28h+arg_0]; this
0x180027ffa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180027fff  mov     rcx, rdi; pv
0x180028002  call    cs:__imp_CoTaskMemFree
0x180028008  lea     rcx, [rsp+28h+arg_0]; this
0x18002800d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180028012  mov     [rbx], rsi
0x180028015  mov     rbx, [rsp+28h+arg_8]
0x18002801a  mov     rsi, [rsp+28h+arg_10]
0x18002801f  add     rsp, 20h
0x180028023  pop     rdi
0x180028024  retn
```
