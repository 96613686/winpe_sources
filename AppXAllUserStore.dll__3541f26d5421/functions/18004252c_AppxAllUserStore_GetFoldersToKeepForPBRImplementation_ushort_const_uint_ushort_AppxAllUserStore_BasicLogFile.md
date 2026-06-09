# AppxAllUserStore::GetFoldersToKeepForPBRImplementation(ushort const *,uint *,ushort * * *,AppxAllUserStore::BasicLogFile *)

- ea: `0x18004252c`
- end: `0x180043078`
- name: `?GetFoldersToKeepForPBRImplementation@AppxAllUserStore@@YAJPEBGPEAIPEAPEAPEAGPEAVBasicLogFile@1@@Z`
- size: `2892`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 ***, struct AppxAllUserStore::BasicLogFile *)`
- caller_count: `2`
- callee_count: `35`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002e590`
- `0x180035140`

## callees

- `0x180002328`
- `0x1800036d4`
- `0x1800039e4`
- `0x180004920`
- `0x180004968`
- `0x180006d40`
- `0x18000d6a0`
- `0x18000e824`
- `0x18000ed34`
- `0x180012c3c`
- `0x1800131f0`
- `0x180016138`
- `0x180017cd0`
- `0x180017f18`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x180021b64`
- `0x180026380`
- `0x18002de30`
- `0x18002e280`
- `0x180033bb4`
- `0x1800340d8`
- `0x180040ba8`
- `0x180041198`
- `0x18004252c`
- `0x180043484`
- `0x1800434c8`
- `0x180043740`
- `0x180044624`
- `0x1800447c8`
- `0x180045120`
- `0x1800468a0`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800425e6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800425e6`

## string_xrefs

- `0x18004275d`: `GetAllUserApplicationsPath failed, 0x%0x.`
- `0x18004297f`: `Open %ws failed, 0x%0x.`
- `0x1800428b5`: `Windows\System32\Config\Software`
- `0x1800425df`: `%temp%`
- `0x180042642`: `OpenLogFileAlways %ws.`
- `0x18004283b`: `Open hive %ws failed, 0x%0x.`
- `0x1800429e6`: `Hive %ws opened.`
- `0x180042a4f`: `GetPackagesFromRegistryStoreInternal %ws failed, 0x%0x.`
- `0x180042b74`: `DeleteAllPackagesFromPackageArray %u, 0x%0x.`
- `0x180042cae`: `AddDeletedAllUserPackagesIfNeeded %ws %u.`
- `0x180042cdc`: `AddDeletedAllUserPackagesIfNeeded %u, 0x%0x.`
- `0x180042d2e`: `AddDeletedAllUserPackagesFolderIfNeeded %u, 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetFoldersToKeepForPBRImplementation(
        AppxAllUserStore *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 ***a4)
{
  AppxAllUserStore::BasicLogFile *v4; // rdi
  unsigned int *v5; // r15
  AppxAllUserStore *v7; // r13
  __int64 v8; // rdx
  unsigned int v9; // ebx
  DWORD v10; // ebx
  unsigned int v11; // eax
  int v12; // eax
  const struct _tlgProvider_t *v13; // rax
  struct Common::StringBuffer *v14; // r8
  __int64 v15; // r9
  int v16; // eax
  struct Common::StringBuffer *v17; // r9
  int v18; // eax
  int AllUserChildStorePath; // eax
  int v20; // eax
  AppxAllUserStore::Internal *v21; // r14
  int v22; // eax
  LSTATUS v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // r14d
  int v26; // eax
  int v27; // eax
  HKEY v28; // rdx
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  int Hive; // eax
  unsigned int v32; // r14d
  int v33; // eax
  LSTATUS v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  int PackagesFromRegistryStoreInternal; // eax
  int v39; // eax
  unsigned int v40; // ebx
  int v41; // eax
  unsigned int v42; // eax
  int v43; // r15d
  int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  int v47; // eax
  int v48; // ebx
  unsigned int v49; // eax
  unsigned int v50; // eax
  int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  int v54; // eax
  int v55; // eax
  unsigned int v56; // r14d
  int v57; // eax
  unsigned int v58; // eax
  int v59; // r13d
  int v60; // eax
  int AllPinnedPackages; // eax
  unsigned int i; // ebx
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  const struct _tlgProvider_t *v68; // rax
  __int64 v69; // r8
  __int64 v70; // r9
  const struct _tlgProvider_t *v71; // rax
  __int64 v72; // r8
  __int64 v73; // r9
  int v74; // eax
  unsigned int *v76; // [rsp+20h] [rbp-E0h]
  int v77; // [rsp+20h] [rbp-E0h]
  char *v78; // [rsp+28h] [rbp-D8h]
  char *v79; // [rsp+28h] [rbp-D8h]
  __int64 v80; // [rsp+30h] [rbp-D0h]
  struct AppxAllUserStore::_PackageInfo *v81; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  struct HKEY__ v83[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v84; // [rsp+70h] [rbp-90h]
  __int64 v85[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v86; // [rsp+88h] [rbp-78h]
  char v87; // [rsp+90h] [rbp-70h]
  __int64 v88; // [rsp+98h] [rbp-68h]
  unsigned int v89[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v90[2]; // [rsp+A8h] [rbp-58h] BYREF
  AppxAllUserStore *v91; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v92; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v93[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v94; // [rsp+D8h] [rbp-28h]
  AppxAllUserStore *v95[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v96; // [rsp+F0h] [rbp-10h]
  __int128 v97; // [rsp+F8h] [rbp-8h] BYREF
  int v98; // [rsp+108h] [rbp+8h]
  __int64 v99; // [rsp+110h] [rbp+10h]
  WCHAR Dst[264]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  *(_QWORD *)v90 = a3;
  v91 = this;
  v4 = (AppxAllUserStore::BasicLogFile *)a4;
  v5 = a3;
  v7 = this;
  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = 1350;
      goto LABEL_3;
    }
    if ( *(_QWORD *)a3 )
    {
      v8 = 1351;
      goto LABEL_3;
    }
    v98 = 0;
    v99 = -1;
    v97 = 0;
    if ( !a4 )
    {
      v10 = ExpandEnvironmentStringsW(L"%temp%", Dst, 0x104u);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0x550,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(v10 == 0),
        (bool)"ExpandEnvironmentStrings",
        v78);
      if ( !v10 )
        goto LABEL_14;
      v11 = AppxAllUserStore::BasicLogFile::OpenLogFileAlways(
              (AppxAllUserStore::BasicLogFile *)&v97,
              (char *)Dst,
              (char *)L"GetFoldersToKeepForPBR.log");
      if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0x555,
                  (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                  (const char *)v11,
                  (__int64)"OpenLogFileAlways %ws.",
                  (const char *)Dst) < 0 )
        goto LABEL_14;
      v4 = (AppxAllUserStore::BasicLogFile *)&v97;
    }
    v12 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"In GetFoldersToKeepForPBRImplementation %ws.", v7);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x55A,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v12);
LABEL_14:
    *(_DWORD *)a2 = 0;
    v13 = AppxAllUserStoreTelemetry::Provider();
    if ( *(_DWORD *)v13 > 5u )
    {
      *(_QWORD *)v89 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v13,
        (unsigned __int8 *)word_18005D342,
        (__int64)v14,
        v15,
        (const unsigned __int16 **)v89);
    }
    v96 = 0;
    *(_OWORD *)v95 = 0;
    v16 = AppxAllUserStore::NormalizeSystemRoot(v7, (void **)v95, v14);
    v9 = v16;
    if ( v16 < 0 )
    {
      if ( v4 )
      {
        v18 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"NormalizeSystemRoot failed, 0x%0x.", (unsigned int)v16);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x567,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v18);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x567,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)v9,
        (int)v76);
      goto LABEL_117;
    }
    v84 = 0;
    *(_OWORD *)&v83[0].unused = 0;
    AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                              (AppxAllUserStore *)L"Applications",
                              0,
                              (unsigned int *)v83,
                              v17);
    v9 = AllUserChildStorePath;
    if ( AllUserChildStorePath < 0 )
    {
      if ( v4 )
      {
        v20 = AppxAllUserStore::BasicLogFile::WriteMsg(
                v4,
                L"GetAllUserApplicationsPath failed, 0x%0x.",
                (unsigned int)AllUserChildStorePath);
        if ( v20 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x56D,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v20);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56D,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)v9,
        (int)v76);
      goto LABEL_26;
    }
    v21 = v95[1];
    if ( v4 )
    {
      v22 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"AppsKey %ws Root %ws.", *(_QWORD *)&v83[2].unused, v95[1]);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x56F,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v22);
    }
    phkResult = 0;
    v92 = 0;
    if ( !v21 )
    {
      v23 = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, L"Software", 0x20019u);
      v9 = v23;
      if ( v23 < 0 )
      {
        v25 = 1403;
        if ( v4 )
        {
          v26 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  v4,
                  L"Open hive %ws failed, 0x%0x.",
                  L"Software",
                  (unsigned int)v23);
          if ( v26 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x57B,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v26);
        }
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0zd_EventWriteTransfer(v24, AppxAllUserStoreOpenKeyError, L"Software", v9);
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)v9,
          (int)v76);
LABEL_38:
        Common::RegistryKey::~RegistryKey(&phkResult);
        AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive((AppxAllUserStore::AutoRegLoadHive *)&v92);
LABEL_26:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v83);
LABEL_117:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v95);
        AppxAllUserStore::BasicLogFile::~BasicLogFile((Common **)&v97);
        return v9;
      }
LABEL_54:
      if ( v4 )
      {
        v37 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"Hive %ws opened.", L"Software");
        if ( v37 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x58B,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v37);
      }
      *(_QWORD *)v89 = 0;
      LODWORD(v81) = 0;
      PackagesFromRegistryStoreInternal = AppxAllUserStore::GetPackagesFromRegistryStoreInternal(
                                            phkResult,
                                            v83,
                                            (struct Common::StringBuffer *)v89,
                                            &v81,
                                            v76);
      v9 = PackagesFromRegistryStoreInternal;
      if ( PackagesFromRegistryStoreInternal < 0 )
      {
        v25 = 1427;
        if ( v4 )
        {
          v39 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  v4,
                  L"GetPackagesFromRegistryStoreInternal %ws failed, 0x%0x.",
                  *(_QWORD *)&v83[2].unused,
                  (unsigned int)PackagesFromRegistryStoreInternal);
          if ( v39 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x593,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v39);
        }
        goto LABEL_37;
      }
      v40 = (unsigned int)v81;
      if ( v4 )
      {
        v41 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"Found %u main packages.", (unsigned int)v81);
        if ( v41 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x595,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v41);
      }
      if ( v40 )
      {
        v87 = 1;
        v85[0] = 0;
        v85[1] = 0;
        v86 = 0;
        v42 = AppxAllUserStore::Internal::ProcessMainPackagesList(v4, v21, v40, (__int64)v89, (__int64)v85);
        v43 = v42;
        if ( v4 )
        {
          v44 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  v4,
                  L"ProcessMainPackagesList got %u folders, 0x%0x.",
                  (unsigned int)v86,
                  v42);
          if ( v44 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5A5,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v44);
        }
        v45 = DeleteAllPackagesFromPackageArray(v40, v89);
        LODWORD(v79) = v40;
        v46 = wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x5A8,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)v45,
                (__int64)"Count %u.",
                v79);
        if ( v4 )
        {
          v47 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"DeleteAllPackagesFromPackageArray %u, 0x%0x.", v40, v46);
          if ( v47 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5A9,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v47);
        }
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5AD,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v43,
            (int)"systemRoot %ws Apps key %ws count %u array size %u.",
            (const char *)v21,
            *(_QWORD *)&v83[2].unused,
            v40,
            v86);
          Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>((__int64)v85);
          Common::RegistryKey::~RegistryKey(&phkResult);
          AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive((AppxAllUserStore::AutoRegLoadHive *)&v92);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v83);
          v9 = v43;
          goto LABEL_117;
        }
        v48 = v86;
        v49 = AppxAllUserStore::Internal::ProcessStagedPackages(v4, v21, &phkResult, v85);
        LODWORD(v80) = v48;
        v50 = wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x5B2,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)v49,
                (__int64)"ProcessStagedPackages %ws %u.",
                (const char *)v21,
                v80);
        if ( v4 )
        {
          v51 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  v4,
                  L"ProcessStagedPackages %u, 0x%0x.",
                  (unsigned int)v86,
                  v50);
          if ( v51 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5B4,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v51);
        }
        v52 = AppxAllUserStore::Internal::AddDeletedAllUserPackagesIfNeeded(v4, v21, phkResult, (unsigned int *)v85);
        v53 = wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x5BB,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)v52,
                (__int64)"AddDeletedAllUserPackagesIfNeeded %ws %u.",
                (const char *)v21);
        if ( v4 )
        {
          v54 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  v4,
                  L"AddDeletedAllUserPackagesIfNeeded %u, 0x%0x.",
                  (unsigned int)v86,
                  v53);
          if ( v54 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5BD,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v54);
        }
        v55 = AppxAllUserStore::Internal::AddDeletedAllUserPackagesFolderIfNeeded(v4, v21, (HANDLE *)v85);
        v9 = v55;
        if ( v55 < 0 )
        {
          v56 = 1477;
          if ( v4 )
          {
            v57 = AppxAllUserStore::BasicLogFile::WriteMsg(
                    v4,
                    L"AddDeletedAllUserPackagesFolderIfNeeded %u, 0x%0x.",
                    (unsigned int)v86,
                    (unsigned int)v55);
            goto LABEL_82;
          }
          goto LABEL_84;
        }
        v58 = AppxAllUserStore::Internal::ProcessAllFrameworksInSIS(v4, v21, (__int64)v85);
        v59 = v58;
        if ( v4 )
        {
          v60 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  v4,
                  L"ProcessAllFrameworksInSIS %u, 0x%0x.",
                  (unsigned int)v86,
                  v58);
          if ( v60 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5CB,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v60);
        }
        v88 = 0;
        LODWORD(v81) = 0;
        AllPinnedPackages = GetAllPinnedPackages(phkResult);
        v9 = AllPinnedPackages;
        if ( AllPinnedPackages < 0 )
        {
          v56 = 1489;
          if ( v4 )
          {
            v57 = AppxAllUserStore::BasicLogFile::WriteMsg(
                    v4,
                    L"GetAllPinnedPackages failed, 0x%0x.",
                    (unsigned int)AllPinnedPackages);
LABEL_82:
            if ( v57 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v56,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v57);
          }
LABEL_84:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v56,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)v9,
            v77);
LABEL_85:
          Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>((__int64)v85);
          goto LABEL_38;
        }
        for ( i = 0; i < (unsigned int)v81; ++i )
        {
          AppxAllUserStore::Internal::ProcessPackageFamily(v4, v21, *(unsigned __int16 **)(v88 + 8LL * i));
          if ( v4 )
          {
            v77 = v59;
            v63 = AppxAllUserStore::BasicLogFile::WriteMsg(
                    v4,
                    L"ProcessPackageFamily %ls : %u, 0x%0x.",
                    *(_QWORD *)(v88 + 8LL * i),
                    (unsigned int)v86);
            if ( v63 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5D9,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v63);
          }
        }
        v5 = *(unsigned int **)v90;
        v64 = AppxAllUserStore::Internal::PopulateOutputFoldersList(v4);
        v9 = v64;
        if ( v64 < 0 )
        {
          if ( v4 )
          {
            v77 = v64;
            v65 = AppxAllUserStore::BasicLogFile::WriteMsg(
                    v4,
                    L"PopulateOutputFoldersList %u %u failed, 0x%0x.",
                    (unsigned int)v86,
                    *(unsigned int *)a2);
            if ( v65 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5E2,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v65);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E2,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)v9,
            v77);
          v66 = DeletePackageFamiliesArray((unsigned int)v81, v88);
          if ( v66 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5D3,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v66);
          goto LABEL_85;
        }
        v67 = DeletePackageFamiliesArray((unsigned int)v81, v88);
        if ( v67 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5D3,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v67);
        Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>((__int64)v85);
        v7 = v91;
      }
      Common::RegistryKey::~RegistryKey(&phkResult);
      if ( !*(_DWORD *)a2 || !*(_QWORD *)v5 )
      {
        v68 = AppxAllUserStoreTelemetry::Provider();
        if ( *(_DWORD *)v68 > 5u )
        {
          if ( (unsigned __int8)tlgKeywordOn(v68, 0x400000000000LL, v68) )
          {
            *(_QWORD *)v90 = *(unsigned int *)a2;
            v91 = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              v69,
              (__int64)&dword_18005D304,
              v69,
              v70,
              (__int64)v90,
              (const unsigned __int16 **)&v91);
          }
        }
      }
      v71 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v71 > 5u )
      {
        *(_QWORD *)v90 = *(unsigned int *)a2;
        v91 = v21;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (__int64)v71,
          (__int64)byte_18005D2C1,
          v72,
          v73,
          (__int64)v90,
          (const unsigned __int16 **)&v91);
      }
      if ( v4 )
      {
        v74 = AppxAllUserStore::BasicLogFile::WriteMsg(
                v4,
                L"GetFoldersToKeepForPBR got %u folders.",
                *(unsigned int *)a2);
        if ( v74 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5F6,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)v74);
      }
      AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive((AppxAllUserStore::AutoRegLoadHive *)&v92);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v83);
      v9 = 0;
      goto LABEL_117;
    }
    v94 = 0;
    *(_OWORD *)v93 = 0;
    v27 = Common::PathHelpers::CombinePaths(
            (const unsigned __int16 **)v95,
            L"Windows\\System32\\Config\\Software",
            (struct Common::StringBuffer *)v93);
    v9 = v27;
    if ( v27 >= 0 )
    {
      Hive = AppxAllUserStore::AutoRegLoadHive::RegLoadHive(
               (AppxAllUserStore::AutoRegLoadHive *)&v92,
               v28,
               L"APPX_HIVE_LOAD_ALIAS_SOFTWARE",
               v93[1]);
      v9 = Hive;
      if ( Hive >= 0 )
      {
        v34 = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, L"APPX_HIVE_LOAD_ALIAS_SOFTWARE", 0x20019u);
        v9 = v34;
        if ( v34 >= 0 )
        {
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v93);
          goto LABEL_54;
        }
        v32 = 1416;
        if ( v4 )
        {
          v36 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"Open %ws failed, 0x%0x.", v93[1], (unsigned int)v34);
          if ( v36 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x588,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v36);
        }
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0zd_EventWriteTransfer(v35, AppxAllUserStoreOpenKeyError, L"APPX_HIVE_LOAD_ALIAS_SOFTWARE", v9);
      }
      else
      {
        v32 = 1413;
        if ( v4 )
        {
          v33 = AppxAllUserStore::BasicLogFile::WriteMsg(v4, L"RegLoadHive failed, 0x%0x.", (unsigned int)Hive);
          if ( v33 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x585,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v33);
        }
      }
      v29 = v9;
      v30 = v32;
    }
    else
    {
      v29 = (unsigned int)v27;
      v30 = 1408;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)v29,
      (int)v76);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v93);
    goto LABEL_38;
  }
  v8 = 1349;
LABEL_3:
  v9 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
    (const char *)0x80070057LL,
    (int)v76);
  return v9;
}

```

## disassembly

```asm
0x18004252c  push    rbp
0x18004252e  push    rbx
0x18004252f  push    rsi
0x180042530  push    rdi
0x180042531  push    r12
0x180042533  push    r13
0x180042535  push    r14
0x180042537  push    r15
0x180042539  lea     rbp, [rsp-248h]
0x180042541  sub     rsp, 348h
0x180042548  mov     rax, cs:__security_cookie
0x18004254f  xor     rax, rsp
0x180042552  mov     [rbp+280h+var_50], rax
0x180042559  xor     r14d, r14d
0x18004255c  mov     qword ptr [rbp+280h+var_2D8], r8
0x180042560  mov     [rbp+280h+var_2D0], rcx
0x180042564  mov     rdi, r9
0x180042567  mov     r15, r8
0x18004256a  mov     r12, rdx
0x18004256d  mov     r13, rcx
0x180042570  test    rdx, rdx
0x180042573  jnz     short loc_18004259A
0x180042575  mov     edx, 545h; void *
0x18004257a  mov     rcx, [rbp+288h]; this
0x180042581  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180042588  mov     ebx, 80070057h
0x18004258d  mov     r9d, ebx; char *
0x180042590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042595  jmp     loc_180043053
0x18004259a  test    r8, r8
0x18004259d  jnz     short loc_1800425A6
0x18004259f  mov     edx, 546h
0x1800425a4  jmp     short loc_18004257A
0x1800425a6  cmp     [r8], r14
0x1800425a9  jz      short loc_1800425B2
0x1800425ab  mov     edx, 547h
0x1800425b0  jmp     short loc_18004257A
0x1800425b2  mov     [rbp+280h+var_278], r14d
0x1800425b6  xorps   xmm0, xmm0
0x1800425b9  mov     [rbp+280h+var_270], 0FFFFFFFFFFFFFFFFh
0x1800425c1  lea     rsi, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800425c8  movups  [rbp+280h+var_288], xmm0
0x1800425cc  test    r9, r9
0x1800425cf  jnz     loc_180042663
0x1800425d5  mov     r8d, 104h; nSize
0x1800425db  lea     rdx, [rbp+280h+Dst]; lpDst
0x1800425df  lea     rcx, Src; "%temp%"
0x1800425e6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800425ec  mov     rcx, [rbp+288h]; this
0x1800425f3  mov     r8, rsi; unsigned int
0x1800425f6  test    eax, eax
0x1800425f8  mov     ebx, eax
0x1800425fa  lea     rax, aExpandenvironm_0; "ExpandEnvironmentStrings"
0x180042601  setz    dl
0x180042604  mov     [rsp+380h+var_360], rax; bool
0x180042609  movzx   r9d, dl; char *
0x18004260d  mov     edx, 550h; void *
0x180042612  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180042617  test    ebx, ebx
0x180042619  jz      short loc_180042690
0x18004261b  lea     r8, aGetfolderstoke_1; "GetFoldersToKeepForPBR.log"
0x180042622  lea     rdx, [rbp+280h+Dst]; char *
0x180042626  lea     rcx, [rbp+280h+var_288]; this
0x18004262a  call    ?OpenLogFileAlways@BasicLogFile@AppxAllUserStore@@QEAAJPEBG0@Z; AppxAllUserStore::BasicLogFile::OpenLogFileAlways(ushort const *,ushort const *)
0x18004262f  mov     rcx, [rbp+288h]; this
0x180042636  lea     rdx, [rbp+280h+Dst]
0x18004263a  mov     [rsp+380h+var_358], rdx; char *
0x18004263f  mov     r9d, eax; char *
0x180042642  lea     rdx, aOpenlogfilealw; "OpenLogFileAlways %ws."
0x180042649  mov     r8, rsi; unsigned int
0x18004264c  mov     [rsp+380h+var_360], rdx; int
0x180042651  mov     edx, 555h; void *
0x180042656  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004265b  test    eax, eax
0x18004265d  js      short loc_180042690
0x18004265f  lea     rdi, [rbp+280h+var_288]
0x180042663  mov     r8, r13
0x180042666  lea     rdx, aInGetfoldersto; "In GetFoldersToKeepForPBRImplementation"...
0x18004266d  mov     rcx, rdi; this
0x180042670  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180042675  test    eax, eax
0x180042677  jns     short loc_180042690
0x180042679  mov     rcx, [rbp+288h]; this
0x180042680  mov     r9d, eax; char *
0x180042683  mov     r8, rsi; unsigned int
0x180042686  mov     edx, 55Ah; void *
0x18004268b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042690  mov     [r12], r14d
0x180042694  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180042699  mov     ecx, [rax]
0x18004269b  cmp     ecx, 5
0x18004269e  jbe     short loc_1800426BC
0x1800426a0  lea     rcx, [rbp+280h+var_2E0]
0x1800426a4  mov     qword ptr [rbp+280h+var_2E0], r13
0x1800426a8  mov     [rsp+380h+var_360], rcx; int
0x1800426ad  lea     rdx, word_18005D342
0x1800426b4  mov     rcx, rax
0x1800426b7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800426bc  xorps   xmm0, xmm0
0x1800426bf  mov     [rbp+280h+var_290], r14d
0x1800426c3  lea     rdx, [rbp+280h+var_2A0]; Common::StringBuffer *
0x1800426c7  mov     rcx, r13; this
0x1800426ca  movups  xmmword ptr [rbp+280h+var_2A0], xmm0
0x1800426ce  call    ?NormalizeSystemRoot@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::NormalizeSystemRoot(ushort const *,Common::StringBuffer &)
0x1800426d3  mov     ebx, eax
0x1800426d5  test    eax, eax
0x1800426d7  jns     short loc_180042729
0x1800426d9  mov     r15d, 567h
0x1800426df  test    rdi, rdi
0x1800426e2  jz      short loc_18004270F
0x1800426e4  mov     r8d, eax
0x1800426e7  lea     rdx, aNormalizesyste; "NormalizeSystemRoot failed, 0x%0x."
0x1800426ee  mov     rcx, rdi; this
0x1800426f1  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800426f6  test    eax, eax
0x1800426f8  jns     short loc_18004270F
0x1800426fa  mov     rcx, [rbp+288h]; this
0x180042701  mov     r9d, eax; char *
0x180042704  mov     r8, rsi; unsigned int
0x180042707  mov     edx, r15d; void *
0x18004270a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004270f  mov     rcx, [rbp+288h]; this
0x180042716  mov     r9d, ebx; char *
0x180042719  mov     r8, rsi; unsigned int
0x18004271c  mov     edx, r15d; void *
0x18004271f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042724  jmp     loc_180043041
0x180042729  xorps   xmm0, xmm0
0x18004272c  mov     [rsp+380h+var_310], r14d
0x180042731  lea     r8, [rsp+380h+var_320]; bool
0x180042736  xor     edx, edx; unsigned __int16 *
0x180042738  lea     rcx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x18004273f  movups  xmmword ptr [rsp+380h+var_320.unused], xmm0
0x180042744  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180042749  mov     ebx, eax
0x18004274b  test    eax, eax
0x18004274d  jns     short loc_1800427A9
0x18004274f  mov     r15d, 56Dh
0x180042755  test    rdi, rdi
0x180042758  jz      short loc_180042785
0x18004275a  mov     r8d, eax
0x18004275d  lea     rdx, aGetalluserappl; "GetAllUserApplicationsPath failed, 0x%0"...
0x180042764  mov     rcx, rdi; this
0x180042767  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004276c  test    eax, eax
0x18004276e  jns     short loc_180042785
0x180042770  mov     rcx, [rbp+288h]; this
0x180042777  mov     r9d, eax; char *
0x18004277a  mov     r8, rsi; unsigned int
0x18004277d  mov     edx, r15d; void *
0x180042780  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042785  mov     rcx, [rbp+288h]; this
0x18004278c  mov     r9d, ebx; char *
0x18004278f  mov     r8, rsi; unsigned int
0x180042792  mov     edx, r15d; void *
0x180042795  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004279a  lea     rcx, [rsp+380h+var_320]; this
0x18004279f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800427a4  jmp     loc_180043041
0x1800427a9  mov     r14, [rbp+280h+var_2A0+8]
0x1800427ad  test    rdi, rdi
0x1800427b0  jz      short loc_1800427E4
0x1800427b2  mov     r8, qword ptr [rsp+380h+var_320.unused+8]
0x1800427b7  lea     rdx, aAppskeyWsRootW; "AppsKey %ws Root %ws."
0x1800427be  mov     r9, r14
0x1800427c1  mov     rcx, rdi; this
0x1800427c4  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800427c9  test    eax, eax
0x1800427cb  jns     short loc_1800427E4
0x1800427cd  mov     rcx, [rbp+288h]; this
0x1800427d4  mov     r9d, eax; char *
0x1800427d7  mov     r8, rsi; unsigned int
0x1800427da  mov     edx, 56Fh; void *
0x1800427df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800427e4  mov     [rsp+380h+phkResult], 0
0x1800427ed  xorps   xmm0, xmm0
0x1800427f0  movdqu  [rbp+280h+var_2C8], xmm0
0x1800427f5  test    r14, r14
0x1800427f8  jnz     loc_1800428AF
0x1800427fe  mov     r9d, 20019h; samDesired
0x180042804  lea     r8, aSoftware_0; "Software"
0x18004280b  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180042812  lea     rcx, [rsp+380h+phkResult]; phkResult
0x180042817  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18004281c  mov     ebx, eax
0x18004281e  test    eax, eax
0x180042820  jns     loc_1800429D7
0x180042826  mov     r14d, 57Bh
0x18004282c  test    rdi, rdi
0x18004282f  jz      short loc_180042863
0x180042831  mov     r9d, eax
0x180042834  lea     r8, aSoftware_0; "Software"
0x18004283b  lea     rdx, aOpenHiveWsFail; "Open hive %ws failed, 0x%0x."
0x180042842  mov     rcx, rdi; this
0x180042845  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004284a  test    eax, eax
0x18004284c  jns     short loc_180042863
0x18004284e  mov     rcx, [rbp+288h]; this
0x180042855  mov     r9d, eax; char *
0x180042858  mov     r8, rsi; unsigned int
0x18004285b  mov     edx, r14d; void *
0x18004285e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042863  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x18004286a  jge     short loc_180042882
0x18004286c  mov     r9d, ebx
0x18004286f  lea     r8, aSoftware_0; "Software"
0x180042876  lea     rdx, AppxAllUserStoreOpenKeyError
0x18004287d  call    McTemplateU0zd_EventWriteTransfer
0x180042882  mov     rcx, [rbp+288h]; this
0x180042889  mov     r9d, ebx; char *
0x18004288c  mov     r8, rsi; unsigned int
0x18004288f  mov     edx, r14d; void *
0x180042892  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042897  lea     rcx, [rsp+380h+phkResult]; this
0x18004289c  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800428a1  lea     rcx, [rbp+280h+var_2C8]; this
0x1800428a5  call    ??1AutoRegLoadHive@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive(void)
0x1800428aa  jmp     loc_18004279A
0x1800428af  xor     eax, eax
0x1800428b1  lea     r8, [rbp+280h+var_2B8]; struct Common::StringBuffer *
0x1800428b5  lea     rdx, aWindowsSystem3; "Windows\\System32\\Config\\Software"
0x1800428bc  mov     [rbp+280h+var_2A8], eax
0x1800428bf  lea     rcx, [rbp+280h+var_2A0]; struct Common::COMMON_STRING *
0x1800428c3  movups  xmmword ptr [rbp+280h+var_2B8], xmm0
0x1800428c7  call    ?CombinePaths@PathHelpers@Common@@SAJPEBUCOMMON_STRING@2@PEBGPEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(Common::COMMON_STRING const *,ushort const *,Common::StringBuffer *)
0x1800428cc  mov     ebx, eax
0x1800428ce  test    eax, eax
0x1800428d0  jns     short loc_1800428F4
0x1800428d2  mov     r9d, eax; char *
0x1800428d5  mov     edx, 580h; void *
0x1800428da  mov     rcx, [rbp+288h]; this
0x1800428e1  mov     r8, rsi; unsigned int
0x1800428e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428e9  lea     rcx, [rbp+280h+var_2B8]; this
0x1800428ed  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800428f2  jmp     short loc_180042897
0x1800428f4  mov     r9, [rbp+280h+var_2B8+8]; unsigned __int16 *
0x1800428f8  lea     r8, aAppxHiveLoadAl; "APPX_HIVE_LOAD_ALIAS_SOFTWARE"
0x1800428ff  lea     rcx, [rbp+280h+var_2C8]; this
0x180042903  call    ?RegLoadHive@AutoRegLoadHive@AppxAllUserStore@@QEAAJQEAUHKEY__@@PEBG1@Z; AppxAllUserStore::AutoRegLoadHive::RegLoadHive(HKEY__ * const,ushort const *,ushort const *)
0x180042908  mov     ebx, eax
0x18004290a  test    eax, eax
0x18004290c  jns     short loc_18004294C
0x18004290e  mov     r14d, 585h
0x180042914  test    rdi, rdi
0x180042917  jz      short loc_180042944
0x180042919  mov     r8d, eax
0x18004291c  lea     rdx, aRegloadhiveFai; "RegLoadHive failed, 0x%0x."
0x180042923  mov     rcx, rdi; this
0x180042926  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18004292b  test    eax, eax
0x18004292d  jns     short loc_180042944
0x18004292f  mov     rcx, [rbp+288h]; this
0x180042936  mov     r9d, eax; char *
0x180042939  mov     r8, rsi; unsigned int
0x18004293c  mov     edx, r14d; void *
0x18004293f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042944  mov     r9d, ebx
0x180042947  mov     edx, r14d
0x18004294a  jmp     short loc_1800428DA
0x18004294c  mov     r9d, 20019h; samDesired
0x180042952  lea     r8, aAppxHiveLoadAl; "APPX_HIVE_LOAD_ALIAS_SOFTWARE"
0x180042959  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180042960  lea     rcx, [rsp+380h+phkResult]; phkResult
0x180042965  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18004296a  mov     ebx, eax
0x18004296c  test    eax, eax
0x18004296e  jns     short loc_1800429CE
0x180042970  mov     r14d, 588h
0x180042976  test    rdi, rdi
0x180042979  jz      short loc_1800429AA
0x18004297b  mov     r8, [rbp+280h+var_2B8+8]
0x18004297f  lea     rdx, aOpenWsFailed0x; "Open %ws failed, 0x%0x."
0x180042986  mov     r9d, eax
0x180042989  mov     rcx, rdi; this
0x18004298c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180042991  test    eax, eax
0x180042993  jns     short loc_1800429AA
0x180042995  mov     rcx, [rbp+288h]; this
0x18004299c  mov     r9d, eax; char *
0x18004299f  mov     r8, rsi; unsigned int
0x1800429a2  mov     edx, r14d; void *
0x1800429a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800429aa  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x1800429b1  jge     short loc_180042944
0x1800429b3  mov     r9d, ebx
0x1800429b6  lea     r8, aAppxHiveLoadAl; "APPX_HIVE_LOAD_ALIAS_SOFTWARE"
0x1800429bd  lea     rdx, AppxAllUserStoreOpenKeyError
0x1800429c4  call    McTemplateU0zd_EventWriteTransfer
0x1800429c9  jmp     loc_180042944
0x1800429ce  lea     rcx, [rbp+280h+var_2B8]; this
0x1800429d2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800429d7  test    rdi, rdi
0x1800429da  jz      short loc_180042A0D
0x1800429dc  lea     r8, aSoftware_0; "Software"
0x1800429e3  mov     rcx, rdi; this
0x1800429e6  lea     rdx, aHiveWsOpened; "Hive %ws opened."
0x1800429ed  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800429f2  test    eax, eax
0x1800429f4  jns     short loc_180042A0D
  ... truncated ...
```
