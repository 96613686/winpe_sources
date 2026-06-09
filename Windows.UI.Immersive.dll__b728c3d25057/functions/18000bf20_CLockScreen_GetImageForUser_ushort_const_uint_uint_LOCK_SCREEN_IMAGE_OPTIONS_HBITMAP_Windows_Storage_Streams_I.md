# CLockScreen::_GetImageForUser(ushort const *,uint,uint,LOCK_SCREEN_IMAGE_OPTIONS,HBITMAP__ * *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18000bf20`
- end: `0x18000d2b1`
- name: `?_GetImageForUser@CLockScreen@@QEAAJPEBGIIW4LOCK_SCREEN_IMAGE_OPTIONS@@PEAPEAUHBITMAP__@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `5009`
- prototype: `int __high(const unsigned __int16 *, unsigned int, unsigned int, enum LOCK_SCREEN_IMAGE_OPTIONS, HBITMAP *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `3`
- callee_count: `53`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fc10`
- `0x1800b1880`
- `0x1800b18c0`

## callees

- `0x180004578`
- `0x180005270`
- `0x18000acdc`
- `0x18000ada8`
- `0x18000af94`
- `0x18000b0d4`
- `0x18000b258`
- `0x18000b3cc`
- `0x18000b458`
- `0x18000b64c`
- `0x18000b774`
- `0x18000bb40`
- `0x18000bc00`
- `0x18000bd60`
- `0x18000bdc0`
- `0x18000bf20`
- `0x18000d2b8`
- `0x18000d41c`
- `0x180013244`
- `0x1800219d4`
- `0x180021fcc`
- `0x180022480`
- `0x180026b18`
- `0x18002a660`
- `0x18002a8c4`
- `0x180030e48`
- `0x180031690`
- `0x18003217c`
- `0x18003395c`
- `0x180033c44`
- `0x180033c9c`
- `0x1800367ec`
- `0x180039e34`
- `0x18003aa84`
- `0x18003d858`
- `0x18003fe54`
- `0x180043e10`
- `0x18004c6c0`
- `0x180050ba0`
- `0x180051524`
- `0x180083150`
- `0x18008ce90`
- `0x1800aaf98`
- `0x1800abed8`
- `0x1800abf7c`
- `0x1800ac020`
- `0x1800ac0c4`
- `0x1800ac14c`
- `0x1800afb98`
- `0x1800b9970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d22c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d22c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c022`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c022`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c0cc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c0cc`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c76d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c94a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000cd8b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c76d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c94a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000cd8b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000cde2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000d0fa`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000cde2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000d0fa`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000c545`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18000c545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c7c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c995`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c7c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c995`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c4e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c4e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c5c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ce36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d04a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ce36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d04a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c171`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cb39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cc7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c171`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cb39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000cc7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c28c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c562`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c28c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c562`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CLockScreen::_GetImageForUser(
        __int64 a1,
        CreativeFramework::LockScreenCreativeConfigHelpers *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        RTL_SRWLOCK *a6,
        struct Windows::Storage::Streams::IRandomAccessStream **a7)
{
  CreativeFramework::LockScreenCreativeConfigHelpers *v7; // rsi
  CreativeFramework::Policy *v9; // rcx
  unsigned __int16 *v10; // r13
  LSTATUS ValueW; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  bool v14; // sf
  char v15; // r15
  bool v16; // bl
  int LocalSystemUserSid; // r12d
  bool v18; // al
  WCHAR *v19; // rdi
  PSID v20; // rbx
  char v21; // al
  int v22; // ebx
  __int16 v23; // r14
  bool IsSpotlightEnabled; // bl
  int Error; // eax
  int CreativeLockScreenPath; // eax
  int v27; // esi
  __int64 v28; // rdx
  int SecureLockScreenDirectory; // eax
  bool v30; // al
  int v31; // eax
  PSID v32; // rbx
  int SecureInboxLockScreenPath; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  bool v36; // al
  CLockScreen *v37; // rcx
  unsigned __int16 HistoryEntryAt; // si
  int v39; // eax
  unsigned int i; // eax
  unsigned int j; // ecx
  PSID v42; // rbx
  int v43; // r14d
  PSID v44; // rsi
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rsi
  unsigned __int64 v47; // r15
  WCHAR *v48; // rdx
  WCHAR *v49; // rcx
  unsigned __int64 v50; // r8
  __int64 v51; // r9
  WCHAR *v52; // r11
  WCHAR v53; // ax
  __int64 v54; // r10
  WCHAR *v55; // rcx
  __int64 v56; // r15
  bool v57; // cf
  PSID v58; // rsi
  unsigned __int64 v59; // rsi
  _WORD *v60; // rax
  _WORD *v61; // r11
  WCHAR *v62; // rcx
  unsigned __int64 v63; // rdx
  WCHAR *v64; // r8
  __int64 v65; // r9
  WCHAR v66; // ax
  __int64 v67; // r10
  WCHAR *v68; // rcx
  __int64 v69; // rsi
  PSID v70; // rbx
  int v71; // eax
  unsigned __int16 v72; // r14
  PSID v73; // rbx
  int v74; // eax
  bool v75; // si
  const wchar_t *v76; // rcx
  const wchar_t *v77; // rax
  HRESULT v78; // eax
  struct Windows::Storage::Streams::IRandomAccessStream **v79; // r15
  bool v80; // r14
  bool v81; // bl
  HRESULT Instance; // eax
  int v83; // eax
  __int64 v84; // rdx
  CreativeFramework::LockScreenCreativeConfigHelpers *v85; // rsi
  unsigned int v86; // ebx
  unsigned int v87; // r12d
  int v88; // eax
  int v89; // eax
  int StreamOfWICBitmapSourceWithOptions; // eax
  GUID *v91; // rbx
  __int64 v92; // rdx
  HRESULT v93; // eax
  LPWSTR v94; // r9
  int OnlyRandomAccessStreamOverStream; // eax
  struct IStream *v96; // rcx
  int LockImageFlags; // eax
  int v98; // eax
  struct IStream *v99; // rcx
  char v100; // di
  int v101; // eax
  __int64 v102; // rdx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  int pdwTyped; // [rsp+20h] [rbp-E0h]
  bool v109; // [rsp+40h] [rbp-C0h]
  char v110[7]; // [rsp+41h] [rbp-BFh] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v112; // [rsp+50h] [rbp-B0h]
  unsigned int v113; // [rsp+51h] [rbp-AFh] BYREF
  WINBOOL IsMember[2]; // [rsp+58h] [rbp-A8h] BYREF
  PSID hMem; // [rsp+60h] [rbp-A0h] BYREF
  PSID v116; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  CreativeFramework::LockScreenCreativeConfigHelpers *v119; // [rsp+80h] [rbp-80h]
  unsigned int v120; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v121; // [rsp+8Ch] [rbp-74h]
  PCWSTR v122; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp-68h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v125; // [rsp+A8h] [rbp-58h]
  struct Windows::Storage::Streams::IRandomAccessStream **v126[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 SidToCheck; // [rsp+C0h] [rbp-40h] BYREF
  int v128; // [rsp+C8h] [rbp-38h]
  void **v129; // [rsp+D0h] [rbp-30h] BYREF
  char v130[264]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD *v131; // [rsp+1E0h] [rbp+E0h]
  _DWORD *v132; // [rsp+1E8h] [rbp+E8h] BYREF
  char v133[24]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v134; // [rsp+208h] [rbp+108h]
  WCHAR pszPath[264]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR pszFile[264]; // [rsp+430h] [rbp+330h] BYREF
  WCHAR pszMore[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v138[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+928h] [rbp+828h]

  v120 = a4;
  v121 = a3;
  v7 = a2;
  v119 = a2;
  v125 = a1;
  SRWLock = a6;
  v126[0] = a7;
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v129,
    "GetImageForUserActivity");
  v129 = &LockScreenTelemetry::GetImageForUserActivity::`vftable';
  LockScreenTelemetry::GetImageForUserActivity::StartActivity(
    (LockScreenTelemetry::GetImageForUserActivity *)&v129,
    v7 != 0,
    a5,
    a6 != 0,
    a7 != 0);
  v10 = 0;
  if ( a6 )
    a6->Ptr = 0;
  if ( a7 )
    *a7 = 0;
  v122 = 0;
  if ( !CreativeFramework::Policy::IsContentDeliveryPolicyEnforced(v9) )
    goto LABEL_12;
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\Personalization",
             L"LockScreenImage",
             2u,
             0,
             pszPath,
             pcbData);
  v14 = ValueW < 0;
  if ( ValueW )
  {
    pszPath[0] = 0;
    if ( ValueW > 0 )
      v14 = 1;
  }
  if ( v14 || (int)_AllocString<CTCoAllocPolicy>(v13, v12, pszPath, &v122) < 0 )
  {
LABEL_12:
    v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v122,
      0);
    v16 = (int)LockScreenPathFromMDMPolicy((unsigned __int16 **)&v122) >= 0;
  }
  else
  {
    v15 = 1;
    v16 = 0;
  }
  v110[1] = 0;
  v110[3] = 0;
  v112 = 0;
  pv = 0;
  Sid = 0;
  v116 = 0;
  StringSid = 0;
  LocalSystemUserSid = 0;
  pcbData[0] = 0;
  v110[2] = 0;
  SidToCheck = 0x500000000000101LL;
  v128 = 18;
  IsMember[0] = 0;
  v18 = CheckTokenMembership(0, &SidToCheck, IsMember) && IsMember[0];
  v109 = v18;
  LOBYTE(v113) = v18;
  if ( v16 )
  {
    Sid = 0;
    LocalSystemUserSid = CLockScreenHistory::s_GetLocalSystemUserSid(&Sid);
    pcbData[0] = LocalSystemUserSid;
    v19 = (WCHAR *)v122;
    v20 = Sid;
    if ( LocalSystemUserSid >= 0 )
    {
      LocalSystemUserSid = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                             Sid,
                             0x50u,
                             v109,
                             pszFile,
                             (unsigned int)pdwType);
      pcbData[0] = LocalSystemUserSid;
      if ( LocalSystemUserSid >= 0 )
      {
        LocalSystemUserSid = CLockScreenHistory::s_GetSecureCustomLockScreenPath(
                               v20,
                               0x50u,
                               1,
                               0,
                               (unsigned __int16 **)&pv);
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
          if ( ConvertSidToStringSidW(v20, &StringSid)
            || (LocalSystemUserSid = ResultFromKnownLastError(), pcbData[0] = LocalSystemUserSid,
                                                                 LocalSystemUserSid >= 0) )
          {
            LocalSystemUserSid = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(a1 + 144), v19);
            pcbData[0] = LocalSystemUserSid;
          }
        }
      }
    }
    LockScreenTelemetry::GetImageForUserActivity::UsePolicyImagePath<long &>(&v129, pcbData);
    if ( v20 )
      LocalFree(v20);
    goto LABEL_26;
  }
  v19 = (WCHAR *)v122;
  v23 = 79;
  if ( v15 || (a5 & 4) == 0 )
    goto LABEL_66;
  if ( !v7 )
    goto LABEL_171;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  IsSpotlightEnabled = CLockScreen::_s_IsSpotlightEnabled(v7);
  v110[1] = IsSpotlightEnabled;
  v110[0] = IsSpotlightEnabled;
  if ( IsSpotlightEnabled )
  {
    hMem = 0;
    if ( ConvertStringSidToSidW((LPCWSTR)v7, &hMem) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    IsMember[0] = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB64,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)Error,
        (int)pdwType);
LABEL_63:
      LockScreenTelemetry::GetImageForUserActivity::UseSpotlightImagePath<long &,bool &,bool &,bool const &>(
        (unsigned int)&v129,
        (unsigned int)IsMember,
        (unsigned int)v110,
        (unsigned int)&v110[3],
        (__int64)&v113);
      if ( hMem )
        LocalFree(hMem);
      goto LABEL_65;
    }
    v110[0] = 0;
    Sid = 0;
    CreativeLockScreenPath = CLockScreenHistory::s_GetCreativeLockScreenPath(
                               v7,
                               (unsigned __int16 **)&Sid,
                               (unsigned __int16 **)&pv,
                               (unsigned __int16 **)&v116,
                               (bool *)v110);
    v27 = CreativeLockScreenPath;
    IsMember[0] = CreativeLockScreenPath;
    if ( CreativeLockScreenPath >= 0 )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
      if ( (a5 & 8) == 0 || v110[0] )
      {
        SecureLockScreenDirectory = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                                      hMem,
                                      0x4Fu,
                                      v109,
                                      pszFile,
                                      pdwTypeb);
        v27 = SecureLockScreenDirectory;
        if ( SecureLockScreenDirectory < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xB6E,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)SecureLockScreenDirectory,
            pdwTypeb);
        IsMember[0] = v27;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB6B,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)CreativeLockScreenPath,
        pdwTypeb);
    }
    LOBYTE(v28) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl'::`2'::impl,
      v28);
    v110[3] = (CreativeFramework::LockScreenCreativeConfigHelpers::GetLockImageFlags(v119) & 2) != 0;
    v30 = v109;
    if ( !v110[3] && v109 )
    {
      v31 = StringCchPrintfW(pszPath, 0x104u, L"%s_%c", L"LockScreen");
      if ( v31 >= 0 )
        DeleteSystemDataFolderForUser(hMem, 1, pszPath);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB77,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v31,
        79);
      v30 = v109;
    }
    v32 = Sid;
    if ( v27 >= 0 )
    {
      v110[1] = 1;
      v110[0] = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
      if ( v32 )
      {
        SidToCheck = (__int64)v32;
        LockScreenTelemetry::GetImageForUserActivity::UseSpotlightContentId<unsigned short *>(&v129, &SidToCheck);
      }
      goto LABEL_60;
    }
    v112 = 1;
    SecureInboxLockScreenPath = CLockScreenHistory::s_GetSecureLockScreenDirectory(hMem, 0x5Au, v30, pszFile, pdwTypeb);
    IsMember[0] = SecureInboxLockScreenPath;
    v34 = retaddr;
    if ( SecureInboxLockScreenPath >= 0 )
    {
      SecureInboxLockScreenPath = CLockScreenHistory::s_GetSecureInboxLockScreenPath(0x5Au, (unsigned __int16 **)&pv);
      IsMember[0] = SecureInboxLockScreenPath;
      v34 = retaddr;
      if ( SecureInboxLockScreenPath >= 0 )
      {
        LockScreenTelemetry::GetImageForUserActivity::UseSpotlightContentId<unsigned short const (&)[8]>(&v129);
        v36 = 1;
        v110[2] = a5 & 1;
        goto LABEL_59;
      }
      v35 = 2957;
    }
    else
    {
      v35 = 2954;
    }
    wil::details::in1diag3::_Log_Hr(
      v34,
      (void *)v35,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)SecureInboxLockScreenPath,
      pdwTypec);
    v36 = 0;
LABEL_59:
    v110[0] = v36;
    v110[1] = v36;
LABEL_60:
    if ( v32 )
      CoTaskMemFree(v32);
    IsSpotlightEnabled = v110[1];
    v7 = v119;
    Sid = v116;
    goto LABEL_63;
  }
LABEL_65:
  if ( IsSpotlightEnabled )
    goto LABEL_188;
LABEL_66:
  if ( !v7 || (unsigned int)SHWindowsPolicy(POLID_NoChangingLockScreen) )
  {
LABEL_171:
    hMem = 0;
    LocalSystemUserSid = CLockScreenHistory::s_GetLocalSystemUserSid(&hMem);
    pcbData[0] = LocalSystemUserSid;
    if ( LocalSystemUserSid < 0 )
    {
LABEL_187:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      goto LABEL_188;
    }
    v72 = String2[0];
    if ( v15 )
      v72 = 80;
    LOWORD(IsMember[0]) = v72;
    v73 = hMem;
    LocalSystemUserSid = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                           hMem,
                           v72,
                           v109,
                           pszFile,
                           (unsigned int)pdwType);
    pcbData[0] = LocalSystemUserSid;
    if ( LocalSystemUserSid >= 0 )
    {
      v74 = v15
          ? CLockScreenHistory::s_GetSecureCustomLockScreenPath(v73, v72, 1, 0, (unsigned __int16 **)&pv)
          : CLockScreenHistory::s_GetSecureInboxLockScreenPath(v72, (unsigned __int16 **)&pv);
      LocalSystemUserSid = v74;
      pcbData[0] = v74;
      if ( v74 >= 0 )
      {
        if ( ConvertSidToStringSidW(v73, &StringSid) )
        {
          LocalSystemUserSid = 0;
          pcbData[0] = 0;
          goto LABEL_182;
        }
        LocalSystemUserSid = ResultFromKnownLastError();
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
LABEL_182:
          v110[2] = a5 & 1;
          if ( v15 )
          {
            LocalSystemUserSid = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(v125 + 144), v19);
            pcbData[0] = LocalSystemUserSid;
          }
          else
          {
            v110[2] = a5 & 1;
          }
          goto LABEL_186;
        }
        v110[2] = a5 & 1;
      }
    }
LABEL_186:
    LockScreenTelemetry::GetImageForUserActivity::UseLocalSystemImagePath<long &,unsigned short const &>(
      &v129,
      pcbData,
      IsMember);
    goto LABEL_187;
  }
  v116 = 0;
  if ( ConvertStringSidToSidW((LPCWSTR)v7, &v116) )
    LocalSystemUserSid = 0;
  else
    LocalSystemUserSid = ResultFromKnownLastError();
  pcbData[0] = LocalSystemUserSid;
  if ( LocalSystemUserSid >= 0 )
  {
    hMem = 0;
    if ( (int)CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(v116, 1, (unsigned __int16 **)&hMem) < 0 )
    {
      HistoryEntryAt = String2[0];
    }
    else
    {
      HistoryEntryAt = *(_WORD *)hMem;
      CoTaskMemFree(hMem);
    }
    LOWORD(IsMember[0]) = HistoryEntryAt;
    if ( HistoryEntryAt == 79 )
    {
      v39 = CLockScreen::_RemoveCreativeHistoryEntryForUser(v37, v116);
      if ( v39 >= 0 )
      {
        HistoryEntryAt = CLockScreenHistory::s_GetHistoryEntryAt(0, v116);
        LOWORD(IsMember[0]) = HistoryEntryAt;
        v23 = HistoryEntryAt;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBC3,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v39,
          (int)pdwType);
      }
    }
    else
    {
      v23 = HistoryEntryAt;
    }
    for ( i = 0; i < 6; ++i )
    {
      if ( HistoryEntryAt == word_18012D7E0[20 * i] )
        goto LABEL_152;
    }
    if ( v23 == 80 )
    {
LABEL_152:
      hMem = 0;
      LocalSystemUserSid = CLockScreenHistory::s_GetLocalSystemUserSid(&hMem);
      pcbData[0] = LocalSystemUserSid;
      if ( LocalSystemUserSid >= 0 )
      {
        v70 = hMem;
        LocalSystemUserSid = CLockScreenHistory::s_GetSecureLockScreenDirectory(
                               hMem,
                               HistoryEntryAt,
                               v109,
                               pszFile,
                               (unsigned int)pdwType);
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
          v71 = v23 == 80
              ? CLockScreenHistory::s_GetSecureCustomLockScreenPath(v70, HistoryEntryAt, 1, 0, (unsigned __int16 **)&pv)
              : CLockScreenHistory::s_GetSecureInboxLockScreenPath(HistoryEntryAt, (unsigned __int16 **)&pv);
          LocalSystemUserSid = v71;
          pcbData[0] = v71;
          if ( v71 >= 0 )
          {
            if ( ConvertSidToStringSidW(v70, &StringSid) )
              LocalSystemUserSid = 0;
            else
              LocalSystemUserSid = ResultFromKnownLastError();
            pcbData[0] = LocalSystemUserSid;
            if ( v23 == 80 || (v110[2] = 1, (a5 & 1) == 0) )
              v110[2] = 0;
            if ( LocalSystemUserSid >= 0 && v23 == 80 && v15 )
            {
              LocalSystemUserSid = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(v125 + 144), v19);
              pcbData[0] = LocalSystemUserSid;
            }
          }
        }
      }
      LockScreenTelemetry::GetImageForUserActivity::UseInboxImagePath<long &,unsigned short &>(&v129, pcbData, IsMember);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      goto LABEL_169;
    }
    for ( j = 0; j < 7; ++j )
    {
      if ( HistoryEntryAt == aAbcdefg[j] )
      {
        v42 = v116;
        v43 = HistoryEntryAt;
        LODWORD(pdwType) = HistoryEntryAt;
        LocalSystemUserSid = StringCchPrintfW(pszPath, 0x104u, L"%s_%c", L"LockScreen");
        if ( LocalSystemUserSid >= 0 )
          LocalSystemUserSid = GetSystemDataFolderForUser(v42, pszPath, 1u, pszFile, (__int64)pdwType, v109);
        pcbData[0] = LocalSystemUserSid;
        if ( LocalSystemUserSid >= 0 )
        {
          v44 = v116;
          pv = 0;
          LODWORD(pdwType) = v43;
          LocalSystemUserSid = StringCchPrintfW(v138, 0x104u, L"%s_%c", L"LockScreen");
          v45 = -1;
          if ( LocalSystemUserSid >= 0 )
          {
            LocalSystemUserSid = GetSystemDataFolderForUser(v44, v138, 1u, pszPath, (__int64)pdwType, v109);
            if ( LocalSystemUserSid >= 0 )
            {
              LocalSystemUserSid = PathCchAppend(pszPath, 0x104u, L"LockScreen.jpg");
              if ( LocalSystemUserSid >= 0 )
              {
                v46 = -1;
                do
                  ++v46;
                while ( pszPath[v46] );
                v47 = v46 + 1;
                if ( v46 + 1 >= v46 && (SidToCheck = 0, is_mul_ok(v47, 2u)) )
                {
                  v48 = (WCHAR *)CoTaskMemAlloc(2 * v47);
                  pv = v48;
                  LocalSystemUserSid = 0;
                  if ( v48 )
                  {
                    if ( v47 <= 0x7FFFFFFF )
                    {
                      if ( v46 < 0x7FFFFFFF )
                      {
                        v49 = pszPath;
                        v50 = v46 + 1;
                        v51 = 0;
                        v52 = v48;
                        do
                        {
                          if ( !v46 )
                            break;
                          v53 = *v49;
                          if ( !*v49 )
                            break;
                          ++v49;
                          *v48++ = v53;
                          --v46;
                          ++v51;
                          --v50;
                        }
                        while ( v50 );
                        v54 = v51 - 1;
                        if ( v50 )
                          v54 = v51;
                        v55 = v48 - 1;
                        if ( v50 )
                          v55 = v48;
                        *v55 = 0;
                        if ( v50 )
                        {
                          v57 = v47 == v54;
                          v56 = v47 - v54;
                          if ( !v57 && v56 != 1 && (unsigned __int64)(2 * v56) > 2 )
                            memset_0(&v52[v54 + 1], 0, 2 * v56 - 2);
                        }
                      }
                      else if ( v46 != -1 )
                      {
                        *v48 = 0;
                      }
                    }
                    else
                    {
                      *v48 = 0;
                    }
                  }
                  else
                  {
                    LocalSystemUserSid = -2147024882;
                  }
                }
                else
                {
                  LocalSystemUserSid = -2147024362;
                }
              }
            }
          }
          pcbData[0] = LocalSystemUserSid;
          if ( LocalSystemUserSid >= 0 )
          {
            v58 = v116;
            Sid = 0;
            LODWORD(pdwType) = v43;
            LocalSystemUserSid = StringCchPrintfW(v138, 0x104u, L"%s_%c", L"LockScreen");
            if ( LocalSystemUserSid >= 0 )
            {
              LocalSystemUserSid = GetSystemDataFolderForUser(v58, v138, 1u, pszPath, (__int64)pdwType, v109);
              if ( LocalSystemUserSid >= 0 )
              {
                LocalSystemUserSid = PathCchAppend(pszPath, 0x104u, L"LockScreenPortrait.jpg");
                if ( LocalSystemUserSid >= 0 )
                {
                  do
                    ++v45;
                  while ( pszPath[v45] );
                  v59 = v45 + 1;
                  if ( v45 + 1 >= v45 && (SidToCheck = 0, is_mul_ok(v59, 2u)) )
                  {
                    v60 = CoTaskMemAlloc(2 * v59);
                    v61 = v60;
                    Sid = v60;
                    LocalSystemUserSid = 0;
                    if ( v60 )
                    {
                      if ( v59 <= 0x7FFFFFFF )
                      {
                        if ( v45 < 0x7FFFFFFF )
                        {
                          v62 = pszPath;
                          v63 = v45 + 1;
                          v64 = v60;
                          v65 = 0;
                          do
                          {
                            if ( !v45 )
                              break;
                            v66 = *v62;
                            if ( !*v62 )
                              break;
                            ++v62;
                            *v64++ = v66;
                            --v45;
                            ++v65;
                            --v63;
                          }
                          while ( v63 );
                          v67 = v65 - 1;
                          if ( v63 )
                            v67 = v65;
                          v68 = v64 - 1;
                          if ( v63 )
                            v68 = v64;
                          *v68 = 0;
                          if ( v63 )
                          {
                            v57 = v59 == v67;
                            v69 = v59 - v67;
                            if ( !v57 && v69 != 1 && (unsigned __int64)(2 * v69) > 2 )
                              memset_0(&v61[v67 + 1], 0, 2 * v69 - 2);
                          }
                        }
                        else if ( v45 != -1 )
                        {
                          *v60 = 0;
                        }
                      }
                      else
                      {
                        *v60 = 0;
                      }
                    }
                    else
                    {
                      LocalSystemUserSid = -2147024882;
                    }
                  }
                  else
                  {
                    LocalSystemUserSid = -2147024362;
                  }
                }
              }
            }
            if ( LocalSystemUserSid < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xBEF,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
                (const char *)(unsigned int)LocalSystemUserSid,
                (int)pdwType);
            pcbData[0] = LocalSystemUserSid;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xBEC,
              (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
              (const char *)(unsigned int)LocalSystemUserSid,
              (int)pdwType);
          }
        }
        LockScreenTelemetry::GetImageForUserActivity::UseCustomImagePath<long &,unsigned short &>(
          &v129,
          pcbData,
          IsMember);
        break;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBBC,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)LocalSystemUserSid,
      (int)pdwType);
  }
LABEL_169:
  if ( v116 )
    LocalFree(v116);
LABEL_188:
  v10 = (unsigned __int16 *)Sid;
  if ( !Sid )
  {
LABEL_26:
    v21 = 0;
    goto LABEL_27;
  }
  v21 = 1;
LABEL_27:
  LOBYTE(v113) = v21;
  v110[0] = pv != 0;
  LOBYTE(IsMember[0]) = 1;
  LockScreenTelemetry::GetImageForUserActivity::ImagePathFound<long &,bool,bool,bool>(
    (__int64)&v129,
    (int *)pcbData,
    IsMember,
    v110,
    (char *)&v113);
  if ( LocalSystemUserSid < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBFA,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)LocalSystemUserSid,
      (int)pdwTypea);
    v22 = LocalSystemUserSid;
    goto LABEL_247;
  }
  v75 = (a5 & 2) != 0;
  v76 = &Class;
  if ( (a5 & 2) == 0 )
    v76 = L"_notdimmed";
  v77 = L"_flipped";
  if ( !v110[2] )
    v77 = &Class;
  LODWORD(pdwTypea) = v120;
  v78 = StringCchPrintfW(pszMore, 0x40u, L"LockScreen___%4.4u_%4.4u%s%s.jpg", v121, pdwTypea, v77, v76);
  LocalSystemUserSid = v78;
  if ( v78 >= 0 )
  {
    v78 = PathCchAppend(pszFile, 0x104u, pszMore);
    LocalSystemUserSid = v78;
  }
  v22 = v78;
  *(_QWORD *)pcbData = 0;
  if ( v78 >= 0 )
  {
    v79 = v126[0];
    v80 = v110[1];
    v81 = v110[3];
    if ( v126[0] && (!v110[1] || v110[3] || v112) )
    {
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
      if ( SHCreateStreamOnFileW(pszFile, 0, (IStream **)pcbData) >= 0 )
      {
        LocalSystemUserSid = CreateReadOnlyRandomAccessStreamOverStream(*(struct IStream **)pcbData, v79);
        v22 = LocalSystemUserSid;
        goto LABEL_245;
      }
    }
    *(_QWORD *)IsMember = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(IsMember);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)IsMember);
    LocalSystemUserSid = Instance;
    if ( Instance < 0 )
    {
      v22 = Instance;
      goto LABEL_244;
    }
    hMem = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
    pdwTyped = 0;
    v83 = LoadImageWithWIC(*(_QWORD *)IsMember, pszFile, 2, &hMem);
    LocalSystemUserSid = v83;
    if ( v83 >= 0 && (!v80 || v81) )
    {
      v22 = v83;
      v85 = v119;
      goto LABEL_229;
    }
    v110[0] = 0;
    v116 = 0;
    v86 = v121;
    if ( !v10 )
      goto LABEL_213;
    v87 = v120;
    if ( v121 >= v120 )
      goto LABEL_213;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v116);
    v88 = CLockScreen::_s_LoadAndScaleBitmapSource(
            *(struct IWICImagingFactory **)IsMember,
            v10,
            v86,
            v87,
            v75,
            (struct IWICBitmapSource **)&v116,
            (bool *)v110);
    LocalSystemUserSid = v88;
    if ( v88 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC2C,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v88,
        pdwTyped);
    if ( !v116 )
    {
LABEL_213:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v116);
      v89 = CLockScreen::_s_LoadAndScaleBitmapSource(
              *(struct IWICImagingFactory **)IsMember,
              (const unsigned __int16 *)pv,
              v86,
              v120,
              v75,
              (struct IWICBitmapSource **)&v116,
              (bool *)v110);
      LocalSystemUserSid = v89;
      if ( v89 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC31,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v89,
          pdwTyped);
    }
    v22 = LocalSystemUserSid;
    if ( LocalSystemUserSid >= 0 )
    {
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
      StreamOfWICBitmapSourceWithOptions = CLockScreen::_s_FlipBitmapSourceIfNecessary(
                                             *(struct IWICImagingFactory **)IsMember,
                                             (struct IWICBitmapSource *)v116,
                                             v110[2],
                                             (struct IWICBitmapSource **)&hMem);
      LocalSystemUserSid = StreamOfWICBitmapSourceWithOptions;
      if ( StreamOfWICBitmapSourceWithOptions >= 0 )
      {
        v91 = &GUID_ContainerFormatPng;
        if ( !v110[0] )
          v91 = &GUID_ContainerFormatJpeg;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
        *(GUID *)v126 = GUID_WICPixelFormat32bppBGRA;
        StreamOfWICBitmapSourceWithOptions = GetStreamOfWICBitmapSourceWithOptions(*(_QWORD *)IsMember, hMem, v91, v126);
        LocalSystemUserSid = StreamOfWICBitmapSourceWithOptions;
        if ( StreamOfWICBitmapSourceWithOptions >= 0 && v109 )
        {
          LOBYTE(v92) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl'::`2'::impl,
            v92);
          Sid = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Sid);
          v93 = CoCreateInstance(
                  &CLSID_ImageSanitizationBroker,
                  0,
                  1u,
                  &GUID_f43f82aa_4498_463d_80e1_cc44cd4c6c14,
                  &Sid);
          LocalSystemUserSid = v93;
          v85 = v119;
          if ( v93 >= 0 )
          {
            v94 = StringSid;
            if ( !StringSid )
              v94 = (LPWSTR)v119;
            pdwTyped = 6;
            v93 = (*(__int64 (__fastcall **)(PSID, _QWORD, WCHAR *, LPWSTR))(*(_QWORD *)Sid + 32LL))(
                    Sid,
                    *(_QWORD *)pcbData,
                    pszFile,
                    v94);
            LocalSystemUserSid = v93;
          }
          v22 = v93;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Sid);
          goto LABEL_228;
        }
      }
      v22 = StreamOfWICBitmapSourceWithOptions;
    }
    v85 = v119;
LABEL_228:
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v116);
LABEL_229:
    if ( v22 < 0 )
    {
LABEL_242:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
LABEL_244:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(IsMember);
      goto LABEL_245;
    }
    if ( SRWLock )
    {
      OnlyRandomAccessStreamOverStream = ConvertWICBitmapToHBITMAP(
                                           *(struct IWICImagingFactory **)IsMember,
                                           (struct IWICBitmapSource *)hMem,
                                           (HBITMAP *)SRWLock);
LABEL_237:
      v22 = OnlyRandomAccessStreamOverStream;
      LocalSystemUserSid = OnlyRandomAccessStreamOverStream;
      goto LABEL_238;
    }
    if ( v79 )
    {
      v96 = *(struct IStream **)pcbData;
      if ( *(_QWORD *)pcbData )
      {
LABEL_236:
        OnlyRandomAccessStreamOverStream = CreateReadOnlyRandomAccessStreamOverStream(v96, v79);
        goto LABEL_237;
      }
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(pcbData);
      LocalSystemUserSid = SHCreateStreamOnFileW(pszFile, 0, (IStream **)pcbData);
      v22 = LocalSystemUserSid;
      if ( LocalSystemUserSid >= 0 )
      {
        v96 = *(struct IStream **)pcbData;
        goto LABEL_236;
      }
    }
LABEL_238:
    if ( v80 && !v112 )
    {
      LOBYTE(v84) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl'::`2'::impl,
        v84);
      LockImageFlags = CreativeFramework::LockScreenCreativeConfigHelpers::GetLockImageFlags(v85);
      v98 = CreativeFramework::LockScreenCreativeConfigHelpers::SetLockImageFlags(LockImageFlags | 2u, v85);
      if ( v98 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF3A,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v98,
          pdwTyped);
    }
    goto LABEL_242;
  }
LABEL_245:
  v99 = *(struct IStream **)pcbData;
  if ( *(_QWORD *)pcbData )
  {
    *(_QWORD *)pcbData = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v99 + 16LL))(v99);
  }
LABEL_247:
  CoTaskMemFree(v10);
  CoTaskMemFree(pv);
  LocalFree(StringSid);
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v129,
    (unsigned int)LocalSystemUserSid);
  if ( v19 )
    CoTaskMemFree(v19);
  v129 = &LockScreenTelemetry::GetImageForUserActivity::`vftable';
  if ( !v132 )
    goto LABEL_257;
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v129,
    &SRWLock);
  if ( v132 && *v132 == 1 )
  {
    v100 = 1;
  }
  else
  {
    v100 = 0;
    wil::details::shared_object<wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v132);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v100 )
  {
LABEL_257:
    if ( *v131 == 1 )
    {
      v101 = v131[22];
      v102 = 2147942974LL;
      if ( v101 < 0 )
        v102 = (unsigned int)v101;
      wil::ActivityBase<LockScreenLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v131,
        v102,
        &v120);
      wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v129);
    }
  }
  if ( v134 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v133);
  wil::details::shared_object<wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v132);
  wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LockScreenLogging,_TlgReflectorTag_Param0IsProviderType>(v130);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000bf20  push    rbp
0x18000bf22  push    rbx
0x18000bf23  push    rsi
0x18000bf24  push    rdi
0x18000bf25  push    r12
0x18000bf27  push    r13
0x18000bf29  push    r14
0x18000bf2b  push    r15
0x18000bf2d  lea     rbp, [rsp-7E8h]
0x18000bf35  sub     rsp, 8E8h
0x18000bf3c  mov     rax, cs:__security_cookie
0x18000bf43  xor     rax, rsp
0x18000bf46  mov     [rbp+820h+var_50], rax
0x18000bf4d  mov     [rbp+820h+var_898], r9d
0x18000bf51  mov     [rbp+820h+var_894], r8d
0x18000bf55  mov     rsi, rdx
0x18000bf58  mov     [rbp+820h+var_8A0], rdx
0x18000bf5c  mov     r14, rcx
0x18000bf5f  mov     [rbp+820h+var_878], rcx
0x18000bf63  mov     r12, [rbp+820h+arg_28]
0x18000bf6a  mov     [rbp+820h+SRWLock], r12
0x18000bf6e  mov     r15, [rbp+820h+arg_30]
0x18000bf75  mov     [rbp+820h+var_870], r15
0x18000bf79  test    r15, r15
0x18000bf7c  setnz   dil
0x18000bf80  test    r12, r12
0x18000bf83  setnz   bl
0x18000bf86  lea     rdx, aGetimageforuse; "GetImageForUserActivity"
0x18000bf8d  lea     rcx, [rbp+820h+var_850]
0x18000bf91  call    ??0?$ActivityBase@VLockScreenLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000bf96  lea     rax, ??_7GetImageForUserActivity@LockScreenTelemetry@@6B@; const LockScreenTelemetry::GetImageForUserActivity::`vftable'
0x18000bf9d  mov     [rbp+820h+var_850], rax
0x18000bfa1  test    rsi, rsi
0x18000bfa4  setnz   dl; bool
0x18000bfa7  mov     byte ptr [rsp+920h+pdwType], dil; unsigned int
0x18000bfac  movzx   r9d, bl; bool
0x18000bfb0  mov     edi, [rbp+820h+arg_20]
0x18000bfb6  mov     r8d, edi; int
0x18000bfb9  lea     rcx, [rbp+820h+var_850]; this
0x18000bfbd  call    ?StartActivity@GetImageForUserActivity@LockScreenTelemetry@@QEAAX_NH00@Z; LockScreenTelemetry::GetImageForUserActivity::StartActivity(bool,int,bool,bool)
0x18000bfc2  nop
0x18000bfc3  xor     r13d, r13d
0x18000bfc6  test    r12, r12
0x18000bfc9  jz      short loc_18000BFCF
0x18000bfcb  mov     [r12], r13
0x18000bfcf  test    r15, r15
0x18000bfd2  jz      short loc_18000BFD7
0x18000bfd4  mov     [r15], r13
0x18000bfd7  mov     [rbp+820h+var_890], r13
0x18000bfdb  call    ?IsContentDeliveryPolicyEnforced@Policy@CreativeFramework@@YA_NXZ; CreativeFramework::Policy::IsContentDeliveryPolicyEnforced(void)
0x18000bfe0  test    al, al
0x18000bfe2  jz      short loc_18000C05D
0x18000bfe4  mov     [rsp+920h+var_8D8], 208h
0x18000bfec  lea     rax, [rsp+920h+var_8D8]
0x18000bff1  mov     [rsp+920h+pcbData], rax; pcbData
0x18000bff6  lea     rax, [rbp+820h+pszPath]
0x18000bffd  mov     [rsp+920h+pvData], rax; pvData
0x18000c002  mov     [rsp+920h+pdwType], r13; pdwType
0x18000c007  mov     r9d, 2; dwFlags
0x18000c00d  lea     r8, Value; "LockScreenImage"
0x18000c014  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18000c01b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c022  call    cs:__imp_RegGetValueW
0x18000c028  test    eax, eax
0x18000c02a  jz      short loc_18000C040
0x18000c02c  mov     [rbp+820h+pszPath], r13w
0x18000c034  jle     short loc_18000C040
0x18000c036  movzx   eax, ax
0x18000c039  or      eax, 80070000h
0x18000c03e  test    eax, eax
0x18000c040  js      short loc_18000C05D
0x18000c042  lea     r9, [rbp+820h+var_890]
0x18000c046  lea     r8, [rbp+820h+pszPath]
0x18000c04d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000c052  test    eax, eax
0x18000c054  js      short loc_18000C05D
0x18000c056  mov     r15b, 1
0x18000c059  xor     bl, bl
0x18000c05b  jmp     short loc_18000C079
0x18000c05d  xor     r15b, r15b
0x18000c060  xor     edx, edx
0x18000c062  lea     rcx, [rbp+820h+var_890]
0x18000c066  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000c06b  lea     rcx, [rbp+820h+var_890]; unsigned __int16 **
0x18000c06f  call    ?LockScreenPathFromMDMPolicy@@YAJPEAPEAG@Z; LockScreenPathFromMDMPolicy(ushort * *)
0x18000c074  test    eax, eax
0x18000c076  setns   bl
0x18000c079  mov     [rsp+920h+var_8DF+1], 0
0x18000c07e  mov     [rsp+920h+var_8DF+3], 0
0x18000c083  mov     [rsp+920h+var_8D0], 0
0x18000c088  mov     [rsp+920h+pv], r13
0x18000c08d  mov     [rsp+920h+Sid], r13
0x18000c092  mov     [rsp+920h+var_8B8], r13
0x18000c097  xor     eax, eax
0x18000c099  mov     [rbp+820h+StringSid], rax
0x18000c09d  mov     r12d, eax
0x18000c0a0  mov     [rsp+920h+var_8D8], eax
0x18000c0a4  mov     [rsp+920h+var_8DF+2], al
0x18000c0a8  mov     dword ptr [rbp+820h+SidToCheck], 101h
0x18000c0af  mov     dword ptr [rbp+820h+SidToCheck+4], 5000000h
0x18000c0b6  mov     [rbp+820h+var_858], 12h
0x18000c0bd  mov     [rsp+920h+IsMember], eax
0x18000c0c1  lea     r8, [rsp+920h+IsMember]; IsMember
0x18000c0c6  lea     rdx, [rbp+820h+SidToCheck]; SidToCheck
0x18000c0ca  xor     ecx, ecx; TokenHandle
0x18000c0cc  call    cs:__imp_CheckTokenMembership
0x18000c0d2  test    eax, eax
0x18000c0d4  jz      short loc_18000C0E1
0x18000c0d6  cmp     [rsp+920h+IsMember], r12d
0x18000c0db  jz      short loc_18000C0E1
0x18000c0dd  mov     al, 1
0x18000c0df  jmp     short loc_18000C0E3
0x18000c0e1  xor     al, al
0x18000c0e3  mov     [rsp+920h+var_8E0], al
0x18000c0e7  mov     byte ptr [rsp+920h+var_8CF], al
0x18000c0eb  test    bl, bl
0x18000c0ed  jz      loc_18000C223
0x18000c0f3  mov     [rsp+920h+Sid], 0
0x18000c0fc  lea     rcx, [rsp+920h+Sid]; void **
0x18000c101  call    ?s_GetLocalSystemUserSid@CLockScreenHistory@@SAJPEAPEAX@Z; CLockScreenHistory::s_GetLocalSystemUserSid(void * *)
0x18000c106  mov     r12d, eax
0x18000c109  mov     [rsp+920h+var_8D8], eax
0x18000c10d  mov     rdi, [rbp+820h+var_890]
0x18000c111  mov     rbx, [rsp+920h+Sid]
0x18000c116  test    eax, eax
0x18000c118  js      loc_18000C1A1
0x18000c11e  mov     esi, 50h ; 'P'
0x18000c123  mov     edx, esi; unsigned __int16
0x18000c125  lea     r9, [rbp+820h+pszFile]; unsigned __int16 *
0x18000c12c  movzx   r8d, [rsp+920h+var_8E0]; bool
0x18000c132  mov     rcx, rbx; void *
0x18000c135  call    ?s_GetSecureLockScreenDirectory@CLockScreenHistory@@SAJPEAXG_NPEAGI@Z; CLockScreenHistory::s_GetSecureLockScreenDirectory(void *,ushort,bool,ushort *,uint)
0x18000c13a  mov     r12d, eax
0x18000c13d  mov     [rsp+920h+var_8D8], eax
0x18000c141  test    eax, eax
0x18000c143  js      short loc_18000C1A1
0x18000c145  mov     edx, esi; unsigned __int16
0x18000c147  lea     rax, [rsp+920h+pv]
0x18000c14c  mov     [rsp+920h+pdwType], rax; unsigned __int16 **
0x18000c151  xor     r9d, r9d; bool
0x18000c154  mov     r8b, 1; bool
0x18000c157  mov     rcx, rbx; void *
0x18000c15a  call    ?s_GetSecureCustomLockScreenPath@CLockScreenHistory@@SAJPEAXG_N1PEAPEAG@Z; CLockScreenHistory::s_GetSecureCustomLockScreenPath(void *,ushort,bool,bool,ushort * *)
0x18000c15f  mov     r12d, eax
0x18000c162  mov     [rsp+920h+var_8D8], eax
0x18000c166  test    eax, eax
0x18000c168  js      short loc_18000C1A1
0x18000c16a  lea     rdx, [rbp+820h+StringSid]; StringSid
0x18000c16e  mov     rcx, rbx; Sid
0x18000c171  call    cs:__imp_ConvertSidToStringSidW
0x18000c177  test    eax, eax
0x18000c179  jnz     short loc_18000C18B
0x18000c17b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c180  mov     r12d, eax
0x18000c183  mov     [rsp+920h+var_8D8], eax
0x18000c187  test    eax, eax
0x18000c189  js      short loc_18000C1A1
0x18000c18b  lea     rcx, [r14+90h]; this
0x18000c192  mov     rdx, rdi; pszPath
0x18000c195  call    ?_InitOrUpdateGPImages@CLockScreenHistory@@IEAAJPEBG@Z; CLockScreenHistory::_InitOrUpdateGPImages(ushort const *)
0x18000c19a  mov     r12d, eax
0x18000c19d  mov     [rsp+920h+var_8D8], eax
0x18000c1a1  lea     rdx, [rsp+920h+var_8D8]
0x18000c1a6  lea     rcx, [rbp+820h+var_850]
0x18000c1aa  call    ??$UsePolicyImagePath@AEAJ@GetImageForUserActivity@LockScreenTelemetry@@QEAAXAEAJ@Z; LockScreenTelemetry::GetImageForUserActivity::UsePolicyImagePath<long &>(long &)
0x18000c1af  nop
0x18000c1b0  test    rbx, rbx
0x18000c1b3  jz      short loc_18000C1BF
0x18000c1b5  mov     rcx, rbx; hMem
0x18000c1b8  call    cs:__imp_LocalFree
0x18000c1be  nop
0x18000c1bf  xor     al, al
0x18000c1c1  mov     byte ptr [rsp+920h+var_8CF], al
0x18000c1c5  cmp     [rsp+920h+pv], 0
0x18000c1cb  setnz   [rsp+920h+var_8DF]
0x18000c1d0  mov     byte ptr [rsp+920h+IsMember], 1
0x18000c1d5  lea     rax, [rsp+920h+var_8CF]
0x18000c1da  mov     [rsp+920h+pdwType], rax; int
0x18000c1df  lea     r9, [rsp+920h+var_8DF]
0x18000c1e4  lea     r8, [rsp+920h+IsMember]
0x18000c1e9  lea     rdx, [rsp+920h+var_8D8]
0x18000c1ee  lea     rcx, [rbp+820h+var_850]
0x18000c1f2  call    ??$ImagePathFound@AEAJ_N_N_N@GetImageForUserActivity@LockScreenTelemetry@@QEAAXAEAJ$$QEA_N11@Z; LockScreenTelemetry::GetImageForUserActivity::ImagePathFound<long &,bool,bool,bool>(long &,bool &&,bool &&,bool &&)
0x18000c1f7  mov     rcx, [rbp+828h]; this
0x18000c1fe  test    r12d, r12d
0x18000c201  jns     loc_18000CD07
0x18000c207  mov     r9d, r12d; char *
0x18000c20a  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c211  mov     edx, 0BFAh; void *
0x18000c216  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c21b  mov     ebx, r12d
0x18000c21e  jmp     loc_18000D1A2
0x18000c223  movzx   r13d, dil
0x18000c227  and     r13b, 1
0x18000c22b  mov     rdi, [rbp+820h+var_890]
0x18000c22f  mov     r14d, 4Fh ; 'O'
0x18000c235  test    r15b, r15b
0x18000c238  jnz     loc_18000C535
0x18000c23e  test    byte ptr [rbp+820h+arg_20], 4
0x18000c245  jz      loc_18000C535
0x18000c24b  test    rsi, rsi
0x18000c24e  jz      loc_18000CBCF
0x18000c254  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18000c25b  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000c260  mov     rcx, rsi; this
0x18000c263  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x18000c268  movzx   ebx, al
0x18000c26b  mov     [rsp+920h+var_8DF+1], al
0x18000c26f  mov     [rsp+920h+var_8DF], al
0x18000c273  test    al, al
0x18000c275  jz      loc_18000C52D
0x18000c27b  mov     [rsp+920h+hMem], 0
0x18000c284  lea     rdx, [rsp+920h+hMem]; Sid
0x18000c289  mov     rcx, rsi; StringSid
0x18000c28c  call    cs:__imp_ConvertStringSidToSidW
0x18000c292  test    eax, eax
0x18000c294  jz      short loc_18000C29A
0x18000c296  xor     eax, eax
0x18000c298  jmp     short loc_18000C29F
0x18000c29a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c29f  mov     [rsp+920h+IsMember], eax
0x18000c2a3  mov     rcx, [rbp+828h]; this
0x18000c2aa  test    eax, eax
0x18000c2ac  jns     short loc_18000C2C7
0x18000c2ae  mov     r9d, eax; char *
0x18000c2b1  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c2b8  mov     edx, 0B64h; void *
0x18000c2bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c2c2  jmp     loc_18000C4F9
0x18000c2c7  mov     [rsp+920h+var_8DF], 0
0x18000c2cc  mov     [rsp+920h+Sid], 0
0x18000c2d5  lea     rax, [rsp+920h+var_8DF]
0x18000c2da  mov     [rsp+920h+pdwType], rax; int
0x18000c2df  lea     r9, [rsp+920h+var_8B8]; unsigned __int16 **
0x18000c2e4  lea     r8, [rsp+920h+pv]; unsigned __int16 **
0x18000c2e9  lea     rdx, [rsp+920h+Sid]; unsigned __int16 **
0x18000c2ee  mov     rcx, rsi; this
0x18000c2f1  call    ?s_GetCreativeLockScreenPath@CLockScreenHistory@@SAJPEBGPEAPEAG11PEA_N@Z; CLockScreenHistory::s_GetCreativeLockScreenPath(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x18000c2f6  mov     esi, eax
0x18000c2f8  mov     [rsp+920h+IsMember], eax
0x18000c2fc  mov     rcx, [rbp+828h]; this
0x18000c303  test    eax, eax
0x18000c305  jns     short loc_18000C31D
0x18000c307  mov     r9d, eax; char *
0x18000c30a  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c311  mov     edx, 0B6Bh; void *
0x18000c316  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c31b  jmp     short loc_18000C378
0x18000c31d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18000c324  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000c329  test    byte ptr [rbp+820h+arg_20], 8
0x18000c330  jz      short loc_18000C339
0x18000c332  cmp     [rsp+920h+var_8DF], 0
0x18000c337  jz      short loc_18000C378
0x18000c339  mov     edx, r14d; unsigned __int16
0x18000c33c  lea     r9, [rbp+820h+pszFile]; unsigned __int16 *
0x18000c343  movzx   r8d, [rsp+920h+var_8E0]; bool
0x18000c349  mov     rcx, [rsp+920h+hMem]; void *
0x18000c34e  call    ?s_GetSecureLockScreenDirectory@CLockScreenHistory@@SAJPEAXG_NPEAGI@Z; CLockScreenHistory::s_GetSecureLockScreenDirectory(void *,ushort,bool,ushort *,uint)
0x18000c353  mov     esi, eax
0x18000c355  mov     rcx, [rbp+828h]; this
0x18000c35c  test    eax, eax
0x18000c35e  jns     short loc_18000C374
0x18000c360  mov     r9d, eax; char *
0x18000c363  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c36a  mov     edx, 0B6Eh; void *
0x18000c36f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c374  mov     [rsp+920h+IsMember], esi
0x18000c378  mov     dl, 1
0x18000c37a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage> `wil::Feature<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::GetImpl(void)'::`2'::impl
0x18000c381  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CacheSpotlightLockScreenImage>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000c386  mov     rcx, [rbp+820h+var_8A0]
0x18000c38a  call    ?GetLockImageFlags@LockScreenCreativeConfigHelpers@CreativeFramework@@YA?AW4LockImageFlags@12@PEBG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetLockImageFlags(ushort const *)
0x18000c38f  bt      eax, 1
0x18000c393  setb    [rsp+920h+var_8DF+3]
0x18000c398  bt      eax, 1
0x18000c39c  movzx   eax, [rsp+920h+var_8E0]
0x18000c3a1  jb      short loc_18000C417
0x18000c3a3  test    al, al
0x18000c3a5  jz      short loc_18000C417
0x18000c3a7  mov     dword ptr [rsp+920h+pdwType], r14d
0x18000c3ac  lea     r9, aLockscreen; "LockScreen"
0x18000c3b3  lea     r8, aSC; "%s_%c"
0x18000c3ba  mov     edx, 104h; unsigned __int64
0x18000c3bf  lea     rcx, [rbp+820h+pszPath]; unsigned __int16 *
0x18000c3c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c3cb  mov     rcx, [rbp+828h]
0x18000c3d2  test    eax, eax
0x18000c3d4  jns     short loc_18000C3DD
0x18000c3d6  mov     edx, 0B77h
0x18000c3db  jmp     short loc_18000C403
0x18000c3dd  lea     r8, [rbp+820h+pszPath]
0x18000c3e4  mov     edx, 1
0x18000c3e9  mov     rcx, [rsp+920h+hMem]
0x18000c3ee  call    ?DeleteSystemDataFolderForUser@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEBG_N@Z; DeleteSystemDataFolderForUser(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort const *,bool)
0x18000c3f3  mov     rcx, [rbp+828h]; this
0x18000c3fa  test    eax, eax
0x18000c3fc  jns     short loc_18000C412
0x18000c3fe  mov     edx, 0B79h; void *
0x18000c403  mov     r9d, eax; char *
  ... truncated ...
```
