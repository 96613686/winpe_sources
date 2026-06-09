# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18000e5f4`
- end: `0x18000e641`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e1e8`

## callees

- `0x18000dea4`
- `0x18000df24`
- `0x18000e5f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e61e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e61e`

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
0x18000e5f4  mov     [rsp+arg_8], rbx
0x18000e5f9  mov     [rsp+arg_10], rsi
0x18000e5fe  push    rdi
0x18000e5ff  sub     rsp, 20h
0x18000e603  mov     rdi, [rcx]
0x18000e606  mov     rsi, rdx
0x18000e609  mov     rbx, rcx
0x18000e60c  test    rdi, rdi
0x18000e60f  jz      short loc_18000E62E
0x18000e611  lea     rcx, [rsp+28h+arg_0]; this
0x18000e616  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e61b  mov     rcx, rdi; pv
0x18000e61e  call    cs:__imp_CoTaskMemFree
0x18000e624  lea     rcx, [rsp+28h+arg_0]; this
0x18000e629  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e62e  mov     [rbx], rsi
0x18000e631  mov     rbx, [rsp+28h+arg_8]
0x18000e636  mov     rsi, [rsp+28h+arg_10]
0x18000e63b  add     rsp, 20h
0x18000e63f  pop     rdi
0x18000e640  retn
```
