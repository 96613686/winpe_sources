# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)

- ea: `0x180010a60`
- end: `0x180010aad`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e8f0`
- `0x18000eab0`
- `0x18000f180`
- `0x180010770`
- `0x180012c48`
- `0x180013c1c`
- `0x180016424`
- `0x1800164c4`
- `0x180017144`
- `0x18001a418`
- `0x18001e55c`
- `0x1800215fc`
- `0x180021830`
- `0x180027b20`
- `0x180029b20`
- `0x180029fa0`
- `0x18002b150`
- `0x18002bb40`
- `0x18002c2f0`
- `0x18002c900`
- `0x18002c9d0`
- `0x18002ce20`
- `0x18002fa88`
- `0x180030714`
- `0x18003106c`
- `0x180031284`
- `0x180032050`
- `0x180037bb8`
- `0x180039090`
- `0x18003a290`
- `0x1800412d0`
- `0x180045468`
- `0x1800464a0`

## callees

- `0x1800068f0`
- `0x180007114`
- `0x180010a60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a8a`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
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
0x180010a60  mov     [rsp+arg_8], rbx
0x180010a65  mov     [rsp+arg_10], rsi
0x180010a6a  push    rdi
0x180010a6b  sub     rsp, 20h
0x180010a6f  mov     rdi, [rcx]
0x180010a72  mov     rsi, rdx
0x180010a75  mov     rbx, rcx
0x180010a78  test    rdi, rdi
0x180010a7b  jz      short loc_180010A9A
0x180010a7d  lea     rcx, [rsp+28h+arg_0]; this
0x180010a82  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180010a87  mov     rcx, rdi; pv
0x180010a8a  call    cs:__imp_CoTaskMemFree
0x180010a90  lea     rcx, [rsp+28h+arg_0]; this
0x180010a95  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180010a9a  mov     [rbx], rsi
0x180010a9d  mov     rbx, [rsp+28h+arg_8]
0x180010aa2  mov     rsi, [rsp+28h+arg_10]
0x180010aa7  add     rsp, 20h
0x180010aab  pop     rdi
0x180010aac  retn
```
