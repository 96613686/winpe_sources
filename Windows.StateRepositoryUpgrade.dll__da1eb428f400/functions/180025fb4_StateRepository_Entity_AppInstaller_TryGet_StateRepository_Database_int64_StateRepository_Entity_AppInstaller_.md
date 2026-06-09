# StateRepository::Entity::AppInstaller::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::AppInstaller &,bool &)

- ea: `0x180025fb4`
- end: `0x180026079`
- name: `?TryGet@AppInstaller@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, __int64, struct StateRepository::Entity::AppInstaller *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013c40`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x18001b5a8`
- `0x180025dd8`
- `0x180025fb4`
- `0x18002a160`

## string_xrefs

- `0x180026025`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x18002604c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x180025fe1`: `SELECT _Revision, PackageFamily, Uri, Version, LastChecked, CheckUpdateInterval, Flags, PauseUntil, _Dictionary FROM AppInstaller WHERE _AppInstallerID=?;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppInstaller::TryGet(
        struct StateRepository::Database *this,
        const char *a2,
        struct StateRepository::Entity::AppInstaller *a3,
        struct StateRepository::Statement *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-48h]
  _BYTE v14[56]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = StateRepository::StatementExecution::PrepareAndBindAndTryGet(
         this,
         (struct StateRepository::Database *)"SELECT _Revision, PackageFamily, Uri, Version, LastChecked, CheckUpdateInte"
                                             "rval, Flags, PauseUntil, _Dictionary FROM AppInstaller WHERE _AppInstallerID=?;",
         0,
         a2,
         (__int64)v14,
         a4,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 367;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
      (const char *)(unsigned int)v8,
      v13);
    goto LABEL_10;
  }
  if ( *(_BYTE *)a4 )
  {
    v8 = StateRepository::Entity::AppInstaller::RowToObject(
           (const struct StateRepository::Statement *)v14,
           a3,
           (__int64)a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 371;
      goto LABEL_6;
    }
  }
  v11 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)v14);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
      (const char *)(unsigned int)v11,
      v13);
  v9 = 0;
LABEL_10:
  StateRepository::Statement::~Statement((StateRepository::Statement *)v14);
  return v9;
}

```

## disassembly

```asm
0x180025fb4  mov     r11, rsp
0x180025fb7  push    rbx
0x180025fb8  push    rbp
0x180025fb9  push    rsi
0x180025fba  push    rdi
0x180025fbb  push    r14
0x180025fbd  sub     rsp, 40h
0x180025fc1  mov     [r11-40h], r9
0x180025fc5  lea     rax, [r11-38h]
0x180025fc9  mov     rdi, r9
0x180025fcc  mov     qword ptr [r11-38h], 0
0x180025fd4  mov     r9, rdx; char *
0x180025fd7  mov     [r11-48h], rax
0x180025fdb  mov     r14, r8
0x180025fde  mov     rbp, rdx
0x180025fe1  lea     rdx, aSelectRevision_3; "SELECT _Revision, PackageFamily, Uri, V"...
0x180025fe8  xor     r8d, r8d; char *
0x180025feb  mov     rsi, rcx
0x180025fee  call    ?PrepareAndBindAndTryGet@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEAVStatement@2@AEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndTryGet(StateRepository::Database &,char const *,char const *,__int64,StateRepository::Statement &,bool &)
0x180025ff3  mov     ebx, eax
0x180025ff5  test    eax, eax
0x180025ff7  jns     short loc_180026000
0x180025ff9  mov     edx, 16Fh
0x180025ffe  jmp     short loc_180026020
0x180026000  cmp     byte ptr [rdi], 0
0x180026003  jz      short loc_180026036
0x180026005  mov     r8, rbp; __int64
0x180026008  lea     rcx, [rsp+68h+var_38]; this
0x18002600d  mov     rdx, r14; struct StateRepository::Entity::AppInstaller *
0x180026010  call    ?RowToObject@AppInstaller@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::AppInstaller::RowToObject(StateRepository::Statement const &,StateRepository::Entity::AppInstaller &,__int64)
0x180026015  mov     ebx, eax
0x180026017  test    eax, eax
0x180026019  jns     short loc_180026036
0x18002601b  mov     edx, 173h; void *
0x180026020  mov     rcx, [rsp+68h]; this
0x180026025  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x18002602c  mov     r9d, eax; char *
0x18002602f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026034  jmp     short loc_180026062
0x180026036  lea     rdx, [rsp+68h+var_38]; struct StateRepository::Statement *
0x18002603b  mov     rcx, rsi; this
0x18002603e  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180026043  test    eax, eax
0x180026045  jns     short loc_180026060
0x180026047  mov     rcx, [rsp+68h]; this
0x18002604c  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180026053  mov     r9d, eax; char *
0x180026056  mov     edx, 176h; void *
0x18002605b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026060  xor     ebx, ebx
0x180026062  lea     rcx, [rsp+68h+var_38]; this
0x180026067  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18002606c  mov     eax, ebx
0x18002606e  add     rsp, 40h
0x180026072  pop     r14
0x180026074  pop     rdi
0x180026075  pop     rsi
0x180026076  pop     rbp
0x180026077  pop     rbx
0x180026078  retn
```
