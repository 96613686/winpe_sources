# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18005bd8c`
- end: `0x18005bde0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180071b24`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x18005bd8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bdb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bdb6`

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
0x18005bd8c  mov     [rsp+arg_8], rbx
0x18005bd91  mov     [rsp+arg_10], rsi
0x18005bd96  push    rdi
0x18005bd97  sub     rsp, 20h
0x18005bd9b  mov     rdi, [rcx]
0x18005bd9e  mov     rsi, rdx
0x18005bda1  mov     rbx, rcx
0x18005bda4  test    rdi, rdi
0x18005bda7  jz      short loc_18005BDCC
0x18005bda9  lea     rcx, [rsp+28h+arg_0]; this
0x18005bdae  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005bdb3  mov     rcx, rdi; pv
0x18005bdb6  call    cs:__imp_CoTaskMemFree
0x18005bdbd  nop     dword ptr [rax+rax+00h]
0x18005bdc2  lea     rcx, [rsp+28h+arg_0]; this
0x18005bdc7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005bdcc  mov     [rbx], rsi
0x18005bdcf  mov     rbx, [rsp+28h+arg_8]
0x18005bdd4  mov     rsi, [rsp+28h+arg_10]
0x18005bdd9  add     rsp, 20h
0x18005bddd  pop     rdi
0x18005bdde  retn
```
