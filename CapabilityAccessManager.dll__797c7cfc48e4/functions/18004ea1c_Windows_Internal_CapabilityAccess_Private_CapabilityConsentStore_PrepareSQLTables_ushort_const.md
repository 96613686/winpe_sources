# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::PrepareSQLTables(ushort const *)

- ea: `0x18004ea1c`
- end: `0x18004f4af`
- name: `?PrepareSQLTables@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SAJPEBG@Z`
- size: `2707`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x1800204f8`
- `0x180039eb8`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001e118`
- `0x18001e42c`
- `0x18002392c`
- `0x180029408`
- `0x18002e79c`
- `0x18003121c`
- `0x1800314fc`
- `0x1800330f8`
- `0x180033360`
- `0x180036e4c`
- `0x180037034`
- `0x1800385c8`
- `0x180038df4`
- `0x18003b1a0`
- `0x18003e21c`
- `0x1800486a4`
- `0x18004d320`
- `0x18004d850`
- `0x18004ea1c`
- `0x18005b1dc`
- `0x1800a0bb8`
- `0x1800a37b8`
- `0x1800a44e8`
- `0x1800a5134`
- `0x1800a5e34`
- `0x1800a6080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec19`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004ebf3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004ebf3`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18004ea5d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18004ea5d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004f05a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004f05a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::PrepareSQLTables(
        const unsigned __int16 *a1)
{
  Windows::Internal::CapabilityAccess::Private::SQL *v1; // rcx
  Windows::Internal::CapabilityAccess::Private::SQL *v2; // rcx
  const char *v3; // r9
  __int64 result; // rax
  Windows::Internal::CapabilityAccess::Private::SQL *v5; // rcx
  const char *v6; // r9
  __int64 CAMDatabaseDirectory; // rax
  const WCHAR *v8; // rax
  BOOL DirectoryW; // ebx
  signed int LastError; // eax
  Windows::Internal::CapabilityAccess::Private::SQL *CAMDatabasePath; // rax
  __int64 v12; // rax
  int v13; // ebx
  Windows::Internal::CapabilityAccess::Private::SQL *v14; // rax
  __int64 v15; // rax
  int v16; // eax
  bool v17; // r12
  int Pragma; // eax
  PVOID *v19; // rcx
  int v20; // esi
  Windows::Internal::CapabilityAccess::Private::SQL *v21; // rcx
  int v22; // eax
  Windows::Internal::CapabilityAccess::Private::SQL *v23; // rcx
  __int64 RuntimeTargetSchemaVersion; // rbx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  Windows::Internal::CapabilityAccess::Private::SQL *v31; // rax
  const WCHAR *v32; // rax
  BOOL v33; // esi
  bool v34; // r12
  Windows::Internal::CapabilityAccess::Private::SQL *v35; // rax
  __int64 v36; // rax
  int v37; // eax
  Windows::Internal::CapabilityAccess::Private::SQL *v38; // rax
  __int64 v39; // rax
  int v40; // eax
  int v41; // eax
  PVOID *v42; // rcx
  unsigned int v43; // ebx
  int v44; // eax
  Windows::Internal::CapabilityAccess::Private::SQL *v45; // rcx
  __int64 v46; // rsi
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // [rsp+20h] [rbp-1E8h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+28h] [rbp-1E0h] BYREF
  _QWORD v52[4]; // [rsp+30h] [rbp-1D8h] BYREF
  char v53; // [rsp+50h] [rbp-1B8h]
  unsigned __int64 v54; // [rsp+58h] [rbp-1B0h] BYREF
  _BYTE v55[16]; // [rsp+60h] [rbp-1A8h] BYREF
  int v56; // [rsp+70h] [rbp-198h]
  _BYTE v57[224]; // [rsp+E0h] [rbp-128h] BYREF
  int v58[8]; // [rsp+1C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]
  const unsigned __int16 *v60; // [rsp+210h] [rbp+8h] BYREF

  v60 = a1;
  LOBYTE(v50) = 0;
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v54 = UnbiasedTime;
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v57);
  v52[0] = &v50;
  v52[1] = &v54;
  v52[2] = &v60;
  v52[3] = v57;
  v53 = 1;
  v1 = (Windows::Internal::CapabilityAccess::Private::SQL *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids);
  }
  try
  {
    if ( !Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(v1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids);
      }
LABEL_10:
      v53 = 0;
      lambda_624eb91712c46328a59e56650350eb72_::operator()(v52);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v57);
      return 0;
    }
    if ( !Windows::Internal::CapabilityAccess::Private::SQL::HasUserConsentedToUsageDataCollection(v2) )
    {
      v5 = (Windows::Internal::CapabilityAccess::Private::SQL *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids);
      }
      try
      {
        Windows::Internal::CapabilityAccess::Private::SQL::RemoveAllHistoryData(v5);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids);
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xBF5,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          v6);
        goto LABEL_10;
      }
      goto LABEL_10;
    }
    StateRepository::Database::Database((StateRepository::Database *)v55);
    CAMDatabaseDirectory = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseDirectory(v58);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(CAMDatabaseDirectory);
    DirectoryW = CreateDirectoryW(v8, 0);
    std::wstring::_Tidy_deallocate(v58);
    if ( !DirectoryW && GetLastError() != 183 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC01,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)LastError,
          v50);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl'::`2'::impl) )
    {
      CAMDatabasePath = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath((Windows::Internal::CapabilityAccess::Private::SQL *)v58);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(CAMDatabasePath);
      v13 = StateRepository::Database::Open(v55, v12, 0);
      std::wstring::_Tidy_deallocate(v58);
      if ( v13 >= 0 )
      {
        v17 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids);
        }
        v14 = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath((Windows::Internal::CapabilityAccess::Private::SQL *)v58);
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
        v16 = StateRepository::Database::Open(v55, v15, 2);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC77,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v16,
            v50);
        std::wstring::_Tidy_deallocate(v58);
        v17 = 0;
      }
      LODWORD(UnbiasedTime) = 0;
      Pragma = StateRepository::Database::GetPragma(
                 (StateRepository::Database *)v55,
                 "user_version",
                 (int *)&UnbiasedTime);
      if ( Pragma < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC81,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)Pragma,
          v50);
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
        v20 = UnbiasedTime;
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v20 = UnbiasedTime;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids,
            (unsigned int)UnbiasedTime);
          v19 = (PVOID *)WPP_GLOBAL_Control;
        }
        else
        {
          v20 = UnbiasedTime;
        }
        if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
          WPP_SF_d(v19[2], 27, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids, 1537);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl'::`2'::impl) )
      {
        v56 = 1;
        if ( !v20 && v17 )
        {
          v20 = 257;
          v22 = StateRepository::Database::SetPragma((StateRepository::Database *)v55, "user_version", 257);
          if ( v22 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xC91,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
              (const char *)(unsigned int)v22,
              v50);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids, 257);
          }
        }
        RuntimeTargetSchemaVersion = (int)Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion();
        if ( v20 )
        {
          if ( (int)(v20 & 0xFFFFFF00) <= (RuntimeTargetSchemaVersion & 0xFFFFFF00) )
          {
            if ( (v20 & 0xFFFFFF00) == (RuntimeTargetSchemaVersion & 0xFFFFFF00)
              && (unsigned __int8)v20 > (unsigned __int8)RuntimeTargetSchemaVersion )
            {
              CapabilityAccessTelemetry::LogDatabaseVersionMismatch(v17, v20, RuntimeTargetSchemaVersion);
            }
            else if ( v20 != (_DWORD)RuntimeTargetSchemaVersion )
            {
              MigrateDatabase(v20);
            }
          }
          else
          {
            CapabilityAccessTelemetry::LogDatabaseVersionMismatch(v17, v20, RuntimeTargetSchemaVersion);
            v26 = Windows::Internal::CapabilityAccess::Private::SQL::ReprovisionCAMDatabase(
                    (Windows::Internal::CapabilityAccess::Private::SQL *)L"Database version is ahead of runtime",
                    (const unsigned __int16 *)(unsigned int)v20,
                    2147549183LL);
            if ( v26 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xCBE,
                (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
                (const char *)(unsigned int)v26,
                v50);
            v27 = StateRepository::Database::SetPragma(
                    (StateRepository::Database *)v55,
                    "user_version",
                    RuntimeTargetSchemaVersion);
            v23 = retaddr;
            if ( v27 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xCC3,
                (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
                (const char *)(unsigned int)v27,
                v50);
          }
        }
        else
        {
          Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(v23);
          v25 = StateRepository::Database::SetPragma(
                  (StateRepository::Database *)v55,
                  "user_version",
                  RuntimeTargetSchemaVersion);
          v23 = retaddr;
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xCB2,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
              (const char *)(unsigned int)v25,
              v50);
        }
        Windows::Internal::CapabilityAccess::Private::SQL::CreateStringTables(v23);
        StateRepository::Database::SetCheckpointOnClose((StateRepository::Database *)v55, 0);
        StateRepository::Repository::AddToCache((struct StateRepository::Database *)v55);
        LOBYTE(v50) = 1;
        StateRepository::Database::~Database((StateRepository::Database *)v55);
        v53 = 0;
        lambda_624eb91712c46328a59e56650350eb72_::operator()(v52);
        wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v57);
        return 0;
      }
      if ( v20 )
      {
        if ( v20 > 1537 )
        {
          CapabilityAccessTelemetry::LogDatabaseVersionMismatch(v17, v20, 1537);
          v29 = Windows::Internal::CapabilityAccess::Private::SQL::ReprovisionCAMDatabase(
                  (Windows::Internal::CapabilityAccess::Private::SQL *)L"Database version is ahead of runtime",
                  (const unsigned __int16 *)(unsigned int)v20,
                  2147549183LL);
          v21 = retaddr;
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xCFE,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
              (const char *)(unsigned int)v29,
              v50);
          goto LABEL_79;
        }
        if ( v20 != 1537 )
          goto LABEL_78;
      }
      else
      {
        if ( v17 )
        {
          v20 = 257;
          v28 = StateRepository::Database::SetPragma((StateRepository::Database *)v55, "user_version", 257);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xCF1,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
              (const char *)(unsigned int)v28,
              v50);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids, 257);
          }
LABEL_78:
          MigrateDatabase(v20);
          goto LABEL_79;
        }
        Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(v21);
      }
LABEL_79:
      Windows::Internal::CapabilityAccess::Private::SQL::CreateStringTables(v21);
      v30 = StateRepository::Database::SetPragma((StateRepository::Database *)v55, "user_version", 1537);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD0A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)v30,
          v50);
      StateRepository::Repository::AddToCache((struct StateRepository::Database *)v55);
      LOBYTE(v50) = 1;
      StateRepository::Database::~Database((StateRepository::Database *)v55);
      v53 = 0;
      lambda_624eb91712c46328a59e56650350eb72_::operator()(v52);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v57);
      return 0;
    }
    v31 = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath((Windows::Internal::CapabilityAccess::Private::SQL *)v58);
    v32 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    v33 = PathFileExistsW(v32);
    v34 = v33;
    std::wstring::_Tidy_deallocate(v58);
    if ( v33 )
    {
      v35 = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath((Windows::Internal::CapabilityAccess::Private::SQL *)v58);
      v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
      v37 = StateRepository::Database::Open(v55, v36, 0);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC0B,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)v37,
          v50);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids);
      }
      v38 = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath((Windows::Internal::CapabilityAccess::Private::SQL *)v58);
      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
      v40 = StateRepository::Database::Open(v55, v39, 2);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC11,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)v40,
          v50);
    }
    std::wstring::_Tidy_deallocate(v58);
    LODWORD(UnbiasedTime) = 0;
    v41 = StateRepository::Database::GetPragma((StateRepository::Database *)v55, "user_version", (int *)&UnbiasedTime);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC15,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v41,
        v50);
    v42 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
      v43 = UnbiasedTime;
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v43 = UnbiasedTime;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids,
          (unsigned int)UnbiasedTime);
        v42 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        v43 = UnbiasedTime;
      }
      if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 1) != 0 && *((_BYTE *)v42 + 25) >= 4u )
        WPP_SF_d(v42[2], 23, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids, 1537);
    }
    v56 = 1;
    if ( !v43 && v33 )
    {
      v43 = 257;
      v44 = StateRepository::Database::SetPragma((StateRepository::Database *)v55, "user_version", 257);
      if ( v44 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC23,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)v44,
          v50);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids, 257);
      }
    }
    v46 = (int)Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion();
    if ( v43 )
    {
      if ( (int)(v43 & 0xFFFFFF00) <= (v46 & 0xFFFFFF00) )
      {
        if ( (v43 & 0xFFFFFF00) == (v46 & 0xFFFFFF00) && (unsigned __int8)v43 > (unsigned __int8)v46 )
        {
          CapabilityAccessTelemetry::LogDatabaseVersionMismatch(v34, v43, v46);
        }
        else if ( v43 != (_DWORD)v46 )
        {
          MigrateDatabase(v43);
        }
      }
      else
      {
        CapabilityAccessTelemetry::LogDatabaseVersionMismatch(v34, v43, v46);
        v48 = Windows::Internal::CapabilityAccess::Private::SQL::ReprovisionCAMDatabase(
                (Windows::Internal::CapabilityAccess::Private::SQL *)L"Database version is ahead of runtime",
                (const unsigned __int16 *)v43,
                2147942487LL);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC4C,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v48,
            v50);
        v49 = StateRepository::Database::SetPragma((StateRepository::Database *)v55, "user_version", v46);
        v45 = retaddr;
        if ( v49 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC51,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v49,
            v50);
      }
    }
    else
    {
      Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(v45);
      v47 = StateRepository::Database::SetPragma((StateRepository::Database *)v55, "user_version", v46);
      v45 = retaddr;
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC44,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)v47,
          v50);
    }
    Windows::Internal::CapabilityAccess::Private::SQL::CreateStringTables(v45);
    LOBYTE(v50) = 1;
    StateRepository::Database::~Database((StateRepository::Database *)v55);
    v53 = 0;
    lambda_624eb91712c46328a59e56650350eb72_::operator()(v52);
    wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v57);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD16,
                           (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18004ea1c  mov     [rsp+arg_8], rbx
0x18004ea21  mov     [rsp+arg_10], rsi
0x18004ea26  mov     [rsp+arg_0], rcx
0x18004ea2b  push    r12
0x18004ea2d  push    r13
0x18004ea2f  push    r15
0x18004ea31  sub     rsp, 1F0h
0x18004ea38  mov     rax, cs:__security_cookie
0x18004ea3f  xor     rax, rsp
0x18004ea42  mov     [rsp+208h+var_28], rax
0x18004ea4a  mov     byte ptr [rsp+208h+var_1E8], 0; int
0x18004ea4f  mov     [rsp+208h+UnbiasedTime], 0
0x18004ea58  lea     rcx, [rsp+208h+UnbiasedTime]; UnbiasedTime
0x18004ea5d  call    cs:__imp_QueryUnbiasedInterruptTime
0x18004ea63  mov     rax, [rsp+208h+UnbiasedTime]
0x18004ea68  mov     [rsp+208h+var_1B0], rax
0x18004ea6d  lea     rcx, [rsp+208h+var_128]; this
0x18004ea75  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x18004ea7a  nop
0x18004ea7b  lea     rax, [rsp+208h+var_1E8]
0x18004ea80  mov     [rsp+208h+var_1D8], rax
0x18004ea85  lea     rax, [rsp+208h+var_1B0]
0x18004ea8a  mov     [rsp+208h+var_1D0], rax
0x18004ea8f  lea     rax, [rsp+208h+arg_0]
0x18004ea97  mov     [rsp+208h+var_1C8], rax
0x18004ea9c  lea     rax, [rsp+208h+var_128]
0x18004eaa4  mov     [rsp+208h+var_1C0], rax
0x18004eaa9  mov     esi, 1
0x18004eaae  mov     [rsp+208h+var_1B8], sil
0x18004eab3  lea     r13, WPP_GLOBAL_Control
0x18004eaba  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004eac1  cmp     rcx, r13
0x18004eac4  jz      short loc_18004EAEA
0x18004eac6  test    [rcx+1Ch], sil
0x18004eaca  jz      short loc_18004EAEA
0x18004eacc  lea     r15, WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids
0x18004ead3  cmp     byte ptr [rcx+19h], 4
0x18004ead7  jb      short loc_18004EAF1
0x18004ead9  lea     edx, [rsi+10h]
0x18004eadc  mov     r8, r15
0x18004eadf  mov     rcx, [rcx+10h]
0x18004eae3  call    WPP_SF_
0x18004eae8  jmp     short loc_18004EAF1
0x18004eaea  lea     r15, WPP_cf65e9eba4ea34e94265eebeb164870c_Traceguids
0x18004eaf1  call    ?IsDatabaseEnabledByEditionPolicy@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(void)
0x18004eaf6  test    al, al
0x18004eaf8  jnz     short loc_18004EB48
0x18004eafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb01  cmp     rcx, r13
0x18004eb04  jz      short loc_18004EB24
0x18004eb06  test    [rcx+1Ch], sil
0x18004eb0a  jz      short loc_18004EB24
0x18004eb0c  cmp     byte ptr [rcx+19h], 4
0x18004eb10  jb      short loc_18004EB24
0x18004eb12  mov     edx, 12h
0x18004eb17  mov     r8, r15
0x18004eb1a  mov     rcx, [rcx+10h]
0x18004eb1e  call    WPP_SF_
0x18004eb23  nop
0x18004eb24  mov     [rsp+208h+var_1B8], 0
0x18004eb29  lea     rcx, [rsp+208h+var_1D8]
0x18004eb2e  call    _lambda_624eb91712c46328a59e56650350eb72___operator__
0x18004eb33  nop
0x18004eb34  lea     rcx, [rsp+208h+var_128]; this
0x18004eb3c  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x18004eb41  xor     eax, eax
0x18004eb43  jmp     loc_18004F32A
0x18004eb48  call    ?HasUserConsentedToUsageDataCollection@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::HasUserConsentedToUsageDataCollection(void)
0x18004eb4d  test    al, al
0x18004eb4f  jnz     short loc_18004EBCE
0x18004eb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb58  cmp     rcx, r13
0x18004eb5b  jz      short loc_18004EB7B
0x18004eb5d  test    [rcx+1Ch], sil
0x18004eb61  jz      short loc_18004EB7B
0x18004eb63  cmp     byte ptr [rcx+19h], 4
0x18004eb67  jb      short loc_18004EB7B
0x18004eb69  mov     edx, 13h
0x18004eb6e  mov     r8, r15
0x18004eb71  mov     rcx, [rcx+10h]
0x18004eb75  call    WPP_SF_
0x18004eb7a  nop
0x18004eb7b  call    ?RemoveAllHistoryData@SQL@Private@CapabilityAccess@Internal@Windows@@YAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::RemoveAllHistoryData(void)
0x18004eb80  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb87  cmp     rcx, r13
0x18004eb8a  jz      short loc_18004EBAA
0x18004eb8c  test    [rcx+1Ch], sil
0x18004eb90  jz      short loc_18004EBAA
0x18004eb92  cmp     byte ptr [rcx+19h], 4
0x18004eb96  jb      short loc_18004EBAA
0x18004eb98  mov     edx, 14h
0x18004eb9d  mov     r8, r15
0x18004eba0  mov     rcx, [rcx+10h]
0x18004eba4  call    WPP_SF_
0x18004eba9  nop
0x18004ebaa  mov     [rsp+208h+var_1B8], 0
0x18004ebaf  lea     rcx, [rsp+208h+var_1D8]
0x18004ebb4  call    _lambda_624eb91712c46328a59e56650350eb72___operator__
0x18004ebb9  nop
0x18004ebba  lea     rcx, [rsp+208h+var_128]; this
0x18004ebc2  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x18004ebc7  xor     eax, eax
0x18004ebc9  jmp     loc_18004F32A
0x18004ebce  lea     rcx, [rsp+208h+var_1A8]; this
0x18004ebd3  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18004ebd8  nop
0x18004ebd9  lea     rcx, [rsp+208h+var_48]
0x18004ebe1  call    ?GetCAMDatabaseDirectory@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseDirectory(void)
0x18004ebe6  mov     rcx, rax
0x18004ebe9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ebee  xor     edx, edx; lpSecurityAttributes
0x18004ebf0  mov     rcx, rax; lpPathName
0x18004ebf3  call    cs:__imp_CreateDirectoryW
0x18004ebf9  mov     ebx, eax
0x18004ebfb  lea     rcx, [rsp+208h+var_48]
0x18004ec03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ec08  test    ebx, ebx
0x18004ec0a  jnz     short loc_18004EC3B
0x18004ec0c  call    cs:__imp_GetLastError
0x18004ec12  cmp     eax, 0B7h
0x18004ec17  jz      short loc_18004EC3B
0x18004ec19  call    cs:__imp_GetLastError
0x18004ec1f  test    eax, eax
0x18004ec21  jle     short loc_18004EC2B
0x18004ec23  movzx   eax, ax
0x18004ec26  or      eax, 80070000h
0x18004ec2b  mov     rcx, [rsp+208h]; this
0x18004ec33  test    eax, eax
0x18004ec35  js      loc_18004F354
0x18004ec3b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload> `wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl(void)'::`2'::impl
0x18004ec42  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(void)
0x18004ec47  lea     rcx, [rsp+208h+var_48]; int
0x18004ec4f  test    al, al
0x18004ec51  jnz     loc_18004F04A
0x18004ec57  call    ?GetCAMDatabasePath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath(void)
0x18004ec5c  nop
0x18004ec5d  mov     rcx, rax
0x18004ec60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ec65  xor     r8d, r8d
0x18004ec68  mov     rdx, rax
0x18004ec6b  lea     rcx, [rsp+208h+var_1A8]
0x18004ec70  call    ?Open@Database@StateRepository@@QEAAJPEB_WW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(wchar_t const *,StateRepository::Database::OpenFlags,uint const *)
0x18004ec75  mov     ebx, eax
0x18004ec77  lea     rcx, [rsp+208h+var_48]
0x18004ec7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ec84  shr     ebx, 1Fh
0x18004ec87  test    bl, bl
0x18004ec89  jz      short loc_18004ECFF
0x18004ec8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec92  cmp     rcx, r13
0x18004ec95  jz      short loc_18004ECB4
0x18004ec97  test    [rcx+1Ch], sil
0x18004ec9b  jz      short loc_18004ECB4
0x18004ec9d  cmp     byte ptr [rcx+19h], 4
0x18004eca1  jb      short loc_18004ECB4
0x18004eca3  mov     edx, 19h
0x18004eca8  mov     r8, r15
0x18004ecab  mov     rcx, [rcx+10h]
0x18004ecaf  call    WPP_SF_
0x18004ecb4  lea     rcx, [rsp+208h+var_48]; int
0x18004ecbc  call    ?GetCAMDatabasePath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath(void)
0x18004ecc1  nop
0x18004ecc2  mov     rcx, rax
0x18004ecc5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ecca  mov     r8d, 2
0x18004ecd0  mov     rdx, rax
0x18004ecd3  lea     rcx, [rsp+208h+var_1A8]
0x18004ecd8  call    ?Open@Database@StateRepository@@QEAAJPEB_WW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(wchar_t const *,StateRepository::Database::OpenFlags,uint const *)
0x18004ecdd  mov     rcx, [rsp+208h]; this
0x18004ece5  test    eax, eax
0x18004ece7  js      loc_18004F369
0x18004eced  lea     rcx, [rsp+208h+var_48]
0x18004ecf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ecfa  xor     r12b, r12b
0x18004ecfd  jmp     short loc_18004ED02
0x18004ecff  mov     r12b, sil
0x18004ed02  mov     dword ptr [rsp+208h+UnbiasedTime], 0
0x18004ed0a  lea     r8, [rsp+208h+UnbiasedTime]; int *
0x18004ed0f  lea     r13, aUserVersion; "user_version"
0x18004ed16  mov     rdx, r13; char *
0x18004ed19  lea     rcx, [rsp+208h+var_1A8]; this
0x18004ed1e  call    ?GetPragma@Database@StateRepository@@QEAAJPEBDPEAH@Z; StateRepository::Database::GetPragma(char const *,int *)
0x18004ed23  mov     rcx, [rsp+208h]; this
0x18004ed2b  test    eax, eax
0x18004ed2d  js      loc_18004F37E
0x18004ed33  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed3a  lea     rbx, WPP_GLOBAL_Control
0x18004ed41  cmp     rcx, rbx
0x18004ed44  jz      short loc_18004EDA1
0x18004ed46  test    [rcx+1Ch], sil
0x18004ed4a  jz      short loc_18004ED73
0x18004ed4c  cmp     byte ptr [rcx+19h], 4
0x18004ed50  jb      short loc_18004ED73
0x18004ed52  mov     edx, 1Ah
0x18004ed57  mov     esi, dword ptr [rsp+208h+UnbiasedTime]
0x18004ed5b  mov     r9d, esi
0x18004ed5e  mov     r8, r15
0x18004ed61  mov     rcx, [rcx+10h]
0x18004ed65  call    WPP_SF_d
0x18004ed6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed71  jmp     short loc_18004ED77
0x18004ed73  mov     esi, dword ptr [rsp+208h+UnbiasedTime]
0x18004ed77  cmp     rcx, rbx
0x18004ed7a  jz      short loc_18004EDA5
0x18004ed7c  test    byte ptr [rcx+1Ch], 1
0x18004ed80  jz      short loc_18004EDA5
0x18004ed82  cmp     byte ptr [rcx+19h], 4
0x18004ed86  jb      short loc_18004EDA5
0x18004ed88  mov     edx, 1Bh
0x18004ed8d  mov     r9d, 601h
0x18004ed93  mov     r8, r15
0x18004ed96  mov     rcx, [rcx+10h]
0x18004ed9a  call    WPP_SF_d
0x18004ed9f  jmp     short loc_18004EDA5
0x18004eda1  mov     esi, dword ptr [rsp+208h+UnbiasedTime]
0x18004eda5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload> `wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl(void)'::`2'::impl
0x18004edac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(void)
0x18004edb1  test    al, al
0x18004edb3  jz      loc_18004EF31
0x18004edb9  mov     [rsp+208h+var_198], 1
0x18004edc1  test    esi, esi
0x18004edc3  jnz     short loc_18004EE24
0x18004edc5  test    r12b, r12b
0x18004edc8  jz      short loc_18004EE24
0x18004edca  mov     ebx, 101h
0x18004edcf  mov     esi, ebx
0x18004edd1  mov     r8d, ebx; __int64
0x18004edd4  mov     rdx, r13; char *
0x18004edd7  lea     rcx, [rsp+208h+var_1A8]; this
0x18004eddc  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x18004ede1  mov     rcx, [rsp+208h]; this
0x18004ede9  test    eax, eax
0x18004edeb  js      loc_18004F392
0x18004edf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004edf8  lea     rax, WPP_GLOBAL_Control
0x18004edff  cmp     rcx, rax
0x18004ee02  jz      short loc_18004EE24
0x18004ee04  test    byte ptr [rcx+1Ch], 1
0x18004ee08  jz      short loc_18004EE24
0x18004ee0a  cmp     byte ptr [rcx+19h], 4
0x18004ee0e  jb      short loc_18004EE24
0x18004ee10  mov     edx, 1Ch
0x18004ee15  mov     r9d, ebx
0x18004ee18  mov     r8, r15
0x18004ee1b  mov     rcx, [rcx+10h]
0x18004ee1f  call    WPP_SF_d
0x18004ee24  call    ?GetRuntimeTargetSchemaVersion@UsageDatabaseManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAHXZ; Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion(void)
0x18004ee29  movsxd  rbx, eax
0x18004ee2c  test    esi, esi
0x18004ee2e  jnz     short loc_18004EE5A
0x18004ee30  call    ?CreateRecordTables@SQL@Private@CapabilityAccess@Internal@Windows@@YAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(void)
0x18004ee35  mov     r8, rbx; __int64
0x18004ee38  mov     rdx, r13; char *
0x18004ee3b  lea     rcx, [rsp+208h+var_1A8]; this
0x18004ee40  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x18004ee45  mov     rcx, [rsp+208h]; this
0x18004ee4d  test    eax, eax
0x18004ee4f  js      loc_18004F3A6
0x18004ee55  jmp     loc_18004EEE2
0x18004ee5a  mov     edx, esi
0x18004ee5c  mov     eax, 0FFFFFF00h
0x18004ee61  and     edx, eax
0x18004ee63  mov     r8d, ebx
0x18004ee66  and     r8d, eax
0x18004ee69  cmp     edx, r8d
0x18004ee6c  jle     short loc_18004EEC1
0x18004ee6e  mov     r8d, ebx; int
0x18004ee71  mov     edx, esi; int
0x18004ee73  mov     cl, r12b; bool
0x18004ee76  call    ?LogDatabaseVersionMismatch@CapabilityAccessTelemetry@@SAX_NHH@Z; CapabilityAccessTelemetry::LogDatabaseVersionMismatch(bool,int,int)
0x18004ee7b  mov     r8d, 8000FFFFh; int
0x18004ee81  mov     edx, esi; unsigned __int16 *
0x18004ee83  lea     rcx, aDatabaseVersio; "Database version is ahead of runtime"
0x18004ee8a  call    ?ReprovisionCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YAJPEBGHJ@Z; Windows::Internal::CapabilityAccess::Private::SQL::ReprovisionCAMDatabase(ushort const *,int,long)
0x18004ee8f  mov     rcx, [rsp+208h]; this
0x18004ee97  test    eax, eax
0x18004ee99  js      loc_18004F3BA
0x18004ee9f  mov     r8, rbx; __int64
0x18004eea2  mov     rdx, r13; char *
0x18004eea5  lea     rcx, [rsp+208h+var_1A8]; this
0x18004eeaa  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x18004eeaf  mov     rcx, [rsp+208h]; this
0x18004eeb7  test    eax, eax
0x18004eeb9  js      loc_18004F3CE
0x18004eebf  jmp     short loc_18004EEE2
0x18004eec1  jnz     short loc_18004EED7
0x18004eec3  cmp     sil, bl
0x18004eec6  jbe     short loc_18004EED7
0x18004eec8  mov     r8d, ebx; int
0x18004eecb  mov     edx, esi; int
0x18004eecd  mov     cl, r12b; bool
0x18004eed0  call    ?LogDatabaseVersionMismatch@CapabilityAccessTelemetry@@SAX_NHH@Z; CapabilityAccessTelemetry::LogDatabaseVersionMismatch(bool,int,int)
0x18004eed5  jmp     short loc_18004EEE2
0x18004eed7  cmp     esi, ebx
0x18004eed9  jz      short loc_18004EEE2
0x18004eedb  mov     ecx, esi; int
0x18004eedd  call    ?MigrateDatabase@@YAXH@Z; MigrateDatabase(int)
0x18004eee2  call    ?CreateStringTables@SQL@Private@CapabilityAccess@Internal@Windows@@YAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::CreateStringTables(void)
0x18004eee7  xor     edx, edx; bool
0x18004eee9  lea     rcx, [rsp+208h+var_1A8]; this
  ... truncated ...
```
