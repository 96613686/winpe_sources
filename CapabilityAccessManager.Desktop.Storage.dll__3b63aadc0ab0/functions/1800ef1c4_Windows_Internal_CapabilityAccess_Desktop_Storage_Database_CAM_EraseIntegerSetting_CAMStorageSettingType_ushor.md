# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::EraseIntegerSetting(CAMStorageSettingType,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800ef1c4`
- end: `0x1800ef688`
- name: `?EraseIntegerSetting@CAM@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXW4CAMStorageSettingType@@PEBG111@Z`
- size: `1220`
- prototype: `void __fastcall(int, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800edda0`

## callees

- `0x1800e5e6c`
- `0x1800edb4c`
- `0x1800ef1c4`
- `0x1800f4518`
- `0x1800f6f6c`
- `0x1800f719c`
- `0x1800f73a4`
- `0x1800f73fc`
- `0x1800f75c0`
- `0x1800ffb60`
- `0x1800ffb94`
- `0x1800ffc78`
- `0x180100908`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800ef299`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800ef309`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800ef3b9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800ef299`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800ef309`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800ef3b9`

## string_xrefs

- `0x1800ef251`: `DELETE FROM SystemGlobal WHERE Capability=?;`
- `0x1800ef2cc`: `DELETE FROM UserGlobal WHERE Capability=? AND User=?; `
- `0x1800ef2a8`: `DELETE FROM UserGlobalWithConsentID WHERE Capability=? AND User=? AND ConsentID=?; `
- `0x1800ef33f`: `DELETE FROM ClassicGlobal WHERE Capability=? AND User=?; `
- `0x1800ef318`: `DELETE FROM ClassicGlobalWithConsentID WHERE Capability=? AND User=? AND ConsentID=?; `
- `0x1800ef3f7`: `DELETE FROM App WHERE Capability=? AND User=? AND PackageFamily=?; `
- `0x1800ef3c8`: `DELETE FROM AppWithConsentID WHERE Capability=? AND User=? AND PackageFamily=? AND ConsentID=?; `
- `0x1800ef46b`: `DELETE FROM ShowGlobalPrompts WHERE Capability=? AND User=?; `
- `0x1800ef4ed`: `SettingType{%d}, key1{%ws}, key2{%ws}, key3{%ws}, userSidString{%ws}`

## pseudocode

```c
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::EraseIntegerSetting(
        int a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t *a5)
{
  int v8; // edi
  const wchar_t *v9; // r8
  int v10; // r14d
  int v11; // r12d
  const char *v12; // rdx
  const wchar_t *v13; // r8
  const wchar_t *v14; // rdi
  const wchar_t *v15; // r8
  unsigned int NoRow; // eax
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  const char *v19; // r9
  unsigned int v20; // eax
  int v21; // [rsp+20h] [rbp-A1h]
  char *v22; // [rsp+28h] [rbp-99h]
  _QWORD v23[2]; // [rsp+50h] [rbp-71h] BYREF
  struct _GUID v24; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v25[6]; // [rsp+70h] [rbp-51h] BYREF
  _QWORD v26[14]; // [rsp+A0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]
  int v28; // [rsp+120h] [rbp+5Fh]

  if ( !a1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C5,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v21);
  v23[0] = 0;
  v26[0] = &std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable';
  v26[1] = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection;
  v26[7] = v26;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
    (__int64)v26,
    0);
  v8 = 1;
  if ( a1 == 1 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D1,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
      "DELETE FROM SystemGlobal WHERE Capability=?;",
      (struct StateRepository::Statement *)v23);
    v9 = a2;
    goto LABEL_36;
  }
  v10 = 2;
  if ( a1 == 2 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E2,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E3,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( a3 && wcsnlen(a3, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
        "DELETE FROM UserGlobalWithConsentID WHERE Capability=? AND User=? AND ConsentID=?; ",
        (struct StateRepository::Statement *)v23);
      StateRepository::Statement::Bind((StateRepository::Statement *)v23, 1, a2);
      v11 = 3;
LABEL_18:
      *(_QWORD *)&v24.Data1 = a3;
      v13 = a5;
LABEL_21:
      StateRepository::Statement::Bind((StateRepository::Statement *)v23, v10, v13);
      v8 = v11;
LABEL_31:
      v9 = *(const wchar_t **)&v24.Data1;
      goto LABEL_36;
    }
    v12 = "DELETE FROM UserGlobal WHERE Capability=? AND User=?; ";
    goto LABEL_20;
  }
  v11 = 3;
  if ( a1 == 3 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x403,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x404,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( a3 && wcsnlen(a3, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
        "DELETE FROM ClassicGlobalWithConsentID WHERE Capability=? AND User=? AND ConsentID=?; ",
        (struct StateRepository::Statement *)v23);
      StateRepository::Statement::Bind((StateRepository::Statement *)v23, 1, a2);
      goto LABEL_18;
    }
    v12 = "DELETE FROM ClassicGlobal WHERE Capability=? AND User=?; ";
LABEL_20:
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
      v12,
      (struct StateRepository::Statement *)v23);
    v11 = 2;
    *(_QWORD *)&v24.Data1 = a5;
    v10 = 1;
    v13 = a2;
    goto LABEL_21;
  }
  v28 = 4;
  if ( a1 == 4 )
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x427,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    if ( a3 && wcsnlen(a3, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
        "DELETE FROM AppWithConsentID WHERE Capability=? AND User=? AND PackageFamily=? AND ConsentID=?; ",
        (struct StateRepository::Statement *)v23);
      StateRepository::Statement::Bind((StateRepository::Statement *)v23, 1, a2);
      *(_QWORD *)&v24.Data1 = a3;
      v14 = a4;
      v15 = a5;
    }
    else
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
        "DELETE FROM App WHERE Capability=? AND User=? AND PackageFamily=?; ",
        (struct StateRepository::Statement *)v23);
      v28 = 3;
      *(_QWORD *)&v24.Data1 = a4;
      v11 = 2;
      v10 = 1;
      v15 = a2;
      v14 = a5;
    }
    StateRepository::Statement::Bind((StateRepository::Statement *)v23, v10, v15);
    StateRepository::Statement::Bind((StateRepository::Statement *)v23, v11, v14);
    v8 = v28;
    goto LABEL_31;
  }
  if ( a1 != 5 )
  {
    v20 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x455,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)v20,
      v21);
  }
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x448,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v21);
  if ( !a5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x449,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v21);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
    "DELETE FROM ShowGlobalPrompts WHERE Capability=? AND User=?; ",
    (struct StateRepository::Statement *)v23);
  StateRepository::Statement::Bind((StateRepository::Statement *)v23, 1, a2);
  v8 = 2;
  v9 = a5;
LABEL_36:
  StateRepository::Statement::Bind((StateRepository::Statement *)v23, v8, v9);
  v24.Data1 = -1337847773;
  *(_DWORD *)&v24.Data2 = 1259665200;
  *(_DWORD *)v24.Data4 = 944030390;
  *(_DWORD *)&v24.Data4[4] = 1986211033;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
    &v24);
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)v23);
  LODWORD(v22) = a1;
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x462,
    (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
    (const char *)NoRow,
    (int)"SettingType{%d}, key1{%ws}, key2{%ws}, key3{%ws}, userSidString{%ws}",
    v22,
    a2,
    a3,
    a4,
    a5);
  if ( v23[0] )
    StateRepository::StatementCache::Add(
      (StateRepository::StatementCache *)(v25[0] + 40LL),
      (struct StateRepository::Statement *)v23);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25,
    v17,
    v18,
    v19);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper((Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v25);
  StateRepository::Statement::~Statement((StateRepository::Statement *)v23);
}

```

## disassembly

```asm
0x1800ef1c4  mov     [rsp-8+arg_8], rbx
0x1800ef1c9  mov     [rsp-8+arg_18], r9
0x1800ef1ce  push    rbp
0x1800ef1cf  push    rsi
0x1800ef1d0  push    rdi
0x1800ef1d1  push    r12
0x1800ef1d3  push    r13
0x1800ef1d5  push    r14
0x1800ef1d7  push    r15
0x1800ef1d9  lea     rbp, [rsp-1Fh]
0x1800ef1de  sub     rsp, 0E0h
0x1800ef1e5  mov     r15, r8
0x1800ef1e8  mov     rbx, rdx
0x1800ef1eb  mov     r13d, ecx
0x1800ef1ee  mov     rcx, [rbp+57h]; this
0x1800ef1f2  test    r13d, r13d
0x1800ef1f5  jz      loc_1800EF598
0x1800ef1fb  mov     [rbp+4Fh+var_C0], 0
0x1800ef203  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZV12@$$V@std@@6B@; const std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable'
0x1800ef20a  mov     [rbp+4Fh+var_70], rax
0x1800ef20e  lea     rax, ?GetDatabaseConnection@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection(void)
0x1800ef215  mov     [rbp+4Fh+var_68], rax
0x1800ef219  lea     rax, [rbp+4Fh+var_70]
0x1800ef21d  mov     [rbp+4Fh+var_38], rax
0x1800ef221  xor     r8d, r8d
0x1800ef224  lea     rdx, [rbp+4Fh+var_70]
0x1800ef228  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef22c  call    ??0DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@V?$function@$$A6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ@std@@I@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(std::function<std::shared_ptr<StateRepository::Database> (void)>,uint)
0x1800ef231  nop
0x1800ef232  mov     rsi, [rbp+4Fh+arg_20]
0x1800ef236  mov     edi, 1
0x1800ef23b  cmp     r13d, edi
0x1800ef23e  jnz     short loc_1800EF269
0x1800ef240  mov     rcx, [rbp+57h]; this
0x1800ef244  test    rbx, rbx
0x1800ef247  jz      loc_1800EF5B0
0x1800ef24d  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef251  lea     rdx, aDeleteFromSyst; "DELETE FROM SystemGlobal WHERE Capabili"...
0x1800ef258  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef25c  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef261  mov     r8, rbx
0x1800ef264  jmp     loc_1800EF48F
0x1800ef269  mov     r14d, 2
0x1800ef26f  cmp     r13d, r14d
0x1800ef272  jnz     short loc_1800EF2D5
0x1800ef274  mov     rcx, [rbp+57h]; this
0x1800ef278  test    rbx, rbx
0x1800ef27b  jz      loc_1800EF5C8
0x1800ef281  mov     rcx, [rbp+57h]; this
0x1800ef285  test    rsi, rsi
0x1800ef288  jz      loc_1800EF5E0
0x1800ef28e  test    r15, r15
0x1800ef291  jz      short loc_1800EF2CC
0x1800ef293  mov     rdx, rdi; MaxCount
0x1800ef296  mov     rcx, r15; Source
0x1800ef299  call    cs:__imp_wcsnlen
0x1800ef29f  test    rax, rax
0x1800ef2a2  jz      short loc_1800EF2CC
0x1800ef2a4  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef2a8  lea     rdx, aDeleteFromUser_0; "DELETE FROM UserGlobalWithConsentID WHE"...
0x1800ef2af  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef2b3  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef2b8  mov     r8, rbx; wchar_t *
0x1800ef2bb  mov     edx, edi; int
0x1800ef2bd  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef2c1  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef2c6  lea     r12d, [r14+1]
0x1800ef2ca  jmp     short loc_1800EF336
0x1800ef2cc  lea     rdx, aDeleteFromUser; "DELETE FROM UserGlobal WHERE Capability"...
0x1800ef2d3  jmp     short loc_1800EF346
0x1800ef2d5  mov     r12d, 3
0x1800ef2db  cmp     r13d, r12d
0x1800ef2de  jnz     loc_1800EF374
0x1800ef2e4  mov     rcx, [rbp+57h]; this
0x1800ef2e8  test    rbx, rbx
0x1800ef2eb  jz      loc_1800EF5F8
0x1800ef2f1  mov     rcx, [rbp+57h]; this
0x1800ef2f5  test    rsi, rsi
0x1800ef2f8  jz      loc_1800EF610
0x1800ef2fe  test    r15, r15
0x1800ef301  jz      short loc_1800EF33F
0x1800ef303  mov     rdx, rdi; MaxCount
0x1800ef306  mov     rcx, r15; Source
0x1800ef309  call    cs:__imp_wcsnlen
0x1800ef30f  test    rax, rax
0x1800ef312  jz      short loc_1800EF33F
0x1800ef314  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef318  lea     rdx, aDeleteFromClas; "DELETE FROM ClassicGlobalWithConsentID "...
0x1800ef31f  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef323  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef328  mov     r8, rbx; wchar_t *
0x1800ef32b  mov     edx, edi; int
0x1800ef32d  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef331  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef336  mov     qword ptr [rbp+4Fh+var_B0.Data1], r15
0x1800ef33a  mov     r8, rsi
0x1800ef33d  jmp     short loc_1800EF360
0x1800ef33f  lea     rdx, aDeleteFromClas_0; "DELETE FROM ClassicGlobal WHERE Capabil"...
0x1800ef346  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef34a  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef34e  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef353  mov     r12d, r14d
0x1800ef356  mov     qword ptr [rbp+4Fh+var_B0.Data1], rsi
0x1800ef35a  mov     r14d, edi
0x1800ef35d  mov     r8, rbx; wchar_t *
0x1800ef360  mov     edx, r14d; int
0x1800ef363  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef367  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef36c  mov     edi, r12d
0x1800ef36f  jmp     loc_1800EF43D
0x1800ef374  mov     eax, 4
0x1800ef379  mov     [rbp+4Fh+arg_0], eax
0x1800ef37c  cmp     r13d, eax
0x1800ef37f  jnz     loc_1800EF443
0x1800ef385  mov     rcx, [rbp+57h]; this
0x1800ef389  test    rbx, rbx
0x1800ef38c  jz      loc_1800EF628
0x1800ef392  mov     rcx, [rbp+57h]; this
0x1800ef396  cmp     [rbp+4Fh+arg_18], 0
0x1800ef39b  jz      loc_1800EF640
0x1800ef3a1  mov     rcx, [rbp+57h]; this
0x1800ef3a5  test    rsi, rsi
0x1800ef3a8  jz      loc_1800EF658
0x1800ef3ae  test    r15, r15
0x1800ef3b1  jz      short loc_1800EF3F3
0x1800ef3b3  mov     rdx, rdi; MaxCount
0x1800ef3b6  mov     rcx, r15; Source
0x1800ef3b9  call    cs:__imp_wcsnlen
0x1800ef3bf  test    rax, rax
0x1800ef3c2  jz      short loc_1800EF3F3
0x1800ef3c4  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef3c8  lea     rdx, aDeleteFromAppw; "DELETE FROM AppWithConsentID WHERE Capa"...
0x1800ef3cf  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef3d3  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef3d8  mov     r8, rbx; wchar_t *
0x1800ef3db  mov     edx, edi; int
0x1800ef3dd  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef3e1  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef3e6  mov     qword ptr [rbp+4Fh+var_B0.Data1], r15
0x1800ef3ea  mov     rdi, [rbp+4Fh+arg_18]
0x1800ef3ee  mov     r8, rsi
0x1800ef3f1  jmp     short loc_1800EF41F
0x1800ef3f3  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef3f7  lea     rdx, aDeleteFromAppW; "DELETE FROM App WHERE Capability=? AND "...
0x1800ef3fe  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef402  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef407  mov     [rbp+4Fh+arg_0], r12d
0x1800ef40b  mov     rax, [rbp+4Fh+arg_18]
0x1800ef40f  mov     qword ptr [rbp+4Fh+var_B0.Data1], rax
0x1800ef413  mov     r12d, r14d
0x1800ef416  mov     r14d, edi
0x1800ef419  mov     r8, rbx; wchar_t *
0x1800ef41c  mov     rdi, rsi
0x1800ef41f  mov     edx, r14d; int
0x1800ef422  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef426  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef42b  mov     r8, rdi; wchar_t *
0x1800ef42e  mov     edx, r12d; int
0x1800ef431  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef435  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef43a  mov     edi, [rbp+4Fh+arg_0]
0x1800ef43d  mov     r8, qword ptr [rbp+4Fh+var_B0.Data1]
0x1800ef441  jmp     short loc_1800EF48F
0x1800ef443  cmp     r13d, 5
0x1800ef447  jnz     loc_1800EF575
0x1800ef44d  mov     rcx, [rbp+57h]; this
0x1800ef451  test    rbx, rbx
0x1800ef454  jz      loc_1800EF670
0x1800ef45a  mov     rcx, [rbp+57h]; this
0x1800ef45e  test    rsi, rsi
0x1800ef461  jz      loc_1800EF55D
0x1800ef467  lea     r8, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef46b  lea     rdx, aDeleteFromShow; "DELETE FROM ShowGlobalPrompts WHERE Cap"...
0x1800ef472  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef476  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800ef47b  mov     r8, rbx; wchar_t *
0x1800ef47e  mov     edx, edi; int
0x1800ef480  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef484  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef489  mov     edi, r14d
0x1800ef48c  mov     r8, rsi; wchar_t *
0x1800ef48f  mov     edx, edi; int
0x1800ef491  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef495  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800ef49a  mov     [rbp+4Fh+var_B0.Data1], 0B0421023h
0x1800ef4a1  mov     dword ptr [rbp+4Fh+var_B0.Data2], 4B14F730h
0x1800ef4a8  mov     dword ptr [rbp+4Fh+var_B0.Data4], 3844C2B6h
0x1800ef4af  mov     dword ptr [rbp+4Fh+var_B0.Data4+4], 76632CD9h
0x1800ef4b6  lea     rdx, [rbp+4Fh+var_B0]; struct _GUID
0x1800ef4ba  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef4be  call    ?BeginExclusiveTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXU_GUID@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(_GUID)
0x1800ef4c3  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef4c7  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x1800ef4cc  mov     rcx, [rbp+57h]; this
0x1800ef4d0  mov     [rsp+110h+var_C8], rsi
0x1800ef4d5  mov     rdx, [rbp+4Fh+arg_18]
0x1800ef4d9  mov     [rsp+110h+var_D0], rdx
0x1800ef4de  mov     [rsp+110h+var_D8], r15
0x1800ef4e3  mov     [rsp+110h+var_E0], rbx
0x1800ef4e8  mov     dword ptr [rsp+110h+var_E8], r13d; char *
0x1800ef4ed  lea     rdx, aSettingtypeDKe_0; "SettingType{%d}, key1{%ws}, key2{%ws}, "...
0x1800ef4f4  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x1800ef4f9  mov     r9d, eax; char *
0x1800ef4fc  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef503  mov     edx, 462h; void *
0x1800ef508  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800ef50d  cmp     [rbp+4Fh+var_C0], 0
0x1800ef512  jz      short loc_1800EF525
0x1800ef514  mov     rcx, [rbp+4Fh+var_A0]
0x1800ef518  add     rcx, 28h ; '('; this
0x1800ef51c  lea     rdx, [rbp+4Fh+var_C0]; struct StateRepository::Statement *
0x1800ef520  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800ef525  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef529  call    ?CommitTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(void)
0x1800ef52e  nop
0x1800ef52f  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800ef533  call    ??1DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(void)
0x1800ef538  nop
0x1800ef539  lea     rcx, [rbp+4Fh+var_C0]; this
0x1800ef53d  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800ef542  mov     rbx, [rsp+110h+arg_8]
0x1800ef54a  add     rsp, 0E0h
0x1800ef551  pop     r15
0x1800ef553  pop     r14
0x1800ef555  pop     r13
0x1800ef557  pop     r12
0x1800ef559  pop     rdi
0x1800ef55a  pop     rsi
0x1800ef55b  pop     rbp
0x1800ef55c  retn
0x1800ef55d  mov     r9d, 80070057h; char *
0x1800ef563  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef56a  mov     edx, 449h; void *
0x1800ef56f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef575  mov     ecx, 80070057h
0x1800ef57a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800ef57f  mov     r9d, eax; char *
0x1800ef582  mov     rcx, [rbp+57h]; this
0x1800ef586  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef58d  mov     edx, 455h; void *
0x1800ef592  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef598  mov     r9d, 80070057h; char *
0x1800ef59e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef5a5  mov     edx, 3C5h; void *
0x1800ef5aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef5b0  mov     r9d, 80070057h; char *
0x1800ef5b6  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef5bd  mov     edx, 3D1h; void *
0x1800ef5c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef5c8  mov     r9d, 80070057h; char *
0x1800ef5ce  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef5d5  mov     edx, 3E2h; void *
0x1800ef5da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef5e0  mov     r9d, 80070057h; char *
0x1800ef5e6  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef5ed  mov     edx, 3E3h; void *
0x1800ef5f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef5f8  mov     r9d, 80070057h; char *
0x1800ef5fe  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef605  mov     edx, 403h; void *
0x1800ef60a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef610  mov     r9d, 80070057h; char *
0x1800ef616  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef61d  mov     edx, 404h; void *
0x1800ef622  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef628  mov     r9d, 80070057h; char *
0x1800ef62e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef635  mov     edx, 425h; void *
0x1800ef63a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef640  mov     r9d, 80070057h; char *
0x1800ef646  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef64d  mov     edx, 426h; void *
0x1800ef652  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef658  mov     r9d, 80070057h; char *
0x1800ef65e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef665  mov     edx, 427h; void *
0x1800ef66a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef670  mov     r9d, 80070057h; char *
0x1800ef676  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef67d  mov     edx, 448h; void *
0x1800ef682  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
