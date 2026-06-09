# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CreateStorageTables(std::shared_ptr<StateRepository::Database> const &)

- ea: `0x1800eebf4`
- end: `0x1800eefeb`
- name: `?CreateStorageTables@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXAEBV?$shared_ptr@VDatabase@StateRepository@@@std@@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(StateRepository::Database **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800f2a54`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e5e6c`
- `0x1800e793c`
- `0x1800edb4c`
- `0x1800ee860`
- `0x1800eea8c`
- `0x1800eebf4`
- `0x1800f4314`
- `0x1800f4818`
- `0x1800f9300`
- `0x1800f9d28`

## string_xrefs

- `0x1800eedc5`: `CREATE TABLE IF NOT EXISTS SystemGlobal(Capability TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability));`
- `0x1800eeddc`: `CREATE TABLE IF NOT EXISTS UserGlobal(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User));`
- `0x1800eedf3`: `CREATE TABLE IF NOT EXISTS ClassicGlobal(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User));`
- `0x1800eee0a`: `CREATE TABLE IF NOT EXISTS App(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,PackageFamily TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, PackageFamily));`
- `0x1800eee21`: `CREATE TABLE IF NOT EXISTS UserGlobalWithConsentID(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,ConsentID TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, ConsentID));`
- `0x1800eee38`: `CREATE TABLE IF NOT EXISTS ClassicGlobalWithConsentID(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,ConsentID TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, ConsentID));`
- `0x1800eee4f`: `CREATE TABLE IF NOT EXISTS AppWithConsentID(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,PackageFamily TEXT COLLATE NOCASE NOT NULL,ConsentID TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, PackageFamily, ConsentID));`
- `0x1800eedae`: `CREATE TABLE IF NOT EXISTS MigratedUsers(User TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(User));`
- `0x1800eee66`: `CREATE TABLE IF NOT EXISTS ShowGlobalPrompts(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(User, Capability));`
- `0x1800eecca`: `CREATE TABLE IF NOT EXISTS %s(ID INTEGER PRIMARY KEY NOT NULL,StringValue TEXT COLLATE NOCASE NOT NULL,UNIQUE(StringValue));`
- `0x1800eec5b`: `CREATE TABLE IF NOT EXISTS McpConsent(ID INTEGER PRIMARY KEY NOT NULL,User INTEGER NOT NULL,Client INTEGER NOT NULL,Server INTEGER NOT NULL,Resource INTEGER NOT NULL,Operation INTEGER NOT NULL,ExpiryTime INTEGER NOT NULL,Value INTEGER NOT NULL,UNIQUE(User, Client, Server, Resource, Operation));`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::CreateStorageTables(
        StateRepository::Database **a1)
{
  unsigned int v2; // r14d
  StateRepository::Database *v3; // rcx
  const char *v4; // r9
  int (*v5)(void *); // r8
  void *v6; // r9
  int v7; // eax
  const char **v8; // r12
  StateRepository::Database *v9; // r13
  size_t v10; // rsi
  int v11; // r14d
  char *v12; // rcx
  int (*v13)(void *); // r8
  void *v14; // r9
  size_t v15; // rcx
  char **v16; // rax
  size_t v17; // r15
  char **v18; // rbx
  char *v19; // rbx
  const char *v20; // rdx
  int v21; // eax
  int v22; // eax
  int (*v23)(void *); // r8
  void *v24; // r9
  int v25; // eax
  int (*v26)(void *); // r8
  void *v27; // r9
  int v28; // eax
  int (*v29)(void *); // r8
  void *v30; // r9
  int v31; // eax
  int (*v32)(void *); // r8
  void *v33; // r9
  int v34; // eax
  int (*v35)(void *); // r8
  void *v36; // r9
  int v37; // eax
  int (*v38)(void *); // r8
  void *v39; // r9
  int v40; // eax
  int (*v41)(void *); // r8
  void *v42; // r9
  int v43; // eax
  int (*v44)(void *); // r8
  void *v45; // r9
  __int64 result; // rax
  unsigned int v47; // eax
  int v48; // [rsp+20h] [rbp-58h]
  char *Buffer[2]; // [rsp+48h] [rbp-30h] BYREF
  size_t v50; // [rsp+58h] [rbp-20h]
  unsigned __int64 v51; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v2 = 0;
  v3 = *a1;
  if ( !*(_QWORD *)v3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)retaddr);
  if ( StateRepository::Database::IsInAutoCommitMode(v3) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      v4);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
  {
    v7 = StateRepository::Database::Execute(
           *a1,
           "CREATE TABLE IF NOT EXISTS McpConsent(ID INTEGER PRIMARY KEY NOT NULL,User INTEGER NOT NULL,Client INTEGER NO"
           "T NULL,Server INTEGER NOT NULL,Resource INTEGER NOT NULL,Operation INTEGER NOT NULL,ExpiryTime INTEGER NOT NU"
           "LL,Value INTEGER NOT NULL,UNIQUE(User, Client, Server, Resource, Operation));",
           v5,
           v6);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
        (const char *)(unsigned int)v7,
        v48);
    v8 = (const char **)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::SQLStringTableNames;
    do
    {
      v9 = *a1;
      v10 = 64;
      *(_OWORD *)Buffer = 0;
      v50 = 0;
      v51 = 15;
      LOBYTE(Buffer[0]) = 0;
      v11 = v2 | 1;
LABEL_7:
      std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(Buffer);
      while ( 1 )
      {
        v12 = (char *)Buffer;
        if ( v51 > 0xF )
          v12 = Buffer[0];
        if ( (unsigned int)StringCchPrintfExA(
                             v12,
                             v10,
                             0,
                             0,
                             0,
                             "CREATE TABLE IF NOT EXISTS %s(ID INTEGER PRIMARY KEY NOT NULL,StringValue TEXT COLLATE NOCA"
                             "SE NOT NULL,UNIQUE(StringValue));",
                             *v8) != -2147024774 )
          break;
        if ( v10 > 0x400 )
        {
          v47 = wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x279,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\Database.h",
            (const char *)v47,
            v48);
        }
        v10 *= 2LL;
        v15 = v50;
        if ( v10 > v50 )
        {
          v17 = v10 - v50;
          if ( v10 - v50 > v51 - v50 )
            goto LABEL_7;
          v50 = v10;
          v18 = Buffer;
          if ( v51 > 0xF )
            v18 = (char **)Buffer[0];
          v19 = (char *)v18 + v15;
          memset_0(v19, 0, v10 - v15);
          v19[v17] = 0;
        }
        else
        {
          v50 = v10;
          v16 = Buffer;
          if ( v51 > 0xF )
            v16 = (char **)Buffer[0];
          *((_BYTE *)v16 + v10) = 0;
        }
      }
      v20 = (const char *)Buffer;
      if ( v51 > 0xF )
        v20 = Buffer[0];
      v21 = StateRepository::Database::Execute(v9, v20, v13, v14);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
          (const char *)(unsigned int)v21,
          v48);
      v2 = v11 & 0xFFFFFFFE;
      std::string::~string(Buffer);
      ++v8;
    }
    while ( v8 != (const char **)&Common::StateSeparation::AppxRoot );
  }
  v22 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS MigratedUsers(User TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(User));",
          v5,
          v6);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v22,
      v48);
  v25 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS SystemGlobal(Capability TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY"
          " KEY(Capability));",
          v23,
          v24);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v25,
      v48);
  v28 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS UserGlobal(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NUL"
          "L,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User));",
          v26,
          v27);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v28,
      v48);
  v31 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS ClassicGlobal(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT "
          "NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User));",
          v29,
          v30);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v31,
      v48);
  v34 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS App(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE NOT NULL,Packa"
          "geFamily TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, PackageFamily));",
          v32,
          v33);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v34,
      v48);
  v37 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS UserGlobalWithConsentID(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE N"
          "OCASE NOT NULL,ConsentID TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, ConsentID));",
          v35,
          v36);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v37,
      v48);
  v40 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS ClassicGlobalWithConsentID(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLAT"
          "E NOCASE NOT NULL,ConsentID TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(Capability, User, ConsentID));",
          v38,
          v39);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v40,
      v48);
  v43 = StateRepository::Database::Execute(
          *a1,
          "CREATE TABLE IF NOT EXISTS AppWithConsentID(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCASE N"
          "OT NULL,PackageFamily TEXT COLLATE NOCASE NOT NULL,ConsentID TEXT COLLATE NOCASE NOT NULL,Value INTEGER NOT NU"
          "LL,PRIMARY KEY(Capability, User, PackageFamily, ConsentID));",
          v41,
          v42);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)v43,
      v48);
  result = StateRepository::Database::Execute(
             *a1,
             "CREATE TABLE IF NOT EXISTS ShowGlobalPrompts(Capability TEXT COLLATE NOCASE NOT NULL,User TEXT COLLATE NOCA"
             "SE NOT NULL,Value INTEGER NOT NULL,PRIMARY KEY(User, Capability));",
             v44,
             v45);
  if ( (int)result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)(unsigned int)result,
      v48);
  return result;
}

```

## disassembly

```asm
0x1800eebf4  push    rbp
0x1800eebf6  push    rbx
0x1800eebf7  push    rsi
0x1800eebf8  push    rdi
0x1800eebf9  push    r12
0x1800eebfb  push    r13
0x1800eebfd  push    r14
0x1800eebff  push    r15
0x1800eec01  mov     rbp, rsp
0x1800eec04  sub     rsp, 78h
0x1800eec08  mov     rax, cs:__security_cookie
0x1800eec0f  xor     rax, rsp
0x1800eec12  mov     [rbp+var_10], rax
0x1800eec16  mov     rdi, rcx
0x1800eec19  xor     ebx, ebx
0x1800eec1b  mov     r14d, ebx
0x1800eec1e  mov     [rbp+var_38], ebx
0x1800eec21  mov     rcx, [rcx]; this
0x1800eec24  cmp     [rcx], rbx
0x1800eec27  setz    al
0x1800eec2a  mov     r9, [rbp+40h]; char *
0x1800eec2e  test    al, al
0x1800eec30  jnz     loc_1800EEEAF
0x1800eec36  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800eec3b  mov     rcx, [rbp+40h]; this
0x1800eec3f  test    al, al
0x1800eec41  jnz     loc_1800EEEC4
0x1800eec47  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800eec4e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800eec53  test    al, al
0x1800eec55  jz      loc_1800EEDAE
0x1800eec5b  lea     rdx, aCreateTableIfN_7; "CREATE TABLE IF NOT EXISTS McpConsent(I"...
0x1800eec62  mov     rcx, [rdi]; this
0x1800eec65  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eec6a  mov     rcx, [rbp+40h]; this
0x1800eec6e  test    eax, eax
0x1800eec70  js      loc_1800EEED6
0x1800eec76  lea     r12, ?SQLStringTableNames@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@3V?$array@PEBD$04@std@@B; std::array<char const *,5> const Windows::Internal::CapabilityAccess::Desktop::Storage::Database::SQLStringTableNames
0x1800eec7d  mov     eax, 40h ; '@'
0x1800eec82  mov     r13, [rdi]
0x1800eec85  mov     esi, eax
0x1800eec87  xorps   xmm0, xmm0
0x1800eec8a  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800eec8e  mov     [rbp+var_20], rbx
0x1800eec92  mov     [rbp+var_18], 0Fh
0x1800eec9a  mov     byte ptr [rbp+Buffer], bl
0x1800eec9d  or      r14d, 1
0x1800eeca1  mov     [rbp+var_38], r14d
0x1800eeca5  mov     r9d, eax
0x1800eeca8  mov     edx, eax
0x1800eecaa  lea     rcx, [rbp+Buffer]; Src
0x1800eecae  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x1800eecb3  mov     rax, [r12]
0x1800eecb7  lea     rcx, [rbp+Buffer]
0x1800eecbb  cmp     [rbp+var_18], 0Fh
0x1800eecc0  cmova   rcx, [rbp+Buffer]; Buffer
0x1800eecc5  mov     [rsp+78h+var_48], rax
0x1800eecca  lea     rax, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS %s(ID INTEGE"...
0x1800eecd1  mov     [rsp+78h+var_50], rax; char *
0x1800eecd6  mov     qword ptr [rsp+78h+var_58], rbx; int
0x1800eecdb  xor     r9d, r9d; unsigned __int64 *
0x1800eecde  xor     r8d, r8d; char **
0x1800eece1  mov     rdx, rsi; Size
0x1800eece4  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800eece9  cmp     eax, 8007007Ah
0x1800eecee  jnz     short loc_1800EED6B
0x1800eecf0  cmp     rsi, 400h
0x1800eecf7  ja      loc_1800EEF04
0x1800eecfd  add     rsi, rsi
0x1800eed00  mov     rcx, [rbp+var_20]
0x1800eed04  cmp     rsi, rcx
0x1800eed07  ja      short loc_1800EED20
0x1800eed09  mov     [rbp+var_20], rsi
0x1800eed0d  lea     rax, [rbp+Buffer]
0x1800eed11  cmp     [rbp+var_18], 0Fh
0x1800eed16  cmova   rax, [rbp+Buffer]
0x1800eed1b  mov     [rax+rsi], bl
0x1800eed1e  jmp     short loc_1800EECB3
0x1800eed20  mov     r15, rsi
0x1800eed23  sub     r15, rcx
0x1800eed26  mov     rax, [rbp+var_18]
0x1800eed2a  sub     rax, rcx
0x1800eed2d  cmp     r15, rax
0x1800eed30  ja      short loc_1800EED60
0x1800eed32  mov     [rbp+var_20], rsi
0x1800eed36  lea     rbx, [rbp+Buffer]
0x1800eed3a  cmp     [rbp+var_18], 0Fh
0x1800eed3f  cmova   rbx, [rbp+Buffer]
0x1800eed44  add     rbx, rcx
0x1800eed47  mov     r8, r15; Size
0x1800eed4a  xor     edx, edx; Val
0x1800eed4c  mov     rcx, rbx; void *
0x1800eed4f  call    memset_0
0x1800eed54  mov     byte ptr [rbx+r15], 0
0x1800eed59  xor     ebx, ebx
0x1800eed5b  jmp     loc_1800EECB3
0x1800eed60  mov     r9, r15
0x1800eed63  mov     rdx, r15
0x1800eed66  jmp     loc_1800EECAA
0x1800eed6b  lea     rdx, [rbp+Buffer]
0x1800eed6f  cmp     [rbp+var_18], 0Fh
0x1800eed74  cmova   rdx, [rbp+Buffer]; char *
0x1800eed79  mov     rcx, r13; this
0x1800eed7c  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eed81  mov     rcx, [rbp+40h]; this
0x1800eed85  test    eax, eax
0x1800eed87  js      loc_1800EEF27
0x1800eed8d  and     r14d, 0FFFFFFFEh
0x1800eed91  lea     rcx, [rbp+Buffer]
0x1800eed95  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800eed9a  add     r12, 8
0x1800eed9e  lea     rax, ?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppxRoot
0x1800eeda5  cmp     r12, rax
0x1800eeda8  jnz     loc_1800EEC7D
0x1800eedae  lea     rdx, aCreateTableIfN_9; "CREATE TABLE IF NOT EXISTS MigratedUser"...
0x1800eedb5  mov     rcx, [rdi]; this
0x1800eedb8  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eedbd  test    eax, eax
0x1800eedbf  js      loc_1800EEEEB
0x1800eedc5  lea     rdx, aCreateTableIfN_4; "CREATE TABLE IF NOT EXISTS SystemGlobal"...
0x1800eedcc  mov     rcx, [rdi]; this
0x1800eedcf  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eedd4  test    eax, eax
0x1800eedd6  js      loc_1800EEF3C
0x1800eeddc  lea     rdx, aCreateTableIfN_10; "CREATE TABLE IF NOT EXISTS UserGlobal(C"...
0x1800eede3  mov     rcx, [rdi]; this
0x1800eede6  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eedeb  test    eax, eax
0x1800eeded  js      loc_1800EEF55
0x1800eedf3  lea     rdx, aCreateTableIfN_6; "CREATE TABLE IF NOT EXISTS ClassicGloba"...
0x1800eedfa  mov     rcx, [rdi]; this
0x1800eedfd  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eee02  test    eax, eax
0x1800eee04  js      loc_1800EEF6E
0x1800eee0a  lea     rdx, aCreateTableIfN_8; "CREATE TABLE IF NOT EXISTS App(Capabili"...
0x1800eee11  mov     rcx, [rdi]; this
0x1800eee14  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eee19  test    eax, eax
0x1800eee1b  js      loc_1800EEF87
0x1800eee21  lea     rdx, aCreateTableIfN_1; "CREATE TABLE IF NOT EXISTS UserGlobalWi"...
0x1800eee28  mov     rcx, [rdi]; this
0x1800eee2b  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eee30  test    eax, eax
0x1800eee32  js      loc_1800EEFA0
0x1800eee38  lea     rdx, aCreateTableIfN_0; "CREATE TABLE IF NOT EXISTS ClassicGloba"...
0x1800eee3f  mov     rcx, [rdi]; this
0x1800eee42  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eee47  test    eax, eax
0x1800eee49  js      loc_1800EEFB9
0x1800eee4f  lea     rdx, aCreateTableIfN_2; "CREATE TABLE IF NOT EXISTS AppWithConse"...
0x1800eee56  mov     rcx, [rdi]; this
0x1800eee59  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eee5e  test    eax, eax
0x1800eee60  js      loc_1800EEFD2
0x1800eee66  lea     rdx, aCreateTableIfN_5; "CREATE TABLE IF NOT EXISTS ShowGlobalPr"...
0x1800eee6d  mov     rcx, [rdi]; this
0x1800eee70  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800eee75  test    eax, eax
0x1800eee77  js      short loc_1800EEE96
0x1800eee79  mov     rcx, [rbp+var_10]
0x1800eee7d  xor     rcx, rsp; StackCookie
0x1800eee80  call    __security_check_cookie
0x1800eee85  add     rsp, 78h
0x1800eee89  pop     r15
0x1800eee8b  pop     r14
0x1800eee8d  pop     r13
0x1800eee8f  pop     r12
0x1800eee91  pop     rdi
0x1800eee92  pop     rsi
0x1800eee93  pop     rbx
0x1800eee94  pop     rbp
0x1800eee95  retn
0x1800eee96  mov     rcx, [rbp+40h]; this
0x1800eee9a  mov     r9d, eax; char *
0x1800eee9d  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eeea4  mov     edx, 166h; void *
0x1800eeea9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eeeaf  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eeeb6  mov     edx, 14Fh; void *
0x1800eeebb  mov     rcx, r9; this
0x1800eeebe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800eeec4  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eeecb  mov     edx, 150h; void *
0x1800eeed0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800eeed6  mov     r9d, eax; char *
0x1800eeed9  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eeee0  mov     edx, 154h; void *
0x1800eeee5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eeeeb  mov     rcx, [rbp+40h]; this
0x1800eeeef  mov     r9d, eax; char *
0x1800eeef2  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eeef9  mov     edx, 15Ch; void *
0x1800eeefe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eef04  mov     ecx, 80070057h
0x1800eef09  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800eef0e  mov     r9d, eax; char *
0x1800eef11  mov     rcx, [rbp+40h]; this
0x1800eef15  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eef1c  mov     edx, 279h; void *
0x1800eef21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eef27  mov     r9d, eax; char *
0x1800eef2a  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eef31  mov     edx, 158h; void *
0x1800eef36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eef3c  mov     rcx, [rbp+40h]; this
0x1800eef40  mov     r9d, eax; char *
0x1800eef43  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eef4a  mov     edx, 15Dh; void *
0x1800eef4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eef55  mov     rcx, [rbp+40h]; this
0x1800eef59  mov     r9d, eax; char *
0x1800eef5c  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eef63  mov     edx, 15Eh; void *
0x1800eef68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eef6e  mov     rcx, [rbp+40h]; this
0x1800eef72  mov     r9d, eax; char *
0x1800eef75  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eef7c  mov     edx, 15Fh; void *
0x1800eef81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eef87  mov     rcx, [rbp+40h]; this
0x1800eef8b  mov     r9d, eax; char *
0x1800eef8e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eef95  mov     edx, 160h; void *
0x1800eef9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eefa0  mov     rcx, [rbp+40h]; this
0x1800eefa4  mov     r9d, eax; char *
0x1800eefa7  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eefae  mov     edx, 162h; void *
0x1800eefb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eefb9  mov     rcx, [rbp+40h]; this
0x1800eefbd  mov     r9d, eax; char *
0x1800eefc0  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eefc7  mov     edx, 163h; void *
0x1800eefcc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800eefd2  mov     rcx, [rbp+40h]; this
0x1800eefd6  mov     r9d, eax; char *
0x1800eefd9  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800eefe0  mov     edx, 164h; void *
0x1800eefe5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
