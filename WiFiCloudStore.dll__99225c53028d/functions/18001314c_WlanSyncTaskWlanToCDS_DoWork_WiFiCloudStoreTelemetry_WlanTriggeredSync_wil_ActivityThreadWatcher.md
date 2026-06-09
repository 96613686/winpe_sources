# WlanSyncTaskWlanToCDS::DoWork(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &)

- ea: `0x18001314c`
- end: `0x180013a8c`
- name: `?DoWork@WlanSyncTaskWlanToCDS@@QEBA?AW4WiFiCloudStoreTelemetryResult@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@@Z`
- size: `2368`
- prototype: `__int64 __fastcall(__int64, struct WiFiCloudStoreTelemetry::WlanTriggeredSync *, struct wil::ActivityThreadWatcher *)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012fb4`
- `0x18001f808`

## callees

- `0x180005e00`
- `0x180006afc`
- `0x18000766c`
- `0x1800077bc`
- `0x180007f90`
- `0x18000aebc`
- `0x18000b528`
- `0x18000b99c`
- `0x1800118a0`
- `0x180011b94`
- `0x18001314c`
- `0x180013ef0`
- `0x1800144c0`
- `0x180014d70`
- `0x18001f3ec`
- `0x1800207c8`
- `0x180020864`
- `0x180025308`
- `0x180025404`
- `0x18002543c`
- `0x180025c70`
- `0x1800272cc`
- `0x180028a70`
- `0x18002a030`
- `0x18002a43c`
- `0x18002c138`
- `0x18002e2d0`
- `0x180031ce4`
- `0x180032ab0`
- `0x180032b68`
- `0x1800337d4`
- `0x180034144`
- `0x1800364c8`
- `0x18003cc40`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013243`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013243`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800134ee`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013541`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800134ee`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013541`
- `wlanapi!WlanFreeMemory` at `0x180013328`
- `wlanapi!WlanFreeMemory` at `0x180013a40`
- `wlanapi!WlanFreeMemory` at `0x180013328`
- `wlanapi!WlanFreeMemory` at `0x180013a40`
- `wlanapi!WlanCloseHandle` at `0x1800131d3`
- `wlanapi!WlanCloseHandle` at `0x180013a57`
- `wlanapi!WlanCloseHandle` at `0x1800131d3`
- `wlanapi!WlanCloseHandle` at `0x180013a57`
- `wlanapi!WlanEnumInterfaces` at `0x1800132d8`
- `wlanapi!WlanEnumInterfaces` at `0x1800132d8`
- `wlanapi!WlanOpenHandle` at `0x1800131b6`
- `wlanapi!WlanOpenHandle` at `0x1800131b6`

## string_xrefs

- `0x180013258`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180013284`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800131f2`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800132ed`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800134cc`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x18001375f`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::DoWork(
        __int64 a1,
        struct WiFiCloudStoreTelemetry::WlanTriggeredSync *a2,
        struct wil::ActivityThreadWatcher *a3)
{
  struct wil::ActivityThreadWatcher *v3; // r14
  struct WiFiCloudStoreTelemetry::WlanTriggeredSync *v4; // rsi
  DWORD v5; // eax
  const char *v7; // r9
  bool v8; // r15
  int LastError; // eax
  DWORD v10; // eax
  void *v11; // rcx
  __int64 i; // rcx
  struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *v13; // rdi
  PWLAN_INTERFACE_INFO_LIST v14; // rax
  unsigned int *v15; // r12
  unsigned __int16 **v16; // r8
  unsigned __int16 **v17; // r8
  wil::filetime *v18; // rcx
  unsigned __int16 **v19; // rax
  unsigned __int16 **v20; // rax
  const char *v21; // r9
  const unsigned __int16 *v22; // r8
  unsigned __int16 **v23; // rax
  const char *v24; // r9
  int v25; // ecx
  __int64 v26; // rax
  __int64 v27; // rax
  void *v28; // rcx
  PVOID v29; // rcx
  const struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *v30; // rbx
  unsigned __int16 **v31; // rax
  unsigned __int16 **v32; // rax
  _BYTE v33[32]; // [rsp+0h] [rbp-1F8h] BYREF
  int v34[2]; // [rsp+20h] [rbp-1D8h]
  WINBOOL IsMember; // [rsp+50h] [rbp-1A8h] BYREF
  int v36; // [rsp+54h] [rbp-1A4h] BYREF
  bool v37; // [rsp+58h] [rbp-1A0h]
  int v38; // [rsp+5Ch] [rbp-19Ch] BYREF
  int v39; // [rsp+60h] [rbp-198h] BYREF
  int v40; // [rsp+64h] [rbp-194h] BYREF
  int v41; // [rsp+68h] [rbp-190h] BYREF
  PVOID pMemory; // [rsp+70h] [rbp-188h] BYREF
  int *v43; // [rsp+78h] [rbp-180h] BYREF
  unsigned __int16 **v44; // [rsp+80h] [rbp-178h] BYREF
  HANDLE hClientHandle; // [rsp+88h] [rbp-170h] BYREF
  __int64 v46; // [rsp+90h] [rbp-168h] BYREF
  Windows::Internal::WiFiCloudStore::SyncNeededProfile *v47[2]; // [rsp+98h] [rbp-160h]
  struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *p_pMemory; // [rsp+A8h] [rbp-150h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+B0h] [rbp-148h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-140h]
  FILETIME FileTime1; // [rsp+C0h] [rbp-138h] BYREF
  DWORD v52; // [rsp+C8h] [rbp-130h] BYREF
  void *Block; // [rsp+D0h] [rbp-128h] BYREF
  struct WiFiCloudStoreTelemetry::WlanTriggeredSync *v54; // [rsp+D8h] [rbp-120h]
  PWLAN_INTERFACE_INFO_LIST j; // [rsp+E0h] [rbp-118h]
  struct WiFiCloudStoreTelemetry::WlanTriggeredSync *v56; // [rsp+E8h] [rbp-110h] BYREF
  struct wil::ActivityThreadWatcher *v57; // [rsp+F0h] [rbp-108h]
  HANDLE *p_hClientHandle; // [rsp+F8h] [rbp-100h]
  unsigned __int16 **v59; // [rsp+100h] [rbp-F8h]
  PVOID *v60; // [rsp+108h] [rbp-F0h]
  WINBOOL *p_IsMember; // [rsp+110h] [rbp-E8h]
  struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *v62; // [rsp+118h] [rbp-E0h]
  FILETIME *p_FileTime2; // [rsp+120h] [rbp-D8h]
  FILETIME v64; // [rsp+128h] [rbp-D0h] BYREF
  struct wil::ActivityThreadWatcher *v65; // [rsp+130h] [rbp-C8h]
  _BYTE v66[64]; // [rsp+140h] [rbp-B8h] BYREF
  FILETIME FileTime2; // [rsp+180h] [rbp-78h] BYREF
  int v68; // [rsp+188h] [rbp-70h]
  unsigned __int16 *v69[3]; // [rsp+190h] [rbp-68h] BYREF
  unsigned __int64 v70; // [rsp+1A8h] [rbp-50h]
  DWORD SidToCheck; // [rsp+1B0h] [rbp-48h] BYREF
  FILETIME v72; // [rsp+1B4h] [rbp-44h]
  int v73; // [rsp+1BCh] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  v54 = a2;
  v65 = a3;
  v52 = 0;
  hClientHandle = (HANDLE)-1LL;
  v5 = WlanOpenHandle(2u, 0, &v52, &hClientHandle);
  if ( v5 == 1062 )
  {
    if ( hClientHandle != (HANDLE)-1LL )
      WlanCloseHandle(hClientHandle, 0);
    return 1;
  }
  else
  {
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
        (const char *)v5,
        v34[0]);
    SidToCheck = 513;
    v72 = (FILETIME)0x2005000000LL;
    v73 = 544;
    IsMember = 0;
    if ( CheckTokenMembership(0, &SidToCheck, &IsMember) )
    {
      v8 = IsMember != 0;
      LastError = 0;
    }
    else
    {
      v8 = 0;
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x27C,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                    v7);
    }
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)(unsigned int)LastError,
        v34[0]);
    WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded(v4, v3, v8);
    pMemory = 0;
    p_pMemory = (struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *)&pMemory;
    ppInterfaceList = 0;
    LOBYTE(v50) = 1;
    v10 = WlanEnumInterfaces(hClientHandle, 0, &ppInterfaceList);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
        (const char *)v10,
        v34[0]);
    v37 = v8;
    if ( (_BYTE)v50 )
    {
      v11 = *(void **)p_pMemory;
      *(_QWORD *)p_pMemory = ppInterfaceList;
      if ( v11 )
        WlanFreeMemory(v11);
    }
    IsMember = 0;
    for ( i = 0; (unsigned int)i < *(_DWORD *)pMemory; i = (unsigned int)++IsMember )
    {
      WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginProcessingWiFiRegistry<_GUID &>(
        v4,
        (char *)pMemory + 532 * i + 8);
      Windows::Internal::WiFiCloudStore::GetSyncNeededProfilesFromRegistry(
        &p_pMemory,
        (char *)pMemory + 532 * (unsigned int)IsMember + 8);
      v36 = -1431655765 * (((char *)ppInterfaceList - (char *)p_pMemory) >> 4);
      WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginSyncingWiFiChanges<unsigned int>(v4, &v36);
      std::vector<bond::blob>::vector<bond::blob>(&v46);
      v13 = p_pMemory;
      v14 = ppInterfaceList;
      for ( j = ppInterfaceList; ; v14 = j )
      {
        v43 = (int *)v13;
        if ( v13 == (struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *)v14 )
          break;
        Windows::Internal::WiFiCloudStore::CDSReferenceIdToProfileName(v69, v13);
        v15 = (unsigned int *)((char *)v13 + 44);
        v16 = v69;
        if ( v70 > 7 )
          v16 = (unsigned __int16 **)v69[0];
        wil::ActivityThreadWatcher::SetMessage(v3, "Profile name: %ws, Generation: %d", v16, *v15);
        FileTime2 = 0;
        v68 = 0;
        Windows::Internal::WiFiCloudStore::TryGetRetryCountForProfile(
          (unsigned int)v69,
          532 * IsMember + (_DWORD)pMemory + 8,
          *((_DWORD *)v13 + 10),
          *v15,
          (__int64)&FileTime2);
        v17 = v69;
        if ( v70 > 7 )
          v17 = (unsigned __int16 **)v69[0];
        v34[0] = FileTime2.dwLowDateTime;
        wil::ActivityThreadWatcher::SetMessage(v3, "Profile name: %ws, Generation: %d, Retry count: %lu", v17, *v15);
        FileTime1 = wil::filetime::get_system_time(v18);
        if ( FileTime2.dwLowDateTime > 3 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
            (const char *)0x80070057LL,
            v34[0]);
        if ( CompareFileTime(&FileTime1, (const FILETIME *)&FileTime2.dwHighDateTime) == -1
          || !FileTime2.dwLowDateTime
          || (v64 = (FILETIME)wil::filetime::add<__int64,0>(
                                &FileTime2.dwHighDateTime,
                                *(_QWORD *)&asc_180045274[8 * FileTime2.dwLowDateTime + 4]),
              CompareFileTime(&FileTime1, &v64) == 1) )
        {
          try
          {
            wil::GetTokenInformation<_TOKEN_USER>(&Block);
            if ( *((_DWORD *)v13 + 10) == 1 || *((_DWORD *)v13 + 10) == 8 )
              goto LABEL_44;
            v22 = (const unsigned __int16 *)v69;
            if ( v70 > 7 )
              v22 = v69[0];
            if ( WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileName(
                   (const struct _TOKEN_USER *)Block,
                   (const struct _GUID *)((char *)pMemory + 532 * (unsigned int)IsMember + 8),
                   v22,
                   v8) )
            {
LABEL_44:
              v25 = *((_DWORD *)v13 + 10);
              if ( (unsigned int)(v25 - 1) <= 1 )
              {
                v56 = v4;
                v57 = v3;
                p_hClientHandle = &hClientHandle;
                v59 = v69;
                v60 = &pMemory;
                p_IsMember = &IsMember;
                v62 = v13;
                p_FileTime2 = &FileTime2;
                v27 = std::function_void___cdecl_unsigned_short_const____::function_void___cdecl_unsigned_short_const______lambda_a4316d221a39b8b1a3f505ab3f9b0fe2__0_(
                        v66,
                        &v56);
                WlanSyncTaskWlanToCDS::PushCloudChangePerStoreForGeneration(*v15, v27);
              }
              else
              {
                if ( ((v25 - 4) & 0xFFFFFFFB) != 0 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0xAF,
                    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
                    v21);
                v56 = v4;
                v57 = v3;
                p_hClientHandle = &hClientHandle;
                v59 = v69;
                v60 = &pMemory;
                p_IsMember = &IsMember;
                v62 = v13;
                p_FileTime2 = &FileTime2;
                v26 = std::function_void___cdecl_unsigned_short_const____::function_void___cdecl_unsigned_short_const______lambda_18dd57a0207f0508aef7a3d88714587b__0_(
                        v66,
                        &v56);
                WlanSyncTaskWlanToCDS::PushCloudChangePerStoreForGeneration(*v15, v26);
              }
              if ( v47[0] == v47[1] )
              {
                std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::_Emplace_reallocate<Windows::Internal::WiFiCloudStore::SyncNeededProfile const &>(
                  &v46,
                  v47[0],
                  v13);
              }
              else
              {
                Windows::Internal::WiFiCloudStore::SyncNeededProfile::SyncNeededProfile(v47[0], v13);
                v47[0] = (Windows::Internal::WiFiCloudStore::SyncNeededProfile *)((char *)v47[0] + 48);
              }
              Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(
                (unsigned int)v69,
                532 * IsMember + (_DWORD)pMemory + 8,
                *((_DWORD *)v13 + 10),
                *v15,
                *(__int64 *)v34);
            }
            else
            {
              v41 = 6;
              v40 = 0;
              v39 = 0;
              v38 = 0;
              v36 = 0;
              v23 = v69;
              if ( v70 > 7 )
                v23 = (unsigned __int16 **)v69[0];
              v44 = v23;
              WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,unsigned long &,enum WiFiSyncAction>(
                (_DWORD)v4,
                (unsigned int)&v44,
                (_DWORD)v13 + 44,
                (unsigned int)&v36,
                (__int64)&v38,
                (__int64)&v39,
                (__int64)&v40,
                (__int64)&FileTime2,
                (__int64)&v41);
            }
            v28 = Block;
            Block = 0;
            if ( v28 )
              operator delete(v28);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0xC4,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              v24);
            v30 = (const struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *)v43;
            if ( FileTime2.dwLowDateTime < 3 )
            {
              SidToCheck = FileTime2.dwLowDateTime + 1;
              v72 = FileTime1;
              Windows::Internal::WiFiCloudStore::SetRetryCountForProfile(
                (unsigned int)v33 + 400,
                532 * IsMember + (_DWORD)pMemory + 8,
                v43[10],
                v43[11],
                (BYTE *)&SidToCheck);
              v41 = 16;
              v40 = 0;
              v39 = 0;
              v38 = 0;
              v36 = 0;
              v32 = v69;
              if ( v70 > 7 )
                v32 = (unsigned __int16 **)v69[0];
              v44 = v32;
              WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,unsigned long &,enum WiFiSyncAction>(
                (_DWORD)v54,
                (unsigned int)v33 + 128,
                (_DWORD)v30 + 44,
                (unsigned int)v33 + 84,
                (__int64)&v38,
                (__int64)&v39,
                (__int64)&v40,
                (__int64)&FileTime2,
                (__int64)&v41);
            }
            else
            {
              v41 = 15;
              v40 = 0;
              v39 = 0;
              v38 = 0;
              v36 = 0;
              v31 = v69;
              if ( v70 > 7 )
                v31 = (unsigned __int16 **)v69[0];
              v44 = v31;
              WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,unsigned long &,enum WiFiSyncAction>(
                (_DWORD)v54,
                (unsigned int)v33 + 128,
                (_DWORD)v43 + 44,
                (unsigned int)v33 + 84,
                (__int64)&v38,
                (__int64)&v39,
                (__int64)&v40,
                (__int64)&FileTime2,
                (__int64)&v41);
              if ( v47[0] == v47[1] )
              {
                std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::_Emplace_reallocate<Windows::Internal::WiFiCloudStore::SyncNeededProfile const &>(
                  &v46,
                  v47[0],
                  v30);
              }
              else
              {
                Windows::Internal::WiFiCloudStore::SyncNeededProfile::SyncNeededProfile(v47[0], v30);
                v47[0] = (Windows::Internal::WiFiCloudStore::SyncNeededProfile *)((char *)v47[0] + 48);
              }
            }
            v8 = v37;
            v13 = (struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *)v43;
            v4 = v54;
            v3 = v65;
          }
          std::wstring::~wstring(v69);
        }
        else
        {
          v19 = v69;
          if ( v70 > 7 )
            v19 = (unsigned __int16 **)v69[0];
          v43 = (int *)v19;
          WiFiCloudStoreTelemetry::ThrottledUploadAttempt<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned long &,_FILETIME const &,_FILETIME &>(
            (unsigned int)&v43,
            (_DWORD)v13 + 44,
            (unsigned int)&FileTime2,
            (unsigned int)&FileTime1,
            (__int64)&FileTime2.dwHighDateTime);
          v36 = 17;
          v38 = 0;
          v39 = 0;
          v40 = 0;
          v41 = 0;
          v20 = v69;
          if ( v70 > 7 )
            v20 = (unsigned __int16 **)v69[0];
          v43 = (int *)v20;
          WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,unsigned long &,enum WiFiSyncAction>(
            (_DWORD)v4,
            (unsigned int)&v43,
            (_DWORD)v13 + 44,
            (unsigned int)&v41,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&FileTime2,
            (__int64)&v36);
          if ( v70 > 7 )
            std::_Deallocate<16>(v69[0], 2 * v70 + 2);
        }
        v13 = (struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *)((char *)v13 + 48);
      }
      wil::details::StoredCallContextInfo::ClearMessage(v3);
      *((_QWORD *)v3 + 2) = 0;
      WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginWiFiCleanup(v4);
      Windows::Internal::WiFiCloudStore::DeleteProcessedProfilesFromRegistry((GUID *)((char *)pMemory
                                                                                    + 532 * (unsigned int)IsMember
                                                                                    + 8));
      if ( v46 )
      {
        std::_Destroy_range<std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>>(v46, v47[0]);
        std::_Deallocate<16>(v46, 16 * (((__int64)v47[1] - v46) >> 4));
        v46 = 0;
        *(_OWORD *)v47 = 0;
      }
      if ( p_pMemory )
      {
        std::_Destroy_range<std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>>(
          p_pMemory,
          ppInterfaceList);
        std::_Deallocate<16>(p_pMemory, 16 * ((v50 - (__int64)p_pMemory) >> 4));
      }
    }
    WlanSyncTaskWlanToCDS::SyncNlmChanges(v4, v8);
    v29 = pMemory;
    pMemory = 0;
    if ( v29 )
      WlanFreeMemory(v29);
    if ( hClientHandle != (HANDLE)-1LL )
      WlanCloseHandle(hClientHandle, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x18001314c  mov     r11, rsp
0x18001314f  mov     [r11+8], rbx
0x180013153  mov     [r11+20h], rsi
0x180013157  push    rdi
0x180013158  push    r12
0x18001315a  push    r13
0x18001315c  push    r14
0x18001315e  push    r15
0x180013160  sub     rsp, 1D0h
0x180013167  mov     rax, cs:__security_cookie
0x18001316e  xor     rax, rsp
0x180013171  mov     [rsp+1F8h+var_38], rax
0x180013179  mov     r14, r8
0x18001317c  mov     rsi, rdx
0x18001317f  mov     [rsp+1F8h+var_120], rdx
0x180013187  mov     [rsp+1F8h+var_C8], r8
0x18001318f  xor     ebx, ebx
0x180013191  mov     [rsp+1F8h+var_130], ebx
0x180013198  mov     qword ptr [r11-170h], 0FFFFFFFFFFFFFFFFh
0x1800131a3  lea     r9, [r11-170h]; phClientHandle
0x1800131aa  lea     r8, [r11-130h]; pdwNegotiatedVersion
0x1800131b1  xor     edx, edx; pReserved
0x1800131b3  lea     ecx, [rbx+2]; dwClientVersion
0x1800131b6  call    cs:__imp_WlanOpenHandle
0x1800131bc  cmp     eax, 426h
0x1800131c1  jnz     short loc_1800131E3
0x1800131c3  mov     rcx, [rsp+1F8h+hClientHandle]; hClientHandle
0x1800131cb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800131cf  jz      short loc_1800131D9
0x1800131d1  xor     edx, edx; pReserved
0x1800131d3  call    cs:__imp_WlanCloseHandle
0x1800131d9  mov     eax, 1
0x1800131de  jmp     loc_180013A5F
0x1800131e3  mov     rcx, [rsp+1F8h]; this
0x1800131eb  test    eax, eax
0x1800131ed  jz      short loc_180013204
0x1800131ef  mov     r9d, eax; char *
0x1800131f2  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800131f9  mov     edx, 47h ; 'G'; void *
0x1800131fe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180013204  mov     [rsp+1F8h+SidToCheck], 201h
0x18001320f  mov     [rsp+1F8h+var_44], 5000000h
0x18001321a  mov     [rsp+1F8h+var_40], 20h ; ' '
0x180013225  mov     [rsp+1F8h+var_3C], 220h
0x180013230  mov     [rsp+1F8h+IsMember], ebx
0x180013234  lea     r8, [rsp+1F8h+IsMember]; IsMember
0x180013239  lea     rdx, [rsp+1F8h+SidToCheck]; SidToCheck
0x180013241  xor     ecx, ecx; TokenHandle
0x180013243  call    cs:__imp_CheckTokenMembership
0x180013249  test    eax, eax
0x18001324b  jnz     short loc_18001326B
0x18001324d  mov     r15b, bl
0x180013250  mov     rcx, [rsp+1F8h]; this
0x180013258  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001325f  mov     edx, 27Ch; void *
0x180013264  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013269  jmp     short loc_180013275
0x18001326b  cmp     [rsp+1F8h+IsMember], ebx
0x18001326f  setnz   r15b
0x180013273  mov     eax, ebx
0x180013275  mov     rcx, [rsp+1F8h]; this
0x18001327d  test    eax, eax
0x18001327f  jns     short loc_180013296
0x180013281  mov     r9d, eax; char *
0x180013284  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001328b  mov     edx, 2C1h; void *
0x180013290  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013296  mov     r8b, r15b; bool
0x180013299  mov     rdx, r14; struct wil::ActivityThreadWatcher *
0x18001329c  mov     rcx, rsi; this
0x18001329f  call    ?BootstrapProfilesIfNeeded@WlanSyncTaskWlanToCDS@@SAXAEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@_N@Z; WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &,bool)
0x1800132a4  mov     [rsp+1F8h+pMemory], rbx
0x1800132a9  lea     rax, [rsp+1F8h+pMemory]
0x1800132ae  mov     [rsp+1F8h+var_150], rax
0x1800132b6  mov     [rsp+1F8h+ppInterfaceList], rbx
0x1800132be  mov     byte ptr [rsp+1F8h+var_140], 1
0x1800132c6  lea     r8, [rsp+1F8h+ppInterfaceList]; ppInterfaceList
0x1800132ce  xor     edx, edx; pReserved
0x1800132d0  mov     rcx, [rsp+1F8h+hClientHandle]; hClientHandle
0x1800132d8  call    cs:__imp_WlanEnumInterfaces
0x1800132de  mov     rcx, [rsp+1F8h]; this
0x1800132e6  test    eax, eax
0x1800132e8  jz      short loc_1800132FF
0x1800132ea  mov     r9d, eax; char *
0x1800132ed  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800132f4  mov     edx, 4Eh ; 'N'; void *
0x1800132f9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800132ff  mov     [rsp+1F8h+var_1A0], r15b
0x180013304  cmp     byte ptr [rsp+1F8h+var_140], bl
0x18001330b  jz      short loc_18001332E
0x18001330d  mov     rdx, [rsp+1F8h+var_150]
0x180013315  mov     rcx, [rdx]; pMemory
0x180013318  mov     rax, [rsp+1F8h+ppInterfaceList]
0x180013320  mov     [rdx], rax
0x180013323  test    rcx, rcx
0x180013326  jz      short loc_18001332E
0x180013328  call    cs:__imp_WlanFreeMemory
0x18001332e  mov     [rsp+1F8h+IsMember], ebx
0x180013332  mov     ecx, ebx
0x180013334  mov     r13, 0AAAAAAAAAAAAAAABh
0x18001333e  mov     rax, [rsp+1F8h+pMemory]
0x180013343  cmp     ecx, [rax]
0x180013345  jnb     loc_180013A25
0x18001334b  imul    rdx, rcx, 214h
0x180013352  add     rax, 8
0x180013356  add     rdx, rax
0x180013359  mov     rcx, rsi
0x18001335c  call    ??$BeginProcessingWiFiRegistry@AEAU_GUID@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXAEAU_GUID@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginProcessingWiFiRegistry<_GUID &>(_GUID &)
0x180013361  mov     eax, [rsp+1F8h+IsMember]
0x180013365  imul    rcx, rax, 214h
0x18001336c  mov     rdx, [rsp+1F8h+pMemory]
0x180013371  add     rdx, 8
0x180013375  add     rdx, rcx
0x180013378  lea     rcx, [rsp+1F8h+var_150]
0x180013380  call    ?GetSyncNeededProfilesFromRegistry@WiFiCloudStore@Internal@Windows@@YA?AV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEBU_GUID@@@Z; Windows::Internal::WiFiCloudStore::GetSyncNeededProfilesFromRegistry(_GUID const &)
0x180013385  nop
0x180013386  mov     rax, [rsp+1F8h+ppInterfaceList]
0x18001338e  sub     rax, [rsp+1F8h+var_150]
0x180013396  sar     rax, 4
0x18001339a  imul    rax, r13
0x18001339e  mov     [rsp+1F8h+var_1A4], eax
0x1800133a2  lea     rdx, [rsp+1F8h+var_1A4]
0x1800133a7  mov     rcx, rsi
0x1800133aa  call    ??$BeginSyncingWiFiChanges@I@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAI@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginSyncingWiFiChanges<uint>(uint &&)
0x1800133af  lea     rcx, [rsp+1F8h+var_168]
0x1800133b7  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x1800133bc  nop
0x1800133bd  mov     rdi, [rsp+1F8h+var_150]
0x1800133c5  mov     rax, [rsp+1F8h+ppInterfaceList]
0x1800133cd  mov     [rsp+1F8h+var_118], rax
0x1800133d5  mov     [rsp+1F8h+var_180], rdi
0x1800133da  cmp     rdi, rax
0x1800133dd  jz      loc_180013945
0x1800133e3  mov     rdx, rdi
0x1800133e6  lea     rcx, [rsp+1F8h+var_68]
0x1800133ee  call    ?CDSReferenceIdToProfileName@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::CDSReferenceIdToProfileName(std::wstring const &)
0x1800133f3  nop
0x1800133f4  lea     r12, [rdi+2Ch]
0x1800133f8  lea     r8, [rsp+1F8h+var_68]
0x180013400  cmp     [rsp+1F8h+var_50], 7
0x180013409  cmova   r8, [rsp+1F8h+var_68]
0x180013412  mov     r9d, [r12]
0x180013416  lea     rdx, aProfileNameWsG_0; "Profile name: %ws, Generation: %d"
0x18001341d  mov     rcx, r14; this
0x180013420  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x180013425  xor     eax, eax
0x180013427  mov     qword ptr [rsp+1F8h+FileTime2.dwLowDateTime], rax
0x18001342f  mov     [rsp+1F8h+var_70], eax
0x180013436  mov     eax, [rsp+1F8h+IsMember]
0x18001343a  imul    rcx, rax, 214h
0x180013441  mov     rdx, [rsp+1F8h+pMemory]
0x180013446  add     rdx, 8
0x18001344a  add     rdx, rcx
0x18001344d  lea     rax, [rsp+1F8h+FileTime2]
0x180013455  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x18001345a  mov     r9d, [r12]
0x18001345e  mov     r8d, [rdi+28h]
0x180013462  lea     rcx, [rsp+1F8h+var_68]
0x18001346a  call    ?TryGetRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEAURetryStatistics@123@@Z; Windows::Internal::WiFiCloudStore::TryGetRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,Windows::Internal::WiFiCloudStore::RetryStatistics *)
0x18001346f  lea     r8, [rsp+1F8h+var_68]
0x180013477  cmp     [rsp+1F8h+var_50], 7
0x180013480  cmova   r8, [rsp+1F8h+var_68]
0x180013489  mov     eax, [rsp+1F8h+FileTime2.dwLowDateTime]
0x180013490  mov     [rsp+1F8h+var_1D8], eax; int
0x180013494  mov     r9d, [r12]
0x180013498  lea     rdx, aProfileNameWsG_2; "Profile name: %ws, Generation: %d, Retr"...
0x18001349f  mov     rcx, r14; this
0x1800134a2  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x1800134a7  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x1800134ac  mov     qword ptr [rsp+1F8h+FileTime1.dwLowDateTime], rax
0x1800134b4  cmp     [rsp+1F8h+FileTime2.dwLowDateTime], 3
0x1800134bc  jbe     short loc_1800134DE
0x1800134be  mov     rcx, [rsp+1F8h]; this
0x1800134c6  mov     r9d, 80070057h; char *
0x1800134cc  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800134d3  mov     edx, 1Ah; void *
0x1800134d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800134de  lea     rdx, [rsp+1F8h+FileTime2.dwHighDateTime]; lpFileTime2
0x1800134e6  lea     rcx, [rsp+1F8h+FileTime1]; lpFileTime1
0x1800134ee  call    cs:__imp_CompareFileTime
0x1800134f4  cmp     eax, 0FFFFFFFFh
0x1800134f7  jz      loc_180013647
0x1800134fd  cmp     [rsp+1F8h+FileTime2.dwLowDateTime], ebx
0x180013504  jz      loc_180013647
0x18001350a  mov     edx, [rsp+1F8h+FileTime2.dwLowDateTime]
0x180013511  lea     rax, asc_180045274+4; ""
0x180013518  mov     rdx, [rax+rdx*8]
0x18001351c  lea     rcx, [rsp+1F8h+FileTime2.dwHighDateTime]
0x180013524  call    ??$add@_J$0A@@filetime@wil@@YA?AU_FILETIME@@AEBU2@_J@Z; wil::filetime::add<__int64,0>(_FILETIME const &,__int64)
0x180013529  mov     qword ptr [rsp+1F8h+var_D0.dwLowDateTime], rax
0x180013531  lea     rdx, [rsp+1F8h+var_D0]; lpFileTime2
0x180013539  lea     rcx, [rsp+1F8h+FileTime1]; lpFileTime1
0x180013541  call    cs:__imp_CompareFileTime
0x180013547  cmp     eax, 1
0x18001354a  jz      loc_180013647
0x180013550  lea     rax, [rsp+1F8h+var_68]
0x180013558  cmp     [rsp+1F8h+var_50], 7
0x180013561  cmova   rax, [rsp+1F8h+var_68]
0x18001356a  mov     [rsp+1F8h+var_180], rax
0x18001356f  lea     rax, [rsp+1F8h+FileTime2.dwHighDateTime]
0x180013577  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x18001357c  lea     r9, [rsp+1F8h+FileTime1]
0x180013584  lea     r8, [rsp+1F8h+FileTime2]
0x18001358c  mov     rdx, r12
0x18001358f  lea     rcx, [rsp+1F8h+var_180]
0x180013594  call    ??$ThrottledUploadAttempt@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEAKAEBU_FILETIME@@AEAU5@@WiFiCloudStoreTelemetry@@SAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEAKAEBU_FILETIME@@AEAU5@@Z; WiFiCloudStoreTelemetry::ThrottledUploadAttempt<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,ulong &,_FILETIME const &,_FILETIME &>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,ulong &,_FILETIME const &,_FILETIME &)
0x180013599  mov     [rsp+1F8h+var_1A4], 11h
0x1800135a1  mov     [rsp+1F8h+var_19C], ebx
0x1800135a5  mov     [rsp+1F8h+var_198], ebx
0x1800135a9  mov     [rsp+1F8h+var_194], ebx
0x1800135ad  mov     [rsp+1F8h+var_190], ebx
0x1800135b1  lea     rax, [rsp+1F8h+var_68]
0x1800135b9  cmp     [rsp+1F8h+var_50], 7
0x1800135c2  cmova   rax, [rsp+1F8h+var_68]
0x1800135cb  mov     [rsp+1F8h+var_180], rax
0x1800135d0  lea     rax, [rsp+1F8h+var_1A4]
0x1800135d5  mov     [rsp+1F8h+var_1B8], rax
0x1800135da  lea     rax, [rsp+1F8h+FileTime2]
0x1800135e2  mov     [rsp+1F8h+var_1C0], rax
0x1800135e7  lea     rax, [rsp+1F8h+var_19C]
0x1800135ec  mov     [rsp+1F8h+var_1C8], rax
0x1800135f1  lea     rax, [rsp+1F8h+var_198]
0x1800135f6  mov     [rsp+1F8h+var_1D0], rax
0x1800135fb  lea     rax, [rsp+1F8h+var_194]
0x180013600  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x180013605  lea     r9, [rsp+1F8h+var_190]
0x18001360a  mov     r8, r12
0x18001360d  lea     rdx, [rsp+1F8h+var_180]
0x180013612  mov     rcx, rsi
0x180013615  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@HHHHAEAKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$$QEAH222AEAK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,ulong &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int &&,int &&,int &&,int &&,ulong &,WiFiSyncAction &&)
0x18001361a  nop
0x18001361b  mov     rdx, [rsp+1F8h+var_50]
0x180013623  cmp     rdx, 7
0x180013627  jbe     loc_180013934
0x18001362d  lea     rdx, ds:2[rdx*2]
0x180013635  mov     rcx, [rsp+1F8h+var_68]
0x18001363d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013642  jmp     loc_180013934
0x180013647  lea     rcx, [rsp+1F8h+Block]
0x18001364f  call    ??$GetTokenInformation@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z
0x180013654  nop
0x180013655  cmp     dword ptr [rdi+28h], 1
0x180013659  jz      loc_18001373E
0x18001365f  cmp     dword ptr [rdi+28h], 8
0x180013663  jz      loc_18001373E
0x180013669  lea     r8, [rsp+1F8h+var_68]
0x180013671  cmp     [rsp+1F8h+var_50], 7
0x18001367a  cmova   r8, [rsp+1F8h+var_68]; unsigned __int16 *
0x180013683  mov     eax, [rsp+1F8h+IsMember]
0x180013687  imul    rdx, rax, 214h
0x18001368e  mov     rax, [rsp+1F8h+pMemory]
0x180013693  add     rax, 8
0x180013697  add     rdx, rax; struct _GUID *
0x18001369a  mov     r9b, r15b; bool
0x18001369d  mov     rcx, [rsp+1F8h+Block]; struct _TOKEN_USER *
0x1800136a5  call    ?DoesSidAllowUpdateWithProfileName@WlanSyncTaskCommon@@SA_NAEBU_TOKEN_USER@@AEBU_GUID@@QEBG_N@Z; WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileName(_TOKEN_USER const &,_GUID const &,ushort const * const,bool)
0x1800136aa  test    al, al
0x1800136ac  jnz     loc_18001373E
0x1800136b2  mov     [rsp+1F8h+var_190], 6
0x1800136ba  mov     [rsp+1F8h+var_194], ebx
0x1800136be  mov     [rsp+1F8h+var_198], ebx
0x1800136c2  mov     [rsp+1F8h+var_19C], ebx
0x1800136c6  mov     [rsp+1F8h+var_1A4], ebx
0x1800136ca  lea     rax, [rsp+1F8h+var_68]
0x1800136d2  cmp     [rsp+1F8h+var_50], 7
0x1800136db  cmova   rax, [rsp+1F8h+var_68]
0x1800136e4  mov     [rsp+1F8h+var_178], rax
0x1800136ec  lea     rax, [rsp+1F8h+var_190]
0x1800136f1  mov     [rsp+1F8h+var_1B8], rax
0x1800136f6  lea     rax, [rsp+1F8h+FileTime2]
0x1800136fe  mov     [rsp+1F8h+var_1C0], rax
0x180013703  lea     rax, [rsp+1F8h+var_194]
0x180013708  mov     [rsp+1F8h+var_1C8], rax
0x18001370d  lea     rax, [rsp+1F8h+var_198]
0x180013712  mov     [rsp+1F8h+var_1D0], rax
0x180013717  lea     rax, [rsp+1F8h+var_19C]
0x18001371c  mov     qword ptr [rsp+1F8h+var_1D8], rax
0x180013721  lea     r9, [rsp+1F8h+var_1A4]
0x180013726  mov     r8, r12
0x180013729  lea     rdx, [rsp+1F8h+var_178]
0x180013731  mov     rcx, rsi
0x180013734  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@HHHHAEAKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$$QEAH222AEAK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,ulong &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int &&,int &&,int &&,int &&,ulong &,WiFiSyncAction &&)
0x180013739  jmp     loc_1800138E4
0x18001373e  mov     ecx, [rdi+28h]
0x180013741  lea     eax, [rcx-1]
0x180013744  cmp     eax, 1
0x180013747  jbe     loc_1800137F9
0x18001374d  lea     eax, [rcx-4]
0x180013750  test    eax, 0FFFFFFFBh
0x180013755  jz      short loc_180013771
0x180013757  mov     rcx, [rsp+1F8h]; this
0x18001375f  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180013766  mov     edx, 0AFh; void *
0x18001376b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013771  mov     [rsp+1F8h+var_110], rsi
0x180013779  mov     [rsp+1F8h+var_108], r14
0x180013781  lea     rax, [rsp+1F8h+hClientHandle]
0x180013789  mov     [rsp+1F8h+var_100], rax
0x180013791  lea     rax, [rsp+1F8h+var_68]
0x180013799  mov     [rsp+1F8h+var_F8], rax
  ... truncated ...
```
