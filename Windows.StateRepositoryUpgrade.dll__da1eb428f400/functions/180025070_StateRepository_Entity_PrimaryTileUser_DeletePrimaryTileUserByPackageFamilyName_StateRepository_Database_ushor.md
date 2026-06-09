# StateRepository::Entity::PrimaryTileUser::DeletePrimaryTileUserByPackageFamilyName(StateRepository::Database &,ushort const *)

- ea: `0x180025070`
- end: `0x180025198`
- name: `?DeletePrimaryTileUserByPackageFamilyName@PrimaryTileUser@Entity@StateRepository@@SAJAEAVDatabase@3@PEBG@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct StateRepository::Database *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012e90`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018f78`
- `0x18001b5a8`
- `0x180025070`
- `0x180029eec`
- `0x18002f010`

## string_xrefs

- `0x18002509b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-primarytileuser-custom.cpp`
- `0x180025116`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-primarytileuser-custom.cpp`
- `0x180025151`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-primarytileuser-custom.cpp`
- `0x1800250f1`: `DELETE FROM PrimaryTileUser WHERE ApplicationIdentity IN ( SELECT _ApplicationIdentityID FROM ApplicationIdentity WHERE (ApplicationUserModelId LIKE ?1 || '!%')) AND _WorkId=0;`
- `0x1800250fc`: `DELETE FROM PrimaryTileUser WHERE ApplicationIdentity IN ( SELECT _ApplicationIdentityID FROM ApplicationIdentity WHERE (ApplicationUserModelId LIKE ?1 || '!%')) AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PrimaryTileUser::DeletePrimaryTileUserByPackageFamilyName(
        struct StateRepository::Database *this,
        const unsigned __int16 *a2)
{
  struct StateRepository::StatementExecution::StatementBinderFunc *v3; // r9
  int v5; // eax
  unsigned int v6; // edi
  int v7; // eax
  _QWORD v8[4]; // [rsp+28h] [rbp-59h] BYREF
  _QWORD *v9; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v10[17]; // [rsp+50h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  const unsigned __int16 *v12; // [rsp+F0h] [rbp+6Fh] BYREF
  __int64 v13; // [rsp+F8h] [rbp+77h] BYREF

  v12 = a2;
  if ( StateRepository::Database::IsInAutoCommitMode(this) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-primarytileuser-custom.cpp",
      (const char *)0x8067000BLL,
      v8[0]);
    return 2154233867LL;
  }
  else
  {
    v13 = 0;
    v10[0] = &off_180030D80;
    v8[2] = 2;
    v10[1] = &v12;
    v9 = v10;
    v8[0] = "DELETE FROM PrimaryTileUser WHERE ApplicationIdentity IN ( SELECT _ApplicationIdentityID FROM ApplicationIde"
            "ntity WHERE (ApplicationUserModelId LIKE ?1 || '!%')) AND _WorkId=0;";
    v8[1] = "DELETE FROM PrimaryTileUser WHERE ApplicationIdentity IN ( SELECT _ApplicationIdentityID FROM ApplicationIde"
            "ntity WHERE (ApplicationUserModelId LIKE ?1 || '!%')) AND (_WorkId=0 OR _WorkId=?);";
    v5 = StateRepository::StatementExecution::PrepareAndBindAndDeleteBy(
           this,
           (struct StateRepository::Database *)v8,
           (const struct StateRepository::StatementExecution::StatementDefinition *)&v9,
           v3);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)&v13);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-primarytileuser-custom.cpp",
          (const char *)(unsigned int)v7,
          v8[0]);
      (*(void (__fastcall **)(_QWORD *, _QWORD))*v9)(v9, 0);
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-primarytileuser-custom.cpp",
        (const char *)(unsigned int)v5,
        v8[0]);
      (*(void (__fastcall **)(_QWORD *, _QWORD))*v9)(v9, 0);
    }
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v13);
    return v6;
  }
}

```

## disassembly

```asm
0x180025070  mov     rax, rsp
0x180025073  mov     [rax+8], rbx
0x180025077  mov     [rax+20h], rdi
0x18002507b  mov     [rax+10h], rdx
0x18002507f  push    rbp
0x180025080  lea     rbp, [rax-5Fh]
0x180025084  sub     rsp, 0D0h
0x18002508b  mov     rbx, rcx
0x18002508e  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180025093  test    al, al
0x180025095  jz      short loc_1800250BB
0x180025097  mov     rcx, [rbp+5Fh]; this
0x18002509b  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x1800250a2  mov     ebx, 8067000Bh
0x1800250a7  mov     edx, 0A1h; void *
0x1800250ac  mov     r9d, ebx; char *
0x1800250af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800250b4  mov     eax, ebx
0x1800250b6  jmp     loc_180025183
0x1800250bb  lea     rax, off_180030D80
0x1800250c2  mov     [rbp+57h+arg_10], 0
0x1800250ca  mov     [rbp+57h+var_88], rax
0x1800250ce  lea     r8, [rbp+57h+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x1800250d2  lea     rax, [rbp+57h+arg_8]
0x1800250d6  mov     [rbp+57h+var_A0], 2
0x1800250de  mov     [rbp+57h+var_80], rax
0x1800250e2  lea     rdx, [rbp+57h+var_B0]; struct StateRepository::Database *
0x1800250e6  lea     rax, [rbp+57h+var_88]
0x1800250ea  mov     rcx, rbx; this
0x1800250ed  mov     [rbp+57h+var_90], rax
0x1800250f1  lea     rax, aDeleteFromPrim_0; "DELETE FROM PrimaryTileUser WHERE Appli"...
0x1800250f8  mov     [rbp+57h+var_B0], rax
0x1800250fc  lea     rax, aDeleteFromPrim; "DELETE FROM PrimaryTileUser WHERE Appli"...
0x180025103  mov     [rbp+57h+var_A8], rax
0x180025107  call    ?PrepareAndBindAndDeleteBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@@Z; StateRepository::StatementExecution::PrepareAndBindAndDeleteBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &)
0x18002510c  mov     edi, eax
0x18002510e  test    eax, eax
0x180025110  jns     short loc_18002513D
0x180025112  mov     rcx, [rbp+5Fh]; this
0x180025116  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x18002511d  mov     r9d, eax; char *
0x180025120  mov     edx, 0B8h; void *
0x180025125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002512a  mov     rcx, [rbp+57h+var_90]
0x18002512e  mov     rdx, [rcx]
0x180025131  mov     rax, [rdx]
0x180025134  xor     edx, edx
0x180025136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002513b  jmp     short loc_180025178
0x18002513d  lea     rdx, [rbp+57h+arg_10]; struct StateRepository::Statement *
0x180025141  mov     rcx, rbx; this
0x180025144  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180025149  test    eax, eax
0x18002514b  jns     short loc_180025165
0x18002514d  mov     rcx, [rbp+5Fh]; this
0x180025151  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180025158  mov     r9d, eax; char *
0x18002515b  mov     edx, 0BAh; void *
0x180025160  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025165  mov     rcx, [rbp+57h+var_90]
0x180025169  xor     edx, edx
0x18002516b  mov     rax, [rcx]
0x18002516e  mov     rax, [rax]
0x180025171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025176  xor     edi, edi
0x180025178  lea     rcx, [rbp+57h+arg_10]; this
0x18002517c  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180025181  mov     eax, edi
0x180025183  lea     r11, [rsp+0D0h+var_s0]
0x18002518b  mov     rbx, [r11+10h]
0x18002518f  mov     rdi, [r11+28h]
0x180025193  mov     rsp, r11
0x180025196  pop     rbp
0x180025197  retn
```
