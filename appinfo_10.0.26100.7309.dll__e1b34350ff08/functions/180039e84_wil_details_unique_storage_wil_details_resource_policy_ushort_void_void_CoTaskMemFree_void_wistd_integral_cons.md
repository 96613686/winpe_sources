# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180039e84`
- end: `0x180039ed8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a1d8`
- `0x18003d0c8`
- `0x18003d9e4`

## callees

- `0x180010f70`
- `0x1800121a4`
- `0x180039e84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039eae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039eae`

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
0x180039e84  mov     [rsp+arg_8], rbx
0x180039e89  mov     [rsp+arg_10], rsi
0x180039e8e  push    rdi
0x180039e8f  sub     rsp, 20h
0x180039e93  mov     rdi, [rcx]
0x180039e96  mov     rsi, rdx
0x180039e99  mov     rbx, rcx
0x180039e9c  test    rdi, rdi
0x180039e9f  jz      short loc_180039EC4
0x180039ea1  lea     rcx, [rsp+28h+arg_0]; this
0x180039ea6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180039eab  mov     rcx, rdi; pv
0x180039eae  call    cs:__imp_CoTaskMemFree
0x180039eb5  nop     dword ptr [rax+rax+00h]
0x180039eba  lea     rcx, [rsp+28h+arg_0]; this
0x180039ebf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039ec4  mov     [rbx], rsi
0x180039ec7  mov     rbx, [rsp+28h+arg_8]
0x180039ecc  mov     rsi, [rsp+28h+arg_10]
0x180039ed1  add     rsp, 20h
0x180039ed5  pop     rdi
0x180039ed6  retn
```
