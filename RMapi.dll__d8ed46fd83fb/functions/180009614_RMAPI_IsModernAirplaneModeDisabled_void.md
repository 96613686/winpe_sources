# RMAPI::IsModernAirplaneModeDisabled(void)

- ea: `0x180009614`
- end: `0x180009705`
- name: `?IsModernAirplaneModeDisabled@RMAPI@@YA_NXZ`
- size: `241`
- prototype: `bool __fastcall(RMAPI *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800135e0`
- `0x18001f6c0`
- `0x180021d48`
- `0x1800222d0`

## callees

- `0x1800043d8`
- `0x180006a0c`
- `0x1800088e0`
- `0x180009614`
- `0x18000a6a0`
- `0x18000a9c0`
- `0x18000ac38`
- `0x18000c15c`
- `0x18000d2a0`

## string_xrefs

- `0x1800096b6`: `DisableModernAPM is Active (registry value is set to non-zero)`
- `0x1800096af`: `DisableModernAPM is Inactive (registry value is set to zero)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall RMAPI::IsModernAirplaneModeDisabled(RMAPI *this)
{
  __int64 PersistentRegPathRMRadioIgnoredState; // rax
  __int64 v2; // r8
  __int64 v3; // rdx
  bool v4; // bl
  __int64 v5; // r8
  __int64 v6; // r9
  const char *v7; // rax
  wil *v8; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  bool v13; // [rsp+30h] [rbp-48h]
  const wchar_t *v14; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  __m128i si128; // [rsp+50h] [rbp-28h]
  __int64 v17; // [rsp+60h] [rbp-18h] BYREF

  try
  {
    v17 = 0;
    PersistentRegPathRMRadioIgnoredState = RMAPI::GetPersistentRegPathRMRadioIgnoredState(&v15);
    v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioIgnoredState);
    WcmCommon::Registry::CreateKeyRO(&v17, v3, v2);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v15, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15) = 0;
    v4 = WcmCommon::Registry::Key::GetDwordValue((WcmCommon::Registry::Key *)&v17, L"DisableModernAPM") != 0;
    v13 = v4;
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v7 = "DisableModernAPM is Active (registry value is set to non-zero)";
      if ( !v4 )
        v7 = "DisableModernAPM is Inactive (registry value is set to zero)";
      v14 = (const wchar_t *)v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)"DisableModernAPM is Inactive (registry value is set to zero)",
        (unsigned __int8 *)byte_1800302F3,
        v5,
        v6,
        &v14);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
  }
  catch ( ... )
  {
    v10 = wil::ResultFromCaughtException(v8);
    if ( v10 != -2147024894 && (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v17) = v10;
      v14 = (const wchar_t *)"Exception accessing DisableModernAPM reg key!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_180037050,
        (unsigned __int8 *)word_1800302AA,
        v11,
        v12,
        &v14,
        (__int64)&v17);
    }
    return v13;
  }
  return v4;
}

```

## disassembly

```asm
0x180009614  push    rbx
0x180009616  sub     rsp, 70h
0x18000961a  mov     rax, cs:__security_cookie
0x180009621  xor     rax, rsp
0x180009624  mov     [rsp+78h+var_10], rax
0x180009629  mov     [rsp+78h+var_48], 0
0x18000962e  mov     [rsp+78h+var_18], 0
0x180009637  lea     rcx, [rsp+78h+var_38]
0x18000963c  call    ?GetPersistentRegPathRMRadioIgnoredState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioIgnoredState(void)
0x180009641  nop
0x180009642  mov     rcx, rax
0x180009645  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18000964a  mov     r8, rax
0x18000964d  lea     rcx, [rsp+78h+var_18]
0x180009652  call    ?CreateKeyRO@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRO(HKEY__ * const,wchar_t const * const)
0x180009657  nop
0x180009658  mov     rdx, [rsp+78h+var_20]
0x18000965d  cmp     rdx, 7
0x180009661  jbe     short loc_180009675
0x180009663  lea     rdx, ds:2[rdx*2]
0x18000966b  mov     rcx, [rsp+78h+var_38]
0x180009670  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009675  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18000967d  movdqu  xmmword ptr [rsp+50h], xmm0
0x180009683  xor     eax, eax
0x180009685  mov     word ptr [rsp+78h+var_38], ax
0x18000968a  lea     rdx, aDisablemoderna; "DisableModernAPM"
0x180009691  lea     rcx, [rsp+78h+var_18]; this
0x180009696  call    ?GetDwordValue@Key@Registry@WcmCommon@@QEBAKQEB_W@Z; WcmCommon::Registry::Key::GetDwordValue(wchar_t const * const)
0x18000969b  test    eax, eax
0x18000969d  setnz   bl
0x1800096a0  mov     [rsp+78h+var_48], bl
0x1800096a4  mov     eax, cs:dword_180037050
0x1800096aa  cmp     eax, 4
0x1800096ad  jbe     short loc_1800096DF
0x1800096af  lea     rcx, aDisablemoderna_1; "DisableModernAPM is Inactive (registry "...
0x1800096b6  lea     rax, aDisablemoderna_0; "DisableModernAPM is Active (registry va"...
0x1800096bd  test    bl, bl
0x1800096bf  cmovz   rax, rcx
0x1800096c3  mov     [rsp+78h+var_40], rax
0x1800096c8  lea     rax, [rsp+78h+var_40]
0x1800096cd  mov     [rsp+78h+var_58], rax
0x1800096d2  lea     rdx, byte_1800302F3
0x1800096d9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800096de  nop
0x1800096df  lea     rcx, [rsp+78h+var_18]
0x1800096e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800096e9  nop
0x1800096ea  jmp     short loc_1800096F0
0x1800096ec  mov     bl, [rsp+78h+var_48]
0x1800096f0  mov     al, bl
0x1800096f2  mov     rcx, [rsp+78h+var_10]
0x1800096f7  xor     rcx, rsp; StackCookie
0x1800096fa  call    __security_check_cookie
0x1800096ff  add     rsp, 70h
0x180009703  pop     rbx
0x180009704  retn
```
