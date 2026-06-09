# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180011b84`
- end: `0x180011bd1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004388`
- `0x180011aa0`
- `0x1800120d0`

## callees

- `0x18000371c`
- `0x1800037a0`
- `0x180011b84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011bae`

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
0x180011b84  mov     [rsp+arg_8], rbx
0x180011b89  mov     [rsp+arg_10], rsi
0x180011b8e  push    rdi
0x180011b8f  sub     rsp, 20h
0x180011b93  mov     rdi, [rcx]
0x180011b96  mov     rsi, rdx
0x180011b99  mov     rbx, rcx
0x180011b9c  test    rdi, rdi
0x180011b9f  jz      short loc_180011BBE
0x180011ba1  lea     rcx, [rsp+28h+arg_0]; this
0x180011ba6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011bab  mov     rcx, rdi; pv
0x180011bae  call    cs:__imp_CoTaskMemFree
0x180011bb4  lea     rcx, [rsp+28h+arg_0]; this
0x180011bb9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011bbe  mov     [rbx], rsi
0x180011bc1  mov     rbx, [rsp+28h+arg_8]
0x180011bc6  mov     rsi, [rsp+28h+arg_10]
0x180011bcb  add     rsp, 20h
0x180011bcf  pop     rdi
0x180011bd0  retn
```
