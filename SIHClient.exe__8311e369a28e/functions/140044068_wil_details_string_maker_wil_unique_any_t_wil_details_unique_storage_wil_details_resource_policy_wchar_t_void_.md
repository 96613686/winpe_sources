# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x140044068`
- end: `0x1400440ef`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004415c`

## callees

- `0x1400374b0`
- `0x140044068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400440ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400440ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004409a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004409a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400440a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400440c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400440a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400440c7`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
        void **a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  void **v5; // rax
  void **v6; // rsi
  void *v7; // rbp
  void *v8; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v5 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3,
                  a4);
  v6 = v5;
  if ( a1 != v5 )
  {
    v7 = *a1;
    v8 = *v5;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v7);
      SetLastError(LastError);
    }
    *a1 = v8;
    *v6 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140044068  mov     [rsp+arg_8], rbx
0x14004406d  mov     [rsp+arg_10], rbp
0x140044072  push    rsi
0x140044073  push    rdi
0x140044074  push    r14
0x140044076  sub     rsp, 20h
0x14004407a  mov     rdi, rcx
0x14004407d  lea     rcx, [rsp+38h+pv]
0x140044082  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x140044087  mov     rsi, rax
0x14004408a  cmp     rdi, rax
0x14004408d  jz      short loc_1400440BD
0x14004408f  mov     rbp, [rdi]
0x140044092  mov     r14, [rax]
0x140044095  test    rbp, rbp
0x140044098  jz      short loc_1400440B3
0x14004409a  call    cs:__imp_GetLastError
0x1400440a0  mov     rcx, rbp; pv
0x1400440a3  mov     ebx, eax
0x1400440a5  call    cs:__imp_CoTaskMemFree
0x1400440ab  mov     ecx, ebx; dwErrCode
0x1400440ad  call    cs:__imp_SetLastError
0x1400440b3  mov     [rdi], r14
0x1400440b6  mov     qword ptr [rsi], 0
0x1400440bd  mov     rcx, [rsp+38h+pv]; pv
0x1400440c2  test    rcx, rcx
0x1400440c5  jz      short loc_1400440CD
0x1400440c7  call    cs:__imp_CoTaskMemFree
0x1400440cd  mov     rax, [rdi]
0x1400440d0  mov     rbx, [rsp+38h+arg_8]
0x1400440d5  neg     rax
0x1400440d8  mov     rbp, [rsp+38h+arg_10]
0x1400440dd  sbb     eax, eax
0x1400440df  not     eax
0x1400440e1  and     eax, 8007000Eh
0x1400440e6  add     rsp, 20h
0x1400440ea  pop     r14
0x1400440ec  pop     rdi
0x1400440ed  pop     rsi
0x1400440ee  retn
```
