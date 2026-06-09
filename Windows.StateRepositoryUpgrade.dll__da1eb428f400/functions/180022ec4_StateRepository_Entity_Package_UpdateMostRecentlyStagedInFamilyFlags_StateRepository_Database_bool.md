# StateRepository::Entity::Package::UpdateMostRecentlyStagedInFamilyFlags(StateRepository::Database &,bool)

- ea: `0x180022ec4`
- end: `0x180023000`
- name: `?UpdateMostRecentlyStagedInFamilyFlags@Package@Entity@StateRepository@@SAJAEAVDatabase@3@_N@Z`
- size: `316`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ed80`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018f78`
- `0x18001b5a8`
- `0x18001b8d4`
- `0x180022ec4`
- `0x180029d1c`
- `0x18002f010`

## string_xrefs

- `0x180022eeb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022f64`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022fbb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022f36`: ` UPDATE Package SET Flags=Flags|0x400 WHERE _PackageID IN (SELECT toSetFlags._PackageID FROM PACKAGE AS toSetFlags INNER JOIN (SELECT p._PackageID, p.SourceBundle, MAX_UINT(Version) AS MaxVersion FROM Package AS p WHERE p.PackageType&0x21!=0 AND p._WorkId=0 AND NOT EXISTS (SELECT 1 FROM PackageUser AS pu WHERE p._PackageID=pu.Package AND (pu.DeploymentState=6 OR pu.DeploymentState=5) AND pu._WorkId=0 AND p._WorkId=0 LIMIT 1) AND (p.PackageFamily NOT IN (SELECT PackageFamily FROM Package WHERE Fl`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Package::UpdateMostRecentlyStagedInFamilyFlags(
        struct StateRepository::Database *this)
{
  int NoRow; // edi
  __int64 v4; // rdx
  int v5; // eax
  _QWORD v6[4]; // [rsp+20h] [rbp-59h] BYREF
  __int64 (__fastcall ***v7)(); // [rsp+40h] [rbp-39h] BYREF
  __int64 (__fastcall **v8)(); // [rsp+48h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v10; // [rsp+F0h] [rbp+77h] BYREF

  if ( StateRepository::Database::IsInAutoCommitMode(this) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF0C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
      (const char *)0x8067000BLL,
      v6[0]);
    return 2154233867LL;
  }
  v10 = 0;
  v8 = off_180030D70;
  v6[1] = 0;
  v7 = &v8;
  v6[2] = 0;
  NoRow = StateRepository::StatementExecution::PrepareAndBind(
            this,
            (struct StateRepository::Database *)v6,
            (const struct StateRepository::StatementExecution::StatementDefinition *)&v7,
            (struct StateRepository::StatementExecution::StatementBinderFunc *)&v10,
            (struct StateRepository::Statement *)" UPDATE Package SET Flags=Flags|0x400 WHERE _PackageID IN (SELECT toSet"
                                                 "Flags._PackageID FROM PACKAGE AS toSetFlags INNER JOIN (SELECT p._Packa"
                                                 "geID, p.SourceBundle, MAX_UINT(Version) AS MaxVersion FROM Package AS p"
                                                 " WHERE p.PackageType&0x21!=0 AND p._WorkId=0 AND NOT EXISTS (SELECT 1 F"
                                                 "ROM PackageUser AS pu WHERE p._PackageID=pu.Package AND (pu.DeploymentS"
                                                 "tate=6 OR pu.DeploymentState=5) AND pu._WorkId=0 AND p._WorkId=0 LIMIT "
                                                 "1) AND (p.PackageFamily NOT IN (SELECT PackageFamily FROM Package WHERE"
                                                 " Flags&0x400!=0 GROUP BY PackageFamily)) GROUP BY PackageFamily) highes"
                                                 "tVersion ON CASE WHEN toSetFlags.SourceBundle=0 THEN highestVersion._Pa"
                                                 "ckageID=toSetFlags._PackageID ELSE toSetFlags.SourceBundle=highestVersi"
                                                 "on.SourceBundle AND toSetFlags.PackageType=8 END)");
  if ( NoRow < 0 )
  {
    v4 = 3893;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
      (const char *)(unsigned int)NoRow,
      v6[0]);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v10);
    ((void (__fastcall *)(__int64 (__fastcall ***)(), _QWORD))**v7)(v7, 0);
    return (unsigned int)NoRow;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v10);
  if ( NoRow < 0 )
  {
    v4 = 3894;
    goto LABEL_5;
  }
  v5 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)&v10);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF37,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
      (const char *)(unsigned int)v5,
      v6[0]);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v10);
  ((void (__fastcall *)(__int64 (__fastcall ***)(), _QWORD))**v7)(v7, 0);
  return 0;
}

```

## disassembly

```asm
0x180022ec4  mov     [rsp-8+arg_0], rbx
0x180022ec9  mov     [rsp-8+arg_8], rdi
0x180022ece  push    rbp
0x180022ecf  lea     rbp, [rsp-57h]
0x180022ed4  sub     rsp, 0D0h
0x180022edb  mov     rbx, rcx
0x180022ede  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180022ee3  test    al, al
0x180022ee5  jz      short loc_180022F0B
0x180022ee7  mov     rcx, [rbp+5Fh]; this
0x180022eeb  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022ef2  mov     ebx, 8067000Bh
0x180022ef7  mov     edx, 0F0Ch; void *
0x180022efc  mov     r9d, ebx; char *
0x180022eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f04  mov     eax, ebx
0x180022f06  jmp     loc_180022FEB
0x180022f0b  lea     rax, off_180030D70
0x180022f12  mov     [rbp+57h+arg_10], 0
0x180022f1a  mov     [rbp+57h+var_88], rax
0x180022f1e  lea     r9, [rbp+57h+arg_10]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x180022f22  lea     rax, [rbp+57h+var_88]
0x180022f26  mov     [rbp+57h+var_A8], 0
0x180022f2e  mov     [rbp+57h+var_90], rax
0x180022f32  lea     r8, [rbp+57h+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x180022f36  lea     rax, aUpdatePackageS_1; " UPDATE Package SET Flags=Flags|0x400 W"...
0x180022f3d  mov     [rbp+57h+var_A0], 0
0x180022f45  lea     rdx, [rbp+57h+var_B0]; struct StateRepository::Database *
0x180022f49  mov     [rbp+57h+var_B0], rax
0x180022f4d  mov     rcx, rbx; this
0x180022f50  call    ?PrepareAndBind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBind(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x180022f55  mov     edi, eax
0x180022f57  test    eax, eax
0x180022f59  jns     short loc_180022F91
0x180022f5b  mov     edx, 0F35h; void *
0x180022f60  mov     rcx, [rbp+5Fh]; this
0x180022f64  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022f6b  mov     r9d, edi; char *
0x180022f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f73  lea     rcx, [rbp+57h+arg_10]; this
0x180022f77  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180022f7c  mov     rcx, [rbp+57h+var_90]
0x180022f80  mov     rdx, [rcx]
0x180022f83  mov     rax, [rdx]
0x180022f86  xor     edx, edx
0x180022f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f8d  mov     eax, edi
0x180022f8f  jmp     short loc_180022FEB
0x180022f91  lea     rcx, [rbp+57h+arg_10]; this
0x180022f95  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180022f9a  mov     edi, eax
0x180022f9c  test    eax, eax
0x180022f9e  jns     short loc_180022FA7
0x180022fa0  mov     edx, 0F36h
0x180022fa5  jmp     short loc_180022F60
0x180022fa7  lea     rdx, [rbp+57h+arg_10]; struct StateRepository::Statement *
0x180022fab  mov     rcx, rbx; this
0x180022fae  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180022fb3  test    eax, eax
0x180022fb5  jns     short loc_180022FCF
0x180022fb7  mov     rcx, [rbp+5Fh]; this
0x180022fbb  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022fc2  mov     r9d, eax; char *
0x180022fc5  mov     edx, 0F37h; void *
0x180022fca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022fcf  lea     rcx, [rbp+57h+arg_10]; this
0x180022fd3  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180022fd8  mov     rcx, [rbp+57h+var_90]
0x180022fdc  xor     edx, edx
0x180022fde  mov     rax, [rcx]
0x180022fe1  mov     rax, [rax]
0x180022fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fe9  xor     eax, eax
0x180022feb  lea     r11, [rsp+0D0h+var_s0]
0x180022ff3  mov     rbx, [r11+10h]
0x180022ff7  mov     rdi, [r11+18h]
0x180022ffb  mov     rsp, r11
0x180022ffe  pop     rbp
0x180022fff  retn
```
