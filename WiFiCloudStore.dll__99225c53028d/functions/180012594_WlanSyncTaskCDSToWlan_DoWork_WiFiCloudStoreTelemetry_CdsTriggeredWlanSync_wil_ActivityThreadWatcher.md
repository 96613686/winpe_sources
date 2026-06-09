# WlanSyncTaskCDSToWlan::DoWork(WiFiCloudStoreTelemetry::CdsTriggeredWlanSync &,wil::ActivityThreadWatcher &)

- ea: `0x180012594`
- end: `0x180012fab`
- name: `?DoWork@WlanSyncTaskCDSToWlan@@QEAA?AW4WiFiCloudStoreTelemetryResult@@AEAVCdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@@Z`
- size: `2583`
- prototype: `__int64 __fastcall(WlanSyncTaskCDSToWlan *, WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *, struct wil::ActivityThreadWatcher *)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011210`

## callees

- `0x180004ce0`
- `0x180006b88`
- `0x1800075bc`
- `0x18000766c`
- `0x1800077bc`
- `0x1800079f0`
- `0x180007f90`
- `0x18000982c`
- `0x18000a710`
- `0x18000a944`
- `0x180010c8c`
- `0x180010d80`
- `0x180010e08`
- `0x180010e7c`
- `0x1800115a0`
- `0x180011690`
- `0x180012594`
- `0x180012fb4`
- `0x1800169bc`
- `0x1800174c0`
- `0x180017de4`
- `0x18001e624`
- `0x1800211b0`
- `0x180025308`
- `0x180025404`
- `0x180028a70`
- `0x1800298f4`
- `0x18002a030`
- `0x18002aad0`
- `0x18002c138`
- `0x18002e2d0`
- `0x180031ce4`
- `0x180039548`
- `0x18003a45c`
- `0x18003a538`
- `0x18003a614`
- `0x180041010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800127f5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800127f5`
- `wlanapi!WlanFreeMemory` at `0x1800127b0`
- `wlanapi!WlanFreeMemory` at `0x180012f47`
- `wlanapi!WlanFreeMemory` at `0x1800127b0`
- `wlanapi!WlanFreeMemory` at `0x180012f47`
- `wlanapi!WlanCloseHandle` at `0x180012629`
- `wlanapi!WlanCloseHandle` at `0x18001277e`
- `wlanapi!WlanCloseHandle` at `0x180012f80`
- `wlanapi!WlanCloseHandle` at `0x180012629`
- `wlanapi!WlanCloseHandle` at `0x18001277e`
- `wlanapi!WlanCloseHandle` at `0x180012f80`
- `wlanapi!WlanPrivateDeleteProfile` at `0x180012bca`
- `wlanapi!WlanPrivateDeleteProfile` at `0x180012bca`
- `wlanapi!WlanEnumInterfaces` at `0x18001271b`
- `wlanapi!WlanEnumInterfaces` at `0x18001271b`
- `wlanapi!WlanOpenHandle` at `0x18001260f`
- `wlanapi!WlanOpenHandle` at `0x18001260f`
- `wlanapi!WlanSetProfileMetadata` at `0x180012ab2`
- `wlanapi!WlanSetProfileMetadata` at `0x180012b12`
- `wlanapi!WlanSetProfileMetadata` at `0x180012ab2`
- `wlanapi!WlanSetProfileMetadata` at `0x180012b12`
- `wlanapi!WlanPrivateSetProfile` at `0x180012a61`
- `wlanapi!WlanPrivateSetProfile` at `0x180012a61`
- `dusmapi!DusmSetUserCost` at `0x180012d90`
- `dusmapi!DusmSetUserCost` at `0x180012d90`

## string_xrefs

- `0x18001280f`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180012840`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180012648`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x1800126ba`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012730`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012a76`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012ac7`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012b27`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012bdf`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012c62`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012d4e`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180012da5`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCDSToWlan::DoWork(
        WlanSyncTaskCDSToWlan *a1,
        WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *a2,
        struct wil::ActivityThreadWatcher *a3)
{
  wil::ActivityThreadWatcher *v3; // r14
  WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *v4; // r13
  WlanSyncTaskCDSToWlan *v5; // r12
  DWORD v6; // eax
  __int64 cloud_store; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, struct _WLAN_INTERFACE_INFO_LIST **); // rbx
  int v11; // eax
  struct _WLAN_INTERFACE_INFO_LIST *v12; // rcx
  DWORD v13; // eax
  void *v14; // rcx
  const char *v15; // r9
  bool v16; // r15
  int LastError; // eax
  WlanSyncTaskCDSToWlan *v18; // rcx
  unsigned int i; // edi
  const struct _GUID *v20; // rbx
  PWLAN_INTERFACE_INFO_LIST v21; // rbx
  PWLAN_INTERFACE_INFO_LIST v22; // rax
  PWLAN_INTERFACE_INFO_LIST v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r12
  _QWORD *v26; // rax
  const char *v27; // r9
  int v28; // ecx
  _QWORD *v29; // r9
  const struct _GUID *v30; // r12
  unsigned int v31; // eax
  PWLAN_INTERFACE_INFO_LIST v32; // rdx
  unsigned int v33; // eax
  PWLAN_INTERFACE_INFO_LIST v34; // rdx
  unsigned int v35; // eax
  PWLAN_INTERFACE_INFO_LIST v36; // rax
  PWLAN_INTERFACE_INFO_LIST v37; // r8
  unsigned int v38; // eax
  PWLAN_INTERFACE_INFO_LIST v39; // rax
  int v40; // edx
  const unsigned __int16 *v41; // r15
  _QWORD *v42; // rax
  const unsigned __int16 *v43; // r8
  int v44; // eax
  _DWORD *v45; // rdx
  unsigned int v46; // eax
  PWLAN_INTERFACE_INFO_LIST v47; // rax
  const char *v48; // r9
  PVOID v49; // rcx
  unsigned int v50; // [rsp+20h] [rbp-4A8h]
  unsigned int v51; // [rsp+20h] [rbp-4A8h]
  bool v52; // [rsp+50h] [rbp-478h]
  bool v53; // [rsp+51h] [rbp-477h]
  WINBOOL IsMember; // [rsp+54h] [rbp-474h] BYREF
  int v55; // [rsp+58h] [rbp-470h] BYREF
  struct _WLAN_INTERFACE_INFO_LIST *v56; // [rsp+60h] [rbp-468h] BYREF
  void *phClientHandle; // [rsp+68h] [rbp-460h] BYREF
  PWLAN_INTERFACE_INFO_LIST v58; // [rsp+70h] [rbp-458h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList[2]; // [rsp+78h] [rbp-450h] BYREF
  __int64 v60; // [rsp+88h] [rbp-440h]
  PVOID pMemory; // [rsp+90h] [rbp-438h] BYREF
  DWORD pdwNegotiatedVersion[4]; // [rsp+98h] [rbp-430h] BYREF
  const struct _GUID *v63; // [rsp+A8h] [rbp-420h]
  _DWORD v64[2]; // [rsp+B0h] [rbp-418h] BYREF
  PWLAN_INTERFACE_INFO_LIST v65; // [rsp+B8h] [rbp-410h]
  WlanSyncTaskCDSToWlan *v66; // [rsp+C0h] [rbp-408h]
  struct _WLAN_INTERFACE_INFO_LIST *v67; // [rsp+C8h] [rbp-400h]
  WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *v68; // [rsp+D0h] [rbp-3F8h]
  WlanSyncTaskCDSToWlan *v69; // [rsp+D8h] [rbp-3F0h]
  struct wil::ActivityThreadWatcher *v70; // [rsp+E0h] [rbp-3E8h]
  int *v71[3]; // [rsp+F0h] [rbp-3D8h] BYREF
  __int64 v72; // [rsp+108h] [rbp-3C0h] BYREF
  std::_Ref_count_base *v73; // [rsp+110h] [rbp-3B8h]
  std::_Ref_count_base *v74; // [rsp+128h] [rbp-3A0h]
  int v75; // [rsp+130h] [rbp-398h] BYREF
  char v76[8]; // [rsp+138h] [rbp-390h] BYREF
  __int64 v77; // [rsp+140h] [rbp-388h]
  char v78[24]; // [rsp+148h] [rbp-380h] BYREF
  __int64 SidToCheck; // [rsp+160h] [rbp-368h] BYREF
  __int64 v80; // [rsp+168h] [rbp-360h]
  _QWORD *v81; // [rsp+170h] [rbp-358h]
  _BYTE v82[40]; // [rsp+178h] [rbp-350h] BYREF
  _QWORD v83[4]; // [rsp+1A0h] [rbp-328h] BYREF
  char v84[8]; // [rsp+1C0h] [rbp-308h] BYREF
  struct _WLAN_INTERFACE_INFO_LIST *v85; // [rsp+1C8h] [rbp-300h]
  _BYTE v86[64]; // [rsp+1F0h] [rbp-2D8h] BYREF
  _BYTE v87[64]; // [rsp+230h] [rbp-298h] BYREF
  struct _GUID v88; // [rsp+270h] [rbp-258h] BYREF
  unsigned __int16 v89[256]; // [rsp+280h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v66 = a1;
  v69 = a1;
  v68 = a2;
  v70 = a3;
  WlanSyncTaskCDSToWlan::RunWlanTriggeredSync(a1, a3);
  pdwNegotiatedVersion[0] = 0;
  phClientHandle = (void *)-1LL;
  v6 = WlanOpenHandle(2u, 0, pdwNegotiatedVersion, &phClientHandle);
  if ( v6 == 1062 )
  {
    if ( phClientHandle != (void *)-1LL )
      WlanCloseHandle(phClientHandle, 0);
    return 1;
  }
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x296,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
      (const char *)v6,
      v50);
  wil::cloud_store::cloud_store(&v72);
  if ( g_downSyncLocalOnlyAccounts )
    goto LABEL_12;
  v56 = 0;
  cloud_store = wil::details::shared_cloud_store_state::get_cloud_store(v72);
  v9 = *(_QWORD *)cloud_store;
  v10 = *(__int64 (__fastcall **)(__int64, struct _WLAN_INTERFACE_INFO_LIST **))(**(_QWORD **)cloud_store + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  v11 = v10(v9, &v56);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
      (const char *)(unsigned int)v11,
      v50);
    v12 = v56;
    goto LABEL_10;
  }
  v12 = v56;
  if ( v56 )
  {
LABEL_10:
    if ( v12 )
    {
      v56 = 0;
      (*(void (__fastcall **)(struct _WLAN_INTERFACE_INFO_LIST *))(*(_QWORD *)&v12->dwNumberOfItems + 16LL))(v12);
    }
LABEL_12:
    pMemory = 0;
    ppInterfaceList[0] = (PWLAN_INTERFACE_INFO_LIST)&pMemory;
    ppInterfaceList[1] = 0;
    LOBYTE(v60) = 1;
    v13 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList[1]);
    if ( v13 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2B0,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
        (const char *)v13,
        v50);
    if ( (_BYTE)v60 )
    {
      v14 = *(void **)ppInterfaceList[0];
      *(_QWORD *)ppInterfaceList[0] = ppInterfaceList[1];
      if ( v14 )
        WlanFreeMemory(v14);
    }
    SidToCheck = 0x500000000000201LL;
    v80 = 0x22000000020LL;
    IsMember = 0;
    if ( CheckTokenMembership(0, &SidToCheck, &IsMember) )
    {
      v16 = IsMember != 0;
      v52 = IsMember != 0;
      LastError = 0;
    }
    else
    {
      v16 = 0;
      v52 = 0;
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x27C,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                    v15);
    }
    v18 = retaddr;
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)(unsigned int)LastError,
        v50);
    v53 = v16;
    for ( i = 0; ; ++i )
    {
      IsMember = i;
      if ( i >= *(_DWORD *)pMemory )
        break;
      v20 = (const struct _GUID *)((char *)pMemory + 532 * i + 8);
      v63 = v20;
      GetGenerationsSupportedOnInterface(v71, v20, phClientHandle);
      WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::BeginComputingNeededWiFiChanges(v4, v20, v71[0], v71[1] - v71[0]);
      v51 = (unsigned int)v20;
      WlanSyncTaskCDSToWlan::ComputeNeededChanges(v5, ppInterfaceList, &v72, v3);
      v55 = -1431655765 * (((char *)ppInterfaceList[1] - (char *)ppInterfaceList[0]) >> 4);
      WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::BeginApplyingNeededWiFiChanges<unsigned int>(v4, &v55);
      v21 = ppInterfaceList[0];
      v22 = ppInterfaceList[1];
      v65 = ppInterfaceList[1];
      while ( 1 )
      {
        v67 = v21;
        if ( v21 == v22 )
          break;
        v23 = v21;
        if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
          v23 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
        wil::ActivityThreadWatcher::SetMessage(
          v3,
          "Profile name: %ws, Generation: %d",
          v23,
          *(unsigned int *)&v21->InterfaceInfo[0].strInterfaceDescription[10]);
        try
        {
          v25 = *(_QWORD *)std::unordered_map<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *>::at(
                             v24,
                             &v21->InterfaceInfo[0].strInterfaceDescription[10]);
          v26 = (_QWORD *)Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(v82, v21);
          if ( v26[3] > 7u )
            v26 = (_QWORD *)*v26;
          wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(v87, v26, v25);
          std::wstring::~wstring(v82);
          wil::cloud_store::load<Windows::Data::WiFi::WiFiProfile>(&v72, v83, v87, 0);
          SidToCheck = (__int64)v3;
          v80 = (__int64)v21;
          v81 = v83;
          v28 = *(_DWORD *)&v21->InterfaceInfo[0].strInterfaceDescription[8];
          if ( v28 == 2 )
          {
            lambda_5905c74302d8c36d27528eb0fc3c0696_::operator()(&SidToCheck);
            pdwNegotiatedVersion[1] = 0;
            v29 = v83;
            if ( v83[3] > 7u )
              v29 = (_QWORD *)v83[0];
            v30 = v63;
            v31 = WlanPrivateSetProfile(phClientHandle, v63, 0, v29);
            if ( v31 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x2E4,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)v31,
                0);
            v32 = v21;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
              v32 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
            v33 = WlanSetProfileMetadata(v30, v32, 0, L"LastModified");
            if ( v33 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x2ED,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)v33,
                8u);
            pdwNegotiatedVersion[2] = 7;
            v34 = v21;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
              v34 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
            v35 = WlanSetProfileMetadata(v30, v34, 0, L"Connection Type");
            if ( v35 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x2F6,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)v35,
                4u);
            v55 = 4;
            v56 = v85;
            v36 = v21;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
              v36 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
            v58 = v36;
            WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::ApplyWiFiCloudChange<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64,unsigned __int64 &,enum WiFiSyncAction>(
              (_DWORD)v4,
              (unsigned int)&v58,
              (_DWORD)v21 + 44,
              (unsigned int)&v56,
              (__int64)v84,
              (__int64)&v55);
          }
          else if ( v28 == 1 )
          {
            lambda_5905c74302d8c36d27528eb0fc3c0696_::operator()(&SidToCheck);
            v37 = v21;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
              v37 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
            v38 = WlanPrivateDeleteProfile(phClientHandle, v63, v37, 0);
            if ( v38 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x304,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)v38,
                0);
            v55 = 3;
            LODWORD(v56) = 0;
            v58 = v85;
            v39 = v21;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
              v39 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
            SidToCheck = (__int64)v39;
            WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::ApplyWiFiCloudChange<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64,int,enum WiFiSyncAction>(
              (_DWORD)v4,
              (unsigned int)&SidToCheck,
              (_DWORD)v21 + 44,
              (unsigned int)&v58,
              (__int64)&v56,
              (__int64)&v55);
          }
          else
          {
            if ( ((v28 - 4) & 0xFFFFFFFB) != 0 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x323,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                v27);
            v40 = 12;
            if ( v28 != 8 )
              v40 = 10;
            LODWORD(v56) = v40;
            lambda_5905c74302d8c36d27528eb0fc3c0696_::operator()(&SidToCheck);
            v41 = c_wiFiCloudStoreDataReferenceDefaultCollectionName;
            v42 = (_QWORD *)Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(v82, v21);
            if ( v42[3] > 7u )
              v42 = (_QWORD *)*v42;
            wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(v86, v42, v41);
            std::wstring::~wstring(v82);
            wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(&v72, &v75, v86, 0);
            memset_0(&v88, 0, 0x210u);
            v88 = *v63;
            v43 = (const unsigned __int16 *)v21;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription > 7u )
              v43 = *(const unsigned __int16 **)&v21->dwNumberOfItems;
            v44 = StringCchCopyW(v89, 0x100u, v43);
            if ( v44 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x318,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)(unsigned int)v44,
                v51);
            v64[0] = v75;
            v64[1] = 2;
            v45 = v64;
            if ( *(_DWORD *)&v21->InterfaceInfo[0].strInterfaceDescription[8] == 8 )
              v45 = 0;
            v46 = DusmSetUserCost(&v88, v45);
            if ( v46 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x31C,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)v46,
                v51);
            SidToCheck = v77;
            if ( *(_QWORD *)v21->InterfaceInfo[0].strInterfaceDescription <= 7u )
              v47 = v21;
            else
              v47 = *(PWLAN_INTERFACE_INFO_LIST *)&v21->dwNumberOfItems;
            v58 = v47;
            WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::ApplyWiFiCloudChange<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64,unsigned __int64 &,enum WiFiSyncAction const &>(
              (_DWORD)v4,
              (unsigned int)&v58,
              (_DWORD)v21 + 44,
              (unsigned int)&SidToCheck,
              (__int64)v76,
              (__int64)&v56);
            wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v78);
            Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v86);
          }
          wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>::~cloud_store_data<Windows::Data::WiFi::WiFiProfile>(v83);
          Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v87);
          v16 = v52;
          v5 = v66;
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x326,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
            v48);
          v16 = v53;
          v52 = v53;
          i = IsMember;
          v21 = v67;
          v4 = v68;
          v5 = v69;
          v66 = v69;
          v3 = v70;
        }
        v22 = v65;
        v21 = (PWLAN_INTERFACE_INFO_LIST)((char *)v21 + 48);
      }
      wil::details::StoredCallContextInfo::ClearMessage(v3);
      *((_QWORD *)v3 + 2) = 0;
      if ( ppInterfaceList[0] )
      {
        std::_Destroy_range<std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>>(
          ppInterfaceList[0],
          ppInterfaceList[1]);
        std::_Deallocate<16>(
          ppInterfaceList[0],
          16 * ((signed __int64)(v60 - (unsigned __int64)ppInterfaceList[0]) >> 4));
        *(_OWORD *)ppInterfaceList = 0;
        v60 = 0;
      }
      v18 = (WlanSyncTaskCDSToWlan *)v71[0];
      if ( v71[0] )
        std::_Deallocate<16>(v71[0], ((char *)v71[2] - (char *)v71[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    }
    WlanSyncTaskCDSToWlan::UpdateLocalNlmCategories(v18, v4, v16);
    v49 = pMemory;
    pMemory = 0;
    if ( v49 )
      WlanFreeMemory(v49);
    if ( v74 )
      std::_Ref_count_base::_Decref(v74);
    if ( v73 )
      std::_Ref_count_base::_Decref(v73);
    if ( phClientHandle != (void *)-1LL )
      WlanCloseHandle(phClientHandle, 0);
    return 0;
  }
  if ( v74 )
    std::_Ref_count_base::_Decref(v74);
  if ( v73 )
    std::_Ref_count_base::_Decref(v73);
  if ( phClientHandle != (void *)-1LL )
    WlanCloseHandle(phClientHandle, 0);
  return 2;
}

```

## disassembly

```asm
0x180012594  push    rbx
0x180012596  push    rsi
0x180012597  push    rdi
0x180012598  push    r12
0x18001259a  push    r13
0x18001259c  push    r14
0x18001259e  push    r15
0x1800125a0  sub     rsp, 490h
0x1800125a7  mov     rax, cs:__security_cookie
0x1800125ae  xor     rax, rsp
0x1800125b1  mov     [rsp+4C8h+var_48], rax
0x1800125b9  mov     r14, r8
0x1800125bc  mov     r13, rdx
0x1800125bf  mov     r12, rcx
0x1800125c2  mov     [rsp+4C8h+var_408], rcx
0x1800125ca  mov     [rsp+4C8h+var_3F0], rcx
0x1800125d2  mov     [rsp+4C8h+var_3F8], rdx
0x1800125da  mov     [rsp+4C8h+var_3E8], r8
0x1800125e2  mov     rdx, r8; struct wil::ActivityThreadWatcher *
0x1800125e5  call    ?RunWlanTriggeredSync@WlanSyncTaskCDSToWlan@@AEAAXAEAVActivityThreadWatcher@wil@@@Z; WlanSyncTaskCDSToWlan::RunWlanTriggeredSync(wil::ActivityThreadWatcher &)
0x1800125ea  nop
0x1800125eb  xor     esi, esi
0x1800125ed  mov     [rsp+4C8h+pdwNegotiatedVersion], esi
0x1800125f4  mov     [rsp+4C8h+phClientHandle], 0FFFFFFFFFFFFFFFFh
0x1800125fd  lea     r9, [rsp+4C8h+phClientHandle]; phClientHandle
0x180012602  lea     r8, [rsp+4C8h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18001260a  xor     edx, edx; pReserved
0x18001260c  lea     ecx, [rsi+2]; dwClientVersion
0x18001260f  call    cs:__imp_WlanOpenHandle
0x180012615  cmp     eax, 426h
0x18001261a  jnz     short loc_180012639
0x18001261c  mov     rcx, [rsp+4C8h+phClientHandle]; hClientHandle
0x180012621  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012625  jz      short loc_18001262F
0x180012627  xor     edx, edx; pReserved
0x180012629  call    cs:__imp_WlanCloseHandle
0x18001262f  mov     eax, 1
0x180012634  jmp     loc_180012F88
0x180012639  mov     rcx, [rsp+4C8h]; this
0x180012641  test    eax, eax
0x180012643  jz      short loc_18001265A
0x180012645  mov     r9d, eax; char *
0x180012648  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18001264f  mov     edx, 296h; void *
0x180012654  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001265a  lea     rcx, [rsp+4C8h+var_3C0]
0x180012662  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180012667  nop
0x180012668  cmp     cs:?g_downSyncLocalOnlyAccounts@@3_NA, sil; bool g_downSyncLocalOnlyAccounts
0x18001266f  jnz     short loc_1800126E7
0x180012671  mov     [rsp+4C8h+var_468], rsi
0x180012676  mov     rcx, [rsp+4C8h+var_3C0]
0x18001267e  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180012683  mov     rdi, [rax]
0x180012686  mov     rax, [rdi]
0x180012689  mov     rbx, [rax+38h]
0x18001268d  lea     rcx, [rsp+4C8h+var_468]
0x180012692  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012697  lea     rdx, [rsp+4C8h+var_468]
0x18001269c  mov     rcx, rdi
0x18001269f  mov     rax, rbx
0x1800126a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126a7  mov     rcx, [rsp+4C8h]; this
0x1800126af  test    eax, eax
0x1800126b1  jns     loc_180012742
0x1800126b7  mov     r9d, eax; char *
0x1800126ba  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800126c1  mov     edx, 2A5h; void *
0x1800126c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800126cb  mov     rcx, [rsp+4C8h+var_468]
0x1800126d0  test    rcx, rcx
0x1800126d3  jz      short loc_1800126E7
0x1800126d5  mov     [rsp+4C8h+var_468], rsi
0x1800126da  mov     rax, [rcx]
0x1800126dd  mov     rax, [rax+10h]
0x1800126e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e6  nop
0x1800126e7  mov     [rsp+4C8h+pMemory], rsi
0x1800126ef  lea     rax, [rsp+4C8h+pMemory]
0x1800126f7  mov     [rsp+4C8h+ppInterfaceList], rax
0x1800126fc  mov     [rsp+4C8h+ppInterfaceList+8], rsi
0x180012704  mov     byte ptr [rsp+4C8h+var_440], 1
0x18001270c  lea     r8, [rsp+4C8h+ppInterfaceList+8]; ppInterfaceList
0x180012714  xor     edx, edx; pReserved
0x180012716  mov     rcx, [rsp+4C8h+phClientHandle]; hClientHandle
0x18001271b  call    cs:__imp_WlanEnumInterfaces
0x180012721  mov     rcx, [rsp+4C8h]; this
0x180012729  test    eax, eax
0x18001272b  jz      short loc_18001278E
0x18001272d  mov     r9d, eax; char *
0x180012730  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180012737  mov     edx, 2B0h; void *
0x18001273c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012742  mov     rcx, [rsp+4C8h+var_468]
0x180012747  test    rcx, rcx
0x18001274a  jnz     short loc_1800126D0
0x18001274c  mov     rcx, [rsp+4C8h+var_3A0]; this
0x180012754  test    rcx, rcx
0x180012757  jz      short loc_18001275E
0x180012759  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001275e  mov     rcx, [rsp+4C8h+var_3B8]; this
0x180012766  test    rcx, rcx
0x180012769  jz      short loc_180012771
0x18001276b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012770  nop
0x180012771  mov     rcx, [rsp+4C8h+phClientHandle]; hClientHandle
0x180012776  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001277a  jz      short loc_180012784
0x18001277c  xor     edx, edx; pReserved
0x18001277e  call    cs:__imp_WlanCloseHandle
0x180012784  mov     eax, 2
0x180012789  jmp     loc_180012F88
0x18001278e  cmp     byte ptr [rsp+4C8h+var_440], sil
0x180012796  jz      short loc_1800127B6
0x180012798  mov     rdx, [rsp+4C8h+ppInterfaceList]
0x18001279d  mov     rcx, [rdx]; pMemory
0x1800127a0  mov     rax, [rsp+4C8h+ppInterfaceList+8]
0x1800127a8  mov     [rdx], rax
0x1800127ab  test    rcx, rcx
0x1800127ae  jz      short loc_1800127B6
0x1800127b0  call    cs:__imp_WlanFreeMemory
0x1800127b6  mov     dword ptr [rsp+4C8h+SidToCheck], 201h
0x1800127c1  mov     dword ptr [rsp+4C8h+SidToCheck+4], 5000000h
0x1800127cc  mov     dword ptr [rsp+4C8h+var_360], 20h ; ' '
0x1800127d7  mov     dword ptr [rsp+4C8h+var_360+4], 220h
0x1800127e2  mov     [rsp+4C8h+IsMember], esi
0x1800127e6  lea     r8, [rsp+4C8h+IsMember]; IsMember
0x1800127eb  lea     rdx, [rsp+4C8h+SidToCheck]; SidToCheck
0x1800127f3  xor     ecx, ecx; TokenHandle
0x1800127f5  call    cs:__imp_CheckTokenMembership
0x1800127fb  test    eax, eax
0x1800127fd  jnz     short loc_180012822
0x1800127ff  mov     r15b, sil
0x180012802  mov     [rsp+4C8h+var_478], sil
0x180012807  mov     rcx, [rsp+4C8h]; this
0x18001280f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012816  mov     edx, 27Ch; void *
0x18001281b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012820  jmp     short loc_180012831
0x180012822  cmp     [rsp+4C8h+IsMember], esi
0x180012826  setnz   r15b
0x18001282a  mov     [rsp+4C8h+var_478], r15b
0x18001282f  mov     eax, esi
0x180012831  mov     rcx, [rsp+4C8h]; this
0x180012839  test    eax, eax
0x18001283b  jns     short loc_180012852
0x18001283d  mov     r9d, eax; char *
0x180012840  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012847  mov     edx, 2C1h; void *
0x18001284c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012852  mov     [rsp+4C8h+var_477], r15b
0x180012857  mov     edi, esi
0x180012859  mov     [rsp+4C8h+IsMember], edi
0x18001285d  mov     rax, [rsp+4C8h+pMemory]
0x180012865  cmp     edi, [rax]
0x180012867  jnb     loc_180012F26
0x18001286d  mov     ecx, edi
0x18001286f  imul    rbx, rcx, 214h
0x180012876  add     rax, 8
0x18001287a  add     rbx, rax
0x18001287d  mov     [rsp+4C8h+var_420], rbx
0x180012885  mov     r8, [rsp+4C8h+phClientHandle]
0x18001288a  mov     rdx, rbx
0x18001288d  lea     rcx, [rsp+4C8h+var_3D8]
0x180012895  call    ?GetGenerationsSupportedOnInterface@@YA?AV?$vector@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@V?$allocator@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEBU_GUID@@QEAX@Z; GetGenerationsSupportedOnInterface(_GUID const &,void * const)
0x18001289a  nop
0x18001289b  mov     r9, [rsp+4C8h+var_3D0]
0x1800128a3  mov     r8, [rsp+4C8h+var_3D8]; int *
0x1800128ab  sub     r9, r8
0x1800128ae  sar     r9, 2; unsigned __int64
0x1800128b2  mov     rdx, rbx; struct _GUID *
0x1800128b5  mov     rcx, r13; this
0x1800128b8  call    ?BeginComputingNeededWiFiChanges@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAAXAEBU_GUID@@PEAH_K@Z; WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::BeginComputingNeededWiFiChanges(_GUID const &,int *,unsigned __int64)
0x1800128bd  mov     byte ptr [rsp+4C8h+var_498], r15b
0x1800128c2  lea     rax, [rsp+4C8h+var_3D8]
0x1800128ca  mov     [rsp+4C8h+var_4A0], rax
0x1800128cf  mov     qword ptr [rsp+4C8h+var_4A8], rbx; unsigned int
0x1800128d4  mov     r9, r14
0x1800128d7  lea     r8, [rsp+4C8h+var_3C0]
0x1800128df  lea     rdx, [rsp+4C8h+ppInterfaceList]
0x1800128e4  mov     rcx, r12
0x1800128e7  call    ?ComputeNeededChanges@WlanSyncTaskCDSToWlan@@QEAA?AV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEAVcloud_store@wil@@AEAVActivityThreadWatcher@5@AEBU_GUID@@AEBV?$vector@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@V?$allocator@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@@3@_N@Z; WlanSyncTaskCDSToWlan::ComputeNeededChanges(wil::cloud_store &,wil::ActivityThreadWatcher &,_GUID const &,std::vector<Windows::Internal::WiFiCloudStore::ProfileGeneration> const &,bool)
0x1800128ec  nop
0x1800128ed  mov     rax, [rsp+4C8h+ppInterfaceList+8]
0x1800128f5  sub     rax, [rsp+4C8h+ppInterfaceList]
0x1800128fa  sar     rax, 4
0x1800128fe  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180012908  imul    rax, rcx
0x18001290c  mov     [rsp+4C8h+var_470], eax
0x180012910  lea     rdx, [rsp+4C8h+var_470]
0x180012915  mov     rcx, r13
0x180012918  call    ??$BeginApplyingNeededWiFiChanges@I@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAI@Z; WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::BeginApplyingNeededWiFiChanges<uint>(uint &&)
0x18001291d  mov     rbx, [rsp+4C8h+ppInterfaceList]
0x180012922  mov     rax, [rsp+4C8h+ppInterfaceList+8]
0x18001292a  mov     [rsp+4C8h+var_410], rax
0x180012932  mov     [rsp+4C8h+var_400], rbx
0x18001293a  cmp     rbx, rax
0x18001293d  jz      loc_180012E9B
0x180012943  lea     r15, [rbx+2Ch]
0x180012947  mov     r8, rbx
0x18001294a  cmp     qword ptr [rbx+18h], 7
0x18001294f  jbe     short loc_180012954
0x180012951  mov     r8, [rbx]
0x180012954  mov     r9d, [r15]
0x180012957  lea     rdx, aProfileNameWsG_0; "Profile name: %ws, Generation: %d"
0x18001295e  mov     rcx, r14; this
0x180012961  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x180012966  mov     rdx, r15
0x180012969  call    ?at@?$unordered_map@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGU?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@@std@@QEBAAEBQEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; std::unordered_map<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *>::at(Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x18001296e  mov     r12, [rax]
0x180012971  mov     rdx, rbx
0x180012974  lea     rcx, [rsp+4C8h+var_350]
0x18001297c  call    ?ProfileNameToCDSReferenceId@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(std::wstring const &)
0x180012981  nop
0x180012982  cmp     qword ptr [rax+18h], 7
0x180012987  jbe     short loc_18001298C
0x180012989  mov     rax, [rax]
0x18001298c  mov     r8, r12
0x18001298f  mov     rdx, rax
0x180012992  lea     rcx, [rsp+4C8h+var_298]
0x18001299a  call    ??$make_cloud_store_data_reference@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@YA?AU?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(ushort const *,ushort const *)
0x18001299f  nop
0x1800129a0  lea     rcx, [rsp+4C8h+var_350]
0x1800129a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800129ad  xor     r9d, r9d
0x1800129b0  lea     r8, [rsp+4C8h+var_298]
0x1800129b8  lea     rdx, [rsp+4C8h+var_328]
0x1800129c0  lea     rcx, [rsp+4C8h+var_3C0]
0x1800129c8  call    ??$load@UWiFiProfile@WiFi@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@1@AEBU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::WiFi::WiFiProfile>(Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> const &,wil::cloud_store_load_options,char const *)
0x1800129cd  nop
0x1800129ce  mov     [rsp+4C8h+SidToCheck], r14
0x1800129d6  mov     [rsp+4C8h+var_360], rbx
0x1800129de  lea     rax, [rsp+4C8h+var_328]
0x1800129e6  mov     [rsp+4C8h+var_358], rax
0x1800129ee  mov     ecx, [rbx+28h]
0x1800129f1  cmp     ecx, 2
0x1800129f4  jnz     loc_180012B90
0x1800129fa  lea     edx, [rcx+2]
0x1800129fd  lea     rcx, [rsp+4C8h+SidToCheck]
0x180012a05  call    _lambda_5905c74302d8c36d27528eb0fc3c0696___operator__
0x180012a0a  mov     [rsp+4C8h+var_42C], esi
0x180012a11  lea     r9, [rsp+4C8h+var_328]
0x180012a19  cmp     [rsp+4C8h+var_310], 7
0x180012a22  cmova   r9, [rsp+4C8h+var_328]
0x180012a2b  lea     rax, [rsp+4C8h+var_42C]
0x180012a33  mov     [rsp+4C8h+var_488], rax
0x180012a38  mov     [rsp+4C8h+var_490], esi
0x180012a3c  mov     [rsp+4C8h+var_498], rsi
0x180012a41  mov     dword ptr [rsp+4C8h+var_4A0], 1
0x180012a49  mov     qword ptr [rsp+4C8h+var_4A8], rsi; unsigned int
0x180012a4e  xor     r8d, r8d
0x180012a51  mov     r12, [rsp+4C8h+var_420]
0x180012a59  mov     rdx, r12
0x180012a5c  mov     rcx, [rsp+4C8h+phClientHandle]
0x180012a61  call    cs:__imp_WlanPrivateSetProfile
0x180012a67  mov     rcx, [rsp+4C8h]; this
0x180012a6f  test    eax, eax
0x180012a71  jz      short loc_180012A87
0x180012a73  mov     r9d, eax; char *
0x180012a76  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180012a7d  mov     edx, 2E4h; void *
0x180012a82  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012a87  mov     rdx, rbx
0x180012a8a  cmp     qword ptr [rbx+18h], 7
0x180012a8f  jbe     short loc_180012A94
0x180012a91  mov     rdx, [rbx]
0x180012a94  lea     rax, [rbx+20h]
0x180012a98  mov     [rsp+4C8h+var_4A0], rax
0x180012a9d  mov     [rsp+4C8h+var_4A8], 8; unsigned int
0x180012aa5  lea     r9, aLastmodified; "LastModified"
0x180012aac  xor     r8d, r8d
0x180012aaf  mov     rcx, r12
0x180012ab2  call    cs:__imp_WlanSetProfileMetadata
0x180012ab8  mov     rcx, [rsp+4C8h]; this
0x180012ac0  test    eax, eax
0x180012ac2  jz      short loc_180012AD8
0x180012ac4  mov     r9d, eax; char *
0x180012ac7  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180012ace  mov     edx, 2EDh; void *
0x180012ad3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012ad8  mov     [rsp+4C8h+var_428], 7
0x180012ae3  mov     rdx, rbx
0x180012ae6  cmp     qword ptr [rbx+18h], 7
0x180012aeb  jbe     short loc_180012AF0
0x180012aed  mov     rdx, [rbx]
0x180012af0  lea     rax, [rsp+4C8h+var_428]
0x180012af8  mov     [rsp+4C8h+var_4A0], rax
0x180012afd  mov     [rsp+4C8h+var_4A8], 4; unsigned int
0x180012b05  lea     r9, aConnectionType; "Connection Type"
0x180012b0c  xor     r8d, r8d
0x180012b0f  mov     rcx, r12
0x180012b12  call    cs:__imp_WlanSetProfileMetadata
0x180012b18  mov     rcx, [rsp+4C8h]; this
0x180012b20  test    eax, eax
0x180012b22  jz      short loc_180012B38
0x180012b24  mov     r9d, eax; char *
0x180012b27  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180012b2e  mov     edx, 2F6h; void *
0x180012b33  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012b38  mov     [rsp+4C8h+var_470], 4
  ... truncated ...
```
