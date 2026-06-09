# RadioManager::_SetSysRadio(bool,bool,MEDIA_RADIO_MANAGER *)

- ea: `0x1800222d0`
- end: `0x1800228d4`
- name: `?_SetSysRadio@RadioManager@@AEAAJ_N0PEAUMEDIA_RADIO_MANAGER@@@Z`
- size: `1540`
- prototype: `__int64 __fastcall(RadioManager *__hidden this, bool, bool, struct MEDIA_RADIO_MANAGER *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001df88`
- `0x18002036c`

## callees

- `0x180001140`
- `0x1800043d8`
- `0x180005ef0`
- `0x180006a0c`
- `0x180006a2c`
- `0x180009614`
- `0x18000a6a0`
- `0x18000a8fc`
- `0x18000a9c0`
- `0x18000acd0`
- `0x18000b180`
- `0x18000b814`
- `0x18000bf38`
- `0x18000c15c`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180019744`
- `0x18001ac60`
- `0x18001b968`
- `0x18001c23c`
- `0x1800222d0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180022470`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180022470`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x1800224e4`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x1800224e4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800224c1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800224c1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTimeEx` at `0x18002250d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTimeEx` at `0x18002250d`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18002253a`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800225b5`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18002253a`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800225b5`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18002255c`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800225e1`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18002255c`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800225e1`

## string_xrefs

- `0x1800223fc`: `Considering media manager NOT ignored because Modern APM is disabled via registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall RadioManager::_SetSysRadio(GUID *this, unsigned __int8 a2, char a3, struct MEDIA_RADIO_MANAGER *a4)
{
  __int64 v8; // rdi
  __int64 PersistentRegPathRMRadioIgnoredState; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  RMAPI *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  FILETIME QwordValue; // rax
  __int64 cchDate; // r14
  __int64 TimeFormat; // rsi
  WCHAR *lpDateStr; // rax
  WCHAR *v20; // rax
  __int64 v21; // rcx
  __m128i v22; // xmm0
  __int64 v24; // rax
  wil *v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  DWORD v30; // [rsp+50h] [rbp-378h]
  const wchar_t *v31; // [rsp+58h] [rbp-370h] BYREF
  const wchar_t *v32; // [rsp+60h] [rbp-368h] BYREF
  const wchar_t *v33; // [rsp+68h] [rbp-360h] BYREF
  __int64 v34; // [rsp+70h] [rbp-358h]
  const wchar_t *v35; // [rsp+78h] [rbp-350h] BYREF
  __int64 v36[2]; // [rsp+80h] [rbp-348h] BYREF
  GUID *p_rguid; // [rsp+90h] [rbp-338h] BYREF
  _QWORD v38[2]; // [rsp+98h] [rbp-330h] BYREF
  GUID si128; // [rsp+A8h] [rbp-320h]
  GUID *v40; // [rsp+B8h] [rbp-310h]
  FILETIME FileTime; // [rsp+C0h] [rbp-308h] BYREF
  GUID rguid; // [rsp+C8h] [rbp-300h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-2F0h] BYREF
  SYSTEMTIME Date; // [rsp+E0h] [rbp-2E8h] BYREF
  _QWORD v45[2]; // [rsp+F0h] [rbp-2D8h] BYREF
  __m128i v46; // [rsp+100h] [rbp-2C8h]
  __int64 v47; // [rsp+128h] [rbp-2A0h]
  _SYSTEMTIME SystemTime; // [rsp+130h] [rbp-298h] BYREF
  _QWORD v49[2]; // [rsp+140h] [rbp-288h] BYREF
  __m128i v50; // [rsp+150h] [rbp-278h]
  __int64 v51; // [rsp+178h] [rbp-250h]
  _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+180h] [rbp-248h] BYREF
  OLECHAR sz[48]; // [rsp+330h] [rbp-98h] BYREF

  p_rguid = this;
  v33 = (const wchar_t *)a4;
  v8 = *(_QWORD *)a4;
  v34 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  rguid = *(GUID *)((char *)a4 + 8);
  v30 = 0;
  if ( a3 )
    goto LABEL_31;
  v43 = 0;
  PersistentRegPathRMRadioIgnoredState = RMAPI::GetPersistentRegPathRMRadioIgnoredState(v38);
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioIgnoredState);
  WcmCommon::Registry::CreateKeyRO(&v43, v11, v10);
  if ( *(_QWORD *)si128.Data4 > 7u )
    std::_Deallocate<16>(v38[0], 2LL * *(_QWORD *)si128.Data4 + 2);
  si128 = (GUID)_mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38[0]) = 0;
  if ( RMAPI::IsModernAirplaneModeDisabled(v12) )
  {
    if ( (unsigned int)dword_180037050 > 2 )
    {
      FileTime.dwLowDateTime = 0;
      v35 = (const wchar_t *)RmGuidToMediaTypeString(&rguid);
      v36[0] = (__int64)&rguid;
      v31 = (const wchar_t *)"Considering media manager NOT ignored because Modern APM is disabled via registry";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)&dword_18002EDEC,
        v14,
        v15,
        &v31,
        v36,
        &v35,
        (__int64)&FileTime);
    }
    goto LABEL_19;
  }
  memset_0(sz, 0, 0x4Eu);
  StringFromGUID2(&rguid, sz, 39);
  QwordValue = (FILETIME)WcmCommon::Registry::Key::GetQwordValue((WcmCommon::Registry::Key *)&v43, sz);
  if ( !*(_QWORD *)&QwordValue )
  {
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
LABEL_31:
    try
    {
      si128 = 0;
      v40 = 0;
      v38[0] = a2;
      v38[1] = v8;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      si128 = rguid;
      v40 = this;
      v47 = 0;
      v47 = std::_Func_impl_no_alloc__RadioManager::_SetSysRadio_::_38_::_lambda_1__void_::_Func_impl_no_alloc__RadioManager::_SetSysRadio_::_38_::_lambda_1__void___RadioManager::_SetSysRadio_::_38_::_lambda_1__const___0_(
              v45,
              v38);
      v24 = RadioManager::_SetSysRadio_::_2_::SetSysRadioWorkitem::SetSysRadioWorkitem_0(sz, this, &rguid, v45);
      v51 = 0;
      v51 = std::_Global_new_std::_Func_impl_no_alloc__RadioManager::_SetSysRadio_::_2_::SetSysRadioWorkitem_void___RadioManager::_SetSysRadio_::_2_::SetSysRadioWorkitem_(v24);
      WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(
        (LPCRITICAL_SECTION)((char *)a4 + 24),
        (__int64)v49,
        1u);
      std::_Func_class<void,>::~_Func_class<void,>(v49);
      RadioManager::_SetSysRadio_::_2_::SetSysRadioWorkitem::_SetSysRadioWorkitem(sz);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    catch ( ... )
    {
      v26 = wil::ResultFromCaughtException(v25);
      v30 = v26;
      if ( (unsigned int)dword_180037050 > 2 )
      {
        FileTime.dwLowDateTime = v26;
        v33 = (const wchar_t *)RmGuidToMediaTypeString(&rguid);
        p_rguid = &rguid;
        v32 = (const wchar_t *)"Exception thrown trying to queue a work item for a MediaRadioManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v27,
          (unsigned __int8 *)byte_18002ECD3,
          v28,
          v29,
          &v32,
          (__int64 *)&p_rguid,
          &v33,
          (__int64)&FileTime);
      }
      v8 = v34;
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return v30;
  }
  FileTime = QwordValue;
  SystemTime = 0;
  FileTimeToSystemTime(&FileTime, &SystemTime);
  memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
  GetDynamicTimeZoneInformation(&pTimeZoneInformation);
  Date = 0;
  SystemTimeToTzSpecificLocalTimeEx(&pTimeZoneInformation, &SystemTime, &Date);
  cchDate = GetDateFormatEx(L"!x-sys-default-locale", 2u, &Date, 0, 0, 0, 0);
  TimeFormat = GetTimeFormatEx(L"!x-sys-default-locale", 0, &Date, 0, 0, 0);
  std::wstring::wstring(v45, cchDate);
  std::wstring::wstring(v49, TimeFormat);
  lpDateStr = (WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45);
  GetDateFormatEx(L"!x-sys-default-locale", 2u, &Date, 0, lpDateStr, cchDate, 0);
  v20 = (WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v49);
  GetTimeFormatEx(L"!x-sys-default-locale", 0, &Date, 0, v20, TimeFormat);
  std::wstring::resize(v45, (int)cchDate - 1);
  std::wstring::resize(v49, (int)TimeFormat - 1);
  if ( (unsigned int)dword_180037050 > 4 )
  {
    v31 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v49);
    v36[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45);
    v35 = (const wchar_t *)RmGuidToMediaTypeString(&rguid);
    v36[1] = (__int64)&rguid;
    v32 = (const wchar_t *)"RM GUID is set to be ignored based on past usage, skipping queuing a work item";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v21,
      byte_18002ED83);
  }
  if ( v50.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v49[0], 2 * v50.m128i_i64[1] + 2);
  v22 = _mm_load_si128((const __m128i *)&_xmm);
  v50 = v22;
  LOWORD(v49[0]) = 0;
  if ( v46.m128i_i64[1] > 7uLL )
  {
    std::_Deallocate<16>(v45[0], 2 * v46.m128i_i64[1] + 2);
    v22 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v46 = v22;
  LOWORD(v45[0]) = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
  if ( v8 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800222d0  mov     [rsp+arg_10], rbx
0x1800222d5  mov     [rsp+arg_8], dl
0x1800222d9  push    rsi
0x1800222da  push    rdi
0x1800222db  push    r12
0x1800222dd  push    r14
0x1800222df  push    r15
0x1800222e1  sub     rsp, 3A0h
0x1800222e8  mov     rax, cs:__security_cookie
0x1800222ef  xor     rax, rsp
0x1800222f2  mov     [rsp+3C8h+var_38], rax
0x1800222fa  mov     rsi, r9
0x1800222fd  mov     r12b, r8b
0x180022300  mov     r15b, dl
0x180022303  mov     r14, rcx
0x180022306  mov     [rsp+3C8h+var_338], rcx
0x18002230e  mov     [rsp+3C8h+var_360], r9
0x180022313  mov     rdi, [r9]
0x180022316  mov     [rsp+3C8h+var_358], rdi
0x18002231b  xor     ebx, ebx
0x18002231d  test    rdi, rdi
0x180022320  jz      short loc_180022332
0x180022322  mov     rax, [rdi]
0x180022325  mov     rcx, rdi
0x180022328  mov     rax, [rax+8]
0x18002232c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022331  nop
0x180022332  movups  xmm0, xmmword ptr [rsi+8]
0x180022336  movdqu  xmmword ptr [rsp+3C8h+rguid.Data1], xmm0
0x18002233f  mov     [rsp+3C8h+var_378], ebx
0x180022343  test    r12b, r12b
0x180022346  jnz     loc_18002278A
0x18002234c  mov     [rsp+3C8h+var_2F0], rbx
0x180022354  lea     rcx, [rsp+3C8h+var_330]
0x18002235c  call    ?GetPersistentRegPathRMRadioIgnoredState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioIgnoredState(void)
0x180022361  nop
0x180022362  mov     rcx, rax
0x180022365  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002236a  mov     r8, rax
0x18002236d  lea     rcx, [rsp+3C8h+var_2F0]
0x180022375  call    ?CreateKeyRO@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRO(HKEY__ * const,wchar_t const * const)
0x18002237a  nop
0x18002237b  mov     rdx, [rsp+3C8h+var_318]
0x180022383  cmp     rdx, 7
0x180022387  jbe     short loc_18002239E
0x180022389  lea     rdx, ds:2[rdx*2]
0x180022391  mov     rcx, qword ptr [rsp+3C8h+var_330]
0x180022399  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002239e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800223a6  movdqu  xmmword ptr [rsp+0A8h], xmm0
0x1800223af  mov     word ptr [rsp+3C8h+var_330], bx
0x1800223b7  call    ?IsModernAirplaneModeDisabled@RMAPI@@YA_NXZ; RMAPI::IsModernAirplaneModeDisabled(void)
0x1800223bc  test    al, al
0x1800223be  jz      loc_180022447
0x1800223c4  mov     eax, cs:dword_180037050
0x1800223ca  cmp     eax, 2
0x1800223cd  jbe     loc_18002275E
0x1800223d3  mov     [rsp+3C8h+FileTime.dwLowDateTime], ebx
0x1800223da  lea     rcx, [rsp+3C8h+rguid]; struct _GUID *
0x1800223e2  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x1800223e7  mov     [rsp+3C8h+var_350], rax
0x1800223ec  lea     rax, [rsp+3C8h+rguid]
0x1800223f4  mov     [rsp+3C8h+var_348], rax
0x1800223fc  lea     rax, aConsideringMed; "Considering media manager NOT ignored b"...
0x180022403  mov     [rsp+3C8h+var_370], rax
0x180022408  lea     rax, [rsp+3C8h+FileTime]
0x180022410  mov     [rsp+3C8h+var_390], rax
0x180022415  lea     rax, [rsp+3C8h+var_350]
0x18002241a  mov     [rsp+3C8h+lpCalendar], rax
0x18002241f  lea     rax, [rsp+3C8h+var_348]
0x180022427  mov     qword ptr [rsp+3C8h+cchDate], rax
0x18002242c  lea     rax, [rsp+3C8h+var_370]
0x180022431  mov     [rsp+3C8h+lpDateStr], rax
0x180022436  lea     rdx, dword_18002EDEC
0x18002243d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180022442  jmp     loc_18002275E
0x180022447  xor     edx, edx; Val
0x180022449  lea     r8d, [rdx+4Eh]; Size
0x18002244d  lea     rcx, [rsp+3C8h+sz]; void *
0x180022455  call    memset_0
0x18002245a  mov     r8d, 27h ; '''; cchMax
0x180022460  lea     rdx, [rsp+3C8h+sz]; lpsz
0x180022468  lea     rcx, [rsp+3C8h+rguid]; rguid
0x180022470  call    cs:__imp_StringFromGUID2
0x180022476  lea     rdx, [rsp+3C8h+sz]; wchar_t *
0x18002247e  lea     rcx, [rsp+3C8h+var_2F0]; this
0x180022486  call    ?GetQwordValue@Key@Registry@WcmCommon@@QEBA_KQEB_W@Z; WcmCommon::Registry::Key::GetQwordValue(wchar_t const * const)
0x18002248b  test    rax, rax
0x18002248e  jz      loc_18002275E
0x180022494  mov     [rsp+3C8h+FileTime.dwLowDateTime], eax
0x18002249b  shr     rax, 20h
0x18002249f  mov     [rsp+3C8h+FileTime.dwHighDateTime], eax
0x1800224a6  xorps   xmm0, xmm0
0x1800224a9  movups  xmmword ptr [rsp+3C8h+SystemTime.wYear], xmm0
0x1800224b1  lea     rdx, [rsp+3C8h+SystemTime]; lpSystemTime
0x1800224b9  lea     rcx, [rsp+3C8h+FileTime]; lpFileTime
0x1800224c1  call    cs:__imp_FileTimeToSystemTime
0x1800224c7  xor     edx, edx; Val
0x1800224c9  mov     r8d, 1B0h; Size
0x1800224cf  lea     rcx, [rsp+3C8h+pTimeZoneInformation]; void *
0x1800224d7  call    memset_0
0x1800224dc  lea     rcx, [rsp+3C8h+pTimeZoneInformation]; pTimeZoneInformation
0x1800224e4  call    cs:__imp_GetDynamicTimeZoneInformation
0x1800224ea  xorps   xmm0, xmm0
0x1800224ed  movups  xmmword ptr [rsp+3C8h+Date.wYear], xmm0
0x1800224f5  lea     r8, [rsp+3C8h+Date]
0x1800224fd  lea     rdx, [rsp+3C8h+SystemTime]
0x180022505  lea     rcx, [rsp+3C8h+pTimeZoneInformation]
0x18002250d  call    cs:__imp_SystemTimeToTzSpecificLocalTimeEx
0x180022513  mov     [rsp+3C8h+lpCalendar], rbx; lpCalendar
0x180022518  mov     [rsp+3C8h+cchDate], ebx; cchDate
0x18002251c  mov     [rsp+3C8h+lpDateStr], rbx; lpDateStr
0x180022521  xor     r9d, r9d; lpFormat
0x180022524  lea     r8, [rsp+3C8h+Date]; lpDate
0x18002252c  lea     edx, [r9+2]; dwFlags
0x180022530  lea     r15, LocaleName; "!x-sys-default-locale"
0x180022537  mov     rcx, r15; lpLocaleName
0x18002253a  call    cs:__imp_GetDateFormatEx
0x180022540  movsxd  r14, eax
0x180022543  mov     [rsp+3C8h+cchDate], ebx; cchTime
0x180022547  mov     [rsp+3C8h+lpDateStr], rbx; lpTimeStr
0x18002254c  xor     r9d, r9d; lpFormat
0x18002254f  lea     r8, [rsp+3C8h+Date]; lpTime
0x180022557  xor     edx, edx; dwFlags
0x180022559  mov     rcx, r15; lpLocaleName
0x18002255c  call    cs:__imp_GetTimeFormatEx
0x180022562  movsxd  rsi, eax
0x180022565  mov     rdx, r14
0x180022568  lea     rcx, [rsp+3C8h+var_2D8]
0x180022570  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180022575  nop
0x180022576  mov     rdx, rsi
0x180022579  lea     rcx, [rsp+3C8h+var_288]
0x180022581  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180022586  nop
0x180022587  lea     rcx, [rsp+3C8h+var_2D8]
0x18002258f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022594  mov     [rsp+3C8h+lpCalendar], rbx; lpCalendar
0x180022599  mov     [rsp+3C8h+cchDate], r14d; cchDate
0x18002259e  mov     [rsp+3C8h+lpDateStr], rax; lpDateStr
0x1800225a3  xor     r9d, r9d; lpFormat
0x1800225a6  lea     r8, [rsp+3C8h+Date]; lpDate
0x1800225ae  lea     edx, [r9+2]; dwFlags
0x1800225b2  mov     rcx, r15; lpLocaleName
0x1800225b5  call    cs:__imp_GetDateFormatEx
0x1800225bb  lea     rcx, [rsp+3C8h+var_288]
0x1800225c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800225c8  mov     [rsp+3C8h+cchDate], esi; cchTime
0x1800225cc  mov     [rsp+3C8h+lpDateStr], rax; lpTimeStr
0x1800225d1  xor     r9d, r9d; lpFormat
0x1800225d4  lea     r8, [rsp+3C8h+Date]; lpTime
0x1800225dc  xor     edx, edx; dwFlags
0x1800225de  mov     rcx, r15; lpLocaleName
0x1800225e1  call    cs:__imp_GetTimeFormatEx
0x1800225e7  lea     eax, [r14-1]
0x1800225eb  movsxd  rdx, eax
0x1800225ee  lea     rcx, [rsp+3C8h+var_2D8]
0x1800225f6  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800225fb  lea     eax, [rsi-1]
0x1800225fe  movsxd  rdx, eax
0x180022601  lea     rcx, [rsp+3C8h+var_288]
0x180022609  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18002260e  mov     eax, cs:dword_180037050
0x180022614  cmp     eax, 4
0x180022617  jbe     loc_1800226B7
0x18002261d  lea     rcx, [rsp+3C8h+var_288]
0x180022625  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002262a  mov     [rsp+3C8h+var_370], rax
0x18002262f  lea     rcx, [rsp+3C8h+var_2D8]
0x180022637  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002263c  mov     [rsp+3C8h+var_348], rax
0x180022644  lea     rcx, [rsp+3C8h+rguid]; struct _GUID *
0x18002264c  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180022651  mov     [rsp+3C8h+var_350], rax
0x180022656  lea     rax, [rsp+3C8h+rguid]
0x18002265e  mov     [rsp+3C8h+var_340], rax
0x180022666  lea     rax, aRmGuidIsSetToB; "RM GUID is set to be ignored based on p"...
0x18002266d  mov     [rsp+3C8h+var_368], rax
0x180022672  lea     rax, [rsp+3C8h+var_370]
0x180022677  mov     [rsp+3C8h+var_388], rax
0x18002267c  lea     rax, [rsp+3C8h+var_348]
0x180022684  mov     [rsp+3C8h+var_390], rax
0x180022689  lea     rax, [rsp+3C8h+var_350]
0x18002268e  mov     [rsp+3C8h+lpCalendar], rax
0x180022693  lea     rax, [rsp+3C8h+var_340]
0x18002269b  mov     qword ptr [rsp+3C8h+cchDate], rax
0x1800226a0  lea     rax, [rsp+3C8h+var_368]
0x1800226a5  mov     [rsp+3C8h+lpDateStr], rax
0x1800226aa  lea     rdx, byte_18002ED83
0x1800226b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1800226b6  nop
0x1800226b7  mov     rdx, [rsp+3C8h+var_270]
0x1800226bf  cmp     rdx, 7
0x1800226c3  jbe     short loc_1800226DA
0x1800226c5  lea     rdx, ds:2[rdx*2]
0x1800226cd  mov     rcx, [rsp+3C8h+var_288]
0x1800226d5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800226da  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800226e2  movdqu  xmmword ptr [rsp+150h], xmm0
0x1800226eb  mov     word ptr [rsp+3C8h+var_288], bx
0x1800226f3  mov     rdx, [rsp+3C8h+var_2C0]
0x1800226fb  cmp     rdx, 7
0x1800226ff  jbe     short loc_18002271E
0x180022701  lea     rdx, ds:2[rdx*2]
0x180022709  mov     rcx, [rsp+3C8h+var_2D8]
0x180022711  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180022716  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002271e  movdqu  xmmword ptr [rsp+100h], xmm0
0x180022727  mov     word ptr [rsp+3C8h+var_2D8], bx
0x18002272f  lea     rcx, [rsp+3C8h+var_2F0]
0x180022737  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002273c  nop
0x18002273d  test    rdi, rdi
0x180022740  jz      short loc_180022757
0x180022742  mov     [rsp+3C8h+var_358], rbx
0x180022747  mov     rax, [rdi]
0x18002274a  mov     rcx, rdi
0x18002274d  mov     rax, [rax+10h]
0x180022751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022756  nop
0x180022757  xor     eax, eax
0x180022759  jmp     loc_1800228AC
0x18002275e  lea     rcx, [rsp+3C8h+var_2F0]
0x180022766  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002276b  nop
0x18002276c  jmp     short loc_18002278A
0x18002276e  xor     ebx, ebx
0x180022770  mov     r15b, [rsp+3C8h+arg_8]
0x180022778  mov     rdi, [rsp+3C8h+var_358]
0x18002277d  mov     r14, [rsp+3C8h+var_338]
0x180022785  mov     rsi, [rsp+3C8h+var_360]
0x18002278a  xorps   xmm0, xmm0
0x18002278d  xor     eax, eax
0x18002278f  movups  [rsp+3C8h+var_330], xmm0
0x180022797  movups  xmmword ptr [rsp+0A8h], xmm0
0x18002279f  mov     [rsp+3C8h+var_310], rax
0x1800227a7  mov     byte ptr [rsp+3C8h+var_330], r15b
0x1800227af  mov     qword ptr [rsp+3C8h+var_330+8], rdi
0x1800227b7  test    rdi, rdi
0x1800227ba  jz      short loc_1800227CC
0x1800227bc  mov     rax, [rdi]
0x1800227bf  mov     rcx, rdi
0x1800227c2  mov     rax, [rax+8]
0x1800227c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227cb  nop
0x1800227cc  movups  xmm0, xmmword ptr [rsp+3C8h+rguid.Data1]
0x1800227d4  movdqu  xmmword ptr [rsp+0A8h], xmm0
0x1800227dd  mov     [rsp+3C8h+var_310], r14
0x1800227e5  mov     [rsp+3C8h+var_2A0], rbx
0x1800227ed  lea     rdx, [rsp+3C8h+var_330]
0x1800227f5  lea     rcx, [rsp+3C8h+var_2D8]
0x1800227fd  call    std___Func_impl_no_alloc__RadioManager___SetSysRadio____38____lambda_1__void____Func_impl_no_alloc__RadioManager___SetSysRadio____38____lambda_1__void___RadioManager___SetSysRadio____38____lambda_1__const___0_
0x180022802  mov     [rsp+3C8h+var_2A0], rax
0x18002280a  lea     r9, [rsp+3C8h+var_2D8]
0x180022812  lea     r8, [rsp+3C8h+rguid]
0x18002281a  mov     rdx, r14
0x18002281d  lea     rcx, [rsp+3C8h+sz]
0x180022825  call    _RadioManager___SetSysRadio____2___SetSysRadioWorkitem__SetSysRadioWorkitem_0
0x18002282a  nop
0x18002282b  mov     [rsp+3C8h+var_250], rbx
0x180022833  mov     rcx, rax
0x180022836  call    std___Global_new_std___Func_impl_no_alloc__RadioManager___SetSysRadio____2___SetSysRadioWorkitem_void___RadioManager___SetSysRadio____2___SetSysRadioWorkitem_
0x18002283b  mov     [rsp+3C8h+var_250], rax
0x180022843  lea     rcx, [rsi+18h]; lpCriticalSection
0x180022847  mov     r8d, 1
0x18002284d  lea     rdx, [rsp+3C8h+var_288]
0x180022855  call    ??$SubmitWork@V?$function@$$A6AXXZ@std@@@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@K@Z; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(std::function<void (void)> &&,ulong)
0x18002285a  nop
0x18002285b  lea     rcx, [rsp+3C8h+var_288]
0x180022863  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180022868  nop
0x180022869  lea     rcx, [rsp+3C8h+sz]
0x180022871  call    _RadioManager___SetSysRadio____2___SetSysRadioWorkitem___SetSysRadioWorkitem
0x180022876  nop
0x180022877  test    rdi, rdi
0x18002287a  jz      short loc_18002288C
0x18002287c  mov     rax, [rdi]
0x18002287f  mov     rcx, rdi
0x180022882  mov     rax, [rax+10h]
0x180022886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002288b  nop
0x18002288c  jmp     short loc_180022893
0x18002288e  mov     rdi, [rsp+3C8h+var_358]
0x180022893  test    rdi, rdi
0x180022896  jz      short loc_1800228A8
0x180022898  mov     rax, [rdi]
0x18002289b  mov     rcx, rdi
0x18002289e  mov     rax, [rax+10h]
0x1800228a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228a7  nop
0x1800228a8  mov     eax, [rsp+3C8h+var_378]
0x1800228ac  mov     rcx, [rsp+3C8h+var_38]
0x1800228b4  xor     rcx, rsp; StackCookie
0x1800228b7  call    __security_check_cookie
0x1800228bc  mov     rbx, [rsp+3C8h+arg_10]
0x1800228c4  add     rsp, 3A0h
0x1800228cb  pop     r15
0x1800228cd  pop     r14
0x1800228cf  pop     r12
0x1800228d1  pop     rdi
  ... truncated ...
```
