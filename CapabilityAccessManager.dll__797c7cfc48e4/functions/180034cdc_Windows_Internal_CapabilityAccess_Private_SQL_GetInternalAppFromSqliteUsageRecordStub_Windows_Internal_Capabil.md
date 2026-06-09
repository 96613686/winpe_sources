# Windows::Internal::CapabilityAccess::Private::SQL::GetInternalAppFromSqliteUsageRecordStub(Windows::Internal::CapabilityAccess::Private::SQL::SqliteUsageRecordStub const &)

- ea: `0x180034cdc`
- end: `0x1800352c8`
- name: `?GetInternalAppFromSqliteUsageRecordStub@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AUInternalApp@12345@AEBUSqliteUsageRecordStub@12345@@Z`
- size: `1516`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x180034c4c`
- `0x18008b230`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x180020fcc`
- `0x18002392c`
- `0x18002d638`
- `0x18002e704`
- `0x18002e9dc`
- `0x18002f560`
- `0x18002f93c`
- `0x18002f978`
- `0x180034cdc`
- `0x1800363b4`
- `0x180037460`
- `0x180039a1c`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a5520`

## string_xrefs

- `0x180034d26`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034dd8`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034e06`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034e37`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034e5f`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034e9c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034eca`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034ef7`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034f27`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180034f5c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800350a7`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800350d5`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035106`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003512e`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035163`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035191`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800351c6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800352b6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003508c`: `SELECT PackageFamilyName, AccessGUID FROM PackagedUsageHistory WHERE ID=?; `
- `0x180034dbd`: `SELECT FileID, ProgramID, BinaryFullPath, AccessGUID FROM NonPackagedUsageHistory WHERE ID=?; `
- `0x180035032`: `AccessGUIDs`
- `0x180035223`: `AccessGUIDs`
- `0x180034ff9`: `BinaryFullPaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Windows::Internal::CapabilityAccess::Private::SQL *__fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetInternalAppFromSqliteUsageRecordStub(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        __int64 a2)
{
  __int64 v4; // rax
  int v5; // esi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  int Row; // eax
  int ColumnUInt64; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 StringFromKeyAndTableName; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  bool v33[4]; // [rsp+20h] [rbp-99h] BYREF
  __int64 v34; // [rsp+28h] [rbp-91h] BYREF
  _DWORD v35[4]; // [rsp+30h] [rbp-89h] BYREF
  StateRepository::Database *v36; // [rsp+40h] [rbp-79h] BYREF
  std::_Ref_count_base *v37; // [rsp+48h] [rbp-71h]
  unsigned __int64 v38; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v39[2]; // [rsp+58h] [rbp-61h] BYREF
  int v40; // [rsp+68h] [rbp-51h]
  unsigned __int64 v41; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int64 v42[3]; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v43[48]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v44[32]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v42[1] = (unsigned __int64)a1;
  v40 = 0;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E7,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      *(int *)v33);
  Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp(a1);
  v40 = 1;
  std::make_shared<StateRepository::Database,>(&v36);
  v35[0] = -82715569;
  v35[1] = 1081603707;
  v35[2] = -47336826;
  v35[3] = -1471923194;
  v4 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
         v39,
         &v36);
  Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(v43, v4, v35, 0);
  v34 = 0;
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 != 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)0x80070057LL,
        *(int *)v33);
    if ( *(_QWORD *)(a2 + 24) )
    {
      std::wstring::operator=((char *)a1 + 32, a2 + 8);
    }
    else
    {
      v22 = StateRepository::Database::PrepareFromCache(
              v36,
              "SELECT PackageFamilyName, AccessGUID FROM PackagedUsageHistory WHERE ID=?; ",
              (struct StateRepository::Statement *)&v34);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91D,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v22,
          *(int *)v33);
      v23 = StateRepository::Statement::Bind((StateRepository::Statement *)&v34, 1, *(_QWORD *)(a2 + 64));
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91E,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v23,
          *(int *)v33);
      v33[0] = 0;
      Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v34, v33);
      if ( Row < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x922,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)Row,
          *(int *)v33);
      if ( !v33[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x923,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)0x80070002LL,
          *(int *)v33);
      v39[0] = 0;
      v38 = 0;
      ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v34, 0, v39);
      if ( ColumnUInt64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x928,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)ColumnUInt64,
          *(int *)v33);
      v26 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v34, 1, &v38);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x929,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v26,
          *(int *)v33);
      StateRepository::Database::AddToCache(v36, (struct StateRepository::Statement *)&v34);
      v27 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v34);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x92D,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v27,
          *(int *)v33);
      v28 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v35,
              &v36);
      StringFromKeyAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                                    v44,
                                    v39[0],
                                    "PackageFamilyNames",
                                    v28);
      std::wstring::operator=((char *)a1 + 32, StringFromKeyAndTableName);
      std::wstring::_Tidy_deallocate(v44);
      v30 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v35,
              &v36);
      v31 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
              v44,
              v38,
              "AccessGUIDs",
              v30);
      std::wstring::operator=((char *)a1 + 224, v31);
      std::wstring::_Tidy_deallocate(v44);
    }
    v5 = 1;
  }
  else
  {
    v5 = 2;
    if ( *(_QWORD *)(a2 + 24) )
    {
      std::wstring::operator=(a1, a2 + 8);
    }
    else
    {
      v6 = StateRepository::Database::PrepareFromCache(
             v36,
             "SELECT FileID, ProgramID, BinaryFullPath, AccessGUID FROM NonPackagedUsageHistory WHERE ID=?; ",
             (struct StateRepository::Statement *)&v34);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8F6,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v6,
          *(int *)v33);
      v7 = StateRepository::Statement::Bind((StateRepository::Statement *)&v34, 1, *(_QWORD *)(a2 + 64));
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8F7,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v7,
          *(int *)v33);
      v33[0] = 0;
      v8 = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v34, v33);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8FB,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v8,
          *(int *)v33);
      if ( !v33[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8FC,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)0x80070002LL,
          *(int *)v33);
      v41 = 0;
      v42[0] = 0;
      v38 = 0;
      v39[0] = 0;
      v9 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v34, 0, &v41);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x903,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v9,
          *(int *)v33);
      v10 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v34, 1, v42);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x904,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v10,
          *(int *)v33);
      v11 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v34, 2, &v38);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x905,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v11,
          *(int *)v33);
      v12 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v34, 3, v39);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x906,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v12,
          *(int *)v33);
      StateRepository::Database::AddToCache(v36, (struct StateRepository::Statement *)&v34);
      v13 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v34);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x90A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v13,
          *(int *)v33);
      v14 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v35,
              &v36);
      v15 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(v44, v41, "FileIDs", v14);
      std::wstring::operator=((char *)a1 + 160, v15);
      std::wstring::_Tidy_deallocate(v44);
      v16 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v35,
              &v36);
      v17 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
              v44,
              v42[0],
              "ProgramIDs",
              v16);
      std::wstring::operator=((char *)a1 + 192, v17);
      std::wstring::_Tidy_deallocate(v44);
      v18 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v35,
              &v36);
      v19 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
              v44,
              v38,
              "BinaryFullPaths",
              v18);
      std::wstring::operator=(a1, v19);
      std::wstring::_Tidy_deallocate(v44);
      v20 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v35,
              &v36);
      v21 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
              v44,
              v39[0],
              "AccessGUIDs",
              v20);
      std::wstring::operator=((char *)a1 + 224, v21);
      std::wstring::_Tidy_deallocate(v44);
    }
  }
  *((_DWORD *)a1 + 64) = v5;
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v34);
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v43);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  return a1;
}

```

## disassembly

```asm
0x180034cdc  mov     [rsp-8+arg_10], rbx
0x180034ce1  push    rbp
0x180034ce2  push    rsi
0x180034ce3  push    rdi
0x180034ce4  push    r14
0x180034ce6  push    r15
0x180034ce8  lea     rbp, [rsp-37h]
0x180034ced  sub     rsp, 0F0h
0x180034cf4  mov     rax, cs:__security_cookie
0x180034cfb  xor     rax, rsp
0x180034cfe  mov     [rbp+57h+var_30], rax
0x180034d02  mov     rdi, rdx
0x180034d05  mov     rbx, rcx
0x180034d08  mov     [rbp+57h+var_90], rcx
0x180034d0c  xor     r14d, r14d
0x180034d0f  mov     [rbp+57h+var_A8], r14d
0x180034d13  mov     rsi, [rbp+5Fh]
0x180034d17  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180034d1c  test    al, al
0x180034d1e  jnz     short loc_180034D3B
0x180034d20  mov     r9d, 80004001h; char *
0x180034d26  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034d2d  mov     edx, 8E7h; void *
0x180034d32  mov     rcx, rsi; this
0x180034d35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034d3b  mov     rcx, rbx; this
0x180034d3e  call    ??0InternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp(void)
0x180034d43  mov     r15d, 1
0x180034d49  mov     [rbp+57h+var_A8], r15d
0x180034d4d  lea     rcx, [rbp+57h+var_D0]
0x180034d51  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180034d56  nop
0x180034d57  mov     [rsp+110h+var_E0], 0FB11DC4Fh
0x180034d5f  mov     [rsp+110h+var_DC], 4077F67Bh
0x180034d67  mov     [rsp+110h+var_D8], 0FD2DB286h
0x180034d6f  mov     [rbp+57h+var_D4], 0A8443C06h
0x180034d76  lea     rdx, [rbp+57h+var_D0]
0x180034d7a  lea     rcx, [rbp+57h+var_B8]
0x180034d7e  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180034d83  xor     r9d, r9d
0x180034d86  lea     r8, [rsp+110h+var_E0]
0x180034d8b  mov     rdx, rax
0x180034d8e  lea     rcx, [rbp+57h+var_80]
0x180034d92  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180034d97  nop
0x180034d98  mov     [rsp+110h+var_E8], r14
0x180034d9d  cmp     [rdi], r14d
0x180034da0  jnz     loc_180035070
0x180034da6  lea     rdx, [rdi+8]
0x180034daa  lea     esi, [r15+1]
0x180034dae  cmp     [rdx+10h], r14
0x180034db2  jnz     loc_180035063
0x180034db8  lea     r8, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x180034dbd  lea     rdx, aSelectFileidPr; "SELECT FileID, ProgramID, BinaryFullPat"...
0x180034dc4  mov     rcx, [rbp+57h+var_D0]; this
0x180034dc8  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180034dcd  mov     rcx, [rbp+5Fh]; this
0x180034dd1  test    eax, eax
0x180034dd3  jns     short loc_180034DEA
0x180034dd5  mov     r9d, eax; char *
0x180034dd8  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034ddf  mov     edx, 8F6h; void *
0x180034de4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034dea  mov     r8, [rdi+40h]; __int64
0x180034dee  mov     edx, r15d; int
0x180034df1  lea     rcx, [rsp+110h+var_E8]; this
0x180034df6  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180034dfb  mov     rcx, [rbp+5Fh]; this
0x180034dff  test    eax, eax
0x180034e01  jns     short loc_180034E18
0x180034e03  mov     r9d, eax; char *
0x180034e06  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034e0d  mov     edx, 8F7h; void *
0x180034e12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034e18  mov     [rsp+110h+var_F0], r14b; int
0x180034e1d  lea     rdx, [rsp+110h+var_F0]; bool *
0x180034e22  lea     rcx, [rsp+110h+var_E8]; this
0x180034e27  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x180034e2c  mov     rcx, [rbp+5Fh]; this
0x180034e30  test    eax, eax
0x180034e32  jns     short loc_180034E49
0x180034e34  mov     r9d, eax; char *
0x180034e37  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034e3e  mov     edx, 8FBh; void *
0x180034e43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034e49  cmp     [rsp+110h+var_F0], r14b
0x180034e4e  setz    al
0x180034e51  mov     rcx, [rbp+5Fh]; this
0x180034e55  test    al, al
0x180034e57  jz      short loc_180034E71
0x180034e59  mov     r9d, 80070002h; char *
0x180034e5f  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034e66  mov     edx, 8FCh; void *
0x180034e6b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034e71  mov     [rbp+57h+var_A0], r14
0x180034e75  mov     [rbp+57h+var_98], r14
0x180034e79  mov     [rbp+57h+var_C0], r14
0x180034e7d  mov     [rbp+57h+var_B8], r14
0x180034e81  lea     r8, [rbp+57h+var_A0]; unsigned __int64 *
0x180034e85  xor     edx, edx; int
0x180034e87  lea     rcx, [rsp+110h+var_E8]; this
0x180034e8c  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180034e91  mov     rcx, [rbp+5Fh]; this
0x180034e95  test    eax, eax
0x180034e97  jns     short loc_180034EAE
0x180034e99  mov     r9d, eax; char *
0x180034e9c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034ea3  mov     edx, 903h; void *
0x180034ea8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034eae  lea     r8, [rbp+57h+var_98]; unsigned __int64 *
0x180034eb2  mov     edx, r15d; int
0x180034eb5  lea     rcx, [rsp+110h+var_E8]; this
0x180034eba  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180034ebf  mov     rcx, [rbp+5Fh]; this
0x180034ec3  test    eax, eax
0x180034ec5  jns     short loc_180034EDC
0x180034ec7  mov     r9d, eax; char *
0x180034eca  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034ed1  mov     edx, 904h; void *
0x180034ed6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034edc  lea     r8, [rbp+57h+var_C0]; unsigned __int64 *
0x180034ee0  mov     edx, esi; int
0x180034ee2  lea     rcx, [rsp+110h+var_E8]; this
0x180034ee7  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180034eec  mov     rcx, [rbp+5Fh]; this
0x180034ef0  test    eax, eax
0x180034ef2  jns     short loc_180034F09
0x180034ef4  mov     r9d, eax; char *
0x180034ef7  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034efe  mov     edx, 905h; void *
0x180034f03  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034f09  lea     r8, [rbp+57h+var_B8]; unsigned __int64 *
0x180034f0d  mov     edx, 3; int
0x180034f12  lea     rcx, [rsp+110h+var_E8]; this
0x180034f17  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180034f1c  mov     rcx, [rbp+5Fh]; this
0x180034f20  test    eax, eax
0x180034f22  jns     short loc_180034F39
0x180034f24  mov     r9d, eax; char *
0x180034f27  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034f2e  mov     edx, 906h; void *
0x180034f33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034f39  lea     rdx, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x180034f3e  mov     rcx, [rbp+57h+var_D0]; this
0x180034f42  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180034f47  lea     rcx, [rsp+110h+var_E8]; this
0x180034f4c  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180034f51  mov     rcx, [rbp+5Fh]; this
0x180034f55  test    eax, eax
0x180034f57  jns     short loc_180034F6E
0x180034f59  mov     r9d, eax; char *
0x180034f5c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180034f63  mov     edx, 90Ah; void *
0x180034f68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034f6e  lea     rdx, [rbp+57h+var_D0]
0x180034f72  lea     rcx, [rsp+110h+var_E0]
0x180034f77  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180034f7c  mov     r9, rax
0x180034f7f  lea     r8, aFileids; "FileIDs"
0x180034f86  mov     rdx, [rbp+57h+var_A0]
0x180034f8a  lea     rcx, [rbp+57h+var_50]
0x180034f8e  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180034f93  lea     rcx, [rbx+0A0h]
0x180034f9a  mov     rdx, rax
0x180034f9d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034fa2  lea     rcx, [rbp+57h+var_50]
0x180034fa6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034fab  lea     rdx, [rbp+57h+var_D0]
0x180034faf  lea     rcx, [rsp+110h+var_E0]
0x180034fb4  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180034fb9  mov     r9, rax
0x180034fbc  lea     r8, aProgramids; "ProgramIDs"
0x180034fc3  mov     rdx, [rbp+57h+var_98]
0x180034fc7  lea     rcx, [rbp+57h+var_50]
0x180034fcb  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180034fd0  lea     rcx, [rbx+0C0h]
0x180034fd7  mov     rdx, rax
0x180034fda  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034fdf  lea     rcx, [rbp+57h+var_50]
0x180034fe3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034fe8  lea     rdx, [rbp+57h+var_D0]
0x180034fec  lea     rcx, [rsp+110h+var_E0]
0x180034ff1  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180034ff6  mov     r9, rax
0x180034ff9  lea     r8, aBinaryfullpath; "BinaryFullPaths"
0x180035000  mov     rdx, [rbp+57h+var_C0]
0x180035004  lea     rcx, [rbp+57h+var_50]
0x180035008  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x18003500d  mov     rdx, rax
0x180035010  mov     rcx, rbx
0x180035013  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035018  lea     rcx, [rbp+57h+var_50]
0x18003501c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035021  lea     rdx, [rbp+57h+var_D0]
0x180035025  lea     rcx, [rsp+110h+var_E0]
0x18003502a  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18003502f  mov     r9, rax
0x180035032  lea     r8, aAccessguids; "AccessGUIDs"
0x180035039  mov     rdx, [rbp+57h+var_B8]
0x18003503d  lea     rcx, [rbp+57h+var_50]
0x180035041  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180035046  lea     rcx, [rbx+0E0h]
0x18003504d  mov     rdx, rax
0x180035050  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035055  lea     rcx, [rbp+57h+var_50]
0x180035059  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003505e  jmp     loc_18003525D
0x180035063  mov     rcx, rbx
0x180035066  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003506b  jmp     loc_18003525D
0x180035070  cmp     [rdi], r15d
0x180035073  jnz     loc_1800352AC
0x180035079  lea     rdx, [rdi+8]
0x18003507d  cmp     [rdx+10h], r14
0x180035081  jnz     loc_180035251
0x180035087  lea     r8, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x18003508c  lea     rdx, aSelectPackagef_0; "SELECT PackageFamilyName, AccessGUID FR"...
0x180035093  mov     rcx, [rbp+57h+var_D0]; this
0x180035097  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003509c  mov     rcx, [rbp+5Fh]; this
0x1800350a0  test    eax, eax
0x1800350a2  jns     short loc_1800350B9
0x1800350a4  mov     r9d, eax; char *
0x1800350a7  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800350ae  mov     edx, 91Dh; void *
0x1800350b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800350b9  mov     r8, [rdi+40h]; __int64
0x1800350bd  mov     edx, r15d; int
0x1800350c0  lea     rcx, [rsp+110h+var_E8]; this
0x1800350c5  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800350ca  mov     rcx, [rbp+5Fh]; this
0x1800350ce  test    eax, eax
0x1800350d0  jns     short loc_1800350E7
0x1800350d2  mov     r9d, eax; char *
0x1800350d5  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800350dc  mov     edx, 91Eh; void *
0x1800350e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800350e7  mov     [rsp+110h+var_F0], r14b; int
0x1800350ec  lea     rdx, [rsp+110h+var_F0]; bool *
0x1800350f1  lea     rcx, [rsp+110h+var_E8]; this
0x1800350f6  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800350fb  mov     rcx, [rbp+5Fh]; this
0x1800350ff  test    eax, eax
0x180035101  jns     short loc_180035118
0x180035103  mov     r9d, eax; char *
0x180035106  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003510d  mov     edx, 922h; void *
0x180035112  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035118  cmp     [rsp+110h+var_F0], r14b
0x18003511d  setz    al
0x180035120  mov     rcx, [rbp+5Fh]; this
0x180035124  test    al, al
0x180035126  jz      short loc_180035140
0x180035128  mov     r9d, 80070002h; char *
0x18003512e  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180035135  mov     edx, 923h; void *
0x18003513a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035140  mov     [rbp+57h+var_B8], r14
0x180035144  mov     [rbp+57h+var_C0], r14
0x180035148  lea     r8, [rbp+57h+var_B8]; unsigned __int64 *
0x18003514c  xor     edx, edx; int
0x18003514e  lea     rcx, [rsp+110h+var_E8]; this
0x180035153  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035158  mov     rcx, [rbp+5Fh]; this
0x18003515c  test    eax, eax
0x18003515e  jns     short loc_180035175
0x180035160  mov     r9d, eax; char *
0x180035163  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003516a  mov     edx, 928h; void *
0x18003516f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035175  lea     r8, [rbp+57h+var_C0]; unsigned __int64 *
0x180035179  mov     edx, r15d; int
0x18003517c  lea     rcx, [rsp+110h+var_E8]; this
0x180035181  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035186  mov     rcx, [rbp+5Fh]; this
0x18003518a  test    eax, eax
0x18003518c  jns     short loc_1800351A3
0x18003518e  mov     r9d, eax; char *
0x180035191  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180035198  mov     edx, 929h; void *
0x18003519d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800351a3  lea     rdx, [rsp+110h+var_E8]; struct StateRepository::Statement *
0x1800351a8  mov     rcx, [rbp+57h+var_D0]; this
0x1800351ac  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x1800351b1  lea     rcx, [rsp+110h+var_E8]; this
0x1800351b6  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x1800351bb  mov     rcx, [rbp+5Fh]; this
0x1800351bf  test    eax, eax
0x1800351c1  jns     short loc_1800351D8
0x1800351c3  mov     r9d, eax; char *
0x1800351c6  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800351cd  mov     edx, 92Dh; void *
0x1800351d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800351d8  lea     rdx, [rbp+57h+var_D0]
0x1800351dc  lea     rcx, [rsp+110h+var_E0]
0x1800351e1  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800351e6  mov     r9, rax
0x1800351e9  lea     r8, aPackagefamilyn_0; "PackageFamilyNames"
0x1800351f0  mov     rdx, [rbp+57h+var_B8]
0x1800351f4  lea     rcx, [rbp+57h+var_50]
  ... truncated ...
```
