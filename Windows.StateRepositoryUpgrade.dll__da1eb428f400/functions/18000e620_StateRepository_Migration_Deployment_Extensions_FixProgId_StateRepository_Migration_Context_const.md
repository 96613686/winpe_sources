# StateRepository::Migration::Deployment_Extensions_FixProgId(StateRepository::Migration::Context const &)

- ea: `0x18000e620`
- end: `0x18000e854`
- name: `?Deployment_Extensions_FixProgId@Migration@StateRepository@@YAJAEBVContext@12@@Z`
- size: `564`
- prototype: `__int64 __fastcall(StateRepository::Migration *__hidden this, const struct StateRepository::Migration::Context *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800041cc`
- `0x18000b81c`
- `0x18000b964`
- `0x18000ba20`
- `0x18000ba60`
- `0x18000c1f4`
- `0x18000c3bc`
- `0x18000d9a4`
- `0x18000d9c4`
- `0x18000dc30`
- `0x18000de98`
- `0x18000e620`
- `0x1800182b0`
- `0x18001849c`
- `0x18002b7b0`
- `0x18002c098`
- `0x18002c35c`

## string_xrefs

- `0x18000e671`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e6f1`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e73e`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e787`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e7d0`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e7f5`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e831`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::Deployment_Extensions_FixProgId(
        StateRepository::Migration *this,
        const struct StateRepository::Migration::Context *a2)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  int v5; // eax
  StateRepository::Migration::Context *v6; // rcx
  HKEY v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rdx
  int fixed; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  int v20; // eax
  int *v22; // [rsp+20h] [rbp-49h]
  int v23[2]; // [rsp+30h] [rbp-39h] BYREF
  int v24[2]; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v25[128]; // [rsp+40h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 v27; // [rsp+D8h] [rbp+6Fh] BYREF
  void *Block; // [rsp+E0h] [rbp+77h] BYREF
  _BYTE *v29; // [rsp+E8h] [rbp+7Fh] BYREF

  StateRepository::Database::Database((StateRepository::Database *)v25);
  v3 = StateRepository::Migration::Context::Open(v2, 1, v25);
  if ( v3 < 0 )
  {
    v4 = 252;
LABEL_24:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v3,
      (int)v22);
    goto LABEL_25;
  }
  v5 = StateRepository::Database::BeginTransaction((StateRepository::Database *)v25, &stru_18003BD50, 0, 0);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v5,
      (int)v22);
    goto LABEL_22;
  }
  Block = 0;
  v29 = v25;
  if ( Common::StateSeparation::GetPersistedRegKeyPath(
         (const struct Common::StateSeparationRedirectionMapping *)&Common::StateSeparation::AppModelPackageRepository,
         (unsigned __int16 **)&Block) >= 0 )
  {
    v27 = 0;
    v10 = Common::RegistryKey::OpenIfExists((Common::RegistryKey *)&v27, v7, (const unsigned __int16 *)Block, 0x2011Fu);
    if ( v10 >= 0 )
    {
      if ( !v27 )
        goto LABEL_12;
      v10 = Common::RegistryKey::DeleteSubKeyTree((Common::RegistryKey *)&v27, v11);
      if ( v10 >= 0 )
        goto LABEL_12;
      v12 = 271;
    }
    else
    {
      v12 = 268;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v10,
      (int)v22);
LABEL_12:
    Common::AutoHandleCloseHKEY<HKEY__ *>(v27);
  }
  LODWORD(v27) = 0;
  *(_QWORD *)v23 = &v27;
  *(_QWORD *)v24 = v25;
  fixed = FixEachExtensionData__lambda_9e63c4bd3d6353b3b6dbd962d3d62c7e___lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_(
            v8,
            v25,
            v9,
            v24);
  if ( fixed < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)fixed,
      (int)v23);
  LODWORD(v27) = 0;
  *(_QWORD *)v24 = &v27;
  *(_QWORD *)v23 = v25;
  v16 = FixEachExtensionData__lambda_dd375580670534beaad58b8162d7c441___lambda_f132b2096735b993c1b4fff6ab29717b_(
          v14,
          v25,
          v15,
          v23);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v16,
      (int)v24);
  LODWORD(v27) = 0;
  *(_QWORD *)v24 = &v27;
  *(_QWORD *)v23 = v25;
  v22 = v24;
  v19 = FixEachExtensionData__lambda_9ad295c35d8e9c6f1b9cc870ceb93a8c___lambda_90b20e028de1632536b7572fff0722e4_(
          v17,
          v25,
          v18,
          v23);
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v19,
      (int)v24);
  v20 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)&v29);
  if ( v20 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)v20,
      (int)v22);
  operator delete(Block);
  StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v29);
LABEL_22:
  v3 = StateRepository::Migration::Context::Close(v6, (struct StateRepository::Database *)v25);
  if ( v3 < 0 )
  {
    v4 = 283;
    goto LABEL_24;
  }
LABEL_25:
  StateRepository::Database::~Database((StateRepository::Database *)v25);
  return 0;
}

```

## disassembly

```asm
0x18000e620  push    rbp
0x18000e622  lea     rbp, [rsp-57h]
0x18000e627  sub     rsp, 0C0h
0x18000e62e  lea     rcx, [rbp+57h+var_80]; this
0x18000e632  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18000e637  lea     r8, [rbp+57h+var_80]
0x18000e63b  mov     edx, 1
0x18000e640  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x18000e645  test    eax, eax
0x18000e647  jns     short loc_18000E653
0x18000e649  mov     edx, 0FCh
0x18000e64e  jmp     loc_18000E82D
0x18000e653  xor     r9d, r9d; void *
0x18000e656  lea     rdx, stru_18003BD50; struct _GUID *
0x18000e65d  xor     r8d, r8d; int (*)(void *)
0x18000e660  lea     rcx, [rbp+57h+var_80]; this
0x18000e664  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x18000e669  test    eax, eax
0x18000e66b  jns     short loc_18000E68A
0x18000e66d  mov     rcx, [rbp+5Fh]; this
0x18000e671  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e678  mov     r9d, eax; char *
0x18000e67b  mov     edx, 102h; void *
0x18000e680  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e685  jmp     loc_18000E81B
0x18000e68a  lea     rax, [rbp+57h+var_80]
0x18000e68e  mov     [rbp+57h+Block], 0
0x18000e696  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x18000e69a  mov     [rbp+57h+arg_18], rax
0x18000e69e  lea     rcx, ?AppModelPackageRepository@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x18000e6a5  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x18000e6aa  test    eax, eax
0x18000e6ac  js      short loc_18000E709
0x18000e6ae  mov     r8, [rbp+57h+Block]; unsigned __int16 *
0x18000e6b2  lea     rcx, [rbp+57h+arg_8]; this
0x18000e6b6  mov     r9d, 2011Fh; unsigned int
0x18000e6bc  mov     [rbp+57h+arg_8], 0
0x18000e6c4  call    ?OpenIfExists@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::OpenIfExists(HKEY__ * const,ushort const *,ulong)
0x18000e6c9  test    eax, eax
0x18000e6cb  jns     short loc_18000E6D4
0x18000e6cd  mov     edx, 10Ch
0x18000e6d2  jmp     short loc_18000E6ED
0x18000e6d4  cmp     [rbp+57h+arg_8], 0
0x18000e6d9  jz      short loc_18000E700
0x18000e6db  lea     rcx, [rbp+57h+arg_8]; this
0x18000e6df  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x18000e6e4  test    eax, eax
0x18000e6e6  jns     short loc_18000E700
0x18000e6e8  mov     edx, 10Fh; void *
0x18000e6ed  mov     rcx, [rbp+5Fh]; this
0x18000e6f1  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e6f8  mov     r9d, eax; char *
0x18000e6fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e700  mov     rcx, [rbp+57h+arg_8]
0x18000e704  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e709  lea     rax, [rbp+57h+arg_8]
0x18000e70d  mov     dword ptr [rbp+57h+arg_8], 0
0x18000e714  mov     qword ptr [rbp+57h+var_90], rax
0x18000e718  lea     r9, [rbp+57h+var_88]
0x18000e71c  lea     rax, [rbp+57h+var_80]
0x18000e720  mov     qword ptr [rbp+57h+var_88], rax
0x18000e724  lea     rdx, [rbp+57h+var_80]
0x18000e728  lea     rax, [rbp+57h+var_90]
0x18000e72c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000e731  call    FixEachExtensionData__lambda_9e63c4bd3d6353b3b6dbd962d3d62c7e___lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6___; FixEachExtensionData__lambda_9e63c4bd3d6353b3b6dbd962d3d62c7e___lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_
0x18000e736  test    eax, eax
0x18000e738  jns     short loc_18000E752
0x18000e73a  mov     rcx, [rbp+5Fh]; this
0x18000e73e  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e745  mov     r9d, eax; char *
0x18000e748  mov     edx, 114h; void *
0x18000e74d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e752  lea     rax, [rbp+57h+arg_8]
0x18000e756  mov     dword ptr [rbp+57h+arg_8], 0
0x18000e75d  mov     qword ptr [rbp+57h+var_88], rax
0x18000e761  lea     r9, [rbp+57h+var_90]
0x18000e765  lea     rax, [rbp+57h+var_80]
0x18000e769  mov     qword ptr [rbp+57h+var_90], rax
0x18000e76d  lea     rdx, [rbp+57h+var_80]
0x18000e771  lea     rax, [rbp+57h+var_88]
0x18000e775  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000e77a  call    FixEachExtensionData__lambda_dd375580670534beaad58b8162d7c441___lambda_f132b2096735b993c1b4fff6ab29717b___; FixEachExtensionData__lambda_dd375580670534beaad58b8162d7c441___lambda_f132b2096735b993c1b4fff6ab29717b_
0x18000e77f  test    eax, eax
0x18000e781  jns     short loc_18000E79B
0x18000e783  mov     rcx, [rbp+5Fh]; this
0x18000e787  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e78e  mov     r9d, eax; char *
0x18000e791  mov     edx, 115h; void *
0x18000e796  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e79b  lea     rax, [rbp+57h+arg_8]
0x18000e79f  mov     dword ptr [rbp+57h+arg_8], 0
0x18000e7a6  mov     qword ptr [rbp+57h+var_88], rax
0x18000e7aa  lea     r9, [rbp+57h+var_90]
0x18000e7ae  lea     rax, [rbp+57h+var_80]
0x18000e7b2  mov     qword ptr [rbp+57h+var_90], rax
0x18000e7b6  lea     rdx, [rbp+57h+var_80]
0x18000e7ba  lea     rax, [rbp+57h+var_88]
0x18000e7be  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18000e7c3  call    FixEachExtensionData__lambda_9ad295c35d8e9c6f1b9cc870ceb93a8c___lambda_90b20e028de1632536b7572fff0722e4___; FixEachExtensionData__lambda_9ad295c35d8e9c6f1b9cc870ceb93a8c___lambda_90b20e028de1632536b7572fff0722e4_
0x18000e7c8  test    eax, eax
0x18000e7ca  jns     short loc_18000E7E4
0x18000e7cc  mov     rcx, [rbp+5Fh]; this
0x18000e7d0  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e7d7  mov     r9d, eax; char *
0x18000e7da  mov     edx, 116h; void *
0x18000e7df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e7e4  lea     rcx, [rbp+57h+arg_18]; this
0x18000e7e8  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x18000e7ed  test    eax, eax
0x18000e7ef  jns     short loc_18000E809
0x18000e7f1  mov     rcx, [rbp+5Fh]; this
0x18000e7f5  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e7fc  mov     r9d, eax; char *
0x18000e7ff  mov     edx, 118h; void *
0x18000e804  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e809  mov     rcx, [rbp+57h+Block]; Block
0x18000e80d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e812  lea     rcx, [rbp+57h+arg_18]; this
0x18000e816  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x18000e81b  lea     rdx, [rbp+57h+var_80]; struct StateRepository::Database *
0x18000e81f  call    ?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z; StateRepository::Migration::Context::Close(StateRepository::Database &)
0x18000e824  test    eax, eax
0x18000e826  jns     short loc_18000E840
0x18000e828  mov     edx, 11Bh; void *
0x18000e82d  mov     rcx, [rbp+5Fh]; this
0x18000e831  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e838  mov     r9d, eax; char *
0x18000e83b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e840  lea     rcx, [rbp+57h+var_80]; this
0x18000e844  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18000e849  xor     eax, eax
0x18000e84b  add     rsp, 0C0h
0x18000e852  pop     rbp
0x18000e853  retn
```
