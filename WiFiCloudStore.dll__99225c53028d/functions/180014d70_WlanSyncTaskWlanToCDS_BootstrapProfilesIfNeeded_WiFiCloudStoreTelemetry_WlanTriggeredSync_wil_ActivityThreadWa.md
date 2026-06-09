# WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &,bool)

- ea: `0x180014d70`
- end: `0x18001561d`
- name: `?BootstrapProfilesIfNeeded@WlanSyncTaskWlanToCDS@@SAXAEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@_N@Z`
- size: `2221`
- prototype: `void __fastcall(struct WiFiCloudStoreTelemetry::WlanTriggeredSync *this, struct wil::ActivityThreadWatcher *, bool)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001314c`

## callees

- `0x180006420`
- `0x180006b88`
- `0x18000766c`
- `0x1800077bc`
- `0x1800079f0`
- `0x180007f90`
- `0x18000ac9c`
- `0x1800115a0`
- `0x180011690`
- `0x180014d70`
- `0x180015624`
- `0x180015aa8`
- `0x180015b6c`
- `0x180015b9c`
- `0x180015fa8`
- `0x180016378`
- `0x18001c92c`
- `0x18001de24`
- `0x18001f3ec`
- `0x18001f950`
- `0x180020980`
- `0x18002a030`
- `0x18002a43c`
- `0x18002e2d0`
- `0x18002e50c`
- `0x180030f60`
- `0x180031ce4`
- `0x180032b38`
- `0x180033378`
- `0x1800336c8`
- `0x180035318`
- `0x180035518`
- `0x180035554`
- `0x180035984`
- `0x180036474`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001538c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001538c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015590`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015590`
- `wlanapi!WlanFreeMemory` at `0x180014ea8`
- `wlanapi!WlanFreeMemory` at `0x1800152ab`
- `wlanapi!WlanFreeMemory` at `0x1800152c7`
- `wlanapi!WlanFreeMemory` at `0x1800155da`
- `wlanapi!WlanFreeMemory` at `0x180014ea8`
- `wlanapi!WlanFreeMemory` at `0x1800152ab`
- `wlanapi!WlanFreeMemory` at `0x1800152c7`
- `wlanapi!WlanFreeMemory` at `0x1800155da`
- `wlanapi!WlanCloseHandle` at `0x1800155f1`
- `wlanapi!WlanCloseHandle` at `0x1800155f1`
- `wlanapi!WlanEnumInterfaces` at `0x180014e59`
- `wlanapi!WlanEnumInterfaces` at `0x180014e59`
- `wlanapi!WlanOpenHandle` at `0x180014df9`
- `wlanapi!WlanOpenHandle` at `0x180014df9`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180015064`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180015115`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180015064`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180015115`
- `wlanapi!WlanWcmGetProfileList` at `0x180014f2d`
- `wlanapi!WlanWcmGetProfileList` at `0x180014f2d`

## string_xrefs

- `0x180015581`: `WlanSvcTaskBootstrapped`
- `0x180014e0e`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180014e6e`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180014f42`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180015079`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800150ad`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800153a1`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800153fd`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180015460`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800155a5`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded(
        struct WiFiCloudStoreTelemetry::WlanTriggeredSync *this,
        struct wil::ActivityThreadWatcher *a2,
        char a3)
{
  char v3; // r12
  struct wil::ActivityThreadWatcher *v4; // r13
  WiFiCloudStoreTelemetry::WlanTriggeredSync *v5; // r15
  const char *v6; // r9
  DWORD v7; // eax
  DWORD v8; // eax
  void *v9; // rdx
  __int64 v10; // rdx
  __int64 i; // rcx
  const struct _GUID *v12; // r14
  unsigned int ProfileList; // eax
  __int64 v14; // rdx
  unsigned int j; // edi
  __int64 v16; // rbx
  __int64 v17; // r8
  bool IsProfileEligibleForCDSSync; // al
  const struct _GUID *v19; // rbx
  unsigned int ProfileMetadataWithProfileGuid; // eax
  int v21; // ebx
  unsigned int v22; // ebx
  int v23; // r12d
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  const char *v28; // r9
  PVOID v29; // rcx
  PVOID v30; // rcx
  HRESULT v31; // eax
  LPVOID v32; // rdi
  __int64 (__fastcall *v33)(LPVOID, __int64, __int64 *); // rbx
  int v34; // eax
  int v35; // r14d
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, struct INetworkPrivate **, int *); // rbx
  int v38; // eax
  struct INetworkPrivate *v39; // rcx
  __int64 v40; // rcx
  LPVOID v41; // rcx
  void *v42; // rcx
  unsigned int v43; // eax
  PVOID v44; // rcx
  int v45; // eax
  const struct _GUID *v46; // rdx
  wil::details::in1diag3 *v47; // rcx
  __int64 v48; // rdx
  int ppv; // [rsp+20h] [rbp-288h]
  unsigned int ppva; // [rsp+20h] [rbp-288h]
  int ppvb; // [rsp+20h] [rbp-288h]
  unsigned int ppvc; // [rsp+20h] [rbp-288h]
  int v53; // [rsp+50h] [rbp-258h] BYREF
  unsigned int v54; // [rsp+54h] [rbp-254h] BYREF
  unsigned int ProfileGeneration; // [rsp+58h] [rbp-250h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-24Ch] BYREF
  struct INetworkPrivate *v57; // [rsp+60h] [rbp-248h] BYREF
  int v58; // [rsp+68h] [rbp-240h] BYREF
  int v59; // [rsp+6Ch] [rbp-23Ch] BYREF
  unsigned int *v60; // [rsp+70h] [rbp-238h] BYREF
  unsigned int *v61; // [rsp+78h] [rbp-230h] BYREF
  __int64 v62; // [rsp+80h] [rbp-228h] BYREF
  LPVOID v63; // [rsp+88h] [rbp-220h] BYREF
  PVOID v64; // [rsp+90h] [rbp-218h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-210h] BYREF
  PVOID pMemory; // [rsp+A0h] [rbp-208h] BYREF
  PVOID v67; // [rsp+A8h] [rbp-200h] BYREF
  void *Block; // [rsp+B0h] [rbp-1F8h] BYREF
  void *phClientHandle; // [rsp+B8h] [rbp-1F0h] BYREF
  char v70; // [rsp+C1h] [rbp-1E7h]
  DWORD pdwNegotiatedVersion; // [rsp+C4h] [rbp-1E4h] BYREF
  const struct _GUID *v72; // [rsp+C8h] [rbp-1E0h]
  struct wil::ActivityThreadWatcher *v73; // [rsp+D0h] [rbp-1D8h]
  _BYTE v74[8]; // [rsp+E0h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v75; // [rsp+E8h] [rbp-1C0h]
  std::_Ref_count_base *v76; // [rsp+100h] [rbp-1A8h]
  _BYTE v77[80]; // [rsp+110h] [rbp-198h] BYREF
  _BYTE v78[64]; // [rsp+160h] [rbp-148h] BYREF
  char v79; // [rsp+1A0h] [rbp-108h] BYREF
  GUID v80; // [rsp+1E0h] [rbp-C8h] BYREF
  char v81; // [rsp+1F0h] [rbp-B8h]
  _BYTE v82[44]; // [rsp+200h] [rbp-A8h] BYREF
  unsigned int v83; // [rsp+22Ch] [rbp-7Ch]
  _BYTE v84[56]; // [rsp+230h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    v3 = a3;
    v4 = a2;
    v5 = this;
    hKey = (HKEY)this;
    v73 = a2;
    if ( Windows::Internal::WiFiCloudStore::IsProfileBootstrapNeededForUser(this, a2) )
    {
      WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginBootstrap(v5);
      pdwNegotiatedVersion = 0;
      phClientHandle = (void *)-1LL;
      v7 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
      if ( v7 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)v7,
          ppva);
      v64 = 0;
      *(_QWORD *)&v80.Data1 = &v64;
      *(_QWORD *)v80.Data4 = 0;
      v81 = 1;
      v8 = WlanEnumInterfaces(phClientHandle, 0, (PWLAN_INTERFACE_INFO_LIST *)v80.Data4);
      if ( v8 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)v8,
          ppva);
      if ( v81 )
      {
        v9 = **(void ***)&v80.Data1;
        **(_QWORD **)&v80.Data1 = *(_QWORD *)v80.Data4;
        if ( v9 )
          WlanFreeMemory(v9);
      }
      v70 = 1;
      wil::cloud_store::cloud_store(v74);
      wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v10);
      v53 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)v64; i = (unsigned int)++v53 )
      {
        v12 = (const struct _GUID *)((char *)v64 + 532 * i + 8);
        v72 = v12;
        v61 = 0;
        *(_QWORD *)&v80.Data1 = &v61;
        *(_QWORD *)v80.Data4 = 0;
        v81 = 1;
        ProfileList = WlanWcmGetProfileList(v12, 0, (struct WCM_WLAN_PROFILE_INFO_LIST **)v80.Data4);
        if ( ProfileList )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x1C7,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
            (const char *)ProfileList,
            ppva);
        if ( v81 )
        {
          v14 = **(_QWORD **)&v80.Data1;
          **(_QWORD **)&v80.Data1 = *(_QWORD *)v80.Data4;
          if ( v14 )
            WlanWcmProfileListFreeMemoryHelper::operator()();
        }
        for ( j = 0; ; ++j )
        {
          *(_DWORD *)Data = j;
          if ( j >= *v61 )
            break;
          v16 = 154LL * j;
          v60 = &v61[v16 + 6];
          ProfileGeneration = WlanSyncTaskCommon::GetProfileGeneration(&v61[v16 + 150]);
          wil::ActivityThreadWatcher::SetMessage(v4, "Profile name: %ws, Generation: %d", v17, ProfileGeneration);
          IsProfileEligibleForCDSSync = WlanSyncTaskCommon::IsProfileEligibleForCDSSync(
                                          v12,
                                          (const struct WCM_WLAN_PROFILE_INFO *)&v61[v16 + 2]);
          try
          {
            if ( IsProfileEligibleForCDSSync )
            {
              v19 = (const struct _GUID *)&v61[v16 + 2];
              if ( WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileGuid(
                     (const struct _TOKEN_USER *)Block,
                     v12,
                     v19,
                     v3) )
              {
                v67 = 0;
                v54 = 0;
                *(_QWORD *)&v80.Data1 = &v67;
                *(_QWORD *)v80.Data4 = 0;
                v81 = 1;
                ProfileMetadataWithProfileGuid = WlanGetProfileMetadataWithProfileGuid(v12, v19, 0, L"LastModified");
                if ( ProfileMetadataWithProfileGuid )
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x1DC,
                    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
                    (const char *)ProfileMetadataWithProfileGuid,
                    (unsigned int)&v54);
                wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&v80);
                if ( v54 != 8 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1E1,
                    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
                    (const char *)0x8000FFFFLL,
                    (int)&v54);
                v58 = 1;
                pMemory = 0;
                *(_QWORD *)&v80.Data1 = &pMemory;
                *(_QWORD *)v80.Data4 = 0;
                v81 = 1;
                v21 = WlanGetProfileMetadataWithProfileGuid(v12, v19, 0, L"Has Connected");
                wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>((__int64)&v80);
                if ( !v21 && v54 == 4 && *(_DWORD *)pMemory == 1 )
                  v58 = 0;
                v22 = ProfileGeneration;
                v23 = (int)v67;
                std::wstring::wstring(&v80, v60);
                v24 = Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(v84, &v80);
                Windows::Internal::WiFiCloudStore::SyncNeededProfile::SyncNeededProfile(
                  (unsigned int)v82,
                  v24,
                  v23,
                  2,
                  v22);
                std::wstring::~wstring((__int64)v84);
                std::wstring::~wstring((__int64)&v80);
                v25 = lambda_7f3ecf42dade528cea96be5b9f4d3ed9_::_lambda_7f3ecf42dade528cea96be5b9f4d3ed9_(
                        (unsigned int)&v79,
                        (unsigned int)&v60,
                        (unsigned int)&v64,
                        (unsigned int)&v53,
                        (__int64)v82,
                        (__int64)v12,
                        (__int64)&Block,
                        (__int64)v5,
                        (__int64)&ProfileGeneration);
                wil::scope_exit__lambda_7f3ecf42dade528cea96be5b9f4d3ed9___(v77, v25);
                v26 = lambda_612a61c8f178d30cb019cab59c668fc2_::_lambda_612a61c8f178d30cb019cab59c668fc2_(
                        (unsigned int)v84,
                        (_DWORD)v5,
                        (_DWORD)v4,
                        (unsigned int)&phClientHandle,
                        (__int64)&v60,
                        (__int64)v12,
                        (__int64)v82,
                        (__int64)&v58);
                v27 = std::function_void___cdecl_unsigned_short_const____::function_void___cdecl_unsigned_short_const______lambda_612a61c8f178d30cb019cab59c668fc2__0_(
                        v78,
                        v26);
                WlanSyncTaskWlanToCDS::PushCloudChangePerStoreForGeneration(v83, v27);
                v77[64] = 0;
                wil::details::lambda_call__lambda_7f3ecf42dade528cea96be5b9f4d3ed9___::_lambda_call__lambda_7f3ecf42dade528cea96be5b9f4d3ed9___(v77);
                std::wstring::~wstring((__int64)v82);
                v29 = pMemory;
                pMemory = 0;
                if ( v29 )
                  WlanFreeMemory(v29);
                v30 = v67;
                v67 = 0;
                if ( v30 )
                  WlanFreeMemory(v30);
              }
              else
              {
                v54 = 5;
                WiFiCloudStoreTelemetry::SidDoesNotAllowAction<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,enum WiFiSyncAction>(
                  (__int64 *)&v60,
                  (int *)&ProfileGeneration,
                  (int *)&v54);
              }
            }
            else
            {
              WiFiCloudStoreTelemetry::ProfileNotEligibleForSync<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
                &v60,
                &ProfileGeneration);
            }
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x24A,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              v28);
            v12 = v72;
            j = *(_DWORD *)Data;
            v5 = (WiFiCloudStoreTelemetry::WlanTriggeredSync *)hKey;
            v4 = v73;
          }
          v3 = a3;
        }
        wil::details::StoredCallContextInfo::ClearMessage(v4);
        *((_QWORD *)v4 + 2) = 0;
        if ( v61 )
          WlanWcmProfileListFreeMemoryHelper::operator()();
      }
      v63 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
      v31 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v63);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x251,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)(unsigned int)v31,
          ppvb);
      v62 = 0;
      v32 = v63;
      v33 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v63 + 32LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
      v34 = v33(v32, 3, &v62);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)(unsigned int)v34,
          ppvb);
      v35 = 0;
      v53 = 0;
      v59 = 0;
      v57 = 0;
      while ( 1 )
      {
        v36 = v62;
        v37 = *(__int64 (__fastcall **)(__int64, __int64, struct INetworkPrivate **, int *))(*(_QWORD *)v62 + 24LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
        v38 = v37(v36, 1, &v57, &v59);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x25B,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
            (const char *)(unsigned int)v38,
            ppvb);
        if ( v38 )
          break;
        try
        {
          v35 += WlanSyncTaskCommon::UploadSignaturesToCloudForNetwork((struct wil::cloud_store *)v74, v57);
          v53 = v35;
        }
        catch ( ... )
        {
          v80 = 0;
          v45 = (*(__int64 (__fastcall **)(struct INetworkPrivate *, GUID *))(*(_QWORD *)v57 + 48LL))(v57, &v80);
          v47 = retaddr;
          if ( v45 < 0 )
          {
            v48 = 612;
            goto LABEL_71;
          }
          v45 = Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser(&v80, v46);
          v47 = retaddr;
          if ( v45 < 0 )
          {
            v48 = 614;
LABEL_71:
            wil::details::in1diag3::_Log_Hr(
              v47,
              (void *)v48,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              (const char *)(unsigned int)v45,
              ppv);
          }
          v35 = v53;
          v5 = (WiFiCloudStoreTelemetry::WlanTriggeredSync *)hKey;
          continue;
        }
      }
      WiFiCloudStoreTelemetry::WlanTriggeredSync::NlmSignaturesBootstrapped<unsigned int &>((__int64)v5, &v53);
      v39 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(struct INetworkPrivate *))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v40 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = Block;
      Block = 0;
      if ( v42 )
        operator delete(v42);
      if ( v76 )
        std::_Ref_count_base::_Decref(v76);
      if ( v75 )
        std::_Ref_count_base::_Decref(v75);
      Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(&hKey);
      *(_DWORD *)Data = 1;
      v43 = RegSetValueExW(hKey, L"WlanSvcTaskBootstrapped", 0, 4u, Data, 4u);
      if ( v43 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x141,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
          (const char *)v43,
          ppvc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v44 = v64;
      v64 = 0;
      if ( v44 )
        WlanFreeMemory(v44);
      if ( phClientHandle != (void *)-1LL )
        WlanCloseHandle(phClientHandle, 0);
    }
    else
    {
      WiFiCloudStoreTelemetry::SkippingBootstrap();
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x180014d70  mov     [rsp+arg_10], r8b
0x180014d75  push    rbx
0x180014d76  push    rsi
0x180014d77  push    rdi
0x180014d78  push    r12
0x180014d7a  push    r13
0x180014d7c  push    r14
0x180014d7e  push    r15
0x180014d80  sub     rsp, 270h
0x180014d87  mov     rax, cs:__security_cookie
0x180014d8e  xor     rax, rsp
0x180014d91  mov     [rsp+2A8h+var_40], rax
0x180014d99  mov     r12b, r8b
0x180014d9c  mov     r13, rdx
0x180014d9f  mov     r15, rcx
0x180014da2  mov     [rsp+2A8h+hKey], rcx
0x180014daa  mov     [rsp+2A8h+var_1D8], rdx
0x180014db2  xor     esi, esi
0x180014db4  call    ?IsProfileBootstrapNeededForUser@WiFiCloudStore@Internal@Windows@@YA_NQEAX@Z; Windows::Internal::WiFiCloudStore::IsProfileBootstrapNeededForUser(void * const)
0x180014db9  test    al, al
0x180014dbb  jnz     short loc_180014DC8
0x180014dbd  call    ?SkippingBootstrap@WiFiCloudStoreTelemetry@@SAXXZ; WiFiCloudStoreTelemetry::SkippingBootstrap(void)
0x180014dc2  nop
0x180014dc3  jmp     loc_1800155FA
0x180014dc8  mov     rcx, r15; this
0x180014dcb  call    ?BeginBootstrap@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXXZ; WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginBootstrap(void)
0x180014dd0  nop
0x180014dd1  mov     [rsp+2A8h+pdwNegotiatedVersion], esi
0x180014dd8  mov     [rsp+2A8h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x180014de4  lea     r9, [rsp+2A8h+phClientHandle]; phClientHandle
0x180014dec  lea     r8, [rsp+2A8h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180014df4  xor     edx, edx; pReserved
0x180014df6  lea     ecx, [rdx+2]; dwClientVersion
0x180014df9  call    cs:__imp_WlanOpenHandle
0x180014dff  mov     rcx, [rsp+2A8h]; this
0x180014e07  test    eax, eax
0x180014e09  jz      short loc_180014E1F
0x180014e0b  mov     r9d, eax; char *
0x180014e0e  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014e15  mov     edx, 1B2h; void *
0x180014e1a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180014e1f  mov     [rsp+2A8h+var_218], rsi
0x180014e27  lea     rax, [rsp+2A8h+var_218]
0x180014e2f  mov     [rsp+2A8h+var_C8], rax
0x180014e37  mov     [rsp+2A8h+ppInterfaceList], rsi
0x180014e3f  mov     [rsp+2A8h+var_B8], 1
0x180014e47  lea     r8, [rsp+2A8h+ppInterfaceList]; ppInterfaceList
0x180014e4f  xor     edx, edx; pReserved
0x180014e51  mov     rcx, [rsp+2A8h+phClientHandle]; hClientHandle
0x180014e59  call    cs:__imp_WlanEnumInterfaces
0x180014e5f  mov     rcx, [rsp+2A8h]; this
0x180014e67  test    eax, eax
0x180014e69  jz      short loc_180014E80
0x180014e6b  mov     r9d, eax; char *
0x180014e6e  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014e75  mov     edx, 1B5h; void *
0x180014e7a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180014e80  cmp     [rsp+2A8h+var_B8], sil
0x180014e88  jz      short loc_180014EAE
0x180014e8a  mov     rcx, [rsp+2A8h+var_C8]
0x180014e92  mov     rdx, [rcx]
0x180014e95  mov     rax, [rsp+2A8h+ppInterfaceList]
0x180014e9d  mov     [rcx], rax
0x180014ea0  test    rdx, rdx
0x180014ea3  jz      short loc_180014EAE
0x180014ea5  mov     rcx, rdx; pMemory
0x180014ea8  call    cs:__imp_WlanFreeMemory
0x180014eae  mov     [rsp+2A8h+var_1E7], 1
0x180014eb6  lea     rcx, [rsp+2A8h+var_1C8]
0x180014ebe  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180014ec3  nop
0x180014ec4  lea     rcx, [rsp+2A8h+Block]
0x180014ecc  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180014ed1  nop
0x180014ed2  mov     [rsp+2A8h+var_258], esi
0x180014ed6  mov     ecx, esi
0x180014ed8  mov     rax, [rsp+2A8h+var_218]
0x180014ee0  cmp     ecx, [rax]
0x180014ee2  jnb     loc_180015356
0x180014ee8  imul    r14, rcx, 214h
0x180014eef  add     rax, 8
0x180014ef3  add     r14, rax
0x180014ef6  mov     [rsp+2A8h+var_1E0], r14
0x180014efe  mov     [rsp+2A8h+var_230], rsi
0x180014f03  lea     rax, [rsp+2A8h+var_230]
0x180014f08  mov     [rsp+2A8h+var_C8], rax
0x180014f10  mov     [rsp+2A8h+ppInterfaceList], rsi
0x180014f18  mov     [rsp+2A8h+var_B8], 1
0x180014f20  lea     r8, [rsp+2A8h+ppInterfaceList]
0x180014f28  xor     edx, edx
0x180014f2a  mov     rcx, r14
0x180014f2d  call    cs:__imp_?WlanWcmGetProfileList@@YAKPEBU_GUID@@PEAXPEAPEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z; WlanWcmGetProfileList(_GUID const *,void *,WCM_WLAN_PROFILE_INFO_LIST * *)
0x180014f33  mov     rcx, [rsp+2A8h]; this
0x180014f3b  test    eax, eax
0x180014f3d  jz      short loc_180014F54
0x180014f3f  mov     r9d, eax; char *
0x180014f42  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014f49  mov     edx, 1C7h; void *
0x180014f4e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180014f54  cmp     [rsp+2A8h+var_B8], sil
0x180014f5c  jz      short loc_180014F7E
0x180014f5e  mov     rcx, [rsp+2A8h+var_C8]
0x180014f66  mov     rdx, [rcx]
0x180014f69  mov     rax, [rsp+2A8h+ppInterfaceList]
0x180014f71  mov     [rcx], rax
0x180014f74  test    rdx, rdx
0x180014f77  jz      short loc_180014F7E
0x180014f79  call    ??RWlanWcmProfileListFreeMemoryHelper@@QEAAXPEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z; WlanWcmProfileListFreeMemoryHelper::operator()(WCM_WLAN_PROFILE_INFO_LIST *)
0x180014f7e  mov     edi, esi
0x180014f80  mov     dword ptr [rsp+2A8h+Data], edi
0x180014f84  mov     rax, [rsp+2A8h+var_230]
0x180014f89  cmp     edi, [rax]
0x180014f8b  jnb     loc_18001532C
0x180014f91  mov     ecx, edi
0x180014f93  imul    rbx, rcx, 268h
0x180014f9a  lea     r8, [rax+18h]
0x180014f9e  add     r8, rbx
0x180014fa1  mov     [rsp+2A8h+var_238], r8
0x180014fa6  lea     rcx, [rax+258h]
0x180014fad  add     rcx, rbx
0x180014fb0  call    ?GetProfileGeneration@WlanSyncTaskCommon@@SA?AW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBUDOT11_AUTH_CIPHER_PAIR@@@Z; WlanSyncTaskCommon::GetProfileGeneration(DOT11_AUTH_CIPHER_PAIR const &)
0x180014fb5  mov     [rsp+2A8h+var_250], eax
0x180014fb9  mov     r9d, eax
0x180014fbc  lea     rdx, aProfileNameWsG_0; "Profile name: %ws, Generation: %d"
0x180014fc3  mov     rcx, r13; this
0x180014fc6  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x180014fcb  mov     rdx, [rsp+2A8h+var_230]
0x180014fd0  add     rdx, 8
0x180014fd4  add     rdx, rbx; struct WCM_WLAN_PROFILE_INFO *
0x180014fd7  mov     rcx, r14; struct _GUID *
0x180014fda  call    ?IsProfileEligibleForCDSSync@WlanSyncTaskCommon@@SA_NAEBU_GUID@@AEBUWCM_WLAN_PROFILE_INFO@@@Z; WlanSyncTaskCommon::IsProfileEligibleForCDSSync(_GUID const &,WCM_WLAN_PROFILE_INFO const &)
0x180014fdf  test    al, al
0x180014fe1  jz      loc_1800152ED
0x180014fe7  mov     rax, [rsp+2A8h+var_230]
0x180014fec  add     rax, 8
0x180014ff0  add     rbx, rax
0x180014ff3  mov     r9b, r12b; bool
0x180014ff6  mov     r8, rbx; struct _GUID *
0x180014ff9  mov     rdx, r14; struct _GUID *
0x180014ffc  mov     rcx, [rsp+2A8h+Block]; struct _TOKEN_USER *
0x180015004  call    ?DoesSidAllowUpdateWithProfileGuid@WlanSyncTaskCommon@@SA_NAEBU_TOKEN_USER@@AEBU_GUID@@1_N@Z; WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileGuid(_TOKEN_USER const &,_GUID const &,_GUID const &,bool)
0x180015009  test    al, al
0x18001500b  jz      loc_1800152CF
0x180015011  mov     [rsp+2A8h+var_200], rsi
0x180015019  mov     [rsp+2A8h+var_254], esi
0x18001501d  lea     rax, [rsp+2A8h+var_200]
0x180015025  mov     [rsp+2A8h+var_C8], rax
0x18001502d  mov     [rsp+2A8h+ppInterfaceList], rsi
0x180015035  mov     [rsp+2A8h+var_B8], 1
0x18001503d  lea     rax, [rsp+2A8h+ppInterfaceList]
0x180015045  mov     qword ptr [rsp+2A8h+cbData], rax
0x18001504a  lea     rax, [rsp+2A8h+var_254]
0x18001504f  mov     [rsp+2A8h+ppv], rax; int
0x180015054  lea     r9, aLastmodified; "LastModified"
0x18001505b  xor     r8d, r8d
0x18001505e  mov     rdx, rbx
0x180015061  mov     rcx, r14
0x180015064  call    cs:__imp_WlanGetProfileMetadataWithProfileGuid
0x18001506a  mov     rcx, [rsp+2A8h]; this
0x180015072  test    eax, eax
0x180015074  jz      short loc_18001508B
0x180015076  mov     r9d, eax; char *
0x180015079  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180015080  mov     edx, 1DCh; void *
0x180015085  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001508b  lea     rcx, [rsp+2A8h+var_C8]
0x180015093  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x180015098  cmp     [rsp+2A8h+var_254], 8
0x18001509d  jz      short loc_1800150BE
0x18001509f  mov     rcx, [rsp+2A8h]; this
0x1800150a7  mov     r9d, 8000FFFFh; char *
0x1800150ad  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800150b4  mov     edx, 1E1h; void *
0x1800150b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800150be  mov     [rsp+2A8h+var_240], 1
0x1800150c6  mov     [rsp+2A8h+pMemory], rsi
0x1800150ce  lea     rax, [rsp+2A8h+pMemory]
0x1800150d6  mov     [rsp+2A8h+var_C8], rax
0x1800150de  mov     [rsp+2A8h+ppInterfaceList], rsi
0x1800150e6  mov     [rsp+2A8h+var_B8], 1
0x1800150ee  lea     rax, [rsp+2A8h+ppInterfaceList]
0x1800150f6  mov     qword ptr [rsp+2A8h+cbData], rax
0x1800150fb  lea     rax, [rsp+2A8h+var_254]
0x180015100  mov     [rsp+2A8h+ppv], rax
0x180015105  lea     r9, aHasConnected; "Has Connected"
0x18001510c  xor     r8d, r8d
0x18001510f  mov     rdx, rbx
0x180015112  mov     rcx, r14
0x180015115  call    cs:__imp_WlanGetProfileMetadataWithProfileGuid
0x18001511b  mov     ebx, eax
0x18001511d  lea     rcx, [rsp+2A8h+var_C8]
0x180015125  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x18001512a  test    ebx, ebx
0x18001512c  jnz     short loc_180015146
0x18001512e  cmp     [rsp+2A8h+var_254], 4
0x180015133  jnz     short loc_180015146
0x180015135  mov     rax, [rsp+2A8h+pMemory]
0x18001513d  cmp     dword ptr [rax], 1
0x180015140  jnz     short loc_180015146
0x180015142  mov     [rsp+2A8h+var_240], esi
0x180015146  mov     ebx, [rsp+2A8h+var_250]
0x18001514a  mov     r12, [rsp+2A8h+var_200]
0x180015152  mov     rdx, [rsp+2A8h+var_238]
0x180015157  lea     rcx, [rsp+2A8h+var_C8]
0x18001515f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015164  nop
0x180015165  lea     rdx, [rsp+2A8h+var_C8]
0x18001516d  lea     rcx, [rsp+2A8h+var_78]
0x180015175  call    ?ProfileNameToCDSReferenceId@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(std::wstring const &)
0x18001517a  nop
0x18001517b  mov     dword ptr [rsp+2A8h+ppv], ebx
0x18001517f  mov     r9d, 2
0x180015185  mov     r8, r12
0x180015188  mov     rdx, rax
0x18001518b  lea     rcx, [rsp+2A8h+var_A8]
0x180015193  call    ??0SyncNeededProfile@WiFiCloudStore@Internal@Windows@@QEAA@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_FILETIME@@W4ProfileModificationType@123@W4ProfileGeneration@123@@Z; Windows::Internal::WiFiCloudStore::SyncNeededProfile::SyncNeededProfile(std::wstring &&,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration)
0x180015198  nop
0x180015199  lea     rcx, [rsp+2A8h+var_78]
0x1800151a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800151a6  nop
0x1800151a7  lea     rcx, [rsp+2A8h+var_C8]
0x1800151af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800151b4  lea     rax, [rsp+2A8h+var_250]
0x1800151b9  mov     [rsp+2A8h+var_268], rax
0x1800151be  mov     [rsp+2A8h+var_270], r15
0x1800151c3  lea     rax, [rsp+2A8h+Block]
0x1800151cb  mov     [rsp+2A8h+var_278], rax
0x1800151d0  mov     qword ptr [rsp+2A8h+cbData], r14
0x1800151d5  lea     rax, [rsp+2A8h+var_A8]
0x1800151dd  mov     [rsp+2A8h+ppv], rax
0x1800151e2  lea     r9, [rsp+2A8h+var_258]
0x1800151e7  lea     r8, [rsp+2A8h+var_218]
0x1800151ef  lea     rdx, [rsp+2A8h+var_238]
0x1800151f4  lea     rcx, [rsp+2A8h+var_108]
0x1800151fc  call    _lambda_7f3ecf42dade528cea96be5b9f4d3ed9____lambda_7f3ecf42dade528cea96be5b9f4d3ed9_
0x180015201  mov     rdx, rax
0x180015204  lea     rcx, [rsp+2A8h+var_198]
0x18001520c  call    wil__scope_exit__lambda_7f3ecf42dade528cea96be5b9f4d3ed9___
0x180015211  nop
0x180015212  lea     rax, [rsp+2A8h+var_240]
0x180015217  mov     [rsp+2A8h+var_270], rax
0x18001521c  lea     rax, [rsp+2A8h+var_A8]
0x180015224  mov     [rsp+2A8h+var_278], rax
0x180015229  mov     qword ptr [rsp+2A8h+cbData], r14
0x18001522e  lea     rax, [rsp+2A8h+var_238]
0x180015233  mov     [rsp+2A8h+ppv], rax
0x180015238  lea     r9, [rsp+2A8h+phClientHandle]
0x180015240  mov     r8, r13
0x180015243  mov     rdx, r15
0x180015246  lea     rcx, [rsp+2A8h+var_78]
0x18001524e  call    _lambda_612a61c8f178d30cb019cab59c668fc2____lambda_612a61c8f178d30cb019cab59c668fc2_
0x180015253  mov     rdx, rax
0x180015256  lea     rcx, [rsp+2A8h+var_148]
0x18001525e  call    std__function_void___cdecl_unsigned_short_const______function_void___cdecl_unsigned_short_const______lambda_612a61c8f178d30cb019cab59c668fc2__0_
0x180015263  mov     rdx, rax
0x180015266  mov     ecx, [rsp+2A8h+var_7C]
0x18001526d  call    ?PushCloudChangePerStoreForGeneration@WlanSyncTaskWlanToCDS@@CAXW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@V?$function@$$A6AXPEBG@Z@std@@@Z; WlanSyncTaskWlanToCDS::PushCloudChangePerStoreForGeneration(Windows::Internal::WiFiCloudStore::ProfileGeneration,std::function<void (ushort const *)>)
0x180015272  mov     [rsp+2A8h+var_158], sil
0x18001527a  lea     rcx, [rsp+2A8h+var_198]
0x180015282  call    wil__details__lambda_call__lambda_7f3ecf42dade528cea96be5b9f4d3ed9______lambda_call__lambda_7f3ecf42dade528cea96be5b9f4d3ed9___
0x180015287  nop
0x180015288  lea     rcx, [rsp+2A8h+var_A8]
0x180015290  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015295  nop
0x180015296  mov     rcx, [rsp+2A8h+pMemory]; pMemory
0x18001529e  mov     [rsp+2A8h+pMemory], rsi
0x1800152a6  test    rcx, rcx
0x1800152a9  jz      short loc_1800152B2
0x1800152ab  call    cs:__imp_WlanFreeMemory
0x1800152b1  nop
0x1800152b2  mov     rcx, [rsp+2A8h+var_200]; pMemory
0x1800152ba  mov     [rsp+2A8h+var_200], rsi
0x1800152c2  test    rcx, rcx
0x1800152c5  jz      short loc_1800152FD
0x1800152c7  call    cs:__imp_WlanFreeMemory
0x1800152cd  jmp     short loc_1800152FD
0x1800152cf  mov     [rsp+2A8h+var_254], 5
0x1800152d7  lea     r8, [rsp+2A8h+var_254]
0x1800152dc  lea     rdx, [rsp+2A8h+var_250]
0x1800152e1  lea     rcx, [rsp+2A8h+var_238]
0x1800152e6  call    ??$SidDoesNotAllowAction@AEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@W4WiFiSyncAction@@@WiFiCloudStoreTelemetry@@SAXAEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::SidDoesNotAllowAction<ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,WiFiSyncAction>(ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,WiFiSyncAction &&)
0x1800152eb  jmp     short loc_1800152FD
0x1800152ed  lea     rdx, [rsp+2A8h+var_250]
0x1800152f2  lea     rcx, [rsp+2A8h+var_238]
0x1800152f7  call    ??$ProfileNotEligibleForSync@AEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@WiFiCloudStoreTelemetry@@SAXAEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; WiFiCloudStoreTelemetry::ProfileNotEligibleForSync<ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x1800152fc  nop
0x1800152fd  jmp     short loc_18001531D
0x1800152ff  xor     esi, esi
0x180015301  mov     r14, [rsp+2A8h+var_1E0]
0x180015309  mov     edi, dword ptr [rsp+2A8h+Data]
0x18001530d  mov     r15, [rsp+2A8h+hKey]
0x180015315  mov     r13, [rsp+2A8h+var_1D8]
0x18001531d  inc     edi
0x18001531f  mov     r12b, [rsp+2A8h+arg_10]
0x180015327  jmp     loc_180014F80
0x18001532c  mov     rcx, r13; this
0x18001532f  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x180015334  mov     [r13+10h], rsi
0x180015338  mov     rdx, [rsp+2A8h+var_230]
0x18001533d  test    rdx, rdx
  ... truncated ...
```
