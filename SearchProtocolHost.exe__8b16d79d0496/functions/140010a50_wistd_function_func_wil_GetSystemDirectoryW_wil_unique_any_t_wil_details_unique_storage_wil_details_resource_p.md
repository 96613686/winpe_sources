# wistd::__function::__func<`wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x140010a50`
- end: `0x140010aa5`
- name: `??R?$__func@V_lambda_1_@?1???$GetSystemDirectoryW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x140010a50`
- `0x14002801c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140010a65`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140010a65`

## string_xrefs

- `0x140010a7a`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall __R____func_V_lambda_1___1____GetSystemDirectoryW_V__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___2__Z___A6AJPEA_W_KPEA_K_Z___function_wistd__UEAAJ__QEAPEA_W__QEA_K__QEAPEA_K_Z(
        __int64 a1,
        LPWSTR *a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  UINT SystemDirectoryW; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a3;
  v5 = *a4;
  SystemDirectoryW = GetSystemDirectoryW(*a2, *a3);
  *v5 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x230,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
             v7);
  if ( SystemDirectoryW < v4 )
    *v5 = SystemDirectoryW + 1LL;
  return 0;
}

```

## disassembly

```asm
0x140010a50  mov     [rsp+arg_0], rbx
0x140010a55  push    rdi
0x140010a56  sub     rsp, 20h
0x140010a5a  mov     rbx, [r8]
0x140010a5d  mov     rcx, [rdx]; lpBuffer
0x140010a60  mov     edx, ebx; uSize
0x140010a62  mov     rdi, [r9]
0x140010a65  call    cs:__imp_GetSystemDirectoryW
0x140010a6b  mov     eax, eax
0x140010a6d  mov     [rdi], rax
0x140010a70  test    rax, rax
0x140010a73  jnz     short loc_140010A8D
0x140010a75  mov     rcx, [rsp+28h]; this
0x140010a7a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140010a81  mov     edx, 230h; void *
0x140010a86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010a8b  jmp     short loc_140010A9A
0x140010a8d  cmp     rax, rbx
0x140010a90  jnb     short loc_140010A98
0x140010a92  inc     rax
0x140010a95  mov     [rdi], rax
0x140010a98  xor     eax, eax
0x140010a9a  mov     rbx, [rsp+28h+arg_0]
0x140010a9f  add     rsp, 20h
0x140010aa3  pop     rdi
0x140010aa4  retn
```
