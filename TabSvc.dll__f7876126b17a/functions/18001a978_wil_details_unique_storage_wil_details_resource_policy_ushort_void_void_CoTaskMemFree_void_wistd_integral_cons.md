# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18001a978`
- end: `0x18001a9c5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a8d4`
- `0x18001b2d4`

## callees

- `0x1800186a0`
- `0x1800186c0`
- `0x18001a978`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9a2`

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
0x18001a978  mov     [rsp+arg_8], rbx
0x18001a97d  mov     [rsp+arg_10], rsi
0x18001a982  push    rdi
0x18001a983  sub     rsp, 20h
0x18001a987  mov     rdi, [rcx]
0x18001a98a  mov     rsi, rdx
0x18001a98d  mov     rbx, rcx
0x18001a990  test    rdi, rdi
0x18001a993  jz      short loc_18001A9B2
0x18001a995  lea     rcx, [rsp+28h+arg_0]; this
0x18001a99a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a99f  mov     rcx, rdi; pv
0x18001a9a2  call    cs:__imp_CoTaskMemFree
0x18001a9a8  lea     rcx, [rsp+28h+arg_0]; this
0x18001a9ad  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a9b2  mov     [rbx], rsi
0x18001a9b5  mov     rbx, [rsp+28h+arg_8]
0x18001a9ba  mov     rsi, [rsp+28h+arg_10]
0x18001a9bf  add     rsp, 20h
0x18001a9c3  pop     rdi
0x18001a9c4  retn
```
