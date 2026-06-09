# Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,unsigned __int64)

- ea: `0x180169c48`
- end: `0x18016a7d9`
- name: `?CopyOutputDirectory@EscalationWorkItem@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N_K@Z`
- size: `2961`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18016c108`
- `0x1801dcd4c`
- `0x1802bb314`

## callees

- `0x180002a28`
- `0x18000a364`
- `0x18002110c`
- `0x18002b7c0`
- `0x18002b95c`
- `0x18002cb04`
- `0x18002d7d0`
- `0x18002df00`
- `0x180038010`
- `0x180053ff4`
- `0x1800561a4`
- `0x180064e34`
- `0x180064e8c`
- `0x18006835c`
- `0x180068c58`
- `0x18009c7e4`
- `0x18009c8c0`
- `0x1800b47f0`
- `0x1800bc488`
- `0x1800bc508`
- `0x1800bc658`
- `0x1800c53b4`
- `0x1800dce08`
- `0x1800f602c`
- `0x180102bbc`
- `0x18010c974`
- `0x18012f3bc`
- `0x180142fcc`
- `0x18016323c`
- `0x180169c48`
- `0x1801abcac`
- `0x1802040a4`
- `0x18020aac0`
- `0x1802b809c`
- `0x1802b8b48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016a394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016a394`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180169fd7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180169fd7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18016a4c4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18016a4c4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18016a495`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18016a495`

## string_xrefs

- `0x18016a1f3`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18016a2f3`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18016a4e3`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18016a687`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x180169d48`: `CopyOutputDirectory_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory(
        __int64 a1,
        __m128i *a2,
        char a3,
        __int64 a4)
{
  __int64 v4; // rbx
  __int64 v9; // r8
  __int64 v10; // rax
  _QWORD *v11; // rax
  int v12; // r8d
  int v13; // r9d
  LPCWSTR *v14; // rax
  const WCHAR *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 last_of; // rax
  unsigned int v23; // ebx
  __int64 v24; // r8
  int Directory; // eax
  unsigned int v26; // r14d
  __int64 v27; // r8
  struct Microsoft::Diagnostics::UserManager *v28; // rax
  __int64 v29; // r8
  struct Microsoft::Diagnostics::UserManager *UserManager; // rax
  Microsoft::Diagnostics::UserManager *v31; // r8
  __int64 UserContextForSid; // rdi
  CONTEXT *v33; // rbx
  __int64 v34; // r8
  int UserToken; // eax
  unsigned int v36; // ebx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rax
  int v40; // r8d
  int v41; // r9d
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // [rsp+20h] [rbp-688h]
  int v45; // [rsp+20h] [rbp-688h]
  char v46; // [rsp+30h] [rbp-678h] BYREF
  char v47; // [rsp+31h] [rbp-677h] BYREF
  char v48; // [rsp+32h] [rbp-676h] BYREF
  char v49; // [rsp+33h] [rbp-675h] BYREF
  char v50; // [rsp+34h] [rbp-674h] BYREF
  __int16 v51; // [rsp+35h] [rbp-673h] BYREF
  int v52; // [rsp+38h] [rbp-670h] BYREF
  _BYTE v53[4]; // [rsp+3Ch] [rbp-66Ch] BYREF
  __m128i v54; // [rsp+40h] [rbp-668h] BYREF
  int v55[4]; // [rsp+50h] [rbp-658h] BYREF
  _QWORD v56[2]; // [rsp+60h] [rbp-648h] BYREF
  char v57; // [rsp+70h] [rbp-638h]
  _QWORD v58[10]; // [rsp+80h] [rbp-628h] BYREF
  char v59; // [rsp+D0h] [rbp-5D8h]
  LPCWSTR lpFileName[3]; // [rsp+E0h] [rbp-5C8h] BYREF
  unsigned __int64 v61; // [rsp+F8h] [rbp-5B0h]
  _QWORD v62[2]; // [rsp+100h] [rbp-5A8h] BYREF
  _OWORD v63[2]; // [rsp+120h] [rbp-588h] BYREF
  _QWORD v64[4]; // [rsp+140h] [rbp-568h] BYREF
  _OWORD v65[2]; // [rsp+160h] [rbp-548h] BYREF
  _QWORD Src[4]; // [rsp+180h] [rbp-528h] BYREF
  _BYTE v67[1184]; // [rsp+1A0h] [rbp-508h] BYREF
  __int128 v68[2]; // [rsp+640h] [rbp-68h] BYREF
  _BYTE v69[6]; // [rsp+66Ah] [rbp-3Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6A8h] [rbp+0h]

  v4 = a4;
  v47 = 0;
  LOBYTE(a4) = *(_BYTE *)(a1 + 577);
  Microsoft::Diagnostics::EscalationWorkItemOverrides::GetCopyOutputDirectoryPath(
    *(_QWORD *)(a1 + 584),
    (unsigned int)lpFileName,
    *(_QWORD *)(a1 + 600),
    a4,
    (__int64)&v47);
  if ( !lpFileName[2] )
  {
    if ( (unsigned int)dword_1804543B0 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          byte_1803F44FB);
    }
    std::wstring::_Tidy_deallocate(lpFileName);
    return 0;
  }
  v65[0] = 0;
  v65[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v65[0]) = 0;
  v48 = 0;
  v46 = 1;
  v49 = 0;
  v51 = 0;
  v50 = 0;
  v52 = 0;
  *(_QWORD *)v55 = L"CopyOutputDirectory_0";
  *(_QWORD *)&v55[2] = 21;
  Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
    (unsigned int)v67,
    (unsigned int)v55,
    0x1000000,
    0,
    0);
  v58[0] = lpFileName;
  v58[1] = v67;
  v58[2] = &v47;
  v58[3] = &v48;
  v58[4] = &v46;
  v58[5] = (char *)&v51 + 1;
  v58[6] = &v49;
  v58[7] = &v51;
  v58[8] = &v50;
  v58[9] = &v52;
  v59 = 1;
  v63[0] = 0;
  v63[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v63[0]) = 0;
  v56[0] = &v52;
  v56[1] = v63;
  v57 = 1;
  if ( a3 )
    std::wstring::append(lpFileName, L"_selfdiagnosis");
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 584) + 42LL) )
  {
    std::wstring::append(lpFileName, L"_");
    v10 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v69, v4);
    std::wstring::wstring(v62, v10, v69);
    std::wstring::_Append<wchar_t>(lpFileName);
    std::wstring::_Tidy_deallocate(v62);
  }
  v54 = *(__m128i *)std::wstring::operator std::wstring_view(lpFileName, v68, v9);
  v11 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(*(_QWORD *)(a1 + 600), v62, &v54);
  std::wstring::operator=(lpFileName, v11);
  std::wstring::_Tidy_deallocate(v62);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
  {
    v14 = lpFileName;
    if ( v61 > 7 )
      v14 = (LPCWSTR *)lpFileName[0];
    *(_QWORD *)v55 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_1804543B0,
      (unsigned int)&unk_1803F4478,
      v12,
      v13,
      (__int64)v55);
  }
  v15 = (const WCHAR *)lpFileName;
  if ( v61 > 7 )
    v15 = lpFileName[0];
  if ( GetFileAttributesW(v15) != -1 )
  {
    if ( (unsigned int)dword_1804543B0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1804543B0,
        qword_1803F44B8);
    v48 = 1;
    v57 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v56);
    std::wstring::_Tidy_deallocate(v63);
    v59 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v58);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(lpFileName);
    return 0;
  }
  v52 = -2147467259;
  std::wstring::wstring(Src, &off_180386200);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src, 1, 0);
  std::wstring::wstring(v64, &off_1803861F0);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v64, 1, 0);
  v54 = *(__m128i *)std::wstring::operator std::wstring_view(Src, v68, v16);
  *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v62, v17);
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(v55, &v54)
    || (v54 = *(__m128i *)std::wstring::operator std::wstring_view(v64, v62, v18),
        *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v68, v19),
        (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(v55, &v54)) )
  {
    v46 = 0;
  }
  v54 = *(__m128i *)std::wstring::operator std::wstring_view(v64, v62, v18);
  *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v68, v20);
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(v55, &v54) )
  {
    last_of = std::wstring::find_last_of(lpFileName, 92);
    if ( last_of == -1 )
    {
      v23 = v52;
      if ( v52 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x528,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
          (const char *)(unsigned int)v52,
          v44);
      std::wstring::_Tidy_deallocate(v64);
      std::wstring::_Tidy_deallocate(Src);
      v57 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v56);
      std::wstring::_Tidy_deallocate(v63);
      v59 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v58);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v23;
    }
    std::wstring::substr(lpFileName, v68, 0, last_of);
    v54 = *(__m128i *)&off_18036C4F8;
    *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(v68, v62, v24);
    Directory = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(
                  (__int64)v55,
                  0,
                  (__int128 *)v54.m128i_i8);
    v26 = Directory;
    if ( Directory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
        (const char *)(unsigned int)Directory,
        v44);
      std::wstring::_Tidy_deallocate(v68);
      std::wstring::_Tidy_deallocate(v64);
      std::wstring::_Tidy_deallocate(Src);
      v57 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v56);
      std::wstring::_Tidy_deallocate(v63);
      v59 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v58);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v26;
    }
    if ( GetLastError() != 183 )
      std::wstring::operator=(v63, v68);
    std::wstring::_Tidy_deallocate(v68);
  }
  *(_QWORD *)v55 = 0;
  std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v54, v21);
  if ( v54.m128i_i64[1]
    && (v28 = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager),
        std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v54, v28),
        (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v29, &v54))
    && v46 )
  {
    UserManager = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v54, UserManager);
    UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v31);
    v33 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
    RtlCaptureContext(v33);
    LOBYTE(v34) = 2;
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(&v54, 240000, v34, v33);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v55,
      0);
    UserToken = UMgrQueryUserToken(UserContextForSid, v55);
    v36 = UserToken;
    v52 = UserToken;
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x540,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
        (const char *)(unsigned int)UserToken,
        v44);
      Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v54);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v55);
      std::wstring::_Tidy_deallocate(v64);
      std::wstring::_Tidy_deallocate(Src);
      v57 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v56);
      std::wstring::_Tidy_deallocate(v63);
      v59 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v58);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(lpFileName);
      return v36;
    }
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v54);
    v49 = 1;
  }
  else if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
  {
    v53[0] = v46;
    std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v54, v27);
    std::wstring::operator std::wstring_view(v37, v68, v38);
    v39 = _tlgWrapBinary<wchar_t,2>(v62, *(_QWORD *)&v68[0], v54.m128i_u32[2]);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperByVal<1>>(
      (unsigned int)v53,
      (unsigned int)byte_1803F4411,
      v40,
      v41,
      v39,
      (__int64)v53);
  }
  v68[0] = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v62, v27);
  v54 = *a2;
  v42 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
          (__int128 *)v54.m128i_i8,
          v68,
          (__int64 *)v55,
          (_BYTE *)&v51 + 1,
          &v51,
          &v50);
  v43 = v42;
  v52 = v42;
  if ( v42 >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v55);
    std::wstring::_Tidy_deallocate(v64);
    std::wstring::_Tidy_deallocate(Src);
    v57 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v56);
    std::wstring::_Tidy_deallocate(v63);
    v59 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v58);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(lpFileName);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x555,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
      (const char *)(unsigned int)v42,
      v45);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v55);
    std::wstring::_Tidy_deallocate(v64);
    std::wstring::_Tidy_deallocate(Src);
    v57 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v56);
    std::wstring::_Tidy_deallocate(v63);
    v59 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v58);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v67);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(lpFileName);
    return v43;
  }
}

```

## disassembly

```asm
0x180169c48  mov     [rsp+arg_10], rbx
0x180169c4d  push    rsi
0x180169c4e  push    rdi
0x180169c4f  push    r12
0x180169c51  push    r14
0x180169c53  push    r15
0x180169c55  sub     rsp, 680h
0x180169c5c  mov     rax, cs:__security_cookie
0x180169c63  xor     rax, rsp
0x180169c66  mov     [rsp+6A8h+var_38], rax
0x180169c6e  mov     rbx, r9
0x180169c71  mov     dil, r8b
0x180169c74  mov     r15, rdx
0x180169c77  mov     rsi, rcx
0x180169c7a  xor     r12d, r12d
0x180169c7d  mov     [rsp+6A8h+var_677], r12b
0x180169c82  lea     rax, [rsp+6A8h+var_677]
0x180169c87  mov     qword ptr [rsp+6A8h+var_688], rax
0x180169c8c  mov     r9b, [rcx+241h]
0x180169c93  mov     r8, [rcx+258h]
0x180169c9a  lea     rdx, [rsp+6A8h+lpFileName]
0x180169ca2  mov     rcx, [rcx+248h]
0x180169ca9  call    ?GetCopyOutputDirectoryPath@EscalationWorkItemOverrides@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVScenarioInst@23@VReservedStateOrdinal@23@AEAVCopyOutputDirectorySource@EnumDetails@23@@Z; Microsoft::Diagnostics::EscalationWorkItemOverrides::GetCopyOutputDirectoryPath(Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::ReservedStateOrdinal,Microsoft::Diagnostics::EnumDetails::CopyOutputDirectorySource &)
0x180169cae  nop
0x180169caf  cmp     [rsp+6A8h+var_5B8], r12
0x180169cb7  jnz     short loc_180169D00
0x180169cb9  mov     eax, cs:dword_1804543B0
0x180169cbf  cmp     eax, 3
0x180169cc2  jbe     short loc_180169CEC
0x180169cc4  lea     edx, [r12+4]
0x180169cc9  lea     rbx, dword_1804543B0
0x180169cd0  mov     rcx, rbx
0x180169cd3  call    _tlgKeywordOn
0x180169cd8  test    al, al
0x180169cda  jz      short loc_180169CEC
0x180169cdc  lea     rdx, byte_1803F44FB
0x180169ce3  mov     rcx, rbx
0x180169ce6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180169ceb  nop
0x180169cec  lea     rcx, [rsp+6A8h+lpFileName]
0x180169cf4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180169cf9  xor     eax, eax
0x180169cfb  jmp     loc_18016A7B0
0x180169d00  xorps   xmm0, xmm0
0x180169d03  movups  [rsp+6A8h+var_548], xmm0
0x180169d0b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180169d13  movdqu  [rsp+6A8h+var_538], xmm1
0x180169d1c  mov     word ptr [rsp+6A8h+var_548], r12w
0x180169d25  mov     [rsp+6A8h+var_676], r12b
0x180169d2a  mov     [rsp+6A8h+var_678], 1
0x180169d2f  mov     byte ptr [rsp+6A8h+var_673+1], r12b
0x180169d34  mov     [rsp+6A8h+var_675], r12b
0x180169d39  mov     byte ptr [rsp+6A8h+var_673], r12b
0x180169d3e  mov     [rsp+6A8h+var_674], r12b
0x180169d43  mov     dword ptr [rsp+6A8h+var_673+3], r12d
0x180169d48  lea     rdx, aCopyoutputdire; "CopyOutputDirectory_0"
0x180169d4f  mov     qword ptr [rsp+6A8h+var_658], rdx
0x180169d54  mov     qword ptr [rsp+6A8h+var_658+8], 15h
0x180169d5d  mov     r8d, 1000000h
0x180169d63  mov     byte ptr [rsp+6A8h+var_680], r12b
0x180169d68  mov     byte ptr [rsp+6A8h+var_688], r12b
0x180169d6d  mov     r9, 800000000000h
0x180169d77  lea     rdx, [rsp+6A8h+var_658]
0x180169d7c  lea     rcx, [rsp+6A8h+var_508]
0x180169d84  call    ?MakeScenarioSyntheticEvent@AsimovSyntheticEvent@Diagnostics@Microsoft@@SA?AV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@23@VTriggerLatency@23@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency)
0x180169d89  nop
0x180169d8a  lea     rax, [rsp+6A8h+lpFileName]
0x180169d92  mov     [rsp+6A8h+var_628], rax
0x180169d9a  lea     rax, [rsp+6A8h+var_508]
0x180169da2  mov     [rsp+6A8h+var_620], rax
0x180169daa  lea     rax, [rsp+6A8h+var_677]
0x180169daf  mov     [rsp+6A8h+var_618], rax
0x180169db7  lea     rax, [rsp+6A8h+var_676]
0x180169dbc  mov     [rsp+6A8h+var_610], rax
0x180169dc4  lea     rax, [rsp+6A8h+var_678]
0x180169dc9  mov     [rsp+6A8h+var_608], rax
0x180169dd1  lea     rax, [rsp+6A8h+var_673+1]
0x180169dd6  mov     [rsp+6A8h+var_600], rax
0x180169dde  lea     rax, [rsp+6A8h+var_675]
0x180169de3  mov     [rsp+6A8h+var_5F8], rax
0x180169deb  lea     rax, [rsp+6A8h+var_673]
0x180169df0  mov     [rsp+6A8h+var_5F0], rax
0x180169df8  lea     rax, [rsp+6A8h+var_674]
0x180169dfd  mov     [rsp+6A8h+var_5E8], rax
0x180169e05  lea     rax, [rsp+6A8h+var_673+3]
0x180169e0a  mov     [rsp+6A8h+var_5E0], rax
0x180169e12  mov     [rsp+6A8h+var_5D8], 1
0x180169e1a  xorps   xmm0, xmm0
0x180169e1d  movups  [rsp+6A8h+var_588], xmm0
0x180169e25  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180169e2d  movdqu  [rsp+6A8h+var_578], xmm1
0x180169e36  mov     word ptr [rsp+6A8h+var_588], r12w
0x180169e3f  lea     rax, [rsp+6A8h+var_673+3]
0x180169e44  mov     [rsp+6A8h+var_648], rax
0x180169e49  lea     rax, [rsp+6A8h+var_588]
0x180169e51  mov     [rsp+6A8h+var_640], rax
0x180169e56  mov     [rsp+6A8h+var_638], 1
0x180169e5b  test    dil, dil
0x180169e5e  jz      short loc_180169E74
0x180169e60  lea     rdx, aSelfdiagnosis_0; "_selfdiagnosis"
0x180169e67  lea     rcx, [rsp+6A8h+lpFileName]
0x180169e6f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180169e74  mov     rax, [rsi+248h]
0x180169e7b  cmp     [rax+2Ah], r12b
0x180169e7f  jz      short loc_180169EFB
0x180169e81  lea     rdx, asc_18039BD38; "_"
0x180169e88  lea     rcx, [rsp+6A8h+lpFileName]
0x180169e90  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180169e95  mov     rdx, rbx
0x180169e98  lea     rcx, [rsp+6A8h+var_3E]
0x180169ea0  call    ??$_UIntegral_to_buff@_W_K@std@@YAPEA_WPEA_W_K@Z; std::_UIntegral_to_buff<wchar_t,unsigned __int64>(wchar_t *,unsigned __int64)
0x180169ea5  lea     r8, [rsp+6A8h+var_3E]
0x180169ead  mov     rdx, rax
0x180169eb0  lea     rcx, [rsp+6A8h+var_5A8]
0x180169eb8  call    ??$?0PEB_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t const *,wchar_t const *,std::allocator<wchar_t> const &)
0x180169ebd  nop
0x180169ebe  lea     rdx, [rsp+6A8h+var_5A8]
0x180169ec6  cmp     [rsp+6A8h+var_590], 7
0x180169ecf  cmova   rdx, [rsp+6A8h+var_5A8]
0x180169ed8  mov     r8, [rsp+6A8h+var_598]
0x180169ee0  lea     rcx, [rsp+6A8h+lpFileName]; Src
0x180169ee8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180169eed  nop
0x180169eee  lea     rcx, [rsp+6A8h+var_5A8]
0x180169ef6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180169efb  lea     rdx, [rsp+6A8h+var_68]
0x180169f03  lea     rcx, [rsp+6A8h+lpFileName]
0x180169f0b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180169f10  movups  xmm0, xmmword ptr [rax]
0x180169f13  movdqu  [rsp+6A8h+var_668], xmm0
0x180169f19  lea     r8, [rsp+6A8h+var_668]
0x180169f1e  lea     rdx, [rsp+6A8h+var_5A8]
0x180169f26  mov     rcx, [rsi+258h]
0x180169f2d  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x180169f32  mov     rdx, rax
0x180169f35  lea     rcx, [rsp+6A8h+lpFileName]
0x180169f3d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180169f42  lea     rcx, [rsp+6A8h+var_5A8]
0x180169f4a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180169f4f  xor     r8d, r8d
0x180169f52  mov     dl, 1
0x180169f54  lea     rcx, [rsp+6A8h+lpFileName]; lpSrc
0x180169f5c  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180169f61  mov     eax, cs:dword_1804543B0
0x180169f67  mov     edi, 4
0x180169f6c  lea     rbx, dword_1804543B0
0x180169f73  cmp     eax, edi
0x180169f75  jbe     short loc_180169FBD
0x180169f77  mov     edx, edi
0x180169f79  mov     rcx, rbx
0x180169f7c  call    _tlgKeywordOn
0x180169f81  test    al, al
0x180169f83  jz      short loc_180169FBD
0x180169f85  lea     rax, [rsp+6A8h+lpFileName]
0x180169f8d  cmp     [rsp+6A8h+var_5B0], 7
0x180169f96  cmova   rax, [rsp+6A8h+lpFileName]
0x180169f9f  mov     qword ptr [rsp+6A8h+var_658], rax
0x180169fa4  lea     rax, [rsp+6A8h+var_658]
0x180169fa9  mov     qword ptr [rsp+6A8h+var_688], rax; int
0x180169fae  lea     rdx, unk_1803F4478
0x180169fb5  mov     rcx, rbx
0x180169fb8  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180169fbd  lea     rcx, [rsp+6A8h+lpFileName]
0x180169fc5  cmp     [rsp+6A8h+var_5B0], 7
0x180169fce  cmova   rcx, [rsp+6A8h+lpFileName]; lpFileName
0x180169fd7  call    cs:__imp_GetFileAttributesW
0x180169fdd  cmp     eax, 0FFFFFFFFh
0x180169fe0  jz      loc_18016A078
0x180169fe6  mov     eax, cs:dword_1804543B0
0x180169fec  cmp     eax, 3
0x180169fef  jbe     short loc_18016A00F
0x180169ff1  mov     rdx, rdi
0x180169ff4  mov     rcx, rbx
0x180169ff7  call    _tlgKeywordOn
0x180169ffc  test    al, al
0x180169ffe  jz      short loc_18016A00F
0x18016a000  lea     rdx, qword_1803F44B8
0x18016a007  mov     rcx, rbx
0x18016a00a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18016a00f  mov     [rsp+6A8h+var_676], 1
0x18016a014  mov     [rsp+6A8h+var_638], r12b
0x18016a019  lea     rcx, [rsp+6A8h+var_648]
0x18016a01e  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_2___operator__
0x18016a023  nop
0x18016a024  lea     rcx, [rsp+6A8h+var_588]
0x18016a02c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016a031  nop
0x18016a032  mov     [rsp+6A8h+var_5D8], r12b
0x18016a03a  lea     rcx, [rsp+6A8h+var_628]
0x18016a042  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_1___operator__
0x18016a047  nop
0x18016a048  lea     rcx, [rsp+6A8h+var_508]; this
0x18016a050  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18016a055  nop
0x18016a056  lea     rcx, [rsp+6A8h+var_548]
0x18016a05e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016a063  nop
0x18016a064  lea     rcx, [rsp+6A8h+lpFileName]
0x18016a06c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016a071  xor     eax, eax
0x18016a073  jmp     loc_18016A7B0
0x18016a078  mov     dword ptr [rsp+6A8h+var_673+3], 80004005h
0x18016a080  lea     rdx, off_180386200; "%DiagtrackStorageRoot%\\FeedbackHub"
0x18016a087  lea     rcx, [rsp+6A8h+Src]
0x18016a08f  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18016a094  nop
0x18016a095  xor     r8d, r8d
0x18016a098  mov     dl, 1
0x18016a09a  lea     rcx, [rsp+6A8h+Src]; lpSrc
0x18016a0a2  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18016a0a7  lea     rdx, off_1803861F0; "%DiagtrackStorageRoot%\\FeedbackArchive"
0x18016a0ae  lea     rcx, [rsp+6A8h+var_568]
0x18016a0b6  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18016a0bb  nop
0x18016a0bc  xor     r8d, r8d
0x18016a0bf  mov     dl, 1
0x18016a0c1  lea     rcx, [rsp+6A8h+var_568]; lpSrc
0x18016a0c9  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18016a0ce  lea     rdx, [rsp+6A8h+var_68]
0x18016a0d6  lea     rcx, [rsp+6A8h+Src]
0x18016a0de  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18016a0e3  movups  xmm0, xmmword ptr [rax]
0x18016a0e6  movdqu  [rsp+6A8h+var_668], xmm0
0x18016a0ec  lea     rdx, [rsp+6A8h+var_5A8]
0x18016a0f4  lea     rcx, [rsp+6A8h+lpFileName]
0x18016a0fc  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18016a101  movups  xmm0, xmmword ptr [rax]
0x18016a104  movdqu  xmmword ptr [rsp+6A8h+var_658], xmm0
0x18016a10a  lea     rdx, [rsp+6A8h+var_668]
0x18016a10f  lea     rcx, [rsp+6A8h+var_658]
0x18016a114  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x18016a119  test    al, al
0x18016a11b  jnz     short loc_18016A16C
0x18016a11d  lea     rdx, [rsp+6A8h+var_5A8]
0x18016a125  lea     rcx, [rsp+6A8h+var_568]
0x18016a12d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18016a132  movups  xmm0, xmmword ptr [rax]
0x18016a135  movdqu  [rsp+6A8h+var_668], xmm0
0x18016a13b  lea     rdx, [rsp+6A8h+var_68]
0x18016a143  lea     rcx, [rsp+6A8h+lpFileName]
0x18016a14b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18016a150  movups  xmm0, xmmword ptr [rax]
0x18016a153  movdqu  xmmword ptr [rsp+6A8h+var_658], xmm0
0x18016a159  lea     rdx, [rsp+6A8h+var_668]
0x18016a15e  lea     rcx, [rsp+6A8h+var_658]
0x18016a163  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x18016a168  test    al, al
0x18016a16a  jz      short loc_18016A171
0x18016a16c  mov     [rsp+6A8h+var_678], r12b
0x18016a171  lea     rdx, [rsp+6A8h+var_5A8]
0x18016a179  lea     rcx, [rsp+6A8h+var_568]
0x18016a181  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18016a186  movups  xmm0, xmmword ptr [rax]
0x18016a189  movdqu  [rsp+6A8h+var_668], xmm0
0x18016a18f  lea     rdx, [rsp+6A8h+var_68]
0x18016a197  lea     rcx, [rsp+6A8h+lpFileName]
0x18016a19f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18016a1a4  movups  xmm0, xmmword ptr [rax]
0x18016a1a7  movdqu  xmmword ptr [rsp+6A8h+var_658], xmm0
0x18016a1ad  lea     rdx, [rsp+6A8h+var_668]
0x18016a1b2  lea     rcx, [rsp+6A8h+var_658]
0x18016a1b7  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x18016a1bc  test    al, al
0x18016a1be  jz      loc_18016A3C4
0x18016a1c4  mov     edx, 5Ch ; '\'
0x18016a1c9  lea     rcx, [rsp+6A8h+lpFileName]
0x18016a1d1  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_last_of(wchar_t,unsigned __int64)
0x18016a1d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016a1da  jnz     loc_18016A285
0x18016a1e0  mov     ebx, dword ptr [rsp+6A8h+var_673+3]
0x18016a1e4  test    ebx, ebx
0x18016a1e6  jns     short loc_18016A205
0x18016a1e8  mov     rcx, [rsp+6A8h]; this
0x18016a1f0  mov     r9d, ebx; char *
0x18016a1f3  lea     r8, aOnecoreBaseTel_134; "onecore\\base\\telemetry\\utc\\service"...
0x18016a1fa  mov     edx, 528h; void *
0x18016a1ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016a204  nop
0x18016a205  lea     rcx, [rsp+6A8h+var_568]
0x18016a20d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016a212  nop
0x18016a213  lea     rcx, [rsp+6A8h+Src]
0x18016a21b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016a220  nop
0x18016a221  mov     [rsp+6A8h+var_638], r12b
0x18016a226  lea     rcx, [rsp+6A8h+var_648]
0x18016a22b  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_2___operator__
0x18016a230  nop
0x18016a231  lea     rcx, [rsp+6A8h+var_588]
0x18016a239  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016a23e  nop
0x18016a23f  mov     [rsp+6A8h+var_5D8], r12b
0x18016a247  lea     rcx, [rsp+6A8h+var_628]
0x18016a24f  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_1___operator__
0x18016a254  nop
0x18016a255  lea     rcx, [rsp+6A8h+var_508]; this
0x18016a25d  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18016a262  nop
0x18016a263  lea     rcx, [rsp+6A8h+var_548]
0x18016a26b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
