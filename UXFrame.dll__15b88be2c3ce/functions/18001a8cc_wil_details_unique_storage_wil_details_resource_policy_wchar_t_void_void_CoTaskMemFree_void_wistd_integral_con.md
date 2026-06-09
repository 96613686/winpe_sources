# wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)

- ea: `0x18001a8cc`
- end: `0x18001a919`
- name: `?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ec74`
- `0x180022958`

## callees

- `0x18000d84c`
- `0x18000e9e4`
- `0x18001a8cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8f6`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
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
0x18001a8cc  mov     [rsp+arg_8], rbx
0x18001a8d1  mov     [rsp+arg_10], rsi
0x18001a8d6  push    rdi
0x18001a8d7  sub     rsp, 20h
0x18001a8db  mov     rdi, [rcx]
0x18001a8de  mov     rsi, rdx
0x18001a8e1  mov     rbx, rcx
0x18001a8e4  test    rdi, rdi
0x18001a8e7  jz      short loc_18001A906
0x18001a8e9  lea     rcx, [rsp+28h+arg_0]; this
0x18001a8ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a8f3  mov     rcx, rdi; pv
0x18001a8f6  call    cs:__imp_CoTaskMemFree
0x18001a8fc  lea     rcx, [rsp+28h+arg_0]; this
0x18001a901  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a906  mov     [rbx], rsi
0x18001a909  mov     rbx, [rsp+28h+arg_8]
0x18001a90e  mov     rsi, [rsp+28h+arg_10]
0x18001a913  add     rsp, 20h
0x18001a917  pop     rdi
0x18001a918  retn
```
