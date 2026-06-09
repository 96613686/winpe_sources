# StateRepository::Entity::PackageUserStatus::PopulateOnDemandRegister(StateRepository::Database &)

- ea: `0x180026118`
- end: `0x180026281`
- name: `?PopulateOnDemandRegister@PackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800145e0`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018f78`
- `0x18001b5a8`
- `0x18001b8d4`
- `0x180023008`
- `0x180026118`
- `0x180029d1c`
- `0x18002f010`

## string_xrefs

- `0x18002613f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800261e5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x18002623c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800261c6`: ` UPDATE PackageUserStatus SET Status=Status|0x10000000 WHERE _PackageUserStatusID IN ( SELECT pus._PackageUserStatusID FROM PACKAGEUSERSTATUS AS pus INNER JOIN PackageIdentity AS pi ON pi._PackageIdentityID=pus.PackageIdentity INNER JOIN Package AS p ON p.PackageFullName=pi.PackageFullName INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE (pu.DeploymentState=0x2) AND (pu.Flags & 0x01=0) AND (p.PackageType&0x21!=0) AND (p.Flags2&0x1000=0) AND (pus.Status&0x800!=0) AND (p._WorkId=0) AN`
- `0x1800261a9`: ` UPDATE PackageUserStatus SET Status=Status|0x10000000 WHERE _PackageUserStatusID IN ( SELECT pus._PackageUserStatusID FROM PACKAGEUSERSTATUS AS pus INNER JOIN PackageIdentity AS pi ON pi._PackageIdentityID=pus.PackageIdentity INNER JOIN Package AS p ON p.PackageFullName=pi.PackageFullName INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE (pu.DeploymentState=0x2) AND (pu.IsExplicitlyInstalled=0) AND (p.PackageType&0x21!=0) AND (p.Flags2&0x1000=0) AND (pus.Status&0x800!=0) AND (p._Wor`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageUserStatus::PopulateOnDemandRegister(
        struct StateRepository::Database *this)
{
  int NoRow; // edi
  __int64 v4; // rdx
  int v5; // eax
  _QWORD v6[4]; // [rsp+20h] [rbp-59h] BYREF
  __int64 (__fastcall ***v7)(); // [rsp+40h] [rbp-39h] BYREF
  __int64 (__fastcall **v8)(); // [rsp+48h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v10; // [rsp+E8h] [rbp+6Fh] BYREF

  if ( StateRepository::Database::IsInAutoCommitMode(this) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x161,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
      (const char *)0x8067000BLL,
      v6[0]);
    return 2154233867LL;
  }
  v10 = 0;
  v8 = off_180030D70;
  v7 = &v8;
  v6[1] = 0;
  v6[2] = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_v7500>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StateRepository_v7500>::GetImpl'::`2'::impl) )
  {
    NoRow = StateRepository::StatementExecution::PrepareAndBind(
              this,
              (struct StateRepository::Database *)v6,
              (const struct StateRepository::StatementExecution::StatementDefinition *)&v7,
              (struct StateRepository::StatementExecution::StatementBinderFunc *)&v10,
              (struct StateRepository::Statement *)" UPDATE PackageUserStatus SET Status=Status|0x10000000 WHERE _Package"
                                                   "UserStatusID IN ( SELECT pus._PackageUserStatusID FROM PACKAGEUSERSTA"
                                                   "TUS AS pus INNER JOIN PackageIdentity AS pi ON pi._PackageIdentityID="
                                                   "pus.PackageIdentity INNER JOIN Package AS p ON p.PackageFullName=pi.P"
                                                   "ackageFullName INNER JOIN PackageUser AS pu ON pu.Package=p._PackageI"
                                                   "D WHERE (pu.DeploymentState=0x2) AND (pu.Flags & 0x01=0) AND (p.Packa"
                                                   "geType&0x21!=0) AND (p.Flags2&0x1000=0) AND (pus.Status&0x800!=0) AND"
                                                   " (p._WorkId=0) AND (pu._WorkId=0));");
    if ( NoRow < 0 )
    {
      v4 = 384;
      goto LABEL_8;
    }
  }
  else
  {
    NoRow = StateRepository::StatementExecution::PrepareAndBind(
              this,
              (struct StateRepository::Database *)v6,
              (const struct StateRepository::StatementExecution::StatementDefinition *)&v7,
              (struct StateRepository::StatementExecution::StatementBinderFunc *)&v10,
              (struct StateRepository::Statement *)" UPDATE PackageUserStatus SET Status=Status|0x10000000 WHERE _Package"
                                                   "UserStatusID IN ( SELECT pus._PackageUserStatusID FROM PACKAGEUSERSTA"
                                                   "TUS AS pus INNER JOIN PackageIdentity AS pi ON pi._PackageIdentityID="
                                                   "pus.PackageIdentity INNER JOIN Package AS p ON p.PackageFullName=pi.P"
                                                   "ackageFullName INNER JOIN PackageUser AS pu ON pu.Package=p._PackageI"
                                                   "D WHERE (pu.DeploymentState=0x2) AND (pu.IsExplicitlyInstalled=0) AND"
                                                   " (p.PackageType&0x21!=0) AND (p.Flags2&0x1000=0) AND (pus.Status&0x80"
                                                   "0!=0) AND (p._WorkId=0) AND (pu._WorkId=0));");
    if ( NoRow < 0 )
    {
      v4 = 408;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
        (const char *)(unsigned int)NoRow,
        v6[0]);
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v10);
      ((void (__fastcall *)(__int64 (__fastcall ***)(), _QWORD))**v7)(v7, 0);
      return (unsigned int)NoRow;
    }
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v10);
  if ( NoRow < 0 )
  {
    v4 = 410;
    goto LABEL_8;
  }
  v5 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)&v10);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
      (const char *)(unsigned int)v5,
      v6[0]);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v10);
  ((void (__fastcall *)(__int64 (__fastcall ***)(), _QWORD))**v7)(v7, 0);
  return 0;
}

```

## disassembly

```asm
0x180026118  mov     [rsp-8+arg_0], rbx
0x18002611d  mov     [rsp-8+arg_10], rdi
0x180026122  push    rbp
0x180026123  lea     rbp, [rsp-57h]
0x180026128  sub     rsp, 0D0h
0x18002612f  mov     rbx, rcx
0x180026132  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180026137  test    al, al
0x180026139  jz      short loc_18002615F
0x18002613b  mov     rcx, [rbp+5Fh]; this
0x18002613f  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\staterepositor"...
0x180026146  mov     ebx, 8067000Bh
0x18002614b  mov     edx, 161h; void *
0x180026150  mov     r9d, ebx; char *
0x180026153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026158  mov     eax, ebx
0x18002615a  jmp     loc_18002626C
0x18002615f  lea     rax, off_180030D70
0x180026166  mov     [rbp+57h+arg_8], 0
0x18002616e  mov     [rbp+57h+var_88], rax
0x180026172  lea     rax, [rbp+57h+var_88]
0x180026176  mov     [rbp+57h+var_90], rax
0x18002617a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StateRepository_v7500@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_v7500@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_v7500> `wil::Feature<__WilFeatureTraits_Feature_StateRepository_v7500>::GetImpl(void)'::`2'::impl
0x180026181  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_v7500@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_v7500>::__private_IsEnabled(void)
0x180026186  mov     [rbp+57h+var_A8], 0
0x18002618e  lea     r9, [rbp+57h+arg_8]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x180026192  mov     [rbp+57h+var_A0], 0
0x18002619a  lea     r8, [rbp+57h+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x18002619e  lea     rdx, [rbp+57h+var_B0]; struct StateRepository::Database *
0x1800261a2  mov     rcx, rbx; this
0x1800261a5  test    al, al
0x1800261a7  jnz     short loc_1800261C6
0x1800261a9  lea     rax, aUpdatePackageu_0; " UPDATE PackageUserStatus SET Status=St"...
0x1800261b0  mov     [rbp+57h+var_B0], rax
0x1800261b4  call    ?PrepareAndBind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBind(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x1800261b9  mov     edi, eax
0x1800261bb  test    eax, eax
0x1800261bd  jns     short loc_180026212
0x1800261bf  mov     edx, 198h
0x1800261c4  jmp     short loc_1800261E1
0x1800261c6  lea     rax, aUpdatePackageu; " UPDATE PackageUserStatus SET Status=St"...
0x1800261cd  mov     [rbp+57h+var_B0], rax
0x1800261d1  call    ?PrepareAndBind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBind(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x1800261d6  mov     edi, eax
0x1800261d8  test    eax, eax
0x1800261da  jns     short loc_180026212
0x1800261dc  mov     edx, 180h; void *
0x1800261e1  mov     rcx, [rbp+5Fh]; this
0x1800261e5  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\staterepositor"...
0x1800261ec  mov     r9d, edi; char *
0x1800261ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800261f4  lea     rcx, [rbp+57h+arg_8]; this
0x1800261f8  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800261fd  mov     rcx, [rbp+57h+var_90]
0x180026201  mov     rdx, [rcx]
0x180026204  mov     rax, [rdx]
0x180026207  xor     edx, edx
0x180026209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002620e  mov     eax, edi
0x180026210  jmp     short loc_18002626C
0x180026212  lea     rcx, [rbp+57h+arg_8]; this
0x180026216  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18002621b  mov     edi, eax
0x18002621d  test    eax, eax
0x18002621f  jns     short loc_180026228
0x180026221  mov     edx, 19Ah
0x180026226  jmp     short loc_1800261E1
0x180026228  lea     rdx, [rbp+57h+arg_8]; struct StateRepository::Statement *
0x18002622c  mov     rcx, rbx; this
0x18002622f  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180026234  test    eax, eax
0x180026236  jns     short loc_180026250
0x180026238  mov     rcx, [rbp+5Fh]; this
0x18002623c  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\staterepositor"...
0x180026243  mov     r9d, eax; char *
0x180026246  mov     edx, 19Bh; void *
0x18002624b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026250  lea     rcx, [rbp+57h+arg_8]; this
0x180026254  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180026259  mov     rcx, [rbp+57h+var_90]
0x18002625d  xor     edx, edx
0x18002625f  mov     rax, [rcx]
0x180026262  mov     rax, [rax]
0x180026265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002626a  xor     eax, eax
0x18002626c  lea     r11, [rsp+0D0h+var_s0]
0x180026274  mov     rbx, [r11+10h]
0x180026278  mov     rdi, [r11+20h]
0x18002627c  mov     rsp, r11
0x18002627f  pop     rbp
0x180026280  retn
```
