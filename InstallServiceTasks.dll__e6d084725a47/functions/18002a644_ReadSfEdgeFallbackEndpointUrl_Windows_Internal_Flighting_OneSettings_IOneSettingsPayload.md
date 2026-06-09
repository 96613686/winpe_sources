# _ReadSfEdgeFallbackEndpointUrl(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)

- ea: `0x18002a644`
- end: `0x18002a7e1`
- name: `?_ReadSfEdgeFallbackEndpointUrl@@YAJPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b21c`
- `0x18002e654`

## callees

- `0x180003450`
- `0x18000912c`
- `0x18000b48c`
- `0x180010f50`
- `0x180012f10`
- `0x1800156a8`
- `0x1800202c4`
- `0x1800206dc`
- `0x18002a644`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a6dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a79d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a6dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a79d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a6fa`

## string_xrefs

- `0x18002a7ce`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002a6c6`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002a787`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002a76a`: `SfEdgeFallbackEndpointUrl fetched from cache: %s`
- `0x18002a77a`: `_ReadSfEdgeFallbackEndpointUrl`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _ReadSfEdgeFallbackEndpointUrl(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1)
{
  __int64 (*v1)(void); // rbx
  char v2; // r8
  int v3; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-78h]
  HSTRING_HEADER v7; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = *(__int64 (**)(void))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, (const WCHAR **)off_180048570, v2);
  try
  {
    v3 = v1();
    v4 = v3;
    if ( v3 >= 0 )
    {
      WindowsDeleteString(0);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v3,
        v6);
      WindowsDeleteString(0);
      result = v4;
    }
  }
  catch ( ... )
  {
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0xFFAu,
      "_ReadSfEdgeFallbackEndpointUrl",
      -1,
      L"Exception while reading SfEdgeFallbackEndpointUrl from OneSettings",
      0,
      0);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002a644  mov     [rsp+arg_8], rbx
0x18002a649  push    rdi
0x18002a64a  sub     rsp, 90h
0x18002a651  mov     rax, cs:__security_cookie
0x18002a658  xor     rax, rsp
0x18002a65b  mov     [rsp+98h+var_10], rax
0x18002a663  mov     rdi, rcx
0x18002a666  mov     [rsp+98h+var_40], 0
0x18002a66e  mov     [rsp+98h+string], 0
0x18002a677  mov     rax, [rcx]
0x18002a67a  mov     rbx, [rax+48h]
0x18002a67e  xor     ecx, ecx; string
0x18002a680  call    cs:__imp_WindowsDeleteString
0x18002a686  mov     [rsp+98h+string], 0
0x18002a68f  lea     rdx, off_180048570; "SFEDGEFALLBACKENDPOINTURL"
0x18002a696  lea     rcx, [rsp+98h+var_30]
0x18002a69b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002a6a0  nop
0x18002a6a1  lea     r8, [rsp+98h+string]
0x18002a6a6  mov     rdx, [rax+18h]
0x18002a6aa  mov     rcx, rdi
0x18002a6ad  mov     rax, rbx
0x18002a6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6b5  mov     ebx, eax
0x18002a6b7  test    eax, eax
0x18002a6b9  jns     short loc_18002A6EA
0x18002a6bb  mov     rcx, [rsp+98h]; this
0x18002a6c3  mov     r9d, eax; char *
0x18002a6c6  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002a6cd  mov     edx, 0FF1h; void *
0x18002a6d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a6d7  nop
0x18002a6d8  mov     rcx, [rsp+98h+string]; string
0x18002a6dd  call    cs:__imp_WindowsDeleteString
0x18002a6e3  mov     eax, ebx
0x18002a6e5  jmp     loc_18002A7AD
0x18002a6ea  mov     rcx, [rsp+98h+string]; string
0x18002a6ef  test    rcx, rcx
0x18002a6f2  jz      loc_18002A79D
0x18002a6f8  xor     edx, edx; length
0x18002a6fa  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a700  nop
0x18002a701  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a705  mov     r8, rbx
0x18002a708  mov     rdx, rax
0x18002a70b  lea     rcx, [rsp+98h+var_38]
0x18002a710  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a715  mov     [rsp+98h+var_40], 2
0x18002a71d  mov     rcx, [rsp+98h]; this
0x18002a725  cmp     [rsp+98h+var_38], 0
0x18002a72b  jz      loc_18002A7CE
0x18002a731  lea     rdx, [rsp+98h+var_38]
0x18002a736  lea     rcx, qword_18006A558
0x18002a73d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002a742  lea     rcx, [rsp+98h+var_38]
0x18002a747  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a74c  mov     rax, cs:qword_18006A558
0x18002a753  mov     [rsp+98h+var_58], rax
0x18002a758  mov     [rsp+98h+var_60], 0; unsigned __int16 *
0x18002a761  mov     [rsp+98h+var_68], 0; char *
0x18002a76a  lea     rax, aSfedgefallback; "SfEdgeFallbackEndpointUrl fetched from "...
0x18002a771  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x18002a776  mov     [rsp+98h+var_78], ebx; int
0x18002a77a  lea     r9, aReadsfedgefall; "_ReadSfEdgeFallbackEndpointUrl"
0x18002a781  mov     r8d, 0FF5h; unsigned int
0x18002a787  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002a78e  mov     ecx, 4; unsigned int
0x18002a793  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002a798  mov     rcx, [rsp+98h+string]; string
0x18002a79d  call    cs:__imp_WindowsDeleteString
0x18002a7a3  nop
0x18002a7a4  xor     eax, eax
0x18002a7a6  jmp     short loc_18002A7AD
0x18002a7a8  mov     eax, 80004005h
0x18002a7ad  mov     rcx, [rsp+98h+var_10]
0x18002a7b5  xor     rcx, rsp; StackCookie
0x18002a7b8  call    __security_check_cookie
0x18002a7bd  mov     rbx, [rsp+98h+arg_8]
0x18002a7c5  add     rsp, 90h
0x18002a7cc  pop     rdi
0x18002a7cd  retn
0x18002a7ce  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002a7d5  mov     edx, 0FF8h; void *
0x18002a7da  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
