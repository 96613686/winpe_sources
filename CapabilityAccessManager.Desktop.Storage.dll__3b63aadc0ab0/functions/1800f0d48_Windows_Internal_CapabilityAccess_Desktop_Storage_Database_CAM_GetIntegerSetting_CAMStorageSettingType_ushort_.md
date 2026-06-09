# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::GetIntegerSetting(CAMStorageSettingType,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64 &)

- ea: `0x1800f0d48`
- end: `0x1800f127d`
- name: `?GetIntegerSetting@CAM@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAJW4CAMStorageSettingType@@PEBG111AEA_K@Z`
- size: `1333`
- prototype: `__int64 __fastcall(int, const wchar_t *, const wchar_t *, wchar_t *, wchar_t *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800edfa0`

## callees

- `0x1800e5e6c`
- `0x1800edb4c`
- `0x1800f0d48`
- `0x1800f4518`
- `0x1800f6f6c`
- `0x1800f719c`
- `0x1800f75c0`
- `0x1800ffb60`
- `0x1800ffb94`
- `0x1800ffcc4`
- `0x1801000a8`
- `0x180100908`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f0e1d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f0e8d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f0f3d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f0e1d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f0e8d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f0f3d`

## string_xrefs

- `0x1800f1079`: `SettingType{%d}, key1{%ws}, key2{%ws}, key3{%ws}, userSidString{%ws}`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::GetIntegerSetting(
        int a1,
        const wchar_t *a2,
        const wchar_t *a3,
        wchar_t *a4,
        wchar_t *a5,
        unsigned __int64 *a6)
{
  int v9; // ebx
  wchar_t *v10; // rsi
  const wchar_t *v11; // r8
  int v12; // r14d
  int v13; // r13d
  const char *v14; // rdx
  const wchar_t *v15; // r8
  wchar_t *v16; // rbx
  const wchar_t *v17; // r8
  unsigned int Row; // eax
  wchar_t *v19; // r14
  char v20; // bl
  unsigned int ColumnUInt64; // eax
  unsigned int v22; // ebx
  unsigned int v24; // eax
  int v25; // [rsp+20h] [rbp-99h]
  char *v26; // [rsp+28h] [rbp-91h]
  char *v27; // [rsp+28h] [rbp-91h]
  struct sqlite3_stmt *v28; // [rsp+50h] [rbp-69h] BYREF
  wchar_t *v29; // [rsp+58h] [rbp-61h]
  _QWORD v30[6]; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v31[14]; // [rsp+90h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]
  int v33; // [rsp+110h] [rbp+57h] BYREF
  wchar_t *v34; // [rsp+128h] [rbp+6Fh]

  v34 = a4;
  if ( !a1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26C,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v25);
  v28 = 0;
  v31[0] = &std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable';
  v31[1] = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection;
  v31[7] = v31;
  v9 = 1;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
    (__int64)v31,
    1u);
  v10 = a5;
  if ( a1 == 1 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v25);
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
      "SELECT Value FROM SystemGlobal WHERE Capability=?;",
      (struct StateRepository::Statement *)&v28);
    v11 = a2;
    goto LABEL_40;
  }
  v12 = 2;
  if ( a1 == 2 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v25);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28A,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v25);
    if ( a3 && wcsnlen(a3, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
        "SELECT Value FROM UserGlobalWithConsentID WHERE Capability=? AND User=? AND ConsentID=?; ",
        (struct StateRepository::Statement *)&v28);
      StateRepository::Statement::Bind((StateRepository::Statement *)&v28, 1, a2);
      v13 = 3;
LABEL_18:
      v29 = (wchar_t *)a3;
      v15 = v10;
LABEL_21:
      StateRepository::Statement::Bind((StateRepository::Statement *)&v28, v12, v15);
      v9 = v13;
LABEL_31:
      v11 = v29;
      goto LABEL_40;
    }
    v14 = "SELECT Value FROM UserGlobal WHERE Capability=? AND User=?; ";
    goto LABEL_20;
  }
  v13 = 3;
  if ( a1 == 3 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v25);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2AB,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v25);
    if ( a3 && wcsnlen(a3, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
        "SELECT Value FROM ClassicGlobalWithConsentID WHERE Capability=? AND User=? AND ConsentID=?; ",
        (struct StateRepository::Statement *)&v28);
      StateRepository::Statement::Bind((StateRepository::Statement *)&v28, 1, a2);
      goto LABEL_18;
    }
    v14 = "SELECT Value FROM ClassicGlobal WHERE Capability=? AND User=?; ";
LABEL_20:
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
      v14,
      (struct StateRepository::Statement *)&v28);
    v13 = 2;
    v29 = v10;
    v12 = 1;
    v15 = a2;
    goto LABEL_21;
  }
  v33 = 4;
  switch ( a1 )
  {
    case 4:
      if ( !a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2CC,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v25);
      if ( !v34 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2CD,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v25);
      if ( !a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2CE,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v25);
      if ( a3 && wcsnlen(a3, 1u) )
      {
        Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
          (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
          "SELECT Value FROM AppWithConsentID WHERE Capability=? AND User=? AND PackageFamily=? AND ConsentID=?; ",
          (struct StateRepository::Statement *)&v28);
        StateRepository::Statement::Bind((StateRepository::Statement *)&v28, 1, a2);
        v29 = (wchar_t *)a3;
        v16 = v34;
        v17 = v10;
      }
      else
      {
        Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
          (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
          "SELECT Value FROM App WHERE Capability=? AND User=? AND PackageFamily=?; ",
          (struct StateRepository::Statement *)&v28);
        v33 = 3;
        v29 = v34;
        v13 = 2;
        v12 = 1;
        v17 = a2;
        v16 = v10;
      }
      StateRepository::Statement::Bind((StateRepository::Statement *)&v28, v12, v17);
      StateRepository::Statement::Bind((StateRepository::Statement *)&v28, v13, v16);
      v9 = v33;
      goto LABEL_31;
    case 6:
      if ( !a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v25);
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
        "SELECT Value FROM MigratedUsers WHERE User=?;",
        (struct StateRepository::Statement *)&v28);
      break;
    case 5:
      if ( !a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2FA,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v25);
      if ( !a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2FB,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v25);
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30,
        "SELECT Value FROM ShowGlobalPrompts WHERE Capability=? AND User=?; ",
        (struct StateRepository::Statement *)&v28);
      StateRepository::Statement::Bind((StateRepository::Statement *)&v28, 1, a2);
      v9 = 2;
      break;
    default:
      v24 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x307,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)v24,
        v25);
  }
  v11 = v10;
LABEL_40:
  StateRepository::Statement::Bind((StateRepository::Statement *)&v28, v9, v11);
  LOBYTE(v33) = 0;
  Row = StateRepository::Statement::FetchRow(&v28, (bool *)&v33);
  v19 = v34;
  LODWORD(v26) = a1;
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x316,
    (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
    (const char *)Row,
    (int)"SettingType{%d}, key1{%ws}, key2{%ws}, key3{%ws}, userSidString{%ws}",
    v26,
    a2,
    a3,
    v34,
    v10);
  v20 = v33;
  if ( (_BYTE)v33 )
  {
    ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v28, 0, a6);
    LODWORD(v27) = a1;
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)ColumnUInt64,
      (int)"SettingType{%d}, key1{%ws}, key2{%ws}, key3{%ws}, userSidString{%ws}",
      v27,
      a2,
      a3,
      v19,
      v10);
  }
  if ( v28 )
    StateRepository::StatementCache::Add(
      (StateRepository::StatementCache *)(v30[0] + 40LL),
      (struct StateRepository::Statement *)&v28);
  if ( v20 )
    v22 = 0;
  else
    v22 = -2147024894;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper((Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v30);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v28);
  return v22;
}

```

## disassembly

```asm
0x1800f0d48  mov     [rsp-8+arg_8], rbx
0x1800f0d4d  mov     [rsp-8+arg_18], r9
0x1800f0d52  push    rbp
0x1800f0d53  push    rsi
0x1800f0d54  push    rdi
0x1800f0d55  push    r12
0x1800f0d57  push    r13
0x1800f0d59  push    r14
0x1800f0d5b  push    r15
0x1800f0d5d  lea     rbp, [rsp-17h]
0x1800f0d62  sub     rsp, 0D0h
0x1800f0d69  mov     r15, r8
0x1800f0d6c  mov     rdi, rdx
0x1800f0d6f  mov     r12d, ecx
0x1800f0d72  mov     rcx, [rbp+4Fh]; this
0x1800f0d76  test    r12d, r12d
0x1800f0d79  jz      loc_1800F1175
0x1800f0d7f  mov     [rbp+47h+var_B0], 0
0x1800f0d87  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZV12@$$V@std@@6B@; const std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable'
0x1800f0d8e  mov     [rbp+47h+var_70], rax
0x1800f0d92  lea     rax, ?GetDatabaseConnection@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection(void)
0x1800f0d99  mov     [rbp+47h+var_68], rax
0x1800f0d9d  lea     rax, [rbp+47h+var_70]
0x1800f0da1  mov     [rbp+47h+var_38], rax
0x1800f0da5  mov     ebx, 1
0x1800f0daa  mov     r8d, ebx
0x1800f0dad  lea     rdx, [rbp+47h+var_70]
0x1800f0db1  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0db5  call    ??0DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@V?$function@$$A6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ@std@@I@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(std::function<std::shared_ptr<StateRepository::Database> (void)>,uint)
0x1800f0dba  nop
0x1800f0dbb  mov     rsi, [rbp+47h+arg_20]
0x1800f0dbf  cmp     r12d, ebx
0x1800f0dc2  jnz     short loc_1800F0DED
0x1800f0dc4  mov     rcx, [rbp+4Fh]; this
0x1800f0dc8  test    rdi, rdi
0x1800f0dcb  jz      loc_1800F118D
0x1800f0dd1  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0dd5  lea     rdx, aSelectValueFro_3; "SELECT Value FROM SystemGlobal WHERE Ca"...
0x1800f0ddc  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0de0  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0de5  mov     r8, rdi
0x1800f0de8  jmp     loc_1800F103C
0x1800f0ded  mov     r14d, 2
0x1800f0df3  cmp     r12d, r14d
0x1800f0df6  jnz     short loc_1800F0E59
0x1800f0df8  mov     rcx, [rbp+4Fh]; this
0x1800f0dfc  test    rdi, rdi
0x1800f0dff  jz      loc_1800F11A5
0x1800f0e05  mov     rcx, [rbp+4Fh]; this
0x1800f0e09  test    rsi, rsi
0x1800f0e0c  jz      loc_1800F11BD
0x1800f0e12  test    r15, r15
0x1800f0e15  jz      short loc_1800F0E50
0x1800f0e17  mov     rdx, rbx; MaxCount
0x1800f0e1a  mov     rcx, r15; Source
0x1800f0e1d  call    cs:__imp_wcsnlen
0x1800f0e23  test    rax, rax
0x1800f0e26  jz      short loc_1800F0E50
0x1800f0e28  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0e2c  lea     rdx, aSelectValueFro_5; "SELECT Value FROM UserGlobalWithConsent"...
0x1800f0e33  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0e37  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0e3c  mov     r8, rdi; wchar_t *
0x1800f0e3f  mov     edx, ebx; int
0x1800f0e41  lea     rcx, [rbp+47h+var_B0]; this
0x1800f0e45  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f0e4a  lea     r13d, [r14+1]
0x1800f0e4e  jmp     short loc_1800F0EBA
0x1800f0e50  lea     rdx, aSelectValueFro; "SELECT Value FROM UserGlobal WHERE Capa"...
0x1800f0e57  jmp     short loc_1800F0ECA
0x1800f0e59  mov     r13d, 3
0x1800f0e5f  cmp     r12d, r13d
0x1800f0e62  jnz     loc_1800F0EF8
0x1800f0e68  mov     rcx, [rbp+4Fh]; this
0x1800f0e6c  test    rdi, rdi
0x1800f0e6f  jz      loc_1800F11D5
0x1800f0e75  mov     rcx, [rbp+4Fh]; this
0x1800f0e79  test    rsi, rsi
0x1800f0e7c  jz      loc_1800F11ED
0x1800f0e82  test    r15, r15
0x1800f0e85  jz      short loc_1800F0EC3
0x1800f0e87  mov     rdx, rbx; MaxCount
0x1800f0e8a  mov     rcx, r15; Source
0x1800f0e8d  call    cs:__imp_wcsnlen
0x1800f0e93  test    rax, rax
0x1800f0e96  jz      short loc_1800F0EC3
0x1800f0e98  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0e9c  lea     rdx, aSelectValueFro_2; "SELECT Value FROM ClassicGlobalWithCons"...
0x1800f0ea3  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0ea7  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0eac  mov     r8, rdi; wchar_t *
0x1800f0eaf  mov     edx, ebx; int
0x1800f0eb1  lea     rcx, [rbp+47h+var_B0]; this
0x1800f0eb5  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f0eba  mov     [rbp+47h+var_A8], r15
0x1800f0ebe  mov     r8, rsi
0x1800f0ec1  jmp     short loc_1800F0EE4
0x1800f0ec3  lea     rdx, aSelectValueFro_6; "SELECT Value FROM ClassicGlobal WHERE C"...
0x1800f0eca  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0ece  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0ed2  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0ed7  mov     r13d, r14d
0x1800f0eda  mov     [rbp+47h+var_A8], rsi
0x1800f0ede  mov     r14d, ebx
0x1800f0ee1  mov     r8, rdi; wchar_t *
0x1800f0ee4  mov     edx, r14d; int
0x1800f0ee7  lea     rcx, [rbp+47h+var_B0]; this
0x1800f0eeb  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f0ef0  mov     ebx, r13d
0x1800f0ef3  jmp     loc_1800F0FC1
0x1800f0ef8  mov     eax, 4
0x1800f0efd  mov     [rbp+47h+arg_0], eax
0x1800f0f00  cmp     r12d, eax
0x1800f0f03  jnz     loc_1800F0FC7
0x1800f0f09  mov     rcx, [rbp+4Fh]; this
0x1800f0f0d  test    rdi, rdi
0x1800f0f10  jz      loc_1800F1205
0x1800f0f16  mov     rcx, [rbp+4Fh]; this
0x1800f0f1a  cmp     [rbp+47h+arg_18], 0
0x1800f0f1f  jz      loc_1800F121D
0x1800f0f25  mov     rcx, [rbp+4Fh]; this
0x1800f0f29  test    rsi, rsi
0x1800f0f2c  jz      loc_1800F1235
0x1800f0f32  test    r15, r15
0x1800f0f35  jz      short loc_1800F0F77
0x1800f0f37  mov     rdx, rbx; MaxCount
0x1800f0f3a  mov     rcx, r15; Source
0x1800f0f3d  call    cs:__imp_wcsnlen
0x1800f0f43  test    rax, rax
0x1800f0f46  jz      short loc_1800F0F77
0x1800f0f48  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0f4c  lea     rdx, aSelectValueFro_8; "SELECT Value FROM AppWithConsentID WHER"...
0x1800f0f53  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0f57  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0f5c  mov     r8, rdi; wchar_t *
0x1800f0f5f  mov     edx, ebx; int
0x1800f0f61  lea     rcx, [rbp+47h+var_B0]; this
0x1800f0f65  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f0f6a  mov     [rbp+47h+var_A8], r15
0x1800f0f6e  mov     rbx, [rbp+47h+arg_18]
0x1800f0f72  mov     r8, rsi
0x1800f0f75  jmp     short loc_1800F0FA3
0x1800f0f77  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0f7b  lea     rdx, aSelectValueFro_7; "SELECT Value FROM App WHERE Capability="...
0x1800f0f82  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0f86  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0f8b  mov     [rbp+47h+arg_0], r13d
0x1800f0f8f  mov     rax, [rbp+47h+arg_18]
0x1800f0f93  mov     [rbp+47h+var_A8], rax
0x1800f0f97  mov     r13d, r14d
0x1800f0f9a  mov     r14d, ebx
0x1800f0f9d  mov     r8, rdi; wchar_t *
0x1800f0fa0  mov     rbx, rsi
0x1800f0fa3  mov     edx, r14d; int
0x1800f0fa6  lea     rcx, [rbp+47h+var_B0]; this
0x1800f0faa  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f0faf  mov     r8, rbx; wchar_t *
0x1800f0fb2  mov     edx, r13d; int
0x1800f0fb5  lea     rcx, [rbp+47h+var_B0]; this
0x1800f0fb9  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f0fbe  mov     ebx, [rbp+47h+arg_0]
0x1800f0fc1  mov     r8, [rbp+47h+var_A8]
0x1800f0fc5  jmp     short loc_1800F103C
0x1800f0fc7  cmp     r12d, 6
0x1800f0fcb  jnz     short loc_1800F0FF0
0x1800f0fcd  mov     rcx, [rbp+4Fh]; this
0x1800f0fd1  test    rsi, rsi
0x1800f0fd4  jz      loc_1800F124D
0x1800f0fda  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f0fde  lea     rdx, aSelectValueFro_0; "SELECT Value FROM MigratedUsers WHERE U"...
0x1800f0fe5  lea     rcx, [rbp+47h+var_A0]; this
0x1800f0fe9  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f0fee  jmp     short loc_1800F1039
0x1800f0ff0  cmp     r12d, 5
0x1800f0ff4  jnz     loc_1800F1152
0x1800f0ffa  mov     rcx, [rbp+4Fh]; this
0x1800f0ffe  test    rdi, rdi
0x1800f1001  jz      loc_1800F1265
0x1800f1007  mov     rcx, [rbp+4Fh]; this
0x1800f100b  test    rsi, rsi
0x1800f100e  jz      loc_1800F113A
0x1800f1014  lea     r8, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f1018  lea     rdx, aSelectValueFro_1; "SELECT Value FROM ShowGlobalPrompts WHE"...
0x1800f101f  lea     rcx, [rbp+47h+var_A0]; this
0x1800f1023  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f1028  mov     r8, rdi; wchar_t *
0x1800f102b  mov     edx, ebx; int
0x1800f102d  lea     rcx, [rbp+47h+var_B0]; this
0x1800f1031  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f1036  mov     ebx, r14d
0x1800f1039  mov     r8, rsi; wchar_t *
0x1800f103c  mov     edx, ebx; int
0x1800f103e  lea     rcx, [rbp+47h+var_B0]; this
0x1800f1042  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f1047  mov     byte ptr [rbp+47h+arg_0], 0
0x1800f104b  lea     rdx, [rbp+47h+arg_0]; bool *
0x1800f104f  lea     rcx, [rbp+47h+var_B0]; this
0x1800f1053  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800f1058  mov     rcx, [rbp+4Fh]; this
0x1800f105c  mov     [rsp+100h+var_B8], rsi
0x1800f1061  mov     r14, [rbp+47h+arg_18]
0x1800f1065  mov     [rsp+100h+var_C0], r14
0x1800f106a  mov     [rsp+100h+var_C8], r15
0x1800f106f  mov     [rsp+100h+var_D0], rdi
0x1800f1074  mov     dword ptr [rsp+100h+var_D8], r12d; char *
0x1800f1079  lea     r13, aSettingtypeDKe_0; "SettingType{%d}, key1{%ws}, key2{%ws}, "...
0x1800f1080  mov     qword ptr [rsp+100h+var_E0], r13; int
0x1800f1085  mov     r9d, eax; char *
0x1800f1088  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f108f  mov     edx, 316h; void *
0x1800f1094  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f1099  mov     bl, byte ptr [rbp+47h+arg_0]
0x1800f109c  test    bl, bl
0x1800f109e  jz      short loc_1800F10E5
0x1800f10a0  mov     r8, [rbp+47h+arg_28]; unsigned __int64 *
0x1800f10a4  xor     edx, edx; int
0x1800f10a6  lea     rcx, [rbp+47h+var_B0]; this
0x1800f10aa  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800f10af  mov     rcx, [rbp+4Fh]; this
0x1800f10b3  mov     [rsp+100h+var_B8], rsi
0x1800f10b8  mov     [rsp+100h+var_C0], r14
0x1800f10bd  mov     [rsp+100h+var_C8], r15
0x1800f10c2  mov     [rsp+100h+var_D0], rdi
0x1800f10c7  mov     dword ptr [rsp+100h+var_D8], r12d; char *
0x1800f10cc  mov     qword ptr [rsp+100h+var_E0], r13; int
0x1800f10d1  mov     r9d, eax; char *
0x1800f10d4  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f10db  mov     edx, 321h; void *
0x1800f10e0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f10e5  cmp     [rbp+47h+var_B0], 0
0x1800f10ea  jz      short loc_1800F10FD
0x1800f10ec  mov     rcx, [rbp+47h+var_A0]
0x1800f10f0  add     rcx, 28h ; '('; this
0x1800f10f4  lea     rdx, [rbp+47h+var_B0]; struct StateRepository::Statement *
0x1800f10f8  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800f10fd  test    bl, bl
0x1800f10ff  jz      short loc_1800F1105
0x1800f1101  xor     ebx, ebx
0x1800f1103  jmp     short loc_1800F110A
0x1800f1105  mov     ebx, 80070002h
0x1800f110a  lea     rcx, [rbp+47h+var_A0]; this
0x1800f110e  call    ??1DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(void)
0x1800f1113  nop
0x1800f1114  lea     rcx, [rbp+47h+var_B0]; this
0x1800f1118  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800f111d  mov     eax, ebx
0x1800f111f  mov     rbx, [rsp+100h+arg_8]
0x1800f1127  add     rsp, 0D0h
0x1800f112e  pop     r15
0x1800f1130  pop     r14
0x1800f1132  pop     r13
0x1800f1134  pop     r12
0x1800f1136  pop     rdi
0x1800f1137  pop     rsi
0x1800f1138  pop     rbp
0x1800f1139  retn
0x1800f113a  mov     r9d, 80070057h; char *
0x1800f1140  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f1147  mov     edx, 2FBh; void *
0x1800f114c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1152  mov     ecx, 80070057h
0x1800f1157  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800f115c  mov     r9d, eax; char *
0x1800f115f  mov     rcx, [rbp+4Fh]; this
0x1800f1163  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f116a  mov     edx, 307h; void *
0x1800f116f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1175  mov     r9d, 80070057h; char *
0x1800f117b  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f1182  mov     edx, 26Ch; void *
0x1800f1187  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f118d  mov     r9d, 80070057h; char *
0x1800f1193  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f119a  mov     edx, 278h; void *
0x1800f119f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f11a5  mov     r9d, 80070057h; char *
0x1800f11ab  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f11b2  mov     edx, 289h; void *
0x1800f11b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f11bd  mov     r9d, 80070057h; char *
0x1800f11c3  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f11ca  mov     edx, 28Ah; void *
0x1800f11cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f11d5  mov     r9d, 80070057h; char *
0x1800f11db  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f11e2  mov     edx, 2AAh; void *
0x1800f11e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f11ed  mov     r9d, 80070057h; char *
0x1800f11f3  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f11fa  mov     edx, 2ABh; void *
0x1800f11ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1205  mov     r9d, 80070057h; char *
0x1800f120b  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f1212  mov     edx, 2CCh; void *
0x1800f1217  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f121d  mov     r9d, 80070057h; char *
0x1800f1223  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f122a  mov     edx, 2CDh; void *
0x1800f122f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1235  mov     r9d, 80070057h; char *
  ... truncated ...
```
