# AppxAllUserStore::Internal::ProcessMainPackage(AppxAllUserStore::BasicLogFile *,ushort const *,HKEY__ * const,Common::StringBuffer const *,AppxAllUserStore::_PackageInfo const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180043b10`
- end: `0x180044454`
- name: `?ProcessMainPackage@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGQEAUHKEY__@@PEBVStringBuffer@Common@@PEBU_PackageInfo@2@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@6@@Z`
- size: `2372`
- prototype: `__int64 __usercall@<rax>(AppxAllUserStore::Internal *this@<rcx>, AppxAllUserStore::Internal *@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044624`

## callees

- `0x180002108`
- `0x180002200`
- `0x1800039e4`
- `0x180004920`
- `0x1800054a4`
- `0x180007a10`
- `0x180008db0`
- `0x18000a170`
- `0x18000e824`
- `0x18000fda0`
- `0x180010384`
- `0x18001073c`
- `0x180012c3c`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x18001ed30`
- `0x18001fe6c`
- `0x180030d2c`
- `0x180033768`
- `0x1800414c8`
- `0x1800417fc`
- `0x1800421f4`
- `0x180043080`
- `0x1800432ac`
- `0x180043b10`
- `0x18004445c`
- `0x1800447c8`
- `0x180045580`
- `0x18004931c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800441ed`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800441ed`

## string_xrefs

- `0x180043ba4`: `GetOfflineFolderPath %ws failed, 0x%0x.`
- `0x180043bc5`: `ExpandEnvironmentInPath %ws failed, 0x%0x.`
- `0x180043ce9`: `Droping non-existent main package path %ws.`
- `0x180043f41`: `GetOfflineFolderPath %ls failed.`
- `0x180044145`: `AddPackagePathsToMainArrayIfNeeded %u failed.`
- `0x18004423b`: `GetPackagesInBundleByPath %ls`
- `0x1800442ea`: `AddPackagePathsToMainArrayIfNeeded %u failed, 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::ProcessMainPackage(
        AppxAllUserStore::Internal *this,
        AppxAllUserStore::Internal *a2,
        __int64 a3,
        struct Common::StringBuffer *a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // eax
  __int64 *v9; // r15
  struct AppxAllUserStore::BasicLogFile *v10; // rdx
  int OfflineFolderPath; // edi
  bool *v12; // r8
  unsigned int v13; // esi
  int v14; // eax
  char v15; // di
  int v16; // eax
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r13
  int v23; // eax
  int v24; // eax
  unsigned __int16 *v25; // r8
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  int PackagesInBundleByPath; // eax
  const unsigned __int16 *v29; // r8
  int v30; // eax
  struct Common::StringBuffer *v31; // rdx
  int PackageRepositoryRoot; // eax
  __int64 v33; // rdx
  const unsigned __int16 *v34; // rdx
  struct Common::StringBuffer *v35; // r9
  int v36; // eax
  char v37; // di
  int v38; // eax
  const unsigned __int16 *v39; // r8
  int v40; // eax
  unsigned __int16 **v41; // r9
  const WCHAR *v42; // rcx
  unsigned __int16 *v43; // rcx
  int v44; // eax
  int v45; // eax
  unsigned __int16 *v46; // rcx
  int v47; // eax
  const struct _tlgProvider_t *v48; // rax
  __int64 v49; // r8
  __int64 v50; // r9
  unsigned int v51; // edi
  int v52; // eax
  unsigned int v53; // esi
  const unsigned __int16 *v54; // r8
  int v55; // eax
  int v56; // eax
  const struct _tlgProvider_t *v57; // rax
  __int64 v58; // r8
  __int64 v59; // r9
  int v60; // eax
  int v61; // eax
  const struct _tlgProvider_t *v62; // rax
  __int64 v63; // r8
  __int64 v64; // r9
  int v65; // eax
  __int64 v66; // rdx
  const struct _tlgProvider_t *v67; // rax
  __int64 v68; // r8
  __int64 v69; // r9
  unsigned __int16 v71[4]; // [rsp+20h] [rbp-B9h]
  char *v72; // [rsp+28h] [rbp-B1h]
  _QWORD v73[2]; // [rsp+40h] [rbp-99h] BYREF
  const unsigned __int16 *v74; // [rsp+50h] [rbp-89h]
  char v75; // [rsp+58h] [rbp-81h]
  Common *v76[2]; // [rsp+60h] [rbp-79h] BYREF
  int v77; // [rsp+70h] [rbp-69h]
  char *v78[2]; // [rsp+78h] [rbp-61h] BYREF
  int v79; // [rsp+88h] [rbp-51h]
  DWORD dwMilliseconds[2]; // [rsp+90h] [rbp-49h] BYREF
  unsigned int v81[2]; // [rsp+98h] [rbp-41h] BYREF
  int v82; // [rsp+A0h] [rbp-39h]
  int v83; // [rsp+A4h] [rbp-35h]
  int v84; // [rsp+A8h] [rbp-31h]
  Common::Deployment *v85[2]; // [rsp+B0h] [rbp-29h] BYREF
  int v86; // [rsp+C0h] [rbp-19h]
  const unsigned __int16 *v87; // [rsp+C8h] [rbp-11h] BYREF
  int v88[2]; // [rsp+D0h] [rbp-9h] BYREF
  unsigned int *v89[9]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]
  Common *v91; // [rsp+130h] [rbp+57h] BYREF
  unsigned __int16 *Src; // [rsp+138h] [rbp+5Fh] BYREF

  if ( this )
  {
    v8 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"ProcessMainPackage %ws %ws.", a2, *((_QWORD *)a4 + 1));
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16B,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v8);
  }
  v9 = (__int64 *)a5;
  v77 = 0;
  *(_OWORD *)v76 = 0;
  v10 = *(struct AppxAllUserStore::BasicLogFile **)(a5 + 8);
  if ( !a2 )
  {
    OfflineFolderPath = AppxAllUserStore::Internal::ExpandEnvironmentInPath(this, v10, (Common::StringBuffer *)v76, a4);
    if ( OfflineFolderPath < 0 )
    {
      v13 = 376;
      if ( !this )
        goto LABEL_13;
      v14 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"ExpandEnvironmentInPath %ws failed, 0x%0x.",
              v9[1],
              (unsigned int)OfflineFolderPath);
LABEL_11:
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v13,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v14);
      goto LABEL_13;
    }
LABEL_14:
    LOBYTE(v91) = 0;
    OfflineFolderPath = Common::FileExists(v76[1], (const unsigned __int16 *)&v91, v12);
    if ( OfflineFolderPath < 0 )
    {
      v13 = 382;
      if ( !this )
        goto LABEL_13;
      v14 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"FileExists %ws failed 0x%0x.",
              v76[1],
              (unsigned int)OfflineFolderPath);
      goto LABEL_11;
    }
    v15 = (char)v91;
    if ( this )
    {
      v16 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"Existence of package %ws is %u.",
              v76[1],
              (unsigned __int8)v91);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x181,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v16);
    }
    if ( !v15 )
    {
      v17 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v17 > 5u && (unsigned __int8)tlgKeywordOn(v17, 0x400000000000LL, v17) )
      {
        Src = (unsigned __int16 *)v76[1];
        v91 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v18,
          (unsigned __int8 *)&word_18005D696,
          v18,
          v19,
          (const unsigned __int16 **)&Src,
          (const unsigned __int16 **)&v91);
      }
      LOBYTE(v71[0]) = 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)0x8000FFFFLL,
        *(int *)v71,
        (bool)"Droping non-existent main package path %ws.",
        (const char *)v76[1]);
      if ( !this )
        goto LABEL_109;
      v20 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"WARNING: Droping non-existent package %ws.", v76[1]);
      if ( v20 >= 0 )
        goto LABEL_109;
      v21 = 398;
LABEL_108:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v21,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v20);
LABEL_109:
      OfflineFolderPath = 0;
      goto LABEL_110;
    }
    v22 = a6;
    v23 = AppxAllUserStore::Internal::ProcessMainPackageDependencies(this, (char *)a2, *v9, a6);
    OfflineFolderPath = v23;
    if ( v23 < 0 )
    {
      v13 = 413;
      if ( !this )
        goto LABEL_13;
      *(_DWORD *)v71 = v23;
      v24 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"ProcessMainPackageDependencies %ws size %u failed, 0x%0x.",
              *v9,
              *(unsigned int *)(v22 + 16));
LABEL_30:
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v13,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v24);
      goto LABEL_13;
    }
    v25 = (unsigned __int16 *)*v9;
    LOBYTE(v91) = 0;
    v26 = AppxAllUserStore::Internal::AddPackageFullNameToMainArrayIfNeeded(
            this,
            a2,
            v25,
            (_QWORD *)v22,
            (unsigned __int16 *)&v91);
    OfflineFolderPath = v26;
    if ( v26 < 0 )
    {
      v13 = 420;
      if ( !this )
        goto LABEL_13;
      v24 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"AddPackageFullNameToMainArrayIfNeeded %ws failed, 0x%0x.",
              *v9,
              (unsigned int)v26);
      goto LABEL_30;
    }
    if ( (_BYTE)v91 )
    {
      if ( Common::Deployment::IsPackageFullNameBundle((Common::Deployment *)*v9, v27) )
      {
        v73[0] = 0;
        v73[1] = 0;
        v74 = 0;
        v75 = 1;
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback>::__private_IsEnabled((__int64)&`wil::Feature<__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback>::GetImpl'::`2'::impl) )
        {
          PackagesInBundleByPath = Common::Deployment::GetPackagesInBundleByPath(v76[1], v73);
          if ( PackagesInBundleByPath >= 0 )
            goto LABEL_113;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B1,
            (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
            (const char *)(unsigned int)PackagesInBundleByPath);
          v30 = AppxAllUserStore::Internal::LogFileInformation(this, v76[1], v29);
          if ( v30 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1B3,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v30);
          v79 = 0;
          *(_OWORD *)v78 = 0;
          PackageRepositoryRoot = Common::Deployment::Configuration::GetPackageRepositoryRoot(
                                    (Common::Deployment::Configuration *)v78,
                                    v31);
          OfflineFolderPath = PackageRepositoryRoot;
          if ( PackageRepositoryRoot < 0 )
          {
            v33 = 438;
LABEL_44:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v33,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)PackageRepositoryRoot,
              *(int *)v71);
LABEL_45:
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v78);
LABEL_46:
            Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>((__int64)v73);
            goto LABEL_110;
          }
          v34 = (const unsigned __int16 *)*v9;
          v89[1] = (unsigned int *)v78;
          v89[0] = (unsigned int *)&Common::StringBufferBuilder::`vftable';
          v89[2] = (unsigned int *)v78;
          PackageRepositoryRoot = Common::PathHelpers::AppendPathSegment((struct Common::StringBufferBuilder *)v89, v34);
          OfflineFolderPath = PackageRepositoryRoot;
          if ( PackageRepositoryRoot < 0 )
          {
            v33 = 441;
            goto LABEL_44;
          }
          PackageRepositoryRoot = Common::StringBuilder::AppendString(v89, (const unsigned __int16 **)&qword_18004E770);
          OfflineFolderPath = PackageRepositoryRoot;
          if ( PackageRepositoryRoot < 0 )
          {
            v33 = 442;
            goto LABEL_44;
          }
          v86 = 0;
          *(_OWORD *)v85 = 0;
          if ( a2 )
          {
            OfflineFolderPath = AppxAllUserStore::Internal::GetOfflineFolderPath(
                                  a2,
                                  v78[1],
                                  (const unsigned __int16 *)v85,
                                  v35);
            if ( OfflineFolderPath < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x1C0,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)OfflineFolderPath,
                (int)"GetOfflineFolderPath %ls failed.",
                v78[1]);
LABEL_54:
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v85);
              goto LABEL_45;
            }
          }
          else
          {
            v36 = Common::StringBuffer::SetValueFromString(
                    (Common::StringBuffer *)v85,
                    (const unsigned __int16 *)v78[1]);
            OfflineFolderPath = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1C4,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v36,
                *(int *)v71);
              goto LABEL_54;
            }
          }
          v37 = 0;
          v38 = Common::Deployment::GetPackagesInBundleByPath(v85[1], v73);
          if ( v38 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1C9,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v38);
            v40 = AppxAllUserStore::Internal::LogFileInformation(this, v85[1], v39);
            if ( v40 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1CB,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v40);
            v42 = (const WCHAR *)*v9;
            *(_QWORD *)dwMilliseconds = &Src;
            Src = 0;
            LODWORD(v91) = 0;
            *(_QWORD *)v81 = 0;
            LOBYTE(v82) = 1;
            OfflineFolderPath = AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(
                                  v42,
                                  (unsigned __int16 *)&v91,
                                  v81,
                                  v41);
            wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>>((__int64)dwMilliseconds);
            if ( OfflineFolderPath < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1CF,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)OfflineFolderPath,
                *(int *)v71);
              v43 = Src;
              Src = 0;
              if ( v43 )
                Common::GlobalHeap::Free(v43);
              goto LABEL_54;
            }
            v44 = AppxAllUserStore::Internal::ProcessPackageFamily(this, a2, Src);
            if ( this )
            {
              *(_DWORD *)v71 = v44;
              v45 = AppxAllUserStore::BasicLogFile::WriteMsg(
                      this,
                      L"Added All Bundle Packages %ls : %u, 0x%0x.",
                      Src,
                      *(unsigned int *)(v22 + 16),
                      *(_QWORD *)v71);
              if ( v45 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1D3,
                  (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                  (const char *)(unsigned int)v45);
            }
            v46 = Src;
            v37 = 1;
            Src = 0;
            if ( v46 )
              Common::GlobalHeap::Free(v46);
          }
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v85);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v78);
          if ( !v37 )
          {
LABEL_113:
            if ( this )
            {
              v47 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Found %u packages.", (unsigned int)v74);
              if ( v47 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1DA,
                  (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                  (const char *)(unsigned int)v47);
            }
            v48 = AppxAllUserStoreTelemetry::Provider();
            if ( *(_DWORD *)v48 > 5u )
            {
              v91 = (Common *)v74;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
                (__int64)v48,
                (__int64)word_18005D662,
                v49,
                v50,
                (__int64)&v91);
            }
            OfflineFolderPath = AppxAllUserStore::Internal::AddPackagePathsToMainArrayIfNeeded(this, a2, v73, v22);
            if ( OfflineFolderPath < 0 )
            {
              LODWORD(v72) = *(_DWORD *)(v22 + 16);
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x1E2,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)OfflineFolderPath,
                (int)"AddPackagePathsToMainArrayIfNeeded %u failed.",
                v72);
              goto LABEL_46;
            }
          }
        }
        else
        {
          dwMilliseconds[0] = 1000;
          v51 = 0;
          dwMilliseconds[1] = 2000;
          v81[0] = 4000;
          v81[1] = 7000;
          v82 = 11000;
          v83 = 15000;
          v84 = 20000;
          while ( 1 )
          {
            v52 = Common::Deployment::GetPackagesInBundleByPath(v76[1], v73);
            v53 = v52;
            if ( v52 >= 0 )
              break;
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1EF,
              (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)v52);
            if ( v51 >= 7 )
            {
              v55 = AppxAllUserStore::Internal::LogFileInformation(this, v76[1], v54);
              if ( v55 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1F9,
                  (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                  (const char *)(unsigned int)v55);
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x1FA,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)v53,
                (int)"GetPackagesInBundleByPath %ls",
                (const char *)v76[1]);
              Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>((__int64)v73);
              OfflineFolderPath = v53;
              goto LABEL_110;
            }
            Sleep(dwMilliseconds[v51++]);
          }
          if ( this )
          {
            v56 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Found %u packages.", (unsigned int)v74);
            if ( v56 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1FE,
                (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                (const char *)(unsigned int)v56);
          }
          v57 = AppxAllUserStoreTelemetry::Provider();
          if ( *(_DWORD *)v57 > 5u )
          {
            v91 = (Common *)v74;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
              (__int64)v57,
              (__int64)&word_18005D62E,
              v58,
              v59,
              (__int64)&v91);
          }
          v60 = AppxAllUserStore::Internal::AddPackagePathsToMainArrayIfNeeded(this, a2, v73, v22);
          OfflineFolderPath = v60;
          if ( v60 < 0 )
          {
            if ( this )
            {
              v61 = AppxAllUserStore::BasicLogFile::WriteMsg(
                      this,
                      L"AddPackagePathsToMainArrayIfNeeded %u failed, 0x%0x.",
                      *(unsigned int *)(v22 + 16),
                      (unsigned int)v60);
              if ( v61 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x20A,
                  (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
                  (const char *)(unsigned int)v61);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x20A,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
              (const char *)(unsigned int)OfflineFolderPath,
              *(int *)v71);
            goto LABEL_46;
          }
        }
        Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>((__int64)v73);
LABEL_103:
        v67 = AppxAllUserStoreTelemetry::Provider();
        if ( *(_DWORD *)v67 > 5u )
        {
          v91 = *(Common **)(v22 + 16);
          *(_QWORD *)v88 = v9[1];
          v87 = (const unsigned __int16 *)a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            (__int64)v67,
            (__int64)&byte_18005D5B7,
            v68,
            v69,
            (const unsigned __int16 **)v88,
            &v87,
            (__int64)&v91);
        }
        if ( !this )
          goto LABEL_109;
        v20 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Main array size is %u.", *(unsigned int *)(v22 + 16));
        if ( v20 >= 0 )
          goto LABEL_109;
        v21 = 546;
        goto LABEL_108;
      }
      v62 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v62 > 5u )
      {
        v91 = v76[1];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v62,
          (unsigned __int8 *)&dword_18005D5FC,
          v63,
          v64,
          (const unsigned __int16 **)&v91);
      }
      if ( !this )
        goto LABEL_103;
      v65 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Skipping non-bundle.");
      if ( v65 >= 0 )
        goto LABEL_103;
      v66 = 531;
    }
    else
    {
      if ( !this )
        goto LABEL_103;
      v65 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Package %ws was NOT added to main array.", *v9);
      if ( v65 >= 0 )
        goto LABEL_103;
      v66 = 536;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v66,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)(unsigned int)v65);
    goto LABEL_103;
  }
  OfflineFolderPath = AppxAllUserStore::Internal::GetOfflineFolderPath(
                        a2,
                        (char *)v10,
                        (const unsigned __int16 *)v76,
                        a4);
  if ( OfflineFolderPath >= 0 )
    goto LABEL_14;
  v13 = 370;
  if ( this )
  {
    v14 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"GetOfflineFolderPath %ws failed, 0x%0x.",
            v9[1],
            (unsigned int)OfflineFolderPath);
    goto LABEL_11;
  }
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
    (const char *)(unsigned int)OfflineFolderPath,
    *(int *)v71);
LABEL_110:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v76);
  return (unsigned int)OfflineFolderPath;
}

```

## disassembly

```asm
0x180043b10  mov     [rsp-8+arg_10], rbx
0x180043b15  push    rbp
0x180043b16  push    rsi
0x180043b17  push    rdi
0x180043b18  push    r12
0x180043b1a  push    r13
0x180043b1c  push    r14
0x180043b1e  push    r15
0x180043b20  lea     rbp, [rsp-17h]
0x180043b25  sub     rsp, 0F0h
0x180043b2c  lea     r13, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180043b33  mov     rsi, r9
0x180043b36  mov     r12, r8
0x180043b39  mov     r14, rdx
0x180043b3c  mov     rbx, rcx
0x180043b3f  test    rcx, rcx
0x180043b42  jz      short loc_180043B6F
0x180043b44  mov     r9, [r9+8]
0x180043b48  mov     r8, rdx
0x180043b4b  lea     rdx, aProcessmainpac_4; "ProcessMainPackage %ws %ws."
0x180043b52  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043b57  test    eax, eax
0x180043b59  jns     short loc_180043B6F
0x180043b5b  mov     rcx, [rbp+4Fh]; this
0x180043b5f  mov     r9d, eax; char *
0x180043b62  mov     r8, r13; unsigned int
0x180043b65  mov     edx, 16Bh; void *
0x180043b6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043b6f  mov     r15, [rbp+47h+arg_20]
0x180043b73  lea     r8, [rbp+47h+var_C0]; Common::StringBuffer *
0x180043b77  xor     eax, eax
0x180043b79  xorps   xmm0, xmm0
0x180043b7c  mov     [rbp+47h+var_B0], eax
0x180043b7f  movups  xmmword ptr [rbp+47h+var_C0], xmm0
0x180043b83  mov     rdx, [r15+8]; struct AppxAllUserStore::BasicLogFile *
0x180043b87  test    r14, r14
0x180043b8a  jz      short loc_180043BAD
0x180043b8c  mov     rcx, r14; this
0x180043b8f  call    ?GetOfflineFolderPath@Internal@AppxAllUserStore@@YAJPEBG0AEAVStringBuffer@Common@@@Z; AppxAllUserStore::Internal::GetOfflineFolderPath(ushort const *,ushort const *,Common::StringBuffer &)
0x180043b94  mov     edi, eax
0x180043b96  test    eax, eax
0x180043b98  jns     short loc_180043C06
0x180043b9a  mov     esi, 172h
0x180043b9f  test    rbx, rbx
0x180043ba2  jz      short loc_180043BF0
0x180043ba4  lea     rdx, aGetofflinefold_0; "GetOfflineFolderPath %ws failed, 0x%0x."
0x180043bab  jmp     short loc_180043BCC
0x180043bad  mov     rcx, rbx; this
0x180043bb0  call    ?ExpandEnvironmentInPath@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::Internal::ExpandEnvironmentInPath(AppxAllUserStore::BasicLogFile *,ushort const *,Common::StringBuffer &)
0x180043bb5  mov     edi, eax
0x180043bb7  test    eax, eax
0x180043bb9  jns     short loc_180043C06
0x180043bbb  mov     esi, 178h
0x180043bc0  test    rbx, rbx
0x180043bc3  jz      short loc_180043BF0
0x180043bc5  lea     rdx, aExpandenvironm; "ExpandEnvironmentInPath %ws failed, 0x%"...
0x180043bcc  mov     r8, [r15+8]
0x180043bd0  mov     r9d, edi
0x180043bd3  mov     rcx, rbx; this
0x180043bd6  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043bdb  test    eax, eax
0x180043bdd  jns     short loc_180043BF0
0x180043bdf  mov     rcx, [rbp+4Fh]; this
0x180043be3  mov     r9d, eax; char *
0x180043be6  mov     r8, r13; unsigned int
0x180043be9  mov     edx, esi; void *
0x180043beb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043bf0  mov     r8, r13; unsigned int
0x180043bf3  mov     rcx, [rbp+4Fh]; this
0x180043bf7  mov     r9d, edi; char *
0x180043bfa  mov     edx, esi; void *
0x180043bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043c01  jmp     loc_18004442E
0x180043c06  mov     rcx, [rbp+47h+var_C0+8]; this
0x180043c0a  lea     rdx, [rbp+47h+arg_0]; unsigned __int16 *
0x180043c0e  mov     byte ptr [rbp+47h+arg_0], 0
0x180043c12  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x180043c17  mov     edi, eax
0x180043c19  test    eax, eax
0x180043c1b  jns     short loc_180043C34
0x180043c1d  mov     esi, 17Eh
0x180043c22  test    rbx, rbx
0x180043c25  jz      short loc_180043BF0
0x180043c27  mov     r8, [rbp+47h+var_C0+8]
0x180043c2b  lea     rdx, aFileexistsWsFa; "FileExists %ws failed 0x%0x."
0x180043c32  jmp     short loc_180043BD0
0x180043c34  movzx   edi, byte ptr [rbp+47h+arg_0]
0x180043c38  test    rbx, rbx
0x180043c3b  jz      short loc_180043C6B
0x180043c3d  mov     r8, [rbp+47h+var_C0+8]
0x180043c41  lea     rdx, aExistenceOfPac; "Existence of package %ws is %u."
0x180043c48  mov     r9d, edi
0x180043c4b  mov     rcx, rbx; this
0x180043c4e  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043c53  test    eax, eax
0x180043c55  jns     short loc_180043C6B
0x180043c57  mov     rcx, [rbp+4Fh]; this
0x180043c5b  mov     r9d, eax; char *
0x180043c5e  mov     r8, r13; unsigned int
0x180043c61  mov     edx, 181h; void *
0x180043c66  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043c6b  test    dil, dil
0x180043c6e  jnz     loc_180043D30
0x180043c74  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180043c79  mov     r8, rax
0x180043c7c  mov     ecx, [rax]
0x180043c7e  cmp     ecx, 5
0x180043c81  jbe     short loc_180043CCB
0x180043c83  mov     rdx, 400000000000h
0x180043c8d  mov     rcx, rax
0x180043c90  call    _tlgKeywordOn
0x180043c95  xor     r12d, r12d
0x180043c98  test    al, al
0x180043c9a  jz      short loc_180043CCE
0x180043c9c  mov     rax, [rbp+47h+var_C0+8]
0x180043ca0  lea     rdx, word_18005D696
0x180043ca7  mov     [rbp+47h+Src], rax
0x180043cab  mov     rcx, r8
0x180043cae  lea     rax, [rbp+47h+arg_0]
0x180043cb2  mov     [rbp+47h+arg_0], r14
0x180043cb6  mov     [rsp+120h+var_F8], rax
0x180043cbb  lea     rax, [rbp+47h+Src]
0x180043cbf  mov     qword ptr [rsp+120h+var_100], rax
0x180043cc4  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180043cc9  jmp     short loc_180043CCE
0x180043ccb  xor     r12d, r12d
0x180043cce  mov     rax, [rbp+47h+var_C0+8]
0x180043cd2  mov     r9d, 8000FFFFh; char *
0x180043cd8  mov     rcx, [rbp+4Fh]; this
0x180043cdc  mov     r8, r13; unsigned int
0x180043cdf  mov     [rsp+120h+var_F0], rax; char *
0x180043ce4  mov     edx, 18Dh; void *
0x180043ce9  lea     rax, aDropingNonExis; "Droping non-existent main package path "...
0x180043cf0  mov     [rsp+120h+var_F8], rax; bool
0x180043cf5  mov     byte ptr [rsp+120h+var_100], 1; int
0x180043cfa  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180043cff  test    rbx, rbx
0x180043d02  jz      loc_18004442B
0x180043d08  mov     r8, [rbp+47h+var_C0+8]
0x180043d0c  lea     rdx, aWarningDroping; "WARNING: Droping non-existent package %"...
0x180043d13  mov     rcx, rbx; this
0x180043d16  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043d1b  test    eax, eax
0x180043d1d  jns     loc_18004442B
0x180043d23  mov     r8, r13
0x180043d26  mov     edx, 18Eh
0x180043d2b  jmp     loc_18004441F
0x180043d30  mov     rax, [r15]
0x180043d33  mov     r9, rsi
0x180043d36  mov     r13, [rbp+47h+arg_28]
0x180043d3a  mov     r8, r12
0x180043d3d  mov     [rsp+120h+var_F8], r13; __int64
0x180043d42  mov     rdx, r14; char *
0x180043d45  mov     rcx, rbx; this
0x180043d48  mov     qword ptr [rsp+120h+var_100], rax; __int64
0x180043d4d  call    ?ProcessMainPackageDependencies@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGQEAUHKEY__@@PEBVStringBuffer@Common@@1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@6@@Z; AppxAllUserStore::Internal::ProcessMainPackageDependencies(AppxAllUserStore::BasicLogFile *,ushort const *,HKEY__ * const,Common::StringBuffer const *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x180043d52  xor     r12d, r12d
0x180043d55  mov     edi, eax
0x180043d57  test    eax, eax
0x180043d59  jns     short loc_180043DA4
0x180043d5b  mov     esi, 19Dh
0x180043d60  test    rbx, rbx
0x180043d63  jz      short loc_180043D98
0x180043d65  mov     r9d, [r13+10h]
0x180043d69  lea     rdx, aProcessmainpac_1; "ProcessMainPackageDependencies %ws size"...
0x180043d70  mov     r8, [r15]
0x180043d73  mov     rcx, rbx; this
0x180043d76  mov     dword ptr [rsp+120h+var_100], eax; int
0x180043d7a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043d7f  test    eax, eax
0x180043d81  jns     short loc_180043D98
0x180043d83  mov     rcx, [rbp+4Fh]; this
0x180043d87  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180043d8e  mov     r9d, eax; char *
0x180043d91  mov     edx, esi; void *
0x180043d93  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043d98  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180043d9f  jmp     loc_180043BF3
0x180043da4  mov     r8, [r15]; unsigned __int16 *
0x180043da7  lea     rax, [rbp+47h+arg_0]
0x180043dab  mov     r9, r13
0x180043dae  mov     qword ptr [rsp+120h+var_100], rax; int
0x180043db3  mov     rdx, r14; struct AppxAllUserStore::BasicLogFile *
0x180043db6  mov     byte ptr [rbp+47h+arg_0], r12b
0x180043dba  mov     rcx, rbx; this
0x180043dbd  call    ?AddPackageFullNameToMainArrayIfNeeded@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBG1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@AEA_N@Z; AppxAllUserStore::Internal::AddPackageFullNameToMainArrayIfNeeded(AppxAllUserStore::BasicLogFile *,ushort const *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &,bool &)
0x180043dc2  mov     edi, eax
0x180043dc4  test    eax, eax
0x180043dc6  jns     short loc_180043DE9
0x180043dc8  mov     esi, 1A4h
0x180043dcd  test    rbx, rbx
0x180043dd0  jz      short loc_180043D98
0x180043dd2  mov     r8, [r15]
0x180043dd5  lea     rdx, aAddpackagefull_0; "AddPackageFullNameToMainArrayIfNeeded %"...
0x180043ddc  mov     r9d, eax
0x180043ddf  mov     rcx, rbx; this
0x180043de2  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180043de7  jmp     short loc_180043D7F
0x180043de9  cmp     byte ptr [rbp+47h+arg_0], r12b
0x180043ded  jz      loc_18004437A
0x180043df3  mov     rcx, [r15]; this
0x180043df6  call    ?IsPackageFullNameBundle@Deployment@Common@@YA_NPEBG@Z; Common::Deployment::IsPackageFullNameBundle(ushort const *)
0x180043dfb  test    al, al
0x180043dfd  jz      loc_18004432F
0x180043e03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback> `wil::Feature<__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback>::GetImpl(void)'::`2'::impl
0x180043e0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PBRBetterEffortBundleManifestFallback>::__private_IsEnabled(void)
0x180043e0f  mov     [rsp+120h+var_E0], r12
0x180043e14  mov     [rsp+120h+var_D8], r12
0x180043e19  mov     [rsp+120h+var_D0], r12
0x180043e1e  mov     [rsp+120h+var_C8], 1
0x180043e23  test    al, al
0x180043e25  jz      loc_18004417D
0x180043e2b  mov     rcx, [rbp+47h+var_C0+8]; this
0x180043e2f  lea     rdx, [rsp+120h+var_E0]
0x180043e34  call    ?GetPackagesInBundleByPath@Deployment@Common@@YAJPEBGAEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@2@@Z; Common::Deployment::GetPackagesInBundleByPath(ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x180043e39  lea     rsi, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180043e40  test    eax, eax
0x180043e42  jns     loc_1800440CA
0x180043e48  mov     rcx, [rbp+4Fh]; this
0x180043e4c  mov     r9d, eax; char *
0x180043e4f  mov     r8, rsi; unsigned int
0x180043e52  mov     edx, 1B1h; void *
0x180043e57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043e5c  mov     rdx, [rbp+47h+var_C0+8]; struct AppxAllUserStore::BasicLogFile *
0x180043e60  mov     rcx, rbx; this
0x180043e63  call    ?LogFileInformation@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBG@Z; AppxAllUserStore::Internal::LogFileInformation(AppxAllUserStore::BasicLogFile *,ushort const *)
0x180043e68  test    eax, eax
0x180043e6a  jns     short loc_180043E80
0x180043e6c  mov     rcx, [rbp+4Fh]; this
0x180043e70  mov     r9d, eax; char *
0x180043e73  mov     r8, rsi; unsigned int
0x180043e76  mov     edx, 1B3h; void *
0x180043e7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043e80  xorps   xmm0, xmm0
0x180043e83  mov     [rbp+47h+var_98], r12d
0x180043e87  lea     rcx, [rbp+47h+var_A8]; this
0x180043e8b  movups  xmmword ptr [rbp+47h+var_A8], xmm0
0x180043e8f  call    ?GetPackageRepositoryRoot@Configuration@Deployment@Common@@YAJPEAVStringBuffer@3@@Z; Common::Deployment::Configuration::GetPackageRepositoryRoot(Common::StringBuffer *)
0x180043e94  mov     edi, eax
0x180043e96  test    eax, eax
0x180043e98  jns     short loc_180043EC6
0x180043e9a  mov     edx, 1B6h; void *
0x180043e9f  mov     rcx, [rbp+4Fh]; this
0x180043ea3  mov     r9d, eax; char *
0x180043ea6  mov     r8, rsi; unsigned int
0x180043ea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043eae  lea     rcx, [rbp+47h+var_A8]; this
0x180043eb2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180043eb7  lea     rcx, [rsp+120h+var_E0]
0x180043ebc  call    ??1?$Array@U_SharedPackageContainerInfo@AppxAllUserStore@@V?$ContainerOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_SharedPackageContainerInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@QEAA@XZ; Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(void)
0x180043ec1  jmp     loc_18004442E
0x180043ec6  mov     rdx, [r15]; unsigned __int16 *
0x180043ec9  lea     rax, [rbp+47h+var_A8]
0x180043ecd  mov     [rbp+47h+var_40], rax
0x180043ed1  lea     rcx, [rbp+47h+var_48]; struct Common::StringBufferBuilder *
0x180043ed5  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180043edc  mov     [rbp+47h+var_48], rax
0x180043ee0  lea     rax, [rbp+47h+var_A8]
0x180043ee4  mov     [rbp+47h+var_38], rax
0x180043ee8  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBufferBuilder *,ushort const *)
0x180043eed  mov     edi, eax
0x180043eef  test    eax, eax
0x180043ef1  jns     short loc_180043EFA
0x180043ef3  mov     edx, 1B9h
0x180043ef8  jmp     short loc_180043E9F
0x180043efa  lea     rdx, qword_18004E770; struct Common::COMMON_STRING *
0x180043f01  lea     rcx, [rbp+47h+var_48]; this
0x180043f05  call    ?AppendString@StringBuilder@Common@@QEAAJPEBUCOMMON_STRING@2@@Z; Common::StringBuilder::AppendString(Common::COMMON_STRING const *)
0x180043f0a  mov     edi, eax
0x180043f0c  test    eax, eax
0x180043f0e  jns     short loc_180043F17
0x180043f10  mov     edx, 1BAh
0x180043f15  jmp     short loc_180043E9F
0x180043f17  mov     rdx, [rbp+47h+var_A8+8]; Src
0x180043f1b  xorps   xmm0, xmm0
0x180043f1e  mov     [rbp+47h+var_60], r12d
0x180043f22  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x180043f26  test    r14, r14
0x180043f29  jz      short loc_180043F74
0x180043f2b  lea     r8, [rbp+47h+var_70]; unsigned __int16 *
0x180043f2f  mov     rcx, r14; this
0x180043f32  call    ?GetOfflineFolderPath@Internal@AppxAllUserStore@@YAJPEBG0AEAVStringBuffer@Common@@@Z; AppxAllUserStore::Internal::GetOfflineFolderPath(ushort const *,ushort const *,Common::StringBuffer &)
0x180043f37  mov     edi, eax
0x180043f39  test    eax, eax
0x180043f3b  jns     short loc_180043F99
0x180043f3d  mov     rdx, [rbp+47h+var_A8+8]
0x180043f41  lea     rax, aGetofflinefold; "GetOfflineFolderPath %ls failed."
0x180043f48  mov     rcx, [rbp+4Fh]; this
0x180043f4c  mov     r9d, edi; char *
0x180043f4f  mov     [rsp+120h+var_F8], rdx; char *
0x180043f54  mov     r8, rsi; unsigned int
0x180043f57  mov     edx, 1C0h; void *
0x180043f5c  mov     qword ptr [rsp+120h+var_100], rax; int
0x180043f61  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180043f66  lea     rcx, [rbp+47h+var_70]; this
0x180043f6a  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180043f6f  jmp     loc_180043EAE
0x180043f74  lea     rcx, [rbp+47h+var_70]; this
0x180043f78  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180043f7d  mov     edi, eax
  ... truncated ...
```
