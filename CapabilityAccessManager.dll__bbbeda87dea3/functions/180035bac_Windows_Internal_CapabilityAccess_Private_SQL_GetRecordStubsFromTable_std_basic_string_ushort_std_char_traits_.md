# Windows::Internal::CapabilityAccess::Private::SQL::GetRecordStubsFromTable(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,Windows::Internal::CapabilityAccess::Private::SQL::SqliteTable,uint)

- ea: `0x180035bac`
- end: `0x18003628e`
- name: `?GetRecordStubsFromTable@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0_KW4SqliteTable@12345@I@Z`
- size: `1762`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180036294`

## callees

- `0x1800094c0`
- `0x180016490`
- `0x18001c3b4`
- `0x18001f4c0`
- `0x180020fcc`
- `0x18002392c`
- `0x18002abb4`
- `0x18002c6d0`
- `0x18002d638`
- `0x18002e704`
- `0x18002ead0`
- `0x18002f560`
- `0x1800352d0`
- `0x180035bac`
- `0x180037460`
- `0x180038894`
- `0x180039a1c`
- `0x180043224`
- `0x180056a64`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a5520`

## string_xrefs

- `0x180036103`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036118`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003612d`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036142`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036157`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003616c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036184`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800361aa`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800361bf`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800361d4`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800361e9`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800361fe`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036213`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036228`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003623d`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036252`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036267`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003627c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035d7e`: `SELECT DISTINCT ID, LastUsedTimeStart, PackageFamilyName, AppName FROM PackagedUsageHistory WHERE UserSid=? AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; `
- `0x180035d54`: `SELECT DISTINCT ID, LastUsedTimeStart, PackageFamilyName, AppName FROM PackagedUsageHistory WHERE (UserSid=? OR UserSid=0) AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; `
- `0x180035d13`: `SELECT DISTINCT ID, LastUsedTimeStart, PackageFamilyName, AppName FROM PackagedUsageHistory WHERE UserSid=? AND Capability=? AND AccessBlocked=1 AND LastUsedTimeStop>? ORDER BY LastUsedTimeStop DESC, ID; `
- `0x180035e16`: `SELECT DISTINCT ID, LastUsedTimeStart, BinaryFullPath, AppName FROM NonPackagedUsageHistory WHERE UserSid=? AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; `
- `0x180035def`: `SELECT DISTINCT ID, LastUsedTimeStart, BinaryFullPath, AppName FROM NonPackagedUsageHistory WHERE (UserSid=? OR UserSid=0) AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; `
- `0x180035db1`: `SELECT DISTINCT ID, LastUsedTimeStart, BinaryFullPath, AppName FROM NonPackagedUsageHistory WHERE UserSid=? AND Capability=? AND AccessBlocked=1 AND LastUsedTimeStop>? ORDER BY LastUsedTimeStop DESC, ID; `

## pseudocode

```c
// Hidden C++ exception states: #wind=9
Windows::Internal::CapabilityAccess::Private::SQL *__fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetRecordStubsFromTable(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        char a6)
{
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 KeyFromStringAndTableName; // r15
  __int64 v13; // rax
  __int64 v14; // r12
  StateRepository::Database *v15; // rdi
  int v16; // eax
  Windows::Internal::CapabilityAccess::Private *v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  unsigned __int64 SystemTimeAsUInt64; // rsi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int Row; // eax
  int ColumnUInt64; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // eax
  int v35; // eax
  __int64 v36; // r9
  unsigned int v38; // eax
  bool v39[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v40; // [rsp+28h] [rbp-D8h] BYREF
  struct _GUID v41; // [rsp+30h] [rbp-D0h] BYREF
  int v42; // [rsp+40h] [rbp-C0h]
  StateRepository::Database *v43; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v44; // [rsp+50h] [rbp-B0h]
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v46; // [rsp+60h] [rbp-A0h]
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v48; // [rsp+70h] [rbp-90h]
  Windows::Internal::CapabilityAccess::Private::SQL *v49; // [rsp+78h] [rbp-88h]
  _BYTE v50[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v51[48]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v56; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v57[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v58; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v59; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v60[2]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v49 = a1;
  v42 = 1;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x806,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      *(int *)v39);
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(&v47);
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v47, &v45, a3);
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  v42 = 1;
  if ( *(_BYTE *)(v45 + 489) || a5 )
  {
    std::make_shared<StateRepository::Database,>(&v43);
    v40 = 0;
    v41.Data1 = 42114603;
    *(_DWORD *)&v41.Data2 = 1241481273;
    *(_DWORD *)v41.Data4 = 1206372760;
    *(_DWORD *)&v41.Data4[4] = 275808188;
    v10 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                      v50,
                      &v43);
    Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(
      (Windows::Internal::CapabilityAccess::Private::SQL *)v51,
      v10,
      &v41,
      0);
    v11 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
            &v41,
            &v43);
    KeyFromStringAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
                                  a2,
                                  "Users",
                                  v11,
                                  0);
    v13 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
            &v41,
            &v43);
    v14 = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(a3, "Capabilities", v13, 0);
    if ( a5 )
    {
      if ( a5 != 1 )
      {
        v38 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x86C,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)v38,
          *(int *)v39);
      }
      if ( (a6 & 1) != 0 )
      {
        v15 = v43;
        v16 = StateRepository::Database::PrepareFromCache(
                v43,
                "SELECT DISTINCT ID, LastUsedTimeStart, PackageFamilyName, AppName FROM PackagedUsageHistory WHERE UserSi"
                "d=? AND Capability=? AND AccessBlocked=1 AND LastUsedTimeStop>? ORDER BY LastUsedTimeStop DESC, ID; ",
                (struct StateRepository::Statement *)&v40);
        v17 = retaddr;
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x84E,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v16,
            *(int *)v39);
      }
      else if ( (a6 & 2) != 0 && *(_BYTE *)(v45 + 489) )
      {
        v15 = v43;
        v18 = StateRepository::Database::PrepareFromCache(
                v43,
                "SELECT DISTINCT ID, LastUsedTimeStart, PackageFamilyName, AppName FROM PackagedUsageHistory WHERE (UserS"
                "id=? OR UserSid=0) AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; ",
                (struct StateRepository::Statement *)&v40);
        v17 = retaddr;
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x85A,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v18,
            *(int *)v39);
      }
      else
      {
        v15 = v43;
        v19 = StateRepository::Database::PrepareFromCache(
                v43,
                "SELECT DISTINCT ID, LastUsedTimeStart, PackageFamilyName, AppName FROM PackagedUsageHistory WHERE UserSi"
                "d=? AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; ",
                (struct StateRepository::Statement *)&v40);
        v17 = retaddr;
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x865,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v19,
            *(int *)v39);
      }
    }
    else if ( (a6 & 1) != 0 )
    {
      v15 = v43;
      v20 = StateRepository::Database::PrepareFromCache(
              v43,
              "SELECT DISTINCT ID, LastUsedTimeStart, BinaryFullPath, AppName FROM NonPackagedUsageHistory WHERE UserSid="
              "? AND Capability=? AND AccessBlocked=1 AND LastUsedTimeStop>? ORDER BY LastUsedTimeStop DESC, ID; ",
              (struct StateRepository::Statement *)&v40);
      v17 = retaddr;
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x82E,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v20,
          *(int *)v39);
    }
    else if ( (a6 & 2) != 0 && *(_BYTE *)(v45 + 489) )
    {
      v15 = v43;
      v21 = StateRepository::Database::PrepareFromCache(
              v43,
              "SELECT DISTINCT ID, LastUsedTimeStart, BinaryFullPath, AppName FROM NonPackagedUsageHistory WHERE (UserSid"
              "=? OR UserSid=0) AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; ",
              (struct StateRepository::Statement *)&v40);
      v17 = retaddr;
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x83A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v21,
          *(int *)v39);
    }
    else
    {
      v15 = v43;
      v22 = StateRepository::Database::PrepareFromCache(
              v43,
              "SELECT DISTINCT ID, LastUsedTimeStart, BinaryFullPath, AppName FROM NonPackagedUsageHistory WHERE UserSid="
              "? AND Capability=? AND AccessBlocked=0 AND LastUsedTimeStart>? ORDER BY LastUsedTimeStop DESC, ID; ",
              (struct StateRepository::Statement *)&v40);
      v17 = retaddr;
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x845,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v22,
          *(int *)v39);
    }
    v39[0] = 1;
    SystemTimeAsUInt64 = Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(v17);
    v24 = StateRepository::Statement::Bind((StateRepository::Statement *)&v40, 1, KeyFromStringAndTableName);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x872,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v24,
        *(int *)v39);
    v25 = StateRepository::Statement::Bind((StateRepository::Statement *)&v40, 2, v14);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x873,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v25,
        *(int *)v39);
    v26 = StateRepository::Statement::Bind((StateRepository::Statement *)&v40, 3, SystemTimeAsUInt64 - 6048000000000LL);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x876,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v26,
        *(int *)v39);
    *(_QWORD *)a1 = 0;
    *((_QWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 2) = 0;
    v42 = 3;
    Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v40, v39);
    if ( Row < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x87F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)Row,
        *(int *)v39);
    v60[0] = 0;
    v60[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v60[0]) = 0;
    while ( v39[0] )
    {
      v53 = 0;
      v54 = 0;
      v55 = 7;
      LOWORD(v53) = 0;
      v56 = 0;
      v57[0] = 0;
      v57[1] = 0;
      v58 = 0;
      v59 = 0;
      v52 = a5;
      ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v40, 0, &v58);
      if ( ColumnUInt64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x888,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)ColumnUInt64,
          *(int *)v39);
      v29 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v40, 1, &v59);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x889,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v29,
          *(int *)v39);
      v30 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v40, 2, &v56);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x88C,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v30,
          *(int *)v39);
      v31 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v40, 3, v57);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x88D,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v31,
          *(int *)v39);
      LOBYTE(v33) = 3;
      LOBYTE(v32) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
        v32,
        v33);
      if ( *((_QWORD *)a1 + 1) == *((_QWORD *)a1 + 2) )
      {
        std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub>::_Emplace_reallocate<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub &>(
          a1,
          *((_QWORD *)a1 + 1),
          &v52);
      }
      else
      {
        Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub::SqliteUsageRecordStub(
          *((Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub **)a1 + 1),
          (const struct Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub *)&v52);
        *((_QWORD *)a1 + 1) += 80LL;
      }
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 4) >= a4 )
      {
        std::wstring::_Tidy_deallocate(&v53);
        break;
      }
      v34 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v40, v39);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8C0,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v34,
          *(int *)v39);
      std::wstring::_Tidy_deallocate(&v53);
    }
    StateRepository::Database::AddToCache(v15, (struct StateRepository::Statement *)&v40);
    v35 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v40);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8C5,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v35,
        *(int *)v39);
    LOBYTE(v36) = v39[0];
    std::_Sort_unchecked_Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub____lambda_20eba8c7d7325dda522c5d11b61e0926___(
      *(_QWORD *)a1,
      *((_QWORD *)a1 + 1),
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 4),
      v36);
    std::wstring::_Tidy_deallocate(v60);
    Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v51);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v40);
    if ( v44 )
      std::_Ref_count_base::_Decref(v44);
  }
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  return a1;
}

```

## disassembly

```asm
0x180035bac  mov     [rsp-8+arg_18], rbx
0x180035bb1  push    rbp
0x180035bb2  push    rsi
0x180035bb3  push    rdi
0x180035bb4  push    r12
0x180035bb6  push    r13
0x180035bb8  push    r14
0x180035bba  push    r15
0x180035bbc  lea     rbp, [rsp-40h]
0x180035bc1  sub     rsp, 140h
0x180035bc8  mov     rax, cs:__security_cookie
0x180035bcf  xor     rax, rsp
0x180035bd2  mov     [rbp+70h+var_40], rax
0x180035bd6  mov     r13, r9
0x180035bd9  mov     rsi, r8
0x180035bdc  mov     r15, rdx
0x180035bdf  mov     rbx, rcx
0x180035be2  mov     [rsp+170h+var_F8], rcx
0x180035be7  mov     r14d, 1
0x180035bed  mov     [rsp+170h+var_130], r14d
0x180035bf2  mov     rdi, [rbp+78h]
0x180035bf6  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180035bfb  test    al, al
0x180035bfd  jz      loc_18003617E
0x180035c03  lea     rcx, [rsp+170h+var_108]
0x180035c08  call    ?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)
0x180035c0d  nop
0x180035c0e  mov     r8, rsi
0x180035c11  lea     rdx, [rsp+170h+var_118]
0x180035c16  mov     rcx, [rsp+170h+var_108]
0x180035c1b  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &)
0x180035c20  nop
0x180035c21  xor     edi, edi
0x180035c23  mov     [rbx], rdi
0x180035c26  mov     [rbx+8], rdi
0x180035c2a  mov     [rbx+10h], rdi
0x180035c2e  mov     [rsp+170h+var_130], r14d
0x180035c33  mov     r14d, [rbp+70h+arg_20]
0x180035c3a  mov     rax, [rsp+170h+var_118]
0x180035c3f  cmp     [rax+1E9h], dil
0x180035c46  jnz     short loc_180035C51
0x180035c48  test    r14d, r14d
0x180035c4b  jz      loc_1800360A9
0x180035c51  lea     rcx, [rsp+170h+var_128]
0x180035c56  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180035c5b  nop
0x180035c5c  mov     [rsp+170h+var_148], rdi
0x180035c61  mov     [rsp+170h+var_140], 2829E2Bh
0x180035c69  mov     [rsp+170h+var_13C], 49FF8039h
0x180035c71  mov     [rsp+170h+var_138], 47E7C998h
0x180035c79  mov     [rsp+170h+var_134], 10707FBCh
0x180035c81  lea     rdx, [rsp+170h+var_128]
0x180035c86  lea     rcx, [rbp+70h+var_F0]
0x180035c8a  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180035c8f  xor     r9d, r9d
0x180035c92  lea     r8, [rsp+170h+var_140]
0x180035c97  mov     rdx, rax
0x180035c9a  lea     rcx, [rbp+70h+var_E0]
0x180035c9e  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180035ca3  nop
0x180035ca4  lea     rdx, [rsp+170h+var_128]
0x180035ca9  lea     rcx, [rsp+170h+var_140]
0x180035cae  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180035cb3  xor     r9d, r9d
0x180035cb6  mov     r8, rax
0x180035cb9  lea     rdx, aUsers; "Users"
0x180035cc0  mov     rcx, r15
0x180035cc3  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180035cc8  mov     r15, rax
0x180035ccb  lea     rdx, [rsp+170h+var_128]
0x180035cd0  lea     rcx, [rsp+170h+var_140]
0x180035cd5  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180035cda  xor     r9d, r9d
0x180035cdd  mov     r8, rax
0x180035ce0  lea     rdx, aCapabilities_0; "Capabilities"
0x180035ce7  mov     rcx, rsi
0x180035cea  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180035cef  mov     r12, rax
0x180035cf2  test    r14d, r14d
0x180035cf5  jz      loc_180035DA3
0x180035cfb  cmp     r14d, 1
0x180035cff  jnz     loc_180036199
0x180035d05  test    [rbp+70h+arg_28], r14b
0x180035d0c  jz      short loc_180035D38
0x180035d0e  lea     r8, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180035d13  lea     rdx, aSelectDistinct_3; "SELECT DISTINCT ID, LastUsedTimeStart, "...
0x180035d1a  mov     rdi, [rsp+170h+var_128]
0x180035d1f  mov     rcx, rdi; this
0x180035d22  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180035d27  mov     rcx, [rbp+78h]; this
0x180035d2b  test    eax, eax
0x180035d2d  js      loc_180036115
0x180035d33  jmp     loc_180035E36
0x180035d38  test    [rbp+70h+arg_28], 2
0x180035d3f  jz      short loc_180035D79
0x180035d41  mov     rax, [rsp+170h+var_118]
0x180035d46  cmp     [rax+1E9h], dil
0x180035d4d  jz      short loc_180035D79
0x180035d4f  lea     r8, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180035d54  lea     rdx, aSelectDistinct_6; "SELECT DISTINCT ID, LastUsedTimeStart, "...
0x180035d5b  mov     rdi, [rsp+170h+var_128]
0x180035d60  mov     rcx, rdi; this
0x180035d63  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180035d68  mov     rcx, [rbp+78h]; this
0x180035d6c  test    eax, eax
0x180035d6e  js      loc_18003612A
0x180035d74  jmp     loc_180035E36
0x180035d79  lea     r8, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180035d7e  lea     rdx, aSelectDistinct_7; "SELECT DISTINCT ID, LastUsedTimeStart, "...
0x180035d85  mov     rdi, [rsp+170h+var_128]
0x180035d8a  mov     rcx, rdi; this
0x180035d8d  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180035d92  mov     rcx, [rbp+78h]; this
0x180035d96  test    eax, eax
0x180035d98  js      loc_18003613F
0x180035d9e  jmp     loc_180035E36
0x180035da3  test    [rbp+70h+arg_28], 1
0x180035daa  jz      short loc_180035DD3
0x180035dac  lea     r8, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180035db1  lea     rdx, aSelectDistinct_5; "SELECT DISTINCT ID, LastUsedTimeStart, "...
0x180035db8  mov     rdi, [rsp+170h+var_128]
0x180035dbd  mov     rcx, rdi; this
0x180035dc0  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180035dc5  mov     rcx, [rbp+78h]; this
0x180035dc9  test    eax, eax
0x180035dcb  js      loc_180036154
0x180035dd1  jmp     short loc_180035E36
0x180035dd3  test    [rbp+70h+arg_28], 2
0x180035dda  jz      short loc_180035E11
0x180035ddc  mov     rax, [rsp+170h+var_118]
0x180035de1  cmp     [rax+1E9h], dil
0x180035de8  jz      short loc_180035E11
0x180035dea  lea     r8, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180035def  lea     rdx, aSelectDistinct_9; "SELECT DISTINCT ID, LastUsedTimeStart, "...
0x180035df6  mov     rdi, [rsp+170h+var_128]
0x180035dfb  mov     rcx, rdi; this
0x180035dfe  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180035e03  mov     rcx, [rbp+78h]; this
0x180035e07  test    eax, eax
0x180035e09  js      loc_180036169
0x180035e0f  jmp     short loc_180035E36
0x180035e11  lea     r8, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180035e16  lea     rdx, aSelectDistinct_0; "SELECT DISTINCT ID, LastUsedTimeStart, "...
0x180035e1d  mov     rdi, [rsp+170h+var_128]
0x180035e22  mov     rcx, rdi; this
0x180035e25  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180035e2a  mov     rcx, [rbp+78h]; this
0x180035e2e  test    eax, eax
0x180035e30  js      loc_1800361BC
0x180035e36  mov     [rsp+170h+var_150], 1; int
0x180035e3b  call    ?GetSystemTimeAsUInt64@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(void)
0x180035e40  mov     rsi, rax
0x180035e43  mov     r8, r15; __int64
0x180035e46  mov     edx, 1; int
0x180035e4b  lea     rcx, [rsp+170h+var_148]; this
0x180035e50  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180035e55  mov     rcx, [rbp+78h]; this
0x180035e59  xor     r15d, r15d
0x180035e5c  test    eax, eax
0x180035e5e  js      loc_1800361D1
0x180035e64  mov     r8, r12; __int64
0x180035e67  lea     r12d, [r15+2]
0x180035e6b  mov     edx, r12d; int
0x180035e6e  lea     rcx, [rsp+170h+var_148]; this
0x180035e73  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180035e78  mov     rcx, [rbp+78h]; this
0x180035e7c  test    eax, eax
0x180035e7e  js      loc_1800361E6
0x180035e84  mov     r8, 0FFFFFA7FD71BC000h
0x180035e8e  add     r8, rsi; __int64
0x180035e91  lea     esi, [r15+3]
0x180035e95  mov     edx, esi; int
0x180035e97  lea     rcx, [rsp+170h+var_148]; this
0x180035e9c  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180035ea1  mov     rcx, [rbp+78h]; this
0x180035ea5  test    eax, eax
0x180035ea7  js      loc_1800361FB
0x180035ead  mov     [rbx], r15
0x180035eb0  mov     [rbx+8], r15
0x180035eb4  mov     [rbx+10h], r15
0x180035eb8  mov     [rsp+170h+var_130], esi
0x180035ebc  lea     rdx, [rsp+170h+var_150]; bool *
0x180035ec1  lea     rcx, [rsp+170h+var_148]; this
0x180035ec6  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x180035ecb  mov     rcx, [rbp+78h]; this
0x180035ecf  test    eax, eax
0x180035ed1  js      loc_180036210
0x180035ed7  xorps   xmm0, xmm0
0x180035eda  movups  [rbp+70h+var_60], xmm0
0x180035ede  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180035ee6  movdqu  [rbp+70h+var_50], xmm1
0x180035eeb  mov     word ptr [rbp+70h+var_60], r15w
0x180035ef0  jmp     loc_180036022
0x180035ef5  xor     eax, eax
0x180035ef7  mov     [rbp+70h+var_B0], rax
0x180035efb  xorps   xmm0, xmm0
0x180035efe  movups  [rbp+70h+var_A8], xmm0
0x180035f02  mov     [rbp+70h+var_98], r15
0x180035f06  mov     [rbp+70h+var_90], 7
0x180035f0e  mov     word ptr [rbp+70h+var_A8], r15w
0x180035f13  mov     [rbp+70h+var_88], r15
0x180035f17  mov     [rbp+70h+var_80], r15
0x180035f1b  mov     [rbp+70h+var_78], r15
0x180035f1f  mov     [rbp+70h+var_70], r15
0x180035f23  mov     [rbp+70h+var_68], r15
0x180035f27  mov     dword ptr [rbp+70h+var_B0], r14d
0x180035f2b  lea     r8, [rbp+70h+var_70]; unsigned __int64 *
0x180035f2f  xor     edx, edx; int
0x180035f31  lea     rcx, [rsp+170h+var_148]; this
0x180035f36  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035f3b  mov     rcx, [rbp+78h]; this
0x180035f3f  test    eax, eax
0x180035f41  js      loc_180036100
0x180035f47  lea     r8, [rbp+70h+var_68]; unsigned __int64 *
0x180035f4b  mov     edx, 1; int
0x180035f50  lea     rcx, [rsp+170h+var_148]; this
0x180035f55  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035f5a  mov     rcx, [rbp+78h]; this
0x180035f5e  test    eax, eax
0x180035f60  js      loc_180036279
0x180035f66  lea     r8, [rbp+70h+var_88]; unsigned __int64 *
0x180035f6a  mov     edx, r12d; int
0x180035f6d  lea     rcx, [rsp+170h+var_148]; this
0x180035f72  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035f77  mov     rcx, [rbp+78h]; this
0x180035f7b  test    eax, eax
0x180035f7d  js      loc_180036264
0x180035f83  lea     r8, [rbp+70h+var_80]; unsigned __int64 *
0x180035f87  mov     edx, esi; int
0x180035f89  lea     rcx, [rsp+170h+var_148]; this
0x180035f8e  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035f93  mov     rcx, [rbp+78h]; this
0x180035f97  test    eax, eax
0x180035f99  js      loc_18003624F
0x180035f9f  mov     r8b, sil
0x180035fa2  mov     dl, 1
0x180035fa4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x180035fab  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180035fb0  mov     rax, [rbx+8]
0x180035fb4  cmp     rax, [rbx+10h]
0x180035fb8  jz      short loc_180035FCD
0x180035fba  lea     rdx, [rbp+70h+var_B0]; struct Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub *
0x180035fbe  mov     rcx, rax; this
0x180035fc1  call    ??0SqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@AEBU012345@@Z; Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub::SqliteUsageRecordStub(Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub const &)
0x180035fc6  add     qword ptr [rbx+8], 50h ; 'P'
0x180035fcb  jmp     short loc_180035FDC
0x180035fcd  lea     r8, [rbp+70h+var_B0]
0x180035fd1  mov     rdx, rax
0x180035fd4  mov     rcx, rbx
0x180035fd7  call    ??$_Emplace_reallocate@AEAUSqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@?$vector@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@V?$allocator@USqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEAAPEAUSqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@QEAU234567@AEAU234567@@Z; std::vector<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub>::_Emplace_reallocate<Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub &>(Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub * const,Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub &)
0x180035fdc  mov     rax, [rbx+8]
0x180035fe0  sub     rax, [rbx]
0x180035fe3  sar     rax, 4
0x180035fe7  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180035ff1  imul    rax, rcx
0x180035ff5  cmp     rax, r13
0x180035ff8  jnb     loc_1800360F2
0x180035ffe  lea     rdx, [rsp+170h+var_150]; bool *
0x180036003  lea     rcx, [rsp+170h+var_148]; this
0x180036008  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x18003600d  mov     rcx, [rbp+78h]; this
0x180036011  test    eax, eax
0x180036013  js      loc_18003623A
0x180036019  lea     rcx, [rbp+70h+var_A8]
0x18003601d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036022  cmp     [rsp+170h+var_150], r15b
0x180036027  jnz     loc_180035EF5
0x18003602d  lea     rdx, [rsp+170h+var_148]; struct StateRepository::Statement *
0x180036032  mov     rcx, rdi; this
0x180036035  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18003603a  lea     rcx, [rsp+170h+var_148]; this
0x18003603f  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180036044  mov     rcx, [rbp+78h]; this
0x180036048  test    eax, eax
0x18003604a  js      loc_180036225
0x180036050  mov     rdx, [rbx+8]
0x180036054  mov     r8, rdx
0x180036057  sub     r8, [rbx]
0x18003605a  sar     r8, 4
0x18003605e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180036068  imul    r8, rax
0x18003606c  mov     r9b, [rsp+170h+var_150]
0x180036071  mov     rcx, [rbx]
0x180036074  call    std___Sort_unchecked_Windows__Internal__CapabilityAccess__Private__SQL__SqliteUsageRecordStub____lambda_20eba8c7d7325dda522c5d11b61e0926___
0x180036079  nop
0x18003607a  lea     rcx, [rbp+70h+var_60]
0x18003607e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036083  nop
0x180036084  lea     rcx, [rbp+70h+var_E0]; this
0x180036088  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x18003608d  nop
0x18003608e  lea     rcx, [rsp+170h+var_148]; this
0x180036093  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180036098  nop
0x180036099  mov     rcx, [rsp+170h+var_120]; this
0x18003609e  test    rcx, rcx
0x1800360a1  jz      short loc_1800360A9
0x1800360a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800360a8  nop
0x1800360a9  mov     rcx, [rsp+170h+var_110]; this
  ... truncated ...
```
