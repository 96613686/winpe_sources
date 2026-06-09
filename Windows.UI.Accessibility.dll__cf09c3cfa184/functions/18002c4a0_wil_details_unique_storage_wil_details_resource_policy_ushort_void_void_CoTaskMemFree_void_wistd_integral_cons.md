# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18002c4a0`
- end: `0x18002c4ed`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b67c`
- `0x18002b89c`
- `0x18002c548`

## callees

- `0x180008be8`
- `0x1800092b0`
- `0x18002c4a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4ca`

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
0x18002c4a0  mov     [rsp+arg_8], rbx
0x18002c4a5  mov     [rsp+arg_10], rsi
0x18002c4aa  push    rdi
0x18002c4ab  sub     rsp, 20h
0x18002c4af  mov     rdi, [rcx]
0x18002c4b2  mov     rsi, rdx
0x18002c4b5  mov     rbx, rcx
0x18002c4b8  test    rdi, rdi
0x18002c4bb  jz      short loc_18002C4DA
0x18002c4bd  lea     rcx, [rsp+28h+arg_0]; this
0x18002c4c2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002c4c7  mov     rcx, rdi; pv
0x18002c4ca  call    cs:__imp_CoTaskMemFree
0x18002c4d0  lea     rcx, [rsp+28h+arg_0]; this
0x18002c4d5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002c4da  mov     [rbx], rsi
0x18002c4dd  mov     rbx, [rsp+28h+arg_8]
0x18002c4e2  mov     rsi, [rsp+28h+arg_10]
0x18002c4e7  add     rsp, 20h
0x18002c4eb  pop     rdi
0x18002c4ec  retn
```
