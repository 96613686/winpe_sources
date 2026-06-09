# _ReadProductCatalogUrl(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *)

- ea: `0x18002a4a0`
- end: `0x18002a63d`
- name: `?_ReadProductCatalogUrl@@YAJPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Z`
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
- `0x18002a4a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a556`

## string_xrefs

- `0x18002a62a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002a522`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002a5e3`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002a5d6`: `_ReadProductCatalogUrl`
- `0x18002a5c6`: `ProductCatalogUrl fetched from cache: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _ReadProductCatalogUrl(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1)
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
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, (const WCHAR **)off_180048590, v2);
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
        (void *)0xFDC,
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
      0xFE5u,
      "_ReadProductCatalogUrl",
      -1,
      L"Exception while reading ProductCatalogUrl from OneSettings",
      0,
      0);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002a4a0  mov     [rsp+arg_8], rbx
0x18002a4a5  push    rdi
0x18002a4a6  sub     rsp, 90h
0x18002a4ad  mov     rax, cs:__security_cookie
0x18002a4b4  xor     rax, rsp
0x18002a4b7  mov     [rsp+98h+var_10], rax
0x18002a4bf  mov     rdi, rcx
0x18002a4c2  mov     [rsp+98h+var_40], 0
0x18002a4ca  mov     [rsp+98h+string], 0
0x18002a4d3  mov     rax, [rcx]
0x18002a4d6  mov     rbx, [rax+48h]
0x18002a4da  xor     ecx, ecx; string
0x18002a4dc  call    cs:__imp_WindowsDeleteString
0x18002a4e2  mov     [rsp+98h+string], 0
0x18002a4eb  lea     rdx, off_180048590; "PRODUCTCATALOGURL"
0x18002a4f2  lea     rcx, [rsp+98h+var_30]
0x18002a4f7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002a4fc  nop
0x18002a4fd  lea     r8, [rsp+98h+string]
0x18002a502  mov     rdx, [rax+18h]
0x18002a506  mov     rcx, rdi
0x18002a509  mov     rax, rbx
0x18002a50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a511  mov     ebx, eax
0x18002a513  test    eax, eax
0x18002a515  jns     short loc_18002A546
0x18002a517  mov     rcx, [rsp+98h]; this
0x18002a51f  mov     r9d, eax; char *
0x18002a522  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002a529  mov     edx, 0FDCh; void *
0x18002a52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a533  nop
0x18002a534  mov     rcx, [rsp+98h+string]; string
0x18002a539  call    cs:__imp_WindowsDeleteString
0x18002a53f  mov     eax, ebx
0x18002a541  jmp     loc_18002A609
0x18002a546  mov     rcx, [rsp+98h+string]; string
0x18002a54b  test    rcx, rcx
0x18002a54e  jz      loc_18002A5F9
0x18002a554  xor     edx, edx; length
0x18002a556  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a55c  nop
0x18002a55d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a561  mov     r8, rbx
0x18002a564  mov     rdx, rax
0x18002a567  lea     rcx, [rsp+98h+var_38]
0x18002a56c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a571  mov     [rsp+98h+var_40], 2
0x18002a579  mov     rcx, [rsp+98h]; this
0x18002a581  cmp     [rsp+98h+var_38], 0
0x18002a587  jz      loc_18002A62A
0x18002a58d  lea     rdx, [rsp+98h+var_38]
0x18002a592  lea     rcx, qword_18006A530
0x18002a599  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002a59e  lea     rcx, [rsp+98h+var_38]
0x18002a5a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a5a8  mov     rax, cs:qword_18006A530
0x18002a5af  mov     [rsp+98h+var_58], rax
0x18002a5b4  mov     [rsp+98h+var_60], 0; unsigned __int16 *
0x18002a5bd  mov     [rsp+98h+var_68], 0; char *
0x18002a5c6  lea     rax, aProductcatalog; "ProductCatalogUrl fetched from cache: %"...
0x18002a5cd  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x18002a5d2  mov     [rsp+98h+var_78], ebx; int
0x18002a5d6  lea     r9, aReadproductcat; "_ReadProductCatalogUrl"
0x18002a5dd  mov     r8d, 0FE0h; unsigned int
0x18002a5e3  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002a5ea  mov     ecx, 4; unsigned int
0x18002a5ef  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002a5f4  mov     rcx, [rsp+98h+string]; string
0x18002a5f9  call    cs:__imp_WindowsDeleteString
0x18002a5ff  nop
0x18002a600  xor     eax, eax
0x18002a602  jmp     short loc_18002A609
0x18002a604  mov     eax, 80004005h
0x18002a609  mov     rcx, [rsp+98h+var_10]
0x18002a611  xor     rcx, rsp; StackCookie
0x18002a614  call    __security_check_cookie
0x18002a619  mov     rbx, [rsp+98h+arg_8]
0x18002a621  add     rsp, 90h
0x18002a628  pop     rdi
0x18002a629  retn
0x18002a62a  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002a631  mov     edx, 0FF8h; void *
0x18002a636  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
