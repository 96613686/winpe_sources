# FixEachExtensionData__lambda_dd375580670534beaad58b8162d7c441___lambda_f132b2096735b993c1b4fff6ab29717b_

- ea: `0x18000de98`
- end: `0x18000e0d5`
- name: `FixEachExtensionData__lambda_dd375580670534beaad58b8162d7c441___lambda_f132b2096735b993c1b4fff6ab29717b___`
- size: `573`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x18000e620`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000c3bc`
- `0x18000de98`
- `0x18000e144`
- `0x18000e264`
- `0x18000e52c`
- `0x18001b5a8`
- `0x18001f7d4`
- `0x18001f900`
- `0x180021030`
- `0x180022034`
- `0x180022064`

## string_xrefs

- `0x18000deea`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000df3f`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000dff4`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`
- `0x18000e072`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-deployment.extensions.fixprogid.cpp`

## pseudocode

```c
__int64 __fastcall FixEachExtensionData__lambda_dd375580670534beaad58b8162d7c441___lambda_f132b2096735b993c1b4fff6ab29717b_(
        __int64 a1,
        struct StateRepository::Database *a2,
        __int64 a3,
        __int64 a4,
        _DWORD **a5)
{
  struct StateRepository::Database **v6; // r9
  struct StateRepository::Database *v7; // rcx
  int FileTypeAssociation; // eax
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
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26[5]; // [rsp+70h] [rbp-90h] BYREF
  int v27[2]; // [rsp+98h] [rbp-68h]
  int v28[2]; // [rsp+A8h] [rbp-58h]
  _BYTE v29[40]; // [rsp+D0h] [rbp-30h] BYREF
  int v30[2]; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v31; // [rsp+108h] [rbp+8h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  __int64 v33; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  __int64 v35; // [rsp+190h] [rbp+90h] BYREF
  __int64 v36; // [rsp+1A0h] [rbp+A0h] BYREF
  void *v37; // [rsp+1A8h] [rbp+A8h] BYREF

  v36 = a3;
  v35 = a1;
  StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FixProgIdInfo((StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v26);
  v7 = *v6;
  v35 = 0;
  FileTypeAssociation = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindFileTypeAssociation(
                          v7,
                          (struct StateRepository::Statement *)&v35);
  v9 = FileTypeAssociation;
  if ( FileTypeAssociation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)(unsigned int)FileTypeAssociation,
      v22);
    v10 = v9;
    v11 = 30;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
      (const char *)v10,
      v22);
    goto LABEL_21;
  }
  LOBYTE(v36) = 0;
  Next = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(
           a2,
           (struct StateRepository::Statement *)&v35,
           (struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v26,
           (bool *)&v36);
  v9 = Next;
  if ( Next < 0 )
  {
    v10 = (unsigned int)Next;
    v11 = 33;
    goto LABEL_5;
  }
  while ( 1 )
  {
    if ( !(_BYTE)v36 )
    {
      v9 = 0;
      goto LABEL_21;
    }
    v37 = 0;
    Block = 0;
    TrustLevel = StateRepository::Entity::Activation::GetTrustLevel(v29);
    RuntimeBehavior = StateRepository::Entity::Activation::GetRuntimeBehavior(v29, TrustLevel);
    ProgIdAndAcidForExtension = StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(
                                  *(_WORD **)v27,
                                  *(_WORD **)v28,
                                  *(const unsigned __int16 **)v30,
                                  RuntimeBehavior,
                                  v15,
                                  v31,
                                  v33,
                                  L"windows.fileTypeAssociation",
                                  v26[1],
                                  v32,
                                  (__int64)&Block,
                                  (unsigned __int16 **)&v37);
    v18 = Block;
    if ( ProgIdAndAcidForExtension >= 0 )
      lambda_f132b2096735b993c1b4fff6ab29717b_::operator()(a5, v17, (__int64)a2, v26, (__int64)Block);
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
        (const char *)(unsigned int)ProgIdAndAcidForExtension,
        v23);
    v19 = StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(
            a2,
            (struct StateRepository::Statement *)&v35,
            (struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v26,
            (bool *)&v36);
    v20 = v19;
    if ( v19 < 0 )
      break;
    if ( v18 )
      operator delete(v18);
    if ( v37 )
      operator delete(v37);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.extensions.fixprogid.cpp",
    (const char *)(unsigned int)v19,
    v24);
  if ( v18 )
    operator delete(v18);
  if ( v37 )
    operator delete(v37);
  v9 = v20;
LABEL_21:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v35);
  StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::~FixProgIdInfo((StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *)v26);
  return v9;
}

```

## disassembly

```asm
0x18000de98  mov     [rsp-8+arg_8], rbx
0x18000de9d  mov     [rsp-8+arg_10], r8
0x18000dea2  mov     [rsp-8+arg_0], rcx
0x18000dea7  push    rbp
0x18000dea8  push    rsi
0x18000dea9  push    rdi
0x18000deaa  lea     rbp, [rsp-70h]
0x18000deaf  sub     rsp, 170h
0x18000deb6  lea     rcx, [rsp+180h+var_110]; this
0x18000debb  mov     rsi, rdx
0x18000debe  call    ??0FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FixProgIdInfo(void)
0x18000dec3  mov     rcx, [r9]; struct StateRepository::Database *
0x18000dec6  lea     rdx, [rbp+80h+arg_0]; struct StateRepository::Statement *
0x18000decd  mov     [rbp+80h+arg_0], 0
0x18000ded8  call    ?FindFileTypeAssociation@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindFileTypeAssociation(StateRepository::Database &,StateRepository::Statement &)
0x18000dedd  mov     ebx, eax
0x18000dedf  test    eax, eax
0x18000dee1  jns     short loc_18000DF08
0x18000dee3  mov     rcx, [rbp+88h]; this
0x18000deea  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000def1  mov     r9d, eax; char *
0x18000def4  mov     edx, 9Fh; void *
0x18000def9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000defe  mov     r9d, ebx
0x18000df01  mov     edx, 1Eh
0x18000df06  jmp     short loc_18000DF38
0x18000df08  lea     r9, [rbp+80h+arg_10]; bool *
0x18000df0f  mov     byte ptr [rbp+80h+arg_10], 0
0x18000df16  lea     r8, [rsp+180h+var_110]; struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *
0x18000df1b  mov     rcx, rsi; struct StateRepository::Database *
0x18000df1e  lea     rdx, [rbp+80h+arg_0]; struct StateRepository::Statement *
0x18000df25  call    ?FindNext@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@AEAV12345@AEA_N@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(StateRepository::Database &,StateRepository::Statement &,StateRepository::Entity::Migrator::Deployment::FixProgIdInfo &,bool &)
0x18000df2a  mov     ebx, eax
0x18000df2c  test    eax, eax
0x18000df2e  jns     short loc_18000DF50
0x18000df30  mov     r9d, eax; char *
0x18000df33  mov     edx, 21h ; '!'; void *
0x18000df38  mov     rcx, [rbp+88h]; this
0x18000df3f  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000df46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df4b  jmp     loc_18000E0AA
0x18000df50  cmp     byte ptr [rbp+80h+arg_10], 0
0x18000df57  jz      loc_18000E0A8
0x18000df5d  lea     rcx, [rbp+80h+var_B0]
0x18000df61  mov     [rbp+80h+arg_18], 0
0x18000df6c  mov     [rsp+180h+Block], 0
0x18000df75  call    ?GetTrustLevel@Activation@Entity@StateRepository@@QEBA?AW4SRTrustLevel@3@XZ; StateRepository::Entity::Activation::GetTrustLevel(void)
0x18000df7a  lea     rcx, [rbp+80h+var_B0]
0x18000df7e  mov     edx, eax
0x18000df80  call    ?GetRuntimeBehavior@Activation@Entity@StateRepository@@QEBA?AW4RuntimeBehavior@3@XZ; StateRepository::Entity::Activation::GetRuntimeBehavior(void)
0x18000df85  mov     rcx, [rbp+80h+var_68]
0x18000df89  mov     r9d, eax; int
0x18000df8c  mov     r8, qword ptr [rbp+80h+var_88]; int
0x18000df90  lea     rax, [rbp+80h+arg_18]
0x18000df97  mov     [rsp+180h+var_128], rax; __int64
0x18000df9c  lea     rax, [rsp+180h+Block]
0x18000dfa1  mov     [rsp+180h+var_130], rax; __int64
0x18000dfa6  lea     rax, aWindowsFiletyp; "windows.fileTypeAssociation"
0x18000dfad  mov     [rsp+180h+var_138], rcx; __int64
0x18000dfb2  mov     rcx, [rsp+180h+var_108]
0x18000dfb7  mov     [rsp+180h+var_140], rcx; __int64
0x18000dfbc  mov     rcx, [rbp+80h+var_48]
0x18000dfc0  mov     [rsp+180h+var_148], rax; __int64
0x18000dfc5  mov     rax, [rbp+80h+var_78]
0x18000dfc9  mov     [rsp+180h+var_150], rcx; __int64
0x18000dfce  mov     rcx, qword ptr [rbp+80h+var_E8]; int
0x18000dfd2  mov     [rsp+180h+var_158], rax; unsigned __int16 *
0x18000dfd7  mov     [rsp+180h+var_160], edx; int
0x18000dfdb  mov     rdx, qword ptr [rbp+80h+var_D8]; int
0x18000dfdf  call    ?GenerateProgIdAndAcidForExtension@ProgId@DataType@StateRepository@@YAJPEBG00W4RuntimeBehavior@3@W4SRTrustLevel@3@00000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z; StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18000dfe4  mov     rbx, [rsp+180h+Block]
0x18000dfe9  test    eax, eax
0x18000dfeb  jns     short loc_18000E00A
0x18000dfed  mov     rcx, [rbp+88h]; this
0x18000dff4  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000dffb  mov     r9d, eax; char *
0x18000dffe  mov     edx, 34h ; '4'; void *
0x18000e003  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e008  jmp     short loc_18000E023
0x18000e00a  mov     rcx, [rbp+80h+arg_20]
0x18000e011  lea     r9, [rsp+180h+var_110]
0x18000e016  mov     r8, rsi
0x18000e019  mov     qword ptr [rsp+180h+var_160], rbx; int
0x18000e01e  call    _lambda_f132b2096735b993c1b4fff6ab29717b___operator__
0x18000e023  lea     r9, [rbp+80h+arg_10]; bool *
0x18000e02a  mov     rcx, rsi; struct StateRepository::Database *
0x18000e02d  lea     r8, [rsp+180h+var_110]; struct StateRepository::Entity::Migrator::Deployment::FixProgIdInfo *
0x18000e032  lea     rdx, [rbp+80h+arg_0]; struct StateRepository::Statement *
0x18000e039  call    ?FindNext@FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@SAJAEAVDatabase@5@AEAVStatement@5@AEAV12345@AEA_N@Z; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::FindNext(StateRepository::Database &,StateRepository::Statement &,StateRepository::Entity::Migrator::Deployment::FixProgIdInfo &,bool &)
0x18000e03e  mov     edi, eax
0x18000e040  test    eax, eax
0x18000e042  js      short loc_18000E06B
0x18000e044  test    rbx, rbx
0x18000e047  jz      short loc_18000E051
0x18000e049  mov     rcx, rbx; Block
0x18000e04c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e051  mov     rcx, [rbp+80h+arg_18]; Block
0x18000e058  test    rcx, rcx
0x18000e05b  jz      loc_18000DF50
0x18000e061  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e066  jmp     loc_18000DF50
0x18000e06b  mov     rcx, [rbp+88h]; this
0x18000e072  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18000e079  mov     r9d, edi; char *
0x18000e07c  mov     edx, 3Ah ; ':'; void *
0x18000e081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e086  test    rbx, rbx
0x18000e089  jz      short loc_18000E093
0x18000e08b  mov     rcx, rbx; Block
0x18000e08e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e093  mov     rcx, [rbp+80h+arg_18]; Block
0x18000e09a  test    rcx, rcx
0x18000e09d  jz      short loc_18000E0A4
0x18000e09f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e0a4  mov     ebx, edi
0x18000e0a6  jmp     short loc_18000E0AA
0x18000e0a8  xor     ebx, ebx
0x18000e0aa  lea     rcx, [rbp+80h+arg_0]; this
0x18000e0b1  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000e0b6  lea     rcx, [rsp+180h+var_110]; this
0x18000e0bb  call    ??1FixProgIdInfo@Deployment@Migrator@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Migrator::Deployment::FixProgIdInfo::~FixProgIdInfo(void)
0x18000e0c0  mov     eax, ebx
0x18000e0c2  mov     rbx, [rsp+180h+arg_8]
0x18000e0ca  add     rsp, 170h
0x18000e0d1  pop     rdi
0x18000e0d2  pop     rsi
0x18000e0d3  pop     rbp
0x18000e0d4  retn
```
