# CCbsStoreRepairExecutionObject::RepairDriverFileHardlinks(void)

- ea: `0x180191210`
- end: `0x1801921de`
- name: `?RepairDriverFileHardlinks@CCbsStoreRepairExecutionObject@@IEAAJXZ`
- size: `4046`
- prototype: `__int64 __fastcall(CCbsStoreRepairExecutionObject *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801921e4`

## callees

- `0x18000b2c0`
- `0x180010138`
- `0x180010cc0`
- `0x180011a14`
- `0x180013018`
- `0x180013250`
- `0x1800132a4`
- `0x1800138b8`
- `0x180015420`
- `0x180018a64`
- `0x180023ca8`
- `0x1800261e0`
- `0x180028e24`
- `0x18002c43c`
- `0x1800345f0`
- `0x180042448`
- `0x180044d30`
- `0x1800458e0`
- `0x180045c24`
- `0x18004b1b8`
- `0x180059a00`
- `0x18005ec58`
- `0x180066c28`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800d1718`
- `0x1800d8a84`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x1800ec920`
- `0x18012a0c8`
- `0x180145fd0`
- `0x18014a984`
- `0x180191210`
- `0x1801a8a84`
- `0x1801b3168`
- `0x1801c1498`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180191764`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180191764`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801915e5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801915e5`

## string_xrefs

- `0x18019144b`: `Failed opening driver update context`
- `0x180191b82`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180191bb3`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180191c50`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180191da3`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180192023`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18019212e`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18019218e`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180191797`: `Failed to get deployment identity for package {}, update {}`
- `0x1801920da`: `Failed opening hash object for inf: {}`
- `0x1801913dd`: `Failed getting CbsStoreObjectDrivers registry key`
- `0x18019135e`: `Failed to get package store directory.`
- `0x180191e44`: `Failed to get updates to pend with package: {}`
- `0x180191f1f`: `Failed to create package`
- `0x180191f73`: `Failed to read manifest content.`
- `0x180191d48`: `Failed copying driver file name for hash: {}`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::RepairDriverFileHardlinks(CCbsSession **this)
{
  unsigned int v1; // edi
  CCbsStoreRepairExecutionObject *v2; // r13
  CCbsSession *v3; // rcx
  CCbsSession *v4; // rcx
  int OfflineWindowsDirectory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int WindowsDirectory; // eax
  unsigned __int64 v9; // r9
  int v10; // eax
  int PackageStoreDirectory; // eax
  int StoreObject; // eax
  int v13; // eax
  void *v14; // rax
  __int64 v15; // rsi
  unsigned int v16; // ebx
  const wchar_t *v17; // r12
  unsigned int v18; // edx
  __int64 v19; // rbx
  wchar_t *v20; // rdi
  int WindowsUpdatePackage; // edi
  __int64 v22; // rdi
  CCbsPackage *v23; // rdi
  __int64 v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdi
  const wchar_t *v29; // rcx
  int CsiDeploymentIdentities; // eax
  const wchar_t *v31; // rcx
  const wchar_t *v32; // rdx
  struct IDefinitionIdentity **v33; // r13
  const wchar_t *v34; // rcx
  int v35; // eax
  unsigned int v36; // edi
  __int64 v37; // rcx
  __int64 v38; // rcx
  int updated; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rcx
  int *v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v48; // [rsp+28h] [rbp-D8h]
  wchar_t *v49; // [rsp+30h] [rbp-D0h]
  wchar_t *v50; // [rsp+38h] [rbp-C8h]
  wchar_t *v51; // [rsp+40h] [rbp-C0h]
  wchar_t *v52; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 InitPointer; // [rsp+68h] [rbp-98h]
  _QWORD *i; // [rsp+70h] [rbp-90h] BYREF
  CCbsPackage *v58; // [rsp+78h] [rbp-88h] BYREF
  int v59[2]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *Str; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  struct HDRIVERUPDATECONTEXT__ *v62; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v63; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v64; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v65[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v66[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v67; // [rsp+D0h] [rbp-30h]
  unsigned int v68; // [rsp+D4h] [rbp-2Ch]
  unsigned int v69; // [rsp+D8h] [rbp-28h]
  struct IDefinitionIdentity **v70; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v71; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v72; // [rsp+F0h] [rbp-10h]
  const wchar_t *v73; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v74; // [rsp+100h] [rbp+0h] BYREF
  int v75; // [rsp+108h] [rbp+8h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  __int64 v77; // [rsp+120h] [rbp+20h]
  unsigned int v78; // [rsp+128h] [rbp+28h] BYREF
  wchar_t *v79; // [rsp+130h] [rbp+30h] BYREF
  __int64 v80; // [rsp+138h] [rbp+38h] BYREF
  int v81; // [rsp+140h] [rbp+40h]
  __int128 v82; // [rsp+148h] [rbp+48h]
  __int64 v83; // [rsp+158h] [rbp+58h]
  __int64 v84; // [rsp+160h] [rbp+60h] BYREF
  int v85; // [rsp+168h] [rbp+68h]
  int v86[4]; // [rsp+170h] [rbp+70h]
  __int64 v87; // [rsp+180h] [rbp+80h]
  __int64 v88; // [rsp+188h] [rbp+88h] BYREF
  int v89; // [rsp+190h] [rbp+90h]
  __int128 v90; // [rsp+198h] [rbp+98h]
  __int64 v91; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v92; // [rsp+1B0h] [rbp+B0h] BYREF
  int v93[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v94; // [rsp+1C0h] [rbp+C0h]
  __int128 v95; // [rsp+1C8h] [rbp+C8h]
  __int64 v96; // [rsp+1D8h] [rbp+D8h]
  _BYTE v97[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v98[24]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v99; // [rsp+238h] [rbp+138h]
  struct IDefinitionIdentity **v100; // [rsp+248h] [rbp+148h]
  wchar_t v101[268]; // [rsp+260h] [rbp+160h] BYREF
  int v102; // [rsp+478h] [rbp+378h]
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v1 = 0;
  *(_QWORD *)v59 = this;
  v74 = 0;
  v2 = (CCbsStoreRepairExecutionObject *)this;
  v75 = 0;
  v3 = this[6];
  v76 = 0;
  v77 = 0;
  *(_QWORD *)v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v71 = 0;
  v64 = 0;
  v62 = 0;
  if ( (unsigned int)CCbsSession::IsOffline(v3) )
  {
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v4, &v64);
    v6 = OfflineWindowsDirectory;
    if ( OfflineWindowsDirectory < 0 )
    {
      v78 = OfflineWindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get offline Windir");
        v62 = (struct HDRIVERUPDATECONTEXT__ *)&v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v62);
      }
      v7 = 4055;
      goto LABEL_125;
    }
  }
  else
  {
    WindowsDirectory = PathGetWindowsDirectory(&v64, 0);
    v6 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v9 = (unsigned int)WindowsDirectory;
      v7 = 4059;
LABEL_126:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)v9,
        (int)v46);
      goto LABEL_127;
    }
  }
  v10 = SczAllocConcatSz(&v64, L"WinSxS");
  v6 = v10;
  if ( v10 < 0 )
  {
    v9 = (unsigned int)v10;
    v7 = 4062;
    goto LABEL_126;
  }
  PackageStoreDirectory = CCbsSession::GetPackageStoreDirectory(*((CCbsSession **)v2 + 6), &v71);
  v6 = PackageStoreDirectory;
  if ( PackageStoreDirectory < 0 )
  {
    v78 = PackageStoreDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get package store directory.");
      v62 = (struct HDRIVERUPDATECONTEXT__ *)&v78;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v62);
    }
    v7 = 4064;
    goto LABEL_125;
  }
  StoreObject = CCbsSession::GetStoreObject(*((_QWORD *)v2 + 6), 0, 10, 0, v93);
  v6 = StoreObject;
  if ( StoreObject < 0 )
  {
    v78 = StoreObject;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting CbsStoreObjectDrivers registry key");
      v62 = (struct HDRIVERUPDATECONTEXT__ *)&v78;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v62);
    }
    v7 = 4067;
    goto LABEL_125;
  }
  v13 = DirectDriverOpenContext(*((_QWORD *)v2 + 6), &v62);
  v6 = v13;
  if ( v13 < 0 )
  {
    v78 = v13;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed opening driver update context");
      v62 = (struct HDRIVERUPDATECONTEXT__ *)&v78;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v62);
    }
    v7 = 4069;
    goto LABEL_125;
  }
  v14 = operator new(0x40u);
  if ( !v14 || (v15 = CCbsArray<_DRIVER_UPDATE>::CCbsArray<_DRIVER_UPDATE>(v14)) == 0 )
  {
    v6 = -2147024882;
    v7 = 4071;
LABEL_125:
    v9 = v6;
    goto LABEL_126;
  }
  v88 = 0;
  v16 = 0;
  v89 = 0;
  v78 = 0;
  v91 = 0;
  v90 = 0;
  if ( CCbsStoreObject::EnumChildren((CCbsStoreObject *)v93, 0, (struct CCbsStoreObject *)&v88) == -2147024637 )
    goto LABEL_70;
  v17 = &qword_1802EB518;
  while ( 1 )
  {
    v69 = 0;
    v84 = 0;
    v85 = 0;
    v87 = 0;
    *(_OWORD *)v86 = 0;
    memset_0(v101, 0, 0x220u);
    CCbsStringArray::CCbsStringArray((CCbsStringArray *)v97);
    v102 = 17;
    if ( CCbsStoreObject::EnumChildren((CCbsStoreObject *)&v88, 0, (struct CCbsStoreObject *)&v84) != -2147024637 )
      break;
LABEL_69:
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v97);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v84);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v88);
    v1 = 0;
    ++v16;
    v88 = 0;
    v78 = v16;
    v89 = 0;
    v91 = 0;
    v90 = 0;
    if ( CCbsStoreObject::EnumChildren((CCbsStoreObject *)v93, v16, (struct CCbsStoreObject *)&v88) == -2147024637 )
    {
LABEL_70:
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v88);
      if ( !*(_QWORD *)(v15 + 24)
        || (updated = DrupDriverUpdateStageUpdates(
                        v62,
                        *(struct _DRIVER_UPDATE **)(v15 + 40),
                        *(_DWORD *)(v15 + 24),
                        WimFileFetcher::Type,
                        0),
            v6 = updated,
            updated >= 0) )
      {
        (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v64);
        CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v93);
        CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v74);
        return 0;
      }
      v78 = updated;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed re-staging drivers.");
        *(_QWORD *)v59 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1082,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)v6,
        v47);
      goto LABEL_75;
    }
  }
  while ( 1 )
  {
    v68 = 0;
    v80 = 0;
    v81 = 0;
    v83 = 0;
    v82 = 0;
    v6 = CCbsStoreObject::EnumChildren((CCbsStoreObject *)&v84, 0, (struct CCbsStoreObject *)&v80);
    if ( v6 != -2147024637 )
      break;
LABEL_67:
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v80);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v97);
    CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v84);
    v84 = 0;
    ++v1;
    v85 = 0;
    v69 = v1;
    v87 = 0;
    *(_OWORD *)v86 = 0;
    memset_0(v101, 0, 0x220u);
    CCbsStringArray::CCbsStringArray((CCbsStringArray *)v97);
    v102 = 17;
    if ( CCbsStoreObject::EnumChildren((CCbsStoreObject *)&v88, v1, (struct CCbsStoreObject *)&v84) == -2147024637 )
    {
      v16 = v78;
      goto LABEL_69;
    }
  }
LABEL_28:
  v18 = 0;
  if ( (v6 & 0x80000000) != 0 )
  {
    v78 = v6;
    if ( LogAdapter::g_Logger )
    {
      if ( *(_QWORD *)&v86[2] )
        v17 = *(const wchar_t **)&v86[2];
      *(_QWORD *)v59 = v17;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed opening hash object for inf: {}",
        (__int64)v59);
      *(_QWORD *)v66 = &v78;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v66);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100D,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)v6,
      (int)v46);
    goto LABEL_79;
  }
  v67 = 0;
  v19 = 0;
  Str = 0;
  v61 = 0;
  v79 = 0;
  v92 = 0;
  v58 = 0;
  for ( i = 0; ; i = 0 )
  {
    WindowsUpdatePackage = CCbsStoreObject::EnumNumericValue((CCbsStoreObject *)&v80, v18, &Str, 0);
    if ( WindowsUpdatePackage == -2147024637 )
    {
      if ( i )
      {
        v38 = (__int64)i + *(int *)(i[1] + 4LL) + 8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        i = 0;
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v58);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v80);
      v80 = 0;
      ++v68;
      v81 = 0;
      v83 = 0;
      v82 = 0;
      v6 = CCbsStoreObject::EnumChildren((CCbsStoreObject *)&v84, v68, (struct CCbsStoreObject *)&v80);
      if ( v6 == -2147024637 )
      {
        v1 = v69;
        goto LABEL_67;
      }
      goto LABEL_28;
    }
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)&v82 + 1) )
          v17 = (const wchar_t *)*((_QWORD *)&v82 + 1);
        *(_QWORD *)v59 = v17;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to enumerate all packages for hash: {}",
          (__int64)v59);
        *(_QWORD *)v66 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v66);
      }
      v44 = 4126;
LABEL_114:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v44,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)WindowsUpdatePackage,
        (int)v46);
LABEL_115:
      if ( i )
      {
        v45 = (__int64)i + *(int *)(i[1] + 4LL) + 8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        i = 0;
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v58);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v80);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v97);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v84);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v88);
      (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
      v6 = WindowsUpdatePackage;
      goto LABEL_127;
    }
    v20 = wcsrchr(Str, 0x7Eu);
    if ( v20 )
    {
      v6 = SczAllocFromSz(&v61, v20 + 1);
      if ( (v6 & 0x80000000) == 0 )
      {
        v19 = v61;
        *v20 = 0;
        goto LABEL_34;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1023,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)v6,
        (int)v46);
      if ( i )
      {
        v40 = (__int64)i + *(int *)(i[1] + 4LL) + 8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        i = 0;
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v58);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
LABEL_79:
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v80);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v97);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v84);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v88);
LABEL_75:
      (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
LABEL_127:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v64);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v93);
      CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v74);
      return v6;
    }
LABEL_34:
    WindowsUpdatePackage = ReadAndConcatenateManifestFromStore(
                             v71,
                             Str,
                             (struct CCbsStringArray *)v97,
                             0,
                             &v79,
                             &v92,
                             0,
                             0,
                             0,
                             0,
                             0);
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to read manifest content.");
        *(_QWORD *)v59 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v44 = 4148;
      goto LABEL_114;
    }
    v22 = *((_QWORD *)v2 + 6);
    InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v58);
    LODWORD(v55) = 0;
    v54 = 0;
    LODWORD(v53) = 0;
    v52 = 0;
    v51 = 0;
    v50 = v79;
    LODWORD(v49) = 3;
    LODWORD(v48) = 0;
    v46 = v66;
    *(GUID *)v66 = GUID_NULL;
    WindowsUpdatePackage = CCbsSession::CreateWindowsUpdatePackage(v22, 0, 0, 0);
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create package");
        *(_QWORD *)v59 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v44 = 4158;
      goto LABEL_114;
    }
    WindowsUpdatePackage = CCbsPackage::MakeSurePackageIsFullyInitialized(v58, *((struct CCbsSession **)v2 + 6));
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)v58 + 15) )
          v17 = (const wchar_t *)*((_QWORD *)v58 + 15);
        *(_QWORD *)v59 = v17;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to fully initialize package: {}",
          (__int64)v59);
        *(_QWORD *)v66 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v66);
      }
      v44 = 4161;
      goto LABEL_114;
    }
    v23 = v58;
    v24 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&i);
    WindowsUpdatePackage = CCbsPackage::GetUpdates(v23, v24);
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)v58 + 15) )
          v17 = (const wchar_t *)*((_QWORD *)v58 + 15);
        *(_QWORD *)v59 = v17;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get updates to pend with package: {}",
          (__int64)v59);
        *(_QWORD *)v66 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v66);
      }
      v44 = 4164;
      goto LABEL_114;
    }
    v25 = i;
    v26 = (_QWORD *)i[5];
    v27 = i[3];
    v72 = v26;
    *(_QWORD *)v66 = &v26[v27];
    if ( v26 == *(_QWORD **)v66 )
      goto LABEL_59;
LABEL_39:
    v28 = *v26;
    v63 = 0;
    v65[0] = 0;
    CCbsInterfaceArray<ICbsUIHandler *>::CCbsInterfaceArray<ICbsUIHandler *>(v98);
    v29 = &qword_1802EB518;
    if ( *(_QWORD *)(v28 + 32) )
      v29 = *(const wchar_t **)(v28 + 32);
    if ( !(unsigned int)_o__wcsicmp(v29, v19) )
      break;
LABEL_57:
    CCbsArrayBase<ICbsUIHandler *,CCbsInterfaceArray<ICbsUIHandler *>>::~CCbsArrayBase<ICbsUIHandler *,CCbsInterfaceArray<ICbsUIHandler *>>(v98);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v65);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v63);
    v26 = v72 + 1;
    v72 = v26;
    if ( v26 != *(_QWORD **)v66 )
      goto LABEL_39;
    v25 = i;
    v2 = *(CCbsStoreRepairExecutionObject **)v59;
LABEL_59:
    if ( v25 )
    {
      v37 = (__int64)v25 + *(int *)(v25[1] + 4LL) + 8;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      i = 0;
    }
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v58);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
    v19 = 0;
    Str = 0;
    v18 = ++v67;
    v61 = 0;
    v79 = 0;
    v92 = 0;
    v58 = 0;
  }
  CsiDeploymentIdentities = CCbsUpdate::GetCsiDeploymentIdentities(v28, v98);
  if ( CsiDeploymentIdentities < 0 )
  {
    v31 = &qword_1802EB518;
    if ( *(_QWORD *)(v28 + 32) )
      v31 = *(const wchar_t **)(v28 + 32);
    v32 = &qword_1802EB518;
    v70 = (struct IDefinitionIdentity **)v31;
    if ( *((_QWORD *)v58 + 15) )
      v32 = (const wchar_t *)*((_QWORD *)v58 + 15);
    v73 = v32;
    LogAdapter::TraceAtLevelIfFailed<long,wchar_t const *,wchar_t const *>(
      3,
      CsiDeploymentIdentities,
      (unsigned int)"Failed to get deployment identity for package {}, update {}",
      (unsigned int)&v73,
      (__int64)&v70);
    goto LABEL_57;
  }
  v33 = v100;
  v70 = &v100[v99];
  if ( v100 == v70 )
    goto LABEL_57;
  while ( 2 )
  {
    WindowsUpdatePackage = GetKeyFormFromDefinitionIdentity(*v33, v65);
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get keyform from identity");
        *(_QWORD *)v59 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v43 = 4190;
      goto LABEL_88;
    }
    v34 = &qword_1802EB518;
    if ( *(_QWORD *)&v86[2] )
      v34 = *(const wchar_t **)&v86[2];
    WindowsUpdatePackage = SczAllocFormatted(
                             &v63,
                             L"%ws\\%ws\\%ws",
                             v64,
                             v65[0],
                             v34,
                             v48,
                             v49,
                             v50,
                             v51,
                             v52,
                             v53,
                             v54,
                             v55,
                             InitPointer);
    if ( WindowsUpdatePackage < 0 )
    {
      v43 = 4198;
LABEL_88:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v43,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)WindowsUpdatePackage,
        (int)v46);
      CCbsArrayBase<ICbsUIHandler *,CCbsInterfaceArray<ICbsUIHandler *>>::~CCbsArrayBase<ICbsUIHandler *,CCbsInterfaceArray<ICbsUIHandler *>>(v98);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v65);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v63);
      goto LABEL_115;
    }
    if ( !(unsigned int)DoesFileExist(v63, 0) )
      goto LABEL_56;
    WindowsUpdatePackage = StringCchCopyW(v101, 0x104u, v63);
    if ( WindowsUpdatePackage < 0 )
    {
      v78 = WindowsUpdatePackage;
      if ( LogAdapter::g_Logger )
      {
        if ( *((_QWORD *)&v82 + 1) )
          v17 = (const wchar_t *)*((_QWORD *)&v82 + 1);
        *(_QWORD *)v59 = v17;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed copying driver file name for hash: {}",
          (__int64)v59);
        *(_QWORD *)v66 = &v78;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v66);
      }
      v43 = 4207;
      goto LABEL_88;
    }
    v35 = CCbsArrayBase<_DRIVER_UPDATE,CCbsArray<_DRIVER_UPDATE>>::InsertAt(v15, v101, *(_QWORD *)(v15 + 24));
    v36 = v35;
    if ( v35 >= 0 )
    {
LABEL_56:
      if ( ++v33 == v70 )
        goto LABEL_57;
      continue;
    }
    break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1071,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
    (const char *)(unsigned int)v35,
    (int)v46);
  CCbsArrayBase<ICbsUIHandler *,CCbsInterfaceArray<ICbsUIHandler *>>::~CCbsArrayBase<ICbsUIHandler *,CCbsInterfaceArray<ICbsUIHandler *>>(v98);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v65);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v63);
  if ( i )
  {
    v41 = (__int64)i + *(int *)(i[1] + 4LL) + 8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    i = 0;
  }
  Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v58);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v61);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v80);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v97);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v84);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v88);
  (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v64);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v93);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v74);
  return v36;
}

```

## disassembly

```asm
0x180191210  push    rbp
0x180191212  push    rbx
0x180191213  push    rsi
0x180191214  push    rdi
0x180191215  push    r12
0x180191217  push    r13
0x180191219  push    r14
0x18019121b  push    r15
0x18019121d  lea     rbp, [rsp-398h]
0x180191225  sub     rsp, 498h
0x18019122c  mov     rax, cs:__security_cookie
0x180191233  xor     rax, rsp
0x180191236  mov     [rbp+3D0h+var_50], rax
0x18019123d  xor     edi, edi
0x18019123f  mov     qword ptr [rbp+3D0h+var_450], rcx
0x180191243  xorps   xmm0, xmm0
0x180191246  mov     [rbp+3D0h+var_3D0], rdi
0x18019124a  mov     r13, rcx
0x18019124d  mov     [rbp+3D0h+var_3C8], edi
0x180191250  mov     rcx, [rcx+30h]; this
0x180191254  movdqu  [rbp+3D0h+var_3C0], xmm0
0x180191259  mov     [rbp+3D0h+var_3B0], rdi
0x18019125d  mov     qword ptr [rbp+3D0h+var_318], rdi
0x180191264  mov     [rbp+3D0h+var_310], edi
0x18019126a  movdqu  [rbp+3D0h+var_308], xmm0
0x180191272  mov     [rbp+3D0h+var_2F8], rdi
0x180191279  mov     [rbp+3D0h+var_3E8], rdi
0x18019127d  mov     [rbp+3D0h+var_428], rdi
0x180191281  mov     [rbp+3D0h+var_438], rdi
0x180191285  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18019128a  test    eax, eax
0x18019128c  jz      short loc_1801912F5
0x18019128e  lea     rdx, [rbp+3D0h+var_428]; wchar_t **
0x180191292  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x180191297  mov     ebx, eax
0x180191299  test    eax, eax
0x18019129b  jns     short loc_180191313
0x18019129d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801912a4  mov     [rbp+3D0h+var_3A8], eax
0x1801912a7  test    rcx, rcx
0x1801912aa  jz      short loc_1801912EB
0x1801912ac  lea     r15d, [rdi+3]
0x1801912b0  xor     edx, edx
0x1801912b2  mov     r8d, r15d
0x1801912b5  lea     r9, aFailedToGetOff_13; "Failed to get offline Windir"
0x1801912bc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801912c1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801912c8  lea     rax, [rbp+3D0h+var_3A8]
0x1801912cc  mov     [rbp+3D0h+var_438], rax
0x1801912d0  lea     r9, asc_1802EE7AC; ": {}"
0x1801912d7  lea     rax, [rbp+3D0h+var_438]
0x1801912db  mov     r8d, r15d
0x1801912de  lea     edx, [rdi+1]
0x1801912e1  mov     [rsp+4D0h+var_4B0], rax
0x1801912e6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801912eb  mov     edx, 0FD7h
0x1801912f0  jmp     loc_180192184
0x1801912f5  xor     edx, edx
0x1801912f7  lea     rcx, [rbp+3D0h+var_428]
0x1801912fb  call    PathGetWindowsDirectory
0x180191300  mov     ebx, eax
0x180191302  test    eax, eax
0x180191304  jns     short loc_180191313
0x180191306  mov     r9d, eax
0x180191309  mov     edx, 0FDBh
0x18019130e  jmp     loc_180192187
0x180191313  lea     rdx, aWinsxs_0; "WinSxS"
0x18019131a  lea     rcx, [rbp+3D0h+var_428]
0x18019131e  call    SczAllocConcatSz
0x180191323  mov     ebx, eax
0x180191325  test    eax, eax
0x180191327  jns     short loc_180191336
0x180191329  mov     r9d, eax
0x18019132c  mov     edx, 0FDEh
0x180191331  jmp     loc_180192187
0x180191336  mov     rcx, [r13+30h]; this
0x18019133a  lea     rdx, [rbp+3D0h+var_3E8]; wchar_t **
0x18019133e  call    ?GetPackageStoreDirectory@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetPackageStoreDirectory(wchar_t * *)
0x180191343  mov     ebx, eax
0x180191345  test    eax, eax
0x180191347  jns     short loc_1801913A4
0x180191349  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180191350  mov     [rbp+3D0h+var_3A8], eax
0x180191353  test    rcx, rcx
0x180191356  jz      short loc_18019139A
0x180191358  mov     r15d, 3
0x18019135e  lea     r9, aFailedToGetPac_19; "Failed to get package store directory."
0x180191365  mov     r8d, r15d
0x180191368  xor     edx, edx
0x18019136a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18019136f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180191376  lea     rax, [rbp+3D0h+var_3A8]
0x18019137a  mov     [rbp+3D0h+var_438], rax
0x18019137e  lea     r9, asc_1802EE7AC; ": {}"
0x180191385  lea     rax, [rbp+3D0h+var_438]
0x180191389  mov     r8d, r15d
0x18019138c  lea     edx, [r15-2]
0x180191390  mov     [rsp+4D0h+var_4B0], rax
0x180191395  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18019139a  mov     edx, 0FE0h
0x18019139f  jmp     loc_180192184
0x1801913a4  mov     rcx, [r13+30h]
0x1801913a8  lea     rax, [rbp+3D0h+var_318]
0x1801913af  xor     r9d, r9d
0x1801913b2  mov     [rsp+4D0h+var_4B0], rax; int
0x1801913b7  xor     edx, edx
0x1801913b9  lea     r8d, [r9+0Ah]
0x1801913bd  call    ?GetStoreObject@CCbsSession@@QEAAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsSession::GetStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x1801913c2  mov     ebx, eax
0x1801913c4  test    eax, eax
0x1801913c6  jns     short loc_180191423
0x1801913c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801913cf  mov     [rbp+3D0h+var_3A8], eax
0x1801913d2  test    rcx, rcx
0x1801913d5  jz      short loc_180191419
0x1801913d7  mov     r15d, 3
0x1801913dd  lea     r9, aFailedGettingC_0; "Failed getting CbsStoreObjectDrivers re"...
0x1801913e4  mov     r8d, r15d
0x1801913e7  xor     edx, edx
0x1801913e9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801913ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801913f5  lea     rax, [rbp+3D0h+var_3A8]
0x1801913f9  mov     [rbp+3D0h+var_438], rax
0x1801913fd  lea     r9, asc_1802EE7AC; ": {}"
0x180191404  lea     rax, [rbp+3D0h+var_438]
0x180191408  mov     r8d, r15d
0x18019140b  lea     edx, [r15-2]
0x18019140f  mov     [rsp+4D0h+var_4B0], rax
0x180191414  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180191419  mov     edx, 0FE3h
0x18019141e  jmp     loc_180192184
0x180191423  mov     rcx, [r13+30h]
0x180191427  lea     rdx, [rbp+3D0h+var_438]
0x18019142b  call    DirectDriverOpenContext
0x180191430  mov     ebx, eax
0x180191432  test    eax, eax
0x180191434  jns     short loc_180191491
0x180191436  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18019143d  mov     [rbp+3D0h+var_3A8], eax
0x180191440  test    rcx, rcx
0x180191443  jz      short loc_180191487
0x180191445  mov     r15d, 3
0x18019144b  lea     r9, aFailedOpeningD_1; "Failed opening driver update context"
0x180191452  mov     r8d, r15d
0x180191455  xor     edx, edx
0x180191457  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18019145c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180191463  lea     rax, [rbp+3D0h+var_3A8]
0x180191467  mov     [rbp+3D0h+var_438], rax
0x18019146b  lea     r9, asc_1802EE7AC; ": {}"
0x180191472  lea     rax, [rbp+3D0h+var_438]
0x180191476  mov     r8d, r15d
0x180191479  lea     edx, [r15-2]
0x18019147d  mov     [rsp+4D0h+var_4B0], rax
0x180191482  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180191487  mov     edx, 0FE5h
0x18019148c  jmp     loc_180192184
0x180191491  mov     ecx, 40h ; '@'; Size
0x180191496  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18019149b  test    rax, rax
0x18019149e  jz      loc_18019217A
0x1801914a4  mov     rcx, rax
0x1801914a7  call    ??0?$CCbsArray@U_DRIVER_UPDATE@@@@QEAA@XZ; CCbsArray<_DRIVER_UPDATE>::CCbsArray<_DRIVER_UPDATE>(void)
0x1801914ac  mov     rsi, rax
0x1801914af  test    rax, rax
0x1801914b2  jz      loc_18019217A
0x1801914b8  xorps   xmm0, xmm0
0x1801914bb  mov     [rbp+3D0h+var_348], rdi
0x1801914c2  mov     ebx, edi
0x1801914c4  mov     [rbp+3D0h+var_340], edi
0x1801914ca  lea     r8, [rbp+3D0h+var_348]; struct CCbsStoreObject *
0x1801914d1  mov     [rbp+3D0h+var_3A8], ebx
0x1801914d4  xor     edx, edx; unsigned int
0x1801914d6  mov     [rbp+3D0h+var_328], rdi
0x1801914dd  lea     rcx, [rbp+3D0h+var_318]; this
0x1801914e4  movdqu  [rbp+3D0h+var_338], xmm0
0x1801914ec  call    ?EnumChildren@CCbsStoreObject@@QEAAJKPEAV1@@Z; CCbsStoreObject::EnumChildren(ulong,CCbsStoreObject *)
0x1801914f1  mov     r15d, 3
0x1801914f7  lea     r14d, [r15-2]
0x1801914fb  cmp     eax, 80070103h
0x180191500  jz      loc_180191AF4
0x180191506  lea     r12, qword_1802EB518
0x18019150d  xor     eax, eax
0x18019150f  mov     [rbp+3D0h+var_3F8], edi
0x180191512  xorps   xmm0, xmm0
0x180191515  mov     [rbp+3D0h+var_370], rax
0x180191519  xor     edx, edx; Val
0x18019151b  mov     [rbp+3D0h+var_368], eax
0x18019151e  mov     r8d, 220h; Size
0x180191524  mov     [rbp+3D0h+var_350], rax
0x18019152b  lea     rcx, [rbp+3D0h+var_270]; void *
0x180191532  movdqu  xmmword ptr [rbp+3D0h+var_360], xmm0
0x180191537  call    memset_0
0x18019153c  lea     rcx, [rbp+3D0h+var_2F0]; this
0x180191543  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x180191548  lea     r8, [rbp+3D0h+var_370]; struct CCbsStoreObject *
0x18019154c  mov     [rbp+3D0h+var_58], 11h
0x180191556  xor     edx, edx; unsigned int
0x180191558  lea     rcx, [rbp+3D0h+var_348]; this
0x18019155f  call    ?EnumChildren@CCbsStoreObject@@QEAAJKPEAV1@@Z; CCbsStoreObject::EnumChildren(ulong,CCbsStoreObject *)
0x180191564  cmp     eax, 80070103h
0x180191569  jz      loc_180191A8C
0x18019156f  xor     ebx, ebx
0x180191571  xorps   xmm0, xmm0
0x180191574  mov     [rbp+3D0h+var_3FC], ebx
0x180191577  lea     r8, [rbp+3D0h+var_398]; struct CCbsStoreObject *
0x18019157b  mov     [rbp+3D0h+var_398], rbx
0x18019157f  xor     edx, edx; unsigned int
0x180191581  mov     [rbp+3D0h+var_390], ebx
0x180191584  lea     rcx, [rbp+3D0h+var_370]; this
0x180191588  mov     [rbp+3D0h+var_378], rbx
0x18019158c  movdqu  [rbp+3D0h+var_388], xmm0
0x180191591  call    ?EnumChildren@CCbsStoreObject@@QEAAJKPEAV1@@Z; CCbsStoreObject::EnumChildren(ulong,CCbsStoreObject *)
0x180191596  mov     ebx, eax
0x180191598  cmp     eax, 80070103h
0x18019159d  jz      loc_180191A06
0x1801915a3  xor     edx, edx
0x1801915a5  test    ebx, ebx
0x1801915a7  js      loc_1801920C7
0x1801915ad  mov     [rbp+3D0h+var_400], edx
0x1801915b0  mov     ebx, edx
0x1801915b2  mov     [rbp+3D0h+Str], rdx
0x1801915b6  mov     [rbp+3D0h+var_440], rdx
0x1801915ba  mov     [rbp+3D0h+var_3A0], rdx
0x1801915be  mov     [rbp+3D0h+var_320], rdx
0x1801915c5  mov     [rsp+4D0h+var_458], rdx
0x1801915ca  mov     [rsp+4D0h+var_460], rdx
0x1801915cf  jmp     loc_180191954
0x1801915d4  test    edi, edi
0x1801915d6  js      loc_180191FB5
0x1801915dc  mov     rcx, [rbp+3D0h+Str]; Str
0x1801915e0  mov     edx, 7Eh ; '~'; Ch
0x1801915e5  call    cs:__imp_wcsrchr
0x1801915ec  nop     dword ptr [rax+rax+00h]
0x1801915f1  mov     rdi, rax
0x1801915f4  xor     eax, eax
0x1801915f6  test    rdi, rdi
0x1801915f9  jz      short loc_18019161B
0x1801915fb  lea     rdx, [rdi+2]
0x1801915ff  lea     rcx, [rbp+3D0h+var_440]
0x180191603  call    SczAllocFromSz
0x180191608  mov     ebx, eax
0x18019160a  xor     eax, eax
0x18019160c  test    ebx, ebx
0x18019160e  js      loc_180191BAC
0x180191614  mov     rbx, [rbp+3D0h+var_440]
0x180191618  mov     [rdi], ax
0x18019161b  mov     rdx, [rbp+3D0h+Str]; wchar_t *
0x18019161f  lea     r8, [rbp+3D0h+var_2F0]; struct CCbsStringArray *
0x180191626  mov     rcx, [rbp+3D0h+var_3E8]; wchar_t *
0x18019162a  xor     r9d, r9d; int
0x18019162d  mov     [rsp+4D0h+var_480], rax; unsigned __int64
0x180191632  mov     [rsp+4D0h+var_488], rax; wchar_t *
0x180191637  mov     [rsp+4D0h+var_490], rax; wchar_t *
0x18019163c  mov     [rsp+4D0h+var_498], rax; wchar_t *
0x180191641  mov     [rsp+4D0h+var_4A0], rax; wchar_t *
0x180191646  lea     rax, [rbp+3D0h+var_320]
0x18019164d  mov     [rsp+4D0h+var_4A8], rax; unsigned __int64 *
0x180191652  lea     rax, [rbp+3D0h+var_3A0]
0x180191656  mov     [rsp+4D0h+var_4B0], rax; wchar_t **
0x18019165b  call    ?ReadAndConcatenateManifestFromStore@@YAJPEB_W0PEAVCCbsStringArray@@HPEAPEA_WPEA_K0000_K@Z; ReadAndConcatenateManifestFromStore(wchar_t const *,wchar_t const *,CCbsStringArray *,int,wchar_t * *,unsigned __int64 *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64)
0x180191660  mov     edi, eax
0x180191662  test    eax, eax
0x180191664  js      loc_180191F64
0x18019166a  mov     rdi, [r13+30h]
0x18019166e  lea     rcx, [rsp+4D0h+var_458]
0x180191673  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180191678  mov     rdx, [rbp+3D0h+var_3A0]
0x18019167c  xor     r9d, r9d
0x18019167f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180191686  mov     [rsp+4D0h+var_468], rax
0x18019168b  xor     r8d, r8d
0x18019168e  xor     eax, eax
0x180191690  mov     rcx, rdi
0x180191693  mov     dword ptr [rsp+4D0h+var_470], eax
0x180191697  mov     [rsp+4D0h+var_478], rax
0x18019169c  mov     dword ptr [rsp+4D0h+var_480], eax
0x1801916a0  mov     [rsp+4D0h+var_488], rax
0x1801916a5  mov     [rsp+4D0h+var_490], rax
0x1801916aa  mov     [rsp+4D0h+var_498], rdx
0x1801916af  xor     edx, edx
0x1801916b1  mov     dword ptr [rsp+4D0h+var_4A0], r15d
0x1801916b6  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x1801916ba  lea     rax, [rbp+3D0h+var_410]
0x1801916be  mov     [rsp+4D0h+var_4B0], rax
0x1801916c3  movdqu  xmmword ptr [rbp+3D0h+var_410], xmm0
0x1801916c8  call    ?CreateWindowsUpdatePackage@CCbsSession@@QEAAJPEAXIPEB_WU_GUID@@IW4_CbsPackageType@@111IQEAUtagCbsPackageDecryptionData@@W4tagCBS_PACKAGE_ENCRYPTION_ENUM@@PEAPEAVCCbsPackage@@@Z; CCbsSession::CreateWindowsUpdatePackage(void *,uint,wchar_t const *,_GUID,uint,_CbsPackageType,wchar_t const *,wchar_t const *,wchar_t const *,uint,tagCbsPackageDecryptionData * const,tagCBS_PACKAGE_ENCRYPTION_ENUM,CCbsPackage * *)
0x1801916cd  mov     edi, eax
0x1801916cf  test    eax, eax
0x1801916d1  js      loc_180191F10
0x1801916d7  mov     rdx, [r13+30h]; struct CCbsSession *
0x1801916db  mov     rcx, [rsp+4D0h+var_458]; this
0x1801916e0  call    ?MakeSurePackageIsFullyInitialized@CCbsPackage@@QEAAJPEAVCCbsSession@@@Z; CCbsPackage::MakeSurePackageIsFullyInitialized(CCbsSession *)
0x1801916e5  mov     edi, eax
0x1801916e7  test    eax, eax
0x1801916e9  js      loc_180191EA0
0x1801916ef  mov     rdi, [rsp+4D0h+var_458]
0x1801916f4  lea     rcx, [rsp+4D0h+var_460]
0x1801916f9  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801916fe  mov     rdx, rax
  ... truncated ...
```
