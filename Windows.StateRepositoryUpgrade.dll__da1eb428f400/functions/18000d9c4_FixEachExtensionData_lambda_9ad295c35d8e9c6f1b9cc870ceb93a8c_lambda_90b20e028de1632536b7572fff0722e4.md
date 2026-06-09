# FixEachExtensionData__lambda_9ad295c35d8e9c6f1b9cc870ceb93a8c___lambda_90b20e028de1632536b7572fff0722e4_

- ea: `0x18000d9c4`
- end: `0x18000dc29`
- name: `FixEachExtensionData__lambda_9ad295c35d8e9c6f1b9cc870ceb93a8c___lambda_90b20e028de1632536b7572fff0722e4___`
- size: `613`
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
- `0x18000d9c4`
- `0x18000e144`
- `0x18000e264`
- `0x18000e438`
- `0x18001b5a8`
- `0x18001f900`
- `0x180021030`
- `0x180022034`
- `0x180022064`
- `0x18002a08c`

## string_xrefs

- `0x18000da3e`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000da93`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000db48`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000dbc6`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000dafa`: `windows.appUriHandler`
- `0x18000da23`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-migrator-deployment-fixprogidinfo.cpp`
- `0x18000d9f5`: `SELECT auh._AppUriHandlerID, auh.HostName, p.PackageFullName, pf.PackageFamilyName, a.PackageRelativeApplicationId, a.ApplicationUserModelId, ae.Activation FROM ApplicationExtension AS ae INNER JOIN AppUriHandler AS auh ON auh.Extension=ae._ApplicationExtensionID INNER JOIN Application AS a ON a._ApplicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily WHERE ae.category='windows.appUriHandler';`

## pseudocode

```c
__int64 __fastcall FixEachExtensionData__lambda_9ad295c35d8e9c6f1b9cc870ceb93a8c___lambda_90b20e028de1632536b7572fff0722e4_(
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
  int v19; // eax
  int v20; // edi
  struct StateRepository::Statement *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28[5]; // [rsp+70h] [rbp-90h] BYREF
  int v29[2]; // [rsp+98h] [rbp-68h]
  int v30[2]; // [rsp+A8h] [rbp-58h]
  _BYTE v31[40]; // [rsp+D0h] [rbp-30h] BYREF
  int v32[2]; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v33; // [rsp+108h] [rbp+8h]
  __int64 v34; // [rsp+118h] [rbp+18h]
  __int64 v35; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  __int64 v37; // [rsp+190h] [rbp+90h] BYREF
  __int64 v38; // [rsp+1A0h] [rbp+A0h] BYREF
  void *v39; // [rsp+1A8h] [rbp+A8h] BYREF

  v38 = a3;
  v37 = a1;
  StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FixProgIdInfo((StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v28);
  v7 = *v6;
  v37 = 0;
  v8 = StateRepository::StatementExecution::PrepareAndBindAndFind(
         v7,
         (struct StateRepository::Database *)"SELECT auh._AppUriHandlerID, auh.HostName, p.PackageFullName, pf.PackageFam"
                                             "ilyName, a.PackageRelativeApplicationId, a.ApplicationUserModelId, ae.Activ"
                                             "ation FROM ApplicationExtension AS ae INNER JOIN AppUriHandler AS auh ON au"
                                             "h.Extension=ae._ApplicationExtensionID INNER JOIN Application AS a ON a._Ap"
                                             "plicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Packag"
                                             "e INNER JOIN PackageFamily AS pf ON pf._PackageFamilyID=p.PackageFamily WHE"
                                             "RE ae.category='windows.appUriHandler';",
         0,
         (const char *)&v37,
         v22);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-migrator-deployment-fixprogidinfo.cpp",
      (const char *)(unsigned int)v8,
      v23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v9,
      v24);
    v10 = v9;
    v11 = 30;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v10,
      v23);
    goto LABEL_21;
  }
  LOBYTE(v38) = 0;
  Next = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(
           a2,
           (struct StateRepository::Statement *)&v37,
           (struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v28,
           (bool *)&v38);
  v9 = Next;
  if ( Next < 0 )
  {
    v10 = (unsigned int)Next;
    v11 = 33;
    goto LABEL_5;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v38 )
    {
      v9 = 0;
      goto LABEL_21;
    }
    v39 = 0;
    Block = 0;
    TrustLevel = StateRepository::Entity::Activation::GetTrustLevel(v31);
    RuntimeBehavior = StateRepository::Entity::Activation::GetRuntimeBehavior(v31, TrustLevel);
    ProgIdAndAcidForExtension = StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(
                                  *(_WORD **)v29,
                                  *(_WORD **)v30,
                                  *(const unsigned __int16 **)v32,
                                  RuntimeBehavior,
                                  v15,
                                  v33,
                                  v35,
                                  L"windows.appUriHandler",
                                  v28[1],
                                  v34,
                                  (__int64)&Block,
                                  (unsigned __int16 **)&v39);
    v18 = Block;
    if ( ProgIdAndAcidForExtension >= 0 )
      lambda_90b20e028de1632536b7572fff0722e4_::operator()(a5, v17, (__int64)a2, v28, (__int64)Block);
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
        (const char *)(unsigned int)ProgIdAndAcidForExtension,
        v25);
    v19 = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(
            a2,
            (struct StateRepository::Statement *)&v37,
            (struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v28,
            (bool *)&v38);
    v20 = v19;
    if ( v19 < 0 )
      break;
    if ( v18 )
      operator delete(v18);
    if ( v39 )
      operator delete(v39);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
    (const char *)(unsigned int)v19,
    v26);
  if ( v18 )
    operator delete(v18);
  if ( v39 )
    operator delete(v39);
  v9 = v20;
LABEL_21:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
  StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::~FixProgIdInfo((StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v28);
  return v9;
}

```

## disassembly

```asm
0x18000d9c4  mov     [rsp-8+arg_8], rbx
0x18000d9c9  mov     [rsp-8+arg_10], r8
0x18000d9ce  mov     [rsp-8+arg_0], rcx
0x18000d9d3  push    rbp
0x18000d9d4  push    rsi
0x18000d9d5  push    rdi
0x18000d9d6  lea     rbp, [rsp-70h]
0x18000d9db  sub     rsp, 170h
0x18000d9e2  lea     rcx, [rsp+180h+var_110]; this
0x18000d9e7  mov     r10, r9
0x18000d9ea  mov     rsi, rdx
0x18000d9ed  call    ??0FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FixProgIdInfo(void)
0x18000d9f2  mov     rcx, [r10]; this
0x18000d9f5  lea     rdx, aSelectAuhAppur; "SELECT auh._AppUriHandlerID, auh.HostNa"...
0x18000d9fc  lea     r9, [rbp+80h+arg_0]; char *
0x18000da03  mov     [rbp+80h+arg_0], 0
0x18000da0e  xor     r8d, r8d; char *
0x18000da11  call    ?PrepareAndBindAndFind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFind(StateRepository::Database &,char const *,char const *,StateRepository::Statement &)
0x18000da16  mov     ebx, eax
0x18000da18  test    eax, eax
0x18000da1a  jns     short loc_18000DA5C
0x18000da1c  mov     rcx, [rbp+88h]; this
0x18000da23  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\staterepositor"...
0x18000da2a  mov     r9d, eax; char *
0x18000da2d  mov     edx, 5Ah ; 'Z'; void *
0x18000da32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da37  mov     rcx, [rbp+88h]; this
0x18000da3e  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000da45  mov     r9d, ebx; char *
0x18000da48  mov     edx, 0DAh; void *
0x18000da4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da52  mov     r9d, ebx
0x18000da55  mov     edx, 1Eh
0x18000da5a  jmp     short loc_18000DA8C
0x18000da5c  lea     r9, [rbp+80h+arg_10]; bool *
0x18000da63  mov     byte ptr [rbp+80h+arg_10], 0
0x18000da6a  lea     r8, [rsp+180h+var_110]; struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *
0x18000da6f  mov     rcx, rsi; struct StateRepository::Database *
0x18000da72  lea     rdx, [rbp+80h+arg_0]; struct StateRepository::Statement *
0x18000da79  call    ?FindNext@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@AEAV12345@AEA_N@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(StateRepository::Database &,StateRepository::Statement &,StateRepository::Entity::Migrator::Deployment::FixProgIdInfo &,bool &)
0x18000da7e  mov     ebx, eax
0x18000da80  test    eax, eax
0x18000da82  jns     short loc_18000DAA4
0x18000da84  mov     r9d, eax; char *
0x18000da87  mov     edx, 21h ; '!'; void *
0x18000da8c  mov     rcx, [rbp+88h]; this
0x18000da93  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000da9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da9f  jmp     loc_18000DBFE
0x18000daa4  cmp     byte ptr [rbp+80h+arg_10], 0
0x18000daab  jz      loc_18000DBFC
0x18000dab1  lea     rcx, [rbp+80h+var_B0]
0x18000dab5  mov     [rbp+80h+arg_18], 0
0x18000dac0  mov     [rsp+180h+Block], 0
0x18000dac9  call    ?GetTrustLevel@Activation@Entity@StateRepository@@QEBA?AW4SRTrustLevel@3@XZ; StateRepository::Entity::Activation::GetTrustLevel(void)
0x18000dace  lea     rcx, [rbp+80h+var_B0]
0x18000dad2  mov     edx, eax
0x18000dad4  call    ?GetRuntimeBehavior@Activation@Entity@StateRepository@@QEBA?AW4RuntimeBehavior@3@XZ; StateRepository::Entity::Activation::GetRuntimeBehavior(void)
0x18000dad9  mov     rcx, [rbp+80h+var_68]
0x18000dadd  mov     r9d, eax; int
0x18000dae0  mov     r8, qword ptr [rbp+80h+var_88]; int
0x18000dae4  lea     rax, [rbp+80h+arg_18]
0x18000daeb  mov     [rsp+180h+var_128], rax; __int64
0x18000daf0  lea     rax, [rsp+180h+Block]
0x18000daf5  mov     [rsp+180h+var_130], rax; __int64
0x18000dafa  lea     rax, aWindowsAppurih; "windows.appUriHandler"
0x18000db01  mov     [rsp+180h+var_138], rcx; __int64
0x18000db06  mov     rcx, [rsp+180h+var_108]
0x18000db0b  mov     [rsp+180h+var_140], rcx; __int64
0x18000db10  mov     rcx, [rbp+80h+var_48]
0x18000db14  mov     [rsp+180h+var_148], rax; __int64
0x18000db19  mov     rax, [rbp+80h+var_78]
0x18000db1d  mov     [rsp+180h+var_150], rcx; __int64
0x18000db22  mov     rcx, qword ptr [rbp+80h+var_E8]; int
0x18000db26  mov     [rsp+180h+var_158], rax; unsigned __int16 *
0x18000db2b  mov     [rsp+180h+var_160], edx; int
0x18000db2f  mov     rdx, qword ptr [rbp+80h+var_D8]; int
0x18000db33  call    ?GenerateProgIdAndAcidForExtension@ProgId@DataType@StateRepository@@YAJPEBG00W4RuntimeBehavior@3@W4SRTrustLevel@3@00000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z; StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18000db38  mov     rbx, [rsp+180h+Block]
0x18000db3d  test    eax, eax
0x18000db3f  jns     short loc_18000DB5E
0x18000db41  mov     rcx, [rbp+88h]; this
0x18000db48  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000db4f  mov     r9d, eax; char *
0x18000db52  mov     edx, 34h ; '4'; void *
0x18000db57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000db5c  jmp     short loc_18000DB77
0x18000db5e  mov     rcx, [rbp+80h+arg_20]
0x18000db65  lea     r9, [rsp+180h+var_110]
0x18000db6a  mov     r8, rsi
0x18000db6d  mov     qword ptr [rsp+180h+var_160], rbx; int
0x18000db72  call    _lambda_90b20e028de1632536b7572fff0722e4___operator__
0x18000db77  lea     r9, [rbp+80h+arg_10]; bool *
0x18000db7e  mov     rcx, rsi; struct StateRepository::Database *
0x18000db81  lea     r8, [rsp+180h+var_110]; struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *
0x18000db86  lea     rdx, [rbp+80h+arg_0]; struct StateRepository::Statement *
0x18000db8d  call    ?FindNext@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@AEAV12345@AEA_N@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(StateRepository::Database &,StateRepository::Statement &,StateRepository::Entity::Migrator::Deployment::FixProgIdInfo &,bool &)
0x18000db92  mov     edi, eax
0x18000db94  test    eax, eax
0x18000db96  js      short loc_18000DBBF
0x18000db98  test    rbx, rbx
0x18000db9b  jz      short loc_18000DBA5
0x18000db9d  mov     rcx, rbx; Block
0x18000dba0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dba5  mov     rcx, [rbp+80h+arg_18]; Block
0x18000dbac  test    rcx, rcx
0x18000dbaf  jz      loc_18000DAA4
0x18000dbb5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dbba  jmp     loc_18000DAA4
0x18000dbbf  mov     rcx, [rbp+88h]; this
0x18000dbc6  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000dbcd  mov     r9d, edi; char *
0x18000dbd0  mov     edx, 3Ah ; ':'; void *
0x18000dbd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbda  test    rbx, rbx
0x18000dbdd  jz      short loc_18000DBE7
0x18000dbdf  mov     rcx, rbx; Block
0x18000dbe2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dbe7  mov     rcx, [rbp+80h+arg_18]; Block
0x18000dbee  test    rcx, rcx
0x18000dbf1  jz      short loc_18000DBF8
0x18000dbf3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dbf8  mov     ebx, edi
0x18000dbfa  jmp     short loc_18000DBFE
0x18000dbfc  xor     ebx, ebx
0x18000dbfe  lea     rcx, [rbp+80h+arg_0]; this
0x18000dc05  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000dc0a  lea     rcx, [rsp+180h+var_110]; this
0x18000dc0f  call    ??1FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::~FixProgIdInfo(void)
0x18000dc14  mov     eax, ebx
0x18000dc16  mov     rbx, [rsp+180h+arg_8]
0x18000dc1e  add     rsp, 170h
0x18000dc25  pop     rdi
0x18000dc26  pop     rsi
0x18000dc27  pop     rbp
0x18000dc28  retn
```
