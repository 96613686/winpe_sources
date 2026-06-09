# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180023b30`
- end: `0x180023b7d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023a8c`

## callees

- `0x1800198fc`
- `0x18001991c`
- `0x180023b30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023b5a`

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
0x180023b30  mov     [rsp+arg_8], rbx
0x180023b35  mov     [rsp+arg_10], rsi
0x180023b3a  push    rdi
0x180023b3b  sub     rsp, 20h
0x180023b3f  mov     rdi, [rcx]
0x180023b42  mov     rsi, rdx
0x180023b45  mov     rbx, rcx
0x180023b48  test    rdi, rdi
0x180023b4b  jz      short loc_180023B6A
0x180023b4d  lea     rcx, [rsp+28h+arg_0]; this
0x180023b52  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180023b57  mov     rcx, rdi; pv
0x180023b5a  call    cs:__imp_CoTaskMemFree
0x180023b60  lea     rcx, [rsp+28h+arg_0]; this
0x180023b65  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180023b6a  mov     [rbx], rsi
0x180023b6d  mov     rbx, [rsp+28h+arg_8]
0x180023b72  mov     rsi, [rsp+28h+arg_10]
0x180023b77  add     rsp, 20h
0x180023b7b  pop     rdi
0x180023b7c  retn
```
