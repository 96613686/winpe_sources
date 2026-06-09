# Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::InitializeForUserWorker(EffectiveUserContext const &,Windows::Internal::Storage::Cloud::Broker::InitializeOption,uchar *)

- ea: `0x180108080`
- end: `0x1801087dc`
- name: `?InitializeForUserWorker@CloudStoreBroker@Broker@Cloud@Storage@Internal@Windows@@SAJAEBVEffectiveUserContext@@W4InitializeOption@23456@PEAE@Z`
- size: `1884`
- prototype: `__int64 __fastcall(void ***, int, _BYTE *)`
- caller_count: `1`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180107ff0`

## callees

- `0x18000dfe4`
- `0x18001057c`
- `0x1800105f0`
- `0x180010688`
- `0x180024020`
- `0x1800307d4`
- `0x18003e670`
- `0x18003f6c4`
- `0x180043e44`
- `0x180043fd8`
- `0x18009cad8`
- `0x1800c8458`
- `0x1800e6ef8`
- `0x1800e93e0`
- `0x1800fc644`
- `0x1800fe694`
- `0x1800ff298`
- `0x180108080`
- `0x1801201a0`
- `0x180176e2c`
- `0x180177af0`
- `0x180177f84`
- `0x180178054`
- `0x180178078`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180108100`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180108100`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180108410`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180108410`
- `ntdll!RtlPublishWnfStateData` at `0x18010870e`
- `ntdll!RtlPublishWnfStateData` at `0x18010873b`
- `ntdll!RtlPublishWnfStateData` at `0x18010870e`
- `ntdll!RtlPublishWnfStateData` at `0x18010873b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010835d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010835d`
- `USERENV!GetProfileType` at `0x18010827b`
- `USERENV!GetProfileType` at `0x1801082e0`
- `USERENV!GetProfileType` at `0x18010827b`
- `USERENV!GetProfileType` at `0x1801082e0`

## string_xrefs

- `0x180108117`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108194`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18010820c`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108298`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1801082f2`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108374`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108425`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1801084dd`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18010855c`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18010861f`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108661`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108755`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180108164`: `HasStoreCacheInitialized`
- `0x18010853a`: `HasStoreCacheInitialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::InitializeForUserWorker(
        void ***a1,
        int a2,
        _BYTE *a3)
{
  HRESULT v6; // eax
  HKEY v7; // rcx
  unsigned int v8; // r9d
  unsigned int v9; // ebx
  int BOOLWithREGSAM; // eax
  HKEY v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // esi
  DWORD v17; // edi
  unsigned int LastErrorMsg; // ebx
  const char *v19; // r9
  unsigned int LastError; // ebx
  HRESULT v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // ebx
  LPVOID v25; // rbx
  DWORD v26; // r13d
  const unsigned __int16 *SidString; // rax
  int v28; // eax
  const unsigned __int16 *v29; // rdx
  int v30; // r9d
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  bool v34; // si
  __int64 (__fastcall *v35)(_QWORD, _QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v36)(_QWORD, const unsigned __int16 *, __int64, _BYTE *); // r15
  const unsigned __int16 *v37; // rax
  __int64 v38; // r8
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  int v41; // r9d
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  wil::details::in1diag3 *v45; // rcx
  __int64 v46; // rdx
  int ppv; // [rsp+20h] [rbp-2B8h]
  int ppva; // [rsp+20h] [rbp-2B8h]
  LPVOID *ppvb; // [rsp+20h] [rbp-2B8h]
  int ppvc; // [rsp+20h] [rbp-2B8h]
  unsigned int ppvd; // [rsp+20h] [rbp-2B8h]
  DWORD dwFlags; // [rsp+50h] [rbp-288h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-280h] BYREF
  _BYTE v54[8]; // [rsp+60h] [rbp-278h] BYREF
  _BYTE v55[8]; // [rsp+68h] [rbp-270h] BYREF
  __int64 v56; // [rsp+70h] [rbp-268h] BYREF
  LPVOID v57; // [rsp+78h] [rbp-260h] BYREF
  __int64 v58; // [rsp+80h] [rbp-258h] BYREF
  __int64 (__fastcall *v59)(LPVOID, const unsigned __int16 *, const WCHAR *, _QWORD); // [rsp+88h] [rbp-250h] BYREF
  WCHAR pszPathOut[264]; // [rsp+90h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  EffectiveUserContext::Impersonate(a1, &v56);
  ____0AEAY0BF___CBG__V___unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA_AEAY0BF___CBG_Z(v54);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    v54,
    v55,
    0,
    0xFFFFFFFFLL);
  v6 = PathCchCombine(pszPathOut, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore", L"StoreInit");
  v9 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
    return v9;
  }
  LODWORD(phkResult) = 0;
  dwFlags = 0;
  BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(v7, pszPathOut, L"HasStoreCacheInitialized", v8, (int *)&dwFlags);
  v14 = BOOLWithREGSAM;
  if ( BOOLWithREGSAM && BOOLWithREGSAM != -2147024894 )
  {
    if ( BOOLWithREGSAM < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)BOOLWithREGSAM,
        ppva);
LABEL_7:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
    return v14;
  }
  *a3 = 1;
  v15 = SHRegGetBOOLWithREGSAM(v12, pszPathOut, L"HasPolicyMirrorRun", v13, (int *)&phkResult);
  v14 = v15;
  if ( v15 && v15 != -2147024894 )
  {
    if ( v15 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v15,
        (int)ppvb);
    goto LABEL_7;
  }
  v58 = 0;
  v16 = (int)phkResult;
  v17 = dwFlags;
  if ( (_DWORD)phkResult && dwFlags )
    goto LABEL_46;
  dwFlags = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::GetImpl'::`2'::impl) )
  {
    if ( !GetProfileType(&dwFlags) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x153,
                       (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
                       "**!!##!!**NoLogTipForceWarn",
                       (const char *)ppvb);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
      return LastErrorMsg;
    }
  }
  else if ( !GetProfileType(&dwFlags) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x157,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
                  v19);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
    return LastError;
  }
  v57 = 0;
  v21 = CoCreateInstance(
          &`Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::InitializeForUserWorker'::`33'::CLSID_CloudCacheInitializer,
          0,
          1u,
          &GUID_f9b86217_3f05_42ef_9db6_59bb82b6df3c,
          &v57);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
      (const char *)(unsigned int)v21,
      ppvc);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
    return v22;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v23 = RegCreateKeyExW(HKEY_CURRENT_USER, pszPathOut, 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
  if ( v23 )
  {
    v24 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x164,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
            (const char *)v23,
            ppvd);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
    return v24;
  }
  if ( !v17 )
  {
    v25 = v57;
    v59 = *(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const WCHAR *, _QWORD))(*(_QWORD *)v57 + 24LL);
    v26 = dwFlags;
    SidString = EffectiveUserContext::GetSidString((EffectiveUserContext *)a1);
    v28 = v59(v25, SidString, &LocaleName, v26);
    v31 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v28,
        ppvd);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
      return v31;
    }
    v32 = SHRegSetBOOL(phkResult, v29, L"HasStoreCacheInitialized", v30);
    v33 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v32,
        ppvd);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
      return v33;
    }
  }
  if ( !v16 && a2 != 2 )
  {
    v34 = a2 == 0;
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreProfileNotify,wil::err_exception_policy>::query<Windows::Internal::Storage::Cloud::ICloudStorePolicyInit>(
      &v57,
      &v59);
    v35 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v59;
    v36 = *(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64, _BYTE *))(*(_QWORD *)v59 + 24LL);
    v37 = EffectiveUserContext::GetSidString((EffectiveUserContext *)a1);
    LOBYTE(v38) = v34;
    v39 = v36(v35, v37, v38, a3);
    if ( v39 >= 0 )
    {
      if ( *a3 )
      {
        v42 = SHRegSetBOOL(phkResult, v40, L"HasPolicyMirrorRun", v41);
        v43 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
            (const char *)(unsigned int)v42,
            ppvd);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v59);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
          return v43;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v39,
        ppvd);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v59);
  }
  if ( !v17 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus>::GetImpl'::`2'::impl) )
    {
      if ( !IsActiveSessionCountLimited() )
        goto LABEL_45;
      v44 = RtlPublishWnfStateData(WNF_WCDS_SYNC_WLAN, 0, 0, 0);
      v45 = retaddr;
      if ( v44 >= 0 )
        goto LABEL_45;
      v46 = 393;
      goto LABEL_44;
    }
    v44 = RtlPublishWnfStateData(WNF_WCDS_SYNC_WLAN, 0, 0, 0);
    v45 = retaddr;
    if ( v44 < 0 )
    {
      v46 = 399;
LABEL_44:
      wil::details::in1diag3::_Log_NtStatus(
        v45,
        (void *)v46,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v44,
        0);
    }
  }
LABEL_45:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
LABEL_46:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v58);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v55);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v54);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v56);
  return 0;
}

```

## disassembly

```asm
0x180108080  mov     [rsp+arg_8], rbx
0x180108085  mov     [rsp+arg_18], rsi
0x18010808a  push    rdi
0x18010808b  push    r12
0x18010808d  push    r13
0x18010808f  push    r14
0x180108091  push    r15
0x180108093  sub     rsp, 2B0h
0x18010809a  mov     rax, cs:__security_cookie
0x1801080a1  xor     rax, rsp
0x1801080a4  mov     [rsp+2D8h+var_38], rax
0x1801080ac  mov     r12, r8
0x1801080af  mov     r15d, edx
0x1801080b2  mov     r14, rcx
0x1801080b5  xor     r13d, r13d
0x1801080b8  lea     rdx, [rsp+2D8h+var_268]
0x1801080bd  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x1801080c2  nop
0x1801080c3  lea     rcx, [rsp+2D8h+var_278]
0x1801080c8  call    ??$?0AEAY0BF@$$CBG$$V@?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@AEAY0BF@$$CBG@Z
0x1801080cd  nop
0x1801080ce  or      r9d, 0FFFFFFFFh
0x1801080d2  xor     r8d, r8d
0x1801080d5  lea     rdx, [rsp+2D8h+var_270]
0x1801080da  lea     rcx, [rsp+2D8h+var_278]
0x1801080df  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1801080e4  nop
0x1801080e5  lea     r9, pszMore; "StoreInit"
0x1801080ec  lea     r8, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801080f3  mov     edx, 104h; cchPathOut
0x1801080f8  lea     rcx, [rsp+2D8h+pszPathOut]; pszPathOut
0x180108100  call    cs:__imp_PathCchCombine
0x180108106  mov     ebx, eax
0x180108108  test    eax, eax
0x18010810a  jns     short loc_180108150
0x18010810c  mov     rcx, [rsp+2D8h]; this
0x180108114  mov     r9d, eax; char *
0x180108117  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18010811e  mov     edx, 139h; void *
0x180108123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108128  nop
0x180108129  lea     rcx, [rsp+2D8h+var_270]
0x18010812e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108133  nop
0x180108134  lea     rcx, [rsp+2D8h+var_278]
0x180108139  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010813e  nop
0x18010813f  lea     rcx, [rsp+2D8h+var_268]
0x180108144  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180108149  mov     eax, ebx
0x18010814b  jmp     loc_1801087AE
0x180108150  mov     dword ptr [rsp+2D8h+var_280], r13d
0x180108155  mov     [rsp+2D8h+dwFlags], r13d
0x18010815a  lea     rax, [rsp+2D8h+dwFlags]
0x18010815f  mov     [rsp+2D8h+ppv], rax; int
0x180108164  lea     r8, aHasstorecachei; "HasStoreCacheInitialized"
0x18010816b  lea     rdx, [rsp+2D8h+pszPathOut]; unsigned __int16 *
0x180108173  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180108178  mov     ebx, eax
0x18010817a  test    eax, eax
0x18010817c  jz      short loc_1801081CD
0x18010817e  cmp     eax, 80070002h
0x180108183  jz      short loc_1801081CD
0x180108185  test    eax, eax
0x180108187  jns     short loc_1801081A6
0x180108189  mov     rcx, [rsp+2D8h]; this
0x180108191  mov     r9d, eax; char *
0x180108194  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18010819b  mov     edx, 141h; void *
0x1801081a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801081a5  nop
0x1801081a6  lea     rcx, [rsp+2D8h+var_270]
0x1801081ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801081b0  nop
0x1801081b1  lea     rcx, [rsp+2D8h+var_278]
0x1801081b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801081bb  nop
0x1801081bc  lea     rcx, [rsp+2D8h+var_268]
0x1801081c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1801081c6  mov     eax, ebx
0x1801081c8  jmp     loc_1801087AE
0x1801081cd  mov     byte ptr [r12], 1
0x1801081d2  lea     rax, [rsp+2D8h+var_280]
0x1801081d7  mov     [rsp+2D8h+ppv], rax; char *
0x1801081dc  lea     r8, aHaspolicymirro; "HasPolicyMirrorRun"
0x1801081e3  lea     rdx, [rsp+2D8h+pszPathOut]; unsigned __int16 *
0x1801081eb  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1801081f0  mov     ebx, eax
0x1801081f2  test    eax, eax
0x1801081f4  jz      short loc_180108245
0x1801081f6  cmp     eax, 80070002h
0x1801081fb  jz      short loc_180108245
0x1801081fd  test    eax, eax
0x1801081ff  jns     short loc_18010821E
0x180108201  mov     rcx, [rsp+2D8h]; this
0x180108209  mov     r9d, eax; char *
0x18010820c  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180108213  mov     edx, 147h; void *
0x180108218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010821d  nop
0x18010821e  lea     rcx, [rsp+2D8h+var_270]
0x180108223  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108228  nop
0x180108229  lea     rcx, [rsp+2D8h+var_278]
0x18010822e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108233  nop
0x180108234  lea     rcx, [rsp+2D8h+var_268]
0x180108239  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18010823e  mov     eax, ebx
0x180108240  jmp     loc_1801087AE
0x180108245  mov     [rsp+2D8h+var_258], r13
0x18010824d  mov     esi, dword ptr [rsp+2D8h+var_280]
0x180108251  mov     edi, [rsp+2D8h+dwFlags]
0x180108255  test    esi, esi
0x180108257  jz      short loc_180108261
0x180108259  test    edi, edi
0x18010825b  jnz     loc_180108778
0x180108261  mov     [rsp+2D8h+dwFlags], r13d
0x180108266  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError> `wil::Feature<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::GetImpl(void)'::`2'::impl
0x18010826d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::__private_IsEnabled(void)
0x180108272  lea     rcx, [rsp+2D8h+dwFlags]; dwFlags
0x180108277  test    al, al
0x180108279  jz      short loc_1801082E0
0x18010827b  call    cs:__imp_GetProfileType
0x180108281  test    eax, eax
0x180108283  jnz     loc_18010833A
0x180108289  mov     rcx, [rsp+2D8h]; this
0x180108291  lea     r9, aNologtipforcew; "**!!##!!**NoLogTipForceWarn"
0x180108298  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18010829f  mov     edx, 153h; void *
0x1801082a4  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1801082a9  mov     ebx, eax
0x1801082ab  lea     rcx, [rsp+2D8h+var_258]
0x1801082b3  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1801082b8  nop
0x1801082b9  lea     rcx, [rsp+2D8h+var_270]
0x1801082be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801082c3  nop
0x1801082c4  lea     rcx, [rsp+2D8h+var_278]
0x1801082c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801082ce  nop
0x1801082cf  lea     rcx, [rsp+2D8h+var_268]
0x1801082d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1801082d9  mov     eax, ebx
0x1801082db  jmp     loc_1801087AE
0x1801082e0  call    cs:__imp_GetProfileType
0x1801082e6  test    eax, eax
0x1801082e8  jnz     short loc_18010833A
0x1801082ea  mov     rcx, [rsp+2D8h]; this
0x1801082f2  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1801082f9  mov     edx, 157h; void *
0x1801082fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180108303  mov     ebx, eax
0x180108305  lea     rcx, [rsp+2D8h+var_258]
0x18010830d  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180108312  nop
0x180108313  lea     rcx, [rsp+2D8h+var_270]
0x180108318  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010831d  nop
0x18010831e  lea     rcx, [rsp+2D8h+var_278]
0x180108323  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108328  nop
0x180108329  lea     rcx, [rsp+2D8h+var_268]
0x18010832e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180108333  mov     eax, ebx
0x180108335  jmp     loc_1801087AE
0x18010833a  mov     [rsp+2D8h+var_260], r13
0x18010833f  lea     rax, [rsp+2D8h+var_260]
0x180108344  mov     [rsp+2D8h+ppv], rax; int
0x180108349  lea     r9, _GUID_f9b86217_3f05_42ef_9db6_59bb82b6df3c; riid
0x180108350  xor     edx, edx; pUnkOuter
0x180108352  lea     r8d, [rdx+1]; dwClsContext
0x180108356  lea     rcx, ?CLSID_CloudCacheInitializer@?CB@??InitializeForUserWorker@CloudStoreBroker@Broker@Cloud@Storage@Internal@Windows@@SAJAEBVEffectiveUserContext@@W4InitializeOption@34567@PEAE@Z@4U_GUID@@B; rclsid
0x18010835d  call    cs:__imp_CoCreateInstance
0x180108363  mov     ebx, eax
0x180108365  test    eax, eax
0x180108367  jns     short loc_1801083C6
0x180108369  mov     rcx, [rsp+2D8h]; this
0x180108371  mov     r9d, eax; char *
0x180108374  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18010837b  mov     edx, 160h; void *
0x180108380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108385  nop
0x180108386  lea     rcx, [rsp+2D8h+var_260]
0x18010838b  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180108390  nop
0x180108391  lea     rcx, [rsp+2D8h+var_258]
0x180108399  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18010839e  nop
0x18010839f  lea     rcx, [rsp+2D8h+var_270]
0x1801083a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801083a9  nop
0x1801083aa  lea     rcx, [rsp+2D8h+var_278]
0x1801083af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801083b4  nop
0x1801083b5  lea     rcx, [rsp+2D8h+var_268]
0x1801083ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1801083bf  mov     eax, ebx
0x1801083c1  jmp     loc_1801087AE
0x1801083c6  mov     [rsp+2D8h+var_280], r13
0x1801083cb  xor     edx, edx
0x1801083cd  lea     rcx, [rsp+2D8h+var_280]
0x1801083d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801083d7  mov     [rsp+2D8h+lpdwDisposition], r13; lpdwDisposition
0x1801083dc  lea     rax, [rsp+2D8h+var_280]
0x1801083e1  mov     [rsp+2D8h+phkResult], rax; phkResult
0x1801083e6  mov     [rsp+2D8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801083eb  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x1801083f3  mov     dword ptr [rsp+2D8h+ppv], 1; int
0x1801083fb  xor     r9d, r9d; lpClass
0x1801083fe  xor     r8d, r8d; Reserved
0x180108401  lea     rdx, [rsp+2D8h+pszPathOut]; lpSubKey
0x180108409  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180108410  call    cs:__imp_RegCreateKeyExW
0x180108416  test    eax, eax
0x180108418  jz      short loc_180108483
0x18010841a  mov     rcx, [rsp+2D8h]; this
0x180108422  mov     r9d, eax; char *
0x180108425  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18010842c  mov     edx, 164h; void *
0x180108431  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180108436  mov     ebx, eax
0x180108438  lea     rcx, [rsp+2D8h+var_280]
0x18010843d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180108442  nop
0x180108443  lea     rcx, [rsp+2D8h+var_260]
0x180108448  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18010844d  nop
0x18010844e  lea     rcx, [rsp+2D8h+var_258]
0x180108456  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18010845b  nop
0x18010845c  lea     rcx, [rsp+2D8h+var_270]
0x180108461  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108466  nop
0x180108467  lea     rcx, [rsp+2D8h+var_278]
0x18010846c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108471  nop
0x180108472  lea     rcx, [rsp+2D8h+var_268]
0x180108477  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18010847c  mov     eax, ebx
0x18010847e  jmp     loc_1801087AE
0x180108483  test    edi, edi
0x180108485  jnz     loc_1801085B9
0x18010848b  mov     rbx, [rsp+2D8h+var_260]
0x180108490  mov     rax, [rbx]
0x180108493  mov     rax, [rax+18h]
0x180108497  mov     [rsp+2D8h+var_250], rax
0x18010849f  mov     r13d, [rsp+2D8h+dwFlags]
0x1801084a4  mov     rcx, r14; this
0x1801084a7  call    ?GetSidString@EffectiveUserContext@@QEBAPEBGXZ; EffectiveUserContext::GetSidString(void)
0x1801084ac  mov     r9d, r13d
0x1801084af  lea     r8, LocaleName
0x1801084b6  mov     rdx, rax
0x1801084b9  mov     rcx, rbx
0x1801084bc  mov     rax, [rsp+2D8h+var_250]
0x1801084c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801084c9  mov     ebx, eax
0x1801084cb  xor     r13d, r13d
0x1801084ce  test    eax, eax
0x1801084d0  jns     short loc_18010853A
0x1801084d2  mov     rcx, [rsp+2D8h]; this
0x1801084da  mov     r9d, eax; char *
0x1801084dd  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1801084e4  mov     edx, 168h; void *
0x1801084e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801084ee  nop
0x1801084ef  lea     rcx, [rsp+2D8h+var_280]
0x1801084f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801084f9  nop
0x1801084fa  lea     rcx, [rsp+2D8h+var_260]
0x1801084ff  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180108504  nop
0x180108505  lea     rcx, [rsp+2D8h+var_258]
0x18010850d  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180108512  nop
0x180108513  lea     rcx, [rsp+2D8h+var_270]
0x180108518  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18010851d  nop
0x18010851e  lea     rcx, [rsp+2D8h+var_278]
0x180108523  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180108528  nop
0x180108529  lea     rcx, [rsp+2D8h+var_268]
0x18010852e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180108533  mov     eax, ebx
0x180108535  jmp     loc_1801087AE
0x18010853a  lea     r8, aHasstorecachei; "HasStoreCacheInitialized"
0x180108541  mov     rcx, [rsp+2D8h+var_280]; HKEY
0x180108546  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18010854b  mov     ebx, eax
0x18010854d  test    eax, eax
0x18010854f  jns     short loc_1801085B9
0x180108551  mov     rcx, [rsp+2D8h]; this
0x180108559  mov     r9d, eax; char *
0x18010855c  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180108563  mov     edx, 16Ch; void *
0x180108568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010856d  nop
0x18010856e  lea     rcx, [rsp+2D8h+var_280]
0x180108573  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180108578  nop
  ... truncated ...
```
