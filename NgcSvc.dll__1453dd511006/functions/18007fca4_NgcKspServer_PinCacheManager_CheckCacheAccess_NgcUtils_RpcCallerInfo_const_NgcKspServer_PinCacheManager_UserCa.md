# NgcKspServer::PinCacheManager::CheckCacheAccess(NgcUtils::RpcCallerInfo const &,NgcKspServer::PinCacheManager::UserCacheEntry const *,NgcUtils::NgcKeyName const &)

- ea: `0x18007fca4`
- end: `0x1800806b0`
- name: `?CheckCacheAccess@PinCacheManager@NgcKspServer@@CAJAEBVRpcCallerInfo@NgcUtils@@PEBVUserCacheEntry@12@AEBVNgcKeyName@4@@Z`
- size: `2572`
- prototype: `__int64 __fastcall(const struct NgcUtils::RpcCallerInfo *, const struct NgcKspServer::PinCacheManager::UserCacheEntry *, const struct NgcUtils::NgcKeyName *)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180057e74`

## callees

- `0x18000e570`
- `0x18000e960`
- `0x180010d1c`
- `0x1800137c0`
- `0x1800138c0`
- `0x180025a80`
- `0x180026410`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x180028d18`
- `0x180029f0c`
- `0x1800323d0`
- `0x180036ee0`
- `0x180046d90`
- `0x180048394`
- `0x18004d9c8`
- `0x1800527ac`
- `0x1800533a4`
- `0x18005cee0`
- `0x18005f8e8`
- `0x18007f408`
- `0x18007f438`
- `0x18007f518`
- `0x18007f5fc`
- `0x18007fa34`
- `0x18007fca4`
- `0x1800806b8`
- `0x180080b78`
- `0x180081064`
- `0x180081098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp_l` at `0x180080287`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp_l` at `0x180080287`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800801eb`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800801eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007fdb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800802dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007fdb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800802dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008054e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008054e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180080030`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800801a4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180080030`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800801a4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007fd6d`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007fd6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800800c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800800c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180080113`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180080113`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008012d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008012d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008017c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008017c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007ff6b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18007ff6b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180080016`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180080016`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180080060`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180080060`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18007ff52`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18007ff52`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetCandidateUserSessionIds` at `0x18007fe8e`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetCandidateUserSessionIds` at `0x18007fe8e`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetNonCandidateUserSessionIds` at `0x18007fef3`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetNonCandidateUserSessionIds` at `0x18007fef3`

## string_xrefs

- `0x18007fe4d`: `onecore\ds\security\ngc\kspsvc\svc\pincachemanager.cpp`
- `0x1800805f5`: `onecore\ds\security\ngc\kspsvc\svc\pincachemanager.cpp`
- `0x180080078`: `CLSID\%s\LocalServer32`
- `0x1800801bf`: `\oobe\UserOOBEBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall NgcKspServer::PinCacheManager::CheckCacheAccess(
        const struct NgcUtils::RpcCallerInfo *a1,
        RTL_SRWLOCK *a2,
        const struct NgcUtils::NgcKeyName *a3)
{
  unsigned int v6; // r14d
  int Ptr; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  char v10; // al
  __m128i si128; // xmm6
  char *v12; // rdi
  const char *v13; // r9
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // r14d
  WCHAR *v17; // rbx
  signed int v18; // ebx
  LSTATUS v19; // eax
  LSTATUS ValueW; // eax
  struct localeinfo_struct *v21; // r9
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  WCHAR *v24; // rbx
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  unsigned int v27; // ebx
  const char *v29; // r9
  int phkResult; // [rsp+20h] [rbp-658h]
  char v31; // [rsp+40h] [rbp-638h]
  char *pcbData; // [rsp+44h] [rbp-634h] BYREF
  DWORD dwSize; // [rsp+4Ch] [rbp-62Ch] BYREF
  __int64 v34; // [rsp+50h] [rbp-628h] BYREF
  __int128 v35; // [rsp+58h] [rbp-620h] BYREF
  __int64 v36; // [rsp+68h] [rbp-610h]
  unsigned int v37; // [rsp+70h] [rbp-608h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-600h] BYREF
  __int128 v39; // [rsp+80h] [rbp-5F8h] BYREF
  __int64 v40; // [rsp+90h] [rbp-5E8h]
  LPWSTR lpExeName; // [rsp+98h] [rbp-5E0h] BYREF
  RTL_SRWLOCK *v42; // [rsp+A0h] [rbp-5D8h] BYREF
  int v43; // [rsp+A8h] [rbp-5D0h] BYREF
  char *v44; // [rsp+B0h] [rbp-5C8h] BYREF
  HKEY *p_hkey; // [rsp+B8h] [rbp-5C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-5B8h]
  RTL_SRWLOCK *v47; // [rsp+C8h] [rbp-5B0h]
  RTL_SRWLOCK *v48; // [rsp+D0h] [rbp-5A8h]
  const struct NgcUtils::NgcKeyName *v49; // [rsp+D8h] [rbp-5A0h]
  _QWORD v50[3]; // [rsp+E0h] [rbp-598h] BYREF
  __int16 v51; // [rsp+F8h] [rbp-580h]
  _QWORD v52[3]; // [rsp+100h] [rbp-578h] BYREF
  __int16 v53; // [rsp+118h] [rbp-560h]
  char v54; // [rsp+120h] [rbp-558h] BYREF
  char v55; // [rsp+128h] [rbp-550h] BYREF
  _BYTE v56[8]; // [rsp+130h] [rbp-548h] BYREF
  _BYTE v57[8]; // [rsp+138h] [rbp-540h] BYREF
  _BYTE v58[56]; // [rsp+140h] [rbp-538h] BYREF
  wchar_t *String1[2]; // [rsp+178h] [rbp-500h] BYREF
  __m128i v60; // [rsp+188h] [rbp-4F0h]
  wchar_t *String2[5]; // [rsp+198h] [rbp-4E0h] BYREF
  _BYTE v62[80]; // [rsp+1C0h] [rbp-4B8h] BYREF
  WCHAR Buffer[264]; // [rsp+210h] [rbp-468h] BYREF
  WCHAR SubKey[256]; // [rsp+420h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+678h] [rbp+0h]

  v49 = a3;
  v48 = a2;
  v6 = 0;
  LODWORD(hkey) = 0;
  pcbData = 0;
  v50[0] = &pcbData;
  v50[1] = a1;
  v50[2] = a3;
  v51 = 256;
  NgcUtils::LsaProcessId::GetLsaProcessId((unsigned int *)&pcbData + 1);
  if ( HIDWORD(pcbData) && HIDWORD(pcbData) == *((_DWORD *)a1 + 15) )
  {
    if ( (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&unk_180104B80,
        0);
LABEL_79:
    v8 = (unsigned int)pcbData;
LABEL_80:
    wil::details::ScopeExitFnGuard__lambda_4b59f22bec208b5e18197b24c0842274___::operator()(v50);
    return v8;
  }
  if ( IsWellKnownSid(*((PSID *)a1 + 3), WinLocalSystemSid) )
  {
    if ( (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180104B55,
        0);
    goto LABEL_79;
  }
  SRWLock = a2 + 7;
  AcquireSRWLockShared(a2 + 7);
  v42 = a2 + 7;
  v47 = a2 + 3;
  Ptr = (int)a2[3].Ptr;
  if ( Ptr != -1
    && *((_DWORD *)a1 + 14) == Ptr
    && (unsigned int)NgcKspServer::EqualSidVectors((char *)a1 + 24, a2)
    && (unsigned int)NgcKspServer::EqualSidVectors((char *)a1 + 24, a3) )
  {
    if ( (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180104B21,
        0);
    v8 = (unsigned int)pcbData;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v42);
    goto LABEL_80;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v42);
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl'::`2'::impl,
    v9);
  if ( !(unsigned __int8)IsCamIsCandidateUserPresent() )
  {
LABEL_75:
    LODWORD(pcbData) = -2146893808;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x44F,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\pincachemanager.cpp",
        (const char *)(unsigned int)pcbData,
        phkResult);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      dwSize = (unsigned int)pcbData;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&word_180104A76,
        0,
        0,
        (__int64)&dwSize);
    }
    goto LABEL_79;
  }
  v10 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    if ( v10 )
      goto LABEL_75;
    v37 = 0;
    v34 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    if ( (int)CamGetCandidateUserSessionIds(&v37, &v34) < 0 )
      goto LABEL_74;
    v35 = 0;
    v36 = 0;
    std::vector<unsigned long>::insert<unsigned long *,0>(
      (unsigned int)&v35,
      (unsigned int)&v54,
      0,
      v34,
      v34 + 4LL * v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    if ( (int)CamGetNonCandidateUserSessionIds(&v37, &v34) < 0 )
      goto LABEL_72;
    v39 = 0;
    v40 = 0;
    std::vector<unsigned long>::insert<unsigned long *,0>(
      (unsigned int)&v39,
      (unsigned int)&v55,
      0,
      v34,
      v34 + 4LL * v37);
    v43 = 0;
    if ( (int)CamIsCandidateUser(*((_QWORD *)a1 + 3), &v43) < 0 )
      goto LABEL_70;
    v12 = (char *)OpenProcess(0x1000u, 0, *((_DWORD *)a1 + 15));
    v44 = v12;
    if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)0x428,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\pincachemanager.cpp",
          v29);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        dwSize = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180104AE9,
          0,
          0,
          (__int64)&dwSize);
      }
LABEL_69:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
LABEL_70:
      if ( (_QWORD)v39 )
      {
        std::_Deallocate<16>((void *)v39, (v40 - v39) & 0xFFFFFFFFFFFFFFFCuLL);
        v39 = 0;
        v40 = 0;
      }
LABEL_72:
      if ( (_QWORD)v35 )
      {
        std::_Deallocate<16>((void *)v35, (v36 - v35) & 0xFFFFFFFFFFFFFFFCuLL);
        v35 = 0;
        v36 = 0;
      }
LABEL_74:
      wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>(&v34);
      goto LABEL_75;
    }
    lpExeName = 0;
    dwSize = 260;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v42,
      0,
      0x104u,
      v13);
    v16 = v6 | 2;
    LODWORD(hkey) = v16;
    if ( !v42 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v14, v15);
    v31 = 0;
    LODWORD(hkey) = v16 & 0xFFFFFFFD;
    v6 = v16 & 0xFFFFFFFC | 1;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpExeName,
      &v42);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
    v17 = lpExeName;
    if ( QueryFullProcessImageNameW(v12, 0, lpExeName, &dwSize) )
    {
      GetLongPathNameW(v17, v17, 0x104u);
      std::wstring::wstring((char **)String2, v17);
      HIDWORD(pcbData) = 0;
      v18 = SHStringFromGUIDW(USER_OOBE_BROKER_CLS_ID, v62, 39);
      if ( v18 >= 0 )
      {
        v18 = StringCchPrintfW(SubKey, 0x100u, L"CLSID\\%s\\LocalServer32", v62);
        if ( v18 >= 0 )
        {
          hkey = 0;
          v19 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hkey);
          v18 = v19;
          if ( v19 > 0 )
            v18 = (unsigned __int16)v19 | 0x80070000;
          if ( v18 >= 0 )
          {
            HIDWORD(pcbData) = 520;
            ValueW = RegGetValueW(hkey, 0, &sourceString, 2u, 0, Buffer, (LPDWORD)&pcbData + 1);
            v18 = ValueW;
            if ( ValueW > 0 )
              v18 = (unsigned __int16)ValueW | 0x80070000;
            RegCloseKey(hkey);
          }
        }
      }
      *(_OWORD *)String1 = 0;
      v60 = si128;
      LOWORD(String1[0]) = 0;
      if ( v18 < 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        HIDWORD(pcbData) = GetSystemDirectoryW(Buffer, 0x104u);
        if ( !HIDWORD(pcbData) )
          goto LABEL_64;
        GetLongPathNameW(Buffer, Buffer, 0x104u);
        std::wstring::assign(String1, Buffer);
        std::wstring::append(String1, L"\\oobe\\UserOOBEBroker.exe");
      }
      else
      {
        std::wstring::assign(String1, Buffer);
      }
      if ( HIDWORD(pcbData) )
      {
        hkey = 0;
        hkey = (HKEY)_create_locale(0, "en-US");
        p_hkey = &hkey;
        v52[0] = retaddr;
        v52[1] = "onecore\\ds\\security\\ngc\\kspsvc\\svc\\pincachemanager.cpp";
        v52[2] = 0;
        v53 = 1042;
        wil::scope_exit_log__lambda_7b469132a53953dba2ab1d2085a9748a___(v58, v52, &p_hkey, hkey);
        v22 = (const wchar_t *)String2;
        if ( String2[3] > (wchar_t *)7 )
          v22 = String2[0];
        v23 = (const wchar_t *)String1;
        if ( v60.m128i_i64[1] > 7uLL )
          v23 = String1[0];
        if ( _wcsicmp_l(v23, v22, v21) )
        {
          wil::details::lambda_call_log__lambda_7b469132a53953dba2ab1d2085a9748a___::reset(v58);
LABEL_64:
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(String1);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(String2);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpExeName);
          goto LABEL_69;
        }
        v31 = 1;
        wil::details::lambda_call_log__lambda_7b469132a53953dba2ab1d2085a9748a___::reset(v58);
      }
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(String1);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(String2);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpExeName);
    v24 = (WCHAR *)SRWLock;
    AcquireSRWLockShared(SRWLock);
    lpExeName = v24;
    if ( LODWORD(v47->Ptr) == -1
      || (v25 = (_QWORD *)std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned long>>>,unsigned long>(
                            v56,
                            v39,
                            *((_QWORD *)&v39 + 1),
                            v47),
          *v25 != *((_QWORD *)&v39 + 1)) )
    {
      dwSize = *((_DWORD *)a1 + 14);
      v26 = (_QWORD *)std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned long>>>,unsigned long>(
                        v57,
                        v35,
                        *((_QWORD *)&v35 + 1),
                        &dwSize);
      if ( *v26 != *((_QWORD *)&v35 + 1)
        && !v43
        && v31
        && (unsigned int)NgcKspServer::EqualSidVectors((char *)a1 + 24, v48)
        && (unsigned int)NgcKspServer::EqualSidVectors((char *)a1 + 24, v49) )
      {
        break;
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&lpExeName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
    if ( (_QWORD)v39 )
    {
      std::_Deallocate<16>((void *)v39, (v40 - v39) & 0xFFFFFFFFFFFFFFFCuLL);
      v39 = 0;
      v40 = 0;
    }
    if ( (_QWORD)v35 )
    {
      std::_Deallocate<16>((void *)v35, (v36 - v35) & 0xFFFFFFFFFFFFFFFCuLL);
      v35 = 0;
      v36 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>(&v34);
    v10 = 1;
  }
  if ( (unsigned int)dword_180122070 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_180104A9F,
      0);
  v27 = (unsigned int)pcbData;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&lpExeName);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
  if ( (_QWORD)v39 )
  {
    std::_Deallocate<16>((void *)v39, (v40 - v39) & 0xFFFFFFFFFFFFFFFCuLL);
    v39 = 0;
    v40 = 0;
  }
  if ( (_QWORD)v35 )
  {
    std::_Deallocate<16>((void *)v35, (v36 - v35) & 0xFFFFFFFFFFFFFFFCuLL);
    v35 = 0;
    v36 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned long *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned long *,unsigned long *,0,std::nullptr_t>>(&v34);
  wil::details::ScopeExitFnGuard__lambda_4b59f22bec208b5e18197b24c0842274___::operator()(v50);
  return v27;
}

```

## disassembly

```asm
0x18007fca4  mov     r11, rsp
0x18007fca7  push    rbx
0x18007fca8  push    rsi
0x18007fca9  push    rdi
0x18007fcaa  push    r12
0x18007fcac  push    r13
0x18007fcae  push    r14
0x18007fcb0  push    r15
0x18007fcb2  sub     rsp, 640h
0x18007fcb9  movaps  xmmword ptr [r11-48h], xmm6
0x18007fcbe  mov     rax, cs:__security_cookie
0x18007fcc5  xor     rax, rsp
0x18007fcc8  mov     [rsp+678h+var_58], rax
0x18007fcd0  mov     r13, r8
0x18007fcd3  mov     [rsp+678h+var_5A0], r8
0x18007fcdb  mov     rbx, rdx
0x18007fcde  mov     [rsp+678h+var_5A8], rdx
0x18007fce6  mov     r15, rcx
0x18007fce9  xor     esi, esi
0x18007fceb  mov     r14d, esi
0x18007fcee  mov     dword ptr [rsp+678h+hkey], esi
0x18007fcf2  mov     dword ptr [rsp+678h+var_634], esi
0x18007fcf6  lea     rax, [rsp+678h+var_634]
0x18007fcfb  mov     [r11-598h], rax
0x18007fd02  mov     [r11-590h], rcx
0x18007fd09  mov     [r11-588h], r8
0x18007fd10  mov     [rsp+678h+var_580], 100h
0x18007fd1a  mov     dword ptr [rsp+678h+var_634+4], esi
0x18007fd1e  lea     rcx, [rsp+678h+var_634+4]; unsigned int *
0x18007fd23  call    ?GetLsaProcessId@LsaProcessId@NgcUtils@@SAJPEAK@Z; NgcUtils::LsaProcessId::GetLsaProcessId(ulong *)
0x18007fd28  mov     eax, dword ptr [rsp+678h+var_634+4]
0x18007fd2c  test    eax, eax
0x18007fd2e  jz      short loc_18007FD60
0x18007fd30  cmp     eax, [r15+3Ch]
0x18007fd34  jnz     short loc_18007FD60
0x18007fd36  mov     eax, cs:dword_180122070
0x18007fd3c  cmp     eax, 4
0x18007fd3f  jbe     loc_180080666
0x18007fd45  xor     r8d, r8d
0x18007fd48  lea     rdx, unk_180104B80
0x18007fd4f  lea     rcx, dword_180122070
0x18007fd56  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007fd5b  jmp     loc_180080666
0x18007fd60  lea     r12, [r15+18h]
0x18007fd64  mov     edx, 16h; WellKnownSidType
0x18007fd69  mov     rcx, [r12]; pSid
0x18007fd6d  call    cs:__imp_IsWellKnownSid
0x18007fd73  test    eax, eax
0x18007fd75  jz      short loc_18007FDA1
0x18007fd77  mov     eax, cs:dword_180122070
0x18007fd7d  cmp     eax, 4
0x18007fd80  jbe     loc_180080666
0x18007fd86  xor     r8d, r8d
0x18007fd89  lea     rdx, byte_180104B55
0x18007fd90  lea     rcx, dword_180122070
0x18007fd97  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007fd9c  jmp     loc_180080666
0x18007fda1  lea     rdi, [rbx+38h]
0x18007fda5  mov     [rsp+678h+SRWLock], rdi
0x18007fdad  mov     rcx, rdi; SRWLock
0x18007fdb0  call    cs:__imp_AcquireSRWLockShared
0x18007fdb6  mov     [rsp+678h+var_5D8], rdi
0x18007fdbe  lea     rdi, [rbx+18h]
0x18007fdc2  mov     [rsp+678h+var_5B0], rdi
0x18007fdca  mov     eax, [rdi]
0x18007fdcc  cmp     eax, 0FFFFFFFFh
0x18007fdcf  jz      short loc_18007FE2C
0x18007fdd1  cmp     [r15+38h], eax
0x18007fdd5  jnz     short loc_18007FE2C
0x18007fdd7  mov     rdx, rbx
0x18007fdda  mov     rcx, r12
0x18007fddd  call    ?EqualSidVectors@NgcKspServer@@YAHAEBV?$vector@EV?$allocator@E@std@@@std@@0@Z; NgcKspServer::EqualSidVectors(std::vector<uchar> const &,std::vector<uchar> const &)
0x18007fde2  test    eax, eax
0x18007fde4  jz      short loc_18007FE2C
0x18007fde6  mov     rdx, r13
0x18007fde9  mov     rcx, r12
0x18007fdec  call    ?EqualSidVectors@NgcKspServer@@YAHAEBV?$vector@EV?$allocator@E@std@@@std@@0@Z; NgcKspServer::EqualSidVectors(std::vector<uchar> const &,std::vector<uchar> const &)
0x18007fdf1  test    eax, eax
0x18007fdf3  jz      short loc_18007FE2C
0x18007fdf5  mov     eax, cs:dword_180122070
0x18007fdfb  cmp     eax, 4
0x18007fdfe  jbe     short loc_18007FE16
0x18007fe00  xor     r8d, r8d
0x18007fe03  lea     rdx, byte_180104B21
0x18007fe0a  lea     rcx, dword_180122070
0x18007fe11  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007fe16  mov     ebx, dword ptr [rsp+678h+var_634]
0x18007fe1a  lea     rcx, [rsp+678h+var_5D8]
0x18007fe22  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007fe27  jmp     loc_18008066A
0x18007fe2c  lea     rcx, [rsp+678h+var_5D8]
0x18007fe34  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007fe39  mov     dl, 1
0x18007fe3b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADPinResetV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2> `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl(void)'::`2'::impl
0x18007fe42  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007fe47  nop
0x18007fe48  call    IsCamIsCandidateUserPresent
0x18007fe4d  lea     r13, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007fe54  test    al, al
0x18007fe56  jz      loc_1800805F3
0x18007fe5c  mov     al, sil
0x18007fe5f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007fe67  test    al, al
0x18007fe69  jnz     loc_1800805F3
0x18007fe6f  mov     [rsp+678h+var_608], esi
0x18007fe73  mov     [rsp+678h+var_628], rsi
0x18007fe78  xor     edx, edx
0x18007fe7a  lea     rcx, [rsp+678h+var_628]
0x18007fe7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAAXPEAK@Z; wil::details::unique_storage<wil::details::resource_policy<ulong *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ulong *,ulong *,0,std::nullptr_t>>::reset(ulong *)
0x18007fe84  lea     rdx, [rsp+678h+var_628]
0x18007fe89  lea     rcx, [rsp+678h+var_608]
0x18007fe8e  call    cs:__imp_CamGetCandidateUserSessionIds
0x18007fe94  test    eax, eax
0x18007fe96  js      loc_1800805E8
0x18007fe9c  xorps   xmm0, xmm0
0x18007fe9f  movdqu  [rsp+678h+var_620], xmm0
0x18007fea5  mov     [rsp+678h+var_610], rsi
0x18007feaa  mov     eax, [rsp+678h+var_608]
0x18007feae  mov     r9, [rsp+678h+var_628]
0x18007feb3  lea     rcx, [r9+rax*4]
0x18007feb7  xor     r8d, r8d
0x18007feba  mov     [rsp+678h+phkResult], rcx
0x18007febf  lea     rdx, [rsp+678h+var_558]
0x18007fec7  lea     rcx, [rsp+678h+var_620]
0x18007fecc  call    ??$insert@PEAK$0A@@?$vector@KV?$allocator@K@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@1@PEAK1@Z; std::vector<ulong>::insert<ulong *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,ulong *,ulong *)
0x18007fed1  xor     edx, edx
0x18007fed3  lea     rcx, [rsp+678h+var_628]
0x18007fed8  call    ?reset@?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAAXPEAK@Z; wil::details::unique_storage<wil::details::resource_policy<ulong *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ulong *,ulong *,0,std::nullptr_t>>::reset(ulong *)
0x18007fedd  xor     edx, edx
0x18007fedf  lea     rcx, [rsp+678h+var_628]
0x18007fee4  call    ?reset@?$unique_storage@U?$resource_policy@PEAKP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAKPEAK$0A@$$T@details@wil@@@details@wil@@QEAAXPEAK@Z; wil::details::unique_storage<wil::details::resource_policy<ulong *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ulong *,ulong *,0,std::nullptr_t>>::reset(ulong *)
0x18007fee9  lea     rdx, [rsp+678h+var_628]
0x18007feee  lea     rcx, [rsp+678h+var_608]
0x18007fef3  call    cs:__imp_CamGetNonCandidateUserSessionIds
0x18007fef9  test    eax, eax
0x18007fefb  js      loc_1800805BF
0x18007ff01  xorps   xmm0, xmm0
0x18007ff04  movdqu  [rsp+678h+var_5F8], xmm0
0x18007ff0d  mov     [rsp+678h+var_5E8], rsi
0x18007ff15  mov     eax, [rsp+678h+var_608]
0x18007ff19  mov     r9, [rsp+678h+var_628]
0x18007ff1e  lea     rcx, [r9+rax*4]
0x18007ff22  xor     r8d, r8d
0x18007ff25  mov     [rsp+678h+phkResult], rcx
0x18007ff2a  lea     rdx, [rsp+678h+var_550]
0x18007ff32  lea     rcx, [rsp+678h+var_5F8]
0x18007ff3a  call    ??$insert@PEAK$0A@@?$vector@KV?$allocator@K@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@1@PEAK1@Z; std::vector<ulong>::insert<ulong *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,ulong *,ulong *)
0x18007ff3f  mov     [rsp+678h+var_5D0], esi
0x18007ff46  lea     rdx, [rsp+678h+var_5D0]
0x18007ff4e  mov     rcx, [r12]
0x18007ff52  call    cs:__imp_CamIsCandidateUser
0x18007ff58  test    eax, eax
0x18007ff5a  js      loc_18008058A
0x18007ff60  mov     r8d, [r15+3Ch]; dwProcessId
0x18007ff64  xor     edx, edx; bInheritHandle
0x18007ff66  mov     ecx, 1000h; dwDesiredAccess
0x18007ff6b  call    cs:__imp_OpenProcess
0x18007ff71  mov     rdi, rax
0x18007ff74  mov     [rsp+678h+var_5C8], rax
0x18007ff7c  dec     rax
0x18007ff7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007ff83  ja      loc_18008051C
0x18007ff89  mov     [rsp+678h+lpExeName], rsi
0x18007ff91  mov     [rsp+678h+dwSize], 104h
0x18007ff99  xor     edx, edx
0x18007ff9b  mov     r8d, 104h
0x18007ffa1  lea     rcx, [rsp+678h+var_5D8]
0x18007ffa9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18007ffae  or      r14d, 2
0x18007ffb2  mov     dword ptr [rsp+678h+hkey], r14d
0x18007ffb7  mov     rcx, [rsp+678h]; this
0x18007ffbf  cmp     [rsp+678h+var_5D8], rsi
0x18007ffc7  jz      loc_1800806A4
0x18007ffcd  mov     [rsp+678h+var_638], sil
0x18007ffd2  and     r14d, 0FFFFFFFDh
0x18007ffd6  mov     dword ptr [rsp+678h+hkey], r14d
0x18007ffdb  or      r14d, 1
0x18007ffdf  lea     rdx, [rsp+678h+var_5D8]
0x18007ffe7  lea     rcx, [rsp+678h+lpExeName]
0x18007ffef  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007fff4  lea     rcx, [rsp+678h+var_5D8]; void *
0x18007fffc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180080001  lea     r9, [rsp+678h+dwSize]; lpdwSize
0x180080006  mov     rbx, [rsp+678h+lpExeName]
0x18008000e  mov     r8, rbx; lpExeName
0x180080011  xor     edx, edx; dwFlags
0x180080013  mov     rcx, rdi; hProcess
0x180080016  call    cs:__imp_QueryFullProcessImageNameW
0x18008001c  test    eax, eax
0x18008001e  jz      loc_1800802C4
0x180080024  mov     r8d, 104h; cchBuffer
0x18008002a  mov     rdx, rbx; lpszLongPath
0x18008002d  mov     rcx, rbx; lpszShortPath
0x180080030  call    cs:__imp_GetLongPathNameW
0x180080036  mov     rdx, rbx
0x180080039  lea     rcx, [rsp+678h+String2]
0x180080041  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080046  nop
0x180080047  mov     dword ptr [rsp+678h+var_634+4], esi
0x18008004b  mov     r8d, 27h ; '''
0x180080051  lea     rdx, [rsp+678h+var_4B8]
0x180080059  lea     rcx, USER_OOBE_BROKER_CLS_ID
0x180080060  call    cs:__imp_SHStringFromGUIDW
0x180080066  mov     ebx, eax
0x180080068  test    eax, eax
0x18008006a  js      loc_180080133
0x180080070  lea     r9, [rsp+678h+var_4B8]
0x180080078  lea     r8, aClsidSLocalser; "CLSID\\%s\\LocalServer32"
0x18008007f  mov     edx, 100h; unsigned __int64
0x180080084  lea     rcx, [rsp+678h+SubKey]; unsigned __int16 *
0x18008008c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180080091  mov     ebx, eax
0x180080093  test    eax, eax
0x180080095  js      loc_180080133
0x18008009b  mov     [rsp+678h+hkey], rsi
0x1800800a0  lea     rax, [rsp+678h+hkey]
0x1800800a5  mov     [rsp+678h+phkResult], rax; phkResult
0x1800800aa  mov     r9d, 20019h; samDesired
0x1800800b0  xor     r8d, r8d; ulOptions
0x1800800b3  lea     rdx, [rsp+678h+SubKey]; lpSubKey
0x1800800bb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800800c2  call    cs:__imp_RegOpenKeyExW
0x1800800c8  mov     ebx, eax
0x1800800ca  test    eax, eax
0x1800800cc  jle     short loc_1800800D7
0x1800800ce  movzx   ebx, ax
0x1800800d1  or      ebx, 80070000h
0x1800800d7  test    ebx, ebx
0x1800800d9  js      short loc_180080133
0x1800800db  mov     dword ptr [rsp+678h+var_634+4], 208h
0x1800800e3  lea     rax, [rsp+678h+var_634+4]
0x1800800e8  mov     [rsp+678h+pcbData], rax; pcbData
0x1800800ed  lea     rax, [rsp+678h+Buffer]
0x1800800f5  mov     [rsp+678h+pvData], rax; pvData
0x1800800fa  mov     [rsp+678h+phkResult], rsi; pdwType
0x1800800ff  mov     r9d, 2; dwFlags
0x180080105  lea     r8, sourceString; lpValue
0x18008010c  xor     edx, edx; lpSubKey
0x18008010e  mov     rcx, [rsp+678h+hkey]; hkey
0x180080113  call    cs:__imp_RegGetValueW
0x180080119  mov     ebx, eax
0x18008011b  test    eax, eax
0x18008011d  jle     short loc_180080128
0x18008011f  movzx   ebx, ax
0x180080122  or      ebx, 80070000h
0x180080128  mov     rcx, [rsp+678h+hkey]; hKey
0x18008012d  call    cs:__imp_RegCloseKey
0x180080133  xorps   xmm0, xmm0
0x180080136  movups  xmmword ptr [rsp+678h+String1], xmm0
0x18008013e  movdqu  [rsp+678h+var_4F0], xmm6
0x180080147  mov     word ptr [rsp+678h+String1], si
0x18008014f  test    ebx, ebx
0x180080151  js      short loc_18008016A
0x180080153  lea     rdx, [rsp+678h+Buffer]
0x18008015b  lea     rcx, [rsp+678h+String1]
0x180080163  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180080168  jmp     short loc_1800801D3
0x18008016a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008016f  mov     edx, 104h; uSize
0x180080174  lea     rcx, [rsp+678h+Buffer]; lpBuffer
0x18008017c  call    cs:__imp_GetSystemDirectoryW
0x180080182  mov     dword ptr [rsp+678h+var_634+4], eax
0x180080186  test    eax, eax
0x180080188  jz      loc_1800804F1
0x18008018e  mov     r8d, 104h; cchBuffer
0x180080194  lea     rdx, [rsp+678h+Buffer]; lpszLongPath
0x18008019c  lea     rcx, [rsp+678h+Buffer]; lpszShortPath
0x1800801a4  call    cs:__imp_GetLongPathNameW
0x1800801aa  lea     rdx, [rsp+678h+Buffer]
0x1800801b2  lea     rcx, [rsp+678h+String1]
0x1800801ba  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800801bf  lea     rdx, aOobeUseroobebr; "\\oobe\\UserOOBEBroker.exe"
0x1800801c6  lea     rcx, [rsp+678h+String1]; Src
0x1800801ce  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800801d3  cmp     dword ptr [rsp+678h+var_634+4], esi
0x1800801d7  jz      loc_1800802A8
0x1800801dd  mov     [rsp+678h+hkey], rsi
0x1800801e2  lea     rdx, Locale; "en-US"
0x1800801e9  xor     ecx, ecx; Category
0x1800801eb  call    cs:__imp__create_locale
0x1800801f1  mov     r9, rax
0x1800801f4  mov     [rsp+678h+hkey], rax
0x1800801f9  lea     rax, [rsp+678h+hkey]
0x1800801fe  mov     [rsp+678h+var_5C0], rax
0x180080206  mov     rcx, [rsp+678h]
0x18008020e  mov     [rsp+678h+var_578], rcx
0x180080216  mov     [rsp+678h+var_570], r13
0x18008021e  mov     [rsp+678h+var_568], rsi
0x180080226  mov     eax, 412h
0x18008022b  mov     [rsp+678h+var_560], ax
0x180080233  lea     r8, [rsp+678h+var_5C0]
0x18008023b  lea     rdx, [rsp+678h+var_578]
0x180080243  lea     rcx, [rsp+678h+var_538]
0x18008024b  call    wil__scope_exit_log__lambda_7b469132a53953dba2ab1d2085a9748a___
0x180080250  lea     rdx, [rsp+678h+String2]
0x180080258  cmp     [rsp+678h+var_4C8], 7
0x180080261  cmova   rdx, [rsp+678h+String2]; String2
0x18008026a  lea     rcx, [rsp+678h+String1]
0x180080272  cmp     qword ptr [rsp+678h+var_4F0+8], 7
0x18008027b  cmova   rcx, [rsp+678h+String1]; String1
  ... truncated ...
```
