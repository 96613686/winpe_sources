# RadioManager::_RefreshPreferredMediaManager(bool)

- ea: `0x180021d48`
- end: `0x180021f96`
- name: `?_RefreshPreferredMediaManager@RadioManager@@AEAAX_N@Z`
- size: `590`
- prototype: `void __fastcall(RadioManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001df88`
- `0x18002036c`

## callees

- `0x1800043d8`
- `0x180006200`
- `0x180006a0c`
- `0x180009614`
- `0x18000a6a0`
- `0x18000a9c0`
- `0x18000acd0`
- `0x18000b814`
- `0x18000c15c`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180021d48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f05`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180021ec2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180021ec2`

## string_xrefs

- `0x180021e62`: `Considering media manager NOT ignored because Modern APM is disabled via registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RadioManager::_RefreshPreferredMediaManager(char **this, char a2)
{
  RadioManager *v2; // r14
  char *v3; // r15
  char *v4; // rbx
  __m128i si128; // xmm6
  bool v6; // si
  __int64 PersistentRegPathRMRadioIgnoredState; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  RMAPI *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  wil *v14; // rcx
  wil *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  bool v20; // [rsp+40h] [rbp-F8h]
  const wchar_t *v21; // [rsp+48h] [rbp-F0h] BYREF
  struct _GUID *v22; // [rsp+50h] [rbp-E8h] BYREF
  const wchar_t *v23; // [rsp+58h] [rbp-E0h] BYREF
  char *v24; // [rsp+60h] [rbp-D8h] BYREF
  RadioManager *v25; // [rsp+68h] [rbp-D0h]
  char *v26; // [rsp+70h] [rbp-C8h]
  __int64 v27; // [rsp+78h] [rbp-C0h] BYREF
  __m128i v28; // [rsp+88h] [rbp-B0h]
  HKEY v29; // [rsp+98h] [rbp-A0h] BYREF
  struct _GUID v30; // [rsp+A0h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-88h] BYREF

  v2 = (RadioManager *)this;
  v25 = (RadioManager *)this;
  v30 = GUID_NULL;
  v3 = this[39];
  v4 = this[38];
  if ( v4 != v3 )
  {
    if ( a2 )
    {
LABEL_15:
      v30 = *(struct _GUID *)(*(_QWORD *)v4 + 72LL);
    }
    else
    {
      v24 = this[39];
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        v26 = v4;
        if ( v4 == v3 )
          break;
        try
        {
          v6 = 0;
          v20 = 0;
          v29 = 0;
          PersistentRegPathRMRadioIgnoredState = RMAPI::GetPersistentRegPathRMRadioIgnoredState(&v27);
          v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioIgnoredState);
          WcmCommon::Registry::CreateKeyRO(&v29, v9, v8);
          if ( v28.m128i_i64[1] > 7uLL )
            std::_Deallocate<16>(v27, 2 * v28.m128i_i64[1] + 2);
          v28 = si128;
          LOWORD(v27) = 0;
          if ( RMAPI::IsModernAirplaneModeDisabled(v10) )
          {
            if ( (unsigned int)dword_180037050 > 4 )
            {
              v21 = (const wchar_t *)RmGuidToMediaTypeString(&v30);
              v22 = &v30;
              v23 = (const wchar_t *)"Considering media manager NOT ignored because Modern APM is disabled via registry";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
                v11,
                (unsigned __int8 *)word_18002F46A,
                v12,
                v13,
                &v23,
                (__int64 *)&v22,
                &v21);
            }
          }
          else
          {
            memset_0(sz, 0, 0x4Eu);
            StringFromGUID2((const GUID *const)(*(_QWORD *)v4 + 72LL), sz, 39);
            v6 = WcmCommon::Registry::Key::GetQwordValue(&v29, sz) != 0;
            v20 = v6;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
        }
        catch ( ... )
        {
          if ( (unsigned int)wil::ResultFromCaughtException(v14) != -2147024894 )
          {
            v16 = wil::ResultFromCaughtException(v15);
            if ( (unsigned int)dword_180037050 > 2 )
            {
              LODWORD(v29) = v16;
              v23 = (const wchar_t *)RmGuidToMediaTypeString(&v30);
              v22 = &v30;
              v21 = (const wchar_t *)"Exception thrown accessing the SystemRadioStateIgnored registry key - preferred med"
                                     "ia radio type might be an ignored media radio type";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned __int8 *)byte_18002F401,
                v18,
                v19,
                &v21,
                (__int64 *)&v22,
                &v23,
                (__int64)&v29);
            }
            v2 = v25;
            break;
          }
          v4 = v26;
          v3 = v24;
          v6 = v20;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          v2 = v25;
        }
        if ( !v6 )
          goto LABEL_15;
        v4 += 8;
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 48));
  v24 = (char *)v2 + 48;
  *(struct _GUID *)((char *)v2 + 124) = v30;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v24);
}

```

## disassembly

```asm
0x180021d48  mov     rax, rsp
0x180021d4b  mov     [rax+10h], rbx
0x180021d4f  mov     [rax+18h], rsi
0x180021d53  push    rdi
0x180021d54  push    r14
0x180021d56  push    r15
0x180021d58  sub     rsp, 120h
0x180021d5f  movaps  xmmword ptr [rax-28h], xmm6
0x180021d63  mov     rax, cs:__security_cookie
0x180021d6a  xor     rax, rsp
0x180021d6d  mov     [rsp+138h+var_38], rax
0x180021d75  mov     r14, rcx
0x180021d78  mov     [rsp+138h+var_D0], rcx
0x180021d7d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180021d84  movdqu  xmmword ptr [rsp+138h+var_98.Data1], xmm0
0x180021d8d  mov     r15, [rcx+138h]
0x180021d94  mov     rbx, [rcx+130h]
0x180021d9b  cmp     rbx, r15
0x180021d9e  jz      loc_180021EFE
0x180021da4  xor     edi, edi
0x180021da6  test    dl, dl
0x180021da8  jnz     loc_180021F78
0x180021dae  mov     [rsp+138h+var_D8], r15
0x180021db3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180021dbb  mov     [rsp+138h+var_C8], rbx
0x180021dc0  cmp     rbx, r15
0x180021dc3  jz      loc_180021EFE
0x180021dc9  mov     sil, dil
0x180021dcc  mov     [rsp+138h+var_F8], dil
0x180021dd1  mov     [rsp+138h+var_A0], rdi
0x180021dd9  lea     rcx, [rsp+138h+var_C0]
0x180021dde  call    ?GetPersistentRegPathRMRadioIgnoredState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioIgnoredState(void)
0x180021de3  nop
0x180021de4  mov     rcx, rax
0x180021de7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021dec  mov     r8, rax
0x180021def  lea     rcx, [rsp+138h+var_A0]
0x180021df7  call    ?CreateKeyRO@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRO(HKEY__ * const,wchar_t const * const)
0x180021dfc  nop
0x180021dfd  mov     rdx, [rsp+138h+var_A8]
0x180021e05  cmp     rdx, 7
0x180021e09  jbe     short loc_180021E1D
0x180021e0b  lea     rdx, ds:2[rdx*2]
0x180021e13  mov     rcx, [rsp+138h+var_C0]
0x180021e18  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021e1d  movdqu  xmmword ptr [rsp+88h], xmm6
0x180021e26  mov     word ptr [rsp+138h+var_C0], di
0x180021e2b  call    ?IsModernAirplaneModeDisabled@RMAPI@@YA_NXZ; RMAPI::IsModernAirplaneModeDisabled(void)
0x180021e30  test    al, al
0x180021e32  jz      short loc_180021E9A
0x180021e34  mov     eax, cs:dword_180037050
0x180021e3a  cmp     eax, 4
0x180021e3d  jbe     loc_180021EE9
0x180021e43  lea     rcx, [rsp+138h+var_98]; struct _GUID *
0x180021e4b  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180021e50  mov     [rsp+138h+var_F0], rax
0x180021e55  lea     rax, [rsp+138h+var_98]
0x180021e5d  mov     [rsp+138h+var_E8], rax
0x180021e62  lea     rax, aConsideringMed; "Considering media manager NOT ignored b"...
0x180021e69  mov     [rsp+138h+var_E0], rax
0x180021e6e  lea     rax, [rsp+138h+var_F0]
0x180021e73  mov     [rsp+138h+var_108], rax
0x180021e78  lea     rax, [rsp+138h+var_E8]
0x180021e7d  mov     [rsp+138h+var_110], rax
0x180021e82  lea     rax, [rsp+138h+var_E0]
0x180021e87  mov     [rsp+138h+var_118], rax
0x180021e8c  lea     rdx, word_18002F46A
0x180021e93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180021e98  jmp     short loc_180021EE9
0x180021e9a  xor     edx, edx; Val
0x180021e9c  lea     r8d, [rdx+4Eh]; Size
0x180021ea0  lea     rcx, [rsp+138h+sz]; void *
0x180021ea8  call    memset_0
0x180021ead  mov     rcx, [rbx]
0x180021eb0  add     rcx, 48h ; 'H'; rguid
0x180021eb4  mov     r8d, 27h ; '''; cchMax
0x180021eba  lea     rdx, [rsp+138h+sz]; lpsz
0x180021ec2  call    cs:__imp_StringFromGUID2
0x180021ec8  lea     rdx, [rsp+138h+sz]; wchar_t *
0x180021ed0  lea     rcx, [rsp+138h+var_A0]; this
0x180021ed8  call    ?GetQwordValue@Key@Registry@WcmCommon@@QEBA_KQEB_W@Z; WcmCommon::Registry::Key::GetQwordValue(wchar_t const * const)
0x180021edd  test    rax, rax
0x180021ee0  setnz   sil
0x180021ee4  mov     [rsp+138h+var_F8], sil
0x180021ee9  lea     rcx, [rsp+138h+var_A0]
0x180021ef1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180021ef6  nop
0x180021ef7  jmp     short loc_180021F73
0x180021ef9  mov     r14, [rsp+138h+var_D0]
0x180021efe  lea     rbx, [r14+30h]
0x180021f02  mov     rcx, rbx; lpCriticalSection
0x180021f05  call    cs:__imp_EnterCriticalSection
0x180021f0b  mov     [rsp+138h+var_D8], rbx
0x180021f10  movups  xmm0, xmmword ptr [rsp+138h+var_98.Data1]
0x180021f18  movdqu  xmmword ptr [rbx+4Ch], xmm0
0x180021f1d  lea     rcx, [rsp+138h+var_D8]
0x180021f22  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180021f27  mov     rcx, [rsp+138h+var_38]
0x180021f2f  xor     rcx, rsp; StackCookie
0x180021f32  call    __security_check_cookie
0x180021f37  lea     r11, [rsp+138h+var_18]
0x180021f3f  mov     rbx, [r11+28h]
0x180021f43  mov     rsi, [r11+30h]
0x180021f47  movaps  xmm6, xmmword ptr [r11-10h]
0x180021f4c  mov     rsp, r11
0x180021f4f  pop     r15
0x180021f51  pop     r14
0x180021f53  pop     rdi
0x180021f54  retn
0x180021f55  xor     edi, edi
0x180021f57  mov     rbx, [rsp+138h+var_C8]
0x180021f5c  mov     r15, [rsp+138h+var_D8]
0x180021f61  mov     sil, [rsp+138h+var_F8]
0x180021f66  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180021f6e  mov     r14, [rsp+138h+var_D0]
0x180021f73  test    sil, sil
0x180021f76  jnz     short loc_180021F8D
0x180021f78  mov     rax, [rbx]
0x180021f7b  movups  xmm0, xmmword ptr [rax+48h]
0x180021f7f  movdqu  xmmword ptr [rsp+138h+var_98.Data1], xmm0
0x180021f88  jmp     loc_180021EFE
0x180021f8d  add     rbx, 8
0x180021f91  jmp     loc_180021DBB
```
