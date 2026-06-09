# Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::InitializeStoreCacheForUserWorker(EffectiveUserContext const &)

- ea: `0x180010020`
- end: `0x180010575`
- name: `?InitializeStoreCacheForUserWorker@CloudStoreBroker@Broker@Cloud@Storage@Internal@Windows@@SAJAEBVEffectiveUserContext@@@Z`
- size: `1365`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000feb0`

## callees

- `0x18000dfe4`
- `0x180010020`
- `0x18001057c`
- `0x1800105f0`
- `0x180010688`
- `0x180024020`
- `0x18002570c`
- `0x1800307d4`
- `0x18003e670`
- `0x18003f6c4`
- `0x180043e44`
- `0x180043fd8`
- `0x1800440c4`
- `0x180044840`
- `0x18009cad8`
- `0x1800c8458`
- `0x1800e6ef8`
- `0x1800fc644`
- `0x1800fe694`
- `0x1800ff298`
- `0x1801201a0`
- `0x180177af0`
- `0x180177f84`
- `0x180178054`
- `0x180178078`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001008a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001008a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800103ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800103ba`
- `ntdll!RtlPublishWnfStateData` at `0x1800104c1`
- `ntdll!RtlPublishWnfStateData` at `0x1800104f2`
- `ntdll!RtlPublishWnfStateData` at `0x1800104c1`
- `ntdll!RtlPublishWnfStateData` at `0x1800104f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010284`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010284`
- `USERENV!GetProfileType` at `0x18001018d`
- `USERENV!GetProfileType` at `0x1800101e4`
- `USERENV!GetProfileType` at `0x18001018d`
- `USERENV!GetProfileType` at `0x1800101e4`

## string_xrefs

- `0x1800100a1`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18001012c`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1800101aa`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1800101f6`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18001029b`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180010320`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1800103cf`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180010441`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18001050c`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1800100fc`: `HasStoreCacheInitialized`
- `0x18001041f`: `HasStoreCacheInitialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::InitializeStoreCacheForUserWorker(
        void ***a1)
{
  HRESULT v2; // eax
  HKEY v3; // rcx
  unsigned int v4; // r9d
  unsigned int v5; // ebx
  void *v6; // rdx
  int BOOLWithREGSAM; // eax
  unsigned int v9; // ebx
  unsigned int LastErrorMsg; // ebx
  const char *v11; // r9
  unsigned int LastError; // ebx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  LPVOID v15; // rbx
  __int64 (__fastcall *v16)(LPVOID, const unsigned __int16 *, const WCHAR *, _QWORD); // r14
  DWORD v17; // esi
  const unsigned __int16 *SidString; // rax
  int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // r9d
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  __int64 v29; // rdx
  int ppv; // [rsp+20h] [rbp-2B8h]
  LPVOID *ppva; // [rsp+20h] [rbp-2B8h]
  int ppvb; // [rsp+20h] [rbp-2B8h]
  unsigned int ppvc; // [rsp+20h] [rbp-2B8h]
  DWORD dwFlags; // [rsp+50h] [rbp-288h] BYREF
  wil::details *v35; // [rsp+58h] [rbp-280h] BYREF
  wil::details *v36; // [rsp+60h] [rbp-278h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-270h] BYREF
  LPVOID v38; // [rsp+70h] [rbp-268h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-260h] BYREF
  IID rclsid; // [rsp+80h] [rbp-258h] BYREF
  WCHAR pszPathOut[264]; // [rsp+90h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  EffectiveUserContext::Impersonate(a1, &hObject);
  ____0AEAY0BF___CBG__V___unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA_AEAY0BF___CBG_Z(&v35);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v35,
    &v36,
    0,
    0xFFFFFFFFLL);
  v2 = PathCchCombine(pszPathOut, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore", L"StoreInit");
  v5 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    if ( v36 )
      wil::details::ReleaseMutex(v36, v6);
    if ( v35 )
      wil::details::CloseHandle(v35, v6);
    if ( hObject != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(hObject, v6);
    return v5;
  }
  dwFlags = 0;
  BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(v3, pszPathOut, L"HasStoreCacheInitialized", v4, (int *)&dwFlags);
  v9 = BOOLWithREGSAM;
  if ( !BOOLWithREGSAM || BOOLWithREGSAM == -2147024894 )
  {
    if ( dwFlags )
    {
LABEL_36:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return 0;
    }
    dwFlags = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::GetImpl'::`2'::impl) )
    {
      if ( !GetProfileType(&dwFlags) )
      {
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x1B7,
                         (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
                         "**!!##!!**NoLogTipForceWarn",
                         (const char *)ppva);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
        return LastErrorMsg;
      }
    }
    else if ( !GetProfileType(&dwFlags) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1BC,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
                    v11);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return LastError;
    }
    rclsid.Data1 = -1618866095;
    *(_DWORD *)&rclsid.Data2 = 1209435077;
    *(_DWORD *)rclsid.Data4 = 1600075963;
    *(_DWORD *)&rclsid.Data4[4] = -614615389;
    v38 = 0;
    v13 = CoCreateInstance(&rclsid, 0, 1u, &GUID_f9b86217_3f05_42ef_9db6_59bb82b6df3c, &v38);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v13,
        ppvb);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v38);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v14;
    }
    v15 = v38;
    v16 = *(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const WCHAR *, _QWORD))(*(_QWORD *)v38 + 24LL);
    v17 = dwFlags;
    SidString = EffectiveUserContext::GetSidString((EffectiveUserContext *)a1);
    v19 = v16(v15, SidString, &LocaleName, v17);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v19,
        ppvb);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v38);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v20;
    }
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v21 = RegCreateKeyExW(HKEY_CURRENT_USER, pszPathOut, 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
    if ( v21 )
    {
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1C8,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
              (const char *)v21,
              ppvc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v38);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v24;
    }
    v25 = SHRegSetBOOL(phkResult, v22, L"HasStoreCacheInitialized", v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v25,
        ppvc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v38);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v26;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus>::GetImpl'::`2'::impl) )
    {
      if ( !IsActiveSessionCountLimited() )
        goto LABEL_35;
      v27 = RtlPublishWnfStateData(WNF_WCDS_SYNC_WLAN, 0, 0, 0);
      v28 = retaddr;
      if ( v27 >= 0 )
        goto LABEL_35;
      v29 = 468;
    }
    else
    {
      v27 = RtlPublishWnfStateData(WNF_WCDS_SYNC_WLAN, 0, 0, 0);
      v28 = retaddr;
      if ( v27 >= 0 )
      {
LABEL_35:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v38);
        goto LABEL_36;
      }
      v29 = 474;
    }
    wil::details::in1diag3::_Log_NtStatus(
      v28,
      (void *)v29,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
      (const char *)(unsigned int)v27,
      0);
    goto LABEL_35;
  }
  if ( BOOLWithREGSAM < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
      (const char *)(unsigned int)BOOLWithREGSAM,
      (int)ppva);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v35);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
  return v9;
}

```

## disassembly

```asm
0x180010020  push    rbx
0x180010022  push    rsi
0x180010023  push    rdi
0x180010024  push    r14
0x180010026  sub     rsp, 2B8h
0x18001002d  mov     rax, cs:__security_cookie
0x180010034  xor     rax, rsp
0x180010037  mov     [rsp+2D8h+var_38], rax
0x18001003f  mov     rdi, rcx
0x180010042  lea     rdx, [rsp+2D8h+hObject]
0x180010047  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x18001004c  nop
0x18001004d  lea     rcx, [rsp+2D8h+var_280]
0x180010052  call    ??$?0AEAY0BF@$$CBG$$V@?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@AEAY0BF@$$CBG@Z
0x180010057  nop
0x180010058  or      r9d, 0FFFFFFFFh
0x18001005c  xor     r8d, r8d
0x18001005f  lea     rdx, [rsp+2D8h+var_278]
0x180010064  lea     rcx, [rsp+2D8h+var_280]
0x180010069  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001006e  nop
0x18001006f  lea     r9, pszMore; "StoreInit"
0x180010076  lea     r8, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001007d  mov     edx, 104h; cchPathOut
0x180010082  lea     rcx, [rsp+2D8h+pszPathOut]; pszPathOut
0x18001008a  call    cs:__imp_PathCchCombine
0x180010090  mov     ebx, eax
0x180010092  test    eax, eax
0x180010094  jns     short loc_1800100EA
0x180010096  mov     rcx, [rsp+2D8h]; this
0x18001009e  mov     r9d, eax; char *
0x1800100a1  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800100a8  mov     edx, 1A8h; void *
0x1800100ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100b2  nop
0x1800100b3  mov     rcx, [rsp+2D8h+var_278]; this
0x1800100b8  test    rcx, rcx
0x1800100bb  jz      short loc_1800100C3
0x1800100bd  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800100c2  nop
0x1800100c3  mov     rcx, [rsp+2D8h+var_280]; this
0x1800100c8  test    rcx, rcx
0x1800100cb  jz      short loc_1800100D3
0x1800100cd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800100d2  nop
0x1800100d3  mov     rcx, [rsp+2D8h+hObject]; hObject
0x1800100d8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800100dc  jz      short loc_1800100E3
0x1800100de  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800100e3  mov     eax, ebx
0x1800100e5  jmp     loc_180010557
0x1800100ea  mov     [rsp+2D8h+dwFlags], 0
0x1800100f2  lea     rax, [rsp+2D8h+dwFlags]
0x1800100f7  mov     [rsp+2D8h+ppv], rax; char *
0x1800100fc  lea     r8, aHasstorecachei; "HasStoreCacheInitialized"
0x180010103  lea     rdx, [rsp+2D8h+pszPathOut]; unsigned __int16 *
0x18001010b  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180010110  mov     ebx, eax
0x180010112  test    eax, eax
0x180010114  jz      short loc_180010165
0x180010116  cmp     eax, 80070002h
0x18001011b  jz      short loc_180010165
0x18001011d  test    eax, eax
0x18001011f  jns     short loc_18001013E
0x180010121  mov     rcx, [rsp+2D8h]; this
0x180010129  mov     r9d, eax; char *
0x18001012c  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180010133  mov     edx, 1ADh; void *
0x180010138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001013d  nop
0x18001013e  lea     rcx, [rsp+2D8h+var_278]
0x180010143  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010148  nop
0x180010149  lea     rcx, [rsp+2D8h+var_280]
0x18001014e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010153  nop
0x180010154  lea     rcx, [rsp+2D8h+hObject]
0x180010159  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001015e  mov     eax, ebx
0x180010160  jmp     loc_180010557
0x180010165  cmp     [rsp+2D8h+dwFlags], 0
0x18001016a  jnz     loc_18001052F
0x180010170  mov     [rsp+2D8h+dwFlags], 0
0x180010178  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError> `wil::Feature<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::GetImpl(void)'::`2'::impl
0x18001017f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IgnoreUserProfileUnavailableError>::__private_IsEnabled(void)
0x180010184  lea     rcx, [rsp+2D8h+dwFlags]; dwFlags
0x180010189  test    al, al
0x18001018b  jz      short loc_1800101E4
0x18001018d  call    cs:__imp_GetProfileType
0x180010193  test    eax, eax
0x180010195  jnz     loc_180010230
0x18001019b  mov     rcx, [rsp+2D8h]; this
0x1800101a3  lea     r9, aNologtipforcew; "**!!##!!**NoLogTipForceWarn"
0x1800101aa  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800101b1  mov     edx, 1B7h; void *
0x1800101b6  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800101bb  mov     ebx, eax
0x1800101bd  lea     rcx, [rsp+2D8h+var_278]
0x1800101c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800101c7  nop
0x1800101c8  lea     rcx, [rsp+2D8h+var_280]
0x1800101cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800101d2  nop
0x1800101d3  lea     rcx, [rsp+2D8h+hObject]
0x1800101d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800101dd  mov     eax, ebx
0x1800101df  jmp     loc_180010557
0x1800101e4  call    cs:__imp_GetProfileType
0x1800101ea  test    eax, eax
0x1800101ec  jnz     short loc_180010230
0x1800101ee  mov     rcx, [rsp+2D8h]; this
0x1800101f6  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800101fd  mov     edx, 1BCh; void *
0x180010202  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010207  mov     ebx, eax
0x180010209  lea     rcx, [rsp+2D8h+var_278]
0x18001020e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010213  nop
0x180010214  lea     rcx, [rsp+2D8h+var_280]
0x180010219  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001021e  nop
0x18001021f  lea     rcx, [rsp+2D8h+hObject]
0x180010224  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180010229  mov     eax, ebx
0x18001022b  jmp     loc_180010557
0x180010230  mov     [rsp+2D8h+rclsid.Data1], 9F821051h
0x18001023b  mov     dword ptr [rsp+2D8h+rclsid.Data2], 481683C5h
0x180010246  mov     dword ptr [rsp+2D8h+rclsid.Data4], 5F5F38BBh
0x180010251  mov     dword ptr [rsp+2D8h+rclsid.Data4+4], 0DB5DB6A3h
0x18001025c  mov     [rsp+2D8h+var_268], 0
0x180010265  lea     rax, [rsp+2D8h+var_268]
0x18001026a  mov     [rsp+2D8h+ppv], rax; int
0x18001026f  lea     r9, _GUID_f9b86217_3f05_42ef_9db6_59bb82b6df3c; riid
0x180010276  xor     edx, edx; pUnkOuter
0x180010278  lea     r8d, [rdx+1]; dwClsContext
0x18001027c  lea     rcx, [rsp+2D8h+rclsid]; rclsid
0x180010284  call    cs:__imp_CoCreateInstance
0x18001028a  mov     ebx, eax
0x18001028c  test    eax, eax
0x18001028e  jns     short loc_1800102DF
0x180010290  mov     rcx, [rsp+2D8h]; this
0x180010298  mov     r9d, eax; char *
0x18001029b  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800102a2  mov     edx, 1C3h; void *
0x1800102a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102ac  nop
0x1800102ad  lea     rcx, [rsp+2D8h+var_268]
0x1800102b2  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800102b7  nop
0x1800102b8  lea     rcx, [rsp+2D8h+var_278]
0x1800102bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800102c2  nop
0x1800102c3  lea     rcx, [rsp+2D8h+var_280]
0x1800102c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800102cd  nop
0x1800102ce  lea     rcx, [rsp+2D8h+hObject]
0x1800102d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800102d8  mov     eax, ebx
0x1800102da  jmp     loc_180010557
0x1800102df  mov     rbx, [rsp+2D8h+var_268]
0x1800102e4  mov     rax, [rbx]
0x1800102e7  mov     r14, [rax+18h]
0x1800102eb  mov     esi, [rsp+2D8h+dwFlags]
0x1800102ef  mov     rcx, rdi; this
0x1800102f2  call    ?GetSidString@EffectiveUserContext@@QEBAPEBGXZ; EffectiveUserContext::GetSidString(void)
0x1800102f7  mov     r9d, esi
0x1800102fa  lea     r8, LocaleName
0x180010301  mov     rdx, rax
0x180010304  mov     rcx, rbx
0x180010307  mov     rax, r14
0x18001030a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001030f  mov     ebx, eax
0x180010311  test    eax, eax
0x180010313  jns     short loc_180010364
0x180010315  mov     rcx, [rsp+2D8h]; this
0x18001031d  mov     r9d, eax; char *
0x180010320  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180010327  mov     edx, 1C4h; void *
0x18001032c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010331  nop
0x180010332  lea     rcx, [rsp+2D8h+var_268]
0x180010337  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18001033c  nop
0x18001033d  lea     rcx, [rsp+2D8h+var_278]
0x180010342  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010347  nop
0x180010348  lea     rcx, [rsp+2D8h+var_280]
0x18001034d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010352  nop
0x180010353  lea     rcx, [rsp+2D8h+hObject]
0x180010358  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001035d  mov     eax, ebx
0x18001035f  jmp     loc_180010557
0x180010364  mov     [rsp+2D8h+var_260], 0
0x18001036d  xor     edx, edx
0x18001036f  lea     rcx, [rsp+2D8h+var_260]
0x180010374  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010379  mov     [rsp+2D8h+lpdwDisposition], 0; lpdwDisposition
0x180010382  lea     rax, [rsp+2D8h+var_260]
0x180010387  mov     [rsp+2D8h+phkResult], rax; phkResult
0x18001038c  mov     [rsp+2D8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010395  mov     [rsp+2D8h+samDesired], 0F003Fh; samDesired
0x18001039d  mov     dword ptr [rsp+2D8h+ppv], 1; int
0x1800103a5  xor     r9d, r9d; lpClass
0x1800103a8  xor     r8d, r8d; Reserved
0x1800103ab  lea     rdx, [rsp+2D8h+pszPathOut]; lpSubKey
0x1800103b3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800103ba  call    cs:__imp_RegCreateKeyExW
0x1800103c0  test    eax, eax
0x1800103c2  jz      short loc_18001041F
0x1800103c4  mov     rcx, [rsp+2D8h]; this
0x1800103cc  mov     r9d, eax; char *
0x1800103cf  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800103d6  mov     edx, 1C8h; void *
0x1800103db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800103e0  mov     ebx, eax
0x1800103e2  lea     rcx, [rsp+2D8h+var_260]
0x1800103e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800103ec  nop
0x1800103ed  lea     rcx, [rsp+2D8h+var_268]
0x1800103f2  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800103f7  nop
0x1800103f8  lea     rcx, [rsp+2D8h+var_278]
0x1800103fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010402  nop
0x180010403  lea     rcx, [rsp+2D8h+var_280]
0x180010408  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001040d  nop
0x18001040e  lea     rcx, [rsp+2D8h+hObject]
0x180010413  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180010418  mov     eax, ebx
0x18001041a  jmp     loc_180010557
0x18001041f  lea     r8, aHasstorecachei; "HasStoreCacheInitialized"
0x180010426  mov     rcx, [rsp+2D8h+var_260]; HKEY
0x18001042b  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x180010430  mov     ebx, eax
0x180010432  test    eax, eax
0x180010434  jns     short loc_180010490
0x180010436  mov     rcx, [rsp+2D8h]; this
0x18001043e  mov     r9d, eax; char *
0x180010441  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180010448  mov     edx, 1C9h; void *
0x18001044d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010452  nop
0x180010453  lea     rcx, [rsp+2D8h+var_260]
0x180010458  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001045d  nop
0x18001045e  lea     rcx, [rsp+2D8h+var_268]
0x180010463  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180010468  nop
0x180010469  lea     rcx, [rsp+2D8h+var_278]
0x18001046e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010473  nop
0x180010474  lea     rcx, [rsp+2D8h+var_280]
0x180010479  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001047e  nop
0x18001047f  lea     rcx, [rsp+2D8h+hObject]
0x180010484  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180010489  mov     eax, ebx
0x18001048b  jmp     loc_180010557
0x180010490  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus> `wil::Feature<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus>::GetImpl(void)'::`2'::impl
0x180010497  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressWlanWnfSignalOnFirstLoadOnMultiSessionSkus>::__private_IsEnabled(void)
0x18001049c  test    al, al
0x18001049e  jz      short loc_1800104DA
0x1800104a0  call    ?IsActiveSessionCountLimited@@YA_NXZ; IsActiveSessionCountLimited(void)
0x1800104a5  test    al, al
0x1800104a7  jz      short loc_180010519
0x1800104a9  mov     [rsp+2D8h+ppv], 0
0x1800104b2  xor     r9d, r9d
0x1800104b5  xor     r8d, r8d
0x1800104b8  xor     edx, edx
0x1800104ba  mov     rcx, cs:WNF_WCDS_SYNC_WLAN
0x1800104c1  call    cs:__imp_RtlPublishWnfStateData
0x1800104c7  mov     rcx, [rsp+2D8h]
0x1800104cf  test    eax, eax
0x1800104d1  jns     short loc_180010519
0x1800104d3  mov     edx, 1D4h
0x1800104d8  jmp     short loc_180010509
0x1800104da  mov     [rsp+2D8h+ppv], 0; int
0x1800104e3  xor     r9d, r9d
0x1800104e6  xor     r8d, r8d
0x1800104e9  xor     edx, edx
0x1800104eb  mov     rcx, cs:WNF_WCDS_SYNC_WLAN
0x1800104f2  call    cs:__imp_RtlPublishWnfStateData
0x1800104f8  mov     rcx, [rsp+2D8h]; this
0x180010500  test    eax, eax
0x180010502  jns     short loc_180010519
0x180010504  mov     edx, 1DAh; void *
0x180010509  mov     r9d, eax; char *
0x18001050c  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180010513  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180010518  nop
0x180010519  lea     rcx, [rsp+2D8h+var_260]
0x18001051e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010523  nop
0x180010524  lea     rcx, [rsp+2D8h+var_268]
0x180010529  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18001052e  nop
0x18001052f  lea     rcx, [rsp+2D8h+var_278]
0x180010534  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
  ... truncated ...
```
