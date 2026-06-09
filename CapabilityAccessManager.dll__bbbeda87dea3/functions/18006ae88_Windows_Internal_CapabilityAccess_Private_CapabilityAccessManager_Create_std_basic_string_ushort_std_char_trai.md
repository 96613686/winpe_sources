# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::Create(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18006ae88`
- end: `0x18006c2b6`
- name: `?Create@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@CA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@00KK0$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@0_N@Z`
- size: `5166`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwProcessId, int, __int64, __int64, __int64, char)`
- caller_count: `4`
- callee_count: `74`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006ae88`
- `0x18006c6f4`
- `0x18006c920`
- `0x18006ca84`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x180016450`
- `0x180016490`
- `0x18001649c`
- `0x180017bc4`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001f4c0`
- `0x18001f5f4`
- `0x180020fcc`
- `0x18002392c`
- `0x1800257a4`
- `0x180027ad8`
- `0x180027b60`
- `0x180029304`
- `0x180029408`
- `0x18002c970`
- `0x18002e704`
- `0x18002f240`
- `0x18002f93c`
- `0x18002f978`
- `0x18002f9ac`
- `0x180038894`
- `0x180039e9c`
- `0x18003b518`
- `0x18003e21c`
- `0x18003f4a0`
- `0x18003f6e4`
- `0x18003f97c`
- `0x18003fe80`
- `0x18003ff78`
- `0x18004049c`
- `0x180040788`
- `0x180040d00`
- `0x180040d7c`
- `0x180041e2c`
- `0x180042054`
- `0x180042410`
- `0x180042720`
- `0x1800428a8`
- `0x1800429ac`
- `0x180042c4c`
- `0x180043610`
- `0x1800437d0`
- `0x1800439d4`
- `0x180043a40`
- `0x180043bc8`
- `0x180044874`
- `0x1800448d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18006af70`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18006af70`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006afd0`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006afd0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006b3a9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006b3a9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18006b844`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18006b844`
- `WINTRUST!WTGetSignatureInfo` at `0x18006c08a`
- `WINTRUST!WTGetSignatureInfo` at `0x18006c08a`

## string_xrefs

- `0x18006c1b2`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c1c3`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c1da`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c1f1`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c209`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c21b`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c233`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c248`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c2a3`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006af81`: `user(%ws), cap(%ws), pid(%u), tid(%u), app(%ws), callertoken(%d)`
- `0x18006be55`: `CreateWithCallerIdentity`
- `0x18006b1ae`: `App user sid is '%ws'`
- `0x18006b3ce`: `App package family name updated to '%ws'`
- `0x18006b467`: `App package family name updated to '%ws'`
- `0x18006b310`: `Non-packaged (non-Store) app. AccessCheck functionality will be limited`
- `0x18006b3ef`: `App package full name updated to '%ws'`
- `0x18006b488`: `App package full name updated to '%ws'`
- `0x18006b8e8`: `Target user sid is '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=34 #try_helpers=1
__int64 *__fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::Create(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        DWORD dwProcessId,
        int a6,
        __int64 a7,
        _QWORD *a8,
        __int64 a9,
        char a10)
{
  DWORD v12; // r13d
  int v13; // r15d
  bool *v14; // r8
  unsigned int v15; // eax
  signed int v16; // ebx
  DWORD CallerInfo; // esi
  char v18; // bl
  unsigned int v19; // edx
  bool IsShellExperienceApp; // cl
  _QWORD *v21; // rcx
  __int64 UserSidStringFromToken; // rax
  __int64 ProcessTokenFromProcessId; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 PackageFamilyNameFromToken; // rax
  __int64 PackageFullNameFromToken; // rax
  __int64 v28; // rsi
  __int64 v29; // rdx
  char *v30; // rcx
  const char *v31; // r9
  __int64 v32; // r14
  __int64 PackageFullNameFromFamilyNameAndUser; // rax
  char HasOneOrMoreAppSilos; // cl
  __int64 v35; // rcx
  __int64 v36; // r14
  __int64 v37; // r8
  __int64 v38; // rdx
  Windows::Internal::CapabilityAccess::Private *v39; // rcx
  __int64 v40; // rdx
  int PackageComplianceClassification; // eax
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 *v48; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // rdx
  std::_Ref_count_base *v52; // rcx
  char IsEnabled; // al
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 AdjustedUserSidString; // rax
  DWORD v57; // r12d
  Windows::Internal::CapabilityAccess::Private *v58; // rcx
  unsigned int v59; // edx
  __int64 v60; // rcx
  __int64 v61; // rax
  std::_Ref_count_base *v62; // rsi
  std::_Ref_count_base *v63; // r14
  __int64 v64; // rax
  int v65; // ebx
  unsigned int v66; // edx
  char v67; // al
  _QWORD *v68; // rcx
  __int64 v69; // rcx
  int v70; // ebx
  const unsigned __int16 *v71; // rax
  const unsigned __int16 *v72; // rdx
  __int64 v73; // rax
  bool v74; // zf
  const char *v75; // r9
  __int64 v76; // rax
  std::_Ref_count_base **p_TokenInformation; // rcx
  bool v78; // bl
  __int64 v79; // rbx
  __int64 ImageFullPathFromProcessId; // rax
  __int64 v81; // r8
  __int64 v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rdx
  char v88; // si
  int v89; // ebx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // r14
  __int64 v93; // r12
  __int64 v94; // r13
  __int64 v95; // rsi
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 v99; // rbx
  DWORD *v100; // rax
  _QWORD *v101; // rax
  _QWORD *v102; // rdx
  __int64 v103; // rdx
  __int64 v104; // rax
  DWORD v105; // ebx
  __int64 v106; // rax
  __int64 v107; // rax
  int v108; // eax
  bool v109; // cl
  __int64 v110; // rcx
  const char *v112; // r9
  unsigned int v113; // eax
  DWORD *ReturnLength; // [rsp+20h] [rbp-208h]
  _BYTE v115[4]; // [rsp+54h] [rbp-1D4h] BYREF
  DWORD v116[2]; // [rsp+58h] [rbp-1D0h] BYREF
  DWORD v117; // [rsp+60h] [rbp-1C8h]
  char v118; // [rsp+64h] [rbp-1C4h]
  Windows::Internal::CapabilityAccess::Private *v119; // [rsp+68h] [rbp-1C0h] BYREF
  int v120[2]; // [rsp+70h] [rbp-1B8h] BYREF
  int v121[2]; // [rsp+78h] [rbp-1B0h]
  int v122; // [rsp+80h] [rbp-1A8h]
  __int64 v123; // [rsp+88h] [rbp-1A0h]
  __int64 v124; // [rsp+90h] [rbp-198h]
  __int64 *v125; // [rsp+98h] [rbp-190h]
  __int64 v126; // [rsp+A0h] [rbp-188h]
  std::_Ref_count_base *v127[2]; // [rsp+A8h] [rbp-180h] BYREF
  __int128 v128; // [rsp+B8h] [rbp-170h]
  std::_Ref_count_base **v129; // [rsp+C8h] [rbp-160h] BYREF
  std::_Ref_count_base *v130; // [rsp+D0h] [rbp-158h]
  __int64 TokenInformation; // [rsp+E8h] [rbp-140h] BYREF
  std::_Ref_count_base *v132; // [rsp+F0h] [rbp-138h]
  __int64 v133; // [rsp+108h] [rbp-120h] BYREF
  std::_Ref_count_base *v134; // [rsp+110h] [rbp-118h]
  _BYTE v135[32]; // [rsp+128h] [rbp-100h] BYREF
  _BYTE v136[40]; // [rsp+148h] [rbp-E0h] BYREF
  int RpcCallAttributes; // [rsp+170h] [rbp-B8h] BYREF
  _BYTE v138[48]; // [rsp+174h] [rbp-B4h] BYREF
  int v139; // [rsp+1A4h] [rbp-84h]
  int v140; // [rsp+1C4h] [rbp-64h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  *(_QWORD *)v120 = a3;
  *(_QWORD *)v121 = a2;
  v124 = a9;
  v125 = a1;
  v126 = a3;
  v12 = dwProcessId;
  v117 = dwProcessId;
  LODWORD(v119) = dwProcessId;
  v122 = a6;
  v123 = a7;
  v118 = a10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
  }
  std::make_shared<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager,>(a1);
  v13 = 1;
  *(_DWORD *)(*a1 + 424) = rand();
  std::wstring::wstring(v127, L"user(%ws), cap(%ws), pid(%u), tid(%u), app(%ws), callertoken(%d)");
  std::wstring::_Tidy_deallocate(v127);
  if ( a10 )
  {
    memset_0(v138, 0, 0x6Cu);
    RpcCallAttributes = 2;
    v15 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
    v16 = v15;
    if ( v15 )
    {
      if ( v15 != 1725 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids, v15);
        }
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        v112 = (const char *)(unsigned int)wil::verify_hresult<long>((unsigned int)v16);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          v112,
          (int)ReturnLength);
      }
      *(_BYTE *)(*a1 + 35) = 0;
    }
    *(_BYTE *)(*a1 + 35) = v139 != 0;
    if ( *(_BYTE *)(*a1 + 35) )
      *(_BYTE *)(*a1 + 33) = 1;
  }
  else
  {
    *(_BYTE *)(*a1 + 35) = 0;
  }
  if ( ((*a8 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && !*(_BYTE *)(*a1 + 35) )
  {
    v115[0] = 0;
    CallerInfo = Windows::Internal::CapabilityAccess::Private::GetCallerInfo(
                   (Windows::Internal::CapabilityAccess::Private *)v115,
                   0,
                   v14);
    v18 = v115[0];
    if ( v115[0] )
    {
      std::wstring::wstring(v127, L"Caller is AppContainer. Override process id. old(%u), new(%u)");
      std::wstring::_Tidy_deallocate(v127);
      v12 = CallerInfo;
      v117 = CallerInfo;
      LODWORD(v119) = CallerInfo;
    }
    std::wstring::wstring(v127, L"Caller pid(%u)");
    std::wstring::_Tidy_deallocate(v127);
    if ( v18 )
      IsShellExperienceApp = Windows::Internal::CapabilityAccess::Private::IsShellExperienceApp(
                               (Windows::Internal::CapabilityAccess::Private *)CallerInfo,
                               v19);
    else
      IsShellExperienceApp = 1;
    *(_BYTE *)(*a1 + 33) = IsShellExperienceApp;
  }
  *(_DWORD *)(*a1 + 48) = v12;
  *(_DWORD *)(*a1 + 52) = v122;
  if ( (unsigned __int64)(*a8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_BYTE *)(*a1 + 33) = Windows::Internal::CapabilityAccess::Private::IsShellExperienceApp(a8);
    v21 = (_QWORD *)(*a1 + 448);
    *(_QWORD *)v116 = *v21;
    *v21 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      v21,
      a8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a8,
      v116);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v116);
LABEL_22:
    UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v127, *a1 + 448);
    std::wstring::operator=(*a1 + 232, UserSidStringFromToken);
    std::wstring::_Tidy_deallocate(v127);
    goto LABEL_25;
  }
  if ( v12 )
  {
    ProcessTokenFromProcessId = Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(
                                  (PHANDLE)v116,
                                  v12);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      *a1 + 448,
      ProcessTokenFromProcessId);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v116);
    goto LABEL_22;
  }
LABEL_25:
  std::wstring::wstring(v127, L"IsCallerShellExperienceApp: %d");
  std::wstring::_Tidy_deallocate(v127);
  std::wstring::wstring(v127, L"App user sid is '%ws'");
  std::wstring::_Tidy_deallocate(v127);
  v25 = *(_QWORD *)(*a1 + 448);
  if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LODWORD(TokenInformation) = 196611;
    *(_QWORD *)v116 = 0;
    v129 = 0;
    ReturnLength = v116;
    AppModelPolicy_GetPolicy_Internal(v25, v24, &TokenInformation, &v129);
    *(_DWORD *)(*a1 + 44) = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AppModelPolicyValueToCAMWindowingModel((unsigned int)TokenInformation);
    *(_DWORD *)(*a1 + 24) = Windows::Internal::CapabilityAccess::Private::GetAppExecutionContext(*a1 + 448);
  }
  std::wstring::wstring(v127, L"App windowing model is %u");
  std::wstring::_Tidy_deallocate(v127);
  std::wstring::wstring(v127, L"AppExecutionContext(%d)");
  std::wstring::_Tidy_deallocate(v127);
  if ( (unsigned __int64)(*(_QWORD *)(*a1 + 448) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v32 = v123;
    v28 = *(_QWORD *)v121;
    PackageFullNameFromFamilyNameAndUser = Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(
                                             v127,
                                             *(_QWORD *)v121,
                                             v123);
    std::wstring::operator=(*a1 + 200, PackageFullNameFromFamilyNameAndUser);
    std::wstring::_Tidy_deallocate(v127);
    std::wstring::operator=(*a1 + 168, v32);
    std::wstring::wstring(v127, L"App package family name updated to '%ws'");
    std::wstring::_Tidy_deallocate(v127);
    std::wstring::wstring(v127, L"App package full name updated to '%ws'");
    std::wstring::_Tidy_deallocate(v127);
    *(_BYTE *)(*a1 + 36) = 1;
  }
  else
  {
    PackageFamilyNameFromToken = Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromToken(v127);
    std::wstring::operator=(*a1 + 168, PackageFamilyNameFromToken);
    std::wstring::_Tidy_deallocate(v127);
    PackageFullNameFromToken = Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromToken(
                                 v127,
                                 *a1 + 448);
    std::wstring::operator=(*a1 + 200, PackageFullNameFromToken);
    std::wstring::_Tidy_deallocate(v127);
    if ( *(_QWORD *)(*a1 + 184) )
    {
      if ( *(_DWORD *)(*a1 + 24) != 2 )
      {
        std::wstring::wstring(v127, L"App package family name updated to '%ws'");
        std::wstring::_Tidy_deallocate(v127);
        std::wstring::wstring(v127, L"App package full name updated to '%ws'");
        std::wstring::_Tidy_deallocate(v127);
        *(_BYTE *)(*a1 + 36) = 1;
      }
    }
    else
    {
      std::wstring::wstring(v127, L"Non-packaged (non-Store) app. AccessCheck functionality will be limited");
      std::wstring::_Tidy_deallocate(v127);
      *(_BYTE *)(*a1 + 36) = 0;
    }
    v28 = *(_QWORD *)v121;
  }
  std::wstring::wstring(v127, L"PackagedApp(%d)");
  std::wstring::_Tidy_deallocate(v127);
  v29 = *a1;
  if ( *(_BYTE *)(*a1 + 36) )
  {
    v30 = *(char **)(v29 + 448);
    if ( (unsigned __int64)(v30 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v35 = v29 + 232;
      if ( *(_QWORD *)(v28 + 16) )
        v35 = v28;
      HasOneOrMoreAppSilos = Windows::Internal::CapabilityAccess::Private::PackageFamilyHasOneOrMoreAppSilos(
                               v35,
                               v29 + 168);
    }
    else
    {
      LODWORD(TokenInformation) = 0;
      v116[0] = 0;
      if ( !GetTokenInformation(v30, TokenAppContainerNumber|TokenAuditPolicy, &TokenInformation, 4u, v116) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1E9,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          v31);
      HasOneOrMoreAppSilos = (_DWORD)TokenInformation != 0;
    }
    *(_BYTE *)(*a1 + 29) = HasOneOrMoreAppSilos;
  }
  v36 = *(_QWORD *)v120;
  std::wstring::operator=(*a1 + 296, *(_QWORD *)v120);
  std::wstring::operator=(*a1 + 264, a4);
  v37 = *a1;
  if ( *(_BYTE *)(*a1 + 36) )
  {
    v38 = v37 + 232;
    if ( *(_QWORD *)(v28 + 16) )
      v38 = v28;
    Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::InvalidateUnknownPackageComplianceClassification(
      v37 + 168,
      v38);
    if ( Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::GetEnforceRestrictedExceptions()
      && !Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(v39) )
    {
      if ( *(_QWORD *)(v28 + 16) )
        v40 = v28;
      else
        v40 = *a1 + 232;
      PackageComplianceClassification = Windows::Internal::CapabilityAccess::Private::GetPackageComplianceClassification(
                                          *a1 + 168,
                                          v40);
      if ( PackageComplianceClassification == 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x202,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)0x8000FFFFLL,
          (int)ReturnLength);
      if ( !PackageComplianceClassification )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)0x8000FFFFLL,
          (int)ReturnLength);
    }
    if ( *(_QWORD *)(v28 + 16) )
      v42 = v28;
    else
      v42 = *a1 + 232;
    v43 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::CreateWithCorrelationId(
            &v129,
            v36,
            *a1 + 424,
            v42);
  }
  else
  {
    v43 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::CreateWithCorrelationId(
            &v129,
            v36,
            v37 + 424);
  }
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*a1 + 96, v43);
  if ( v130 )
    std::_Ref_count_base::_Decref(v130);
  v44 = Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore>>::Instance(&v129);
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*a1 + 112, v44);
  if ( v130 )
    std::_Ref_count_base::_Decref(v130);
  std::wstring::operator=(*a1 + 328, v124);
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(&v133);
  if ( *(_BYTE *)(*a1 + 36) )
  {
    v45 = *a1 + 232;
    if ( *(_QWORD *)(v28 + 16) )
      v45 = v28;
    v46 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v133, &v129, v36, v45);
  }
  else
  {
    v46 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v133, &v129, v36);
  }
  std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager>::operator=(*a1 + 128, v46);
  if ( v130 )
    std::_Ref_count_base::_Decref(v130);
  v47 = *a1;
  if ( *(_QWORD *)(*a1 + 128) && v117 )
  {
    v48 = (__int64 *)std::make_shared<Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo,unsigned long &,std::wstring const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &>(
                       &v129,
                       &v119,
                       v28);
    v49 = *a1;
    v50 = *v48;
    v51 = v48[1];
    *v48 = 0;
    v48[1] = 0;
    *(_QWORD *)(v49 + 80) = v50;
    v52 = *(std::_Ref_count_base **)(v49 + 88);
    *(_QWORD *)(v49 + 88) = v51;
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
    if ( v130 )
      std::_Ref_count_base::_Decref(v130);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl);
    v54 = *a1;
    if ( IsEnabled )
    {
      v55 = *(_QWORD *)(v54 + 80) + 176LL;
    }
    else
    {
      AdjustedUserSidString = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AdjustedUserSidString(*(_QWORD *)(v54 + 80));
      v54 = *a1;
      v55 = AdjustedUserSidString;
    }
    std::wstring::operator=(v54 + 392, v55);
    v57 = (unsigned int)v119;
    v117 = (unsigned int)v119;
  }
  else
  {
    if ( *(_QWORD *)(v28 + 16) )
      std::wstring::operator=(v47 + 392, v28);
    else
      std::wstring::operator=(v47 + 392, v47 + 232);
    v57 = v117;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
  {
    if ( Windows::Internal::CapabilityAccess::Private::IsAsyncSessionSupportEnabled(v58) )
    {
      v60 = *a1;
      if ( *(_QWORD *)(*a1 + 128) )
      {
        v61 = *(_QWORD *)(v60 + 80);
        if ( v61 )
        {
          *(_BYTE *)(v60 + 40) = *(_BYTE *)(v61 + 248);
        }
        else if ( v57 )
        {
          *(_BYTE *)(*a1 + 40) = Windows::Internal::CapabilityAccess::Private::IsAgenticSession(
                                   (Windows::Internal::CapabilityAccess::Private *)v57,
                                   v59);
        }
        else
        {
          Windows::Internal::CapabilityAccess::Private::GetAllSessionIds(v127);
          v62 = v127[0];
          v63 = v127[1];
          while ( v62 != v63 )
          {
            *(_QWORD *)v116 = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              v116,
              0);
            if ( (int)UMgrGetSessionActiveShellUserToken(*(unsigned int *)v62, v116) >= 0 )
            {
              v64 = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(&v129, v116);
              v65 = std::wstring::compare(*(_QWORD *)v121, v64);
              std::wstring::_Tidy_deallocate(&v129);
              if ( !v65 )
              {
                *(_BYTE *)(*a1 + 40) = Windows::Internal::CapabilityAccess::Private::IsAgenticSession(
                                         (Windows::Internal::CapabilityAccess::Private *)*(unsigned int *)v62,
                                         v66);
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v116);
                v67 = 0;
                goto LABEL_96;
              }
            }
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v116);
            v62 = (std::_Ref_count_base *)((char *)v62 + 4);
          }
          v67 = 1;
LABEL_96:
          if ( v67 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x27C,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
              (const char *)0x8000FFFFLL,
              (int)ReturnLength);
          if ( v127[0] )
            std::_Deallocate<16>(v127[0], (v128 - (unsigned __int64)v127[0]) & 0xFFFFFFFFFFFFFFFCuLL);
          v36 = *(_QWORD *)v120;
        }
      }
    }
  }
  std::wstring::wstring(v127, L"Target user sid is '%ws'");
  std::wstring::_Tidy_deallocate(v127);
  v68 = (_QWORD *)(*a1 + 448);
  if ( (unsigned __int64)(*v68 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    Windows::Internal::CapabilityAccess::Private::GetUserTokenFromSidString(v116, *a1 + 392);
    if ( (unsigned __int64)(*(_QWORD *)v116 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
      }
      v113 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x29F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)v113,
        (int)ReturnLength);
    }
    *(_BYTE *)(*a1 + 41) = Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(v116, 11);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v116);
  }
  else
  {
    *(_BYTE *)(*a1 + 41) = Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(v68, 11);
    if ( !*(_BYTE *)(*a1 + 41) )
      *(_BYTE *)(*a1 + 41) = Windows::Internal::CapabilityAccess::Private::TokenContainsGroup(*a1 + 448);
  }
  std::wstring::wstring(v127, L"InteractiveUser(%d)");
  std::wstring::_Tidy_deallocate(v127);
  v69 = *a1;
  if ( !*(_BYTE *)(*a1 + 36) )
  {
    if ( (unsigned int)(*(_DWORD *)(v69 + 24) - 1) <= 1 )
    {
      *(_BYTE *)(v69 + 34) = 0;
      goto LABEL_125;
    }
    v73 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
    v74 = (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                             v73,
                             *(_QWORD *)(v36 + 16),
                             L"microphone",
                             10) == 0;
    v76 = *a1;
    if ( v74 )
    {
      if ( (unsigned __int64)(*(_QWORD *)(v76 + 448) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x2CE,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          v75);
      std::wstring::wstring(v127, L"runFullTrust");
      *(_BYTE *)(*a1 + 34) = Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(*a1 + 448, v127);
      p_TokenInformation = v127;
    }
    else
    {
      *(_BYTE *)(v76 + 34) = 1;
      if ( (unsigned __int64)(*(_QWORD *)(*a1 + 448) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL || !v57 )
        goto LABEL_125;
      std::wstring::wstring(v127, L"runFullTrust");
      v78 = !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(*a1 + 448, v127)
         && !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(*a1 + 448, v36);
      v13 = 1;
      std::wstring::_Tidy_deallocate(v127);
      if ( !v78 )
        goto LABEL_125;
      v129 = v127;
      v79 = std::wstring::wstring(v127, v36);
      ImageFullPathFromProcessId = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                                     &TokenInformation,
                                     v57);
      CapabilityAccessTelemetry::LogLowILCapabilityFailure(ImageFullPathFromProcessId, v79);
      p_TokenInformation = (std::_Ref_count_base **)&TokenInformation;
    }
    std::wstring::_Tidy_deallocate(p_TokenInformation);
    goto LABEL_125;
  }
  v70 = v69 + 232;
  if ( !*(_QWORD *)(v69 + 248) )
    v70 = v69 + 392;
  v115[0] = 0;
  std::wstring::wstring(v127, L"runFullTrust");
  *(_BYTE *)(*a1 + 34) = Windows::Internal::CapabilityAccess::Private::PackageFamilyHasCapability(
                           v70,
                           *(_DWORD *)a1 + 168,
                           (unsigned int)v127,
                           0,
                           0);
  std::wstring::_Tidy_deallocate(v127);
  if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::PackageFamilyHasCapability(
                          v70,
                          *(_DWORD *)a1 + 168,
                          v36,
                          0,
                          (__int64)v115)
    && v115[0] )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
    v71 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1 + 168);
    LogNonDeclarativeApplication(v71, v72);
  }
LABEL_125:
  std::wstring::wstring(v127, L"Full Trust App (%d)");
  std::wstring::_Tidy_deallocate(v127);
  v82 = *(_QWORD *)(*a1 + 128);
  if ( v82 )
  {
    v83 = *(_QWORD *)(v82 + 360);
    if ( v83 != *(_QWORD *)(v82 + 368) )
    {
      std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
        &TokenInformation,
        v83);
      v84 = TokenInformation;
      if ( TokenInformation )
      {
        Windows::Internal::CapabilityAccess::Private::CLSIDToString((LPOLESTR *)v116, (IID *)(TokenInformation + 20));
        std::wstring::wstring(v127, L"Capability handler found: %ws");
        std::wstring::_Tidy_deallocate(v127);
        v85 = Windows::Internal::CapabilityAccess::Private::CapabilityHandler::get_AccessCheck(v84, &v129);
        Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(*a1 + 64, v85);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v129);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v116);
      }
      if ( v132 )
        std::_Ref_count_base::_Decref(v132);
    }
    v86 = *a1;
    if ( *(_BYTE *)(*a1 + 33) )
      *(_DWORD *)(v86 + 56) = *(_DWORD *)(*(_QWORD *)(v86 + 128) + 136LL);
    else
      *(_DWORD *)(v86 + 56) = 0;
  }
  v87 = *a1;
  v88 = *(_BYTE *)(*a1 + 29);
  if ( v88 )
  {
    v89 = 2 - (*(_BYTE *)(v87 + 36) != 0);
    v129 = v127;
    if ( *(_BYTE *)(v87 + 36) )
    {
      v90 = std::wstring::wstring(v135, v87 + 168);
      v13 = 5;
    }
    else
    {
      v90 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
              v136,
              *(unsigned int *)(v87 + 48));
      v13 = 9;
    }
    *(_OWORD *)v127 = 0;
    v128 = 0u;
    *(_OWORD *)v127 = *(_OWORD *)v90;
    v128 = *(_OWORD *)(v90 + 16);
    *(_QWORD *)(v90 + 16) = 0;
    *(_QWORD *)(v90 + 24) = 7;
    *(_WORD *)v90 = 0;
    std::wstring::wstring(&TokenInformation, v36);
    LogObjectCreation(0, v89, v88);
    if ( (v13 & 8) != 0 )
    {
      v13 &= ~8u;
      std::wstring::_Tidy_deallocate(v136);
    }
    if ( (v13 & 4) != 0 )
    {
      v13 &= ~4u;
      std::wstring::_Tidy_deallocate(v135);
    }
  }
  v91 = *(_QWORD *)(*a1 + 128);
  if ( v91 )
  {
    v92 = *(_QWORD *)(v91 + 432);
    v93 = *(_QWORD *)(v91 + 440);
    v94 = *(_QWORD *)v120;
    while ( v92 != v93 )
    {
      v95 = 0;
      *(_QWORD *)v120 = 0;
      v96 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v124);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v96,
                              *(_QWORD *)(v97 + 16),
                              L"CreateWithCallerIdentity",
                              24) )
      {
        v98 = Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(&v129);
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          v120,
          v98);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v129);
        v95 = *(_QWORD *)v120;
      }
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequiredCapabilityCircularDependencyRecursiveCheck(
        v94,
        v92,
        &v133);
      v99 = *a1;
      if ( (unsigned __int64)(v95 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        *(_QWORD *)v116 = 0;
        v100 = v116;
        v13 |= 0x20u;
      }
      else
      {
        TokenInformation = v95;
        *(_QWORD *)v120 = 0;
        v100 = (DWORD *)&TokenInformation;
        v13 |= 0x10u;
      }
      v101 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::Create(
                         (int)v127,
                         v121[0],
                         v92,
                         v94,
                         v117,
                         v122,
                         v123,
                         (__int64)v100,
                         v124,
                         v118);
      v102 = *(_QWORD **)(v99 + 152);
      if ( v102 == *(_QWORD **)(v99 + 160) )
      {
        std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>>::_Emplace_reallocate<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>>(
          v99 + 144,
          v102,
          v101);
      }
      else
      {
        *v102 = 0;
        v102[1] = 0;
        *v102 = *v101;
        v102[1] = v101[1];
        *v101 = 0;
        v101[1] = 0;
        *(_QWORD *)(v99 + 152) += 16LL;
      }
      if ( v127[1] )
        std::_Ref_count_base::_Decref(v127[1]);
      if ( (v13 & 0x20) != 0 )
      {
        v13 &= ~0x20u;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v116);
      }
      if ( (v13 & 0x10) != 0 )
      {
        v13 &= ~0x10u;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenInformation);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v120);
      v92 += 32;
    }
  }
  v103 = *a1;
  v104 = *(_QWORD *)(*a1 + 128);
  if ( v104 && *(_BYTE *)(v104 + 60) )
  {
    if ( *(_BYTE *)(v103 + 36) )
    {
      v110 = v103 + 232;
      if ( !*(_QWORD *)(v103 + 248) )
        v110 = v103 + 392;
      v109 = (unsigned int)Windows::Internal::CapabilityAccess::Private::GetPackageOriginFromFamilyNameAndUser(
                             v110,
                             v103 + 168) == 2;
    }
    else
    {
      LOBYTE(v103) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
        v103);
      v105 = v117;
      if ( !v117 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32E,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)0x80070057LL,
          (int)ReturnLength);
      memset_0(v138, 0, 0x54u);
      RpcCallAttributes = 88;
      v106 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(v135, v105);
      v107 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106);
      v108 = WTGetSignatureInfo(v107, -1, 2049, &RpcCallAttributes);
      if ( v108 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x337,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)(unsigned int)v108,
          0);
      std::wstring::_Tidy_deallocate(v135);
      v109 = v140 != 0;
    }
    *(_BYTE *)(*a1 + 28) = v109;
  }
  LOBYTE(v81) = 3;
  LOBYTE(v103) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
    v103,
    v81);
  if ( *(_BYTE *)(*a1 + 36) )
    *(_QWORD *)(*a1 + 432) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::GetAppCategoryForPackage(*a1 + 200);
  if ( v134 )
    std::_Ref_count_base::_Decref(v134);
  return a1;
}

```

## disassembly

```asm
0x18006ae88  push    rbx
0x18006ae8a  push    rsi
0x18006ae8b  push    rdi
0x18006ae8c  push    r12
0x18006ae8e  push    r13
0x18006ae90  push    r14
0x18006ae92  push    r15
0x18006ae94  sub     rsp, 1F0h
0x18006ae9b  mov     rax, cs:__security_cookie
0x18006aea2  xor     rax, rsp
0x18006aea5  mov     [rsp+228h+var_48], rax
0x18006aead  mov     r12, r9
0x18006aeb0  mov     qword ptr [rsp+228h+var_1B8], r8
0x18006aeb5  mov     qword ptr [rsp+228h+var_1B0], rdx
0x18006aeba  mov     rdi, rcx
0x18006aebd  mov     rax, [rsp+228h+arg_40]
0x18006aec5  mov     [rsp+228h+var_198], rax
0x18006aecd  mov     r14, [rsp+228h+arg_38]
0x18006aed5  mov     [rsp+228h+var_190], rcx
0x18006aedd  mov     [rsp+228h+var_188], r8
0x18006aee5  mov     r13d, [rsp+228h+dwProcessId]
0x18006aeed  mov     [rsp+228h+var_1C8], r13d
0x18006aef2  mov     dword ptr [rsp+228h+var_1C0], r13d
0x18006aef7  mov     eax, [rsp+228h+arg_28]
0x18006aefe  mov     [rsp+228h+var_1A8], eax
0x18006af05  mov     rax, [rsp+228h+arg_30]
0x18006af0d  mov     [rsp+228h+var_1A0], rax
0x18006af15  mov     bl, [rsp+228h+arg_48]
0x18006af1c  mov     [rsp+228h+var_1C4], bl
0x18006af20  mov     [rsp+228h+var_1D8], 1
0x18006af28  lea     rax, WPP_GLOBAL_Control
0x18006af2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006af36  cmp     rcx, rax
0x18006af39  jz      short loc_18006AF5C
0x18006af3b  test    byte ptr [rcx+1Ch], 1
0x18006af3f  jz      short loc_18006AF5C
0x18006af41  cmp     byte ptr [rcx+19h], 5
0x18006af45  jb      short loc_18006AF5C
0x18006af47  mov     edx, 0Bh
0x18006af4c  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x18006af53  mov     rcx, [rcx+10h]
0x18006af57  call    WPP_SF_
0x18006af5c  mov     rcx, rdi
0x18006af5f  call    ??$make_shared@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@$$V@std@@YA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@0@XZ; std::make_shared<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager,>(void)
0x18006af64  nop
0x18006af65  mov     r15d, 1
0x18006af6b  mov     [rsp+228h+var_1D8], r15d
0x18006af70  call    cs:__imp_rand
0x18006af76  mov     ecx, eax
0x18006af78  mov     rax, [rdi]
0x18006af7b  mov     [rax+1A8h], ecx
0x18006af81  lea     rdx, aUserWsCapWsPid; "user(%ws), cap(%ws), pid(%u), tid(%u), "...
0x18006af88  lea     rcx, [rsp+228h+var_180]
0x18006af90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006af95  lea     rcx, [rsp+228h+var_180]
0x18006af9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006afa2  xor     esi, esi
0x18006afa4  test    bl, bl
0x18006afa6  jz      short loc_18006B00D
0x18006afa8  xor     edx, edx; Val
0x18006afaa  lea     r8d, [r15+6Bh]; Size
0x18006afae  lea     rcx, [rsp+228h+var_B4]; void *
0x18006afb6  call    memset_0
0x18006afbb  mov     [rsp+228h+RpcCallAttributes], 2
0x18006afc6  lea     rdx, [rsp+228h+RpcCallAttributes]; RpcCallAttributes
0x18006afce  xor     ecx, ecx; ClientBinding
0x18006afd0  call    cs:__imp_RpcServerInqCallAttributesW
0x18006afd6  mov     ebx, eax
0x18006afd8  test    eax, eax
0x18006afda  jz      short loc_18006AFEE
0x18006afdc  cmp     eax, 6BDh
0x18006afe1  jnz     loc_18006C15C
0x18006afe7  mov     rax, [rdi]
0x18006afea  mov     [rax+23h], sil
0x18006afee  cmp     [rsp+228h+var_84], esi
0x18006aff5  setnz   cl
0x18006aff8  mov     rax, [rdi]
0x18006affb  mov     [rax+23h], cl
0x18006affe  mov     rax, [rdi]
0x18006b001  cmp     [rax+23h], sil
0x18006b005  jz      short loc_18006B014
0x18006b007  mov     byte ptr [rax+21h], 1
0x18006b00b  jmp     short loc_18006B014
0x18006b00d  mov     rax, [rdi]
0x18006b010  mov     [rax+23h], sil
0x18006b014  mov     rax, [r14]
0x18006b017  inc     rax
0x18006b01a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006b020  jnz     loc_18006B0B4
0x18006b026  mov     rax, [rdi]
0x18006b029  cmp     [rax+23h], sil
0x18006b02d  jnz     loc_18006B0B4
0x18006b033  mov     [rsp+228h+var_1D4], sil
0x18006b038  xor     edx, edx; bool *
0x18006b03a  lea     rcx, [rsp+228h+var_1D4]; this
0x18006b03f  call    ?GetCallerInfo@Private@CapabilityAccess@Internal@Windows@@YAKPEA_N0@Z; Windows::Internal::CapabilityAccess::Private::GetCallerInfo(bool *,bool *)
0x18006b044  mov     esi, eax
0x18006b046  mov     bl, [rsp+228h+var_1D4]
0x18006b04a  test    bl, bl
0x18006b04c  jz      short loc_18006B07A
0x18006b04e  lea     rdx, aCallerIsAppcon; "Caller is AppContainer. Override proces"...
0x18006b055  lea     rcx, [rsp+228h+var_180]
0x18006b05d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b062  lea     rcx, [rsp+228h+var_180]
0x18006b06a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b06f  mov     r13d, esi
0x18006b072  mov     [rsp+228h+var_1C8], esi
0x18006b076  mov     dword ptr [rsp+228h+var_1C0], esi
0x18006b07a  lea     rdx, aCallerPidU; "Caller pid(%u)"
0x18006b081  lea     rcx, [rsp+228h+var_180]
0x18006b089  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b08e  lea     rcx, [rsp+228h+var_180]
0x18006b096  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b09b  test    bl, bl
0x18006b09d  jz      short loc_18006B0AA
0x18006b09f  mov     ecx, esi; this
0x18006b0a1  call    ?IsShellExperienceApp@Private@CapabilityAccess@Internal@Windows@@YA_NK@Z; Windows::Internal::CapabilityAccess::Private::IsShellExperienceApp(ulong)
0x18006b0a6  mov     cl, al
0x18006b0a8  jmp     short loc_18006B0AC
0x18006b0aa  mov     cl, 1
0x18006b0ac  mov     rax, [rdi]
0x18006b0af  mov     [rax+21h], cl
0x18006b0b2  xor     esi, esi
0x18006b0b4  mov     rax, [rdi]
0x18006b0b7  mov     [rax+30h], r13d
0x18006b0bb  mov     rax, [rdi]
0x18006b0be  mov     ecx, [rsp+228h+var_1A8]
0x18006b0c5  mov     [rax+34h], ecx
0x18006b0c8  mov     rax, [r14]
0x18006b0cb  dec     rax
0x18006b0ce  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b0d2  ja      short loc_18006B152
0x18006b0d4  mov     rcx, r14
0x18006b0d7  call    ?IsShellExperienceApp@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::IsShellExperienceApp(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18006b0dc  mov     dl, al
0x18006b0de  mov     rax, [rdi]
0x18006b0e1  mov     [rax+21h], dl
0x18006b0e4  mov     rcx, [rdi]
0x18006b0e7  add     rcx, 1C0h
0x18006b0ee  mov     rax, [rcx]
0x18006b0f1  mov     qword ptr [rsp+228h+var_1D0], rax
0x18006b0f6  mov     [rcx], rsi
0x18006b0f9  mov     rdx, r14
0x18006b0fc  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006b101  lea     rdx, [rsp+228h+var_1D0]
0x18006b106  mov     rcx, r14
0x18006b109  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006b10e  lea     rcx, [rsp+228h+var_1D0]
0x18006b113  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b118  mov     esi, 1C0h
0x18006b11d  mov     rdx, [rdi]
0x18006b120  add     rdx, rsi
0x18006b123  lea     rcx, [rsp+228h+var_180]
0x18006b12b  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18006b130  mov     rcx, [rdi]
0x18006b133  mov     ebx, 0E8h
0x18006b138  add     rcx, rbx
0x18006b13b  mov     rdx, rax
0x18006b13e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b143  lea     rcx, [rsp+228h+var_180]
0x18006b14b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b150  jmp     short loc_18006B18D
0x18006b152  test    r13d, r13d
0x18006b155  jz      short loc_18006B183
0x18006b157  mov     edx, r13d; dwProcessId
0x18006b15a  lea     rcx, [rsp+228h+var_1D0]; phNewToken
0x18006b15f  call    ?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)
0x18006b164  mov     rcx, [rdi]
0x18006b167  mov     esi, 1C0h
0x18006b16c  add     rcx, rsi
0x18006b16f  mov     rdx, rax
0x18006b172  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006b177  lea     rcx, [rsp+228h+var_1D0]
0x18006b17c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b181  jmp     short loc_18006B11D
0x18006b183  mov     esi, 1C0h
0x18006b188  mov     ebx, 0E8h
0x18006b18d  lea     rdx, aIscallershelle; "IsCallerShellExperienceApp: %d"
0x18006b194  lea     rcx, [rsp+228h+var_180]
0x18006b19c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b1a1  lea     rcx, [rsp+228h+var_180]
0x18006b1a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b1ae  lea     rdx, aAppUserSidIsWs; "App user sid is '%ws'"
0x18006b1b5  lea     rcx, [rsp+228h+var_180]
0x18006b1bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b1c2  lea     rcx, [rsp+228h+var_180]
0x18006b1ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b1cf  mov     rax, [rdi]
0x18006b1d2  mov     rcx, [rax+1C0h]
0x18006b1d9  lea     rax, [rcx-1]
0x18006b1dd  xor     r14d, r14d
0x18006b1e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b1e4  ja      short loc_18006B244
0x18006b1e6  mov     dword ptr [rsp+228h+TokenInformation], 30003h
0x18006b1f1  mov     qword ptr [rsp+228h+var_1D0], r14
0x18006b1f6  mov     [rsp+228h+var_160], r14
0x18006b1fe  lea     rax, [rsp+228h+var_1D0]
0x18006b203  mov     [rsp+228h+ReturnLength], rax; int
0x18006b208  lea     r9, [rsp+228h+var_160]
0x18006b210  lea     r8, [rsp+228h+TokenInformation]
0x18006b218  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x18006b21d  mov     ecx, dword ptr [rsp+228h+TokenInformation]
0x18006b224  call    ?AppModelPolicyValueToCAMWindowingModel@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@SA?AW4CAMWindowingModel@2345@W4AppModelPolicy_PolicyValue@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AppModelPolicyValueToCAMWindowingModel(AppModelPolicy_PolicyValue)
0x18006b229  mov     edx, eax
0x18006b22b  mov     rax, [rdi]
0x18006b22e  mov     [rax+2Ch], edx
0x18006b231  mov     rcx, [rdi]
0x18006b234  add     rcx, rsi
0x18006b237  call    ?GetAppExecutionContext@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppExecutionContext@1234@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetAppExecutionContext(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::wstring const &)
0x18006b23c  mov     ecx, eax
0x18006b23e  mov     rax, [rdi]
0x18006b241  mov     [rax+18h], ecx
0x18006b244  lea     rdx, aAppWindowingMo; "App windowing model is %u"
0x18006b24b  lea     rcx, [rsp+228h+var_180]
0x18006b253  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b258  lea     rcx, [rsp+228h+var_180]
0x18006b260  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b265  lea     rdx, aAppexecutionco; "AppExecutionContext(%d)"
0x18006b26c  lea     rcx, [rsp+228h+var_180]
0x18006b274  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b279  lea     rcx, [rsp+228h+var_180]
0x18006b281  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b286  mov     rdx, [rdi]
0x18006b289  add     rdx, 1C0h
0x18006b290  mov     rax, [rdx]
0x18006b293  dec     rax
0x18006b296  lea     rcx, [rsp+228h+var_180]
0x18006b29e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b2a2  ja      loc_18006B41C
0x18006b2a8  call    ?GetPackageFamilyNameFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18006b2ad  mov     rcx, [rdi]
0x18006b2b0  mov     r13d, 0A8h
0x18006b2b6  add     rcx, r13
0x18006b2b9  mov     rdx, rax
0x18006b2bc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b2c1  lea     rcx, [rsp+228h+var_180]
0x18006b2c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b2ce  mov     rdx, [rdi]
0x18006b2d1  add     rdx, rsi
0x18006b2d4  lea     rcx, [rsp+228h+var_180]
0x18006b2dc  call    ?GetPackageFullNameFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18006b2e1  mov     rcx, [rdi]
0x18006b2e4  add     rcx, 0C8h
0x18006b2eb  mov     rdx, rax
0x18006b2ee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006b2f3  lea     rcx, [rsp+228h+var_180]
0x18006b2fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b300  mov     rax, [rdi]
0x18006b303  cmp     [rax+0B8h], r14
0x18006b30a  jnz     loc_18006B3C4
0x18006b310  lea     rdx, aNonPackagedNon; "Non-packaged (non-Store) app. AccessChe"...
0x18006b317  lea     rcx, [rsp+228h+var_180]
0x18006b31f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b324  lea     rcx, [rsp+228h+var_180]
0x18006b32c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b331  mov     rax, [rdi]
0x18006b334  mov     [rax+24h], r14b
0x18006b338  mov     rsi, qword ptr [rsp+228h+var_1B0]
0x18006b33d  lea     rdx, aPackagedappD; "PackagedApp(%d)"
0x18006b344  lea     rcx, [rsp+228h+var_180]
0x18006b34c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b351  lea     rcx, [rsp+228h+var_180]
0x18006b359  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b35e  mov     rdx, [rdi]
0x18006b361  cmp     [rdx+24h], r14b
0x18006b365  jz      loc_18006B4E9
0x18006b36b  mov     rcx, [rdx+1C0h]; TokenHandle
0x18006b372  lea     rax, [rcx-1]
0x18006b376  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006b37a  ja      loc_18006B4C5
0x18006b380  mov     dword ptr [rsp+228h+TokenInformation], r14d
0x18006b388  mov     [rsp+228h+var_1D0], r14d
0x18006b38d  lea     rax, [rsp+228h+var_1D0]
0x18006b392  mov     [rsp+228h+ReturnLength], rax; ReturnLength
0x18006b397  mov     r9d, 4; TokenInformationLength
0x18006b39d  lea     r8, [rsp+228h+TokenInformation]; TokenInformation
0x18006b3a5  lea     edx, [r9+2Ch]; TokenInformationClass
0x18006b3a9  call    cs:__imp_GetTokenInformation
0x18006b3af  mov     rcx, [rsp+228h]; this
0x18006b3b7  test    eax, eax
0x18006b3b9  jz      loc_18006C1C3
0x18006b3bf  jmp     loc_18006B4B8
0x18006b3c4  cmp     dword ptr [rax+18h], 2
0x18006b3c8  jz      loc_18006B338
0x18006b3ce  lea     rdx, aAppPackageFami; "App package family name updated to '%ws"...
0x18006b3d5  lea     rcx, [rsp+228h+var_180]
0x18006b3dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b3e2  lea     rcx, [rsp+228h+var_180]
0x18006b3ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b3ef  lea     rdx, aAppPackageFull; "App package full name updated to '%ws'"
0x18006b3f6  lea     rcx, [rsp+228h+var_180]
0x18006b3fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b403  lea     rcx, [rsp+228h+var_180]
0x18006b40b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b410  mov     rax, [rdi]
0x18006b413  mov     byte ptr [rax+24h], 1
0x18006b417  jmp     loc_18006B338
0x18006b41c  mov     r14, [rsp+228h+var_1A0]
0x18006b424  mov     r8, r14
0x18006b427  mov     rsi, qword ptr [rsp+228h+var_1B0]
  ... truncated ...
```
