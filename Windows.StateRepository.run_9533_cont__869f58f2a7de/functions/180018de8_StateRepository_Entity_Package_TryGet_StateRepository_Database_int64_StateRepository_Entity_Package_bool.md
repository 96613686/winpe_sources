# StateRepository::Entity::Package::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::Package &,bool &)

- ea: `0x180018de8`
- end: `0x180019158`
- name: `?TryGet@Package@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z`
- size: `880`
- prototype: `__int64 __fastcall(struct StateRepository::Database *, __int64, struct StateRepository::Entity::Package *, bool *)`
- caller_count: `6`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000eef0`
- `0x1800160d0`
- `0x180066e10`
- `0x180067100`
- `0x18006f050`
- `0x1800a3a94`

## callees

- `0x180010d28`
- `0x1800131f8`
- `0x180017a58`
- `0x180018bbc`
- `0x180018de8`
- `0x180019794`
- `0x18001a548`
- `0x18001a9e0`
- `0x18001aa10`
- `0x18020b074`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int64` at `0x180018f38`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180018f71`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180018f38`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180018f71`

## string_xrefs

- `0x180018e2d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018e51`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180018fec`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180018e64`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package.cpp`
- `0x18001901f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package.cpp`
- `0x18001905f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package.cpp`
- `0x180018e09`: `SELECT _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsInbox, PackageType, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVersionTested, TargetDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, SourceBundle, EditionId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE _PackageID=? AND _WorkId=0;`
- `0x180018dfe`: `SELECT _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsInbox, PackageType, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVersionTested, TargetDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, SourceBundle, EditionId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE _PackageID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;`
- `0x180018eff`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x180018e90`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180018ecb`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180018f98`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1800190a7`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1800190fb`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180019113`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180019130`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Package::TryGet(
        struct StateRepository::Database *a1,
        __int64 a2,
        struct StateRepository::Entity::Package *a3,
        bool *a4)
{
  const char *v4; // rbx
  bool v5; // zf
  unsigned int v10; // ebx
  __int64 v11; // rdx
  signed int v12; // eax
  int v13; // eax
  unsigned __int64 v14; // r9
  StateRepository::StatementCache *v15; // r15
  int v16; // eax
  int v17; // r8d
  bool v18; // si
  int v19; // eax
  __int64 v20; // r8
  bool v21; // sf
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // eax
  unsigned int v30; // edi
  const char **v31; // [rsp+20h] [rbp-18h]
  int v32; // [rsp+20h] [rbp-18h]
  int v33; // [rsp+20h] [rbp-18h]
  int v34; // [rsp+20h] [rbp-18h]
  int v35; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]
  struct sqlite3_stmt *v37; // [rsp+80h] [rbp+48h] BYREF

  v4 = "SELECT _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsInbox, PackageTyp"
       "e, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVersionTested, TargetD"
       "eviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, SourceBundle, EditionId, O"
       "SVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE _PackageID=? AND (_WorkId=0 OR _WorkId"
       "=?) ORDER BY _WorkId DESC;";
  v5 = *((_QWORD *)a1 + 1) == 0;
  v37 = 0;
  if ( v5 )
    v4 = "SELECT _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsInbox, PackageT"
         "ype, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVersionTested, Tar"
         "getDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, SourceBundle, Editio"
         "nId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE _PackageID=? AND _WorkId=0;";
  if ( !*(_QWORD *)a1 )
  {
    v10 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      (int)v31);
LABEL_5:
    v11 = 164;
LABEL_6:
    v12 = v10;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
      (const char *)(unsigned int)v12,
      (int)v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package.cpp",
      (const char *)v10,
      v32);
    v13 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v37);
    if ( v13 >= 0 )
      return v10;
    v14 = (unsigned int)v13;
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)v14,
      v33);
    return v10;
  }
  v15 = (struct StateRepository::Database *)((char *)a1 + 40);
  if ( !StateRepository::StatementCache::Get(
          (struct StateRepository::Database *)((char *)a1 + 40),
          v4,
          (struct StateRepository::Statement *)&v37) )
  {
    v16 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v37);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
        (const char *)(unsigned int)v16,
        (int)v31);
    v10 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)a1, v4, v17, &v37, v31);
    if ( (v10 & 0x80000000) != 0 )
      goto LABEL_5;
  }
  if ( !v37 )
  {
    v10 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v31);
LABEL_13:
    v11 = 165;
    goto LABEL_6;
  }
  v18 = 1;
  v19 = sqlite3_bind_int64(v37, 1, a2);
  v10 = v19;
  if ( v19 > 0 )
    v10 = (unsigned __int16)v19 | 0x87AF0000;
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_13;
  v20 = *((_QWORD *)a1 + 1);
  v10 = -2147019873;
  if ( v20 )
  {
    if ( v37 )
    {
      v12 = sqlite3_bind_int64(v37, 2, v20);
      v21 = v12 < 0;
      if ( v12 <= 0 )
        goto LABEL_26;
      v12 = (unsigned __int16)v12 | 0x87AF0000;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        (int)v31);
      v12 = -2147019873;
    }
    v21 = v12 < 0;
LABEL_26:
    if ( v21 )
    {
      v10 = v12;
      v11 = 168;
      goto LABEL_7;
    }
  }
  if ( !v37 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      (int)v31);
LABEL_29:
    v11 = 171;
    goto LABEL_6;
  }
  v22 = StateRepository::Statement::dal_step(v37);
  v10 = v22;
  if ( v22 == -2018574236 )
    goto LABEL_31;
  if ( v22 == -2018574235 )
  {
    v18 = 0;
LABEL_31:
    *a4 = v18;
    goto LABEL_32;
  }
  if ( v22 < 0 )
    goto LABEL_29;
LABEL_32:
  if ( *a4 )
    goto LABEL_59;
  if ( v37 )
  {
    v23 = StateRepository::StatementCache::Add(v15, (struct StateRepository::Statement *)&v37);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)(unsigned int)v23,
        (int)v31);
  }
  if ( *a4 )
  {
LABEL_59:
    v24 = StateRepository::Entity::Package::RowToObject((const struct StateRepository::Statement *)&v37, a3, a2);
    v10 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package.cpp",
        (const char *)(unsigned int)v24,
        (int)v31);
      if ( !v37 )
        return v10;
      v29 = StateRepository::Statement::dal_finalize(v37);
      v30 = v29;
      if ( v29 >= 0 )
      {
        v37 = 0;
        return v10;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v29,
        v34);
      v14 = v30;
      goto LABEL_9;
    }
  }
  if ( v37 )
  {
    v26 = StateRepository::StatementCache::Add(v15, (struct StateRepository::Statement *)&v37);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x752,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package.cpp",
        (const char *)(unsigned int)v26,
        (int)v31);
  }
  if ( v37 )
  {
    v27 = StateRepository::Statement::dal_finalize(v37);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v27,
        (int)v31);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)v28,
        v35);
    }
    else
    {
      v37 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018de8  push    rbp
0x180018dea  push    rbx
0x180018deb  push    rsi
0x180018dec  push    rdi
0x180018ded  push    r12
0x180018def  push    r13
0x180018df1  push    r14
0x180018df3  push    r15
0x180018df5  mov     rbp, rsp
0x180018df8  sub     rsp, 38h
0x180018dfc  xor     esi, esi
0x180018dfe  lea     rbx, aSelectRevision_14; "SELECT _Revision, _WorkId, PackageFamil"...
0x180018e05  cmp     [rcx+8], rsi
0x180018e09  lea     rax, aSelectRevision_107; "SELECT _Revision, _WorkId, PackageFamil"...
0x180018e10  mov     r14, r9
0x180018e13  mov     [rbp+arg_0], rsi
0x180018e17  cmovz   rbx, rax
0x180018e1b  mov     r13, r8
0x180018e1e  mov     r12, rdx
0x180018e21  mov     rdi, rcx
0x180018e24  cmp     [rcx], rsi
0x180018e27  jnz     short loc_180018EA6
0x180018e29  mov     rcx, [rbp+40h]; this
0x180018e2d  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x180018e34  mov     ebx, 8007139Fh
0x180018e39  mov     edx, 66Eh; void *
0x180018e3e  mov     r9d, ebx; char *
0x180018e41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e46  mov     edx, 0A4h; void *
0x180018e4b  mov     eax, ebx
0x180018e4d  mov     rcx, [rbp+40h]; this
0x180018e51  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x180018e58  mov     r9d, eax; char *
0x180018e5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e60  mov     rcx, [rbp+40h]; this
0x180018e64  lea     r8, aOnecoreBaseApp_458; "onecore\\base\\appmodel\\staterepositor"...
0x180018e6b  mov     r9d, ebx; char *
0x180018e6e  mov     edx, 74Bh; void *
0x180018e73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e78  lea     rcx, [rbp+arg_0]; this
0x180018e7c  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180018e81  test    eax, eax
0x180018e83  jns     loc_180019040
0x180018e89  mov     r9d, eax; char *
0x180018e8c  mov     rcx, [rbp+40h]; this
0x180018e90  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180018e97  mov     edx, 16h; void *
0x180018e9c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018ea1  jmp     loc_180019040
0x180018ea6  lea     r15, [rcx+28h]
0x180018eaa  mov     rdx, rbx; char *
0x180018ead  mov     rcx, r15; this
0x180018eb0  lea     r8, [rbp+arg_0]; struct StateRepository::Statement *
0x180018eb4  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x180018eb9  test    rax, rax
0x180018ebc  jz      short loc_180018EEE
0x180018ebe  mov     rcx, [rbp+arg_0]
0x180018ec2  test    rcx, rcx
0x180018ec5  jnz     short loc_180018F2E
0x180018ec7  mov     rcx, [rbp+40h]; this
0x180018ecb  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180018ed2  mov     ebx, 8007139Fh
0x180018ed7  mov     edx, 0C9h; void *
0x180018edc  mov     r9d, ebx; char *
0x180018edf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ee4  mov     edx, 0A5h
0x180018ee9  jmp     loc_180018E4B
0x180018eee  lea     rcx, [rbp+arg_0]; this
0x180018ef2  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180018ef7  test    eax, eax
0x180018ef9  jns     short loc_180018F13
0x180018efb  mov     rcx, [rbp+40h]; this
0x180018eff  lea     r8, aOnecoreBaseApp_149; "onecore\\base\\appmodel\\StateRepositor"...
0x180018f06  mov     r9d, eax; char *
0x180018f09  mov     edx, 127h; void *
0x180018f0e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018f13  mov     rcx, [rdi]; struct sqlite3 *
0x180018f16  lea     r9, [rbp+arg_0]; struct sqlite3_stmt **
0x180018f1a  mov     rdx, rbx; char *
0x180018f1d  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x180018f22  mov     ebx, eax
0x180018f24  test    eax, eax
0x180018f26  js      loc_180018E46
0x180018f2c  jmp     short loc_180018EBE
0x180018f2e  mov     esi, 1
0x180018f33  mov     r8, r12
0x180018f36  mov     edx, esi
0x180018f38  call    cs:__imp_sqlite3_bind_int64
0x180018f3e  mov     ebx, eax
0x180018f40  test    eax, eax
0x180018f42  jle     short loc_180018F4D
0x180018f44  movzx   ebx, ax
0x180018f47  or      ebx, 87AF0000h
0x180018f4d  test    ebx, ebx
0x180018f4f  js      short loc_180018EE4
0x180018f51  mov     r8, [rdi+8]
0x180018f55  mov     ebx, 8007139Fh
0x180018f5a  test    r8, r8
0x180018f5d  jz      short loc_180018F8B
0x180018f5f  mov     rcx, [rbp+arg_0]
0x180018f63  test    rcx, rcx
0x180018f66  jz      loc_1800190A3
0x180018f6c  mov     edx, 2
0x180018f71  call    cs:__imp_sqlite3_bind_int64
0x180018f77  test    eax, eax
0x180018f79  jle     short loc_180018F85
0x180018f7b  movzx   eax, ax
0x180018f7e  or      eax, 87AF0000h
0x180018f83  test    eax, eax
0x180018f85  js      loc_18001914C
0x180018f8b  mov     rcx, [rbp+arg_0]; struct sqlite3_stmt *
0x180018f8f  test    rcx, rcx
0x180018f92  jnz     short loc_180018FB6
0x180018f94  mov     rcx, [rbp+40h]; this
0x180018f98  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180018f9f  mov     r9d, ebx; char *
0x180018fa2  mov     edx, 3Fh ; '?'; void *
0x180018fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fac  mov     edx, 0ABh
0x180018fb1  jmp     loc_180018E4B
0x180018fb6  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x180018fbb  mov     ebx, eax
0x180018fbd  cmp     eax, 87AF0064h
0x180018fc2  jnz     loc_18001908F
0x180018fc8  mov     [r14], sil
0x180018fcb  cmp     byte ptr [r14], 0
0x180018fcf  jnz     short loc_180019006
0x180018fd1  cmp     [rbp+arg_0], 0
0x180018fd6  jz      short loc_180019000
0x180018fd8  lea     rdx, [rbp+arg_0]; struct StateRepository::Statement *
0x180018fdc  mov     rcx, r15; this
0x180018fdf  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x180018fe4  test    eax, eax
0x180018fe6  jns     short loc_180019000
0x180018fe8  mov     rcx, [rbp+40h]; this
0x180018fec  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x180018ff3  mov     r9d, eax; char *
0x180018ff6  mov     edx, 0AFh; void *
0x180018ffb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019000  cmp     byte ptr [r14], 0
0x180019004  jz      short loc_180019044
0x180019006  mov     r8, r12; __int64
0x180019009  lea     rcx, [rbp+arg_0]; struct StateRepository::Statement *
0x18001900d  mov     rdx, r13; struct StateRepository::Entity::Package *
0x180019010  call    ?RowToObject@Package@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::Package::RowToObject(StateRepository::Statement const &,StateRepository::Entity::Package &,__int64)
0x180019015  mov     ebx, eax
0x180019017  test    eax, eax
0x180019019  jns     short loc_180019044
0x18001901b  mov     rcx, [rbp+40h]; this
0x18001901f  lea     r8, aOnecoreBaseApp_458; "onecore\\base\\appmodel\\staterepositor"...
0x180019026  mov     r9d, eax; char *
0x180019029  mov     edx, 74Fh; void *
0x18001902e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019033  mov     rcx, [rbp+arg_0]; struct sqlite3_stmt *
0x180019037  test    rcx, rcx
0x18001903a  jnz     loc_1800190DF
0x180019040  mov     eax, ebx
0x180019042  jmp     short loc_18001907E
0x180019044  cmp     [rbp+arg_0], 0
0x180019049  jz      short loc_180019073
0x18001904b  lea     rdx, [rbp+arg_0]; struct StateRepository::Statement *
0x18001904f  mov     rcx, r15; this
0x180019052  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x180019057  test    eax, eax
0x180019059  jns     short loc_180019073
0x18001905b  mov     rcx, [rbp+40h]; this
0x18001905f  lea     r8, aOnecoreBaseApp_458; "onecore\\base\\appmodel\\staterepositor"...
0x180019066  mov     r9d, eax; char *
0x180019069  mov     edx, 752h; void *
0x18001906e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019073  mov     rcx, [rbp+arg_0]; struct sqlite3_stmt *
0x180019077  test    rcx, rcx
0x18001907a  jnz     short loc_1800190CA
0x18001907c  xor     eax, eax
0x18001907e  add     rsp, 38h
0x180019082  pop     r15
0x180019084  pop     r14
0x180019086  pop     r13
0x180019088  pop     r12
0x18001908a  pop     rdi
0x18001908b  pop     rsi
0x18001908c  pop     rbx
0x18001908d  pop     rbp
0x18001908e  retn
0x18001908f  cmp     eax, 87AF0065h
0x180019094  jz      short loc_1800190C2
0x180019096  test    eax, eax
0x180019098  js      loc_180018FAC
0x18001909e  jmp     loc_180018FCB
0x1800190a3  mov     rcx, [rbp+40h]; this
0x1800190a7  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x1800190ae  mov     r9d, ebx; char *
0x1800190b1  mov     edx, 0C9h; void *
0x1800190b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800190bb  mov     eax, ebx
0x1800190bd  jmp     loc_180018F83
0x1800190c2  xor     sil, sil
0x1800190c5  jmp     loc_180018FC8
0x1800190ca  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x1800190cf  mov     ebx, eax
0x1800190d1  test    eax, eax
0x1800190d3  js      short loc_1800190F7
0x1800190d5  mov     [rbp+arg_0], 0
0x1800190dd  jmp     short loc_18001907C
0x1800190df  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x1800190e4  mov     edi, eax
0x1800190e6  test    eax, eax
0x1800190e8  js      short loc_18001912C
0x1800190ea  mov     [rbp+arg_0], 0
0x1800190f2  jmp     loc_180019040
0x1800190f7  mov     rcx, [rbp+40h]; this
0x1800190fb  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180019102  mov     r9d, ebx; char *
0x180019105  mov     edx, 7Bh ; '{'; void *
0x18001910a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001910f  mov     rcx, [rbp+40h]; this
0x180019113  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18001911a  mov     r9d, ebx; char *
0x18001911d  mov     edx, 16h; void *
0x180019122  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019127  jmp     loc_18001907C
0x18001912c  mov     rcx, [rbp+40h]; this
0x180019130  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180019137  mov     r9d, edi; char *
0x18001913a  mov     edx, 7Bh ; '{'; void *
0x18001913f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019144  mov     r9d, edi
0x180019147  jmp     loc_180018E8C
0x18001914c  mov     ebx, eax
0x18001914e  mov     edx, 0A8h
0x180019153  jmp     loc_180018E4D
```
