# Windows::Internal::StateRepository::PackageFactoryServer::FindByUserOrDefaultAccountAndPackageFamilyNameAndPackageType(Windows::Internal::StateRepository::IUser *,HSTRING__ *,Windows::Internal::StateRepository::PackageType,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Package *> * *)

- ea: `0x18000bb70`
- end: `0x18000c2ed`
- name: `?FindByUserOrDefaultAccountAndPackageFamilyNameAndPackageType@PackageFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUIUser@234@PEAUHSTRING__@@W4PackageType@234@PEAPEAU?$IVectorView@PEAVPackage@StateRepository@Internal@Windows@@@Collections@Foundation@4@@Z`
- size: `1917`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003e54`
- `0x180007a40`
- `0x18000b380`
- `0x18000b3a0`
- `0x18000bb70`
- `0x18000c73c`
- `0x18000cc30`
- `0x18000d0a4`
- `0x18000d170`
- `0x18000dc60`
- `0x180010d28`
- `0x1800131f8`
- `0x180014e54`
- `0x18001518c`
- `0x180016030`
- `0x180017098`
- `0x1800171c0`
- `0x180017a58`
- `0x180018574`
- `0x180018628`
- `0x18001a548`
- `0x18001a9e0`
- `0x1800a612c`
- `0x1800ad7dc`
- `0x18018f650`
- `0x18020b074`
- `0x1802385c0`
- `0x180259348`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc02`
- `StateRepository.Core!sqlite3_bind_int64` at `0x18000bf64`
- `StateRepository.Core!sqlite3_bind_int64` at `0x18000bf64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bcb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bcb0`

## string_xrefs

- `0x18000bd42`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18000bddf`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18000bdff`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000be15`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000bfad`: `onecore\base\appmodel\StateRepository\WinRT\common\inc\WinRT-DAL.hpp`
- `0x18000c1bc`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x18000bd1c`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000be30`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x18000bcf3`: `WITH PackageIdByUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE pu.User=?1 AND p._WorkID=0 AND pu._WorkID=0), PackageIdByDefaultAccountForPackageFamilyNotUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE ?5 AND pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?4) AND p.PackageFamily NOT IN (SELECT DISTINCT PackageFamily FROM Package AS p INNER JOIN `
- `0x18000bcfa`: `WITH PackageIdByUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), PackageIdByDefaultAccountForPackageFamilyNotUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE ?5 AND pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?4) AND p.PackageFamily NOT IN (SELECT DISTINCT Packag`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::StateRepository::PackageFactoryServer::FindByUserOrDefaultAccountAndPackageFamilyNameAndPackageType(
        StateRepository::WinRT::Caller *a1,
        struct Windows::Internal::StateRepository::IUser *a2,
        HSTRING a3,
        int a4,
        _QWORD *a5)
{
  WINBOOL ProcessId; // r14d
  int v9; // ebx
  unsigned __int64 v10; // rdx
  int v11; // eax
  int v12; // ebx
  int UserIdFromUser; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rax
  char *v16; // rdi
  int v17; // ebx
  __int64 v18; // rdx
  int v19; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // rcx
  int v34; // eax
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  bool v39; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v40; // [rsp+38h] [rbp-C8h] BYREF
  struct sqlite3_stmt *v41; // [rsp+40h] [rbp-C0h] BYREF
  struct sqlite3 **v42; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL v44; // [rsp+58h] [rbp-A8h] BYREF
  char v45; // [rsp+5Ch] [rbp-A4h]
  PCWSTR v46; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  struct sqlite3 *v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h]
  _BYTE v50[88]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v51[20]; // [rsp+F0h] [rbp-10h] BYREF
  int v52; // [rsp+104h] [rbp+4h]
  _QWORD v53[18]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v54[42]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v45 = 0;
  _InterlockedIncrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
  ProcessId = StateRepository::WinRT::Caller::GetProcessId(a1);
  v44 = ProcessId;
  wil::ActivityBase<StateRepository::Tracing::Service,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StateRepository::Tracing::Service,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v54);
  v54[0] = &StateRepository::Trace::WinRT::API::Method::`vftable';
  StateRepository::Trace::WinRT::API::Method::StartActivity(
    (StateRepository::Trace::WinRT::API::Method *)v54,
    "PackageStatics::FindByUserOrDefaultAccountAndPackageFamilyNameAndPackageType",
    ProcessId);
  v9 = dword_1804E01A8;
  if ( v9 != GetCurrentThreadId() )
  {
    v40 = *(_QWORD *)&qword_1804E01A0;
    if ( (*(_BYTE *)(&qword_1804E01A0 + 1) & 2) != 0 )
    {
      v12 = -2147023781;
    }
    else if ( (v40 & 0x100000000LL) != 0 )
    {
      v12 = -2140733424;
    }
    else
    {
      if ( !(_DWORD)v40 )
        goto LABEL_5;
      v12 = -2140733434;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x460,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)(unsigned int)v12,
      v35);
    goto LABEL_29;
  }
LABEL_5:
  if ( !a5 )
  {
    v12 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x462,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)0x80004003LL,
      v35);
    goto LABEL_24;
  }
  *a5 = 0;
  StateRepository::Database::Database((StateRepository::Database *)&v48);
  v11 = StateRepository::Repository::OpenDatabaseFromCache(1, v10, (__int64)&v48);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x469,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)(unsigned int)v11,
      v35);
    goto LABEL_28;
  }
  v42 = &v48;
  v43 = 0;
  v39 = 0;
  UserIdFromUser = StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdFromUser(a2, &v48, &v43, &v39);
  v12 = UserIdFromUser;
  if ( UserIdFromUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)(unsigned int)UserIdFromUser,
      v35);
    StateRepository::Repository::AddToCache((struct StateRepository::Database *)&v48);
LABEL_28:
    StateRepository::Database::~Database((StateRepository::Database *)&v48);
LABEL_29:
    StateRepository::Trace::WinRT::API::Method::~Method((StateRepository::Trace::WinRT::API::Method *)v54);
    _InterlockedDecrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
    return (unsigned int)v12;
  }
  if ( !v39 )
  {
    v34 = StateRepository::WinRT::DAL::Statement::CreateEmptyVectorView<Windows::Internal::StateRepository::Package>(a5);
    v12 = v34;
    if ( v34 >= 0 )
    {
      StateRepository::Trace::WinRT::API::Method::Stop(
        (StateRepository::Trace::WinRT::API::Method *)v54,
        "PackageStatics::FindByUserOrDefaultAccountAndPackageFamilyNameAndPackageType",
        ProcessId);
      StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v42);
      StateRepository::Database::~Database((StateRepository::Database *)&v48);
      v12 = 0;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)(unsigned int)v34,
      v35);
    goto LABEL_23;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v41 = 0;
  LODWORD(v40) = a4;
  v46 = StringRawBuffer;
  v47 = v43;
  v15 = lambda_f4ca7f8a52b3c014a8b9b635aa235862_::_lambda_f4ca7f8a52b3c014a8b9b635aa235862_(v51, &v47, &v46, &v40);
  StateRepository::StatementExecution::StatementBinderFunc::StatementBinderFunc__lambda_3ef7347d5705c7d0ad069836862e7b33___(
    v53,
    v15);
  v16 = "WITH PackageIdByUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Pack"
        "age=p._PackageID WHERE pu.User=?1 AND p._WorkID=0 AND pu._WorkID=0), PackageIdByDefaultAccountForPackageFamilyNo"
        "tUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Package=p._PackageI"
        "D WHERE ?5 AND pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?4) AND p.PackageFamily NOT IN (SELECT "
        "DISTINCT PackageFamily FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE pu.User=?"
        "1 AND p._WorkID=0 AND pu._WorkID=0)AND p._WorkID=0 AND pu._WorkID=0), PackageIdByAll(_PackageID) AS (SELECT _Pac"
        "kageID FROM PackageIdByUser UNION ALL SELECT _PackageID FROM PackageIdByDefaultAccountForPackageFamilyNotUser)SE"
        "LECT p._PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.PackageFu"
        "llName, p.IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Description, p.Log"
        "o, p.OSMinVersion, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.SignatureOrig"
        "in, p.PackageOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceUpdateBaseline,"
        " p._Dictionary FROM Package AS p INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily INNER JOI"
        "N PackageIdByAll AS cte_p ON cte_p._PackageID=p._PackageID WHERE pf.PackageFamilyName=?2 AND p.PackageType & ?3 "
        "!=0 AND p._WorkId=0;";
  v52 = 0;
  if ( v49
    && "WITH PackageIdByUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Packa"
       "ge=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), PackageI"
       "dByDefaultAccountForPackageFamilyNotUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUs"
       "er AS pu ON pu.Package=p._PackageID WHERE ?5 AND pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?4) AN"
       "D p.PackageFamily NOT IN (SELECT DISTINCT PackageFamily FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Pack"
       "age=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)) AND (p._"
       "WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), PackageIdByAll(_PackageID) AS (SELECT _PackageID "
       "FROM PackageIdByUser UNION ALL SELECT _PackageID FROM PackageIdByDefaultAccountForPackageFamilyNotUser)SELECT p._"
       "PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.PackageFullName, p"
       ".IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Description, p.Logo, p.OSMin"
       "Version, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.SignatureOrigin, p.Packa"
       "geOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceUpdateBaseline, p._Dictiona"
       "ry FROM Package AS p INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily INNER JOIN PackageIdBy"
       "All AS cte_p ON cte_p._PackageID=p._PackageID WHERE pf.PackageFamilyName=?2 AND p.PackageType & ?3 !=0 AND (p._Wo"
       "rkId=0 OR p._WorkId=?6);" )
  {
    v16 = "WITH PackageIdByUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Pa"
          "ckage=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), Pa"
          "ckageIdByDefaultAccountForPackageFamilyNotUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN "
          "PackageUser AS pu ON pu.Package=p._PackageID WHERE ?5 AND pu.User IN (SELECT _UserID FROM User AS u WHERE u.Us"
          "erSid=?4) AND p.PackageFamily NOT IN (SELECT DISTINCT PackageFamily FROM Package AS p INNER JOIN PackageUser A"
          "S pu ON pu.Package=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._Wo"
          "rkID=?6)) AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), PackageIdByAll(_PackageID) A"
          "S (SELECT _PackageID FROM PackageIdByUser UNION ALL SELECT _PackageID FROM PackageIdByDefaultAccountForPackage"
          "FamilyNotUser)SELECT p._PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Ve"
          "rsion, p.PackageFullName, p.IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, "
          "p.Description, p.Logo, p.OSMinVersion, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.Supported"
          "Users, p.SignatureOrigin, p.PackageOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, "
          "p.InPlaceUpdateBaseline, p._Dictionary FROM Package AS p INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID"
          "=p.PackageFamily INNER JOIN PackageIdByAll AS cte_p ON cte_p._PackageID=p._PackageID WHERE pf.PackageFamilyNam"
          "e=?2 AND p.PackageType & ?3 !=0 AND (p._WorkId=0 OR p._WorkId=?6);";
  }
  if ( !v48 )
  {
    v12 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      v35);
LABEL_21:
    v18 = 21;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
      (const char *)(unsigned int)v12,
      v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
      (const char *)(unsigned int)v12,
      v36);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
      (const char *)(unsigned int)v12,
      v37);
    (**(void (__fastcall ***)(_QWORD, _QWORD))v53[0])(v53[0], 0);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)(unsigned int)v12,
      v38);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v41);
LABEL_23:
    StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v42);
    StateRepository::Database::~Database((StateRepository::Database *)&v48);
LABEL_24:
    StateRepository::Trace::WinRT::API::Method::~Method((StateRepository::Trace::WinRT::API::Method *)v54);
    StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)&v44);
    return (unsigned int)v12;
  }
  if ( !v41 )
    goto LABEL_12;
  v30 = StateRepository::Statement::dal_finalize(v41);
  v17 = v30;
  if ( v30 >= 0 )
  {
    v41 = 0;
LABEL_12:
    v17 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
    (const char *)(unsigned int)v30,
    v35);
LABEL_13:
  if ( v17 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x679,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v17);
  if ( !StateRepository::StatementCache::Get(
          (StateRepository::StatementCache *)v50,
          v16,
          (struct StateRepository::Statement *)&v41) )
  {
    v31 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v41);
    if ( v31 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
        (const char *)(unsigned int)v31);
    v12 = StateRepository::Database::dal_prepare_v2(v48, v16, v32, &v41);
    if ( v12 < 0 )
      goto LABEL_21;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, struct sqlite3_stmt **))(*(_QWORD *)v53[0] + 8LL))(v53[0], &v41);
  if ( v12 < 0 )
  {
    v18 = 23;
    goto LABEL_22;
  }
  if ( "WITH PackageIdByUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Packa"
       "ge=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), PackageI"
       "dByDefaultAccountForPackageFamilyNotUser(_PackageID) AS (SELECT _PackageID FROM Package AS p INNER JOIN PackageUs"
       "er AS pu ON pu.Package=p._PackageID WHERE ?5 AND pu.User IN (SELECT _UserID FROM User AS u WHERE u.UserSid=?4) AN"
       "D p.PackageFamily NOT IN (SELECT DISTINCT PackageFamily FROM Package AS p INNER JOIN PackageUser AS pu ON pu.Pack"
       "age=p._PackageID WHERE pu.User=?1 AND (p._WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)) AND (p._"
       "WorkID=0 OR p._WorkID=?6) AND (pu._WorkID=0 OR pu._WorkID=?6)), PackageIdByAll(_PackageID) AS (SELECT _PackageID "
       "FROM PackageIdByUser UNION ALL SELECT _PackageID FROM PackageIdByDefaultAccountForPackageFamilyNotUser)SELECT p._"
       "PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.PackageFullName, p"
       ".IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Description, p.Logo, p.OSMin"
       "Version, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.SignatureOrigin, p.Packa"
       "geOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceUpdateBaseline, p._Dictiona"
       "ry FROM Package AS p INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily INNER JOIN PackageIdBy"
       "All AS cte_p ON cte_p._PackageID=p._PackageID WHERE pf.PackageFamilyName=?2 AND p.PackageType & ?3 !=0 AND (p._Wo"
       "rkId=0 OR p._WorkId=?6);"
    && v49 )
  {
    if ( v41 )
    {
      v21 = sqlite3_bind_int64(v41, 6, v49);
      v12 = v21;
      if ( v21 > 0 )
        v12 = (unsigned __int16)v21 | 0x87AF0000;
    }
    else
    {
      v12 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        v35);
    }
    if ( v12 < 0 )
    {
      v18 = 27;
      goto LABEL_22;
    }
  }
  (**(void (__fastcall ***)(_QWORD, _QWORD))v53[0])(v53[0], 0);
  v40 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v23 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Package,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0>>(
          v22,
          &v40);
  v12 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\WinRT\\common\\inc\\WinRT-DAL.hpp",
      (const char *)(unsigned int)v23,
      v35);
    v33 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
  }
  else
  {
    v24 = StateRepository::WinRT::DAL::Statement::AppendResultsToAgileVector<StateRepository::Entity::Package,Windows::Internal::StateRepository::IPackage,Windows::Internal::StateRepository::PackageServer,Windows::Internal::StateRepository::Package>(
            (__int64)&v48,
            &v41,
            v40);
    v12 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\WinRT\\common\\inc\\WinRT-DAL.hpp",
        (const char *)(unsigned int)v24,
        v35);
      v28 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    else
    {
      v25 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v40 + 64LL))(v40, a5);
      v12 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\WinRT\\common\\inc\\WinRT-DAL.hpp",
          (const char *)(unsigned int)v25,
          v35);
        v29 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
      }
      else
      {
        v26 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v12 = 0;
      }
    }
  }
  v27 = StateRepository::Repository::AddToCache((struct StateRepository::Database *)&v48);
  if ( v27 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7F,
      (int)"onecore\\base\\appmodel\\StateRepository\\WinRT\\common\\inc\\WinRT-DAL.hpp",
      (const char *)(unsigned int)v27);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x481,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.packa"
                    "gefactory-custom.cpp",
      (const char *)(unsigned int)v12,
      v35);
    v19 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v41);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v19);
    StateRepository::Repository::AddToCache((struct StateRepository::Database *)&v48);
    goto LABEL_28;
  }
  StateRepository::Trace::WinRT::API::Method::Stop(
    (StateRepository::Trace::WinRT::API::Method *)v54,
    "PackageStatics::FindByUserOrDefaultAccountAndPackageFamilyNameAndPackageType",
    ProcessId);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v41);
  StateRepository::Repository::AddToCache((struct StateRepository::Database *)&v48);
  StateRepository::Database::~Database((StateRepository::Database *)&v48);
  StateRepository::Trace::WinRT::API::Method::~Method((StateRepository::Trace::WinRT::API::Method *)v54);
  _InterlockedDecrement(&StateRepository::WinRT::Client::RequestInProgress::s_count);
  return 0;
}

```

## disassembly

```asm
0x18000bb70  mov     [rsp-8+arg_0], rbx
0x18000bb75  push    rbp
0x18000bb76  push    rsi
0x18000bb77  push    rdi
0x18000bb78  push    r12
0x18000bb7a  push    r13
0x18000bb7c  push    r14
0x18000bb7e  push    r15
0x18000bb80  lea     rbp, [rsp-200h]
0x18000bb88  sub     rsp, 300h
0x18000bb8f  mov     rax, cs:__security_cookie
0x18000bb96  xor     rax, rsp
0x18000bb99  mov     [rbp+230h+var_40], rax
0x18000bba0  mov     r15d, r9d
0x18000bba3  mov     r12, r8
0x18000bba6  mov     rdi, rdx
0x18000bba9  mov     rsi, [rbp+230h+arg_20]
0x18000bbb0  xor     r13d, r13d
0x18000bbb3  mov     [rsp+330h+var_2D4], r13b
0x18000bbb8  lock inc cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18000bbbf  call    ?GetProcessId@Caller@WinRT@StateRepository@@YAIXZ; StateRepository::WinRT::Caller::GetProcessId(void)
0x18000bbc4  mov     r14d, eax
0x18000bbc7  mov     [rsp+330h+var_2D8], eax
0x18000bbcb  lea     rcx, [rbp+230h+var_190]
0x18000bbd2  call    ??0?$ActivityBase@VService@Tracing@StateRepository@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StateRepository::Tracing::Service,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StateRepository::Tracing::Service,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000bbd7  lea     rax, ??_7Method@API@WinRT@Trace@StateRepository@@6B@; const StateRepository::Trace::WinRT::API::Method::`vftable'
0x18000bbde  mov     [rbp+230h+var_190], rax
0x18000bbe5  mov     r8d, r14d; unsigned int
0x18000bbe8  lea     rdx, aPackagestatics_37; "PackageStatics::FindByUserOrDefaultAcco"...
0x18000bbef  lea     rcx, [rbp+230h+var_190]; this
0x18000bbf6  call    ?StartActivity@Method@API@WinRT@Trace@StateRepository@@QEAAXPEBDI@Z; StateRepository::Trace::WinRT::API::Method::StartActivity(char const *,uint)
0x18000bbfb  nop
0x18000bbfc  mov     ebx, cs:dword_1804E01A8
0x18000bc02  call    cs:__imp_GetCurrentThreadId
0x18000bc08  cmp     ebx, eax
0x18000bc0a  jz      short loc_18000BC3C
0x18000bc0c  mov     rax, cs:qword_1804E01A0
0x18000bc13  mov     [rsp+330h+var_2F8], rax
0x18000bc18  mov     eax, dword ptr [rsp+330h+var_2F8+4]
0x18000bc1c  test    al, 2
0x18000bc1e  jnz     loc_18000C14B
0x18000bc24  mov     eax, dword ptr [rsp+330h+var_2F8+4]
0x18000bc28  test    al, 1
0x18000bc2a  jnz     loc_18000C1EE
0x18000bc30  mov     eax, dword ptr [rsp+330h+var_2F8]
0x18000bc34  test    eax, eax
0x18000bc36  jnz     loc_18000BF38
0x18000bc3c  test    rsi, rsi
0x18000bc3f  jz      loc_18000C24D
0x18000bc45  mov     [rsi], r13
0x18000bc48  lea     rcx, [rsp+330h+var_2C0]; this
0x18000bc4d  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18000bc52  lea     r8, [rsp+330h+var_2C0]
0x18000bc57  mov     ecx, 1
0x18000bc5c  call    ?OpenDatabaseFromCache@Repository@StateRepository@@SAJW4Partition@2@W4OpenFlags@12@AEAVDatabase@2@@Z; StateRepository::Repository::OpenDatabaseFromCache(StateRepository::Partition,StateRepository::Repository::OpenFlags,StateRepository::Database &)
0x18000bc61  mov     ebx, eax
0x18000bc63  test    eax, eax
0x18000bc65  js      loc_18000C184
0x18000bc6b  lea     rax, [rsp+330h+var_2C0]
0x18000bc70  mov     [rsp+330h+var_2E8], rax
0x18000bc75  mov     [rsp+330h+var_2E0], r13
0x18000bc7a  mov     [rsp+330h+var_300], r13b
0x18000bc7f  lea     r9, [rsp+330h+var_300]; bool *
0x18000bc84  lea     r8, [rsp+330h+var_2E0]; __int64 *
0x18000bc89  lea     rdx, [rsp+330h+var_2C0]; struct StateRepository::Database *
0x18000bc8e  mov     rcx, rdi; struct Windows::Internal::StateRepository::IUser *
0x18000bc91  call    ?TryGet_UserIdFromUser@User@DataAccessLayer@WinRT@StateRepository@@SAJPEAUIUser@4Internal@Windows@@AEAVDatabase@4@PEA_JPEA_N@Z; StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdFromUser(Windows::Internal::StateRepository::IUser *,StateRepository::Database &,__int64 *,bool *)
0x18000bc96  mov     ebx, eax
0x18000bc98  test    eax, eax
0x18000bc9a  js      loc_18000C11F
0x18000bca0  cmp     [rsp+330h+var_300], r13b
0x18000bca5  jz      loc_18000C272
0x18000bcab  xor     edx, edx; length
0x18000bcad  mov     rcx, r12; string
0x18000bcb0  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bcb6  mov     [rsp+330h+var_2F0], r13
0x18000bcbb  mov     dword ptr [rsp+330h+var_2F8], r15d
0x18000bcc0  mov     [rsp+330h+var_2D0], rax
0x18000bcc5  mov     rax, [rsp+330h+var_2E0]
0x18000bcca  mov     [rsp+330h+var_2C8], rax
0x18000bccf  lea     r9, [rsp+330h+var_2F8]
0x18000bcd4  lea     r8, [rsp+330h+var_2D0]
0x18000bcd9  lea     rdx, [rsp+330h+var_2C8]
0x18000bcde  lea     rcx, [rbp+230h+var_240]
0x18000bce2  call    _lambda_f4ca7f8a52b3c014a8b9b635aa235862____lambda_f4ca7f8a52b3c014a8b9b635aa235862_
0x18000bce7  mov     rdx, rax
0x18000bcea  lea     rcx, [rbp+230h+var_220]
0x18000bcee  call    StateRepository__StatementExecution__StatementBinderFunc__StatementBinderFunc__lambda_3ef7347d5705c7d0ad069836862e7b33___
0x18000bcf3  lea     rdi, aWithPackageidb_20; "WITH PackageIdByUser(_PackageID) AS (SE"...
0x18000bcfa  lea     r12, aWithPackageidb_4; "WITH PackageIdByUser(_PackageID) AS (SE"...
0x18000bd01  xor     eax, eax
0x18000bd03  mov     [rbp+230h+var_22C], eax
0x18000bd06  cmp     [rsp+330h+var_2B8], r13
0x18000bd0b  jnz     loc_18000C2D2
0x18000bd11  cmp     [rsp+330h+var_2C0], r13
0x18000bd16  jz      loc_18000BDD0
0x18000bd1c  lea     r15, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18000bd23  mov     rcx, [rsp+330h+var_2F0]; struct sqlite3_stmt *
0x18000bd28  test    rcx, rcx
0x18000bd2b  jnz     loc_18000C106
0x18000bd31  mov     ebx, r13d
0x18000bd34  mov     rcx, [rbp+238h]; this
0x18000bd3b  test    ebx, ebx
0x18000bd3d  jns     short loc_18000BD53
0x18000bd3f  mov     r9d, ebx; char *
0x18000bd42  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x18000bd49  mov     edx, 679h; void *
0x18000bd4e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bd53  lea     r8, [rsp+330h+var_2F0]; struct StateRepository::Statement *
0x18000bd58  mov     rdx, rdi; char *
0x18000bd5b  lea     rcx, [rbp+230h+var_298]; this
0x18000bd5f  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x18000bd64  test    rax, rax
0x18000bd67  jz      loc_18000C1A4
0x18000bd6d  mov     rcx, [rbp+230h+var_220]
0x18000bd71  mov     rax, [rcx]
0x18000bd74  lea     rdx, [rsp+330h+var_2F0]
0x18000bd79  mov     rax, [rax+8]
0x18000bd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd82  mov     ebx, eax
0x18000bd84  test    eax, eax
0x18000bd86  js      loc_18000BF5A
0x18000bd8c  test    r12, r12
0x18000bd8f  jz      loc_18000BF81
0x18000bd95  mov     r8, [rsp+330h+var_2B8]
0x18000bd9a  test    r8, r8
0x18000bd9d  jz      loc_18000BF81
0x18000bda3  mov     rcx, [rbp+238h]; this
0x18000bdaa  mov     edx, 6
0x18000bdaf  mov     eax, edx
0x18000bdb1  shr     eax, 1Fh
0x18000bdb4  test    al, al
0x18000bdb6  jz      loc_18000C155
0x18000bdbc  mov     r9d, 80070057h; char *
0x18000bdc2  mov     r8, r15; unsigned int
0x18000bdc5  mov     edx, 0C7h; void *
0x18000bdca  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000bdd0  mov     rcx, [rbp+238h]; this
0x18000bdd7  mov     ebx, 8007139Fh
0x18000bddc  mov     r9d, ebx; char *
0x18000bddf  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x18000bde6  mov     edx, 66Eh; void *
0x18000bdeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdf0  mov     edx, 15h; void *
0x18000bdf5  mov     rcx, [rbp+238h]; this
0x18000bdfc  mov     r9d, ebx; char *
0x18000bdff  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x18000be06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be0b  mov     rcx, [rbp+238h]; this
0x18000be12  mov     r9d, ebx; char *
0x18000be15  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x18000be1c  mov     edx, 0E8h; void *
0x18000be21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be26  mov     rcx, [rbp+238h]; this
0x18000be2d  mov     r9d, ebx; char *
0x18000be30  lea     r8, aOnecoreBaseApp_71; "onecore\\base\\appmodel\\staterepositor"...
0x18000be37  mov     edx, 9B5h; void *
0x18000be3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be41  mov     rcx, [rbp+230h+var_220]
0x18000be45  mov     rax, [rcx]
0x18000be48  xor     edx, edx
0x18000be4a  mov     rax, [rax]
0x18000be4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be52  mov     rcx, [rbp+238h]; this
0x18000be59  mov     r9d, ebx; char *
0x18000be5c  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appmodel\\staterepositor"...
0x18000be63  mov     edx, 47Bh; void *
0x18000be68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be6d  lea     rcx, [rsp+330h+var_2F0]; this
0x18000be72  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000be77  lea     rcx, [rsp+330h+var_2E8]; this
0x18000be7c  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x18000be81  lea     rcx, [rsp+330h+var_2C0]; this
0x18000be86  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18000be8b  lea     rcx, [rbp+230h+var_190]; this
0x18000be92  call    ??1Method@API@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::API::Method::~Method(void)
0x18000be97  lea     rcx, [rsp+330h+var_2D8]; this
0x18000be9c  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x18000bea1  jmp     short loc_18000BF0C
0x18000bea3  mov     rcx, [rbp+238h]; this
0x18000beaa  mov     r9d, ebx; char *
0x18000bead  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appmodel\\staterepositor"...
0x18000beb4  mov     edx, 481h; void *
0x18000beb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bebe  lea     rcx, [rsp+330h+var_2F0]; this
0x18000bec3  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18000bec8  mov     rcx, [rbp+238h]; this
0x18000becf  test    eax, eax
0x18000bed1  jns     short loc_18000BEE4
0x18000bed3  mov     r9d, eax; char *
0x18000bed6  mov     r8, r15; unsigned int
0x18000bed9  mov     edx, 16h; void *
0x18000bede  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bee3  nop
0x18000bee4  lea     rcx, [rsp+330h+var_2C0]; struct StateRepository::Database *
0x18000bee9  call    ?AddToCache@Repository@StateRepository@@SAJAEAVDatabase@2@@Z; StateRepository::Repository::AddToCache(StateRepository::Database &)
0x18000beee  nop
0x18000beef  lea     rcx, [rsp+330h+var_2C0]; this
0x18000bef4  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18000bef9  lea     rcx, [rbp+230h+var_190]; this
0x18000bf00  call    ??1Method@API@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::API::Method::~Method(void)
0x18000bf05  lock dec cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18000bf0c  mov     eax, ebx
0x18000bf0e  mov     rcx, [rbp+230h+var_40]
0x18000bf15  xor     rcx, rsp; StackCookie
0x18000bf18  call    __security_check_cookie
0x18000bf1d  mov     rbx, [rsp+330h+arg_0]
0x18000bf25  add     rsp, 300h
0x18000bf2c  pop     r15
0x18000bf2e  pop     r14
0x18000bf30  pop     r13
0x18000bf32  pop     r12
0x18000bf34  pop     rdi
0x18000bf35  pop     rsi
0x18000bf36  pop     rbp
0x18000bf37  retn
0x18000bf38  mov     ebx, 80670006h
0x18000bf3d  mov     rcx, [rbp+238h]; this
0x18000bf44  mov     r9d, ebx; char *
0x18000bf47  lea     r8, aOnecoreBaseApp_106; "onecore\\base\\appmodel\\staterepositor"...
0x18000bf4e  mov     edx, 460h; void *
0x18000bf53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf58  jmp     short loc_18000BEF9
0x18000bf5a  mov     edx, 17h
0x18000bf5f  jmp     loc_18000BDF5
0x18000bf64  call    cs:__imp_sqlite3_bind_int64
0x18000bf6a  mov     ebx, eax
0x18000bf6c  test    eax, eax
0x18000bf6e  jle     short loc_18000BF79
0x18000bf70  movzx   ebx, ax
0x18000bf73  or      ebx, 87AF0000h
0x18000bf79  test    ebx, ebx
0x18000bf7b  js      loc_18000C2E3
0x18000bf81  mov     rcx, [rbp+230h+var_220]
0x18000bf85  mov     rax, [rcx]
0x18000bf88  xor     edx, edx
0x18000bf8a  mov     rax, [rax]
0x18000bf8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf92  mov     [rsp+330h+var_2F8], r13
0x18000bf97  lea     rcx, [rsp+330h+var_2F8]
0x18000bf9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000bfa1  lea     rdx, [rsp+330h+var_2F8]
0x18000bfa6  call    ??$CreateExternalObjectVector@VPackage@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackage@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackage@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackage@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackage@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackage@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackage@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Package,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0> * *)
0x18000bfab  mov     ebx, eax
0x18000bfad  lea     rdi, aOnecoreBaseApp_443; "onecore\\base\\appmodel\\StateRepositor"...
0x18000bfb4  test    eax, eax
0x18000bfb6  js      loc_18000C214
0x18000bfbc  mov     r8, [rsp+330h+var_2F8]
0x18000bfc1  lea     rdx, [rsp+330h+var_2F0]
0x18000bfc6  lea     rcx, [rsp+330h+var_2C0]
0x18000bfcb  call    ??$AppendResultsToAgileVector@VPackage@Entity@StateRepository@@UIPackage@3Internal@Windows@@VPackageServer@356@V1356@@Statement@DAL@WinRT@StateRepository@@YAJAEAVDatabase@3@AEAV03@PEAV?$AgileVector@PEAVPackage@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackage@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackage@StateRepository@Internal@Windows@@@3674@$0A@@Internal@Collections@Foundation@Windows@@@Z; StateRepository::WinRT::DAL::Statement::AppendResultsToAgileVector<StateRepository::Entity::Package,Windows::Internal::StateRepository::IPackage,Windows::Internal::StateRepository::PackageServer,Windows::Internal::StateRepository::Package>(StateRepository::Database &,StateRepository::Statement &,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0> *)
0x18000bfd0  mov     ebx, eax
0x18000bfd2  test    eax, eax
0x18000bfd4  js      loc_18000C094
0x18000bfda  mov     rcx, [rsp+330h+var_2F8]
0x18000bfdf  mov     rax, [rcx]
0x18000bfe2  mov     rdx, rsi
0x18000bfe5  mov     rax, [rax+40h]
0x18000bfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfee  mov     ebx, eax
0x18000bff0  test    eax, eax
0x18000bff2  js      loc_18000C0CD
0x18000bff8  mov     rcx, [rsp+330h+var_2F8]
0x18000bffd  test    rcx, rcx
0x18000c000  jz      short loc_18000C014
0x18000c002  mov     [rsp+330h+var_2F8], r13
0x18000c007  mov     rax, [rcx]
0x18000c00a  mov     rax, [rax+10h]
0x18000c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c013  nop
0x18000c014  mov     ebx, r13d
0x18000c017  lea     rcx, [rsp+330h+var_2C0]; struct StateRepository::Database *
0x18000c01c  call    ?AddToCache@Repository@StateRepository@@SAJAEAVDatabase@2@@Z; StateRepository::Repository::AddToCache(StateRepository::Database &)
0x18000c021  mov     rcx, [rbp+238h]; this
0x18000c028  test    eax, eax
0x18000c02a  jns     short loc_18000C03C
0x18000c02c  mov     r9d, eax; char *
0x18000c02f  mov     r8, rdi; unsigned int
0x18000c032  mov     edx, 7Fh; void *
0x18000c037  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c03c  test    ebx, ebx
0x18000c03e  js      loc_18000BEA3
0x18000c044  mov     r8d, r14d; unsigned int
0x18000c047  lea     rdx, aPackagestatics_37; "PackageStatics::FindByUserOrDefaultAcco"...
0x18000c04e  lea     rcx, [rbp+230h+var_190]; this
0x18000c055  call    ?Stop@Method@API@WinRT@Trace@StateRepository@@QEAAXPEBDI@Z; StateRepository::Trace::WinRT::API::Method::Stop(char const *,uint)
0x18000c05a  lea     rcx, [rsp+330h+var_2F0]; this
0x18000c05f  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000c064  nop
0x18000c065  lea     rcx, [rsp+330h+var_2C0]; struct StateRepository::Database *
0x18000c06a  call    ?AddToCache@Repository@StateRepository@@SAJAEAVDatabase@2@@Z; StateRepository::Repository::AddToCache(StateRepository::Database &)
0x18000c06f  nop
0x18000c070  lea     rcx, [rsp+330h+var_2C0]; this
0x18000c075  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18000c07a  lea     rcx, [rbp+230h+var_190]; this
0x18000c081  call    ??1Method@API@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::API::Method::~Method(void)
0x18000c086  lock dec cs:?s_count@RequestInProgress@Client@WinRT@StateRepository@@0JC; long volatile StateRepository::WinRT::Client::RequestInProgress::s_count
0x18000c08d  xor     eax, eax
0x18000c08f  jmp     loc_18000BF0E
0x18000c094  mov     rcx, [rbp+238h]; this
  ... truncated ...
```
