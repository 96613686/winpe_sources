# StateRepository::Migration::StateRepository_PrimaryTileUser_DeleteEndOFLifeTiles(StateRepository::Migration::Context const &)

- ea: `0x180012e90`
- end: `0x180012fe9`
- name: `?StateRepository_PrimaryTileUser_DeleteEndOFLifeTiles@Migration@StateRepository@@YAJAEBVContext@12@@Z`
- size: `345`
- prototype: `__int64 __fastcall(StateRepository::Migration *__hidden this, const struct StateRepository::Migration::Context *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003980`
- `0x18000b81c`
- `0x18000b964`
- `0x18000ba20`
- `0x18000ba60`
- `0x18000c1f4`
- `0x18000c3bc`
- `0x180012e90`
- `0x1800182b0`
- `0x18001849c`
- `0x180025070`

## string_xrefs

- `0x180012ef3`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.primarytileuser.deleteendoflifetiles.cpp`
- `0x180012f4d`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.primarytileuser.deleteendoflifetiles.cpp`
- `0x180012f7f`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.primarytileuser.deleteendoflifetiles.cpp`
- `0x180012fb2`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.primarytileuser.deleteendoflifetiles.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::StateRepository_PrimaryTileUser_DeleteEndOFLifeTiles(
        StateRepository::Migration *this,
        const struct StateRepository::Migration::Context *a2)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  int v5; // eax
  StateRepository::Migration::Context *v6; // rcx
  const unsigned __int16 **v7; // rbx
  int v8; // eax
  int v9; // eax
  int v11[4]; // [rsp+20h] [rbp-59h] BYREF
  _BYTE v12[128]; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v13[3]; // [rsp+B0h] [rbp+37h] BYREF
  __int64 v14; // [rsp+C8h] [rbp+4Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  StateRepository::Database::Database((StateRepository::Database *)v12);
  v3 = StateRepository::Migration::Context::Open(v2, 1u, (StateRepository::Database *)v12);
  if ( v3 < 0 )
  {
    v4 = 22;
LABEL_14:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.primarytileuser.del"
                    "eteendoflifetiles.cpp",
      (const char *)(unsigned int)v3,
      v11[0]);
    goto LABEL_15;
  }
  v5 = StateRepository::Database::BeginTransaction((StateRepository::Database *)v12, &stru_18003C280, 0, 0);
  if ( v5 >= 0 )
  {
    *(_QWORD *)v11 = v12;
    v7 = (const unsigned __int16 **)v13;
    v13[0] = L"Microsoft.Windows.SecondaryTileExperience_cw5n1h2txyewy";
    v13[1] = L"Windows.MiracastView_cw5n1h2txyewy";
    v13[2] = L"Windows.ContactSupport_cw5n1h2txyewy";
    do
    {
      v8 = StateRepository::Entity::PrimaryTileUser::DeletePrimaryTileUserByPackageFamilyName(
             (struct StateRepository::Database *)v12,
             *v7);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.primarytileuser"
                        ".deleteendoflifetiles.cpp",
          (const char *)(unsigned int)v8,
          v11[0]);
      ++v7;
    }
    while ( v7 != (const unsigned __int16 **)&v14 );
    v9 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)v11);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.primarytileuser.d"
                      "eleteendoflifetiles.cpp",
        (const char *)(unsigned int)v9,
        v11[0]);
    StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)v11);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.primarytileuser.del"
                    "eteendoflifetiles.cpp",
      (const char *)(unsigned int)v5,
      v11[0]);
  }
  v3 = StateRepository::Migration::Context::Close(v6, (struct StateRepository::Database *)v12);
  if ( v3 < 0 )
  {
    v4 = 42;
    goto LABEL_14;
  }
LABEL_15:
  StateRepository::Database::~Database((StateRepository::Database *)v12);
  return 0;
}

```

## disassembly

```asm
0x180012e90  mov     [rsp-8+arg_0], rbx
0x180012e95  push    rbp
0x180012e96  lea     rbp, [rsp-57h]
0x180012e9b  sub     rsp, 0D0h
0x180012ea2  mov     rax, cs:__security_cookie
0x180012ea9  xor     rax, rsp
0x180012eac  mov     [rbp+57h+var_8], rax
0x180012eb0  lea     rcx, [rbp+57h+var_A0]; this
0x180012eb4  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x180012eb9  lea     r8, [rbp+57h+var_A0]
0x180012ebd  mov     edx, 1
0x180012ec2  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x180012ec7  test    eax, eax
0x180012ec9  jns     short loc_180012ED5
0x180012ecb  mov     edx, 16h
0x180012ed0  jmp     loc_180012FAE
0x180012ed5  xor     r9d, r9d; void *
0x180012ed8  lea     rdx, stru_18003C280; struct _GUID *
0x180012edf  xor     r8d, r8d; int (*)(void *)
0x180012ee2  lea     rcx, [rbp+57h+var_A0]; this
0x180012ee6  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x180012eeb  test    eax, eax
0x180012eed  jns     short loc_180012F0C
0x180012eef  mov     rcx, [rbp+5Fh]; this
0x180012ef3  lea     r8, aOnecoreBaseApp_44; "onecore\\base\\appmodel\\staterepositor"...
0x180012efa  mov     r9d, eax; char *
0x180012efd  mov     edx, 1Dh; void *
0x180012f02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012f07  jmp     loc_180012F9C
0x180012f0c  lea     rax, [rbp+57h+var_A0]
0x180012f10  mov     qword ptr [rbp+57h+var_B0], rax
0x180012f14  lea     rbx, [rbp+57h+var_20]
0x180012f18  lea     rax, aMicrosoftWindo; "Microsoft.Windows.SecondaryTileExperien"...
0x180012f1f  mov     [rbp+57h+var_20], rax
0x180012f23  lea     rax, aWindowsMiracas; "Windows.MiracastView_cw5n1h2txyewy"
0x180012f2a  mov     [rbp+57h+var_18], rax
0x180012f2e  lea     rax, aWindowsContact; "Windows.ContactSupport_cw5n1h2txyewy"
0x180012f35  mov     [rbp+57h+var_10], rax
0x180012f39  mov     rdx, [rbx]; unsigned __int16 *
0x180012f3c  lea     rcx, [rbp+57h+var_A0]; this
0x180012f40  call    ?DeletePrimaryTileUserByPackageFamilyName@PrimaryTileUser@Entity@StateRepository@@SAJAEAVDatabase@3@PEBG@Z; StateRepository::Entity::PrimaryTileUser::DeletePrimaryTileUserByPackageFamilyName(StateRepository::Database &,ushort const *)
0x180012f45  test    eax, eax
0x180012f47  jns     short loc_180012F61
0x180012f49  mov     rcx, [rbp+5Fh]; this
0x180012f4d  lea     r8, aOnecoreBaseApp_44; "onecore\\base\\appmodel\\staterepositor"...
0x180012f54  mov     r9d, eax; char *
0x180012f57  mov     edx, 26h ; '&'; void *
0x180012f5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012f61  add     rbx, 8
0x180012f65  lea     rax, [rbp+57h+var_8]
0x180012f69  cmp     rbx, rax
0x180012f6c  jnz     short loc_180012F39
0x180012f6e  lea     rcx, [rbp+57h+var_B0]; this
0x180012f72  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x180012f77  test    eax, eax
0x180012f79  jns     short loc_180012F93
0x180012f7b  mov     rcx, [rbp+5Fh]; this
0x180012f7f  lea     r8, aOnecoreBaseApp_44; "onecore\\base\\appmodel\\staterepositor"...
0x180012f86  mov     r9d, eax; char *
0x180012f89  mov     edx, 28h ; '('; void *
0x180012f8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012f93  lea     rcx, [rbp+57h+var_B0]; this
0x180012f97  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x180012f9c  lea     rdx, [rbp+57h+var_A0]; struct StateRepository::Database *
0x180012fa0  call    ?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z; StateRepository::Migration::Context::Close(StateRepository::Database &)
0x180012fa5  test    eax, eax
0x180012fa7  jns     short loc_180012FC1
0x180012fa9  mov     edx, 2Ah ; '*'; void *
0x180012fae  mov     rcx, [rbp+5Fh]; this
0x180012fb2  lea     r8, aOnecoreBaseApp_44; "onecore\\base\\appmodel\\staterepositor"...
0x180012fb9  mov     r9d, eax; char *
0x180012fbc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012fc1  lea     rcx, [rbp+57h+var_A0]; this
0x180012fc5  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x180012fca  xor     eax, eax
0x180012fcc  mov     rcx, [rbp+57h+var_8]
0x180012fd0  xor     rcx, rsp; StackCookie
0x180012fd3  call    __security_check_cookie
0x180012fd8  mov     rbx, [rsp+0D0h+arg_0]
0x180012fe0  add     rsp, 0D0h
0x180012fe7  pop     rbp
0x180012fe8  retn
```
