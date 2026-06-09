# FixEachExtensionData__lambda_9e63c4bd3d6353b3b6dbd962d3d62c7e___lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_

- ea: `0x18000dc30`
- end: `0x18000de92`
- name: `FixEachExtensionData__lambda_9e63c4bd3d6353b3b6dbd962d3d62c7e___lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6___`
- size: `610`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000e620`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000c3bc`
- `0x18000dc30`
- `0x18000e144`
- `0x18000e264`
- `0x18000e2e0`
- `0x18001b5a8`
- `0x18001f900`
- `0x180021030`
- `0x180022034`
- `0x180022064`
- `0x18002a08c`

## string_xrefs

- `0x18000dca8`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000dcfd`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000ddb9`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000de38`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000dd64`: `windows.protocol`
- `0x18000dc5f`: `SELECT pr._ProtocolID, pr.ProtocolName, p.PackageFullName, pf.PackageFamilyName, a.PackageRelativeApplicationId, a.ApplicationUserModelId, ae.Activation FROM ApplicationExtension AS ae INNER JOIN Protocol AS pr ON pr.Extension=ae._ApplicationExtensionID INNER JOIN Application AS a ON a._ApplicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily WHERE ae.category='windows.protocol';`
- `0x18000dc8d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-migrator-deployment-fixprogidinfo.cpp`

## pseudocode

```c
__int64 __fastcall FixEachExtensionData__lambda_9e63c4bd3d6353b3b6dbd962d3d62c7e___lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_(
        __int64 a1,
        struct StateRepository::Database *a2,
        __int64 a3,
        __int64 a4,
        _DWORD **a5)
{
  StateRepository::StatementExecution **v6; // r10
  StateRepository::StatementExecution *v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int Next; // eax
  unsigned int TrustLevel; // eax
  int RuntimeBehavior; // eax
  int v15; // edx
  int ProgIdAndAcidForExtension; // eax
  __int64 v17; // rdx
  void *v18; // rbx
  void *v19; // rdi
  int v20; // eax
  int v21; // esi
  struct StateRepository::Statement *v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29[5]; // [rsp+70h] [rbp-90h] BYREF
  int v30[2]; // [rsp+98h] [rbp-68h]
  int v31[2]; // [rsp+A8h] [rbp-58h]
  _BYTE v32[40]; // [rsp+D0h] [rbp-30h] BYREF
  int v33[2]; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v34; // [rsp+108h] [rbp+8h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  __int64 v36; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  __int64 v38; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v39; // [rsp+1B0h] [rbp+B0h] BYREF
  void *v40; // [rsp+1B8h] [rbp+B8h] BYREF

  v39 = a3;
  v38 = a1;
  StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FixProgIdInfo((StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v29);
  v7 = *v6;
  v38 = 0;
  v8 = StateRepository::StatementExecution::PrepareAndBindAndFind(
         v7,
         (struct StateRepository::Database *)"SELECT pr._ProtocolID, pr.ProtocolName, p.PackageFullName, pf.PackageFamily"
                                             "Name, a.PackageRelativeApplicationId, a.ApplicationUserModelId, ae.Activati"
                                             "on FROM ApplicationExtension AS ae INNER JOIN Protocol AS pr ON pr.Extensio"
                                             "n=ae._ApplicationExtensionID INNER JOIN Application AS a ON a._ApplicationI"
                                             "D=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JO"
                                             "IN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily WHERE ae.cate"
                                             "gory='windows.protocol';",
         0,
         (const char *)&v38,
         v23);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-migrator-deployment-fixprogidinfo.cpp",
      (const char *)(unsigned int)v8,
      v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v9,
      v25);
    v10 = v9;
    v11 = 30;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v10,
      v24);
    goto LABEL_21;
  }
  LOBYTE(v39) = 0;
  Next = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(
           a2,
           (struct StateRepository::Statement *)&v38,
           (struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v29,
           (bool *)&v39);
  v9 = Next;
  if ( Next < 0 )
  {
    v10 = (unsigned int)Next;
    v11 = 33;
    goto LABEL_5;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v39 )
    {
      v9 = 0;
      goto LABEL_21;
    }
    v40 = 0;
    Block = 0;
    TrustLevel = StateRepository::Entity::Activation::GetTrustLevel(v32);
    RuntimeBehavior = StateRepository::Entity::Activation::GetRuntimeBehavior(v32, TrustLevel);
    ProgIdAndAcidForExtension = StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(
                                  *(_WORD **)v30,
                                  *(_WORD **)v31,
                                  *(const unsigned __int16 **)v33,
                                  RuntimeBehavior,
                                  v15,
                                  v34,
                                  v36,
                                  L"windows.protocol",
                                  v29[1],
                                  v35,
                                  (__int64)&Block,
                                  (unsigned __int16 **)&v40);
    v18 = v40;
    v19 = Block;
    if ( ProgIdAndAcidForExtension >= 0 )
      lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6_::operator()(a5, v17, (__int64)a2, v29, (__int64)Block, (int)v40);
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
        (const char *)(unsigned int)ProgIdAndAcidForExtension,
        v26);
    v20 = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(
            a2,
            (struct StateRepository::Statement *)&v38,
            (struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v29,
            (bool *)&v39);
    v21 = v20;
    if ( v20 < 0 )
      break;
    if ( v19 )
      operator delete(v19);
    if ( v18 )
      operator delete(v18);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
    (const char *)(unsigned int)v20,
    v27);
  if ( v19 )
    operator delete(v19);
  if ( v18 )
    operator delete(v18);
  v9 = v21;
LABEL_21:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v38);
  StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::~FixProgIdInfo((StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v29);
  return v9;
}

```

## disassembly

```asm
0x18000dc30  mov     [rsp-8+arg_10], r8
0x18000dc35  mov     [rsp-8+arg_0], rcx
0x18000dc3a  push    rbp
0x18000dc3b  push    rbx
0x18000dc3c  push    rsi
0x18000dc3d  push    rdi
0x18000dc3e  push    r14
0x18000dc40  lea     rbp, [rsp-70h]
0x18000dc45  sub     rsp, 170h
0x18000dc4c  lea     rcx, [rsp+190h+var_120]; this
0x18000dc51  mov     r10, r9
0x18000dc54  mov     r14, rdx
0x18000dc57  call    ??0FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FixProgIdInfo(void)
0x18000dc5c  mov     rcx, [r10]; this
0x18000dc5f  lea     rdx, aSelectPrProtoc; "SELECT pr._ProtocolID, pr.ProtocolName,"...
0x18000dc66  lea     r9, [rbp+90h+arg_0]; char *
0x18000dc6d  mov     [rbp+90h+arg_0], 0
0x18000dc78  xor     r8d, r8d; char *
0x18000dc7b  call    ?PrepareAndBindAndFind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFind(StateRepository::Database &,char const *,char const *,StateRepository::Statement &)
0x18000dc80  mov     ebx, eax
0x18000dc82  test    eax, eax
0x18000dc84  jns     short loc_18000DCC6
0x18000dc86  mov     rcx, [rbp+98h]; this
0x18000dc8d  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\staterepositor"...
0x18000dc94  mov     r9d, eax; char *
0x18000dc97  mov     edx, 3Ah ; ':'; void *
0x18000dc9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dca1  mov     rcx, [rbp+98h]; this
0x18000dca8  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000dcaf  mov     r9d, ebx; char *
0x18000dcb2  mov     edx, 5Dh ; ']'; void *
0x18000dcb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcbc  mov     r9d, ebx
0x18000dcbf  mov     edx, 1Eh
0x18000dcc4  jmp     short loc_18000DCF6
0x18000dcc6  lea     r9, [rbp+90h+arg_10]; bool *
0x18000dccd  mov     byte ptr [rbp+90h+arg_10], 0
0x18000dcd4  lea     r8, [rsp+190h+var_120]; struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *
0x18000dcd9  mov     rcx, r14; struct StateRepository::Database *
0x18000dcdc  lea     rdx, [rbp+90h+arg_0]; struct StateRepository::Statement *
0x18000dce3  call    ?FindNext@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@AEAV12345@AEA_N@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(StateRepository::Database &,StateRepository::Statement &,StateRepository::Entity::Migrator::Deployment::FixProgIdInfo &,bool &)
0x18000dce8  mov     ebx, eax
0x18000dcea  test    eax, eax
0x18000dcec  jns     short loc_18000DD0E
0x18000dcee  mov     r9d, eax; char *
0x18000dcf1  mov     edx, 21h ; '!'; void *
0x18000dcf6  mov     rcx, [rbp+98h]; this
0x18000dcfd  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000dd04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd09  jmp     loc_18000DE6C
0x18000dd0e  cmp     byte ptr [rbp+90h+arg_10], 0
0x18000dd15  jz      loc_18000DE6A
0x18000dd1b  lea     rcx, [rbp+90h+var_C0]
0x18000dd1f  mov     [rbp+90h+arg_18], 0
0x18000dd2a  mov     [rsp+190h+Block], 0
0x18000dd33  call    ?GetTrustLevel@Activation@Entity@StateRepository@@QEBA?AW4SRTrustLevel@3@XZ; StateRepository::Entity::Activation::GetTrustLevel(void)
0x18000dd38  lea     rcx, [rbp+90h+var_C0]
0x18000dd3c  mov     edx, eax
0x18000dd3e  call    ?GetRuntimeBehavior@Activation@Entity@StateRepository@@QEBA?AW4RuntimeBehavior@3@XZ; StateRepository::Entity::Activation::GetRuntimeBehavior(void)
0x18000dd43  mov     rcx, [rbp+90h+var_78]
0x18000dd47  mov     r9d, eax; int
0x18000dd4a  mov     r8, qword ptr [rbp+90h+var_98]; int
0x18000dd4e  lea     rax, [rbp+90h+arg_18]
0x18000dd55  mov     [rsp+190h+var_138], rax; __int64
0x18000dd5a  lea     rax, [rsp+190h+Block]
0x18000dd5f  mov     [rsp+190h+var_140], rax; __int64
0x18000dd64  lea     rax, aWindowsProtoco; "windows.protocol"
0x18000dd6b  mov     [rsp+190h+var_148], rcx; __int64
0x18000dd70  mov     rcx, [rsp+190h+var_118]
0x18000dd75  mov     [rsp+190h+var_150], rcx; __int64
0x18000dd7a  mov     rcx, [rbp+90h+var_58]
0x18000dd7e  mov     [rsp+190h+var_158], rax; __int64
0x18000dd83  mov     rax, [rbp+90h+var_88]
0x18000dd87  mov     [rsp+190h+var_160], rcx; __int64
0x18000dd8c  mov     rcx, qword ptr [rbp+90h+var_F8]; int
0x18000dd90  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x18000dd95  mov     [rsp+190h+var_170], edx; int
0x18000dd99  mov     rdx, qword ptr [rbp+90h+var_E8]; int
0x18000dd9d  call    ?GenerateProgIdAndAcidForExtension@ProgId@DataType@StateRepository@@YAJPEBG00W4RuntimeBehavior@3@W4SRTrustLevel@3@00000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z; StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18000dda2  mov     rbx, [rbp+90h+arg_18]
0x18000dda9  mov     rdi, [rsp+190h+Block]
0x18000ddae  test    eax, eax
0x18000ddb0  jns     short loc_18000DDCF
0x18000ddb2  mov     rcx, [rbp+98h]; this
0x18000ddb9  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000ddc0  mov     r9d, eax; char *
0x18000ddc3  mov     edx, 34h ; '4'; void *
0x18000ddc8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ddcd  jmp     short loc_18000DDED
0x18000ddcf  mov     rcx, [rbp+90h+arg_20]
0x18000ddd6  lea     r9, [rsp+190h+var_120]
0x18000dddb  mov     [rsp+190h+var_168], rbx
0x18000dde0  mov     r8, r14
0x18000dde3  mov     qword ptr [rsp+190h+var_170], rdi; int
0x18000dde8  call    _lambda_405a3eaa0ff9467ec374fcf6a1cfb7c6___operator__
0x18000dded  lea     r9, [rbp+90h+arg_10]; bool *
0x18000ddf4  mov     rcx, r14; struct StateRepository::Database *
0x18000ddf7  lea     r8, [rsp+190h+var_120]; struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *
0x18000ddfc  lea     rdx, [rbp+90h+arg_0]; struct StateRepository::Statement *
0x18000de03  call    ?FindNext@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@AEAV12345@AEA_N@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(StateRepository::Database &,StateRepository::Statement &,StateRepository::Entity::Migrator::Deployment::FixProgIdInfo &,bool &)
0x18000de08  mov     esi, eax
0x18000de0a  test    eax, eax
0x18000de0c  js      short loc_18000DE31
0x18000de0e  test    rdi, rdi
0x18000de11  jz      short loc_18000DE1B
0x18000de13  mov     rcx, rdi; Block
0x18000de16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de1b  test    rbx, rbx
0x18000de1e  jz      loc_18000DD0E
0x18000de24  mov     rcx, rbx; Block
0x18000de27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de2c  jmp     loc_18000DD0E
0x18000de31  mov     rcx, [rbp+98h]; this
0x18000de38  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000de3f  mov     r9d, esi; char *
0x18000de42  mov     edx, 3Ah ; ':'; void *
0x18000de47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de4c  test    rdi, rdi
0x18000de4f  jz      short loc_18000DE59
0x18000de51  mov     rcx, rdi; Block
0x18000de54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de59  test    rbx, rbx
0x18000de5c  jz      short loc_18000DE66
0x18000de5e  mov     rcx, rbx; Block
0x18000de61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de66  mov     ebx, esi
0x18000de68  jmp     short loc_18000DE6C
0x18000de6a  xor     ebx, ebx
0x18000de6c  lea     rcx, [rbp+90h+arg_0]; this
0x18000de73  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000de78  lea     rcx, [rsp+190h+var_120]; this
0x18000de7d  call    ??1FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::~FixProgIdInfo(void)
0x18000de82  mov     eax, ebx
0x18000de84  add     rsp, 170h
0x18000de8b  pop     r14
0x18000de8d  pop     rdi
0x18000de8e  pop     rsi
0x18000de8f  pop     rbx
0x18000de90  pop     rbp
0x18000de91  retn
```
