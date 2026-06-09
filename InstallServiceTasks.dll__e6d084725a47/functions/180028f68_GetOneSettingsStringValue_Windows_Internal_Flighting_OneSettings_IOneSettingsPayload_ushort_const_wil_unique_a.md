# _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180028f68`
- end: `0x180029091`
- name: `?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e654`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x180010f50`
- `0x1800156a8`
- `0x1800202c4`
- `0x1800206dc`
- `0x180028f68`
- `0x1800291d8`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002905c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002905c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028fef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028fef`

## string_xrefs

- `0x18002907e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180029045`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall _GetOneSettingsStringValue(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int64 (__fastcall *v5)(__int64, PVOID, HSTRING *); // rbx
  char v6; // r8
  HSTRING_HEADER *v7; // rax
  int v8; // ebx
  char *StringRawBuffer; // rax
  const char *v10; // r9
  const char *v11; // r9
  int v12; // [rsp+20h] [rbp-98h]
  HSTRING string; // [rsp+50h] [rbp-68h] BYREF
  int v14; // [rsp+58h] [rbp-60h]
  void *v15; // [rsp+60h] [rbp-58h] BYREF
  const WCHAR *v16; // [rsp+68h] [rbp-50h] BYREF
  HSTRING_HEADER v17; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v16 = a2;
  v14 = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  string = 0;
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v17, &v16, v6);
  try
  {
    v8 = v5(a1, v7[1].Reserved.Reserved1, &string);
    if ( v8 >= 0 && string )
    {
      StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v15,
        StringRawBuffer,
        0xFFFFFFFFFFFFFFFFuLL,
        v10);
      v14 = 2;
      if ( !v15 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v11);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        a3,
        &v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
    }
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v8,
        v12);
    WindowsDeleteString(string);
  }
  catch ( ... )
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x207u,
      "_GetOneSettingsStringValue",
      -1,
      L"Exception while reading OneSettings value for %s, using default value",
      0,
      0,
      v16);
  }
}

```

## disassembly

```asm
0x180028f68  push    rbx
0x180028f6a  push    rsi
0x180028f6b  push    rdi
0x180028f6c  sub     rsp, 0A0h
0x180028f73  mov     rax, cs:__security_cookie
0x180028f7a  xor     rax, rsp
0x180028f7d  mov     [rsp+0B8h+var_28], rax
0x180028f85  mov     rdi, r8
0x180028f88  mov     rsi, rcx
0x180028f8b  mov     [rsp+0B8h+var_50], rdx
0x180028f90  mov     [rsp+0B8h+var_60], 0
0x180028f98  mov     [rsp+0B8h+string], 0
0x180028fa1  mov     rax, [rcx]
0x180028fa4  mov     rbx, [rax+48h]
0x180028fa8  xor     ecx, ecx; string
0x180028faa  call    cs:__imp_WindowsDeleteString
0x180028fb0  mov     [rsp+0B8h+string], 0
0x180028fb9  lea     rdx, [rsp+0B8h+var_50]
0x180028fbe  lea     rcx, [rsp+0B8h+var_48]
0x180028fc3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180028fc8  nop
0x180028fc9  lea     r8, [rsp+0B8h+string]
0x180028fce  mov     rdx, [rax+18h]
0x180028fd2  mov     rcx, rsi
0x180028fd5  mov     rax, rbx
0x180028fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fdd  mov     ebx, eax
0x180028fdf  test    eax, eax
0x180028fe1  js      short loc_180029036
0x180028fe3  mov     rcx, [rsp+0B8h+string]; string
0x180028fe8  test    rcx, rcx
0x180028feb  jz      short loc_180029036
0x180028fed  xor     edx, edx; length
0x180028fef  call    cs:__imp_WindowsGetStringRawBuffer
0x180028ff5  nop
0x180028ff6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028ffa  mov     rdx, rax
0x180028ffd  lea     rcx, [rsp+0B8h+var_58]
0x180029002  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180029007  mov     [rsp+0B8h+var_60], 2
0x18002900f  mov     rcx, [rsp+0B8h]; this
0x180029017  cmp     [rsp+0B8h+var_58], 0
0x18002901d  jz      short loc_18002907E
0x18002901f  lea     rdx, [rsp+0B8h+var_58]
0x180029024  mov     rcx, rdi
0x180029027  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002902c  lea     rcx, [rsp+0B8h+var_58]
0x180029031  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029036  mov     rcx, [rsp+0B8h]; this
0x18002903e  test    ebx, ebx
0x180029040  jns     short loc_180029057
0x180029042  mov     r9d, ebx; char *
0x180029045  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002904c  mov     edx, 203h; void *
0x180029051  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029056  nop
0x180029057  mov     rcx, [rsp+0B8h+string]; string
0x18002905c  call    cs:__imp_WindowsDeleteString
0x180029062  nop
0x180029063  mov     rcx, [rsp+0B8h+var_28]
0x18002906b  xor     rcx, rsp; StackCookie
0x18002906e  call    __security_check_cookie
0x180029073  add     rsp, 0A0h
0x18002907a  pop     rdi
0x18002907b  pop     rsi
0x18002907c  pop     rbx
0x18002907d  retn
0x18002907e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029085  mov     edx, 0FF8h; void *
0x18002908a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
