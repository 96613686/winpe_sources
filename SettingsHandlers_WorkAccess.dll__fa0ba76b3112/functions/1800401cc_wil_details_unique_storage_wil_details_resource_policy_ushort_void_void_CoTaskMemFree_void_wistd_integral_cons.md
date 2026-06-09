# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x1800401cc`
- end: `0x180040220`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042c88`
- `0x180043448`

## callees

- `0x18000526c`
- `0x1800058fc`
- `0x1800401cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800401f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800401f6`

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
0x1800401cc  mov     [rsp+arg_8], rbx
0x1800401d1  mov     [rsp+arg_10], rsi
0x1800401d6  push    rdi
0x1800401d7  sub     rsp, 20h
0x1800401db  mov     rdi, [rcx]
0x1800401de  mov     rsi, rdx
0x1800401e1  mov     rbx, rcx
0x1800401e4  test    rdi, rdi
0x1800401e7  jz      short loc_18004020C
0x1800401e9  lea     rcx, [rsp+28h+arg_0]; this
0x1800401ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800401f3  mov     rcx, rdi; pv
0x1800401f6  call    cs:__imp_CoTaskMemFree
0x1800401fd  nop     dword ptr [rax+rax+00h]
0x180040202  lea     rcx, [rsp+28h+arg_0]; this
0x180040207  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004020c  mov     [rbx], rsi
0x18004020f  mov     rbx, [rsp+28h+arg_8]
0x180040214  mov     rsi, [rsp+28h+arg_10]
0x180040219  add     rsp, 20h
0x18004021d  pop     rdi
0x18004021e  retn
```
