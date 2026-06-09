# Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace(wchar_t const *)

- ea: `0x180295d80`
- end: `0x180296a97`
- name: `?SnapCustomTrace@UtcApiManager@Diagnostics@Microsoft@@UEBAJPEB_W@Z`
- size: `3351`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiManager *this, const wchar_t *)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180020150`
- `0x18002110c`
- `0x180027c28`
- `0x180027e50`
- `0x180028ba8`
- `0x18002ac10`
- `0x18002afd8`
- `0x18002b770`
- `0x18002b9c0`
- `0x18002d7d0`
- `0x18002df00`
- `0x180031168`
- `0x180064e34`
- `0x180064e8c`
- `0x180087174`
- `0x18008a4ec`
- `0x18008abf4`
- `0x18009b404`
- `0x18009b658`
- `0x18009b694`
- `0x18009c8c0`
- `0x1800bc488`
- `0x1800bc508`
- `0x1800bc658`
- `0x1800c53b4`
- `0x1800c5d5c`
- `0x1800cf7d8`
- `0x1800dce08`
- `0x1800f7f64`
- `0x180102bbc`
- `0x180140a5c`
- `0x180142fcc`
- `0x18017732c`
- `0x1801d5a9c`
- `0x18020aac0`
- `0x18020ba94`
- `0x180287234`
- `0x180295d80`
- `0x1802b8b48`
- `0x1802f2544`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180295f16`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180295f16`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180295e9b`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180295e9b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18029679c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18029679c`

## string_xrefs

- `0x180295dbf`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180295e2b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180295eb5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180295f64`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18029601e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802960cf`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802962af`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802963a0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802964c8`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802965d5`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18029663e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802967b7`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x18029692a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace(
        Microsoft::Diagnostics::UtcApiManager *this,
        const wchar_t *a2)
{
  _QWORD *v4; // rcx
  WCHAR *v5; // rcx
  const WCHAR *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  PWSTR *v9; // rax
  unsigned int v10; // ebx
  struct Microsoft::Diagnostics::TraceManager *TraceManager; // rdi
  struct _GUID *OwnerScenarioId; // rax
  __int64 UtcTemporaryPath; // rax
  __int64 v14; // r8
  void *appended; // rax
  __int64 v16; // rax
  void *v17; // rbx
  __int64 v18; // r8
  int v19; // eax
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // r8
  __int128 v23; // xmm6
  int v24; // edx
  int v25; // eax
  __int64 v26; // r8
  __int64 v27; // r8
  int v28; // ecx
  int v29; // eax
  wil::details::in1diag3 *v30; // rcx
  int RpcImpersonationToken; // eax
  __int64 v32; // r8
  struct Microsoft::Diagnostics::UserManager *UserManager; // rax
  __int64 v34; // r8
  struct Microsoft::Diagnostics::UserManager *v35; // rax
  Microsoft::Diagnostics::UserManager *v36; // r8
  __int64 UserContextForSid; // rbx
  int UserToken; // eax
  __int64 v39; // r8
  __int64 v40; // r8
  __int64 v41; // r8
  int v42; // eax
  unsigned int v43; // ebx
  __int64 v44; // r8
  __int64 v45; // r8
  unsigned int v46; // [rsp+20h] [rbp-1D8h]
  int v47; // [rsp+20h] [rbp-1D8h]
  int v48; // [rsp+20h] [rbp-1D8h]
  int v49; // [rsp+20h] [rbp-1D8h]
  char v50; // [rsp+40h] [rbp-1B8h] BYREF
  int v51; // [rsp+41h] [rbp-1B7h] BYREF
  PWSTR *v52; // [rsp+48h] [rbp-1B0h] BYREF
  char v53; // [rsp+50h] [rbp-1A8h]
  unsigned int v54[4]; // [rsp+60h] [rbp-198h] BYREF
  struct _GUID v55; // [rsp+70h] [rbp-188h] BYREF
  _QWORD v56[2]; // [rsp+80h] [rbp-178h] BYREF
  __int128 v57; // [rsp+90h] [rbp-168h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-158h] BYREF
  char v59; // [rsp+A8h] [rbp-150h]
  _BYTE v60[16]; // [rsp+B0h] [rbp-148h] BYREF
  WCHAR Src; // [rsp+C0h] [rbp-138h] BYREF
  __int64 v62; // [rsp+C2h] [rbp-136h]
  int v63; // [rsp+CAh] [rbp-12Eh]
  __int16 v64; // [rsp+CEh] [rbp-12Ah]
  __m128i v65; // [rsp+D0h] [rbp-128h]
  PWSTR pszPathOut[3]; // [rsp+E0h] [rbp-118h] BYREF
  unsigned __int64 v67; // [rsp+F8h] [rbp-100h]
  _OWORD v68[2]; // [rsp+100h] [rbp-F8h] BYREF
  _QWORD v69[2]; // [rsp+120h] [rbp-D8h] BYREF
  __int64 v70; // [rsp+130h] [rbp-C8h]
  unsigned __int64 v71; // [rsp+138h] [rbp-C0h]
  WCHAR v72; // [rsp+140h] [rbp-B8h] BYREF
  __int64 v73; // [rsp+142h] [rbp-B6h]
  int v74; // [rsp+14Ah] [rbp-AEh]
  __int16 v75; // [rsp+14Eh] [rbp-AAh]
  __m128i si128; // [rsp+150h] [rbp-A8h]
  _BYTE v77[32]; // [rsp+170h] [rbp-88h] BYREF
  WCHAR v78[16]; // [rsp+190h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v46);
    return 2147942487LL;
  }
  std::wstring::wstring(v69, a2);
  v4 = v69;
  if ( v71 > 7 )
    v4 = (_QWORD *)v69[0];
  if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v4, v70, 0, 47) != -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD18,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v46);
    std::wstring::_Tidy_deallocate(v69);
    return 2147942487LL;
  }
  std::wstring::wstring(pszPathOut, v70, 0);
  v5 = (WCHAR *)pszPathOut;
  if ( v67 > 7 )
    v5 = pszPathOut[0];
  if ( PathCchCanonicalizeEx(v5, (size_t)pszPathOut[2] + 1, a2, 1u) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v46);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v69);
    return 2147942487LL;
  }
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)pszPathOut);
  v6 = (const WCHAR *)pszPathOut;
  if ( v67 > 7 )
    v6 = pszPathOut[0];
  if ( GetFileAttributesW(v6) != -1 )
  {
    if ( (unsigned int)dword_1804543B0 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          byte_1803EBBD1);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v46);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v69);
    return 2147942487LL;
  }
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
  {
    v9 = pszPathOut;
    if ( v67 > 7 )
      v9 = (PWSTR *)pszPathOut[0];
    *(_QWORD *)v54 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_1804543B0,
      (unsigned int)byte_1803EBC1B,
      v7,
      v8,
      (__int64)v54);
  }
  v52 = pszPathOut;
  v53 = 1;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631A0, 0, 0) )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xD45,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x15,
            v46);
    v53 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
LABEL_40:
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v69);
    return v10;
  }
  TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  *(_QWORD *)&v68[0] = *((_QWORD *)TraceManager + 2);
  *((_QWORD *)&v68[0] + 1) = (char *)TraceManager + 272;
  OwnerScenarioId = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerScenarioId(
                      (Microsoft::Diagnostics::TraceSlotSafeWrapper *)v68,
                      &v55);
  if ( memcmp_0(OwnerScenarioId, &Microsoft::Diagnostics::UtcApiManager::k_customTraceId, 0x10u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C5100DLL,
      v46);
    v53 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v69);
    return 2277838861LL;
  }
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)&v72);
  UtcTemporaryPath = Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(v78);
  v57 = *(_OWORD *)std::wstring::operator std::wstring_view(UtcTemporaryPath, &v55, v14);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(&v72);
  v16 = Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  WORD1(v57) = 0;
  LOBYTE(v54[0]) = 1;
  *(_WORD *)((char *)v54 + 1) = BYTE1(v57);
  HIBYTE(v54[0]) = 0;
  v54[1] = 2097153;
  *(_QWORD *)&v54[2] = 0;
  v17 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v16, v54);
  Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  Microsoft::Diagnostics::WideStringStream::operator<<(v17);
  std::wstring::_Tidy_deallocate(v78);
  Src = v72;
  v62 = v73;
  v63 = v74;
  v64 = v75;
  v65 = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v72 = 0;
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(&Src);
  v57 = *(_OWORD *)&off_18036C4E8;
  *(_OWORD *)v54 = *(_OWORD *)std::wstring::operator std::wstring_view(&Src, &v55, v18);
  v19 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v54, 0, &v57);
  v10 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v19,
      v46);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v72);
    v53 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    goto LABEL_40;
  }
  *(_QWORD *)&v57 = &Src;
  BYTE8(v57) = 1;
  v58 = 0;
  v59 = 0;
  BYTE3(v58) = (unsigned int)Microsoft::Diagnostics::TraceSlotSafeWrapper::GetRunningWprTraceProfileType(v68) == 2;
  std::wstring::wstring(v77, &Src);
  *(_OWORD *)v54 = *(_OWORD *)&Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames;
  v20 = Microsoft::Diagnostics::Utils::String::AppendPath(v77, v54);
  v10 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD67,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v20,
      v46);
    std::wstring::_Tidy_deallocate(v77);
    v57 = *(_OWORD *)std::wstring::operator std::wstring_view(&Src, &v55, v22);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(&v57);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v72);
    v53 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    goto LABEL_40;
  }
  v23 = *(_OWORD *)std::wstring::operator std::wstring_view(v77, &v55, v21);
  *(_QWORD *)v54 = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)v68);
  LOBYTE(v24) = 0;
  v68[0] = v23;
  v25 = Microsoft::Diagnostics::TraceManager::SnapSlotTrace(
          (_DWORD)TraceManager,
          v24,
          (unsigned int)&Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
          (unsigned int)&GUID_NULL,
          (__int64)v54,
          (__int64)v68,
          0,
          (__int64)&v58);
  v10 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v25,
      v47);
    std::wstring::_Tidy_deallocate(v77);
    v57 = *(_OWORD *)std::wstring::operator std::wstring_view(&Src, &v55, v27);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(&v57);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v72);
    v53 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    goto LABEL_40;
  }
  LOWORD(v54[0]) = 1;
  v68[0] = *(_OWORD *)&off_180385360;
  v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(&Src, v60, v26);
  v29 = Microsoft::Diagnostics::UtcApiManager::SnapAgentTraces(
          v28,
          (unsigned int)&v55,
          (unsigned int)v68,
          (unsigned int)&Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
          1,
          v54[0]);
  v30 = retaddr;
  if ( v29 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD72,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v29,
      v48);
  v56[0] = 0;
  v68[0] = 0;
  v68[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v68[0]) = 0;
  *(_QWORD *)v54 = 0;
  RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(v30, v54, v68);
  v10 = RpcImpersonationToken;
  if ( RpcImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD79,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)RpcImpersonationToken,
      v48);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
    std::wstring::_Tidy_deallocate(v68);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
    std::wstring::_Tidy_deallocate(v77);
    v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(&Src, v60, v32);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(&v55);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v72);
    v53 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    goto LABEL_40;
  }
  UserManager = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(v68, v60, UserManager);
  if ( (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v34, &v55) )
  {
    v35 = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(v68, v60, v35);
    UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v36);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v56,
      0);
    UserToken = UMgrQueryUserToken(UserContextForSid, v56);
    v10 = UserToken;
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD7E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)UserToken,
        v48);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
      std::wstring::_Tidy_deallocate(v68);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
      std::wstring::_Tidy_deallocate(v77);
      v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(&Src, v60, v39);
      Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(&v55);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(&v72);
      v53 = 0;
      Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
      goto LABEL_40;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
  std::wstring::_Tidy_deallocate(v68);
  LOWORD(v51) = 0;
  v50 = 0;
  v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(pszPathOut, v60, v40);
  v68[0] = *(_OWORD *)std::wstring::operator std::wstring_view(&Src, v78, v41);
  v42 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
          (unsigned int)v68,
          (unsigned int)&v55,
          (unsigned int)v56,
          (unsigned int)&v51 + 1,
          (__int64)&v51,
          (__int64)&v50);
  v43 = v42;
  if ( v42 >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
    std::wstring::_Tidy_deallocate(v77);
    v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(&Src, v78, v45);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(&v55);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v72);
    if ( v53 )
    {
      v53 = 0;
      Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    }
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v69);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v42,
      v49);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v56);
    std::wstring::_Tidy_deallocate(v77);
    v55 = *(struct _GUID *)std::wstring::operator std::wstring_view(&Src, v78, v44);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(&v55);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v72);
    if ( v53 )
    {
      v53 = 0;
      Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v52);
    }
    std::wstring::_Tidy_deallocate(pszPathOut);
    std::wstring::_Tidy_deallocate(v69);
    return v43;
  }
}

```

## disassembly

```asm
0x180295d80  mov     rax, rsp
0x180295d83  push    rbx
0x180295d84  push    rsi
0x180295d85  push    rdi
0x180295d86  push    r14
0x180295d88  sub     rsp, 1D8h
0x180295d8f  movaps  xmmword ptr [rax-38h], xmm6
0x180295d93  mov     rax, cs:__security_cookie
0x180295d9a  xor     rax, rsp
0x180295d9d  mov     [rsp+1F8h+var_48], rax
0x180295da5  mov     rbx, rdx
0x180295da8  xor     esi, esi
0x180295daa  test    rdx, rdx
0x180295dad  jnz     short loc_180295DD7
0x180295daf  mov     rcx, [rsp+1F8h]; this
0x180295db7  mov     ebx, 80070057h
0x180295dbc  mov     r9d, ebx; char *
0x180295dbf  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180295dc6  mov     edx, 0D12h; void *
0x180295dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180295dd0  mov     eax, ebx
0x180295dd2  jmp     loc_180296A71
0x180295dd7  lea     rcx, [rsp+1F8h+var_D8]
0x180295ddf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180295de4  nop
0x180295de5  lea     rcx, [rsp+1F8h+var_D8]
0x180295ded  cmp     [rsp+1F8h+var_C0], 7
0x180295df6  cmova   rcx, [rsp+1F8h+var_D8]
0x180295dff  mov     r9d, 2Fh ; '/'
0x180295e05  xor     r8d, r8d
0x180295e08  mov     rdx, [rsp+1F8h+var_C8]
0x180295e10  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180295e15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180295e19  jz      short loc_180295E51
0x180295e1b  mov     rcx, [rsp+1F8h]; this
0x180295e23  mov     ebx, 80070057h
0x180295e28  mov     r9d, ebx; char *
0x180295e2b  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180295e32  mov     edx, 0D18h; void *
0x180295e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180295e3c  nop
0x180295e3d  lea     rcx, [rsp+1F8h+var_D8]
0x180295e45  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180295e4a  mov     eax, ebx
0x180295e4c  jmp     loc_180296A71
0x180295e51  xor     r8d, r8d
0x180295e54  mov     rdx, [rsp+1F8h+var_C8]
0x180295e5c  lea     rcx, [rsp+1F8h+pszPathOut]
0x180295e64  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x180295e69  nop
0x180295e6a  mov     rdx, [rsp+1F8h+var_108]
0x180295e72  lea     rcx, [rsp+1F8h+pszPathOut]
0x180295e7a  cmp     [rsp+1F8h+var_100], 7
0x180295e83  cmova   rcx, [rsp+1F8h+pszPathOut]; pszPathOut
0x180295e8c  inc     rdx; cchPathOut
0x180295e8f  mov     r14d, 1
0x180295e95  mov     r9d, r14d; dwFlags
0x180295e98  mov     r8, rbx; pszPathIn
0x180295e9b  call    cs:__imp_PathCchCanonicalizeEx
0x180295ea1  test    eax, eax
0x180295ea3  jns     short loc_180295EE9
0x180295ea5  mov     rcx, [rsp+1F8h]; this
0x180295ead  mov     ebx, 80070057h
0x180295eb2  mov     r9d, ebx; char *
0x180295eb5  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180295ebc  mov     edx, 0D1Fh; void *
0x180295ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180295ec6  nop
0x180295ec7  lea     rcx, [rsp+1F8h+pszPathOut]
0x180295ecf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180295ed4  nop
0x180295ed5  lea     rcx, [rsp+1F8h+var_D8]
0x180295edd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180295ee2  mov     eax, ebx
0x180295ee4  jmp     loc_180296A71
0x180295ee9  xor     r8d, r8d
0x180295eec  mov     dl, r14b
0x180295eef  lea     rcx, [rsp+1F8h+pszPathOut]; lpSrc
0x180295ef7  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180295efc  lea     rcx, [rsp+1F8h+pszPathOut]
0x180295f04  cmp     [rsp+1F8h+var_100], 7
0x180295f0d  cmova   rcx, [rsp+1F8h+pszPathOut]; lpFileName
0x180295f16  call    cs:__imp_GetFileAttributesW
0x180295f1c  cmp     eax, 0FFFFFFFFh
0x180295f1f  mov     eax, cs:dword_1804543B0
0x180295f25  jz      short loc_180295F98
0x180295f27  cmp     eax, 3
0x180295f2a  jbe     short loc_180295F54
0x180295f2c  mov     edx, 2000h
0x180295f31  lea     rcx, dword_1804543B0
0x180295f38  call    _tlgKeywordOn
0x180295f3d  test    al, al
0x180295f3f  jz      short loc_180295F54
0x180295f41  lea     rdx, byte_1803EBBD1
0x180295f48  lea     rcx, dword_1804543B0
0x180295f4f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180295f54  mov     rcx, [rsp+1F8h]; this
0x180295f5c  mov     ebx, 80070057h
0x180295f61  mov     r9d, ebx; char *
0x180295f64  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180295f6b  mov     edx, 0D2Eh; void *
0x180295f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180295f75  nop
0x180295f76  lea     rcx, [rsp+1F8h+pszPathOut]
0x180295f7e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180295f83  nop
0x180295f84  lea     rcx, [rsp+1F8h+var_D8]
0x180295f8c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180295f91  mov     eax, ebx
0x180295f93  jmp     loc_180296A71
0x180295f98  cmp     eax, 4
0x180295f9b  jbe     short loc_180295FEE
0x180295f9d  mov     edx, 2000h
0x180295fa2  lea     rcx, dword_1804543B0
0x180295fa9  call    _tlgKeywordOn
0x180295fae  test    al, al
0x180295fb0  jz      short loc_180295FEE
0x180295fb2  lea     rax, [rsp+1F8h+pszPathOut]
0x180295fba  cmp     [rsp+1F8h+var_100], 7
0x180295fc3  cmova   rax, [rsp+1F8h+pszPathOut]
0x180295fcc  mov     qword ptr [rsp+1F8h+var_198], rax
0x180295fd1  lea     rax, [rsp+1F8h+var_198]
0x180295fd6  mov     qword ptr [rsp+1F8h+var_1D8], rax; int
0x180295fdb  lea     rdx, byte_1803EBC1B
0x180295fe2  lea     rcx, dword_1804543B0
0x180295fe9  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180295fee  lea     rax, [rsp+1F8h+pszPathOut]
0x180295ff6  mov     [rsp+1F8h+var_1B0], rax
0x180295ffb  mov     [rsp+1F8h+var_1A8], r14b
0x180296000  mov     rcx, rsi
0x180296003  xor     eax, eax
0x180296005  lock cmpxchg qword ptr cs:xmmword_1804631A0, rcx
0x18029600e  jnz     short loc_18029606A
0x180296010  mov     rcx, [rsp+1F8h]; this
0x180296018  mov     r9d, 15h; char *
0x18029601e  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180296025  mov     edx, 0D45h; void *
0x18029602a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18029602f  mov     ebx, eax
0x180296031  cmp     [rsp+1F8h+var_1A8], sil
0x180296036  jz      short loc_180296048
0x180296038  mov     [rsp+1F8h+var_1A8], sil
0x18029603d  lea     rcx, [rsp+1F8h+var_1B0]
0x180296042  call    _Microsoft__Diagnostics__UtcApiManager__SnapCustomTrace____3____lambda_1___operator__
0x180296047  nop
0x180296048  lea     rcx, [rsp+1F8h+pszPathOut]
0x180296050  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296055  nop
0x180296056  lea     rcx, [rsp+1F8h+var_D8]
0x18029605e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296063  mov     eax, ebx
0x180296065  jmp     loc_180296A71
0x18029606a  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180296071  call    ?GetTraceManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTraceManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTraceManager(void)
0x180296076  mov     rdi, rax
0x180296079  mov     rcx, [rax+10h]
0x18029607d  mov     qword ptr [rsp+1F8h+var_F8], rcx
0x180296085  lea     rcx, [rax+110h]
0x18029608c  mov     qword ptr [rsp+1F8h+var_F8+8], rcx
0x180296094  lea     rdx, [rsp+1F8h+var_188]; retstr
0x180296099  lea     rcx, [rsp+1F8h+var_F8]; this
0x1802960a1  call    ?GetOwnerScenarioId@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA?AU_GUID@@XZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerScenarioId(void)
0x1802960a6  mov     r8d, 10h; Size
0x1802960ac  lea     rdx, ?k_customTraceId@UtcApiManager@Diagnostics@Microsoft@@2U_GUID@@B; Buf2
0x1802960b3  mov     rcx, rax; Buf1
0x1802960b6  call    memcmp_0
0x1802960bb  test    eax, eax
0x1802960bd  jz      short loc_18029611A
0x1802960bf  mov     rcx, [rsp+1F8h]; this
0x1802960c7  mov     ebx, 87C5100Dh
0x1802960cc  mov     r9d, ebx; char *
0x1802960cf  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1802960d6  mov     edx, 0D4Dh; void *
0x1802960db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802960e0  nop
0x1802960e1  cmp     [rsp+1F8h+var_1A8], sil
0x1802960e6  jz      short loc_1802960F8
0x1802960e8  mov     [rsp+1F8h+var_1A8], sil
0x1802960ed  lea     rcx, [rsp+1F8h+var_1B0]
0x1802960f2  call    _Microsoft__Diagnostics__UtcApiManager__SnapCustomTrace____3____lambda_1___operator__
0x1802960f7  nop
0x1802960f8  lea     rcx, [rsp+1F8h+pszPathOut]
0x180296100  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296105  nop
0x180296106  lea     rcx, [rsp+1F8h+var_D8]
0x18029610e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296113  mov     eax, ebx
0x180296115  jmp     loc_180296A71
0x18029611a  lea     rcx, [rsp+1F8h+var_B8]; this
0x180296122  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x180296127  nop
0x180296128  lea     rcx, [rsp+1F8h+var_68]; lpSrc
0x180296130  call    ?GetUtcTemporaryPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(void)
0x180296135  nop
0x180296136  lea     rdx, [rsp+1F8h+var_188]
0x18029613b  mov     rcx, rax
0x18029613e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180296143  movups  xmm0, xmmword ptr [rax]
0x180296146  movdqu  [rsp+1F8h+var_168], xmm0
0x18029614f  lea     rdx, [rsp+1F8h+var_168]
0x180296157  lea     rcx, [rsp+1F8h+var_B8]; Src
0x18029615f  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x180296164  lea     rdx, aDiagtrackCusto; "DiagTrack_CustomTrace_"
0x18029616b  mov     rcx, rax; Src
0x18029616e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x180296173  mov     word ptr [rsp+1F8h+var_168+2], si
0x18029617b  mov     byte ptr [rsp+1F8h+var_198], r14b
0x180296180  movzx   ecx, word ptr [rsp+1F8h+var_168+1]
0x180296188  mov     word ptr [rsp+1F8h+var_198+1], cx
0x18029618d  mov     cl, byte ptr [rsp+1F8h+var_168+3]
0x180296194  mov     byte ptr [rsp+1F8h+var_198+3], cl
0x180296198  mov     [rsp+1F8h+var_198+4], 200001h
0x1802961a0  mov     qword ptr [rsp+1F8h+var_198+8], rsi
0x1802961a5  lea     rdx, [rsp+1F8h+var_198]
0x1802961aa  mov     rcx, rax
0x1802961ad  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1802961b2  mov     rbx, rax
0x1802961b5  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x1802961ba  mov     rdx, rax
0x1802961bd  mov     rcx, rbx; Src
0x1802961c0  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x1802961c5  nop
0x1802961c6  lea     rcx, [rsp+1F8h+var_68]
0x1802961ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802961d3  movzx   eax, [rsp+1F8h+var_B8]
0x1802961db  mov     [rsp+1F8h+Src], ax
0x1802961e3  movsd   xmm0, [rsp+1F8h+var_B6]
0x1802961ec  movsd   [rsp+1F8h+var_136], xmm0
0x1802961f5  mov     eax, [rsp+1F8h+var_AE]
0x1802961fc  mov     [rsp+1F8h+var_12E], eax
0x180296203  movzx   eax, [rsp+1F8h+var_AA]
0x18029620b  mov     [rsp+1F8h+var_12A], ax
0x180296213  mov     rax, qword ptr [rsp+1F8h+var_A8]
0x18029621b  mov     qword ptr [rsp+1F8h+var_128], rax
0x180296223  mov     rax, qword ptr [rsp+1F8h+var_A8+8]
0x18029622b  mov     qword ptr [rsp+1F8h+var_128+8], rax
0x180296233  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18029623b  movdqu  [rsp+1F8h+var_A8], xmm0
0x180296244  mov     [rsp+1F8h+var_B8], si
0x18029624c  xor     r8d, r8d
0x18029624f  mov     dl, r14b
0x180296252  lea     rcx, [rsp+1F8h+Src]; lpSrc
0x18029625a  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18029625f  movups  xmm0, xmmword ptr cs:off_18036C4E8; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x180296266  movdqu  [rsp+1F8h+var_168], xmm0
0x18029626f  lea     rdx, [rsp+1F8h+var_188]
0x180296274  lea     rcx, [rsp+1F8h+Src]
0x18029627c  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180296281  movups  xmm0, xmmword ptr [rax]
0x180296284  movdqu  xmmword ptr [rsp+1F8h+var_198], xmm0
0x18029628a  lea     r8, [rsp+1F8h+var_168]
0x180296292  xor     edx, edx
0x180296294  lea     rcx, [rsp+1F8h+var_198]
0x180296299  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x18029629e  mov     ebx, eax
0x1802962a0  test    eax, eax
0x1802962a2  jns     short loc_180296316
0x1802962a4  mov     rcx, [rsp+1F8h]; this
0x1802962ac  mov     r9d, eax; char *
0x1802962af  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1802962b6  mov     edx, 0D5Bh; void *
0x1802962bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802962c0  nop
0x1802962c1  lea     rcx, [rsp+1F8h+Src]
0x1802962c9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802962ce  nop
0x1802962cf  lea     rcx, [rsp+1F8h+var_B8]
0x1802962d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802962dc  nop
0x1802962dd  cmp     [rsp+1F8h+var_1A8], sil
0x1802962e2  jz      short loc_1802962F4
0x1802962e4  mov     [rsp+1F8h+var_1A8], sil
0x1802962e9  lea     rcx, [rsp+1F8h+var_1B0]
0x1802962ee  call    _Microsoft__Diagnostics__UtcApiManager__SnapCustomTrace____3____lambda_1___operator__
0x1802962f3  nop
0x1802962f4  lea     rcx, [rsp+1F8h+pszPathOut]
0x1802962fc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180296301  nop
0x180296302  lea     rcx, [rsp+1F8h+var_D8]
0x18029630a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029630f  mov     eax, ebx
0x180296311  jmp     loc_180296A71
0x180296316  lea     rax, [rsp+1F8h+Src]
0x18029631e  mov     qword ptr [rsp+1F8h+var_168], rax
0x180296326  mov     byte ptr [rsp+1F8h+var_168+8], r14b
0x18029632e  mov     [rsp+1F8h+var_158], rsi
0x180296336  mov     [rsp+1F8h+var_150], sil
0x18029633e  lea     rcx, [rsp+1F8h+var_F8]
0x180296346  call    ?GetRunningWprTraceProfileType@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA?AW4__MIDL_IProfile_0001@@XZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetRunningWprTraceProfileType(void)
0x18029634b  cmp     eax, 2
0x18029634e  setz    byte ptr [rsp+1F8h+var_158+3]
0x180296356  lea     rdx, [rsp+1F8h+Src]
0x18029635e  lea     rcx, [rsp+1F8h+var_88]
0x180296366  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18029636b  nop
0x18029636c  movaps  xmm0, xmmword ptr cs:?k_traceSlotOutputNames@TraceSlot@Diagnostics@Microsoft@@2QBV?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const near * const Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames
0x180296373  movdqu  xmmword ptr [rsp+1F8h+var_198], xmm0
0x180296379  lea     rdx, [rsp+1F8h+var_198]
0x18029637e  lea     rcx, [rsp+1F8h+var_88]
0x180296386  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
  ... truncated ...
```
