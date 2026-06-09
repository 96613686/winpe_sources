# StateRepository::Entity::Application::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::Application &,bool &)

- ea: `0x180012e84`
- end: `0x1800131f0`
- name: `?TryGet@Application@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z`
- size: `876`
- prototype: `__int64 __fastcall(struct StateRepository::Database *, __int64, struct Application *, bool *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180012c20`
- `0x180070618`
- `0x1802782b4`
- `0x180278880`

## callees

- `0x180007a40`
- `0x180010d28`
- `0x180012e84`
- `0x1800131f8`
- `0x180017a58`
- `0x180018bbc`
- `0x180019794`
- `0x18001a548`
- `0x18001a9e0`
- `0x180039570`
- `0x18020b074`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int64` at `0x180012fc6`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180012fff`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180012fc6`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180012fff`

## string_xrefs

- `0x180012e9a`: `SELECT _Revision, _WorkId, Package, "Index", ApplicationType, Flags, Subsystem, PackageRelativeApplicationId, ApplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150Logo, Square310x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, Entrypoint, StartPage, ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBackgroundColor, InitialRotationPreference, ApplicationViewMinWidth, App`
- `0x180012ea5`: `SELECT _Revision, _WorkId, Package, "Index", ApplicationType, Flags, Subsystem, PackageRelativeApplicationId, ApplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150Logo, Square310x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, Entrypoint, StartPage, ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBackgroundColor, InitialRotationPreference, ApplicationViewMinWidth, App`
- `0x180012ec9`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180012eed`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18001307a`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180012f8d`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x180012f59`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180013026`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180013104`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180013158`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180013170`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001318d`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1800131a5`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180012f00`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application.cpp`
- `0x1800130c8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application.cpp`
- `0x1800131ce`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Application::TryGet(
        struct StateRepository::Database *a1,
        __int64 a2,
        struct Application *a3,
        bool *a4)
{
  const char *v4; // rbx
  bool v5; // zf
  signed int v10; // ebx
  __int64 v11; // rdx
  signed int v12; // eax
  StateRepository::StatementCache *v14; // r15
  int v15; // eax
  int v16; // r8d
  bool v17; // si
  int v18; // eax
  __int64 v19; // r8
  bool v20; // sf
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // ebx
  const char **v29; // [rsp+20h] [rbp-18h]
  int v30; // [rsp+20h] [rbp-18h]
  int v31; // [rsp+20h] [rbp-18h]
  int v32; // [rsp+20h] [rbp-18h]
  int v33; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]
  struct sqlite3_stmt *v35; // [rsp+80h] [rbp+48h] BYREF

  v4 = "SELECT _Revision, _WorkId, Package, \"Index\", ApplicationType, Flags, Subsystem, PackageRelativeApplicationId, A"
       "pplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150Logo, Square310x3"
       "10Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, Entrypoint, StartPage, "
       "ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBackgroundColor, Initi"
       "alRotationPreference, ApplicationViewMinWidth, AppListEntry, EditionId, VisualGroup, Parameters, CurrentDirectory"
       "Path, _Dictionary FROM Application WHERE _ApplicationID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;";
  v5 = *((_QWORD *)a1 + 1) == 0;
  v35 = 0;
  if ( v5 )
    v4 = "SELECT _Revision, _WorkId, Package, \"Index\", ApplicationType, Flags, Subsystem, PackageRelativeApplicationId,"
         " ApplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150Logo, Square3"
         "10x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, Entrypoint, Start"
         "Page, ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBackgroundColo"
         "r, InitialRotationPreference, ApplicationViewMinWidth, AppListEntry, EditionId, VisualGroup, Parameters, Curren"
         "tDirectoryPath, _Dictionary FROM Application WHERE _ApplicationID=? AND _WorkId=0;";
  if ( !*(_QWORD *)a1 )
  {
    v10 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      (int)v29);
LABEL_5:
    v11 = 164;
LABEL_6:
    v12 = v10;
    goto LABEL_7;
  }
  v14 = (struct StateRepository::Database *)((char *)a1 + 40);
  if ( !StateRepository::StatementCache::Get(
          (struct StateRepository::Database *)((char *)a1 + 40),
          v4,
          (struct StateRepository::Statement *)&v35) )
  {
    v15 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v35);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
        (const char *)(unsigned int)v15,
        (int)v29);
    v10 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)a1, v4, v16, &v35, v29);
    if ( v10 < 0 )
      goto LABEL_5;
  }
  if ( !v35 )
  {
    v10 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v29);
LABEL_12:
    v11 = 165;
    goto LABEL_6;
  }
  v17 = 1;
  v18 = sqlite3_bind_int64(v35, 1, a2);
  v10 = v18;
  if ( v18 > 0 )
    v10 = (unsigned __int16)v18 | 0x87AF0000;
  if ( v10 < 0 )
    goto LABEL_12;
  v19 = *((_QWORD *)a1 + 1);
  v10 = -2147019873;
  if ( v19 )
  {
    if ( v35 )
    {
      v12 = sqlite3_bind_int64(v35, 2, v19);
      v20 = v12 < 0;
      if ( v12 <= 0 )
        goto LABEL_25;
      v12 = (unsigned __int16)v12 | 0x87AF0000;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        (int)v29);
      v12 = -2147019873;
    }
    v20 = v12 < 0;
LABEL_25:
    if ( v20 )
    {
      v10 = v12;
      v11 = 168;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)(unsigned int)v12,
        (int)v29);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C8,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application.cpp",
        (const char *)(unsigned int)v10,
        v30);
      if ( v35 )
      {
        v25 = StateRepository::Statement::dal_finalize(v35);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v25,
            v31);
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)v26,
            v32);
        }
        else
        {
          v35 = 0;
        }
      }
      return (unsigned int)v10;
    }
  }
  if ( !v35 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v29);
LABEL_28:
    v11 = 171;
    goto LABEL_6;
  }
  v21 = StateRepository::Statement::dal_step(v35);
  v10 = v21;
  if ( v21 == -2018574236 )
    goto LABEL_30;
  if ( v21 == -2018574235 )
  {
    v17 = 0;
LABEL_30:
    *a4 = v17;
    goto LABEL_31;
  }
  if ( v21 < 0 )
    goto LABEL_28;
LABEL_31:
  if ( *a4 )
    goto LABEL_57;
  if ( v35 )
  {
    v22 = StateRepository::StatementCache::Add(v14, (struct StateRepository::Statement *)&v35);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)(unsigned int)v22,
        (int)v29);
  }
  if ( *a4 )
  {
LABEL_57:
    v23 = StateRepository::Entity::Application::RowToObject((const struct StateRepository::Statement *)&v35, a3, a2);
    v10 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CC,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application.cpp",
        (const char *)(unsigned int)v23,
        (int)v29);
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v35);
      return (unsigned int)v10;
    }
  }
  if ( v35 )
  {
    v24 = StateRepository::StatementCache::Add(v14, (struct StateRepository::Statement *)&v35);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application.cpp",
        (const char *)(unsigned int)v24,
        (int)v29);
  }
  if ( v35 )
  {
    v27 = StateRepository::Statement::dal_finalize(v35);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v27,
        (int)v29);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)v28,
        v33);
    }
    else
    {
      v35 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012e84  push    rbp
0x180012e86  push    rbx
0x180012e87  push    rsi
0x180012e88  push    rdi
0x180012e89  push    r12
0x180012e8b  push    r13
0x180012e8d  push    r14
0x180012e8f  push    r15
0x180012e91  mov     rbp, rsp
0x180012e94  sub     rsp, 38h
0x180012e98  xor     esi, esi
0x180012e9a  lea     rbx, aSelectRevision_82; "SELECT _Revision, _WorkId, Package, \"I"...
0x180012ea1  cmp     [rcx+8], rsi
0x180012ea5  lea     rax, aSelectRevision_99; "SELECT _Revision, _WorkId, Package, \"I"...
0x180012eac  mov     r14, r9
0x180012eaf  mov     [rbp+arg_0], rsi
0x180012eb3  cmovz   rbx, rax
0x180012eb7  mov     r13, r8
0x180012eba  mov     r12, rdx
0x180012ebd  mov     rdi, rcx
0x180012ec0  cmp     [rcx], rsi
0x180012ec3  jnz     short loc_180012F34
0x180012ec5  mov     rcx, [rbp+40h]; this
0x180012ec9  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x180012ed0  mov     ebx, 8007139Fh
0x180012ed5  mov     edx, 66Eh; void *
0x180012eda  mov     r9d, ebx; char *
0x180012edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ee2  mov     edx, 0A4h; void *
0x180012ee7  mov     eax, ebx
0x180012ee9  mov     rcx, [rbp+40h]; this
0x180012eed  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x180012ef4  mov     r9d, eax; char *
0x180012ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012efc  mov     rcx, [rbp+40h]; this
0x180012f00  lea     r8, aOnecoreBaseApp_435; "onecore\\base\\appmodel\\staterepositor"...
0x180012f07  mov     r9d, ebx; char *
0x180012f0a  mov     edx, 3C8h; void *
0x180012f0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f14  mov     rcx, [rbp+arg_0]; struct sqlite3_stmt *
0x180012f18  test    rcx, rcx
0x180012f1b  jnz     loc_18001311F
0x180012f21  mov     eax, ebx
0x180012f23  add     rsp, 38h
0x180012f27  pop     r15
0x180012f29  pop     r14
0x180012f2b  pop     r13
0x180012f2d  pop     r12
0x180012f2f  pop     rdi
0x180012f30  pop     rsi
0x180012f31  pop     rbx
0x180012f32  pop     rbp
0x180012f33  retn
0x180012f34  lea     r15, [rcx+28h]
0x180012f38  mov     rdx, rbx; char *
0x180012f3b  mov     rcx, r15; this
0x180012f3e  lea     r8, [rbp+arg_0]; struct StateRepository::Statement *
0x180012f42  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x180012f47  test    rax, rax
0x180012f4a  jz      short loc_180012F7C
0x180012f4c  mov     rcx, [rbp+arg_0]
0x180012f50  test    rcx, rcx
0x180012f53  jnz     short loc_180012FBC
0x180012f55  mov     rcx, [rbp+40h]; this
0x180012f59  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180012f60  mov     ebx, 8007139Fh
0x180012f65  mov     edx, 0C9h; void *
0x180012f6a  mov     r9d, ebx; char *
0x180012f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f72  mov     edx, 0A5h
0x180012f77  jmp     loc_180012EE7
0x180012f7c  lea     rcx, [rbp+arg_0]; this
0x180012f80  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180012f85  test    eax, eax
0x180012f87  jns     short loc_180012FA1
0x180012f89  mov     rcx, [rbp+40h]; this
0x180012f8d  lea     r8, aOnecoreBaseApp_149; "onecore\\base\\appmodel\\StateRepositor"...
0x180012f94  mov     r9d, eax; char *
0x180012f97  mov     edx, 127h; void *
0x180012f9c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012fa1  mov     rcx, [rdi]; struct sqlite3 *
0x180012fa4  lea     r9, [rbp+arg_0]; struct sqlite3_stmt **
0x180012fa8  mov     rdx, rbx; char *
0x180012fab  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x180012fb0  mov     ebx, eax
0x180012fb2  test    eax, eax
0x180012fb4  js      loc_180012EE2
0x180012fba  jmp     short loc_180012F4C
0x180012fbc  mov     esi, 1
0x180012fc1  mov     r8, r12
0x180012fc4  mov     edx, esi
0x180012fc6  call    cs:__imp_sqlite3_bind_int64
0x180012fcc  mov     ebx, eax
0x180012fce  test    eax, eax
0x180012fd0  jle     short loc_180012FDB
0x180012fd2  movzx   ebx, ax
0x180012fd5  or      ebx, 87AF0000h
0x180012fdb  test    ebx, ebx
0x180012fdd  js      short loc_180012F72
0x180012fdf  mov     r8, [rdi+8]
0x180012fe3  mov     ebx, 8007139Fh
0x180012fe8  test    r8, r8
0x180012feb  jz      short loc_180013019
0x180012fed  mov     rcx, [rbp+arg_0]
0x180012ff1  test    rcx, rcx
0x180012ff4  jz      loc_180013100
0x180012ffa  mov     edx, 2
0x180012fff  call    cs:__imp_sqlite3_bind_int64
0x180013005  test    eax, eax
0x180013007  jle     short loc_180013013
0x180013009  movzx   eax, ax
0x18001300c  or      eax, 87AF0000h
0x180013011  test    eax, eax
0x180013013  js      loc_1800131BE
0x180013019  mov     rcx, [rbp+arg_0]; struct sqlite3_stmt *
0x18001301d  test    rcx, rcx
0x180013020  jnz     short loc_180013044
0x180013022  mov     rcx, [rbp+40h]; this
0x180013026  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18001302d  mov     r9d, ebx; char *
0x180013030  mov     edx, 3Fh ; '?'; void *
0x180013035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001303a  mov     edx, 0ABh
0x18001303f  jmp     loc_180012EE7
0x180013044  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x180013049  mov     ebx, eax
0x18001304b  cmp     eax, 87AF0064h
0x180013050  jnz     loc_1800130EC
0x180013056  mov     [r14], sil
0x180013059  cmp     byte ptr [r14], 0
0x18001305d  jnz     short loc_180013094
0x18001305f  cmp     [rbp+arg_0], 0
0x180013064  jz      short loc_18001308E
0x180013066  lea     rdx, [rbp+arg_0]; struct StateRepository::Statement *
0x18001306a  mov     rcx, r15; this
0x18001306d  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x180013072  test    eax, eax
0x180013074  jns     short loc_18001308E
0x180013076  mov     rcx, [rbp+40h]; this
0x18001307a  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x180013081  mov     r9d, eax; char *
0x180013084  mov     edx, 0AFh; void *
0x180013089  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001308e  cmp     byte ptr [r14], 0
0x180013092  jz      short loc_1800130AD
0x180013094  mov     r8, r12; __int64
0x180013097  lea     rcx, [rbp+arg_0]; struct StateRepository::Statement *
0x18001309b  mov     rdx, r13; struct Application *
0x18001309e  call    ?RowToObject@Application@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::Application::RowToObject(StateRepository::Statement const &,StateRepository::Entity::Application &,__int64)
0x1800130a3  mov     ebx, eax
0x1800130a5  test    eax, eax
0x1800130a7  js      loc_1800131CA
0x1800130ad  cmp     [rbp+arg_0], 0
0x1800130b2  jz      short loc_1800130DC
0x1800130b4  lea     rdx, [rbp+arg_0]; struct StateRepository::Statement *
0x1800130b8  mov     rcx, r15; this
0x1800130bb  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800130c0  test    eax, eax
0x1800130c2  jns     short loc_1800130DC
0x1800130c4  mov     rcx, [rbp+40h]; this
0x1800130c8  lea     r8, aOnecoreBaseApp_435; "onecore\\base\\appmodel\\staterepositor"...
0x1800130cf  mov     r9d, eax; char *
0x1800130d2  mov     edx, 3CFh; void *
0x1800130d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800130dc  mov     rcx, [rbp+arg_0]; struct sqlite3_stmt *
0x1800130e0  test    rcx, rcx
0x1800130e3  jnz     short loc_18001313F
0x1800130e5  xor     eax, eax
0x1800130e7  jmp     loc_180012F23
0x1800130ec  cmp     eax, 87AF0065h
0x1800130f1  jz      short loc_180013137
0x1800130f3  test    eax, eax
0x1800130f5  js      loc_18001303A
0x1800130fb  jmp     loc_180013059
0x180013100  mov     rcx, [rbp+40h]; this
0x180013104  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18001310b  mov     r9d, ebx; char *
0x18001310e  mov     edx, 0C9h; void *
0x180013113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013118  mov     eax, ebx
0x18001311a  jmp     loc_180013011
0x18001311f  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x180013124  mov     edi, eax
0x180013126  test    eax, eax
0x180013128  js      short loc_180013154
0x18001312a  mov     [rbp+arg_0], 0
0x180013132  jmp     loc_180012F21
0x180013137  xor     sil, sil
0x18001313a  jmp     loc_180013056
0x18001313f  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x180013144  mov     ebx, eax
0x180013146  test    eax, eax
0x180013148  js      short loc_180013189
0x18001314a  mov     [rbp+arg_0], 0
0x180013152  jmp     short loc_1800130E5
0x180013154  mov     rcx, [rbp+40h]; this
0x180013158  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18001315f  mov     r9d, edi; char *
0x180013162  mov     edx, 7Bh ; '{'; void *
0x180013167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001316c  mov     rcx, [rbp+40h]; this
0x180013170  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180013177  mov     r9d, edi; char *
0x18001317a  mov     edx, 16h; void *
0x18001317f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013184  jmp     loc_180012F21
0x180013189  mov     rcx, [rbp+40h]; this
0x18001318d  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180013194  mov     r9d, ebx; char *
0x180013197  mov     edx, 7Bh ; '{'; void *
0x18001319c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131a1  mov     rcx, [rbp+40h]; this
0x1800131a5  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x1800131ac  mov     r9d, ebx; char *
0x1800131af  mov     edx, 16h; void *
0x1800131b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800131b9  jmp     loc_1800130E5
0x1800131be  mov     ebx, eax
0x1800131c0  mov     edx, 0A8h
0x1800131c5  jmp     loc_180012EE9
0x1800131ca  mov     rcx, [rbp+40h]; this
0x1800131ce  lea     r8, aOnecoreBaseApp_435; "onecore\\base\\appmodel\\staterepositor"...
0x1800131d5  mov     r9d, ebx; char *
0x1800131d8  mov     edx, 3CCh; void *
0x1800131dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131e2  lea     rcx, [rbp+arg_0]; this
0x1800131e6  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800131eb  jmp     loc_180012F21
```
