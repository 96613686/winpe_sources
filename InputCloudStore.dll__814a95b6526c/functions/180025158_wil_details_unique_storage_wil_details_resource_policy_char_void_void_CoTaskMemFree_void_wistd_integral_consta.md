# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)

- ea: `0x180025158`
- end: `0x1800251a5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e60`
- `0x180016f00`

## callees

- `0x180004dc8`
- `0x180005094`
- `0x180025158`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025182`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
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
0x180025158  mov     [rsp+arg_8], rbx
0x18002515d  mov     [rsp+arg_10], rsi
0x180025162  push    rdi
0x180025163  sub     rsp, 20h
0x180025167  mov     rdi, [rcx]
0x18002516a  mov     rsi, rdx
0x18002516d  mov     rbx, rcx
0x180025170  test    rdi, rdi
0x180025173  jz      short loc_180025192
0x180025175  lea     rcx, [rsp+28h+arg_0]; this
0x18002517a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002517f  mov     rcx, rdi; pv
0x180025182  call    cs:__imp_CoTaskMemFree
0x180025188  lea     rcx, [rsp+28h+arg_0]; this
0x18002518d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025192  mov     [rbx], rsi
0x180025195  mov     rbx, [rsp+28h+arg_8]
0x18002519a  mov     rsi, [rsp+28h+arg_10]
0x18002519f  add     rsp, 20h
0x1800251a3  pop     rdi
0x1800251a4  retn
```
