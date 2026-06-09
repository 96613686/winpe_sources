# Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(void)

- ea: `0x18003121c`
- end: `0x1800314f6`
- name: `?CreateRecordTables@SQL@Private@CapabilityAccess@Internal@Windows@@YAXXZ`
- size: `730`
- prototype: `void __fastcall(Windows::Internal::CapabilityAccess::Private::SQL *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180038df4`
- `0x18004ea1c`

## callees

- `0x18001e118`
- `0x18001e42c`
- `0x180020fcc`
- `0x18002392c`
- `0x18002d638`
- `0x18002e704`
- `0x18002f560`
- `0x18002fab0`
- `0x1800311c4`
- `0x18003121c`
- `0x180037460`
- `0x18003b1a0`
- `0x18003e21c`
- `0x1800a3ef4`
- `0x1800a6080`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003128b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003128b`

## string_xrefs

- `0x18003147b`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031490`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800314a5`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800314ba`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800314cf`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800314e4`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031378`: `CREATE TABLE IF NOT EXISTS NonPackagedGlobalPromptHistory(ID INTEGER PRIMARY KEY NOT NULL,ShownTime INTEGER NOT NULL,Capability INTEGER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,UserSid INTEGER NOT NULL);`
- `0x180031398`: `CREATE TABLE IF NOT EXISTS NonPackagedGlobalPromptHistory(ID INTEGER PRIMARY KEY NOT NULL,ShownTime INTEGER NOT NULL,Capability INTEGER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,UserSid INTEGER NOT NULL);`
- `0x180031358`: `CREATE TABLE IF NOT EXISTS NonPackagedIdentityRelationship(ID INTEGER PRIMARY KEY NOT NULL,BinaryFullPath INTEGER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,LastObservedTime INTEGER NOT NULL);`
- `0x180031338`: `CREATE TABLE IF NOT EXISTS PackagedUsageHistory(ID INTEGER PRIMARY KEY NOT NULL,LastUsedTimeStart INTEGER NOT NULL,LastUsedTimeStop INTEGER NOT NULL,AccessBlocked INTEGER NOT NULL,Capability INTEGER NOT NULL,PackageFamilyName INTEGER NOT NULL,UserSid INTEGER NOT NULL,AccessGUID INTEGER NOT NULL,Label INTEGER NOT NULL,AppName INTEGER NOT NULL);`
- `0x180031318`: `CREATE TABLE IF NOT EXISTS NonPackagedUsageHistory(ID INTEGER PRIMARY KEY NOT NULL,LastUsedTimeStart INTEGER NOT NULL,LastUsedTimeStop INTEGER NOT NULL,AccessBlocked INTEGER NOT NULL,Capability INTEGER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,BinaryFullPath INTEGER NOT NULL,UserSid INTEGER NOT NULL,AppName INTEGER NOT NULL,ServiceName INTEGER NOT NULL DEFAULT '0',AccessGUID INTEGER NOT NULL,Label INTEGER NOT NULL);`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(
        Windows::Internal::CapabilityAccess::Private::SQL *this)
{
  __int64 v1; // rax
  int (*v2)(void *); // r8
  void *v3; // r9
  int v4; // eax
  int (*v5)(void *); // r8
  void *v6; // r9
  int v7; // eax
  int (*v8)(void *); // r8
  void *v9; // r9
  int v10; // eax
  int (*v11)(void *); // r8
  void *v12; // r9
  int v13; // eax
  int (*v14)(void *); // r8
  void *v15; // r9
  int v16; // eax
  int v17; // eax
  int v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  StateRepository::Database *v19; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v20; // [rsp+38h] [rbp-C8h]
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[224]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  char v27; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int64 v29; // [rsp+1A0h] [rbp+A0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids, 1537);
  }
  v27 = 0;
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v25);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v29 = UnbiasedTime;
  v21[0] = v25;
  v21[1] = &v29;
  v21[2] = &v27;
  v22 = 1;
  std::make_shared<StateRepository::Database,>(&v19);
  v18[0] = -1606430041;
  v18[1] = 1211908259;
  v18[2] = -704725576;
  v18[3] = 1190996144;
  v1 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
         v23,
         &v19);
  Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(v24, v1, v18, 7);
  v4 = StateRepository::Database::Execute(
         v19,
         "CREATE TABLE IF NOT EXISTS NonPackagedUsageHistory(ID INTEGER PRIMARY KEY NOT NULL,LastUsedTimeStart INTEGER NO"
         "T NULL,LastUsedTimeStop INTEGER NOT NULL,AccessBlocked INTEGER NOT NULL,Capability INTEGER NOT NULL,FileID INTE"
         "GER NOT NULL,ProgramID INTEGER NOT NULL,BinaryFullPath INTEGER NOT NULL,UserSid INTEGER NOT NULL,AppName INTEGE"
         "R NOT NULL,ServiceName INTEGER NOT NULL DEFAULT '0',AccessGUID INTEGER NOT NULL,Label INTEGER NOT NULL);",
         v2,
         v3);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xADF,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v4,
      v18[0]);
  v7 = StateRepository::Database::Execute(
         v19,
         "CREATE TABLE IF NOT EXISTS PackagedUsageHistory(ID INTEGER PRIMARY KEY NOT NULL,LastUsedTimeStart INTEGER NOT N"
         "ULL,LastUsedTimeStop INTEGER NOT NULL,AccessBlocked INTEGER NOT NULL,Capability INTEGER NOT NULL,PackageFamilyN"
         "ame INTEGER NOT NULL,UserSid INTEGER NOT NULL,AccessGUID INTEGER NOT NULL,Label INTEGER NOT NULL,AppName INTEGER NOT NULL);",
         v5,
         v6);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE2,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v7,
      v18[0]);
  v10 = StateRepository::Database::Execute(
          v19,
          "CREATE TABLE IF NOT EXISTS NonPackagedIdentityRelationship(ID INTEGER PRIMARY KEY NOT NULL,BinaryFullPath INTE"
          "GER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,LastObservedTime INTEGER NOT NULL);",
          v8,
          v9);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE6,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v10,
      v18[0]);
  v13 = StateRepository::Database::Execute(
          v19,
          "CREATE TABLE IF NOT EXISTS NonPackagedGlobalPromptHistory(ID INTEGER PRIMARY KEY NOT NULL,ShownTime INTEGER NO"
          "T NULL,Capability INTEGER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,UserSid INTEGER NOT NULL);",
          v11,
          v12);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF0,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v13,
      v18[0]);
  v16 = StateRepository::Database::Execute(
          v19,
          "CREATE TABLE IF NOT EXISTS NonPackagedGlobalPromptHistory(ID INTEGER PRIMARY KEY NOT NULL,ShownTime INTEGER NO"
          "T NULL,Capability INTEGER NOT NULL,FileID INTEGER NOT NULL,ProgramID INTEGER NOT NULL,UserSid INTEGER NOT NULL);",
          v14,
          v15);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF4,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v16,
      v18[0]);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl'::`2'::impl) )
  {
    v17 = StateRepository::Database::SetPragma(v19, "user_version", 1537);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB03,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v17,
        v18[0]);
  }
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v24);
  v27 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids, 1537);
  }
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v24);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  v22 = 0;
  lambda_68e93242627837b1523ef53b40ce6604_::operator()(v21);
  wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v25);
}

```

## disassembly

```asm
0x18003121c  mov     [rsp-8+arg_18], r14
0x180031221  push    rbp
0x180031222  lea     rbp, [rsp-80h]
0x180031227  sub     rsp, 180h
0x18003122e  lea     r14, WPP_GLOBAL_Control
0x180031235  mov     rcx, cs:WPP_GLOBAL_Control
0x18003123c  cmp     rcx, r14
0x18003123f  jz      short loc_180031268
0x180031241  test    byte ptr [rcx+1Ch], 1
0x180031245  jz      short loc_180031268
0x180031247  cmp     byte ptr [rcx+19h], 4
0x18003124b  jb      short loc_180031268
0x18003124d  mov     edx, 13h
0x180031252  mov     r9d, 601h
0x180031258  lea     r8, WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids
0x18003125f  mov     rcx, [rcx+10h]
0x180031263  call    WPP_SF_d
0x180031268  mov     [rbp+80h+arg_0], 0
0x18003126f  lea     rcx, [rbp+80h+var_E0]; this
0x180031273  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x180031278  nop
0x180031279  mov     [rbp+80h+UnbiasedTime], 0
0x180031284  lea     rcx, [rbp+80h+UnbiasedTime]; UnbiasedTime
0x18003128b  call    cs:__imp_QueryUnbiasedInterruptTime
0x180031291  mov     rax, [rbp+80h+UnbiasedTime]
0x180031298  mov     [rbp+80h+arg_10], rax
0x18003129f  lea     rax, [rbp+80h+var_E0]
0x1800312a3  mov     [rsp+180h+var_140], rax
0x1800312a8  lea     rax, [rbp+80h+arg_10]
0x1800312af  mov     [rsp+180h+var_138], rax
0x1800312b4  lea     rax, [rbp+80h+arg_0]
0x1800312bb  mov     [rsp+180h+var_130], rax
0x1800312c0  mov     [rsp+180h+var_128], 1
0x1800312c5  lea     rcx, [rsp+180h+var_150]
0x1800312ca  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x1800312cf  nop
0x1800312d0  mov     [rsp+180h+var_160], 0A03FD2A7h; int
0x1800312d8  mov     [rsp+180h+var_15C], 483C40A3h
0x1800312e0  mov     [rsp+180h+var_158], 0D5FEBDB8h
0x1800312e8  mov     [rsp+180h+var_154], 46FD28B0h
0x1800312f0  lea     rdx, [rsp+180h+var_150]
0x1800312f5  lea     rcx, [rsp+180h+var_120]
0x1800312fa  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800312ff  mov     r9d, 7
0x180031305  lea     r8, [rsp+180h+var_160]
0x18003130a  mov     rdx, rax
0x18003130d  lea     rcx, [rsp+180h+var_110]
0x180031312  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180031317  nop
0x180031318  lea     rdx, aCreateTableIfN_4; "CREATE TABLE IF NOT EXISTS NonPackagedU"...
0x18003131f  mov     rcx, [rsp+180h+var_150]; this
0x180031324  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180031329  mov     rcx, [rbp+88h]; this
0x180031330  test    eax, eax
0x180031332  js      loc_18003148D
0x180031338  lea     rdx, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS PackagedUsag"...
0x18003133f  mov     rcx, [rsp+180h+var_150]; this
0x180031344  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180031349  mov     rcx, [rbp+88h]; this
0x180031350  test    eax, eax
0x180031352  js      loc_1800314A2
0x180031358  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS NonPackagedI"...
0x18003135f  mov     rcx, [rsp+180h+var_150]; this
0x180031364  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180031369  mov     rcx, [rbp+88h]; this
0x180031370  test    eax, eax
0x180031372  js      loc_1800314B7
0x180031378  lea     rdx, aCreateTableIfN_3; "CREATE TABLE IF NOT EXISTS NonPackagedG"...
0x18003137f  mov     rcx, [rsp+180h+var_150]; this
0x180031384  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180031389  mov     rcx, [rbp+88h]; this
0x180031390  test    eax, eax
0x180031392  js      loc_1800314CC
0x180031398  lea     rdx, aCreateTableIfN_3; "CREATE TABLE IF NOT EXISTS NonPackagedG"...
0x18003139f  mov     rcx, [rsp+180h+var_150]; this
0x1800313a4  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800313a9  mov     rcx, [rbp+88h]; this
0x1800313b0  test    eax, eax
0x1800313b2  js      loc_1800314E1
0x1800313b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload> `wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl(void)'::`2'::impl
0x1800313bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(void)
0x1800313c4  test    al, al
0x1800313c6  jnz     short loc_1800313EE
0x1800313c8  mov     r8d, 601h; __int64
0x1800313ce  lea     rdx, aUserVersion; "user_version"
0x1800313d5  mov     rcx, [rsp+180h+var_150]; this
0x1800313da  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x1800313df  mov     rcx, [rbp+88h]; this
0x1800313e6  test    eax, eax
0x1800313e8  js      loc_180031478
0x1800313ee  lea     rcx, [rsp+180h+var_110]; this
0x1800313f3  call    ?CommitTransaction@DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction(void)
0x1800313f8  mov     [rbp+80h+arg_0], 1
0x1800313ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180031406  cmp     rcx, r14
0x180031409  jz      short loc_180031433
0x18003140b  test    byte ptr [rcx+1Ch], 1
0x18003140f  jz      short loc_180031433
0x180031411  cmp     byte ptr [rcx+19h], 4
0x180031415  jb      short loc_180031433
0x180031417  mov     edx, 14h
0x18003141c  mov     r9d, 601h
0x180031422  lea     r8, WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids
0x180031429  mov     rcx, [rcx+10h]
0x18003142d  call    WPP_SF_d
0x180031432  nop
0x180031433  lea     rcx, [rsp+180h+var_110]; this
0x180031438  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x18003143d  nop
0x18003143e  mov     rcx, [rsp+180h+var_148]; this
0x180031443  test    rcx, rcx
0x180031446  jz      short loc_18003144E
0x180031448  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003144d  nop
0x18003144e  mov     [rsp+180h+var_128], 0
0x180031453  lea     rcx, [rsp+180h+var_140]
0x180031458  call    _lambda_68e93242627837b1523ef53b40ce6604___operator__
0x18003145d  nop
0x18003145e  lea     rcx, [rbp+80h+var_E0]; this
0x180031462  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180031467  mov     r14, [rsp+180h+arg_18]
0x18003146f  add     rsp, 180h
0x180031476  pop     rbp
0x180031477  retn
0x180031478  mov     r9d, eax; char *
0x18003147b  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031482  mov     edx, 0B03h; void *
0x180031487  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003148d  mov     r9d, eax; char *
0x180031490  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031497  mov     edx, 0ADFh; void *
0x18003149c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314a2  mov     r9d, eax; char *
0x1800314a5  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800314ac  mov     edx, 0AE2h; void *
0x1800314b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314b7  mov     r9d, eax; char *
0x1800314ba  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800314c1  mov     edx, 0AE6h; void *
0x1800314c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314cc  mov     r9d, eax; char *
0x1800314cf  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800314d6  mov     edx, 0AF0h; void *
0x1800314db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800314e1  mov     r9d, eax; char *
0x1800314e4  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800314eb  mov     edx, 0AF4h; void *
0x1800314f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
