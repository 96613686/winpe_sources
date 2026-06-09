# OSIntegration::Package::InitializePackageFromRepository(void)

- ea: `0x18001cb00`
- end: `0x18001d742`
- name: `?InitializePackageFromRepository@Package@OSIntegration@@AEAAJXZ`
- size: `3138`
- prototype: `__int64 __fastcall(OSIntegration::Package *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007d844`

## callees

- `0x180005e08`
- `0x180009dc0`
- `0x180012fc8`
- `0x180014860`
- `0x18001adb4`
- `0x18001cb00`
- `0x18001d748`
- `0x18001d7f0`
- `0x18001d99c`
- `0x18001d9bc`
- `0x18001e6f0`
- `0x180056260`
- `0x180056e38`
- `0x180056f8c`
- `0x18008678c`
- `0x1800867cc`
- `0x180086ab8`
- `0x180086c5c`
- `0x180087604`
- `0x18008d658`
- `0x18008f5ec`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x1800d8354`
- `0x1800da1fc`
- `0x1800da6cc`
- `0x1800da864`
- `0x1800da964`
- `0x180132b00`
- `0x18017e6fc`
- `0x18017f550`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18001d279`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18001d279`

## string_xrefs

- `0x18001cb5c`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001cba0`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001cc61`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d1a7`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d209`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d2bc`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d31e`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d3da`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d43c`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d489`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d4cc`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d53f`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d5b5`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18001d610`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`

## pseudocode

```c
__int64 __fastcall OSIntegration::Package::InitializePackageFromRepository(OSIntegration::Package *this)
{
  __int64 v2; // rcx
  signed int IsUserExternalLocation; // ebx
  __int64 v4; // rdx
  const struct std::nothrow_t *v5; // rdx
  _DWORD *v7; // rbx
  int appended; // esi
  __int64 v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  _DWORD *v11; // rsi
  PackageRepository::PackageRow *v12; // rbx
  int ExternalLocationInfo; // eax
  PackageRepository::PackageRow *v14; // rdx
  PackageRepository::PackageRow *v15; // rdx
  PackageRepository::PackageRow *v16; // r8
  PackageRepository::PackageRow *v17; // r8
  const unsigned __int16 *v18; // rdx
  signed int v19; // eax
  struct Common::StringBuffer *v20; // r8
  __int64 v21; // rdx
  int v22; // ecx
  struct Common::Deployment::Volume *v23; // rsi
  const struct std::nothrow_t *v24; // rdx
  __int64 v25; // rax
  WCHAR *v26; // r14
  LONG v27; // eax
  struct Common::StringBuffer *v28; // r8
  __int64 v29; // rdx
  int v30; // ecx
  struct Common::Deployment::Volume *v31; // rsi
  const struct std::nothrow_t *v32; // rdx
  WCHAR *v33; // rcx
  signed int v34; // eax
  struct Common::StringBuffer *v35; // r8
  __int64 v36; // rdx
  int v37; // ecx
  struct Common::Deployment::Volume *v38; // rsi
  const struct std::nothrow_t *v39; // rdx
  int v40; // eax
  int v41; // eax
  StatePaths *v42; // rcx
  const struct std::nothrow_t *v43; // rdx
  unsigned __int16 *v44; // rcx
  struct Common::Deployment::Volume *v45; // rsi
  int StateRootFolderPathForVolume; // eax
  const struct std::nothrow_t *v47; // rdx
  const unsigned __int16 *v48; // r8
  int MetadataDirectory; // eax
  const struct std::nothrow_t *v50; // rdx
  unsigned __int16 *v51; // rbx
  int v52; // eax
  unsigned int v53; // r14d
  const struct std::nothrow_t *v54; // rdx
  const struct std::nothrow_t *v55; // rdx
  const struct std::nothrow_t *v56; // rdx
  const struct std::nothrow_t *v57; // rdx
  const unsigned __int16 *v58; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v59; // [rsp+20h] [rbp-E0h]
  int v60; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v61; // [rsp+30h] [rbp-D0h]
  unsigned int *v62; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v63[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v64; // [rsp+50h] [rbp-B0h]
  struct Common::Deployment::Volume *v65[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v66; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v67; // [rsp+70h] [rbp-90h] BYREF
  struct PackageRepository::ITable *v68; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v69; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  __int128 v72; // [rsp+98h] [rbp-68h]
  __int64 v73; // [rsp+A8h] [rbp-58h]
  __int128 v74; // [rsp+B0h] [rbp-50h]
  __int64 v75; // [rsp+C0h] [rbp-40h]
  __int128 v76; // [rsp+C8h] [rbp-38h]
  __int64 v77; // [rsp+D8h] [rbp-28h]
  __int128 v78; // [rsp+E0h] [rbp-20h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int16 v80; // [rsp+F8h] [rbp-8h]
  WCHAR *v81; // [rsp+100h] [rbp+0h]
  void **v82; // [rsp+108h] [rbp+8h] BYREF
  unsigned int *v83; // [rsp+110h] [rbp+10h]
  unsigned __int16 **v84; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  UINT32 packageFamilyNameLength; // [rsp+170h] [rbp+70h] BYREF
  PackageRepository::PackageRow *v87; // [rsp+178h] [rbp+78h] BYREF
  __int64 v88; // [rsp+180h] [rbp+80h] BYREF
  char v89; // [rsp+188h] [rbp+88h] BYREF

  *(_OWORD *)v63 = 0;
  v64 = 0;
  v83 = (unsigned int *)v63;
  v82 = &Common::StringBufferBuilder::`vftable';
  v84 = v63;
  v2 = *((_QWORD *)this + 6);
  if ( !v2 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)0x8007054FLL,
      (int)v58);
  v70 = 0;
  v87 = 0;
  v68 = 0;
  v88 = 0;
  IsUserExternalLocation = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 40LL))(v2, &v70);
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 600;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v58);
LABEL_6:
    Common::AutoPtrDeallocate<PackageRepository::VisibilityRow>(v88);
    Common::AutoPtrDeallocate<PackageRepository::PackageRow>(v87);
    if ( v63[1] )
      operator delete(v63[1], v5);
    return (unsigned int)IsUserExternalLocation;
  }
  IsUserExternalLocation = (*(__int64 (__fastcall **)(_QWORD, struct PackageRepository::ITable **))(**((_QWORD **)this + 6)
                                                                                                  + 48LL))(
                             *((_QWORD *)this + 6),
                             &v68);
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 603;
    goto LABEL_5;
  }
  IsUserExternalLocation = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, PackageRepository::PackageRow **))(*(_QWORD *)v70 + 128LL))(
                             v70,
                             *((_QWORD *)this + 8),
                             *((_QWORD *)this + 98),
                             &v87);
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 606;
    goto LABEL_5;
  }
  v7 = (_DWORD *)((char *)this + 136);
  appended = Common::StringBuffer::SetValueFromString(
               (OSIntegration::Package *)((char *)this + 136),
               *((const unsigned __int16 **)v87 + 59));
  if ( appended < 0 )
  {
    v9 = 608;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)appended,
      (int)v58);
    Common::AutoPtrDeallocate<PackageRepository::VisibilityRow>(v88);
    Common::AutoPtrDeallocate<PackageRepository::PackageRow>(v87);
    if ( v63[1] )
      operator delete(v63[1], v10);
    return (unsigned int)appended;
  }
  if ( *v7 )
  {
    if ( *(_WORD *)(*((_QWORD *)this + 18) + 2LL * (unsigned int)(*v7 - 1)) != 92 )
    {
      v65[1] = (OSIntegration::Package *)((char *)this + 136);
      v65[0] = (struct Common::Deployment::Volume *)&Common::StringBufferBuilder::`vftable';
      v66 = (char *)this + 136;
      appended = Common::StringBuilder::AppendChar((Common::StringBuilder *)v65, 0x5Cu);
      if ( appended < 0 )
      {
        v9 = 613;
        goto LABEL_15;
      }
    }
  }
  *((_BYTE *)this + 408) = *v7 != 0;
  v11 = (_DWORD *)((char *)this + 112);
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 112),
                             *((const unsigned __int16 **)v87 + 61));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 617;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 160),
                             *((const unsigned __int16 **)v87 + 61));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 618;
    goto LABEL_5;
  }
  if ( *v11 )
  {
    if ( *(_WORD *)(*((_QWORD *)this + 15) + 2LL * (unsigned int)(*v11 - 1)) != 92 )
    {
      v65[1] = (OSIntegration::Package *)((char *)this + 112);
      v65[0] = (struct Common::Deployment::Volume *)&Common::StringBufferBuilder::`vftable';
      v66 = (char *)this + 112;
      IsUserExternalLocation = Common::StringBuilder::AppendChar((Common::StringBuilder *)v65, 0x5Cu);
      if ( IsUserExternalLocation < 0 )
      {
        v4 = 623;
        goto LABEL_5;
      }
    }
  }
  if ( *((_DWORD *)this + 40) )
    Common::PathHelpers::StripTrailingSlashIfNecessary((OSIntegration::Package *)((char *)this + 160));
  v12 = v87;
  if ( !*((_BYTE *)v87 + 624) )
  {
    ExternalLocationInfo = PackageRepository::PackageRow::LoadExternalLocationInfo(v87);
    appended = ExternalLocationInfo;
    if ( ExternalLocationInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\admin\\appmodel\\PackageRepository\\Inc\\External\\PackageRow.hpp",
        (const char *)(unsigned int)ExternalLocationInfo,
        (int)v58);
      v9 = 632;
      goto LABEL_15;
    }
    *((_BYTE *)v12 + 624) = 1;
  }
  IsUserExternalLocation = OSIntegration::Package::SetExternalLocation(this, *((const unsigned __int16 **)v12 + 73));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 633;
    goto LABEL_5;
  }
  IsUserExternalLocation = PackageRepository::PackageRow::GetIsUserExternalLocation(v87, (bool *)this + 208);
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 634;
    goto LABEL_5;
  }
  appended = Common::StringBuffer::SetValueFromString(
               (OSIntegration::Package *)((char *)this + 88),
               *((const unsigned __int16 **)v87 + 57));
  if ( appended < 0 )
  {
    v9 = 636;
    goto LABEL_15;
  }
  if ( *(_WORD *)(*((_QWORD *)this + 12) + 2LL * (unsigned int)(*((_DWORD *)this + 22) - 1)) != 92 )
  {
    v65[1] = (OSIntegration::Package *)((char *)this + 88);
    v65[0] = (struct Common::Deployment::Volume *)&Common::StringBufferBuilder::`vftable';
    v66 = (char *)this + 88;
    appended = Common::StringBuilder::AppendChar((Common::StringBuilder *)v65, 0x5Cu);
    if ( appended < 0 )
    {
      v9 = 641;
      goto LABEL_15;
    }
  }
  IsUserExternalLocation = Common::StringBuilder::AppendString(
                             (Common::StringBuilder *)&v82,
                             (OSIntegration::Package *)((char *)this + 88));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 646;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuilder::InsertChars(
                             (Common::StringBuilder *)&v82,
                             *v83,
                             L"AppxManifest.xml",
                             0x10u);
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 647;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::InitializeFromString(
                             (OSIntegration::Package *)((char *)this + 264),
                             v63[1]);
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 650;
    goto LABEL_5;
  }
  v63[1] = 0;
  LODWORD(v63[0]) = 0;
  v64 = 0;
  v14 = v87;
  *((_DWORD *)this + 96) = *((_DWORD *)v87 + 22);
  *((_DWORD *)this + 97) = *((_DWORD *)v14 + 23);
  *((_BYTE *)this + 412) = (*((_DWORD *)v14 + 22) & 0x80) != 0;
  *((_BYTE *)this + 413) = (*((_DWORD *)v14 + 22) & 0x800) != 0;
  *((_BYTE *)this + 414) = (*((_DWORD *)v14 + 22) & 0x400000) != 0;
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 440),
                             *((const unsigned __int16 **)v14 + 36));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 659;
    goto LABEL_5;
  }
  v15 = v87;
  *((_QWORD *)this + 58) = *((_QWORD *)v87 + 7);
  *((_DWORD *)this + 124) = *((_DWORD *)v15 + 12);
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 504),
                             *((const unsigned __int16 **)v15 + 4));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 664;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 528),
                             *((const unsigned __int16 **)v87 + 38));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 665;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 552),
                             *((const unsigned __int16 **)v87 + 40));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 666;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 216),
                             *((const unsigned __int16 **)v87 + 8));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 667;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 576),
                             *((const unsigned __int16 **)v87 + 12));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 668;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 600),
                             *((const unsigned __int16 **)v87 + 14));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 669;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 624),
                             *((const unsigned __int16 **)v87 + 16));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 670;
    goto LABEL_5;
  }
  IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                             (OSIntegration::Package *)((char *)this + 648),
                             *((const unsigned __int16 **)v87 + 18));
  if ( IsUserExternalLocation < 0 )
  {
    v4 = 671;
    goto LABEL_5;
  }
  v16 = v87;
  *((_DWORD *)this + 190) = *((_DWORD *)v87 + 46);
  *((_DWORD *)this + 191) = Common::Deployment::PackageInfo::ConvertStateRepositorySupportedUsersToCommonDeploymentSupportedUsers(*((unsigned int *)v16 + 47));
  *((_QWORD *)this + 54) = *((_QWORD *)v17 + 22);
  v18 = (const unsigned __int16 *)*((_QWORD *)v17 + 4);
  if ( v18 )
  {
    IsUserExternalLocation = Common::StringBuffer::SetValueFromString(
                               (OSIntegration::Package *)((char *)this + 504),
                               v18);
    if ( IsUserExternalLocation < 0 )
    {
      v4 = 679;
      goto LABEL_5;
    }
    v17 = v87;
  }
  if ( *((_BYTE *)v17 + 80) )
  {
    *((_BYTE *)this + 369) = 1;
    *((_BYTE *)this + 392) = 0;
    if ( *((_BYTE *)this + 368) )
    {
      IsUserExternalLocation = OSIntegration::GetIsInboxFullTrustFromPackage(
                                 (OSIntegration::Package *)((char *)this + 216),
                                 (OSIntegration::Package *)((char *)this + 380),
                                 (bool *)v17);
      if ( IsUserExternalLocation < 0 )
      {
        v4 = 695;
        goto LABEL_5;
      }
    }
  }
  else
  {
    *((_BYTE *)this + 369) = 0;
    *((_BYTE *)this + 380) = 0;
  }
  PackageRepository::AutoStatementDoneTable::AutoStatementDoneTable(
    (PackageRepository::AutoStatementDoneTable *)&v89,
    v68);
  v19 = (*(__int64 (__fastcall **)(struct PackageRepository::ITable *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v68 + 168LL))(
          v68,
          *((_QWORD *)this + 98),
          *((_QWORD *)this + 8),
          &v88);
  IsUserExternalLocation = v19;
  if ( v19 < 0 )
  {
    *(_OWORD *)v65 = 0;
    LODWORD(v66) = 0;
    OSIntegration::Tools::FormatMessageInternal(v19, (Common::StringBuffer *)v65, v20);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v58);
    v23 = v65[1];
    if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v22,
        (unsigned int)OSIMPackageRepositoryError,
        *((_QWORD *)this + 28),
        v65[1],
        IsUserExternalLocation);
    details::appxLog<unsigned short const *,long,unsigned short *>(
      (unsigned int)IsUserExternalLocation,
      v21,
      OSIMPackageRepositoryError,
      *((_QWORD *)this + 28));
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v23);
    if ( v23 )
      operator delete(v23, v24);
    goto LABEL_83;
  }
  v25 = v88;
  *((_DWORD *)this + 198) = *(_DWORD *)(v88 + 68);
  *(_QWORD *)((char *)this + 796) = *(_QWORD *)(v25 + 40);
  packageFamilyNameLength = 65;
  v26 = (WCHAR *)operator new[](0x82u);
  v81 = v26;
  v27 = PackageFamilyNameFromFullName(*((PCWSTR *)this + 28), &packageFamilyNameLength, v26);
  IsUserExternalLocation = v27;
  if ( v27 > 0 )
    IsUserExternalLocation = (unsigned __int16)v27 | 0x80070000;
  if ( IsUserExternalLocation < 0 )
  {
    *(_OWORD *)v65 = 0;
    LODWORD(v66) = 0;
    OSIntegration::Tools::FormatMessageInternal(IsUserExternalLocation, (Common::StringBuffer *)v65, v28);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v58);
    v31 = v65[1];
    if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v30,
        (unsigned int)OSIMInvalidPackageMonikerString,
        *((_QWORD *)this + 28),
        v65[1],
        IsUserExternalLocation);
    details::appxLog<unsigned short const *,long,unsigned short *>(
      (unsigned int)IsUserExternalLocation,
      v29,
      OSIMInvalidPackageMonikerString,
      *((_QWORD *)this + 28));
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v31);
    if ( v31 )
      operator delete(v31, v32);
    v33 = v26;
    goto LABEL_92;
  }
  Common::StringBuffer::InitializeFromString((OSIntegration::Package *)((char *)this + 240), v26);
  v81 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v34 = Common::Deployment::VolumeManager::FindByKey(*(_DWORD *)(v88 + 72), (struct Common::Deployment::Volume *)&v71);
  IsUserExternalLocation = v34;
  if ( v34 < 0 )
  {
    *(_OWORD *)v65 = 0;
    LODWORD(v66) = 0;
    OSIntegration::Tools::FormatMessageInternal(v34, (Common::StringBuffer *)v65, v35);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v58);
    v38 = v65[1];
    if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 1) != 0 )
      McTemplateU0zzd_EventWriteTransfer(
        v37,
        (unsigned int)OSIMPackageRepositoryError,
        *((_QWORD *)this + 28),
        v65[1],
        IsUserExternalLocation);
    details::appxLog<unsigned short const *,long,unsigned short *>(
      (unsigned int)IsUserExternalLocation,
      v36,
      OSIMPackageRepositoryError,
      *((_QWORD *)this + 28));
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)IsUserExternalLocation,
      (int)v38);
    if ( v38 )
      operator delete(v38, v39);
    goto LABEL_98;
  }
  v40 = OSIntegration::Package::SetAppDataVolume(this, (const struct Common::Deployment::Volume *)&v71);
  IsUserExternalLocation = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)v40,
      (int)v58);
LABEL_98:
    Common::Deployment::Volume::~Volume((Common::Deployment::Volume *)&v71);
LABEL_99:
    v33 = 0;
LABEL_92:
    operator delete(v33, (const struct std::nothrow_t *)2);
LABEL_83:
    PackageRepository::AutoStatementDoneTable::~AutoStatementDoneTable((PackageRepository::AutoStatementDoneTable *)&v89);
    goto LABEL_6;
  }
  v67 = 0;
  *(_OWORD *)v65 = 0;
  LODWORD(v66) = 0;
  v41 = Common::SidHelper::ConvertSidToString(*((PSID *)this + 98), (struct Common::StringBuffer *)v65);
  IsUserExternalLocation = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)v41,
      (int)v58);
    if ( v65[1] )
      operator delete(v65[1], v43);
LABEL_105:
    v44 = 0;
LABEL_106:
    operator delete(v44, (const struct std::nothrow_t *)2);
    Common::Deployment::Volume::~Volume((Common::Deployment::Volume *)&v71);
    goto LABEL_99;
  }
  v45 = v65[1];
  StateRootFolderPathForVolume = StatePaths::GetStateRootFolderPathForVolume(
                                   v42,
                                   *((_QWORD *)this + 10),
                                   v65[1],
                                   *((const unsigned __int16 **)this + 31),
                                   v58,
                                   (unsigned int)&v67,
                                   v61,
                                   v62);
  IsUserExternalLocation = StateRootFolderPathForVolume;
  if ( StateRootFolderPathForVolume < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)StateRootFolderPathForVolume,
      (int)v59);
    if ( v45 )
      operator delete(v45, v47);
    v44 = v67;
    goto LABEL_106;
  }
  Common::StringBuffer::InitializeFromString((OSIntegration::Package *)((char *)this + 288), v67);
  v67 = 0;
  v69 = 0;
  v48 = (const unsigned __int16 *)(*((_DWORD *)v87 + 22) >> 5);
  LOBYTE(v48) = (*((_DWORD *)v87 + 22) & 0x20) != 0;
  MetadataDirectory = Common::Deployment::GetMetadataDirectory(
                        *((Common::Deployment **)v87 + 57),
                        *((const unsigned __int16 **)v87 + 8),
                        v48,
                        (bool)&v69,
                        v59);
  IsUserExternalLocation = MetadataDirectory;
  if ( MetadataDirectory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)MetadataDirectory,
      v60);
    operator delete(v69, (const struct std::nothrow_t *)2);
    if ( v45 )
      operator delete(v45, v50);
    goto LABEL_105;
  }
  v51 = v69;
  v52 = Common::StringBuffer::SetValueFromString((OSIntegration::Package *)((char *)this + 344), v69);
  v53 = v52;
  if ( v52 >= 0 )
  {
    *((_BYTE *)this + 407) = Common::PathHelpers::IsNetworkPath(*((const unsigned __int16 **)this + 12));
    *((_DWORD *)this + 94) = *((_DWORD *)v87 + 49);
    operator delete(v51, (const struct std::nothrow_t *)2);
    if ( v45 )
      operator delete(v45, v56);
    operator delete(0, (const struct std::nothrow_t *)2);
    Common::Deployment::Volume::~Volume((Common::Deployment::Volume *)&v71);
    operator delete(0, (const struct std::nothrow_t *)2);
    PackageRepository::AutoStatementDoneTable::~AutoStatementDoneTable((PackageRepository::AutoStatementDoneTable *)&v89);
    Common::AutoPtrDeallocate<PackageRepository::VisibilityRow>(v88);
    Common::AutoPtrDeallocate<PackageRepository::PackageRow>(v87);
    if ( v63[1] )
      operator delete(v63[1], v57);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
      (const char *)(unsigned int)v52,
      v60);
    operator delete(v51, (const struct std::nothrow_t *)2);
    if ( v45 )
      operator delete(v45, v54);
    operator delete(0, (const struct std::nothrow_t *)2);
    Common::Deployment::Volume::~Volume((Common::Deployment::Volume *)&v71);
    operator delete(0, (const struct std::nothrow_t *)2);
    PackageRepository::AutoStatementDoneTable::~AutoStatementDoneTable((PackageRepository::AutoStatementDoneTable *)&v89);
    Common::AutoPtrDeallocate<PackageRepository::VisibilityRow>(v88);
    Common::AutoPtrDeallocate<PackageRepository::PackageRow>(v87);
    if ( v63[1] )
      operator delete(v63[1], v55);
    return v53;
  }
}

```

## disassembly

```asm
0x18001cb00  push    rbp
0x18001cb02  push    rbx
0x18001cb03  push    rsi
0x18001cb04  push    rdi
0x18001cb05  push    r12
0x18001cb07  push    r13
0x18001cb09  push    r14
0x18001cb0b  push    r15
0x18001cb0d  lea     rbp, [rsp-28h]
0x18001cb12  sub     rsp, 128h
0x18001cb19  mov     rdi, rcx
0x18001cb1c  xorps   xmm0, xmm0
0x18001cb1f  movups  xmmword ptr [rsp+160h+var_120], xmm0
0x18001cb24  xor     r15d, r15d
0x18001cb27  mov     [rsp+160h+var_110], r15d
0x18001cb2c  lea     rax, [rsp+160h+var_120]
0x18001cb31  mov     [rbp+60h+var_50], rax
0x18001cb35  lea     r13, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001cb3c  mov     [rbp+60h+var_58], r13
0x18001cb40  lea     rax, [rsp+160h+var_120]
0x18001cb45  mov     [rbp+60h+var_48], rax
0x18001cb49  mov     rcx, [rcx+30h]
0x18001cb4d  mov     rax, [rbp+68h]
0x18001cb51  test    rcx, rcx
0x18001cb54  jnz     short loc_18001CB71
0x18001cb56  mov     r9d, 8007054Fh; char *
0x18001cb5c  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001cb63  mov     edx, 24Dh; void *
0x18001cb68  mov     rcx, rax; this
0x18001cb6b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001cb71  mov     [rbp+60h+var_D8], r15
0x18001cb75  mov     [rbp+60h+arg_8], r15
0x18001cb79  mov     [rsp+160h+var_E8], r15
0x18001cb7e  mov     [rbp+60h+arg_10], r15
0x18001cb85  mov     rax, [rcx]
0x18001cb88  lea     rdx, [rbp+60h+var_D8]
0x18001cb8c  mov     rax, [rax+28h]
0x18001cb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb95  mov     ebx, eax
0x18001cb97  test    eax, eax
0x18001cb99  jns     short loc_18001CBE1
0x18001cb9b  mov     edx, 258h; void *
0x18001cba0  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001cba7  mov     r9d, ebx; char *
0x18001cbaa  mov     rcx, [rbp+68h]; this
0x18001cbae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbb3  nop
0x18001cbb4  mov     rcx, [rbp+60h+arg_10]
0x18001cbbb  call    ??$AutoPtrDeallocate@VVisibilityRow@PackageRepository@@@Common@@YAXPEAVVisibilityRow@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::VisibilityRow>(PackageRepository::VisibilityRow *)
0x18001cbc0  nop
0x18001cbc1  mov     rcx, [rbp+60h+arg_8]
0x18001cbc5  call    ??$AutoPtrDeallocate@VPackageRow@PackageRepository@@@Common@@YAXPEAVPackageRow@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::PackageRow>(PackageRepository::PackageRow *)
0x18001cbca  nop
0x18001cbcb  mov     rcx, [rsp+160h+var_120+8]; void *
0x18001cbd0  test    rcx, rcx
0x18001cbd3  jz      short loc_18001CBDA
0x18001cbd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cbda  mov     eax, ebx
0x18001cbdc  jmp     loc_18001D72D
0x18001cbe1  mov     rcx, [rdi+30h]
0x18001cbe5  mov     rax, [rcx]
0x18001cbe8  lea     rdx, [rsp+160h+var_E8]
0x18001cbed  mov     rax, [rax+30h]
0x18001cbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbf6  mov     ebx, eax
0x18001cbf8  test    eax, eax
0x18001cbfa  jns     short loc_18001CC03
0x18001cbfc  mov     edx, 25Bh
0x18001cc01  jmp     short loc_18001CBA0
0x18001cc03  mov     rcx, [rbp+60h+var_D8]
0x18001cc07  mov     rax, [rcx]
0x18001cc0a  lea     r9, [rbp+60h+arg_8]
0x18001cc0e  mov     r8, [rdi+310h]
0x18001cc15  mov     rdx, [rdi+40h]
0x18001cc19  mov     rax, [rax+80h]
0x18001cc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc25  mov     ebx, eax
0x18001cc27  test    eax, eax
0x18001cc29  jns     short loc_18001CC35
0x18001cc2b  mov     edx, 25Eh
0x18001cc30  jmp     loc_18001CBA0
0x18001cc35  lea     rbx, [rdi+88h]
0x18001cc3c  mov     rdx, [rbp+60h+arg_8]
0x18001cc40  mov     rdx, [rdx+1D8h]; unsigned __int16 *
0x18001cc47  mov     rcx, rbx; this
0x18001cc4a  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001cc4f  mov     esi, eax
0x18001cc51  test    eax, eax
0x18001cc53  jns     short loc_18001CC9B
0x18001cc55  mov     edx, 260h; void *
0x18001cc5a  mov     rcx, [rbp+68h]; this
0x18001cc5e  mov     r9d, esi; char *
0x18001cc61  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001cc68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc6d  nop
0x18001cc6e  mov     rcx, [rbp+60h+arg_10]
0x18001cc75  call    ??$AutoPtrDeallocate@VVisibilityRow@PackageRepository@@@Common@@YAXPEAVVisibilityRow@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::VisibilityRow>(PackageRepository::VisibilityRow *)
0x18001cc7a  nop
0x18001cc7b  mov     rcx, [rbp+60h+arg_8]
0x18001cc7f  call    ??$AutoPtrDeallocate@VPackageRow@PackageRepository@@@Common@@YAXPEAVPackageRow@PackageRepository@@@Z; Common::AutoPtrDeallocate<PackageRepository::PackageRow>(PackageRepository::PackageRow *)
0x18001cc84  nop
0x18001cc85  mov     rcx, [rsp+160h+var_120+8]; void *
0x18001cc8a  test    rcx, rcx
0x18001cc8d  jz      short loc_18001CC94
0x18001cc8f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cc94  mov     eax, esi
0x18001cc96  jmp     loc_18001D72D
0x18001cc9b  mov     eax, [rbx]
0x18001cc9d  mov     r12d, 5Ch ; '\'
0x18001cca3  test    eax, eax
0x18001cca5  jz      short loc_18001CCE4
0x18001cca7  lea     ecx, [rax-1]
0x18001ccaa  mov     rax, [rdi+90h]
0x18001ccb1  cmp     [rax+rcx*2], r12w
0x18001ccb6  jz      short loc_18001CCE4
0x18001ccb8  mov     [rsp+160h+var_108+8], rbx
0x18001ccbd  mov     [rsp+160h+var_108], r13
0x18001ccc2  mov     [rsp+160h+var_F8], rbx
0x18001ccc7  mov     edx, r12d; unsigned __int16
0x18001ccca  lea     rcx, [rsp+160h+var_108]; this
0x18001cccf  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x18001ccd4  mov     esi, eax
0x18001ccd6  test    eax, eax
0x18001ccd8  jns     short loc_18001CCE4
0x18001ccda  mov     edx, 265h
0x18001ccdf  jmp     loc_18001CC5A
0x18001cce4  cmp     [rbx], r15d
0x18001cce7  setnbe  al
0x18001ccea  mov     [rdi+198h], al
0x18001ccf0  lea     rsi, [rdi+70h]
0x18001ccf4  mov     rdx, [rbp+60h+arg_8]
0x18001ccf8  mov     rdx, [rdx+1E8h]; unsigned __int16 *
0x18001ccff  mov     rcx, rsi; this
0x18001cd02  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001cd07  mov     ebx, eax
0x18001cd09  test    eax, eax
0x18001cd0b  jns     short loc_18001CD17
0x18001cd0d  mov     edx, 269h
0x18001cd12  jmp     loc_18001CBA0
0x18001cd17  lea     r14, [rdi+0A0h]
0x18001cd1e  mov     rdx, [rbp+60h+arg_8]
0x18001cd22  mov     rdx, [rdx+1E8h]; unsigned __int16 *
0x18001cd29  mov     rcx, r14; this
0x18001cd2c  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001cd31  mov     ebx, eax
0x18001cd33  test    eax, eax
0x18001cd35  jns     short loc_18001CD41
0x18001cd37  mov     edx, 26Ah
0x18001cd3c  jmp     loc_18001CBA0
0x18001cd41  mov     eax, [rsi]
0x18001cd43  test    eax, eax
0x18001cd45  jz      short loc_18001CD81
0x18001cd47  lea     ecx, [rax-1]
0x18001cd4a  mov     rax, [rdi+78h]
0x18001cd4e  cmp     [rax+rcx*2], r12w
0x18001cd53  jz      short loc_18001CD81
0x18001cd55  mov     [rsp+160h+var_108+8], rsi
0x18001cd5a  mov     [rsp+160h+var_108], r13
0x18001cd5f  mov     [rsp+160h+var_F8], rsi
0x18001cd64  mov     edx, r12d; unsigned __int16
0x18001cd67  lea     rcx, [rsp+160h+var_108]; this
0x18001cd6c  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x18001cd71  mov     ebx, eax
0x18001cd73  test    eax, eax
0x18001cd75  jns     short loc_18001CD81
0x18001cd77  mov     edx, 26Fh
0x18001cd7c  jmp     loc_18001CBA0
0x18001cd81  cmp     [r14], r15d
0x18001cd84  jz      short loc_18001CD8E
0x18001cd86  mov     rcx, r14; struct Common::StringBuffer *
0x18001cd89  call    ?StripTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::StripTrailingSlashIfNecessary(Common::StringBuffer *)
0x18001cd8e  mov     rbx, [rbp+60h+arg_8]
0x18001cd92  mov     r13d, 1
0x18001cd98  cmp     [rbx+270h], r15b
0x18001cd9f  jnz     short loc_18001CDD8
0x18001cda1  mov     rcx, rbx; this
0x18001cda4  call    ?LoadExternalLocationInfo@PackageRow@PackageRepository@@AEAAJXZ; PackageRepository::PackageRow::LoadExternalLocationInfo(void)
0x18001cda9  mov     esi, eax
0x18001cdab  test    eax, eax
0x18001cdad  jns     short loc_18001CDD1
0x18001cdaf  mov     rcx, [rbp+68h]; this
0x18001cdb3  mov     r9d, eax; char *
0x18001cdb6  lea     r8, aOnecoreAdminAp_155; "onecore\\admin\\appmodel\\PackageReposi"...
0x18001cdbd  mov     edx, 10Ch; void *
0x18001cdc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cdc7  mov     edx, 278h
0x18001cdcc  jmp     loc_18001CC5A
0x18001cdd1  mov     [rbx+270h], r13b
0x18001cdd8  mov     rdx, [rbx+248h]; unsigned __int16 *
0x18001cddf  mov     rcx, rdi; this
0x18001cde2  call    ?SetExternalLocation@Package@OSIntegration@@AEAAJPEBG@Z; OSIntegration::Package::SetExternalLocation(ushort const *)
0x18001cde7  mov     ebx, eax
0x18001cde9  test    eax, eax
0x18001cdeb  jns     short loc_18001CDF7
0x18001cded  mov     edx, 279h
0x18001cdf2  jmp     loc_18001CBA0
0x18001cdf7  lea     rdx, [rdi+0D0h]; bool *
0x18001cdfe  mov     rcx, [rbp+60h+arg_8]; this
0x18001ce02  call    ?GetIsUserExternalLocation@PackageRow@PackageRepository@@QEBAJPEA_N@Z; PackageRepository::PackageRow::GetIsUserExternalLocation(bool *)
0x18001ce07  mov     ebx, eax
0x18001ce09  test    eax, eax
0x18001ce0b  jns     short loc_18001CE17
0x18001ce0d  mov     edx, 27Ah
0x18001ce12  jmp     loc_18001CBA0
0x18001ce17  lea     rbx, [rdi+58h]
0x18001ce1b  mov     rdx, [rbp+60h+arg_8]
0x18001ce1f  mov     rdx, [rdx+1C8h]; unsigned __int16 *
0x18001ce26  mov     rcx, rbx; this
0x18001ce29  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001ce2e  mov     esi, eax
0x18001ce30  test    eax, eax
0x18001ce32  jns     short loc_18001CE3E
0x18001ce34  mov     edx, 27Ch
0x18001ce39  jmp     loc_18001CC5A
0x18001ce3e  mov     ecx, [rbx]
0x18001ce40  sub     ecx, r13d
0x18001ce43  mov     rax, [rdi+60h]
0x18001ce47  cmp     [rax+rcx*2], r12w
0x18001ce4c  jz      short loc_18001CE81
0x18001ce4e  mov     [rsp+160h+var_108+8], rbx
0x18001ce53  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001ce5a  mov     [rsp+160h+var_108], rax
0x18001ce5f  mov     [rsp+160h+var_F8], rbx
0x18001ce64  mov     edx, r12d; unsigned __int16
0x18001ce67  lea     rcx, [rsp+160h+var_108]; this
0x18001ce6c  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x18001ce71  mov     esi, eax
0x18001ce73  test    eax, eax
0x18001ce75  jns     short loc_18001CE81
0x18001ce77  mov     edx, 281h
0x18001ce7c  jmp     loc_18001CC5A
0x18001ce81  mov     rdx, rbx; struct Common::COMMON_STRING *
0x18001ce84  lea     rcx, [rbp+60h+var_58]; this
0x18001ce88  call    ?AppendString@StringBuilder@Common@@QEAAJPEBUCOMMON_STRING@2@@Z; Common::StringBuilder::AppendString(Common::COMMON_STRING const *)
0x18001ce8d  mov     ebx, eax
0x18001ce8f  test    eax, eax
0x18001ce91  jns     short loc_18001CE9D
0x18001ce93  mov     edx, 286h
0x18001ce98  jmp     loc_18001CBA0
0x18001ce9d  mov     r9d, 10h; unsigned int
0x18001cea3  mov     r8, cs:off_1801AD148; unsigned __int16 *
0x18001ceaa  mov     rdx, [rbp+60h+var_50]
0x18001ceae  mov     edx, [rdx]; unsigned int
0x18001ceb0  lea     rcx, [rbp+60h+var_58]; this
0x18001ceb4  call    ?InsertChars@StringBuilder@Common@@QEAAJKPEBGK@Z; Common::StringBuilder::InsertChars(ulong,ushort const *,ulong)
0x18001ceb9  mov     ebx, eax
0x18001cebb  test    eax, eax
0x18001cebd  jns     short loc_18001CEC9
0x18001cebf  mov     edx, 287h
0x18001cec4  jmp     loc_18001CBA0
0x18001cec9  lea     rcx, [rdi+108h]; this
0x18001ced0  mov     rdx, [rsp+160h+var_120+8]; unsigned __int16 *
0x18001ced5  call    ?InitializeFromString@StringBuffer@Common@@QEAAJPEAG@Z; Common::StringBuffer::InitializeFromString(ushort *)
0x18001ceda  mov     ebx, eax
0x18001cedc  test    eax, eax
0x18001cede  jns     short loc_18001CEEA
0x18001cee0  mov     edx, 28Ah
0x18001cee5  jmp     loc_18001CBA0
0x18001ceea  mov     [rsp+160h+var_120+8], r15
0x18001ceef  mov     dword ptr [rsp+160h+var_120], r15d
0x18001cef4  mov     [rsp+160h+var_110], r15d
0x18001cef9  mov     rdx, [rbp+60h+arg_8]
0x18001cefd  mov     eax, [rdx+58h]
0x18001cf00  mov     [rdi+180h], eax
0x18001cf06  mov     eax, [rdx+5Ch]
0x18001cf09  mov     [rdi+184h], eax
0x18001cf0f  mov     eax, [rdx+58h]
0x18001cf12  shr     eax, 7
0x18001cf15  and     al, r13b
0x18001cf18  mov     [rdi+19Ch], al
0x18001cf1e  mov     eax, [rdx+58h]
0x18001cf21  shr     eax, 0Bh
0x18001cf24  and     al, r13b
0x18001cf27  mov     [rdi+19Dh], al
0x18001cf2d  mov     eax, [rdx+58h]
0x18001cf30  shr     eax, 16h
0x18001cf33  and     al, r13b
0x18001cf36  mov     [rdi+19Eh], al
0x18001cf3c  lea     rcx, [rdi+1B8h]; this
0x18001cf43  mov     rdx, [rdx+120h]; unsigned __int16 *
0x18001cf4a  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001cf4f  mov     ebx, eax
0x18001cf51  test    eax, eax
0x18001cf53  jns     short loc_18001CF5F
0x18001cf55  mov     edx, 293h
0x18001cf5a  jmp     loc_18001CBA0
0x18001cf5f  mov     rdx, [rbp+60h+arg_8]
0x18001cf63  mov     rax, [rdx+38h]
0x18001cf67  mov     [rdi+1D0h], rax
0x18001cf6e  mov     eax, [rdx+30h]
0x18001cf71  mov     [rdi+1F0h], eax
0x18001cf77  lea     r14, [rdi+1F8h]
0x18001cf7e  mov     rdx, [rdx+20h]; unsigned __int16 *
0x18001cf82  mov     rcx, r14; this
0x18001cf85  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001cf8a  mov     ebx, eax
0x18001cf8c  test    eax, eax
0x18001cf8e  jns     short loc_18001CF9A
0x18001cf90  mov     edx, 298h
0x18001cf95  jmp     loc_18001CBA0
  ... truncated ...
```
