# Windows::Internal::CapabilityAccess::Private::SQL::GetAppAggregatedSuspiciousRecordStubsFromTable(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::SQL::SqliteTable)

- ea: `0x180031ef0`
- end: `0x180032d2f`
- name: `?GetAppAggregatedSuspiciousRecordStubsFromTable@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@USqliteAppSuspiciousUsageRecordsStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteAppSuspiciousUsageRecordsStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0W4SqliteTable@12345@@Z`
- size: `3647`
- prototype: ``
- caller_count: `1`
- callee_count: `56`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031b30`

## callees

- `0x1800094c0`
- `0x18000d380`
- `0x18000d3a0`
- `0x180016338`
- `0x180016450`
- `0x18001649c`
- `0x180017bc4`
- `0x18001c3b4`
- `0x18001e254`
- `0x18001f4c0`
- `0x18001f5f4`
- `0x180020fcc`
- `0x18002392c`
- `0x180024b58`
- `0x18002570c`
- `0x1800293e8`
- `0x18002a634`
- `0x18002a838`
- `0x18002a9e8`
- `0x18002b048`
- `0x18002b778`
- `0x18002bcac`
- `0x18002c9a4`
- `0x18002d1f8`
- `0x18002d638`
- `0x18002e704`
- `0x18002ea4c`
- `0x18002ef24`
- `0x18002f560`
- `0x18002f65c`
- `0x18002f93c`
- `0x18002f978`
- `0x180031ef0`
- `0x1800352d0`
- `0x1800363b4`
- `0x180036f0c`
- `0x180037460`
- `0x180039a1c`
- `0x18003b188`
- `0x180042514`
- `0x180043224`
- `0x180044f4c`
- `0x18004b30c`
- `0x180056a64`
- `0x18005ed6c`
- `0x18005ff60`
- `0x18006013c`
- `0x1800a25e8`
- `0x1800a261c`
- `0x1800a26e8`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180032582`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180032582`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180032574`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180032574`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x1800323a3`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x1800323a3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003236e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003236e`

## string_xrefs

- `0x180032bcb`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032be8`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032bfd`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c12`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c27`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c3c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c51`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c66`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c7b`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032c90`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032caa`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032cc5`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032cda`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032cef`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032d04`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032d1c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003202b`: `SELECT PackageFamilyName, MAX(LastUsedTimeStart), group_concat(ID) FROM PackagedUsageHistory WHERE UserSid=? AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? AND Label=? GROUP BY PackageFamilyName; `
- `0x180032056`: `SELECT BinaryFullPath, MAX(LastUsedTimeStart), group_concat(ID) FROM NonPackagedUsageHistory WHERE UserSid=? AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? AND Label=? GROUP BY BinaryFullPath; `
- `0x1800321e9`: `BinaryFullPaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
Windows::Internal::CapabilityAccess::Private::SQL *__fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetAppAggregatedSuspiciousRecordStubsFromTable(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        _DWORD *a2,
        __int64 a3,
        int a4)
{
  int v4; // r12d
  __int64 v5; // r13
  _DWORD *v6; // r15
  int v7; // esi
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int64 KeyFromStringAndTableName; // rbx
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // r14
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned __int64 SystemTimeAsUInt64; // rax
  int v19; // eax
  int v20; // eax
  int Row; // eax
  __int64 v22; // rax
  int ColumnUInt64; // eax
  __int64 v24; // rax
  const char *v25; // r8
  __int64 StringFromKeyAndTableName; // rax
  int v27; // eax
  int ColumnText8; // eax
  unsigned __int64 v29; // r14
  __int64 v30; // rax
  unsigned __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r13
  unsigned __int64 v34; // rbx
  __int64 not_ch_1; // rax
  unsigned __int64 v36; // r15
  __int64 v37; // rax
  unsigned __int64 v38; // rdx
  __int64 v39; // r8
  unsigned __int64 v40; // rbx
  __int64 trivial_1; // rax
  __int64 v42; // rax
  const char *v43; // rbx
  int v44; // eax
  __int64 v45; // r14
  int v46; // eax
  int v47; // eax
  __int64 CapabilityUsageInfoForPackagedClients; // rax
  int v49; // esi
  unsigned __int64 v50; // r14
  char *v51; // rcx
  Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo *v52; // r15
  unsigned __int64 v53; // r13
  unsigned __int64 v54; // rbx
  int v55; // esi
  int v56; // ecx
  __int64 v57; // rcx
  char v58; // al
  __int64 v59; // rcx
  _QWORD *v60; // rax
  char *v61; // rcx
  Windows::Internal::CapabilityAccess::Private::SQL *v62; // r13
  int v63; // esi
  __int64 v64; // rbx
  char HasCapability; // al
  __int64 **v66; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  int v70; // [rsp+20h] [rbp-288h]
  bool v71[4]; // [rsp+30h] [rbp-278h] BYREF
  int v72; // [rsp+34h] [rbp-274h]
  unsigned __int64 v73; // [rsp+38h] [rbp-270h] BYREF
  _QWORD v74[2]; // [rsp+40h] [rbp-268h] BYREF
  struct _GUID v75; // [rsp+50h] [rbp-258h] BYREF
  __int64 v76; // [rsp+60h] [rbp-248h]
  char *v77; // [rsp+68h] [rbp-240h] BYREF
  Windows::Internal::CapabilityAccess::Private::SQL *v78; // [rsp+70h] [rbp-238h]
  _DWORD *v79; // [rsp+78h] [rbp-230h]
  char *EndPtr[2]; // [rsp+80h] [rbp-228h] BYREF
  __int64 v81; // [rsp+90h] [rbp-218h]
  __int128 v82; // [rsp+98h] [rbp-210h] BYREF
  StateRepository::Database *v83; // [rsp+A8h] [rbp-200h] BYREF
  std::_Ref_count_base *v84; // [rsp+B0h] [rbp-1F8h]
  int v85; // [rsp+B8h] [rbp-1F0h]
  Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo *v86; // [rsp+C0h] [rbp-1E8h] BYREF
  __int128 v87; // [rsp+C8h] [rbp-1E0h]
  Windows::Internal::CapabilityAccess::Private::SQL *v88; // [rsp+D8h] [rbp-1D0h]
  _DWORD *v89; // [rsp+E0h] [rbp-1C8h]
  __int64 v90; // [rsp+E8h] [rbp-1C0h] BYREF
  std::_Ref_count_base *v91; // [rsp+F0h] [rbp-1B8h]
  char v92[8]; // [rsp+F8h] [rbp-1B0h] BYREF
  std::_Ref_count_base *v93; // [rsp+100h] [rbp-1A8h]
  __int64 v94; // [rsp+108h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v95; // [rsp+110h] [rbp-198h]
  __int64 v96; // [rsp+118h] [rbp-190h] BYREF
  std::_Ref_count_base *v97; // [rsp+120h] [rbp-188h]
  _BYTE v98[16]; // [rsp+128h] [rbp-180h] BYREF
  _BYTE v99[16]; // [rsp+138h] [rbp-170h] BYREF
  _BYTE v100[48]; // [rsp+148h] [rbp-160h] BYREF
  Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo *v101[4]; // [rsp+178h] [rbp-130h] BYREF
  Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo *v102; // [rsp+198h] [rbp-110h] BYREF
  char *v103; // [rsp+1A0h] [rbp-108h]
  unsigned __int64 v104; // [rsp+1A8h] [rbp-100h]
  unsigned __int64 v105; // [rsp+1B0h] [rbp-F8h]
  unsigned __int64 v106; // [rsp+1C0h] [rbp-E8h] BYREF
  __int64 v107; // [rsp+1C8h] [rbp-E0h] BYREF
  __int128 v108; // [rsp+1D0h] [rbp-D8h]
  _BYTE v109[32]; // [rsp+1E0h] [rbp-C8h] BYREF
  int v110; // [rsp+200h] [rbp-A8h]
  __int64 v111; // [rsp+210h] [rbp-98h] BYREF
  _QWORD v112[3]; // [rsp+218h] [rbp-90h] BYREF
  _BYTE v113[32]; // [rsp+230h] [rbp-78h] BYREF
  int v114; // [rsp+250h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v76 = a3;
  v6 = a2;
  v79 = a2;
  v78 = a1;
  v88 = a1;
  v89 = a2;
  v85 = a4;
  v7 = 0;
  v72 = 0;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD77,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      v70);
  std::make_shared<StateRepository::Database,>(&v83);
  v74[0] = 0;
  *(_QWORD *)&v75.Data1 = 0x4981D77E3451EB77LL;
  *(_DWORD *)v75.Data4 = -581149537;
  *(_DWORD *)&v75.Data4[4] = 2039138420;
  v8 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                   EndPtr,
                   &v83);
  Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(
    (Windows::Internal::CapabilityAccess::Private::SQL *)v100,
    v8,
    &v75,
    0);
  v9 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
         &v75,
         &v83);
  KeyFromStringAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
                                v6,
                                "Users",
                                v9,
                                0);
  v11 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v75,
          &v83);
  v13 = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(v5, "Capabilities", v11, 0);
  if ( v4 )
  {
    if ( v4 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD8B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        v12);
    v14 = StateRepository::Database::PrepareFromCache(
            v83,
            "SELECT PackageFamilyName, MAX(LastUsedTimeStart), group_concat(ID) FROM PackagedUsageHistory WHERE UserSid=?"
            " AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? AND Label=? GROUP BY PackageFamilyName; ",
            (struct StateRepository::Statement *)v74);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD88,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v14,
        v70);
  }
  else
  {
    v15 = StateRepository::Database::PrepareFromCache(
            v83,
            "SELECT BinaryFullPath, MAX(LastUsedTimeStart), group_concat(ID) FROM NonPackagedUsageHistory WHERE UserSid=?"
            " AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? AND Label=? GROUP BY BinaryFullPath; ",
            (struct StateRepository::Statement *)v74);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD85,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v15,
        v70);
  }
  v16 = StateRepository::Statement::Bind((StateRepository::Statement *)v74, 1, KeyFromStringAndTableName);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD8E,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v16,
      v70);
  v17 = StateRepository::Statement::Bind((StateRepository::Statement *)v74, 2, v13);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD8F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v17,
      v70);
  SystemTimeAsUInt64 = Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(retaddr);
  v19 = StateRepository::Statement::Bind((StateRepository::Statement *)v74, 3, SystemTimeAsUInt64 - 6048000000000LL);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD92,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v19,
      v70);
  v20 = StateRepository::Statement::Bind((StateRepository::Statement *)v74, 4, 0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD94,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v20,
      v70);
  v71[0] = 0;
  Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)v74, v71);
  if ( Row < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD97,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)Row,
      v70);
  v82 = 0;
  v22 = std::_Allocate<16,std::_Default_allocate_traits>(136);
  *(_QWORD *)v22 = v22;
  *(_QWORD *)(v22 + 8) = v22;
  *(_QWORD *)(v22 + 16) = v22;
  *(_WORD *)(v22 + 24) = 257;
  *(_QWORD *)&v82 = v22;
  if ( v71[0] )
  {
LABEL_13:
    v77 = 0;
    v73 = 0;
    Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub::SqliteAppSuspiciousUsageRecordsStub((Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub *)&v106);
    ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)v74, 0, &v73);
    if ( ColumnUInt64 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)ColumnUInt64,
        v70);
    if ( v4 )
    {
      v24 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v98,
              &v83);
      v25 = "PackageFamilyNames";
    }
    else
    {
      v24 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v92,
              &v83);
      v25 = "BinaryFullPaths";
    }
    StringFromKeyAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                                  v101,
                                  v73,
                                  v25,
                                  v24);
    std::wstring::operator=(v109, StringFromKeyAndTableName);
    std::wstring::_Tidy_deallocate(v101);
    v27 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)v74, 1, &v106);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDAD,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v27,
        v70);
    ColumnText8 = StateRepository::Statement::GetColumnText8((StateRepository::Statement *)v74, 2, (const char **)&v77);
    if ( ColumnText8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDAE,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)ColumnText8,
        v70);
    std::string::string(&v102, v77);
    v29 = 0;
    while ( 1 )
    {
      v30 = std::_String_val<std::_Simple_types<char>>::_Myptr(&v102);
      v33 = v30;
      if ( v29 >= v31
        || (v34 = v31 + v30, LOBYTE(v32) = 44, not_ch_1 = _std_find_not_ch_1(v29 + v30, v31 + v30, v32), not_ch_1 == v34)
        || (v36 = not_ch_1 - v33, not_ch_1 - v33 == -1) )
      {
        v110 = v4;
        v45 = *(_QWORD *)std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>::_Try_emplace<std::wstring const &,>(
                           &v82,
                           v99,
                           v109);
        *(_QWORD *)(v45 + 64) = v106;
        if ( (__int64 *)(v45 + 72) != &v107 )
        {
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>(v45 + 72);
          *(_QWORD *)(v45 + 72) = v107;
          *(_OWORD *)(v45 + 80) = v108;
          v107 = 0;
          v108 = 0;
        }
        std::wstring::operator=(v45 + 96, v109);
        *(_DWORD *)(v45 + 128) = v110;
        v46 = StateRepository::Statement::FetchRow((StateRepository::Statement *)v74, v71);
        if ( v46 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDC7,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v46,
            v70);
        if ( v105 > 0xF )
          std::_Deallocate<16>(v102, v105 + 1);
        v104 = 0;
        v105 = 15;
        LOBYTE(v102) = 0;
        Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub::~SqliteAppSuspiciousUsageRecordsStub((Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub *)&v106);
        if ( !v71[0] )
        {
          v6 = v79;
          v5 = v76;
          goto LABEL_42;
        }
        goto LABEL_13;
      }
      v37 = std::_String_val<std::_Simple_types<char>>::_Myptr(&v102);
      v5 = v37;
      if ( v36 >= v38
        || (v40 = v38 + v37,
            LOBYTE(v39) = 44,
            trivial_1 = _std_find_trivial_1(v36 + v37, v38 + v37, v39),
            trivial_1 == v40) )
      {
        v29 = -1;
      }
      else
      {
        v29 = trivial_1 - v5;
      }
      memset(v101, 0, sizeof(v101));
      if ( v104 < v36 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      v42 = std::_String_val<std::_Simple_types<char>>::_Myptr(&v102);
      std::string::_Construct<1,char const *>(v101, v36 + v42);
      v7 |= 0x10u;
      v72 = v7;
      v6 = (_DWORD *)_o__errno();
      v43 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v101);
      EndPtr[0] = 0;
      *v6 = 0;
      v44 = strtol(v43, EndPtr, 10);
      if ( v43 == EndPtr[0] )
        break;
      if ( *v6 == 34 )
      {
        std::_Xout_of_range("stoi argument out of range");
        __debugbreak();
      }
      LODWORD(v73) = v44;
      if ( (_QWORD)v108 == *((_QWORD *)&v108 + 1) )
      {
        std::vector<unsigned __int64>::_Emplace_reallocate<int>(&v107, v108, &v73);
      }
      else
      {
        *(_QWORD *)v108 = v44;
        *(_QWORD *)&v108 = v108 + 8;
      }
      if ( v101[3] > (Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo *)0xF )
        std::_Deallocate<16>(v101[0], (char *)v101[3] + 1);
    }
    std::_Xinvalid_argument("invalid stoi argument");
  }
  else
  {
LABEL_42:
    StateRepository::Database::AddToCache(v83, (struct StateRepository::Statement *)v74);
    v47 = StateRepository::Statement::Finalize((StateRepository::Statement *)v74);
    if ( v47 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDCB,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v47,
        v70);
  }
  Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::Create(&v90, v5);
  if ( v4 == 1 )
  {
    CapabilityUsageInfoForPackagedClients = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::GetCapabilityUsageInfoForPackagedClients(
                                              v90,
                                              v101,
                                              v6);
    v49 = v7 | 1;
  }
  else
  {
    CapabilityUsageInfoForPackagedClients = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::GetCapabilityUsageInfoForNonPackagedClients(
                                              v90,
                                              &v86,
                                              v6);
    v49 = v7 | 2;
  }
  v72 = v49;
  *(_QWORD *)&v75.Data1 = *(_QWORD *)(CapabilityUsageInfoForPackagedClients + 16);
  v50 = *(_QWORD *)&v75.Data1;
  *(_QWORD *)(CapabilityUsageInfoForPackagedClients + 16) = 0;
  v77 = *(char **)(CapabilityUsageInfoForPackagedClients + 8);
  v51 = v77;
  *(_QWORD *)(CapabilityUsageInfoForPackagedClients + 8) = 0;
  v52 = *(Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo **)CapabilityUsageInfoForPackagedClients;
  *(_QWORD *)CapabilityUsageInfoForPackagedClients = 0;
  v102 = v52;
  v103 = v51;
  v104 = v50;
  if ( (v49 & 2) != 0 )
  {
    v49 &= ~2u;
    v72 = v49;
    if ( v86 )
    {
      std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo>>(v86);
      std::_Deallocate<16>(v86, 8 * ((__int64)(*((_QWORD *)&v87 + 1) - (_QWORD)v86) >> 3));
      v86 = 0;
      v87 = 0;
    }
  }
  if ( (v49 & 1) != 0 )
  {
    v49 &= ~1u;
    v72 = v49;
    if ( v101[0] )
    {
      std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo>>(v101[0]);
      std::_Deallocate<16>(v101[0], 8 * ((v101[2] - v101[0]) >> 3));
      memset(v101, 0, 24);
    }
  }
  v53 = 0;
  v54 = 0x84BDA12F684BDA13uLL * ((v77 - (char *)v52) >> 3);
  if ( v54 )
  {
    v55 = (int)v79;
    do
    {
      v73 = 216 * v53;
      Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(v92);
      if ( !(unsigned int)Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetLastUserAnnotatedLabel(
                            v56,
                            v55,
                            v76,
                            (int)v52 + (int)v73 + 104,
                            (unsigned int)(v4 != 1) + 1) )
      {
        std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Find_lower_bound<std::wstring>(
          &v82,
          EndPtr,
          (char *)v52 + v73 + 104);
        v58 = std::_Tree<std::_Tmap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::ConsentPolicyNamesEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::ConsentPolicyNamesEntry>>,0>>::_Lower_bound_duplicate<std::wstring>(
                v57,
                v81,
                (char *)v52 + v73 + 104);
        v59 = v82;
        if ( v58 )
          v59 = v81;
        if ( v59 == (_QWORD)v82 )
        {
          Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub::SqliteAppSuspiciousUsageRecordsStub((Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub *)&v111);
          std::wstring::operator=(v113, (char *)v52 + v73 + 104);
          v114 = v4;
          EndPtr[0] = 0;
          std::vector<unsigned __int64>::emplace_back<unsigned __int64>(v112, EndPtr);
          v111 = *(_QWORD *)((char *)v52 + v73 + 200);
          v61 = *(char **)std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>::_Try_emplace<std::wstring const &,>(
                            &v82,
                            v98,
                            v113);
          EndPtr[0] = v61;
          *((_QWORD *)v61 + 8) = v111;
          if ( v61 + 72 != (char *)v112 )
          {
            std::vector<unsigned __int64>::_Assign_counted_range<unsigned __int64 *>(
              v61 + 72,
              v112[0],
              (__int64)(v112[1] - v112[0]) >> 3);
            v61 = EndPtr[0];
          }
          std::wstring::operator=(v61 + 96, v113);
          *((_DWORD *)EndPtr[0] + 32) = v114;
          Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub::~SqliteAppSuspiciousUsageRecordsStub((Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub *)&v111);
        }
        else
        {
          EndPtr[0] = 0;
          v60 = (_QWORD *)std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>::_Try_emplace<std::wstring const &,>(
                            &v82,
                            v99,
                            (char *)v52 + v73 + 104);
          std::vector<unsigned __int64>::emplace_back<unsigned __int64>(*v60 + 72LL, EndPtr);
        }
      }
      if ( v93 )
        std::_Ref_count_base::_Decref(v93);
      ++v53;
    }
    while ( v53 < v54 );
    v49 = v72;
    v50 = *(_QWORD *)&v75.Data1;
  }
  v62 = v78;
  *(_QWORD *)v78 = 0;
  *((_QWORD *)v62 + 1) = 0;
  *((_QWORD *)v62 + 2) = 0;
  v63 = v49 | 4;
  v72 = v63;
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(&v96);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v96, &v94, v76);
  v64 = *(_QWORD *)v82;
  while ( 1 )
  {
    v76 = v64;
    if ( *(_BYTE *)(v64 + 25) )
      break;
    try
    {
      if ( v4 == 1 )
      {
        if ( !*(_QWORD *)Windows::Internal::CapabilityAccess::Private::GetPackageFromFamilyNameAndUser(
                           &v75,
                           v79,
                           v64 + 32) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDFF,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)0x80070002LL,
            v70);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
      }
      if ( *(_BYTE *)(v94 + 489) )
      {
        v62 = v78;
        std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>::_Emplace_one_at_back<Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub const &>(
          v78,
          v64 + 64);
      }
      else
      {
        if ( v4 != 1
          || (std::wstring::wstring(v101, L"runFullTrust"),
              v63 |= 8u,
              v72 = v63,
              HasCapability = Windows::Internal::CapabilityAccess::Private::PackageFamilyHasCapability(
                                (_DWORD)v79,
                                (int)v64 + 32,
                                (unsigned int)v101,
                                0,
                                0),
              v71[0] = 1,
              HasCapability) )
        {
          v71[0] = 0;
        }
        if ( (v63 & 8) != 0 )
        {
          v63 &= ~8u;
          v72 = v63;
          std::wstring::_Tidy_deallocate(v101);
        }
        v62 = v78;
        if ( v71[0] )
          std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>::_Emplace_one_at_back<Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub const &>(
            v78,
            v64 + 64);
      }
    }
    catch ( ... )
    {
      v50 = v104;
      v77 = v103;
      v52 = v102;
      v64 = v76;
      v63 = v72;
      v62 = v88;
      v78 = v88;
      v79 = v89;
      v4 = v85;
    }
    v66 = *(__int64 ***)(v64 + 16);
    if ( *((_BYTE *)v66 + 25) )
    {
      for ( i = *(_QWORD *)(v64 + 8); !*(_BYTE *)(i + 25) && v64 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v64 = i;
      v64 = i;
    }
    else
    {
      v64 = *(_QWORD *)(v64 + 16);
      for ( j = *v66; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v64 = (__int64)j;
    }
  }
  if ( v95 )
    std::_Ref_count_base::_Decref(v95);
  if ( v97 )
    std::_Ref_count_base::_Decref(v97);
  if ( v52 )
  {
    std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInfo>>(v52);
    std::_Deallocate<16>(v52, 8 * ((__int64)(v50 - (_QWORD)v52) >> 3));
  }
  if ( v91 )
    std::_Ref_count_base::_Decref(v91);
  std::_Tree<std::_Tmap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>>,0>>(&v82);
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v100);
  StateRepository::Statement::~Statement((StateRepository::Statement *)v74);
  if ( v84 )
    std::_Ref_count_base::_Decref(v84);
  return v62;
}

```

## disassembly

```asm
0x180031ef0  push    rbx
0x180031ef2  push    rsi
0x180031ef3  push    rdi
0x180031ef4  push    r12
0x180031ef6  push    r13
0x180031ef8  push    r14
0x180031efa  push    r15
0x180031efc  sub     rsp, 270h
0x180031f03  mov     rax, cs:__security_cookie
0x180031f0a  xor     rax, rsp
0x180031f0d  mov     [rsp+2A8h+var_48], rax
0x180031f15  mov     r12d, r9d
0x180031f18  mov     r13, r8
0x180031f1b  mov     [rsp+2A8h+var_248], r8
0x180031f20  mov     r15, rdx
0x180031f23  mov     [rsp+2A8h+var_230], rdx
0x180031f28  mov     [rsp+2A8h+var_238], rcx
0x180031f2d  mov     [rsp+2A8h+var_1D0], rcx
0x180031f35  mov     [rsp+2A8h+var_1C8], rdx
0x180031f3d  mov     [rsp+2A8h+var_1F0], r9d
0x180031f45  xor     edi, edi
0x180031f47  mov     esi, edi
0x180031f49  mov     [rsp+2A8h+var_274], edi
0x180031f4d  mov     rbx, [rsp+2A8h]
0x180031f55  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180031f5a  test    al, al
0x180031f5c  jz      loc_180032BC5
0x180031f62  lea     rcx, [rsp+2A8h+var_200]
0x180031f6a  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180031f6f  nop
0x180031f70  mov     [rsp+2A8h+var_268], rdi
0x180031f75  mov     dword ptr [rsp+2A8h+var_258], 3451EB77h
0x180031f7d  mov     dword ptr [rsp+2A8h+var_258+4], 4981D77Eh
0x180031f85  mov     [rsp+2A8h+var_250], 0DD5C5C9Fh
0x180031f8d  mov     [rsp+2A8h+var_24C], 798AC874h
0x180031f95  lea     rdx, [rsp+2A8h+var_200]
0x180031f9d  lea     rcx, [rsp+2A8h+EndPtr]
0x180031fa5  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180031faa  xor     r9d, r9d
0x180031fad  lea     r8, [rsp+2A8h+var_258]
0x180031fb2  mov     rdx, rax
0x180031fb5  lea     rcx, [rsp+2A8h+var_160]
0x180031fbd  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180031fc2  nop
0x180031fc3  lea     rdx, [rsp+2A8h+var_200]
0x180031fcb  lea     rcx, [rsp+2A8h+var_258]
0x180031fd0  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180031fd5  xor     r9d, r9d
0x180031fd8  mov     r8, rax
0x180031fdb  lea     rdx, aUsers; "Users"
0x180031fe2  mov     rcx, r15
0x180031fe5  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180031fea  mov     rbx, rax
0x180031fed  lea     rdx, [rsp+2A8h+var_200]
0x180031ff5  lea     rcx, [rsp+2A8h+var_258]
0x180031ffa  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180031fff  xor     r9d, r9d
0x180032002  mov     r8, rax
0x180032005  lea     rdx, aCapabilities_0; "Capabilities"
0x18003200c  mov     rcx, r13
0x18003200f  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180032014  mov     r14, rax
0x180032017  test    r12d, r12d
0x18003201a  jz      short loc_180032051
0x18003201c  cmp     r12d, 1
0x180032020  jnz     loc_180032BE0
0x180032026  lea     r8, [rsp+2A8h+var_268]; struct StateRepository::Statement *
0x18003202b  lea     rdx, aSelectPackagef; "SELECT PackageFamilyName, MAX(LastUsedT"...
0x180032032  mov     rcx, [rsp+2A8h+var_200]; this
0x18003203a  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003203f  mov     rcx, [rsp+2A8h]; this
0x180032047  test    eax, eax
0x180032049  js      loc_180032BFA
0x18003204f  jmp     short loc_18003207A
0x180032051  lea     r8, [rsp+2A8h+var_268]; struct StateRepository::Statement *
0x180032056  lea     rdx, aSelectBinaryfu; "SELECT BinaryFullPath, MAX(LastUsedTime"...
0x18003205d  mov     rcx, [rsp+2A8h+var_200]; this
0x180032065  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003206a  mov     rcx, [rsp+2A8h]; this
0x180032072  test    eax, eax
0x180032074  js      loc_180032C0F
0x18003207a  mov     r8, rbx; __int64
0x18003207d  mov     edx, 1; int
0x180032082  lea     rcx, [rsp+2A8h+var_268]; this
0x180032087  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18003208c  mov     rcx, [rsp+2A8h]; this
0x180032094  test    eax, eax
0x180032096  js      loc_180032C24
0x18003209c  mov     r8, r14; __int64
0x18003209f  mov     edx, 2; int
0x1800320a4  lea     rcx, [rsp+2A8h+var_268]; this
0x1800320a9  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800320ae  mov     rcx, [rsp+2A8h]; this
0x1800320b6  test    eax, eax
0x1800320b8  js      loc_180032C39
0x1800320be  call    ?GetSystemTimeAsUInt64@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(void)
0x1800320c3  mov     r8, 0FFFFFA7FD71BC000h
0x1800320cd  add     r8, rax; __int64
0x1800320d0  mov     edx, 3; int
0x1800320d5  lea     rcx, [rsp+2A8h+var_268]; this
0x1800320da  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800320df  mov     rcx, [rsp+2A8h]; this
0x1800320e7  test    eax, eax
0x1800320e9  js      loc_180032C4E
0x1800320ef  xor     r8d, r8d; int
0x1800320f2  lea     edx, [r8+4]; int
0x1800320f6  lea     rcx, [rsp+2A8h+var_268]; this
0x1800320fb  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180032100  mov     rcx, [rsp+2A8h]; this
0x180032108  test    eax, eax
0x18003210a  js      loc_180032C63
0x180032110  mov     [rsp+2A8h+var_278], dil
0x180032115  lea     rdx, [rsp+2A8h+var_278]; bool *
0x18003211a  lea     rcx, [rsp+2A8h+var_268]; this
0x18003211f  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x180032124  mov     rcx, [rsp+2A8h]; this
0x18003212c  test    eax, eax
0x18003212e  js      loc_180032C78
0x180032134  xorps   xmm0, xmm0
0x180032137  movdqu  [rsp+2A8h+var_210], xmm0
0x180032140  mov     ecx, 88h
0x180032145  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003214a  mov     [rax], rax
0x18003214d  mov     [rax+8], rax
0x180032151  mov     [rax+10h], rax
0x180032155  mov     word ptr [rax+18h], 101h
0x18003215b  mov     qword ptr [rsp+2A8h+var_210], rax
0x180032163  cmp     [rsp+2A8h+var_278], dil
0x180032168  jz      loc_18003253F
0x18003216e  mov     [rsp+2A8h+var_240], rdi
0x180032173  mov     [rsp+2A8h+var_270], rdi
0x180032178  lea     rcx, [rsp+2A8h+var_E8]; this
0x180032180  call    ??0SqliteAppSuspiciousUsageRecordsStub@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub::SqliteAppSuspiciousUsageRecordsStub(void)
0x180032185  nop
0x180032186  lea     r8, [rsp+2A8h+var_270]; unsigned __int64 *
0x18003218b  xor     edx, edx; int
0x18003218d  lea     rcx, [rsp+2A8h+var_268]; this
0x180032192  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180032197  mov     rcx, [rsp+2A8h]; this
0x18003219f  test    eax, eax
0x1800321a1  js      loc_180032D01
0x1800321a7  test    r12d, r12d
0x1800321aa  jz      short loc_1800321D4
0x1800321ac  cmp     r12d, 1
0x1800321b0  jnz     loc_180032CA2
0x1800321b6  lea     rdx, [rsp+2A8h+var_200]
0x1800321be  lea     rcx, [rsp+2A8h+var_180]
0x1800321c6  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800321cb  lea     r8, aPackagefamilyn_0; "PackageFamilyNames"
0x1800321d2  jmp     short loc_1800321F0
0x1800321d4  lea     rdx, [rsp+2A8h+var_200]
0x1800321dc  lea     rcx, [rsp+2A8h+var_1B0]
0x1800321e4  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800321e9  lea     r8, aBinaryfullpath; "BinaryFullPaths"
0x1800321f0  mov     r9, rax
0x1800321f3  mov     rdx, [rsp+2A8h+var_270]
0x1800321f8  lea     rcx, [rsp+2A8h+var_130]
0x180032200  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180032205  mov     rdx, rax
0x180032208  lea     rcx, [rsp+2A8h+var_C8]
0x180032210  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032215  lea     rcx, [rsp+2A8h+var_130]
0x18003221d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032222  lea     r8, [rsp+2A8h+var_E8]; unsigned __int64 *
0x18003222a  mov     edx, 1; int
0x18003222f  lea     rcx, [rsp+2A8h+var_268]; this
0x180032234  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180032239  mov     rcx, [rsp+2A8h]; this
0x180032241  test    eax, eax
0x180032243  js      loc_180032CEC
0x180032249  lea     r8, [rsp+2A8h+var_240]; char **
0x18003224e  mov     edx, 2; int
0x180032253  lea     rcx, [rsp+2A8h+var_268]; this
0x180032258  call    ?GetColumnText8@Statement@StateRepository@@QEBAJHPEAPEBD@Z; StateRepository::Statement::GetColumnText8(int,char const * *)
0x18003225d  mov     rcx, [rsp+2A8h]; this
0x180032265  test    eax, eax
0x180032267  js      loc_180032CD7
0x18003226d  mov     rdx, [rsp+2A8h+var_240]
0x180032272  lea     rcx, [rsp+2A8h+var_110]
0x18003227a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003227f  nop
0x180032280  mov     r14, rdi
0x180032283  mov     rdx, [rsp+2A8h+var_100]
0x18003228b  lea     rcx, [rsp+2A8h+var_110]
0x180032293  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180032298  mov     r13, rax
0x18003229b  cmp     r14, rdx
0x18003229e  jnb     loc_180032421
0x1800322a4  lea     rbx, [rdx+rax]
0x1800322a8  lea     rcx, [r14+rax]
0x1800322ac  mov     r8b, 2Ch ; ','
0x1800322af  mov     rdx, rbx
0x1800322b2  call    __std_find_not_ch_1
0x1800322b7  mov     r15, rax
0x1800322ba  cmp     rax, rbx
0x1800322bd  jz      loc_180032421
0x1800322c3  sub     r15, r13
0x1800322c6  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800322ca  jz      loc_180032421
0x1800322d0  mov     rdx, [rsp+2A8h+var_100]
0x1800322d8  lea     rcx, [rsp+2A8h+var_110]
0x1800322e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800322e5  mov     r13, rax
0x1800322e8  cmp     r15, rdx
0x1800322eb  jnb     short loc_18003230D
0x1800322ed  lea     rbx, [rdx+rax]
0x1800322f1  lea     rcx, [r15+rax]
0x1800322f5  mov     r8b, 2Ch ; ','
0x1800322f8  mov     rdx, rbx
0x1800322fb  call    __std_find_trivial_1
0x180032300  mov     r14, rax
0x180032303  cmp     rax, rbx
0x180032306  jz      short loc_18003230D
0x180032308  sub     r14, r13
0x18003230b  jmp     short loc_180032311
0x18003230d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180032311  xorps   xmm0, xmm0
0x180032314  movups  xmmword ptr [rsp+2A8h+var_130], xmm0
0x18003231c  xorps   xmm1, xmm1
0x18003231f  movdqu  [rsp+2A8h+var_120], xmm1
0x180032328  mov     r8, [rsp+2A8h+var_100]
0x180032330  cmp     r8, r15
0x180032333  jb      loc_180032CBC
0x180032339  mov     rax, r14
0x18003233c  sub     rax, r15
0x18003233f  sub     r8, r15
0x180032342  cmp     r8, rax
0x180032345  cmovnb  r8, rax
0x180032349  lea     rcx, [rsp+2A8h+var_110]
0x180032351  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180032356  lea     rdx, [r15+rax]
0x18003235a  lea     rcx, [rsp+2A8h+var_130]
0x180032362  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180032367  or      esi, 10h
0x18003236a  mov     [rsp+2A8h+var_274], esi
0x18003236e  call    cs:__imp__o__errno
0x180032374  mov     r15, rax
0x180032377  lea     rcx, [rsp+2A8h+var_130]
0x18003237f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180032384  mov     rbx, rax
0x180032387  mov     [rsp+2A8h+EndPtr], rdi
0x18003238f  mov     [r15], edi
0x180032392  mov     r8d, 0Ah; Radix
0x180032398  lea     rdx, [rsp+2A8h+EndPtr]; EndPtr
0x1800323a0  mov     rcx, rax; String
0x1800323a3  call    cs:__imp_strtol
0x1800323a9  cmp     rbx, [rsp+2A8h+EndPtr]
0x1800323b1  jz      loc_18003257B
0x1800323b7  cmp     dword ptr [r15], 22h ; '"'
0x1800323bb  jz      loc_18003256D
0x1800323c1  mov     dword ptr [rsp+2A8h+var_270], eax
0x1800323c5  mov     rdx, qword ptr [rsp+2A8h+var_D8]
0x1800323cd  cmp     rdx, qword ptr [rsp+2A8h+var_D8+8]
0x1800323d5  jz      short loc_1800323E7
0x1800323d7  cdqe
0x1800323d9  mov     [rdx], rax
0x1800323dc  add     qword ptr [rsp+2A8h+var_D8], 8
0x1800323e5  jmp     short loc_1800323FA
0x1800323e7  lea     r8, [rsp+2A8h+var_270]
0x1800323ec  lea     rcx, [rsp+2A8h+var_E0]
0x1800323f4  call    ??$_Emplace_reallocate@H@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_K$$QEAH@Z; std::vector<unsigned __int64>::_Emplace_reallocate<int>(unsigned __int64 * const,int &&)
0x1800323f9  nop
0x1800323fa  mov     rdx, qword ptr [rsp+2A8h+var_120+8]
0x180032402  cmp     rdx, 0Fh
0x180032406  jbe     loc_180032283
0x18003240c  inc     rdx
0x18003240f  mov     rcx, [rsp+2A8h+var_130]
0x180032417  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003241c  jmp     loc_180032283
0x180032421  mov     [rsp+2A8h+var_A8], r12d
0x180032429  lea     r8, [rsp+2A8h+var_C8]
0x180032431  lea     rdx, [rsp+2A8h+var_170]
0x180032439  lea     rcx, [rsp+2A8h+var_210]
0x180032441  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USqliteAppSuspiciousUsageRecordsStub@SQL@Private@CapabilityAccess@Internal@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USqliteAppSuspiciousUsageRecordsStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USqliteAppSuspiciousUsageRecordsStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Internal::CapabilityAccess::Private::SQL::SqliteAppSuspiciousUsageRecordsStub>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180032446  mov     r14, [rax]
0x180032449  mov     rax, [rsp+2A8h+var_E8]
0x180032451  mov     [r14+40h], rax
0x180032455  lea     rbx, [r14+48h]
0x180032459  lea     rax, [rsp+2A8h+var_E0]
0x180032461  cmp     rbx, rax
0x180032464  jz      short loc_1800324A5
0x180032466  mov     rcx, rbx
0x180032469  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>>>>>(void)
0x18003246e  mov     rax, [rsp+2A8h+var_E0]
0x180032476  mov     [rbx], rax
0x180032479  mov     rax, qword ptr [rsp+2A8h+var_D8]
0x180032481  mov     [rbx+8], rax
0x180032485  mov     rax, qword ptr [rsp+2A8h+var_D8+8]
0x18003248d  mov     [rbx+10h], rax
0x180032491  mov     [rsp+2A8h+var_E0], rdi
0x180032499  xorps   xmm0, xmm0
0x18003249c  movdqa  [rsp+2A8h+var_D8], xmm0
0x1800324a5  lea     rcx, [r14+60h]
0x1800324a9  lea     rdx, [rsp+2A8h+var_C8]
0x1800324b1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800324b6  mov     eax, [rsp+2A8h+var_A8]
0x1800324bd  mov     [r14+80h], eax
0x1800324c4  lea     rdx, [rsp+2A8h+var_278]; bool *
0x1800324c9  lea     rcx, [rsp+2A8h+var_268]; this
0x1800324ce  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
  ... truncated ...
```
