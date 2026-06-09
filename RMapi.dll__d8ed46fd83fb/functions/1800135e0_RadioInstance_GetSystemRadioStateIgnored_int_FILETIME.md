# RadioInstance::GetSystemRadioStateIgnored(int *,_FILETIME *)

- ea: `0x1800135e0`
- end: `0x180013796`
- name: `?GetSystemRadioStateIgnored@RadioInstance@@UEAAJPEAHPEAU_FILETIME@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(RadioInstance *__hidden this, int *, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800043d8`
- `0x180006200`
- `0x180006a0c`
- `0x180009614`
- `0x18000a6a0`
- `0x18000a9c0`
- `0x18000acd0`
- `0x18000b814`
- `0x18000be90`
- `0x18000c15c`
- `0x18000d2a0`
- `0x18000df4c`
- `0x1800135e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013720`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013720`

## string_xrefs

- `0x1800136b3`: `Considering radio instance NOT ignored because Modern APM is disabled via registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RadioInstance::GetSystemRadioStateIgnored(RadioInstance *this, int *a2, struct _FILETIME *a3)
{
  __int64 PersistentRegPathRMRadioIgnoredState; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  RMAPI *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 QwordValue; // rax
  __int64 v15; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v16[2]; // [rsp+50h] [rbp-B8h] BYREF
  const wchar_t *v17; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+68h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+78h] [rbp-90h]
  HKEY v20; // [rsp+88h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-78h] BYREF

  v16[1] = (const wchar_t *)this;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v20 = 0;
    PersistentRegPathRMRadioIgnoredState = RMAPI::GetPersistentRegPathRMRadioIgnoredState(&v18);
    v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioIgnoredState);
    WcmCommon::Registry::CreateKeyRO(&v20, v8, v7);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v18, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v18) = 0;
    if ( RMAPI::IsModernAirplaneModeDisabled(v9) )
    {
      if ( (unsigned int)dword_180037050 > 4 )
      {
        v17 = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)((char *)this + 120));
        v15 = v10;
        v16[0] = (const wchar_t *)"Considering radio instance NOT ignored because Modern APM is disabled via registry";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v10,
          (unsigned __int8 *)&unk_18002E480,
          v11,
          v12,
          v16,
          &v15,
          &v17);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
      return 0;
    }
    else
    {
      memset_0(sz, 0, 0x4Eu);
      StringFromGUID2((const GUID *const)((char *)this + 120), sz, 39);
      QwordValue = WcmCommon::Registry::Key::GetQwordValue(&v20, sz);
      if ( QwordValue )
      {
        *a2 = 1;
        *a3 = (struct _FILETIME)QwordValue;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
      return 0;
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800135e0  mov     r11, rsp
0x1800135e3  mov     [r11+20h], rbx
0x1800135e7  push    rsi
0x1800135e8  push    rdi
0x1800135e9  push    r14
0x1800135eb  sub     rsp, 0F0h
0x1800135f2  mov     rax, cs:__security_cookie
0x1800135f9  xor     rax, rsp
0x1800135fc  mov     [rsp+108h+var_28], rax
0x180013604  mov     rdi, r8
0x180013607  mov     rsi, rdx
0x18001360a  mov     r14, rcx
0x18001360d  mov     [rsp+108h+var_B0], rcx
0x180013612  test    rdx, rdx
0x180013615  jz      loc_180013767
0x18001361b  test    r8, r8
0x18001361e  jz      loc_180013767
0x180013624  xor     ebx, ebx
0x180013626  mov     [rsp+108h+var_C8], ebx
0x18001362a  mov     [rdx], ebx
0x18001362c  mov     [r8], rbx
0x18001362f  mov     [r11-80h], rbx
0x180013633  lea     rcx, [rsp+108h+var_A0]
0x180013638  call    ?GetPersistentRegPathRMRadioIgnoredState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioIgnoredState(void)
0x18001363d  nop
0x18001363e  mov     rcx, rax
0x180013641  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013646  mov     r8, rax
0x180013649  lea     rcx, [rsp+108h+var_80]
0x180013651  call    ?CreateKeyRO@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRO(HKEY__ * const,wchar_t const * const)
0x180013656  nop
0x180013657  mov     rdx, [rsp+108h+var_88]
0x18001365f  cmp     rdx, 7
0x180013663  jbe     short loc_180013677
0x180013665  lea     rdx, ds:2[rdx*2]
0x18001366d  mov     rcx, [rsp+108h+var_A0]
0x180013672  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013677  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001367f  movdqu  xmmword ptr [rsp+78h], xmm0
0x180013685  xor     eax, eax
0x180013687  mov     word ptr [rsp+108h+var_A0], ax
0x18001368c  call    ?IsModernAirplaneModeDisabled@RMAPI@@YA_NXZ; RMAPI::IsModernAirplaneModeDisabled(void)
0x180013691  test    al, al
0x180013693  jz      short loc_1800136FB
0x180013695  mov     eax, cs:dword_180037050
0x18001369b  cmp     eax, 4
0x18001369e  jbe     short loc_1800136EA
0x1800136a0  lea     rcx, [r14+78h]; struct _GUID *
0x1800136a4  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x1800136a9  mov     [rsp+108h+var_A8], rax
0x1800136ae  mov     [rsp+108h+var_C0], rcx
0x1800136b3  lea     rax, aConsideringRad; "Considering radio instance NOT ignored "...
0x1800136ba  mov     [rsp+108h+var_B8], rax
0x1800136bf  lea     rax, [rsp+108h+var_A8]
0x1800136c4  mov     [rsp+108h+var_D8], rax
0x1800136c9  lea     rax, [rsp+108h+var_C0]
0x1800136ce  mov     [rsp+108h+var_E0], rax
0x1800136d3  lea     rax, [rsp+108h+var_B8]
0x1800136d8  mov     [rsp+108h+var_E8], rax
0x1800136dd  lea     rdx, unk_18002E480
0x1800136e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x1800136e9  nop
0x1800136ea  lea     rcx, [rsp+108h+var_80]
0x1800136f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800136f7  xor     eax, eax
0x1800136f9  jmp     short loc_180013771
0x1800136fb  xor     edx, edx; Val
0x1800136fd  lea     r8d, [rdx+4Eh]; Size
0x180013701  lea     rcx, [rsp+108h+sz]; void *
0x180013709  call    memset_0
0x18001370e  lea     rcx, [r14+78h]; rguid
0x180013712  mov     r8d, 27h ; '''; cchMax
0x180013718  lea     rdx, [rsp+108h+sz]; lpsz
0x180013720  call    cs:__imp_StringFromGUID2
0x180013726  lea     rdx, [rsp+108h+sz]; wchar_t *
0x18001372e  lea     rcx, [rsp+108h+var_80]; this
0x180013736  call    ?GetQwordValue@Key@Registry@WcmCommon@@QEBA_KQEB_W@Z; WcmCommon::Registry::Key::GetQwordValue(wchar_t const * const)
0x18001373b  test    rax, rax
0x18001373e  jz      short loc_18001374F
0x180013740  mov     dword ptr [rsi], 1
0x180013746  mov     [rdi], eax
0x180013748  shr     rax, 20h
0x18001374c  mov     [rdi+4], eax
0x18001374f  lea     rcx, [rsp+108h+var_80]
0x180013757  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001375c  nop
0x18001375d  jmp     short loc_180013763
0x18001375f  mov     ebx, [rsp+108h+var_C8]
0x180013763  mov     eax, ebx
0x180013765  jmp     short loc_180013771
0x180013767  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001376c  mov     eax, 80070057h
0x180013771  mov     rcx, [rsp+108h+var_28]
0x180013779  xor     rcx, rsp; StackCookie
0x18001377c  call    __security_check_cookie
0x180013781  mov     rbx, [rsp+108h+arg_18]
0x180013789  add     rsp, 0F0h
0x180013790  pop     r14
0x180013792  pop     rdi
0x180013793  pop     rsi
0x180013794  retn
```
