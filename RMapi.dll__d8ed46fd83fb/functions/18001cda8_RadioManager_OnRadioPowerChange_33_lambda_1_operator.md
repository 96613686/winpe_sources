# _RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()

- ea: `0x18001cda8`
- end: `0x18001d182`
- name: `_RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()`
- size: `986`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020d00`

## callees

- `0x180001d54`
- `0x1800043d8`
- `0x180006a0c`
- `0x180006c2c`
- `0x1800082cc`
- `0x18000a6a0`
- `0x18000b814`
- `0x18000b960`
- `0x18000c15c`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180019e30`
- `0x18001cda8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d037`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d037`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001ce65`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001ce65`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cf01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cf01`

## string_xrefs

- `0x18001cfaa`: `Updated ignored state`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()(const wchar_t *a1)
{
  struct _GUID *v1; // rsi
  signed int v2; // r14d
  __int64 PersistentRegPathRMRadioIgnoredState; // rax
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  wil *v7; // rcx
  bool v8; // r15
  char v9; // r12
  bool v10; // bl
  const char *v11; // rax
  __int64 v12; // rcx
  wil *v13; // rcx
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  __int64 v15; // rax
  _QWORD **v16; // rbx
  _QWORD **v17; // r15
  _QWORD *v18; // rcx
  _QWORD *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  const wchar_t *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  DWORD v27; // ecx
  const wchar_t *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  bool v31; // [rsp+50h] [rbp-138h]
  bool v32; // [rsp+51h] [rbp-137h]
  char v33; // [rsp+52h] [rbp-136h]
  const char *v34; // [rsp+58h] [rbp-130h] BYREF
  const wchar_t *v35; // [rsp+60h] [rbp-128h] BYREF
  const wchar_t *v36; // [rsp+68h] [rbp-120h] BYREF
  wchar_t *v37; // [rsp+70h] [rbp-118h] BYREF
  __int64 v38; // [rsp+78h] [rbp-110h] BYREF
  __m128i si128; // [rsp+88h] [rbp-100h]
  _QWORD v40[8]; // [rsp+98h] [rbp-F0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D8h] [rbp-B0h] BYREF
  const char *v42; // [rsp+E0h] [rbp-A8h] BYREF
  struct _RTL_CRITICAL_SECTION *v43; // [rsp+E8h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+F0h] [rbp-98h] BYREF

  try
  {
    v1 = (struct _GUID *)a1;
    v37 = (wchar_t *)a1;
    v2 = 0;
    v43 = 0;
    PersistentRegPathRMRadioIgnoredState = RMAPI::GetPersistentRegPathRMRadioIgnoredState(&v38);
    v4 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioIgnoredState);
    WcmCommon::Registry::CreateKeyRW(&v43, v5, v4);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v38, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v38) = 0;
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(v1, sz, 39);
    try
    {
      v9 = 0;
      v33 = 0;
      v40[0] = ___7___Func_impl_no_alloc_V_lambda_1___1____TryGetQwordValue_H_Key_Registry_WcmCommon__QEBA_KQEB_WAEBH_Z__K__V_std__6B_;
      v40[1] = &v43;
      v40[2] = sz;
      v40[7] = v40;
      v8 = WcmCommon::Registry::Key::ThrowIfValueNotFound<unsigned __int64,int>(v6, v40, 0) != 0;
      v32 = v8;
    }
    catch ( ... )
    {
      if ( (unsigned int)wil::ResultFromCaughtException(v7) != -2147024894 )
      {
        v33 = 1;
        if ( (unsigned int)dword_180037050 > 2 )
        {
          SystemTimeAsFileTime.dwLowDateTime = 0;
          v35 = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)v37);
          v36 = v24;
          v34 = "Exception thrown accessing the SystemRadioStateIgnored registry key to read state";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (__int64)v24,
            (unsigned __int8 *)word_18002FA12,
            v25,
            v26,
            (const wchar_t **)&v34,
            (__int64 *)&v36,
            &v35,
            (__int64)&SystemTimeAsFileTime);
        }
      }
      v2 = 0;
      v8 = v32;
      v9 = v33;
      v1 = (struct _GUID *)v37;
    }
    if ( v1[1].Data1 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      WcmCommon::Registry::Key::SetQwordValue((HKEY *)&v43, sz, *(_QWORD *)&SystemTimeAsFileTime);
      v10 = 1;
    }
    else
    {
      WcmCommon::Registry::Key::SetQwordValue((HKEY *)&v43, sz, 0);
      v10 = v8;
    }
    v31 = v10;
    if ( (unsigned int)dword_180037050 > 4 )
    {
      SystemTimeAsFileTime.dwLowDateTime = v1[1].Data1;
      if ( v9 )
      {
        v11 = "unknown";
      }
      else
      {
        v11 = "true";
        if ( !v8 )
          v11 = "false";
      }
      v34 = v11;
      v36 = (const wchar_t *)RmGuidToMediaTypeString(v1);
      v35 = (const wchar_t *)v1;
      v42 = "Updated ignored state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        byte_18002F99B);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
  }
  catch ( ... )
  {
    v27 = wil::ResultFromCaughtException(v13);
    LODWORD(v42) = v27;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      SystemTimeAsFileTime.dwLowDateTime = v27;
      v34 = RmGuidToMediaTypeString((const struct _GUID *)v37);
      v36 = v28;
      v35 = (const wchar_t *)"Exception thrown accessing the SystemRadioStateIgnored registry key to set state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)v28,
        (unsigned __int8 *)byte_18002F93D,
        v29,
        v30,
        &v35,
        (__int64 *)&v36,
        (const wchar_t **)&v34,
        (__int64)&SystemTimeAsFileTime);
    }
    v2 = (int)v42;
    v10 = v31;
    v1 = (struct _GUID *)v37;
  }
  if ( v10 )
  {
    v14 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)v1[1].Data4 + 240LL);
    EnterCriticalSection(v14);
    v43 = v14;
    v15 = *(_QWORD *)v1[1].Data4;
    v16 = *(_QWORD ***)(v15 + 304);
    v17 = *(_QWORD ***)(v15 + 312);
    while ( v16 != v17 )
    {
      v18 = *v16;
      if ( (*v16)[9] == *(_QWORD *)&v1->Data1 && v18[10] == *(_QWORD *)v1->Data4 )
      {
        LODWORD(v42) = 0;
        v2 = (*(__int64 (__fastcall **)(_QWORD, const char **))(*(_QWORD *)*v18 + 64LL))(*v18, &v42);
        if ( v2 < 0 )
        {
          if ( (unsigned int)dword_180037050 > 2 )
          {
            SystemTimeAsFileTime.dwLowDateTime = v2;
            v34 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*v16 + 5);
            v36 = (const wchar_t *)RmGuidToMediaTypeString(v1);
            v35 = (const wchar_t *)v1;
            v37 = (wchar_t *)"Failed to notify radio instance of a change";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
              v20,
              (unsigned __int8 *)byte_18002F8D3,
              v21,
              v22,
              (const wchar_t **)&v37,
              (__int64 *)&v35,
              &v36,
              (__int64 **)&v34,
              (__int64)&SystemTimeAsFileTime);
          }
        }
        else
        {
          v19 = *v16;
          LOBYTE(v19) = *((_BYTE *)*v16 + 88);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)**v16 + 40LL))(**v16, (unsigned int)v42, v19);
        }
      }
      ++v16;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v43);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001cda8  push    rbx
0x18001cdaa  push    rsi
0x18001cdab  push    rdi
0x18001cdac  push    r12
0x18001cdae  push    r14
0x18001cdb0  push    r15
0x18001cdb2  sub     rsp, 158h
0x18001cdb9  mov     rax, cs:__security_cookie
0x18001cdc0  xor     rax, rsp
0x18001cdc3  mov     [rsp+188h+var_48], rax
0x18001cdcb  mov     rsi, rcx
0x18001cdce  mov     [rsp+188h+var_118], rcx
0x18001cdd3  xor     edi, edi
0x18001cdd5  mov     r14d, edi
0x18001cdd8  mov     bl, dil
0x18001cddb  mov     [rsp+188h+var_138], bl
0x18001cddf  mov     [rsp+188h+var_A0], rdi
0x18001cde7  lea     rcx, [rsp+188h+var_110]
0x18001cdec  call    ?GetPersistentRegPathRMRadioIgnoredState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioIgnoredState(void)
0x18001cdf1  nop
0x18001cdf2  mov     rcx, rax
0x18001cdf5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cdfa  mov     r8, rax
0x18001cdfd  lea     rcx, [rsp+188h+var_A0]
0x18001ce05  call    ?CreateKeyRW@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRW(HKEY__ * const,wchar_t const * const)
0x18001ce0a  nop
0x18001ce0b  mov     rdx, [rsp+188h+var_F8]
0x18001ce13  cmp     rdx, 7
0x18001ce17  jbe     short loc_18001CE2B
0x18001ce19  lea     rdx, ds:2[rdx*2]
0x18001ce21  mov     rcx, [rsp+188h+var_110]
0x18001ce26  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ce2b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001ce33  movdqu  xmmword ptr [rsp+88h], xmm0
0x18001ce3c  mov     word ptr [rsp+188h+var_110], di
0x18001ce41  xor     edx, edx; Val
0x18001ce43  lea     r8d, [rdx+4Eh]; Size
0x18001ce47  lea     rcx, [rsp+188h+sz]; void *
0x18001ce4f  call    memset_0
0x18001ce54  mov     r8d, 27h ; '''; cchMax
0x18001ce5a  lea     rdx, [rsp+188h+sz]; lpsz
0x18001ce62  mov     rcx, rsi; rguid
0x18001ce65  call    cs:__imp_StringFromGUID2
0x18001ce6b  mov     [rsp+188h+var_137], dil
0x18001ce70  mov     r12b, dil
0x18001ce73  mov     [rsp+188h+var_136], dil
0x18001ce78  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???$TryGetQwordValue@H@Key@Registry@WcmCommon@@QEBA_KQEB_WAEBH@Z@_K$$V@std@@6B@; const std::_Func_impl_no_alloc<`WcmCommon::Registry::Key::TryGetQwordValue<int>(wchar_t const * const,int const &)'::`2'::_lambda_1_,unsigned __int64,>::`vftable'
0x18001ce7f  mov     [rsp+188h+var_F0], rax
0x18001ce87  lea     rax, [rsp+188h+var_A0]
0x18001ce8f  mov     [rsp+188h+var_E8], rax
0x18001ce97  lea     rax, [rsp+188h+sz]
0x18001ce9f  mov     [rsp+188h+var_E0], rax
0x18001cea7  lea     rax, [rsp+188h+var_F0]
0x18001ceaf  mov     [rsp+188h+var_B8], rax
0x18001ceb7  xor     r8d, r8d
0x18001ceba  lea     rdx, [rsp+188h+var_F0]
0x18001cec2  call    ??$ThrowIfValueNotFound@_KH@Key@Registry@WcmCommon@@AEBA_KV?$function@$$A6A_KXZ@std@@H@Z; WcmCommon::Registry::Key::ThrowIfValueNotFound<unsigned __int64,int>(std::function<unsigned __int64 (void)>,int)
0x18001cec7  test    rax, rax
0x18001ceca  setnz   r15b
0x18001cece  mov     [rsp+188h+var_137], r15b
0x18001ced3  jmp     short loc_18001CEEC
0x18001ced5  xor     edi, edi
0x18001ced7  mov     r14d, edi
0x18001ceda  mov     bl, dil
0x18001cedd  mov     r15b, [rsp+188h+var_137]
0x18001cee2  mov     r12b, [rsp+188h+var_136]
0x18001cee7  mov     rsi, [rsp+188h+var_118]
0x18001ceec  cmp     [rsi+10h], edi
0x18001ceef  jz      short loc_18001CF2B
0x18001cef1  mov     qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18001cef9  lea     rcx, [rsp+188h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001cf01  call    cs:__imp_GetSystemTimeAsFileTime
0x18001cf07  mov     r8, qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime]; unsigned __int64
0x18001cf0f  lea     rdx, [rsp+188h+sz]; wchar_t *
0x18001cf17  lea     rcx, [rsp+188h+var_A0]; this
0x18001cf1f  call    ?SetQwordValue@Key@Registry@WcmCommon@@QEAAXQEB_W_K@Z; WcmCommon::Registry::Key::SetQwordValue(wchar_t const * const,unsigned __int64)
0x18001cf24  mov     ebx, 1
0x18001cf29  jmp     short loc_18001CF53
0x18001cf2b  xor     r8d, r8d; unsigned __int64
0x18001cf2e  lea     rdx, [rsp+188h+sz]; wchar_t *
0x18001cf36  lea     rcx, [rsp+188h+var_A0]; this
0x18001cf3e  call    ?SetQwordValue@Key@Registry@WcmCommon@@QEAAXQEB_W_K@Z; WcmCommon::Registry::Key::SetQwordValue(wchar_t const * const,unsigned __int64)
0x18001cf43  movzx   eax, bl
0x18001cf46  mov     ebx, 1
0x18001cf4b  test    r15b, r15b
0x18001cf4e  cmovnz  eax, ebx
0x18001cf51  mov     bl, al
0x18001cf53  mov     [rsp+188h+var_138], bl
0x18001cf57  mov     eax, cs:dword_180037050
0x18001cf5d  cmp     eax, 4
0x18001cf60  jbe     loc_18001CFFE
0x18001cf66  mov     eax, [rsi+10h]
0x18001cf69  mov     [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18001cf70  test    r12b, r12b
0x18001cf73  jz      short loc_18001CF7E
0x18001cf75  lea     rax, aUnknown_0; "unknown"
0x18001cf7c  jmp     short loc_18001CF93
0x18001cf7e  lea     rax, aTrue_0; "true"
0x18001cf85  lea     rcx, aFalse; "false"
0x18001cf8c  test    r15b, r15b
0x18001cf8f  cmovz   rax, rcx
0x18001cf93  mov     [rsp+188h+var_130], rax
0x18001cf98  mov     rcx, rsi; struct _GUID *
0x18001cf9b  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001cfa0  mov     [rsp+188h+var_120], rax
0x18001cfa5  mov     [rsp+188h+var_128], rsi
0x18001cfaa  lea     rax, aUpdatedIgnored; "Updated ignored state"
0x18001cfb1  mov     [rsp+188h+var_A8], rax
0x18001cfb9  lea     rax, [rsp+188h+SystemTimeAsFileTime]
0x18001cfc1  mov     [rsp+188h+var_148], rax
0x18001cfc6  lea     rax, [rsp+188h+var_130]
0x18001cfcb  mov     [rsp+188h+var_150], rax
0x18001cfd0  lea     rax, [rsp+188h+var_120]
0x18001cfd5  mov     [rsp+188h+var_158], rax
0x18001cfda  lea     rax, [rsp+188h+var_128]
0x18001cfdf  mov     [rsp+188h+var_160], rax
0x18001cfe4  lea     rax, [rsp+188h+var_A8]
0x18001cfec  mov     [rsp+188h+var_168], rax
0x18001cff1  lea     rdx, byte_18002F99B
0x18001cff8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001cffd  nop
0x18001cffe  lea     rcx, [rsp+188h+var_A0]
0x18001d006  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001d00b  nop
0x18001d00c  jmp     short loc_18001D021
0x18001d00e  xor     edi, edi
0x18001d010  mov     r14d, dword ptr [rsp+188h+var_A8]
0x18001d018  mov     bl, [rsp+188h+var_138]
0x18001d01c  mov     rsi, [rsp+188h+var_118]
0x18001d021  test    bl, bl
0x18001d023  jz      loc_18001D15E
0x18001d029  mov     rbx, [rsi+18h]
0x18001d02d  add     rbx, 0F0h
0x18001d034  mov     rcx, rbx; lpCriticalSection
0x18001d037  call    cs:__imp_EnterCriticalSection
0x18001d03d  mov     [rsp+188h+var_A0], rbx
0x18001d045  mov     rax, [rsi+18h]
0x18001d049  mov     rbx, [rax+130h]
0x18001d050  mov     r15, [rax+138h]
0x18001d057  jmp     loc_18001D148
0x18001d05c  mov     rcx, [rbx]
0x18001d05f  mov     rax, [rcx+48h]
0x18001d063  cmp     rax, [rsi]
0x18001d066  jnz     loc_18001D144
0x18001d06c  mov     rax, [rcx+50h]
0x18001d070  cmp     rax, [rsi+8]
0x18001d074  jnz     loc_18001D144
0x18001d07a  mov     dword ptr [rsp+188h+var_A8], edi
0x18001d081  mov     rcx, [rcx]
0x18001d084  mov     rax, [rcx]
0x18001d087  lea     rdx, [rsp+188h+var_A8]
0x18001d08f  mov     rax, [rax+40h]
0x18001d093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d098  mov     r14d, eax
0x18001d09b  test    eax, eax
0x18001d09d  js      short loc_18001D0C1
0x18001d09f  mov     r8, [rbx]
0x18001d0a2  mov     rcx, [r8]
0x18001d0a5  mov     rdx, [rcx]
0x18001d0a8  mov     rax, [rdx+28h]
0x18001d0ac  mov     r8b, [r8+58h]
0x18001d0b0  mov     edx, dword ptr [rsp+188h+var_A8]
0x18001d0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0bc  jmp     loc_18001D144
0x18001d0c1  mov     eax, cs:dword_180037050
0x18001d0c7  cmp     eax, 2
0x18001d0ca  jbe     short loc_18001D144
0x18001d0cc  mov     [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], r14d
0x18001d0d4  mov     rcx, [rbx]
0x18001d0d7  add     rcx, 28h ; '('
0x18001d0db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d0e0  mov     [rsp+188h+var_130], rax
0x18001d0e5  mov     rcx, rsi; struct _GUID *
0x18001d0e8  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001d0ed  mov     [rsp+188h+var_120], rax
0x18001d0f2  mov     [rsp+188h+var_128], rsi
0x18001d0f7  lea     rax, aFailedToNotify; "Failed to notify radio instance of a ch"...
0x18001d0fe  mov     [rsp+188h+var_118], rax
0x18001d103  lea     rax, [rsp+188h+SystemTimeAsFileTime]
0x18001d10b  mov     [rsp+188h+var_148], rax
0x18001d110  lea     rax, [rsp+188h+var_130]
0x18001d115  mov     [rsp+188h+var_150], rax
0x18001d11a  lea     rax, [rsp+188h+var_120]
0x18001d11f  mov     [rsp+188h+var_158], rax
0x18001d124  lea     rax, [rsp+188h+var_128]
0x18001d129  mov     [rsp+188h+var_160], rax
0x18001d12e  lea     rax, [rsp+188h+var_118]
0x18001d133  mov     [rsp+188h+var_168], rax
0x18001d138  lea     rdx, byte_18002F8D3
0x18001d13f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001d144  add     rbx, 8
0x18001d148  cmp     rbx, r15
0x18001d14b  jnz     loc_18001D05C
0x18001d151  lea     rcx, [rsp+188h+var_A0]
0x18001d159  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001d15e  mov     eax, r14d
0x18001d161  mov     rcx, [rsp+188h+var_48]
0x18001d169  xor     rcx, rsp; StackCookie
0x18001d16c  call    __security_check_cookie
0x18001d171  add     rsp, 158h
0x18001d178  pop     r15
0x18001d17a  pop     r14
0x18001d17c  pop     r12
0x18001d17e  pop     rdi
0x18001d17f  pop     rsi
0x18001d180  pop     rbx
0x18001d181  retn
```
