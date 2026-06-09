# Windows::Internal::CapabilityAccess::Private::SQL::QueryAppList(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::UsageHistory::AppType)

- ea: `0x180037690`
- end: `0x18003809a`
- name: `?QueryAppList@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@UInternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UInternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0W4AppType@UsageHistory@345@@Z`
- size: `2570`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180088030`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001c3b4`
- `0x18001e0e8`
- `0x18001e1f8`
- `0x18001e254`
- `0x18001f5f4`
- `0x180020fcc`
- `0x18002392c`
- `0x18002b55c`
- `0x18002d070`
- `0x18002d1b0`
- `0x18002d1f8`
- `0x18002d234`
- `0x18002d638`
- `0x18002e704`
- `0x18002e9dc`
- `0x18002f560`
- `0x18002f5f4`
- `0x18002f93c`
- `0x180031698`
- `0x1800352d0`
- `0x1800363b4`
- `0x180036e4c`
- `0x180037460`
- `0x180037690`
- `0x18003afa0`
- `0x18003f904`
- `0x180042514`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a5520`

## string_xrefs

- `0x180037eb4`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037ec9`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037ede`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037ef6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f0e`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f23`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f38`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f4d`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f62`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f77`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037f8c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037fa1`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037fb6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037fcb`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037fe0`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037ff5`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003800a`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003801f`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180038034`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180038049`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003805e`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180038073`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180038088`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180037c7d`: `SELECT DISTINCT PackageFamilyName FROM PackagedUsageHistory WHERE PackageFamilyName!=0 AND Capability=? AND (UserSid=? OR UserSid=0);`
- `0x180037c3f`: `SELECT DISTINCT PackageFamilyName FROM PackagedUsageHistory WHERE PackageFamilyName!=0 AND (UserSid=? OR UserSid=0);`
- `0x180037ac7`: `BinaryFullPaths`
- `0x18003794c`: `SELECT MAX(LastObservedTime), ProgramID, BinaryFullPath FROM NonPackagedIdentityRelationship  WHERE FileID=?;`
- `0x18003783d`: `SELECT DISTINCT FileID FROM NonPackagedUsageHistory WHERE FileID!=0 AND Capability=? AND (UserSid=? OR UserSid=0);`
- `0x1800377ff`: `SELECT DISTINCT FileID FROM NonPackagedUsageHistory WHERE FileID!=0 AND (UserSid=? OR UserSid=0);`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
Windows::Internal::CapabilityAccess::Private::SQL *__fastcall Windows::Internal::CapabilityAccess::Private::SQL::QueryAppList(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  int v4; // r14d
  Windows::Internal::CapabilityAccess::Private::SQL *v8; // rcx
  __int64 v9; // rax
  __int64 KeyFromStringAndTableName; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r13
  StateRepository::Database *v14; // rdi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int Row; // eax
  int ColumnUInt64; // eax
  int v22; // eax
  __int64 *v23; // r15
  __int64 *i; // r14
  unsigned __int128 v25; // kr00_16
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  int v33; // eax
  _QWORD *v34; // rbx
  _QWORD *v35; // r15
  __int64 v36; // rax
  __int64 StringFromKeyAndTableName; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // r15
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  _QWORD *j; // rdi
  _QWORD *v52; // r14
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rbx
  bool v57[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v58; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v59; // [rsp+30h] [rbp-D0h] BYREF
  int v60; // [rsp+38h] [rbp-C8h]
  int v61; // [rsp+3Ch] [rbp-C4h]
  unsigned __int64 v62; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v63; // [rsp+48h] [rbp-B8h] BYREF
  StateRepository::Database *v64; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v65; // [rsp+58h] [rbp-A8h]
  __int128 v66; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v67; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+78h] [rbp-88h]
  int v69; // [rsp+7Ch] [rbp-84h]
  __int64 *v70; // [rsp+80h] [rbp-80h]
  __int64 v71; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int128 v72; // [rsp+90h] [rbp-70h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h]
  _QWORD v74[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v75[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v76[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v77; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v78; // [rsp+E8h] [rbp-18h]
  Windows::Internal::CapabilityAccess::Private::SQL *v79; // [rsp+F0h] [rbp-10h]
  char v80[16]; // [rsp+F8h] [rbp-8h] BYREF
  char v81[24]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v82[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v83[48]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v84[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v85[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v86[128]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v87[32]; // [rsp+250h] [rbp+150h] BYREF
  char v88[64]; // [rsp+270h] [rbp+170h] BYREF
  int v89; // [rsp+2B0h] [rbp+1B0h]
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v4 = a4;
  v69 = a4;
  v71 = a2;
  v79 = a1;
  v68 = 1;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      *(int *)v57);
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  v68 = 1;
  if ( Windows::Internal::CapabilityAccess::Private::SQL::HasUserConsentedToUsageDataCollection(v8) )
  {
    std::make_shared<StateRepository::Database,>(&v64);
    v58 = 0;
    v77 = 0;
    v78 = 0;
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v82);
    v59 = 0x4E078FDA6E5265EDLL;
    v60 = 1383663274;
    v61 = 874482165;
    v9 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
           v80,
           &v64);
    Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(v83, v9, &v59, 0);
    if ( *(_QWORD *)(a3 + 16) )
    {
      v11 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v74,
              &v64);
      KeyFromStringAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
                                    a3,
                                    "Capabilities",
                                    v11,
                                    0);
    }
    else
    {
      KeyFromStringAndTableName = 0;
    }
    v59 = KeyFromStringAndTableName;
    v12 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
            v74,
            &v64);
    v13 = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(a2, "Users", v12, 0);
    v14 = v64;
    if ( (v4 & 0xFFFFFFFD) == 0 )
    {
      if ( *(_QWORD *)(a3 + 16) )
      {
        v17 = StateRepository::Database::PrepareFromCache(
                v64,
                "SELECT DISTINCT FileID FROM NonPackagedUsageHistory WHERE FileID!=0 AND Capability=? AND (UserSid=? OR UserSid=0);",
                (struct StateRepository::Statement *)&v58);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E2,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v17,
            *(int *)v57);
        v18 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 1, KeyFromStringAndTableName);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E3,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v18,
            *(int *)v57);
        v19 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 2, v13);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E4,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v19,
            *(int *)v57);
      }
      else
      {
        v15 = StateRepository::Database::PrepareFromCache(
                v64,
                "SELECT DISTINCT FileID FROM NonPackagedUsageHistory WHERE FileID!=0 AND (UserSid=? OR UserSid=0);",
                (struct StateRepository::Statement *)&v58);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2DD,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v15,
            *(int *)v57);
        v16 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 1, v13);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2DE,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v16,
            *(int *)v57);
      }
      v57[0] = 0;
      Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v58, v57);
      if ( Row < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E8,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)Row,
          *(int *)v57);
      v72 = 0;
      v73 = 0;
      while ( v57[0] )
      {
        v62 = 0;
        ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v58, 0, &v62);
        if ( ColumnUInt64 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2F0,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)ColumnUInt64,
            *(int *)v57);
        std::vector<unsigned __int64>::emplace_back<unsigned __int64>(&v72, &v62);
        v22 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v58, v57);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2F3,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v22,
            *(int *)v57);
      }
      StateRepository::Database::AddToCache(v14, (struct StateRepository::Statement *)&v58);
      v23 = (__int64 *)*((_QWORD *)&v72 + 1);
      v25 = v72;
      v70 = (__int64 *)(v25 >> 64);
      for ( i = (__int64 *)v25; i != v23; ++i )
      {
        v57[0] = 0;
        v26 = StateRepository::Database::PrepareFromCache(
                v14,
                "SELECT MAX(LastObservedTime), ProgramID, BinaryFullPath FROM NonPackagedIdentityRelationship  WHERE FileID=?;",
                (struct StateRepository::Statement *)&v58);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2FC,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v26,
            *(int *)v57);
        v27 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 1, *i);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2FE,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v27,
            *(int *)v57);
        v28 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v58, v57);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2FF,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v28,
            *(int *)v57);
        v66 = 0;
        v67 = 0;
        while ( v57[0] )
        {
          v63 = 0;
          v62 = 0;
          v29 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v58, 1, &v63);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x30B,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v29,
              *(int *)v57);
          v30 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v58, 2, &v62);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x30C,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v30,
              *(int *)v57);
          v74[0] = v62;
          v31 = v63;
          v74[1] = v63;
          v32 = *((_QWORD *)&v66 + 1);
          if ( *((_QWORD *)&v66 + 1) == v67 )
          {
            std::vector<std::tuple<unsigned __int64,unsigned __int64>>::_Emplace_reallocate<std::tuple<unsigned __int64,unsigned __int64>>(
              &v66,
              *((_QWORD *)&v66 + 1),
              v74);
          }
          else
          {
            **((_QWORD **)&v66 + 1) = v62;
            *(_QWORD *)(v32 + 8) = v31;
            *((_QWORD *)&v66 + 1) += 16LL;
          }
          v33 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v58, v57);
          if ( v33 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x310,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v33,
              *(int *)v57);
        }
        StateRepository::Database::AddToCache(v14, (struct StateRepository::Statement *)&v58);
        v34 = (_QWORD *)v66;
        if ( (_QWORD)v66 != *((_QWORD *)&v66 + 1) )
        {
          StateRepository::Statement::Finalize((StateRepository::Statement *)&v58);
          v35 = (_QWORD *)*((_QWORD *)&v66 + 1);
          v34 = (_QWORD *)v66;
          if ( (_QWORD)v66 != *((_QWORD *)&v66 + 1) )
          {
            do
            {
              Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp((Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *)v85);
              v36 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                      v81,
                      &v64);
              StringFromKeyAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                                            v84,
                                            *v34,
                                            "BinaryFullPaths",
                                            v36);
              std::wstring::operator=(v85, StringFromKeyAndTableName);
              std::wstring::_Tidy_deallocate(v84);
              if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::BinaryExistsAtFullPath(v85) )
              {
                v38 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                        v76,
                        &v64);
                v39 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                        v84,
                        *i,
                        "FileIDs",
                        v38);
                std::wstring::operator=(v87, v39);
                std::wstring::_Tidy_deallocate(v84);
                v40 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                        v75,
                        &v64);
                v41 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                        v84,
                        v34[1],
                        "ProgramIDs",
                        v40);
                std::wstring::operator=(v88, v41);
                std::wstring::_Tidy_deallocate(v84);
                v89 = 2;
                std::vector<std::wstring>::emplace_back<std::wstring &>(&v77, v85);
                std::vector<Windows::Internal::CapabilityAccess::Private::SQL::InternalApp>::emplace_back<Windows::Internal::CapabilityAccess::Private::SQL::InternalApp>(
                  a1,
                  (const struct Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *)v85);
              }
              Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::~InternalApp((Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *)v85);
              v34 += 2;
            }
            while ( v34 != v35 );
            v34 = (_QWORD *)v66;
          }
          v23 = v70;
        }
        if ( v34 )
          std::_Deallocate<16>(v34, (v67 - (_QWORD)v34) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>(&v72);
      v4 = v69;
      if ( !v69 )
        goto LABEL_44;
    }
    if ( v4 == 1 )
    {
LABEL_44:
      v42 = v71;
      if ( *(_QWORD *)(v71 + 16) )
      {
        if ( *(_QWORD *)(a3 + 16) )
        {
          v45 = StateRepository::Database::PrepareFromCache(
                  v14,
                  "SELECT DISTINCT PackageFamilyName FROM PackagedUsageHistory WHERE PackageFamilyName!=0 AND Capability="
                  "? AND (UserSid=? OR UserSid=0);",
                  (struct StateRepository::Statement *)&v58);
          if ( v45 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x33D,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v45,
              *(int *)v57);
          v46 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 1, v59);
          if ( v46 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x33E,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v46,
              *(int *)v57);
          v47 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 2, v13);
          if ( v47 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x33F,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v47,
              *(int *)v57);
        }
        else
        {
          v43 = StateRepository::Database::PrepareFromCache(
                  v14,
                  "SELECT DISTINCT PackageFamilyName FROM PackagedUsageHistory WHERE PackageFamilyName!=0 AND (UserSid=? OR UserSid=0);",
                  (struct StateRepository::Statement *)&v58);
          if ( v43 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x338,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v43,
              *(int *)v57);
          v44 = StateRepository::Statement::Bind((StateRepository::Statement *)&v58, 1, v13);
          if ( v44 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x339,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v44,
              *(int *)v57);
        }
        v57[0] = 0;
        v48 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v58, v57);
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x343,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v48,
            *(int *)v57);
        v72 = 0;
        v73 = 0;
        while ( v57[0] )
        {
          v59 = 0;
          v49 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v58, 0, &v59);
          if ( v49 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x34B,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v49,
              *(int *)v57);
          std::vector<unsigned __int64>::emplace_back<unsigned __int64>(&v72, &v59);
          v50 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v58, v57);
          if ( v50 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x34E,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v50,
              *(int *)v57);
        }
        StateRepository::Database::AddToCache(v14, (struct StateRepository::Statement *)&v58);
        v52 = (_QWORD *)*((_QWORD *)&v72 + 1);
        for ( j = (_QWORD *)v72; j != v52; ++j )
        {
          StateRepository::Statement::Finalize((StateRepository::Statement *)&v58);
          Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp((Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *)v85);
          v53 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                  v75,
                  &v64);
          v54 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                  v84,
                  *j,
                  "PackageFamilyNames",
                  v53);
          std::wstring::operator=(v86, v54);
          std::wstring::_Tidy_deallocate(v84);
          v55 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::GetPackageFromFamilyNameAndUser(&v71, v42, v86);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
          if ( v55 )
          {
            v89 = 1;
            std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
              v82,
              (__int64)v76,
              (__int64)v86);
            std::vector<Windows::Internal::CapabilityAccess::Private::SQL::InternalApp>::emplace_back<Windows::Internal::CapabilityAccess::Private::SQL::InternalApp>(
              a1,
              (const struct Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *)v85);
          }
          Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::~InternalApp((Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *)v85);
        }
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>(&v72);
      }
    }
    Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v83);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v82);
    std::vector<std::wstring>::_Tidy(&v77);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v58);
    if ( v65 )
      std::_Ref_count_base::_Decref(v65);
  }
  return a1;
}

```

## disassembly

```asm
0x180037690  mov     [rsp-8+arg_18], rbx
0x180037695  push    rbp
0x180037696  push    rsi
0x180037697  push    rdi
0x180037698  push    r12
0x18003769a  push    r13
0x18003769c  push    r14
0x18003769e  push    r15
0x1800376a0  lea     rbp, [rsp-1D0h]
0x1800376a8  sub     rsp, 2D0h
0x1800376af  mov     rax, cs:__security_cookie
0x1800376b6  xor     rax, rsp
0x1800376b9  mov     [rbp+200h+var_40], rax
0x1800376c0  mov     r14d, r9d
0x1800376c3  mov     [rsp+300h+var_284], r9d
0x1800376c8  mov     r12, r8
0x1800376cb  mov     rdi, rdx
0x1800376ce  mov     [rbp+200h+var_278], rdx
0x1800376d2  mov     rsi, rcx
0x1800376d5  mov     [rbp+200h+var_210], rcx
0x1800376d9  mov     r13d, 1
0x1800376df  mov     [rsp+300h+var_288], r13d
0x1800376e4  mov     rbx, [rbp+208h]
0x1800376eb  call    ?DatabaseReady@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(void)
0x1800376f0  xor     r15d, r15d
0x1800376f3  test    al, al
0x1800376f5  jz      loc_180037EF0
0x1800376fb  mov     [rsi], r15
0x1800376fe  mov     [rsi+8], r15
0x180037702  mov     [rsi+10h], r15
0x180037706  mov     [rsp+300h+var_288], r13d
0x18003770b  call    ?HasUserConsentedToUsageDataCollection@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::HasUserConsentedToUsageDataCollection(void)
0x180037710  test    al, al
0x180037712  jz      loc_180037E84
0x180037718  lea     rcx, [rsp+300h+var_2B0]
0x18003771d  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180037722  nop
0x180037723  mov     [rsp+300h+var_2D8], r15
0x180037728  xorps   xmm0, xmm0
0x18003772b  movdqu  [rbp+200h+var_228], xmm0
0x180037730  mov     [rbp+200h+var_218], r15
0x180037734  lea     rcx, [rbp+200h+var_1E0]
0x180037738  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18003773d  nop
0x18003773e  mov     dword ptr [rsp+300h+var_2D0], 6E5265EDh
0x180037746  mov     dword ptr [rsp+300h+var_2D0+4], 4E078FDAh
0x18003774e  mov     [rsp+300h+var_2C8], 527906AAh
0x180037756  mov     [rsp+300h+var_2C4], 341F89F5h
0x18003775e  lea     rdx, [rsp+300h+var_2B0]
0x180037763  lea     rcx, [rbp+200h+var_208]
0x180037767  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18003776c  xor     r9d, r9d
0x18003776f  lea     r8, [rsp+300h+var_2D0]
0x180037774  mov     rdx, rax
0x180037777  lea     rcx, [rbp+200h+var_1A0]
0x18003777b  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180037780  nop
0x180037781  cmp     [r12+10h], r15
0x180037786  jnz     short loc_18003778D
0x180037788  mov     ebx, r15d
0x18003778b  jmp     short loc_1800377B3
0x18003778d  lea     rdx, [rsp+300h+var_2B0]
0x180037792  lea     rcx, [rbp+200h+var_258]
0x180037796  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18003779b  xor     r9d, r9d
0x18003779e  mov     r8, rax
0x1800377a1  lea     rdx, aCapabilities_0; "Capabilities"
0x1800377a8  mov     rcx, r12
0x1800377ab  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x1800377b0  mov     rbx, rax
0x1800377b3  mov     [rsp+300h+var_2D0], rbx
0x1800377b8  lea     rdx, [rsp+300h+var_2B0]
0x1800377bd  lea     rcx, [rbp+200h+var_258]
0x1800377c1  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800377c6  xor     r9d, r9d
0x1800377c9  mov     r8, rax
0x1800377cc  lea     rdx, aUsers; "Users"
0x1800377d3  mov     rcx, rdi
0x1800377d6  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x1800377db  mov     r13, rax
0x1800377de  mov     rdi, [rsp+300h+var_2B0]
0x1800377e3  test    r14d, 0FFFFFFFDh
0x1800377ea  jnz     loc_180037C16
0x1800377f0  lea     r8, [rsp+300h+var_2D8]; struct StateRepository::Statement *
0x1800377f5  mov     rcx, rdi; this
0x1800377f8  cmp     [r12+10h], r15
0x1800377fd  jnz     short loc_18003783D
0x1800377ff  lea     rdx, aSelectDistinct; "SELECT DISTINCT FileID FROM NonPackaged"...
0x180037806  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003780b  mov     rcx, [rbp+208h]; this
0x180037812  xor     ebx, ebx
0x180037814  test    eax, eax
0x180037816  js      loc_180037F0B
0x18003781c  mov     r8, r13; __int64
0x18003781f  lea     edx, [rbx+1]; int
0x180037822  lea     rcx, [rsp+300h+var_2D8]; this
0x180037827  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18003782c  mov     rcx, [rbp+208h]; this
0x180037833  test    eax, eax
0x180037835  js      loc_180037EC6
0x18003783b  jmp     short loc_18003789A
0x18003783d  lea     rdx, aSelectDistinct_2; "SELECT DISTINCT FileID FROM NonPackaged"...
0x180037844  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180037849  mov     rcx, [rbp+208h]; this
0x180037850  test    eax, eax
0x180037852  js      loc_180037F20
0x180037858  mov     r8, rbx; __int64
0x18003785b  mov     edx, 1; int
0x180037860  lea     rcx, [rsp+300h+var_2D8]; this
0x180037865  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18003786a  mov     rcx, [rbp+208h]; this
0x180037871  xor     ebx, ebx
0x180037873  test    eax, eax
0x180037875  js      loc_180037F35
0x18003787b  mov     r8, r13; __int64
0x18003787e  lea     edx, [rbx+2]; int
0x180037881  lea     rcx, [rsp+300h+var_2D8]; this
0x180037886  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18003788b  mov     rcx, [rbp+208h]; this
0x180037892  test    eax, eax
0x180037894  js      loc_180037F4A
0x18003789a  mov     [rsp+300h+var_2E0], bl; int
0x18003789e  lea     rdx, [rsp+300h+var_2E0]; bool *
0x1800378a3  lea     rcx, [rsp+300h+var_2D8]; this
0x1800378a8  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800378ad  mov     rcx, [rbp+208h]; this
0x1800378b4  test    eax, eax
0x1800378b6  js      loc_180037F5F
0x1800378bc  xorps   xmm0, xmm0
0x1800378bf  movdqu  [rbp+200h+var_270], xmm0
0x1800378c4  mov     [rbp+200h+var_260], rbx
0x1800378c8  jmp     short loc_18003791B
0x1800378ca  mov     [rsp+300h+var_2C0], rbx
0x1800378cf  lea     r8, [rsp+300h+var_2C0]; unsigned __int64 *
0x1800378d4  xor     edx, edx; int
0x1800378d6  lea     rcx, [rsp+300h+var_2D8]; this
0x1800378db  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800378e0  mov     rcx, [rbp+208h]; this
0x1800378e7  test    eax, eax
0x1800378e9  js      loc_180037F89
0x1800378ef  lea     rdx, [rsp+300h+var_2C0]
0x1800378f4  lea     rcx, [rbp+200h+var_270]
0x1800378f8  call    ??$emplace_back@_K@?$vector@_KV?$allocator@_K@std@@@std@@QEAAAEA_K$$QEA_K@Z; std::vector<unsigned __int64>::emplace_back<unsigned __int64>(unsigned __int64 &&)
0x1800378fd  lea     rdx, [rsp+300h+var_2E0]; bool *
0x180037902  lea     rcx, [rsp+300h+var_2D8]; this
0x180037907  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x18003790c  mov     rcx, [rbp+208h]; this
0x180037913  test    eax, eax
0x180037915  js      loc_180037F74
0x18003791b  cmp     [rsp+300h+var_2E0], bl
0x18003791f  jnz     short loc_1800378CA
0x180037921  lea     rdx, [rsp+300h+var_2D8]; struct StateRepository::Statement *
0x180037926  mov     rcx, rdi; this
0x180037929  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18003792e  mov     r14, qword ptr [rbp+200h+var_270]
0x180037932  mov     r15, qword ptr [rbp+200h+var_270+8]
0x180037936  mov     [rbp+200h+var_280], r15
0x18003793a  cmp     r14, r15
0x18003793d  jz      loc_180037C01
0x180037943  mov     [rsp+300h+var_2E0], bl; int
0x180037947  lea     r8, [rsp+300h+var_2D8]; struct StateRepository::Statement *
0x18003794c  lea     rdx, aSelectMaxLasto; "SELECT MAX(LastObservedTime), ProgramID"...
0x180037953  mov     rcx, rdi; this
0x180037956  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003795b  mov     rcx, [rbp+208h]; this
0x180037962  test    eax, eax
0x180037964  js      loc_180038007
0x18003796a  mov     r8, [r14]; __int64
0x18003796d  mov     edx, 1; int
0x180037972  lea     rcx, [rsp+300h+var_2D8]; this
0x180037977  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18003797c  mov     rcx, [rbp+208h]; this
0x180037983  test    eax, eax
0x180037985  js      loc_180037FF2
0x18003798b  lea     rdx, [rsp+300h+var_2E0]; bool *
0x180037990  lea     rcx, [rsp+300h+var_2D8]; this
0x180037995  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x18003799a  mov     rcx, [rbp+208h]; this
0x1800379a1  test    eax, eax
0x1800379a3  js      loc_180037FDD
0x1800379a9  xorps   xmm0, xmm0
0x1800379ac  movdqu  [rsp+300h+var_2A0], xmm0
0x1800379b2  mov     [rsp+300h+var_290], rbx
0x1800379b7  jmp     loc_180037A65
0x1800379bc  mov     [rsp+300h+var_2B8], rbx
0x1800379c1  mov     [rsp+300h+var_2C0], rbx
0x1800379c6  lea     r8, [rsp+300h+var_2B8]; unsigned __int64 *
0x1800379cb  mov     edx, 1; int
0x1800379d0  lea     rcx, [rsp+300h+var_2D8]; this
0x1800379d5  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800379da  mov     rcx, [rbp+208h]; this
0x1800379e1  test    eax, eax
0x1800379e3  js      loc_180037FC8
0x1800379e9  lea     r8, [rsp+300h+var_2C0]; unsigned __int64 *
0x1800379ee  mov     edx, 2; int
0x1800379f3  lea     rcx, [rsp+300h+var_2D8]; this
0x1800379f8  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800379fd  mov     rcx, [rbp+208h]; this
0x180037a04  test    eax, eax
0x180037a06  js      loc_180037FB3
0x180037a0c  mov     rax, [rsp+300h+var_2C0]
0x180037a11  mov     [rbp+200h+var_258], rax
0x180037a15  mov     rcx, [rsp+300h+var_2B8]
0x180037a1a  mov     [rbp+200h+var_250], rcx
0x180037a1e  mov     rdx, qword ptr [rsp+300h+var_2A0+8]
0x180037a23  cmp     rdx, [rsp+300h+var_290]
0x180037a28  jz      short loc_180037A39
0x180037a2a  mov     [rdx], rax
0x180037a2d  mov     [rdx+8], rcx
0x180037a31  add     qword ptr [rsp+300h+var_2A0+8], 10h
0x180037a37  jmp     short loc_180037A47
0x180037a39  lea     r8, [rbp+200h+var_258]
0x180037a3d  lea     rcx, [rsp+300h+var_2A0]
0x180037a42  call    ??$_Emplace_reallocate@V?$tuple@_K_K@std@@@?$vector@V?$tuple@_K_K@std@@V?$allocator@V?$tuple@_K_K@std@@@2@@std@@AEAAPEAV?$tuple@_K_K@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<unsigned __int64,unsigned __int64>>::_Emplace_reallocate<std::tuple<unsigned __int64,unsigned __int64>>(std::tuple<unsigned __int64,unsigned __int64> * const,std::tuple<unsigned __int64,unsigned __int64> &&)
0x180037a47  lea     rdx, [rsp+300h+var_2E0]; bool *
0x180037a4c  lea     rcx, [rsp+300h+var_2D8]; this
0x180037a51  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x180037a56  mov     rcx, [rbp+208h]; this
0x180037a5d  test    eax, eax
0x180037a5f  js      loc_180037F9E
0x180037a65  cmp     [rsp+300h+var_2E0], bl
0x180037a69  jnz     loc_1800379BC
0x180037a6f  lea     rdx, [rsp+300h+var_2D8]; struct StateRepository::Statement *
0x180037a74  mov     rcx, rdi; this
0x180037a77  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180037a7c  mov     rbx, qword ptr [rsp+300h+var_2A0]
0x180037a81  cmp     rbx, qword ptr [rsp+300h+var_2A0+8]
0x180037a86  jz      loc_180037BDD
0x180037a8c  lea     rcx, [rsp+300h+var_2D8]; this
0x180037a91  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180037a96  mov     rbx, qword ptr [rsp+300h+var_2A0]
0x180037a9b  mov     r15, qword ptr [rsp+300h+var_2A0+8]
0x180037aa0  cmp     rbx, r15
0x180037aa3  jz      loc_180037BD9
0x180037aa9  lea     rcx, [rbp+200h+var_150]; this
0x180037ab0  call    ??0InternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp(void)
0x180037ab5  nop
0x180037ab6  lea     rdx, [rsp+300h+var_2B0]
0x180037abb  lea     rcx, [rbp+200h+var_1F8]
0x180037abf  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180037ac4  mov     r9, rax
0x180037ac7  lea     r8, aBinaryfullpath; "BinaryFullPaths"
0x180037ace  mov     rdx, [rbx]
0x180037ad1  lea     rcx, [rbp+200h+var_170]
0x180037ad8  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180037add  mov     rdx, rax
0x180037ae0  lea     rcx, [rbp+200h+var_150]
0x180037ae7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037aec  lea     rcx, [rbp+200h+var_170]
0x180037af3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037af8  lea     rcx, [rbp+200h+var_150]
0x180037aff  call    ?BinaryExistsAtFullPath@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::BinaryExistsAtFullPath(std::wstring const &)
0x180037b04  test    al, al
0x180037b06  jz      loc_180037BBB
0x180037b0c  lea     rdx, [rsp+300h+var_2B0]
0x180037b11  lea     rcx, [rbp+200h+var_238]
0x180037b15  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180037b1a  mov     r9, rax
0x180037b1d  lea     r8, aFileids; "FileIDs"
0x180037b24  mov     rdx, [r14]
0x180037b27  lea     rcx, [rbp+200h+var_170]
0x180037b2e  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180037b33  mov     rdx, rax
0x180037b36  lea     rcx, [rbp+200h+var_B0]
0x180037b3d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037b42  lea     rcx, [rbp+200h+var_170]
0x180037b49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037b4e  lea     rdx, [rsp+300h+var_2B0]
0x180037b53  lea     rcx, [rbp+200h+var_248]
0x180037b57  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180037b5c  mov     r9, rax
0x180037b5f  lea     r8, aProgramids; "ProgramIDs"
0x180037b66  mov     rdx, [rbx+8]
0x180037b6a  lea     rcx, [rbp+200h+var_170]
0x180037b71  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180037b76  mov     rdx, rax
0x180037b79  lea     rcx, [rbp+200h+var_90]
0x180037b80  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180037b85  lea     rcx, [rbp+200h+var_170]
0x180037b8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037b91  mov     [rbp+200h+var_50], 2
0x180037b9b  lea     rdx, [rbp+200h+var_150]
0x180037ba2  lea     rcx, [rbp+200h+var_228]
0x180037ba6  call    ??$emplace_back@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring &>(std::wstring &)
0x180037bab  lea     rdx, [rbp+200h+var_150]
0x180037bb2  mov     rcx, rsi
0x180037bb5  call    ??$emplace_back@UInternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@@?$vector@UInternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UInternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@QEAAAEAUInternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@$$QEAU234567@@Z; std::vector<Windows::Internal::CapabilityAccess::Private::SQL::InternalApp>::emplace_back<Windows::Internal::CapabilityAccess::Private::SQL::InternalApp>(Windows::Internal::CapabilityAccess::Private::SQL::InternalApp &&)
0x180037bba  nop
0x180037bbb  lea     rcx, [rbp+200h+var_150]; this
0x180037bc2  call    ??1InternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::~InternalApp(void)
0x180037bc7  add     rbx, 10h
0x180037bcb  cmp     rbx, r15
0x180037bce  jnz     loc_180037AA9
0x180037bd4  mov     rbx, qword ptr [rsp+300h+var_2A0]
0x180037bd9  mov     r15, [rbp+200h+var_280]
0x180037bdd  test    rbx, rbx
0x180037be0  jz      short loc_180037BF6
0x180037be2  mov     rdx, [rsp+300h+var_290]
0x180037be7  sub     rdx, rbx
0x180037bea  and     rdx, 0FFFFFFFFFFFFFFF0h
  ... truncated ...
```
