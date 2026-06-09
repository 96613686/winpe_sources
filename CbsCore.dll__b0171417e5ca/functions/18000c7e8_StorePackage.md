# StorePackage

- ea: `0x18000c7e8`
- end: `0x18000d90a`
- name: `StorePackage`
- size: `4386`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180027790`

## callees

- `0x18000b46c`
- `0x18000b4b8`
- `0x18000b5fc`
- `0x18000c7e8`
- `0x18000d910`
- `0x18000e928`
- `0x180010f54`
- `0x1800110d0`
- `0x180013018`
- `0x180013250`
- `0x180013280`
- `0x1800132a4`
- `0x180015420`
- `0x180028e24`
- `0x180048fc0`
- `0x180069d10`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ae508`
- `0x1800b3248`
- `0x1800b693c`
- `0x1800b6a6c`
- `0x1800b980c`
- `0x1800bce9c`
- `0x1800c0054`
- `0x1800c2430`
- `0x1800cc844`
- `0x1800eb500`
- `0x1800eb920`
- `0x180167884`
- `0x1801a43e0`
- `0x1801b5b30`
- `0x1801e9cf8`
- `0x1801ea414`
- `0x1801ebcac`

## string_xrefs

- `0x18000d0af`: `InstallGroup`
- `0x18000cf70`: `InstallClient`
- `0x18000c9fd`: `LastMappingPackageCache`
- `0x18000cfa0`: `InstallName`
- `0x18000d19e`: `SelfUpdate`
- `0x18000cff1`: `InstallLocation`
- `0x18000cb8e`: `Failed to stage package manifest.`
- `0x18000cb21`: `Expected to find file in package manifest path: {}`
- `0x18000ca10`: `Not able to write last mapping package caching time`
- `0x18000ca6c`: `Failed to get manifest path for Package: {}`
- `0x18000cf09`: `Failed to get package store registry key to write package manifest location for package: {}`
- `0x18000d008`: `Unable to store package install location: {}, continuing...`
- `0x18000d0d1`: `Unable to store package install group: {}, continuing...`
- `0x18000cf8b`: `Unable to store package install client: {}, continuing...`
- `0x18000cfbb`: `Unable to store package install name: {}, continuing...`
- `0x18000d25e`: `Failed to write visibility for package: {}`
- `0x18000d1cd`: `Failed to set SelfUpdate property for package: {}`
- `0x18000d404`: `Failed to write baseline for package: {}`
- `0x18000d5b4`: `Failed to write baseline for package: {}`
- `0x18000d683`: `Failed to write baseline for package: {}`
- `0x18000d7e1`: `Failed to persist update detects.`
- `0x18000d848`: `Failed to persist component dependencies.`

## pseudocode

```c
__int64 __fastcall StorePackage(struct CCbsSession *a1, CCbsPackage *a2, void *a3, wchar_t *a4, int a5, __int64 a6)
{
  wchar_t *v7; // rbx
  int StoreObject; // r14d
  __int64 v11; // rdx
  int v12; // eax
  int ManifestPath; // eax
  CCbsSession *v14; // r12
  __int64 v15; // rdx
  wchar_t *v16; // rdi
  int v17; // eax
  CCbsIdentity *v18; // rcx
  int VersionlessStringId; // eax
  CCbsSession *v20; // r12
  __int64 v21; // rdx
  wchar_t *v22; // rsi
  CCbsSession *v23; // r12
  const wchar_t *v24; // rdx
  int v25; // eax
  wchar_t *SpecialPackageIndex; // rax
  __int64 v27; // r8
  const wchar_t *v28; // rdx
  int v29; // eax
  const wchar_t *v30; // rdx
  int v31; // eax
  int v32; // eax
  CCbsSession *v33; // r14
  struct CCbsSession *v34; // rdx
  unsigned int v35; // eax
  int TargetState; // eax
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  const wchar_t *v40; // rax
  int v41; // eax
  __int64 v42; // r14
  unsigned __int64 i; // rax
  const wchar_t *v44; // rdx
  const wchar_t *v45; // rax
  const struct std::nothrow_t *v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  const wchar_t *v48; // rax
  int v49; // eax
  const wchar_t *v50; // rax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int updated; // eax
  int v55; // eax
  int v57; // [rsp+20h] [rbp-E0h]
  CCbsSession *v58; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v59; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v60; // [rsp+40h] [rbp-C0h] BYREF
  int *v61; // [rsp+48h] [rbp-B8h] BYREF
  int v62[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v63; // [rsp+58h] [rbp-A8h] BYREF
  int v64[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v65; // [rsp+68h] [rbp-98h]
  __int128 v66; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v68[2]; // [rsp+88h] [rbp-78h] BYREF
  char v69; // [rsp+98h] [rbp-68h]
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  int v71; // [rsp+A8h] [rbp-58h]
  __int128 v72; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v74; // [rsp+C8h] [rbp-38h] BYREF
  int v75; // [rsp+D0h] [rbp-30h]
  __int128 v76; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-10h] BYREF
  int v79; // [rsp+F8h] [rbp-8h]
  __int128 v80; // [rsp+100h] [rbp+0h] BYREF
  __int64 v81; // [rsp+110h] [rbp+10h] BYREF
  wchar_t *v82; // [rsp+118h] [rbp+18h] BYREF
  wchar_t *v83; // [rsp+120h] [rbp+20h] BYREF
  int v84; // [rsp+128h] [rbp+28h] BYREF
  int v85[2]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v86; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_QWORD *)v62 = a6;
  v58 = a1;
  v68[1] = &vPackageStoreLock;
  v83 = a4;
  v7 = 0;
  v68[0] = &PackageTrackerLocker::`vftable';
  v82 = 0;
  *(_QWORD *)v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v86 = 0;
  v63 = 0;
  v84 = 0;
  v69 = 0;
  MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v68);
  if ( !a1 )
  {
    StoreObject = -2147024809;
    v84 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No session specified");
      v58 = (CCbsSession *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v11 = 2926;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)0x80070057LL,
      v57);
LABEL_183:
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v68);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v63);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v86);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v78);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v70);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v74);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v64);
    return (unsigned int)StoreObject;
  }
  if ( !a2 )
  {
    StoreObject = -2147024809;
    v84 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No package specified");
      v58 = (CCbsSession *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v11 = 2927;
    goto LABEL_13;
  }
  if ( !a5 )
  {
    StoreObject = -2147024809;
    v84 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Cannot add a package that is absent");
      v58 = (CCbsSession *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v11 = 2928;
    goto LABEL_13;
  }
  v12 = PackageStoreSetProperty(a1, L"LastMappingPackageCache", 0);
  if ( v12 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v12, "Not able to write last mapping package caching time");
  v60 = 0;
  ManifestPath = CCbsPackage::GetManifestPath(a2, a1, &v60);
  StoreObject = ManifestPath;
  if ( ManifestPath < 0 )
  {
    v84 = ManifestPath;
    if ( LogAdapter::g_Logger )
    {
      v14 = (CCbsSession *)&qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v14 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v14;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get manifest path for Package: {}",
        (__int64)&v58);
      v59 = (wchar_t *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v59);
    }
    v15 = 2940;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)(unsigned int)StoreObject,
      v57);
LABEL_23:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v60);
    goto LABEL_183;
  }
  v16 = v60;
  v82 = (wchar_t *)FileFromPath(v60);
  if ( !v82 )
  {
    StoreObject = -2147024809;
    v84 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      v58 = (CCbsSession *)v16;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Expected to find file in package manifest path: {}",
        (__int64)&v58);
      v59 = (wchar_t *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v59);
    }
    v15 = 2943;
    goto LABEL_22;
  }
  v17 = StorePackageManifestAndCatalog(a1, (CCbsPackage **)a2, a3);
  StoreObject = v17;
  if ( v17 < 0 )
  {
    v84 = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to stage package manifest.");
      v58 = (CCbsSession *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v15 = 2949;
    goto LABEL_22;
  }
  v18 = (CCbsIdentity *)*((_QWORD *)a2 + 14);
  v59 = 0;
  VersionlessStringId = CCbsIdentity::GetVersionlessStringId(v18, &v59);
  StoreObject = VersionlessStringId;
  if ( VersionlessStringId < 0 )
  {
    v84 = VersionlessStringId;
    if ( LogAdapter::g_Logger )
    {
      v20 = (CCbsSession *)&qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v20 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v20;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get versionless identity for package: {}",
        (__int64)&v58);
      *(_QWORD *)v85 = &v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v21 = 2957;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
      (const char *)(unsigned int)StoreObject,
      v57);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v59);
    goto LABEL_23;
  }
  v22 = v59;
  StoreObject = CCbsSession::GetStoreObject(a1, v59, 3, 1, &v74);
  if ( StoreObject < 0 )
  {
    v84 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get package index store object for package ");
      v58 = (CCbsSession *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v58);
    }
    v21 = 2961;
    goto LABEL_38;
  }
  v23 = (CCbsSession *)&qword_1802EB518;
  v24 = &qword_1802EB518;
  if ( *((_QWORD *)a2 + 15) )
    v24 = (const wchar_t *)*((_QWORD *)a2 + 15);
  v25 = CCbsStoreObject::SetValue((CCbsStoreObject *)&v74, v24, 0);
  StoreObject = v25;
  if ( v25 < 0 )
  {
    v84 = v25;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v23;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to store package index for package: {}",
        (__int64)&v58);
      *(_QWORD *)v85 = &v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v21 = 2965;
    goto LABEL_38;
  }
  SpecialPackageIndex = CCbsPackage::GetSpecialPackageIndex(a2);
  if ( SpecialPackageIndex )
  {
    StoreObject = CCbsSession::GetStoreObject(v58, SpecialPackageIndex, 3, 1, &v70);
    if ( StoreObject < 0 )
    {
      v84 = StoreObject;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get system index store object");
        v58 = (CCbsSession *)&v84;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v58);
      }
      v21 = 2976;
      goto LABEL_38;
    }
    v28 = &qword_1802EB518;
    if ( *((_QWORD *)a2 + 15) )
      v28 = (const wchar_t *)*((_QWORD *)a2 + 15);
    v29 = CCbsStoreObject::SetValue((CCbsStoreObject *)&v70, v28, 0);
    v27 = 0;
    StoreObject = v29;
    if ( v29 < 0 )
    {
      v84 = v29;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)a2 + 15) )
          v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
        v58 = v23;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to store package index for package: {}",
          (__int64)&v58);
        *(_QWORD *)v85 = &v84;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v85);
      }
      v21 = 2979;
      goto LABEL_38;
    }
  }
  v30 = &qword_1802EB518;
  if ( *((_QWORD *)a2 + 15) != v27 )
    v30 = (const wchar_t *)*((_QWORD *)a2 + 15);
  StoreObject = CCbsSession::GetStoreObject(v58, v30, 2, 1, v64);
  if ( StoreObject < 0 )
  {
    v84 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v23;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get package store registry key to write package manifest location for package: {}",
        (__int64)&v58);
      *(_QWORD *)v85 = &v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v21 = 2983;
    goto LABEL_38;
  }
  if ( v83 )
  {
    if ( *v83 )
    {
      v31 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"InstallClient", v83);
      if ( v31 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          2,
          (unsigned int)v31,
          "Unable to store package install client: {}, continuing...",
          &v83);
    }
  }
  v32 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"InstallName", v82);
  if ( v32 < 0 )
    LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
      2,
      (unsigned int)v32,
      "Unable to store package install name: {}, continuing...",
      &v82);
  v33 = v58;
  v34 = v58;
  *v82 = 0;
  if ( (int)CCbsPackage::GetInstallLocation(a2, v34, &v86) >= 0 )
  {
    v35 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"InstallLocation", v86);
    LogAdapter::TraceAtLevelIfFailed<long,AutoScz>(
      2,
      v35,
      "Unable to store package install location: {}, continuing...",
      &v86);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UninstallInstallGroup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_UninstallInstallGroup>::GetImpl'::`2'::impl) )
  {
    TargetState = CCbsPackage::GetTargetState(a2, v33, 0, (enum CbsState *)&v84);
    v37 = (unsigned int)TargetState;
    if ( TargetState < 0 )
    {
      v40 = &qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v40 = (const wchar_t *)*((_QWORD *)a2 + 15);
      *(_QWORD *)v85 = v40;
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
        1,
        v37,
        "Unable to get package target state for package: {}, continuing...",
        v85);
    }
    else if ( *((_BYTE *)v33 + 2254) && CCbsPackage::IsLCUPackage(a2) && a5 <= 64 )
    {
      v38 = SczAllocFromSz(&v63, *((_QWORD *)v33 + 80));
      if ( v38 >= 0 )
      {
        v7 = v63;
        *(_QWORD *)v85 = v63;
        v39 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"InstallGroup", v63);
        if ( v39 < 0 )
          LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
            2,
            (unsigned int)v39,
            "Unable to store package install group: {}, continuing...",
            v85);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x689,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageplanning.cpp",
          (const char *)(unsigned int)v38,
          v57);
        v7 = v63;
      }
    }
  }
  StoreObject = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"CurrentState", a5);
  if ( StoreObject < 0 )
  {
    v84 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v23;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to store current state for package: {}",
        (__int64)&v58);
      *(_QWORD *)v85 = &v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v21 = 3029;
    goto LABEL_38;
  }
  StoreObject = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"SelfUpdate", *((_DWORD *)a2 + 149));
  if ( StoreObject < 0 )
  {
    v84 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v23;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to set SelfUpdate property for package: {}",
        (__int64)&v58);
      *(_QWORD *)v85 = &v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v85);
    }
    v21 = 3032;
    goto LABEL_38;
  }
  v41 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"Visibility", 2u);
  StoreObject = v41;
  if ( v41 < 0 )
  {
    v85[0] = v41;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v23;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to write visibility for package: {}",
        (__int64)&v58);
      *(_QWORD *)v62 = v85;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v62);
    }
    v21 = 3040;
    goto LABEL_38;
  }
  v42 = *(_QWORD *)v62 + 152LL;
  if ( *(_QWORD *)v62 == -152 )
  {
    StoreObject = -2147467261;
    v84 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      if ( *((_QWORD *)a2 + 15) )
        v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
      v58 = v23;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get package owners for package: {}",
        (__int64)&v58);
      *(_QWORD *)v62 = &v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v62);
    }
    v21 = 3054;
    goto LABEL_38;
  }
  if ( *(_QWORD *)(*(_QWORD *)v62 + 176LL) )
  {
    v84 = 0;
    for ( i = 0; ; i = *(_QWORD *)v85 + 1LL )
    {
      *(_QWORD *)v85 = i;
      if ( i >= *(_QWORD *)(v42 + 24) )
        break;
      v44 = &qword_1802EB518;
      if ( *((_QWORD *)a2 + 15) )
        v44 = (const wchar_t *)*((_QWORD *)a2 + 15);
      if ( (unsigned __int8)StringsAreEqual(*(_QWORD *)(*(_QWORD *)(v42 + 40) + 8 * i), v44, 1) )
        goto LABEL_123;
    }
  }
  else
  {
LABEL_123:
    v84 = 1;
  }
  if ( !*((_BYTE *)a2 + 1062) )
    goto LABEL_143;
  v45 = &qword_1802EB518;
  if ( *((_QWORD *)a2 + 15) )
    v45 = (const wchar_t *)*((_QWORD *)a2 + 15);
  v61 = (int *)v45;
  if ( LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      1,
      1,
      (__int64)"Client specified that package {} is a baseline.",
      (__int64)&v61);
  StoreObject = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"Baseline", 1u);
  if ( StoreObject >= 0 )
  {
LABEL_143:
    if ( v84 )
    {
      if ( (unsigned int)CCbsSession::IsOffline(v58) && *((char *)v58 + 692) < 0 )
      {
        v48 = &qword_1802EB518;
        if ( *((_QWORD *)a2 + 15) )
          v48 = (const wchar_t *)*((_QWORD *)a2 + 15);
        v61 = (int *)v48;
        LogAdapter::TraceAtLevel<wchar_t const *>(
          1,
          "Client specified that session contains all baseline packages: {}",
          &v61);
        v49 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"Baseline", 1u);
        StoreObject = v49;
        if ( v49 < 0 )
        {
          v85[0] = v49;
          if ( LogAdapter::g_Logger )
          {
            if ( *((_QWORD *)a2 + 15) )
              v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
            v61 = (int *)v23;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to write baseline for package: {}",
              (__int64)&v61);
            *(_QWORD *)v62 = v85;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v62);
          }
          v21 = 3083;
          goto LABEL_38;
        }
      }
      if ( CCbsPackage::IsFODorLPPackage(a2) && !*((_BYTE *)a2 + 1063) )
      {
        v50 = &qword_1802EB518;
        if ( *((_QWORD *)a2 + 15) )
          v50 = (const wchar_t *)*((_QWORD *)a2 + 15);
        v61 = (int *)v50;
        LogAdapter::TraceAtLevel<wchar_t const *>(1, "Found baseline FOD or LP Package {}", &v61);
        v51 = CCbsStoreObject::SetValue((CCbsStoreObject *)v64, L"Baseline", 1u);
        StoreObject = v51;
        if ( v51 < 0 )
        {
          v85[0] = v51;
          if ( LogAdapter::g_Logger )
          {
            if ( *((_QWORD *)a2 + 15) )
              v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
            v61 = (int *)v23;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to write baseline for package: {}",
              (__int64)&v61);
            *(_QWORD *)v62 = v85;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v62);
          }
          v21 = 3090;
          goto LABEL_38;
        }
      }
    }
    v52 = StorePackageSources((CCbsStoreObject *)v64, a2);
    StoreObject = v52;
    if ( v52 >= 0 )
    {
      v53 = StorePackageDetects(v58, a2);
      StoreObject = v53;
      if ( v53 >= 0 )
      {
        updated = StoreUpdateDetects(v58, a2);
        StoreObject = updated;
        if ( updated >= 0 )
        {
          v55 = StoreComponentDependencies(v58, a2);
          StoreObject = v55;
          if ( v55 >= 0 )
          {
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v59);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v60);
            StoreObject = 0;
            goto LABEL_183;
          }
          v85[0] = v55;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist component dependencies.");
            v61 = v85;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v61);
          }
          v21 = 3104;
        }
        else
        {
          v85[0] = updated;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist update detects.");
            v61 = v85;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v61);
          }
          v21 = 3102;
        }
      }
      else
      {
        v85[0] = v53;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist package detects.");
          v61 = v85;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v61);
        }
        v21 = 3100;
      }
    }
    else
    {
      v85[0] = v52;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)a2 + 15) )
          v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
        v61 = (int *)v23;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to persist sources for package: {}",
          (__int64)&v61);
        *(_QWORD *)v62 = v85;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v62);
      }
      v21 = 3095;
    }
    goto LABEL_38;
  }
  v85[0] = StoreObject;
  if ( LogAdapter::g_Logger )
  {
    if ( *((_QWORD *)a2 + 15) )
      v23 = (CCbsSession *)*((_QWORD *)a2 + 15);
    v61 = (int *)v23;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"Failed to write baseline for package: {}",
      (__int64)&v61);
    *(_QWORD *)v62 = v85;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v62);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC04,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)(unsigned int)StoreObject,
    v57);
  if ( v22 )
    operator delete(v22 - 4, v46);
  if ( v16 )
    operator delete(v16 - 4, v46);
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v68);
  if ( v7 )
    operator delete(v7 - 4, v47);
  if ( v86 )
  {
    operator delete(v86 - 4, v47);
    v86 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v81);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v80 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v80);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v73);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v72 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v72);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v76 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v76);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((char *)&v66 + 8);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v66);
  return (unsigned int)StoreObject;
}

```

## disassembly

```asm
0x18000c7e8  push    rbp
0x18000c7ea  push    rbx
0x18000c7eb  push    rsi
0x18000c7ec  push    rdi
0x18000c7ed  push    r12
0x18000c7ef  push    r13
0x18000c7f1  push    r14
0x18000c7f3  push    r15
0x18000c7f5  lea     rbp, [rsp-58h]
0x18000c7fa  sub     rsp, 158h
0x18000c801  mov     rax, cs:__security_cookie
0x18000c808  xor     rax, rsp
0x18000c80b  mov     [rbp+90h+var_50], rax
0x18000c80f  mov     rax, [rbp+90h+arg_28]
0x18000c816  xor     r15d, r15d
0x18000c819  xorps   xmm0, xmm0
0x18000c81c  mov     qword ptr [rsp+190h+var_140], rax
0x18000c821  lea     rax, ?vPackageStoreLock@@3UMonitoredCritSec@@A; MonitoredCritSec vPackageStoreLock
0x18000c828  mov     [rsp+190h+var_160], rcx
0x18000c82d  mov     [rbp+90h+var_100], rax
0x18000c831  mov     r12, rcx
0x18000c834  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x18000c83b  mov     [rbp+90h+var_70], r9
0x18000c83f  mov     ebx, r15d
0x18000c842  mov     [rbp+90h+var_108], rax
0x18000c846  lea     rcx, [rbp+90h+var_108]; this
0x18000c84a  mov     [rbp+90h+var_78], r15
0x18000c84e  mov     rsi, r8
0x18000c851  mov     qword ptr [rsp+190h+var_130], r15
0x18000c856  mov     r13, rdx
0x18000c859  mov     [rsp+190h+var_128], r15d
0x18000c85e  movdqu  [rsp+190h+var_120], xmm0
0x18000c864  mov     [rbp+90h+var_110], r15
0x18000c868  mov     [rbp+90h+var_C8], r15
0x18000c86c  mov     [rbp+90h+var_C0], r15d
0x18000c870  movdqu  [rbp+90h+var_B8], xmm0
0x18000c875  mov     [rbp+90h+var_A8], r15
0x18000c879  mov     [rbp+90h+var_F0], r15
0x18000c87d  mov     [rbp+90h+var_E8], r15d
0x18000c881  movdqu  [rbp+90h+var_E0], xmm0
0x18000c886  mov     [rbp+90h+var_D0], r15
0x18000c88a  mov     [rbp+90h+var_A0], r15
0x18000c88e  mov     [rbp+90h+var_98], r15d
0x18000c892  movdqu  [rbp+90h+var_90], xmm0
0x18000c897  mov     [rbp+90h+var_80], r15
0x18000c89b  mov     [rbp+90h+var_58], r15
0x18000c89f  mov     [rsp+190h+var_138], rbx
0x18000c8a4  mov     [rbp+90h+var_68], r15d
0x18000c8a8  mov     [rbp+90h+var_F8], r15b
0x18000c8ac  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x18000c8b1  test    r12, r12
0x18000c8b4  jnz     short loc_18000C917
0x18000c8b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c8bd  mov     r14d, 80070057h
0x18000c8c3  mov     [rbp+90h+var_68], r14d
0x18000c8c7  test    rcx, rcx
0x18000c8ca  jz      short loc_18000C90D
0x18000c8cc  lea     r15d, [r12+3]
0x18000c8d1  xor     edx, edx
0x18000c8d3  mov     r8d, r15d
0x18000c8d6  lea     r9, aNoSessionSpeci_0; "No session specified"
0x18000c8dd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000c8e2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c8e9  lea     rax, [rbp+90h+var_68]
0x18000c8ed  mov     [rsp+190h+var_160], rax
0x18000c8f2  lea     r9, asc_1802EE7AC; ": {}"
0x18000c8f9  lea     rax, [rsp+190h+var_160]
0x18000c8fe  mov     r8d, r15d
0x18000c901  mov     dl, 1
0x18000c903  mov     qword ptr [rsp+190h+var_170], rax
0x18000c908  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000c90d  mov     edx, 0B6Eh
0x18000c912  jmp     loc_18000C9DF
0x18000c917  test    r13, r13
0x18000c91a  jnz     short loc_18000C979
0x18000c91c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c923  mov     r14d, 80070057h
0x18000c929  mov     [rbp+90h+var_68], r14d
0x18000c92d  test    rcx, rcx
0x18000c930  jz      short loc_18000C972
0x18000c932  lea     r15d, [r13+3]
0x18000c936  xor     edx, edx
0x18000c938  mov     r8d, r15d
0x18000c93b  lea     r9, aNoPackageSpeci; "No package specified"
0x18000c942  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000c947  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c94e  lea     rax, [rbp+90h+var_68]
0x18000c952  mov     [rsp+190h+var_160], rax
0x18000c957  lea     r9, asc_1802EE7AC; ": {}"
0x18000c95e  lea     rax, [rsp+190h+var_160]
0x18000c963  mov     r8d, r15d
0x18000c966  mov     dl, 1
0x18000c968  mov     qword ptr [rsp+190h+var_170], rax
0x18000c96d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000c972  mov     edx, 0B6Fh
0x18000c977  jmp     short loc_18000C9DF
0x18000c979  cmp     [rbp+90h+arg_20], r15d
0x18000c980  jnz     short loc_18000C9FA
0x18000c982  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c989  mov     r14d, 80070057h
0x18000c98f  mov     [rbp+90h+var_68], r14d
0x18000c993  test    rcx, rcx
0x18000c996  jz      short loc_18000C9DA
0x18000c998  mov     r15d, 3
0x18000c99e  lea     r9, aCannotAddAPack; "Cannot add a package that is absent"
0x18000c9a5  mov     r8d, r15d
0x18000c9a8  xor     edx, edx
0x18000c9aa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000c9af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000c9b6  lea     rax, [rbp+90h+var_68]
0x18000c9ba  mov     [rsp+190h+var_160], rax
0x18000c9bf  lea     r9, asc_1802EE7AC; ": {}"
0x18000c9c6  lea     rax, [rsp+190h+var_160]
0x18000c9cb  mov     r8d, r15d
0x18000c9ce  mov     dl, 1
0x18000c9d0  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000c9d5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000c9da  mov     edx, 0B70h; void *
0x18000c9df  mov     rcx, [rbp+98h]; this
0x18000c9e6  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000c9ed  mov     r9d, r14d; char *
0x18000c9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9f5  jmp     loc_18000D8A5
0x18000c9fa  xor     r8d, r8d; unsigned int
0x18000c9fd  lea     rdx, aLastmappingpac; "LastMappingPackageCache"
0x18000ca04  mov     rcx, r12; struct CCbsSession *
0x18000ca07  call    ?PackageStoreSetProperty@@YAJPEAVCCbsSession@@PEB_WK@Z; PackageStoreSetProperty(CCbsSession *,wchar_t const *,ulong)
0x18000ca0c  test    eax, eax
0x18000ca0e  jns     short loc_18000CA23
0x18000ca10  lea     r8, aNotAbleToWrite; "Not able to write last mapping package "...
0x18000ca17  mov     edx, eax
0x18000ca19  mov     ecx, 2
0x18000ca1e  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18000ca23  lea     r8, [rsp+190h+var_150]; wchar_t **
0x18000ca28  mov     [rsp+190h+var_150], r15
0x18000ca2d  mov     rdx, r12; struct CCbsSession *
0x18000ca30  mov     rcx, r13; this
0x18000ca33  call    ?GetManifestPath@CCbsPackage@@QEAAJPEAVCCbsSession@@PEAPEA_W@Z; CCbsPackage::GetManifestPath(CCbsSession *,wchar_t * *)
0x18000ca38  mov     r14d, eax
0x18000ca3b  test    eax, eax
0x18000ca3d  jns     loc_18000CADD
0x18000ca43  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ca4a  mov     [rbp+90h+var_68], eax
0x18000ca4d  test    rcx, rcx
0x18000ca50  jz      short loc_18000CAB3
0x18000ca52  cmp     [r13+78h], r15
0x18000ca56  lea     rax, [rsp+190h+var_160]
0x18000ca5b  lea     r12, qword_1802EB518
0x18000ca62  mov     qword ptr [rsp+190h+var_170], rax
0x18000ca67  cmovnz  r12, [r13+78h]
0x18000ca6c  lea     r9, aFailedToGetMan_1; "Failed to get manifest path for Package"...
0x18000ca73  mov     r15d, 3
0x18000ca79  mov     [rsp+190h+var_160], r12
0x18000ca7e  xor     edx, edx
0x18000ca80  mov     r8d, r15d
0x18000ca83  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000ca88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ca8f  lea     rax, [rbp+90h+var_68]
0x18000ca93  mov     [rsp+190h+var_158], rax
0x18000ca98  lea     r9, asc_1802EE7AC; ": {}"
0x18000ca9f  lea     rax, [rsp+190h+var_158]
0x18000caa4  mov     r8d, r15d
0x18000caa7  mov     dl, 1
0x18000caa9  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000caae  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cab3  mov     edx, 0B7Ch; void *
0x18000cab8  mov     rcx, [rbp+98h]; this
0x18000cabf  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000cac6  mov     r9d, r14d; char *
0x18000cac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cace  lea     rcx, [rsp+190h+var_150]
0x18000cad3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000cad8  jmp     loc_18000D8A5
0x18000cadd  mov     rdi, [rsp+190h+var_150]
0x18000cae2  mov     rcx, rdi
0x18000cae5  call    FileFromPath
0x18000caea  mov     [rbp+90h+var_78], rax
0x18000caee  test    rax, rax
0x18000caf1  jnz     short loc_18000CB64
0x18000caf3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cafa  mov     r14d, 80070057h
0x18000cb00  mov     [rbp+90h+var_68], r14d
0x18000cb04  test    rcx, rcx
0x18000cb07  jz      short loc_18000CB5A
0x18000cb09  lea     rax, [rsp+190h+var_160]
0x18000cb0e  mov     [rsp+190h+var_160], rdi
0x18000cb13  mov     r15d, 3
0x18000cb19  mov     qword ptr [rsp+190h+var_170], rax
0x18000cb1e  mov     r8d, r15d
0x18000cb21  lea     r9, aExpectedToFind; "Expected to find file in package manife"...
0x18000cb28  xor     edx, edx
0x18000cb2a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000cb2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cb36  lea     rax, [rbp+90h+var_68]
0x18000cb3a  mov     [rsp+190h+var_158], rax
0x18000cb3f  lea     r9, asc_1802EE7AC; ": {}"
0x18000cb46  lea     rax, [rsp+190h+var_158]
0x18000cb4b  mov     r8d, r15d
0x18000cb4e  mov     dl, 1
0x18000cb50  mov     qword ptr [rsp+190h+var_170], rax
0x18000cb55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cb5a  mov     edx, 0B7Fh
0x18000cb5f  jmp     loc_18000CAB8
0x18000cb64  mov     r8, rsi
0x18000cb67  mov     rdx, r13
0x18000cb6a  mov     rcx, r12
0x18000cb6d  call    StorePackageManifestAndCatalog
0x18000cb72  mov     r14d, eax
0x18000cb75  test    eax, eax
0x18000cb77  jns     short loc_18000CBD4
0x18000cb79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cb80  mov     [rbp+90h+var_68], eax
0x18000cb83  test    rcx, rcx
0x18000cb86  jz      short loc_18000CBCA
0x18000cb88  mov     r15d, 3
0x18000cb8e  lea     r9, aFailedToStageP; "Failed to stage package manifest."
0x18000cb95  mov     r8d, r15d
0x18000cb98  xor     edx, edx
0x18000cb9a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000cb9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cba6  lea     rax, [rbp+90h+var_68]
0x18000cbaa  mov     [rsp+190h+var_160], rax
0x18000cbaf  lea     r9, asc_1802EE7AC; ": {}"
0x18000cbb6  lea     rax, [rsp+190h+var_160]
0x18000cbbb  mov     r8d, r15d
0x18000cbbe  mov     dl, 1
0x18000cbc0  mov     qword ptr [rsp+190h+var_170], rax
0x18000cbc5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cbca  mov     edx, 0B85h
0x18000cbcf  jmp     loc_18000CAB8
0x18000cbd4  mov     rcx, [r13+70h]; this
0x18000cbd8  lea     rdx, [rsp+190h+var_158]; wchar_t **
0x18000cbdd  mov     [rsp+190h+var_158], r15
0x18000cbe2  call    ?GetVersionlessStringId@CCbsIdentity@@QEAAJPEAPEA_W@Z; CCbsIdentity::GetVersionlessStringId(wchar_t * *)
0x18000cbe7  mov     r14d, eax
0x18000cbea  test    eax, eax
0x18000cbec  jns     loc_18000CC8A
0x18000cbf2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cbf9  mov     [rbp+90h+var_68], eax
0x18000cbfc  test    rcx, rcx
0x18000cbff  jz      short loc_18000CC60
0x18000cc01  cmp     [r13+78h], r15
0x18000cc05  lea     rax, [rsp+190h+var_160]
0x18000cc0a  lea     r12, qword_1802EB518
0x18000cc11  mov     qword ptr [rsp+190h+var_170], rax
0x18000cc16  cmovnz  r12, [r13+78h]
0x18000cc1b  lea     r9, aFailedToGetVer_6; "Failed to get versionless identity for "...
0x18000cc22  mov     r15d, 3
0x18000cc28  mov     [rsp+190h+var_160], r12
0x18000cc2d  xor     edx, edx
0x18000cc2f  mov     r8d, r15d
0x18000cc32  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18000cc37  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cc3e  lea     rax, [rbp+90h+var_68]
0x18000cc42  mov     qword ptr [rbp+90h+var_60], rax
0x18000cc46  lea     r9, asc_1802EE7AC; ": {}"
0x18000cc4d  lea     rax, [rbp+90h+var_60]
0x18000cc51  mov     r8d, r15d
0x18000cc54  mov     dl, 1
0x18000cc56  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000cc5b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cc60  mov     edx, 0B8Dh; void *
0x18000cc65  mov     rcx, [rbp+98h]; this
0x18000cc6c  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18000cc73  mov     r9d, r14d; char *
0x18000cc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc7b  lea     rcx, [rsp+190h+var_158]
0x18000cc80  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18000cc85  jmp     loc_18000CACE
0x18000cc8a  mov     rsi, [rsp+190h+var_158]
0x18000cc8f  lea     rax, [rbp+90h+var_C8]
0x18000cc93  mov     r9d, 1
0x18000cc99  mov     qword ptr [rsp+190h+var_170], rax
0x18000cc9e  mov     rdx, rsi
0x18000cca1  mov     rcx, r12
0x18000cca4  lea     r15d, [r9+2]
0x18000cca8  mov     r8d, r15d
0x18000ccab  call    ?GetStoreObject@CCbsSession@@QEAAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsSession::GetStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x18000ccb0  mov     r14d, eax
0x18000ccb3  xor     eax, eax
0x18000ccb5  test    r14d, r14d
0x18000ccb8  jns     short loc_18000CD10
0x18000ccba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000ccc1  mov     [rbp+90h+var_68], r14d
0x18000ccc5  test    rcx, rcx
0x18000ccc8  jz      short loc_18000CD06
0x18000ccca  lea     r9, aFailedToGetPac_25; "Failed to get package index store objec"...
0x18000ccd1  mov     r8d, r15d
0x18000ccd4  xor     edx, edx
0x18000ccd6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18000ccdb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000cce2  lea     rax, [rbp+90h+var_68]
0x18000cce6  mov     [rsp+190h+var_160], rax
0x18000cceb  lea     r9, asc_1802EE7AC; ": {}"
0x18000ccf2  lea     rax, [rsp+190h+var_160]
0x18000ccf7  mov     r8d, r15d
0x18000ccfa  mov     dl, 1
0x18000ccfc  mov     qword ptr [rsp+190h+var_170], rax
0x18000cd01  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18000cd06  mov     edx, 0B91h
  ... truncated ...
```
