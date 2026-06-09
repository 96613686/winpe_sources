# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::PrepareStoreStatement(StateRepository::Statement &,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper,CAMStorageSettingType,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1800f2d38`
- end: `0x1800f31e1`
- name: `?PrepareStoreStatement@CAM@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXAEAVStatement@StateRepository@@VDatabaseWrapper@Shared@4567@W4CAMStorageSettingType@@PEBG333_K@Z`
- size: `1193`
- prototype: `void __high(struct StateRepository::Statement *, struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper, enum CAMStorageSettingType, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800f3efc`
- `0x1800f40c8`

## callees

- `0x1800e5e6c`
- `0x1800edb4c`
- `0x1800f2d38`
- `0x1800f719c`
- `0x1800f75c0`
- `0x1800ffb94`
- `0x1800ffc0c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f2ddd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f2e9f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f2f45`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f2ddd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f2e9f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f2f45`

## string_xrefs

- `0x1800f2d72`: `INSERT INTO SystemGlobal(Capability, Value) VALUES(?,?)ON CONFLICT(Capability)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f2e16`: `INSERT INTO UserGlobal(Capability, User, Value) VALUES(?,?,?)ON CONFLICT(Capability, User)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f2deb`: `INSERT INTO UserGlobalWithConsentID(Capability, User, ConsentID, Value) VALUES(?,?,?,?)ON CONFLICT(Capability, User, ConsentID)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f2ed2`: `INSERT INTO ClassicGlobal(Capability, User, Value) VALUES(?,?,?)ON CONFLICT(Capability, User)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f2ead`: `INSERT INTO ClassicGlobalWithConsentID(Capability, User, ConsentID, Value) VALUES(?,?,?,?)ON CONFLICT(Capability, User, ConsentID)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f2f81`: `INSERT INTO App(Capability, User, PackageFamily, Value) VALUES(?,?,?,?)ON CONFLICT(Capability, User, PackageFamily)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f2f53`: `INSERT INTO AppWithConsentID(Capability, User, PackageFamily, ConsentID, Value) VALUES(?,?,?,?,?)ON CONFLICT(Capability, User, PackageFamily, ConsentID)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f3009`: `INSERT INTO MigratedUsers(User, Value) VALUES(?,?)ON CONFLICT(User)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f305e`: `INSERT INTO ShowGlobalPrompts(Capability, User, Value) VALUES(?,?,?)ON CONFLICT(Capability, User)DO UPDATE SET Value=Excluded.Value;`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CAM::PrepareStoreStatement(
        struct StateRepository::Statement *a1,
        Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *a2,
        int a3,
        const wchar_t *a4,
        wchar_t *Source,
        wchar_t *a6,
        wchar_t *a7)
{
  int v10; // edx
  int v11; // esi
  const wchar_t *v12; // r13
  const wchar_t *v13; // r12
  int v14; // ebp
  int v15; // r15d
  int v16; // r15d
  const wchar_t *v17; // r13
  int v18; // r12d
  const wchar_t *v19; // r8
  unsigned int v20; // eax
  int v21; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a3 == 1 )
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      a2,
      "INSERT INTO SystemGlobal(Capability, Value) VALUES(?,?)ON CONFLICT(Capability)DO UPDATE SET Value=Excluded.Value;",
      a1);
    StateRepository::Statement::Bind(a1, 1, a4);
    v10 = 2;
    goto LABEL_37;
  }
  v11 = 2;
  if ( a3 == 2 )
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    v12 = a7;
    if ( !a7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    v13 = Source;
    if ( Source && wcsnlen(Source, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        a2,
        "INSERT INTO UserGlobalWithConsentID(Capability, User, ConsentID, Value) VALUES(?,?,?,?)ON CONFLICT(Capability, U"
        "ser, ConsentID)DO UPDATE SET Value=Excluded.Value;",
        a1);
      StateRepository::Statement::Bind(a1, 1, a4);
      v14 = 3;
LABEL_10:
      v15 = 4;
LABEL_13:
      StateRepository::Statement::Bind(a1, v11, v12);
      StateRepository::Statement::Bind(a1, v14, v13);
      v10 = v15;
      goto LABEL_37;
    }
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      a2,
      "INSERT INTO UserGlobal(Capability, User, Value) VALUES(?,?,?)ON CONFLICT(Capability, User)DO UPDATE SET Value=Excluded.Value;",
      a1);
    v15 = 3;
    goto LABEL_12;
  }
  v14 = 3;
  if ( a3 == 3 )
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    v12 = a7;
    if ( !a7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)0x80070057LL,
        v21);
    v13 = Source;
    if ( Source && wcsnlen(Source, 1u) )
    {
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        a2,
        "INSERT INTO ClassicGlobalWithConsentID(Capability, User, ConsentID, Value) VALUES(?,?,?,?)ON CONFLICT(Capability"
        ", User, ConsentID)DO UPDATE SET Value=Excluded.Value;",
        a1);
      StateRepository::Statement::Bind(a1, 1, a4);
      goto LABEL_10;
    }
    Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
      a2,
      "INSERT INTO ClassicGlobal(Capability, User, Value) VALUES(?,?,?)ON CONFLICT(Capability, User)DO UPDATE SET Value=Excluded.Value;",
      a1);
    v15 = 3;
LABEL_12:
    v14 = 2;
    v13 = v12;
    v11 = 1;
    v12 = a4;
    goto LABEL_13;
  }
  v16 = 4;
  switch ( a3 )
  {
    case 4:
      if ( !a4 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x21F,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v21);
      if ( !a6 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x220,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v21);
      if ( !a7 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v21);
      v17 = Source;
      if ( Source && wcsnlen(Source, 1u) )
      {
        Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
          a2,
          "INSERT INTO AppWithConsentID(Capability, User, PackageFamily, ConsentID, Value) VALUES(?,?,?,?,?)ON CONFLICT(C"
          "apability, User, PackageFamily, ConsentID)DO UPDATE SET Value=Excluded.Value;",
          a1);
        StateRepository::Statement::Bind(a1, 1, a4);
        v18 = 5;
        v19 = a7;
      }
      else
      {
        Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
          a2,
          "INSERT INTO App(Capability, User, PackageFamily, Value) VALUES(?,?,?,?)ON CONFLICT(Capability, User, PackageFa"
          "mily)DO UPDATE SET Value=Excluded.Value;",
          a1);
        v18 = 4;
        v16 = 3;
        v17 = a6;
        v14 = 2;
        a6 = a7;
        v11 = 1;
        v19 = a4;
      }
      StateRepository::Statement::Bind(a1, v11, v19);
      StateRepository::Statement::Bind(a1, v14, a6);
      StateRepository::Statement::Bind(a1, v16, v17);
      v10 = v18;
      break;
    case 6:
      if ( !a7 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x23F,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v21);
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        a2,
        "INSERT INTO MigratedUsers(User, Value) VALUES(?,?)ON CONFLICT(User)DO UPDATE SET Value=Excluded.Value;",
        a1);
      StateRepository::Statement::Bind(a1, 1, a7);
      v10 = 2;
      break;
    case 5:
      if ( !a4 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x250,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v21);
      if ( !a7 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x251,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)0x80070057LL,
          v21);
      Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
        a2,
        "INSERT INTO ShowGlobalPrompts(Capability, User, Value) VALUES(?,?,?)ON CONFLICT(Capability, User)DO UPDATE SET V"
        "alue=Excluded.Value;",
        a1);
      StateRepository::Statement::Bind(a1, 1, a4);
      StateRepository::Statement::Bind(a1, 2, a7);
      v10 = 3;
      break;
    default:
      v20 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25E,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)v20,
        v21);
  }
LABEL_37:
  StateRepository::Statement::Bind(a1, v10);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(a2);
}

```

## disassembly

```asm
0x1800f2d38  mov     [rsp+arg_8], rdx
0x1800f2d3d  push    rbx
0x1800f2d3e  push    rbp
0x1800f2d3f  push    rsi
0x1800f2d40  push    rdi
0x1800f2d41  push    r12
0x1800f2d43  push    r13
0x1800f2d45  push    r14
0x1800f2d47  push    r15
0x1800f2d49  sub     rsp, 28h
0x1800f2d4d  mov     rdi, r9
0x1800f2d50  mov     r14, rdx
0x1800f2d53  mov     rbx, rcx
0x1800f2d56  mov     r15d, 1
0x1800f2d5c  cmp     r8d, r15d
0x1800f2d5f  jnz     short loc_1800F2D98
0x1800f2d61  mov     rcx, [rsp+68h]; this
0x1800f2d66  test    r9, r9
0x1800f2d69  jz      loc_1800F30F1
0x1800f2d6f  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2d72  lea     rdx, aInsertIntoSyst; "INSERT INTO SystemGlobal(Capability, Va"...
0x1800f2d79  mov     rcx, r14; this
0x1800f2d7c  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2d81  mov     r8, rdi; wchar_t *
0x1800f2d84  mov     edx, r15d; int
0x1800f2d87  mov     rcx, rbx; this
0x1800f2d8a  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2d8f  lea     edx, [r15+1]
0x1800f2d93  jmp     loc_1800F308C
0x1800f2d98  mov     esi, 2
0x1800f2d9d  cmp     r8d, esi
0x1800f2da0  jnz     loc_1800F2E5A
0x1800f2da6  mov     rcx, [rsp+68h]; this
0x1800f2dab  test    rdi, rdi
0x1800f2dae  jz      loc_1800F3109
0x1800f2db4  mov     rcx, [rsp+68h]; this
0x1800f2db9  mov     r13, [rsp+68h+arg_30]
0x1800f2dc1  test    r13, r13
0x1800f2dc4  jz      loc_1800F3121
0x1800f2dca  mov     r12, [rsp+68h+Source]
0x1800f2dd2  test    r12, r12
0x1800f2dd5  jz      short loc_1800F2E13
0x1800f2dd7  mov     rdx, r15; MaxCount
0x1800f2dda  mov     rcx, r12; Source
0x1800f2ddd  call    cs:__imp_wcsnlen
0x1800f2de3  test    rax, rax
0x1800f2de6  jz      short loc_1800F2E13
0x1800f2de8  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2deb  lea     rdx, aInsertIntoUser; "INSERT INTO UserGlobalWithConsentID(Cap"...
0x1800f2df2  mov     rcx, r14; this
0x1800f2df5  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2dfa  mov     r8, rdi; wchar_t *
0x1800f2dfd  mov     edx, r15d; int
0x1800f2e00  mov     rcx, rbx; this
0x1800f2e03  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2e08  lea     ebp, [rsi+1]
0x1800f2e0b  mov     r15d, 4
0x1800f2e11  jmp     short loc_1800F2E38
0x1800f2e13  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2e16  lea     rdx, aInsertIntoUser_0; "INSERT INTO UserGlobal(Capability, User"...
0x1800f2e1d  mov     rcx, r14; this
0x1800f2e20  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2e25  mov     r15d, 3
0x1800f2e2b  mov     ebp, esi
0x1800f2e2d  mov     r12, r13
0x1800f2e30  mov     esi, 1
0x1800f2e35  mov     r13, rdi
0x1800f2e38  mov     r8, r13; wchar_t *
0x1800f2e3b  mov     edx, esi; int
0x1800f2e3d  mov     rcx, rbx; this
0x1800f2e40  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2e45  mov     r8, r12; wchar_t *
0x1800f2e48  mov     edx, ebp; int
0x1800f2e4a  mov     rcx, rbx; this
0x1800f2e4d  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2e52  mov     edx, r15d
0x1800f2e55  jmp     loc_1800F308C
0x1800f2e5a  mov     ebp, 3
0x1800f2e5f  cmp     r8d, ebp
0x1800f2e62  jnz     loc_1800F2EE9
0x1800f2e68  mov     rcx, [rsp+68h]; this
0x1800f2e6d  test    rdi, rdi
0x1800f2e70  jz      loc_1800F3139
0x1800f2e76  mov     rcx, [rsp+68h]; this
0x1800f2e7b  mov     r13, [rsp+68h+arg_30]
0x1800f2e83  test    r13, r13
0x1800f2e86  jz      loc_1800F3151
0x1800f2e8c  mov     r12, [rsp+68h+Source]
0x1800f2e94  test    r12, r12
0x1800f2e97  jz      short loc_1800F2ECF
0x1800f2e99  mov     rdx, r15; MaxCount
0x1800f2e9c  mov     rcx, r12; Source
0x1800f2e9f  call    cs:__imp_wcsnlen
0x1800f2ea5  test    rax, rax
0x1800f2ea8  jz      short loc_1800F2ECF
0x1800f2eaa  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2ead  lea     rdx, aInsertIntoClas; "INSERT INTO ClassicGlobalWithConsentID("...
0x1800f2eb4  mov     rcx, r14; this
0x1800f2eb7  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2ebc  mov     r8, rdi; wchar_t *
0x1800f2ebf  mov     edx, r15d; int
0x1800f2ec2  mov     rcx, rbx; this
0x1800f2ec5  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2eca  jmp     loc_1800F2E0B
0x1800f2ecf  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2ed2  lea     rdx, aInsertIntoClas_0; "INSERT INTO ClassicGlobal(Capability, U"...
0x1800f2ed9  mov     rcx, r14; this
0x1800f2edc  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2ee1  mov     r15d, ebp
0x1800f2ee4  jmp     loc_1800F2E2B
0x1800f2ee9  mov     r15d, 4
0x1800f2eef  cmp     r8d, r15d
0x1800f2ef2  jnz     loc_1800F2FEA
0x1800f2ef8  mov     rcx, [rsp+68h]; this
0x1800f2efd  test    rdi, rdi
0x1800f2f00  jz      loc_1800F3169
0x1800f2f06  mov     rcx, [rsp+68h]; this
0x1800f2f0b  cmp     [rsp+68h+arg_28], 0
0x1800f2f14  jz      loc_1800F3181
0x1800f2f1a  mov     rcx, [rsp+68h]; this
0x1800f2f1f  cmp     [rsp+68h+arg_30], 0
0x1800f2f28  jz      loc_1800F3199
0x1800f2f2e  mov     r13, [rsp+68h+Source]
0x1800f2f36  test    r13, r13
0x1800f2f39  jz      short loc_1800F2F7E
0x1800f2f3b  lea     r12d, [r15-3]
0x1800f2f3f  mov     edx, r12d; MaxCount
0x1800f2f42  mov     rcx, r13; Source
0x1800f2f45  call    cs:__imp_wcsnlen
0x1800f2f4b  test    rax, rax
0x1800f2f4e  jz      short loc_1800F2F7E
0x1800f2f50  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2f53  lea     rdx, aInsertIntoAppw; "INSERT INTO AppWithConsentID(Capability"...
0x1800f2f5a  mov     rcx, r14; this
0x1800f2f5d  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2f62  mov     r8, rdi; wchar_t *
0x1800f2f65  mov     edx, r12d; int
0x1800f2f68  mov     rcx, rbx; this
0x1800f2f6b  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2f70  lea     r12d, [r15+1]
0x1800f2f74  mov     r8, [rsp+68h+arg_30]
0x1800f2f7c  jmp     short loc_1800F2FB8
0x1800f2f7e  mov     r8, rbx; struct StateRepository::Statement *
0x1800f2f81  lea     rdx, aInsertIntoAppC; "INSERT INTO App(Capability, User, Packa"...
0x1800f2f88  mov     rcx, r14; this
0x1800f2f8b  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f2f90  mov     r12d, r15d
0x1800f2f93  mov     r15d, ebp
0x1800f2f96  mov     r13, [rsp+68h+arg_28]
0x1800f2f9e  mov     ebp, esi
0x1800f2fa0  mov     r8, [rsp+68h+arg_30]
0x1800f2fa8  mov     [rsp+68h+arg_28], r8
0x1800f2fb0  mov     esi, 1
0x1800f2fb5  mov     r8, rdi; wchar_t *
0x1800f2fb8  mov     edx, esi; int
0x1800f2fba  mov     rcx, rbx; this
0x1800f2fbd  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2fc2  mov     r8, [rsp+68h+arg_28]; wchar_t *
0x1800f2fca  mov     edx, ebp; int
0x1800f2fcc  mov     rcx, rbx; this
0x1800f2fcf  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2fd4  mov     r8, r13; wchar_t *
0x1800f2fd7  mov     edx, r15d; int
0x1800f2fda  mov     rcx, rbx; this
0x1800f2fdd  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f2fe2  mov     edx, r12d
0x1800f2fe5  jmp     loc_1800F308C
0x1800f2fea  cmp     r8d, 6
0x1800f2fee  jnz     short loc_1800F302C
0x1800f2ff0  mov     rcx, [rsp+68h]; this
0x1800f2ff5  mov     rdi, [rsp+68h+arg_30]
0x1800f2ffd  test    rdi, rdi
0x1800f3000  jz      loc_1800F31B1
0x1800f3006  mov     r8, rbx; struct StateRepository::Statement *
0x1800f3009  lea     rdx, aInsertIntoMigr; "INSERT INTO MigratedUsers(User, Value) "...
0x1800f3010  mov     rcx, r14; this
0x1800f3013  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f3018  mov     r8, rdi; wchar_t *
0x1800f301b  mov     edx, 1; int
0x1800f3020  mov     rcx, rbx; this
0x1800f3023  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f3028  mov     edx, esi
0x1800f302a  jmp     short loc_1800F308C
0x1800f302c  mov     r12d, 5
0x1800f3032  cmp     r8d, r12d
0x1800f3035  jnz     loc_1800F30CD
0x1800f303b  mov     rcx, [rsp+68h]; this
0x1800f3040  test    rdi, rdi
0x1800f3043  jz      loc_1800F31C9
0x1800f3049  mov     rcx, [rsp+68h]; this
0x1800f304e  mov     r15, [rsp+68h+arg_30]
0x1800f3056  test    r15, r15
0x1800f3059  jz      short loc_1800F30B5
0x1800f305b  mov     r8, rbx; struct StateRepository::Statement *
0x1800f305e  lea     rdx, aInsertIntoShow; "INSERT INTO ShowGlobalPrompts(Capabilit"...
0x1800f3065  mov     rcx, r14; this
0x1800f3068  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f306d  mov     r8, rdi; wchar_t *
0x1800f3070  lea     edx, [r12-4]; int
0x1800f3075  mov     rcx, rbx; this
0x1800f3078  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f307d  mov     r8, r15; wchar_t *
0x1800f3080  mov     edx, esi; int
0x1800f3082  mov     rcx, rbx; this
0x1800f3085  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800f308a  mov     edx, ebp; int
0x1800f308c  mov     r8, [rsp+68h+arg_38]; __int64
0x1800f3094  mov     rcx, rbx; this
0x1800f3097  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f309c  nop
0x1800f309d  mov     rcx, r14; this
0x1800f30a0  add     rsp, 28h
0x1800f30a4  pop     r15
0x1800f30a6  pop     r14
0x1800f30a8  pop     r13
0x1800f30aa  pop     r12
0x1800f30ac  pop     rdi
0x1800f30ad  pop     rsi
0x1800f30ae  pop     rbp
0x1800f30af  pop     rbx
0x1800f30b0  jmp     ??1DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(void)
0x1800f30b5  mov     r9d, 80070057h; char *
0x1800f30bb  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f30c2  mov     edx, 251h; void *
0x1800f30c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f30cd  mov     ecx, 80070057h
0x1800f30d2  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800f30d7  mov     r9d, eax; char *
0x1800f30da  mov     rcx, [rsp+68h]; this
0x1800f30df  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f30e6  mov     edx, 25Eh; void *
0x1800f30eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f30f1  mov     r9d, 80070057h; char *
0x1800f30f7  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f30fe  mov     edx, 1C6h; void *
0x1800f3103  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3109  mov     r9d, 80070057h; char *
0x1800f310f  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3116  mov     edx, 1D8h; void *
0x1800f311b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3121  mov     r9d, 80070057h; char *
0x1800f3127  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f312e  mov     edx, 1D9h; void *
0x1800f3133  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3139  mov     r9d, 80070057h; char *
0x1800f313f  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3146  mov     edx, 1FBh; void *
0x1800f314b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3151  mov     r9d, 80070057h; char *
0x1800f3157  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f315e  mov     edx, 1FCh; void *
0x1800f3163  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3169  mov     r9d, 80070057h; char *
0x1800f316f  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3176  mov     edx, 21Fh; void *
0x1800f317b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3181  mov     r9d, 80070057h; char *
0x1800f3187  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f318e  mov     edx, 220h; void *
0x1800f3193  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3199  mov     r9d, 80070057h; char *
0x1800f319f  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f31a6  mov     edx, 221h; void *
0x1800f31ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f31b1  mov     r9d, 80070057h; char *
0x1800f31b7  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f31be  mov     edx, 23Fh; void *
0x1800f31c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f31c9  mov     r9d, 80070057h; char *
0x1800f31cf  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f31d6  mov     edx, 250h; void *
0x1800f31db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
