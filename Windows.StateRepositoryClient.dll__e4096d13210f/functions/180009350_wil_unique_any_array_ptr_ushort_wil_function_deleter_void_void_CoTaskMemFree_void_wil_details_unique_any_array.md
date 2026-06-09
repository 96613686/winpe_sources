# wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)

- ea: `0x180009350`
- end: `0x1800093aa`
- name: `??$reset_array@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@AEAAXAEBU?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@1@@Z`
- size: `90`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d100`
- `0x18000d490`
- `0x18000d7d0`

## callees

- `0x1800050ac`
- `0x180005468`
- `0x180009350`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009381`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        __int64 a1,
        __int64 a2)
{
  void **v2; // rdi
  __int64 v3; // rsi
  void *v4; // rbx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  v2 = *(void ***)a1;
  v3 = *(_QWORD *)a1 + 8LL * *(_QWORD *)(a1 + 8);
  while ( v2 != (void **)v3 )
  {
    v4 = *v2;
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
    ++v2;
  }
}

```

## disassembly

```asm
0x180009350  mov     [rsp+arg_0], rbx
0x180009355  mov     [rsp+arg_10], rsi
0x18000935a  mov     [rsp+arg_8], rdx
0x18000935f  push    rdi
0x180009360  sub     rsp, 20h
0x180009364  mov     rdi, [rcx]
0x180009367  mov     rax, [rcx+8]
0x18000936b  lea     rsi, [rdi+rax*8]
0x18000936f  jmp     short loc_180009395
0x180009371  mov     rbx, [rdi]
0x180009374  lea     rcx, [rsp+28h+arg_8]; this
0x180009379  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000937e  mov     rcx, rbx; pv
0x180009381  call    cs:__imp_CoTaskMemFree
0x180009387  lea     rcx, [rsp+28h+arg_8]; this
0x18000938c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009391  add     rdi, 8
0x180009395  cmp     rdi, rsi
0x180009398  jnz     short loc_180009371
0x18000939a  mov     rbx, [rsp+28h+arg_0]
0x18000939f  mov     rsi, [rsp+28h+arg_10]
0x1800093a4  add     rsp, 20h
0x1800093a8  pop     rdi
0x1800093a9  retn
```
