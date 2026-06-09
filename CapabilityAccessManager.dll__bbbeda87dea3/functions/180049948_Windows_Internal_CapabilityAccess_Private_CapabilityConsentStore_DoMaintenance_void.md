# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::DoMaintenance(void)

- ea: `0x180049948`
- end: `0x18004a074`
- name: `?DoMaintenance@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SAJXZ`
- size: `1836`
- prototype: `__int64 __fastcall(Windows::Internal::CapabilityAccess::Private::SQL *)`
- caller_count: `2`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800375f4`
- `0x1800879f0`

## callees

- `0x18000b908`
- `0x18001e118`
- `0x18001e42c`
- `0x18001fd3c`
- `0x180020fcc`
- `0x18002392c`
- `0x180029304`
- `0x18002d638`
- `0x18002e704`
- `0x18002f560`
- `0x1800311c4`
- `0x1800334a8`
- `0x1800349dc`
- `0x1800356e0`
- `0x1800358ec`
- `0x180037460`
- `0x180039a1c`
- `0x18003b1a0`
- `0x18003b2c0`
- `0x180043224`
- `0x180047968`
- `0x180047f48`
- `0x1800480b8`
- `0x1800480f0`
- `0x1800484ec`
- `0x180049060`
- `0x180049948`
- `0x18004f9d8`
- `0x180052004`
- `0x18005b1dc`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a2758`
- `0x1800a3ef4`
- `0x1800a44e8`
- `0x1800a5520`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180049a16`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180049a16`
- `ext-ms-win-capabilityaccessmanager-storage-l1-1-0!DoCAMStorageDatabaseMaintenance` at `0x1800499d4`
- `ext-ms-win-capabilityaccessmanager-storage-l1-1-0!DoCAMStorageDatabaseMaintenance` at `0x1800499d4`

## string_xrefs

- `0x180049ddb`: `DELETE FROM ServiceNames WHERE ID NOT IN (SELECT DISTINCT ServiceName FROM NonPackagedUsageHistory);`
- `0x180049dba`: `DELETE FROM AppNames WHERE ID NOT IN (SELECT DISTINCT AppName FROM PackagedUsageHistory UNION SELECT DISTINCT AppName FROM NonPackagedUsageHistory);`
- `0x180049d99`: `DELETE FROM AccessGUIDs WHERE ID NOT IN (SELECT DISTINCT AccessGUID FROM PackagedUsageHistory UNION SELECT DISTINCT AccessGUID FROM NonPackagedUsageHistory);`
- `0x180049d78`: `DELETE FROM Capabilities WHERE ID NOT IN (SELECT DISTINCT Capability FROM PackagedUsageHistory UNION SELECT DISTINCT Capability FROM NonPackagedUsageHistory UNION SELECT DISTINCT Capability FROM NonPackagedGlobalPromptHistory);`
- `0x180049d57`: `DELETE FROM Users WHERE ID NOT IN (SELECT DISTINCT UserSid FROM PackagedUsageHistory UNION SELECT DISTINCT UserSid FROM NonPackagedUsageHistory UNION SELECT DISTINCT UserSid FROM NonPackagedGlobalPromptHistory);`
- `0x180049d36`: `DELETE FROM BinaryFullPaths WHERE ID NOT IN (SELECT DISTINCT BinaryFullPath FROM NonPackagedUsageHistory UNION SELECT DISTINCT BinaryFullPath FROM NonPackagedIdentityRelationship);`
- `0x180049d15`: `DELETE FROM ProgramIDs WHERE ID NOT IN (SELECT DISTINCT ProgramID FROM NonPackagedUsageHistory UNION SELECT DISTINCT ProgramID FROM NonPackagedIdentityRelationship UNION SELECT DISTINCT ProgramID FROM NonPackagedGlobalPromptHistory);`
- `0x180049cf4`: `DELETE FROM NonPackagedIdentityRelationship WHERE FileID NOT IN (SELECT DISTINCT ID FROM FileIDs);`
- `0x180049cd3`: `DELETE FROM FileIDs WHERE ID NOT IN (SELECT DISTINCT FileID FROM NonPackagedUsageHistory UNION SELECT DISTINCT FileID FROM NonPackagedGlobalPromptHistory);`
- `0x180049cb2`: `DELETE FROM PackageFamilyNames WHERE ID NOT IN (SELECT DISTINCT PackageFamilyName FROM PackagedUsageHistory); `
- `0x180049c4f`: `DELETE FROM PackagedUsageHistory WHERE LastUsedTimeStop<?;`
- `0x180049bd4`: `DELETE FROM NonPackagedUsageHistory WHERE LastUsedTimeStop<?;`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::DoMaintenance(
        Windows::Internal::CapabilityAccess::Private::SQL *a1)
{
  __int64 v1; // rdx
  const char *v2; // r9
  __int64 result; // rax
  volatile signed __int32 *v4; // rcx
  void *v5; // rax
  __int64 v6; // rdx
  Windows::Internal::CapabilityAccess::Private::SQL *v7; // rcx
  Windows::Internal::CapabilityAccess::Private::SQL *v8; // rcx
  Windows::Internal::CapabilityAccess::Private::SQL *v9; // rcx
  __int64 v10; // rax
  Windows::Internal::CapabilityAccess::Private::SQL *v11; // rcx
  int RuntimeTargetSchemaVersion; // ebx
  int Pragma; // eax
  unsigned int ExpirationPolicyInDays; // edi
  Windows::Internal::CapabilityAccess::Private *v15; // rcx
  unsigned __int64 SystemTimeAsUInt64; // rbx
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  int NoRow; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int (*v24)(void *); // r8
  void *v25; // r9
  int v26; // eax
  int (*v27)(void *); // r8
  void *v28; // r9
  int v29; // eax
  int (*v30)(void *); // r8
  void *v31; // r9
  int v32; // eax
  int (*v33)(void *); // r8
  void *v34; // r9
  int v35; // eax
  int (*v36)(void *); // r8
  void *v37; // r9
  int v38; // eax
  int (*v39)(void *); // r8
  void *v40; // r9
  int v41; // eax
  int (*v42)(void *); // r8
  void *v43; // r9
  int v44; // eax
  int (*v45)(void *); // r8
  void *v46; // r9
  int v47; // eax
  int (*v48)(void *); // r8
  void *v49; // r9
  int v50; // eax
  int (*v51)(void *); // r8
  void *v52; // r9
  int v53; // eax
  int (*v54)(void *); // r8
  void *v55; // r9
  int v56; // eax
  __int64 v57; // rdx
  char v58; // di
  unsigned __int64 v59; // rbx
  StateRepository::Database *v60; // [rsp+20h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v61; // [rsp+28h] [rbp-1C0h]
  _DWORD v62[4]; // [rsp+30h] [rbp-1B8h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-1A8h] BYREF
  char v64; // [rsp+48h] [rbp-1A0h]
  unsigned __int64 v65; // [rsp+50h] [rbp-198h] BYREF
  unsigned __int64 NumRowsInUsageHistoryTable; // [rsp+58h] [rbp-190h] BYREF
  unsigned __int64 NumAppsInHistoryTable; // [rsp+60h] [rbp-188h] BYREF
  __int64 CAMDatabaseSizeInBytes; // [rsp+68h] [rbp-180h] BYREF
  _QWORD v69[6]; // [rsp+70h] [rbp-178h] BYREF
  char v70; // [rsp+A0h] [rbp-148h]
  _BYTE v71[16]; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v72[48]; // [rsp+C0h] [rbp-128h] BYREF
  _BYTE v73[248]; // [rsp+F0h] [rbp-F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]
  int v75; // [rsp+1F0h] [rbp+8h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+1F8h] [rbp+10h] BYREF
  __int64 v77; // [rsp+200h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+208h] [rbp+20h] BYREF

  try
  {
    if ( Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    {
      pv = 0;
      LOBYTE(v1) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
        v1);
      v4 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>>((struct wil::details::IFailureCallback *)v69)
                                       + 56);
      v5 = pv;
      pv = (LPVOID)v4;
      if ( v4 )
        _InterlockedIncrement(v4 + 70);
      if ( v5 )
        tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>::Release(v5);
      tip2::test_watcher<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>::~test_watcher<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>(v69);
      LOBYTE(v6) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl'::`2'::impl,
        v6);
      if ( (unsigned __int8)IsCAMStorageAccessCheckPresent() )
        DoCAMStorageDatabaseMaintenance();
      p_pv = &pv;
      v64 = 1;
      wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v73);
      LOBYTE(v75) = 0;
      UnbiasedTime = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v65 = UnbiasedTime;
      NumRowsInUsageHistoryTable = Windows::Internal::CapabilityAccess::Private::SQL::GetNumRowsInUsageHistoryTable(v7);
      CAMDatabaseSizeInBytes = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseSizeInBytes(v8);
      NumAppsInHistoryTable = Windows::Internal::CapabilityAccess::Private::SQL::GetNumAppsInHistoryTable(v9);
      v69[0] = v73;
      v69[1] = &v75;
      v69[2] = &v65;
      v69[3] = &NumRowsInUsageHistoryTable;
      v69[4] = &NumAppsInHistoryTable;
      v69[5] = &CAMDatabaseSizeInBytes;
      v70 = 1;
      std::make_shared<StateRepository::Database,>(&v60);
      v62[0] = 699776354;
      v62[1] = 1135222249;
      v62[2] = -1858443131;
      v62[3] = 2107382305;
      v10 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v71,
              &v60);
      Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(v72, v10, v62, 1);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl'::`2'::impl) )
        goto LABEL_16;
      LODWORD(UnbiasedTime) = 0;
      RuntimeTargetSchemaVersion = Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion();
      Pragma = StateRepository::Database::GetPragma(v60, "user_version", (int *)&UnbiasedTime);
      v11 = retaddr;
      if ( Pragma < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7F,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)Pragma,
          (int)v60);
      if ( (_DWORD)UnbiasedTime == RuntimeTargetSchemaVersion )
      {
LABEL_16:
        ExpirationPolicyInDays = Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(v11);
        SystemTimeAsUInt64 = Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(v15);
        v77 = 0;
        v17 = StateRepository::Database::PrepareFromCache(
                v60,
                "DELETE FROM NonPackagedUsageHistory WHERE LastUsedTimeStop<?;",
                (struct StateRepository::Statement *)&v77);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF1D,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v17,
            (int)v60);
        v18 = SystemTimeAsUInt64 - 864000000000LL * ExpirationPolicyInDays;
        v19 = StateRepository::Statement::Bind((StateRepository::Statement *)&v77, 1, v18);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF1E,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v19,
            (int)v60);
        NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v77);
        if ( NoRow < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF1F,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)NoRow,
            (int)v60);
        v21 = StateRepository::Database::PrepareFromCache(
                v60,
                "DELETE FROM PackagedUsageHistory WHERE LastUsedTimeStop<?;",
                (struct StateRepository::Statement *)&v77);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF21,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v21,
            (int)v60);
        v22 = StateRepository::Statement::Bind((StateRepository::Statement *)&v77, 1, v18);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF22,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v22,
            (int)v60);
        v23 = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v77);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF23,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v23,
            (int)v60);
        v26 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM PackageFamilyNames WHERE ID NOT IN (SELECT DISTINCT PackageFamilyName FROM PackagedUsageHistory); ",
                v24,
                v25);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF2B,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v26,
            (int)v60);
        v29 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM FileIDs WHERE ID NOT IN (SELECT DISTINCT FileID FROM NonPackagedUsageHistory UNION SELECT DI"
                "STINCT FileID FROM NonPackagedGlobalPromptHistory);",
                v27,
                v28);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF2C,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v29,
            (int)v60);
        v32 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM NonPackagedIdentityRelationship WHERE FileID NOT IN (SELECT DISTINCT ID FROM FileIDs);",
                v30,
                v31);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF2D,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v32,
            (int)v60);
        v35 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM ProgramIDs WHERE ID NOT IN (SELECT DISTINCT ProgramID FROM NonPackagedUsageHistory UNION SEL"
                "ECT DISTINCT ProgramID FROM NonPackagedIdentityRelationship UNION SELECT DISTINCT ProgramID FROM NonPack"
                "agedGlobalPromptHistory);",
                v33,
                v34);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF2E,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v35,
            (int)v60);
        v38 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM BinaryFullPaths WHERE ID NOT IN (SELECT DISTINCT BinaryFullPath FROM NonPackagedUsageHistory"
                " UNION SELECT DISTINCT BinaryFullPath FROM NonPackagedIdentityRelationship);",
                v36,
                v37);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF2F,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v38,
            (int)v60);
        v41 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM Users WHERE ID NOT IN (SELECT DISTINCT UserSid FROM PackagedUsageHistory UNION SELECT DISTIN"
                "CT UserSid FROM NonPackagedUsageHistory UNION SELECT DISTINCT UserSid FROM NonPackagedGlobalPromptHistory);",
                v39,
                v40);
        if ( v41 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF30,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v41,
            (int)v60);
        v44 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM Capabilities WHERE ID NOT IN (SELECT DISTINCT Capability FROM PackagedUsageHistory UNION SEL"
                "ECT DISTINCT Capability FROM NonPackagedUsageHistory UNION SELECT DISTINCT Capability FROM NonPackagedGl"
                "obalPromptHistory);",
                v42,
                v43);
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF31,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v44,
            (int)v60);
        v47 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM AccessGUIDs WHERE ID NOT IN (SELECT DISTINCT AccessGUID FROM PackagedUsageHistory UNION SELE"
                "CT DISTINCT AccessGUID FROM NonPackagedUsageHistory);",
                v45,
                v46);
        if ( v47 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF32,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v47,
            (int)v60);
        v50 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM AppNames WHERE ID NOT IN (SELECT DISTINCT AppName FROM PackagedUsageHistory UNION SELECT DIS"
                "TINCT AppName FROM NonPackagedUsageHistory);",
                v48,
                v49);
        if ( v50 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF33,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v50,
            (int)v60);
        v53 = StateRepository::Database::Execute(
                v60,
                "DELETE FROM ServiceNames WHERE ID NOT IN (SELECT DISTINCT ServiceName FROM NonPackagedUsageHistory);",
                v51,
                v52);
        if ( v53 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF34,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v53,
            (int)v60);
        v56 = StateRepository::Database::Execute(v60, "PRAGMA optimize;", v54, v55);
        if ( v56 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF35,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)(unsigned int)v56,
            (int)v60);
        Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v72);
        LOBYTE(v75) = 1;
        LOBYTE(v57) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
          v57);
        v58 = v75;
        v59 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>::ensure_data(&pv);
        UnbiasedTime = v59;
        if ( v59 )
          _InterlockedIncrement((volatile signed __int32 *)(v59 + 280));
        tip2::details::shared_data<1,0,0>::begin_update(v59 + 8);
        *(_BYTE *)(v59 + 272) = v58;
        tip2::test_data_control<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>::~test_data_control<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>(&UnbiasedTime);
        StateRepository::Statement::~Statement((StateRepository::Statement *)&v77);
        Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v72);
        if ( v61 )
          std::_Ref_count_base::_Decref(v61);
      }
      else
      {
        Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v72);
        if ( v61 )
          std::_Ref_count_base::_Decref(v61);
      }
      v70 = 0;
      lambda_aa05cf6f2ed078acf18449aeda8ebdf1_::operator()(v69);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v73);
      v64 = 0;
      lambda_043bf680549d25ee91a6592b2c9e0840_::operator()(&p_pv);
      wil::com_ptr_t<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>,wil::err_returncode_policy>(&pv);
      result = 0;
    }
    else
    {
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF4A,
                           (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180049948  push    rbx
0x18004994a  push    rdi
0x18004994b  sub     rsp, 1D8h
0x180049952  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180049957  test    al, al
0x180049959  jnz     short loc_180049962
0x18004995b  xor     eax, eax
0x18004995d  jmp     loc_180049EFF
0x180049962  mov     [rsp+1E8h+pv], 0
0x18004996e  mov     dl, 1
0x180049970  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se> `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl(void)'::`2'::impl
0x180049977  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004997c  lea     rcx, [rsp+1E8h+var_178]; struct wil::details::IFailureCallback *
0x180049981  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180049986  mov     rcx, [rax+38h]
0x18004998a  mov     rax, [rsp+1E8h+pv]
0x180049992  mov     [rsp+1E8h+pv], rcx
0x18004999a  test    rcx, rcx
0x18004999d  jz      short loc_1800499A6
0x18004999f  lock inc dword ptr [rcx+118h]
0x1800499a6  test    rax, rax
0x1800499a9  jz      short loc_1800499B3
0x1800499ab  mov     rcx, rax; pv
0x1800499ae  call    ?Release@?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>::Release(void)
0x1800499b3  lea     rcx, [rsp+1E8h+var_178]
0x1800499b8  call    ??1?$test_watcher@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>::~test_watcher<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>(void)
0x1800499bd  mov     dl, 1
0x1800499bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase> `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl(void)'::`2'::impl
0x1800499c6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800499cb  call    IsCAMStorageAccessCheckPresent
0x1800499d0  test    al, al
0x1800499d2  jz      short loc_1800499DA
0x1800499d4  call    cs:__imp_DoCAMStorageDatabaseMaintenance
0x1800499da  lea     rax, [rsp+1E8h+pv]
0x1800499e2  mov     [rsp+1E8h+var_1A8], rax
0x1800499e7  mov     [rsp+1E8h+var_1A0], 1
0x1800499ec  lea     rcx, [rsp+1E8h+var_F8]; this
0x1800499f4  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x1800499f9  nop
0x1800499fa  mov     byte ptr [rsp+1E8h+arg_0], 0
0x180049a02  mov     [rsp+1E8h+UnbiasedTime], 0
0x180049a0e  lea     rcx, [rsp+1E8h+UnbiasedTime]; UnbiasedTime
0x180049a16  call    cs:__imp_QueryUnbiasedInterruptTime
0x180049a1c  mov     rax, [rsp+1E8h+UnbiasedTime]
0x180049a24  mov     [rsp+1E8h+var_198], rax
0x180049a29  call    ?GetNumRowsInUsageHistoryTable@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetNumRowsInUsageHistoryTable(void)
0x180049a2e  mov     [rsp+1E8h+var_190], rax
0x180049a33  call    ?GetCAMDatabaseSizeInBytes@SQL@Private@CapabilityAccess@Internal@Windows@@YA_JXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseSizeInBytes(void)
0x180049a38  mov     [rsp+1E8h+var_180], rax
0x180049a3d  call    ?GetNumAppsInHistoryTable@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetNumAppsInHistoryTable(void)
0x180049a42  mov     [rsp+1E8h+var_188], rax
0x180049a47  lea     rax, [rsp+1E8h+var_F8]
0x180049a4f  mov     [rsp+1E8h+var_178], rax
0x180049a54  lea     rax, [rsp+1E8h+arg_0]
0x180049a5c  mov     [rsp+1E8h+var_170], rax
0x180049a61  lea     rax, [rsp+1E8h+var_198]
0x180049a66  mov     [rsp+1E8h+var_168], rax
0x180049a6e  lea     rax, [rsp+1E8h+var_190]
0x180049a73  mov     [rsp+1E8h+var_160], rax
0x180049a7b  lea     rax, [rsp+1E8h+var_188]
0x180049a80  mov     [rsp+1E8h+var_158], rax
0x180049a88  lea     rax, [rsp+1E8h+var_180]
0x180049a8d  mov     [rsp+1E8h+var_150], rax
0x180049a95  mov     [rsp+1E8h+var_148], 1
0x180049a9d  lea     rcx, [rsp+1E8h+var_1C8]
0x180049aa2  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180049aa7  nop
0x180049aa8  mov     [rsp+1E8h+var_1B8], 29B5BD62h
0x180049ab0  mov     [rsp+1E8h+var_1B4], 43AA1DE9h
0x180049ab8  mov     [rsp+1E8h+var_1B0], 913A6885h
0x180049ac0  mov     [rsp+1E8h+var_1AC], 7D9C1A21h
0x180049ac8  lea     rdx, [rsp+1E8h+var_1C8]
0x180049acd  lea     rcx, [rsp+1E8h+var_138]
0x180049ad5  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180049ada  mov     r9d, 1
0x180049ae0  lea     r8, [rsp+1E8h+var_1B8]
0x180049ae5  mov     rdx, rax
0x180049ae8  lea     rcx, [rsp+1E8h+var_128]
0x180049af0  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180049af5  nop
0x180049af6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload> `wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl(void)'::`2'::impl
0x180049afd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(void)
0x180049b02  test    al, al
0x180049b04  jz      loc_180049BB1
0x180049b0a  mov     dword ptr [rsp+1E8h+UnbiasedTime], 0
0x180049b15  call    ?GetRuntimeTargetSchemaVersion@UsageDatabaseManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAHXZ; Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion(void)
0x180049b1a  mov     ebx, eax
0x180049b1c  lea     r8, [rsp+1E8h+UnbiasedTime]; int *
0x180049b24  lea     rdx, aUserVersion; "user_version"
0x180049b2b  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049b30  call    ?GetPragma@Database@StateRepository@@QEAAJPEBDPEAH@Z; StateRepository::Database::GetPragma(char const *,int *)
0x180049b35  mov     rcx, [rsp+1E8h]; this
0x180049b3d  test    eax, eax
0x180049b3f  js      loc_180049F09
0x180049b45  cmp     dword ptr [rsp+1E8h+UnbiasedTime], ebx
0x180049b4c  jz      short loc_180049BB1
0x180049b4e  lea     rcx, [rsp+1E8h+var_128]; this
0x180049b56  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x180049b5b  nop
0x180049b5c  mov     rcx, [rsp+1E8h+var_1C0]; this
0x180049b61  test    rcx, rcx
0x180049b64  jz      short loc_180049B6C
0x180049b66  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049b6b  nop
0x180049b6c  mov     [rsp+1E8h+var_148], 0
0x180049b74  lea     rcx, [rsp+1E8h+var_178]
0x180049b79  call    _lambda_aa05cf6f2ed078acf18449aeda8ebdf1___operator__
0x180049b7e  nop
0x180049b7f  lea     rcx, [rsp+1E8h+var_F8]; this
0x180049b87  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180049b8c  nop
0x180049b8d  mov     [rsp+1E8h+var_1A0], 0
0x180049b92  lea     rcx, [rsp+1E8h+var_1A8]
0x180049b97  call    _lambda_043bf680549d25ee91a6592b2c9e0840___operator__
0x180049b9c  nop
0x180049b9d  lea     rcx, [rsp+1E8h+pv]
0x180049ba5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>,wil::err_returncode_policy>(void)
0x180049baa  xor     eax, eax
0x180049bac  jmp     loc_180049EFF
0x180049bb1  call    ?GetExpirationPolicyInDays@SQL@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(void)
0x180049bb6  mov     edi, eax
0x180049bb8  call    ?GetSystemTimeAsUInt64@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(void)
0x180049bbd  mov     rbx, rax
0x180049bc0  mov     [rsp+1E8h+arg_10], 0
0x180049bcc  lea     r8, [rsp+1E8h+arg_10]; struct StateRepository::Statement *
0x180049bd4  lea     rdx, aDeleteFromNonp_0; "DELETE FROM NonPackagedUsageHistory WHE"...
0x180049bdb  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049be0  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180049be5  mov     rcx, [rsp+1E8h]; this
0x180049bed  test    eax, eax
0x180049bef  js      loc_180049F1E
0x180049bf5  imul    ecx, edi, 5A0h
0x180049bfb  imul    rax, rcx, 23C34600h
0x180049c02  sub     rbx, rax
0x180049c05  mov     r8, rbx; __int64
0x180049c08  mov     edx, 1; int
0x180049c0d  lea     rcx, [rsp+1E8h+arg_10]; this
0x180049c15  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180049c1a  mov     rcx, [rsp+1E8h]; this
0x180049c22  test    eax, eax
0x180049c24  js      loc_180049F32
0x180049c2a  lea     rcx, [rsp+1E8h+arg_10]; this
0x180049c32  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180049c37  mov     rcx, [rsp+1E8h]; this
0x180049c3f  test    eax, eax
0x180049c41  js      loc_180049F46
0x180049c47  lea     r8, [rsp+1E8h+arg_10]; struct StateRepository::Statement *
0x180049c4f  lea     rdx, aDeleteFromPack_0; "DELETE FROM PackagedUsageHistory WHERE "...
0x180049c56  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049c5b  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180049c60  mov     rcx, [rsp+1E8h]; this
0x180049c68  test    eax, eax
0x180049c6a  js      loc_180049F5A
0x180049c70  mov     r8, rbx; __int64
0x180049c73  mov     edx, 1; int
0x180049c78  lea     rcx, [rsp+1E8h+arg_10]; this
0x180049c80  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180049c85  mov     rcx, [rsp+1E8h]; this
0x180049c8d  test    eax, eax
0x180049c8f  js      loc_180049F6E
0x180049c95  lea     rcx, [rsp+1E8h+arg_10]; this
0x180049c9d  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180049ca2  mov     rcx, [rsp+1E8h]; this
0x180049caa  test    eax, eax
0x180049cac  js      loc_180049F82
0x180049cb2  lea     rdx, aDeleteFromPack; "DELETE FROM PackageFamilyNames WHERE ID"...
0x180049cb9  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049cbe  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049cc3  mov     rcx, [rsp+1E8h]; this
0x180049ccb  test    eax, eax
0x180049ccd  js      loc_180049F96
0x180049cd3  lea     rdx, aDeleteFromFile; "DELETE FROM FileIDs WHERE ID NOT IN (SE"...
0x180049cda  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049cdf  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049ce4  mov     rcx, [rsp+1E8h]; this
0x180049cec  test    eax, eax
0x180049cee  js      loc_180049FAA
0x180049cf4  lea     rdx, aDeleteFromNonp; "DELETE FROM NonPackagedIdentityRelation"...
0x180049cfb  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049d00  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049d05  mov     rcx, [rsp+1E8h]; this
0x180049d0d  test    eax, eax
0x180049d0f  js      loc_180049FBE
0x180049d15  lea     rdx, aDeleteFromProg; "DELETE FROM ProgramIDs WHERE ID NOT IN "...
0x180049d1c  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049d21  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049d26  mov     rcx, [rsp+1E8h]; this
0x180049d2e  test    eax, eax
0x180049d30  js      loc_180049FD2
0x180049d36  lea     rdx, aDeleteFromBina; "DELETE FROM BinaryFullPaths WHERE ID NO"...
0x180049d3d  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049d42  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049d47  mov     rcx, [rsp+1E8h]; this
0x180049d4f  test    eax, eax
0x180049d51  js      loc_180049FE6
0x180049d57  lea     rdx, aDeleteFromUser; "DELETE FROM Users WHERE ID NOT IN (SELE"...
0x180049d5e  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049d63  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049d68  mov     rcx, [rsp+1E8h]; this
0x180049d70  test    eax, eax
0x180049d72  js      loc_180049FFA
0x180049d78  lea     rdx, aDeleteFromCapa; "DELETE FROM Capabilities WHERE ID NOT I"...
0x180049d7f  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049d84  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049d89  mov     rcx, [rsp+1E8h]; this
0x180049d91  test    eax, eax
0x180049d93  js      loc_18004A00E
0x180049d99  lea     rdx, aDeleteFromAcce; "DELETE FROM AccessGUIDs WHERE ID NOT IN"...
0x180049da0  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049da5  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049daa  mov     rcx, [rsp+1E8h]; this
0x180049db2  test    eax, eax
0x180049db4  js      loc_18004A022
0x180049dba  lea     rdx, aDeleteFromAppn; "DELETE FROM AppNames WHERE ID NOT IN (S"...
0x180049dc1  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049dc6  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049dcb  mov     rcx, [rsp+1E8h]; this
0x180049dd3  test    eax, eax
0x180049dd5  js      loc_18004A036
0x180049ddb  lea     rdx, aDeleteFromServ; "DELETE FROM ServiceNames WHERE ID NOT I"...
0x180049de2  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049de7  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049dec  mov     rcx, [rsp+1E8h]; this
0x180049df4  test    eax, eax
0x180049df6  js      loc_18004A04A
0x180049dfc  lea     rdx, aPragmaOptimize; "PRAGMA optimize;"
0x180049e03  mov     rcx, [rsp+1E8h+var_1C8]; this
0x180049e08  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180049e0d  mov     rcx, [rsp+1E8h]; this
0x180049e15  test    eax, eax
0x180049e17  js      loc_18004A05E
0x180049e1d  lea     rcx, [rsp+1E8h+var_128]; this
0x180049e25  call    ?CommitTransaction@DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction(void)
0x180049e2a  mov     byte ptr [rsp+1E8h+arg_0], 1
0x180049e32  mov     dl, 1
0x180049e34  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se> `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl(void)'::`2'::impl
0x180049e3b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180049e40  mov     dil, byte ptr [rsp+1E8h+arg_0]
0x180049e48  lea     rcx, [rsp+1E8h+pv]
0x180049e50  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>::ensure_data(void)
0x180049e55  mov     rbx, [rax]
0x180049e58  mov     [rsp+1E8h+UnbiasedTime], rbx
0x180049e60  test    rbx, rbx
0x180049e63  jz      short loc_180049E6C
0x180049e65  lock inc dword ptr [rbx+118h]
0x180049e6c  lea     rcx, [rbx+8]
0x180049e70  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180049e75  mov     [rbx+110h], dil
0x180049e7c  lea     rcx, [rsp+1E8h+UnbiasedTime]
0x180049e84  call    ??1?$test_data_control@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>::~test_data_control<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>>(void)
0x180049e89  nop
0x180049e8a  lea     rcx, [rsp+1E8h+arg_10]; this
0x180049e92  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180049e97  nop
0x180049e98  lea     rcx, [rsp+1E8h+var_128]; this
0x180049ea0  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x180049ea5  nop
0x180049ea6  mov     rcx, [rsp+1E8h+var_1C0]; this
0x180049eab  test    rcx, rcx
0x180049eae  jz      short loc_180049EB6
0x180049eb0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049eb5  nop
0x180049eb6  mov     [rsp+1E8h+var_148], 0
0x180049ebe  lea     rcx, [rsp+1E8h+var_178]
0x180049ec3  call    _lambda_aa05cf6f2ed078acf18449aeda8ebdf1___operator__
0x180049ec8  nop
0x180049ec9  lea     rcx, [rsp+1E8h+var_F8]; this
0x180049ed1  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180049ed6  nop
0x180049ed7  mov     [rsp+1E8h+var_1A0], 0
0x180049edc  lea     rcx, [rsp+1E8h+var_1A8]
0x180049ee1  call    _lambda_043bf680549d25ee91a6592b2c9e0840___operator__
0x180049ee6  nop
0x180049ee7  lea     rcx, [rsp+1E8h+pv]
0x180049eef  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMDatabaseMaintenanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMDatabaseMaintenanceTest,_tip_CAMDatabaseMaintenanceTest>,wil::err_returncode_policy>(void)
0x180049ef4  xor     eax, eax
0x180049ef6  jmp     short loc_180049EFF
0x180049ef8  mov     eax, [rsp+1E8h+arg_0]
0x180049eff  add     rsp, 1D8h
0x180049f06  pop     rdi
0x180049f07  pop     rbx
0x180049f08  retn
0x180049f09  mov     r9d, eax; char *
0x180049f0c  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180049f13  mov     edx, 0D7Fh; void *
0x180049f18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049f1e  mov     r9d, eax; char *
0x180049f21  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180049f28  mov     edx, 0F1Dh; void *
0x180049f2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049f32  mov     r9d, eax; char *
0x180049f35  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180049f3c  mov     edx, 0F1Eh; void *
0x180049f41  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049f46  mov     r9d, eax; char *
0x180049f49  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180049f50  mov     edx, 0F1Fh; void *
0x180049f55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049f5a  mov     r9d, eax; char *
0x180049f5d  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
  ... truncated ...
```
