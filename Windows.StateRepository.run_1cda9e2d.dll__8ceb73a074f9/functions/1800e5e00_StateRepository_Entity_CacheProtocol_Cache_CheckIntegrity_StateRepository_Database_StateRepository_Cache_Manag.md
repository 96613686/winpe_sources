# StateRepository::Entity::CacheProtocol::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1800e5e00`
- end: `0x1800e62b1`
- name: `?Cache_CheckIntegrity@CacheProtocol@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1201`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x180024398`
- `0x1800337a4`
- `0x180062cd8`
- `0x18009294c`
- `0x18009f634`
- `0x1800ae890`
- `0x1800e5e00`
- `0x1800e62b8`
- `0x18026544c`
- `0x18026fb8c`
- `0x18026fdd8`
- `0x18026fea0`
- `0x18026ff80`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e60b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e6204`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e6232`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e60b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e6204`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e6232`

## string_xrefs

- `0x1800e5e77`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e5ec5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e5fdd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e6096`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e60f6`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e61b7`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e61d4`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e628e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheprotocol.cpp`
- `0x1800e607e`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Protocol.hpp`
- `0x1800e6021`: `CacheProtocol`
- `0x1800e624a`: `CacheProtocol`
- `0x1800e6135`: `SELECT EXISTS(SELECT 1 FROM CacheProtocol WHERE _CacheProtocolID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheProtocol::Cache_CheckIntegrity(
        StateRepository::Database *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        _QWORD *a4)
{
  struct StateRepository::Cache::Manager_NoThrow *v4; // rsi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  int Next; // eax
  int v10; // ecx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  int appended; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // edi
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rdi
  int v27; // eax
  __int64 v28; // rdx
  char v29; // r8
  int v30; // esi
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  bool *v35; // [rsp+20h] [rbp-A9h]
  int v36; // [rsp+20h] [rbp-A9h]
  int v37; // [rsp+20h] [rbp-A9h]
  bool *v38; // [rsp+28h] [rbp-A1h]
  __int64 v39; // [rsp+30h] [rbp-99h] BYREF
  int v40; // [rsp+38h] [rbp-91h]
  __int64 v41; // [rsp+40h] [rbp-89h]
  __int64 v42; // [rsp+48h] [rbp-81h] BYREF
  int v43[2]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v44; // [rsp+58h] [rbp-71h]
  char *v45[2]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v46; // [rsp+70h] [rbp-59h]
  __int128 v47; // [rsp+80h] [rbp-49h]
  unsigned __int64 v48; // [rsp+90h] [rbp-39h] BYREF
  _OWORD v49[2]; // [rsp+98h] [rbp-31h] BYREF
  _OWORD v50[6]; // [rsp+B8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  bool v52; // [rsp+130h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v53; // [rsp+138h] [rbp+6Fh]
  _QWORD *v54; // [rsp+148h] [rbp+7Fh]

  v54 = a4;
  v53 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 569;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 570;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
      (const char *)v6,
      (int)v35);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 571;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v43 = 0;
  v44 = 0;
  v42 = 0;
  v8 = StateRepository::Entity::CacheProtocol::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v43);
    return v6;
  }
  v52 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v47 = 0;
  Next = StateRepository::Entity::CacheProtocol::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CacheProtocol *)v45,
           &v52);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
      (const char *)(unsigned int)Next,
      (int)v35);
    StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation((StateRepository::Entity::CacheFileTypeAssociation *)v45);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v52 )
  {
    v35 = &v52;
    memset(v49, 0, sizeof(v49));
    appended = StateRepository::Cache::Entity::Protocol_NoThrow::Get(v4, v45[0], v11, v49);
    if ( appended < 0 )
    {
      v19 = 590;
      goto LABEL_27;
    }
    if ( v52 )
    {
      v48 = 0;
      appended = StateRepository::Entity::CacheProtocol::Cache_Check(
                   (const struct StateRepository::Entity::CacheProtocol *)v45,
                   (const struct StateRepository::Cache::Entity::Protocol_NoThrow *)v49,
                   &v48);
      if ( appended < 0 )
      {
        v19 = 595;
        goto LABEL_27;
      }
      v18 = v48;
      if ( v48 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v17);
        if ( appended < 0 )
        {
          v19 = 599;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
            (const char *)(unsigned int)appended,
            (int)&v52);
          StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v49);
          StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation((StateRepository::Entity::CacheFileTypeAssociation *)v45);
          v6 = appended;
          goto LABEL_28;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v16);
      if ( appended < 0 )
      {
        v19 = 605;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheProtocol::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CacheProtocol *)v45,
                 &v52);
    if ( appended < 0 )
    {
      v19 = 607;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v49);
    v4 = v53;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)&CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheProtocol",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation((StateRepository::Entity::CacheFileTypeAssociation *)v45);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::ProtocolIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::ProtocolIterator_NoThrow *)&v39,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
      (const char *)v23,
      v36);
LABEL_34:
    v24 = v39;
    v39 = 0;
    if ( v24 )
      SRCacheContext_Close(v24);
    v6 = v23;
    goto LABEL_53;
  }
  v52 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v25 = StateRepository::Cache::Entity::ProtocolIterator_NoThrow::Get(&v39, v22, v45, &v52);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
      (const char *)(unsigned int)v25,
      (int)v35);
    StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v45);
    goto LABEL_34;
  }
  v26 = 0;
  while ( v52 )
  {
    memset(v50, 0, 48);
    v27 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheProtocol WHERE _CacheProtocolID=? LIMIT 1);",
            0,
            v45[0],
            (__int64)&v52,
            v38);
    v30 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
        (const char *)(unsigned int)v27,
        v37);
      v31 = 631;
      goto LABEL_50;
    }
    if ( !v52 )
    {
      v30 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v29);
      if ( v30 < 0 )
      {
        v31 = 636;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheprotocol.cpp",
          (const char *)(unsigned int)v30,
          v37);
        StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation((StateRepository::Entity::CacheFileTypeAssociation *)v50);
        StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v45);
        v32 = v39;
        v39 = 0;
        if ( v32 )
          SRCacheContext_Close(v32);
        v6 = v30;
        goto LABEL_53;
      }
      ++v26;
      ++v12;
    }
    ++v40;
    v30 = StateRepository::Cache::Entity::ProtocolIterator_NoThrow::Get(&v39, v28, v45, &v52);
    if ( v30 < 0 )
    {
      v31 = 638;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation((StateRepository::Entity::CacheFileTypeAssociation *)v50);
  }
  StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v45);
  v33 = v39;
  v39 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  if ( v26 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v33,
      (unsigned int)&CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheProtocol",
      v26,
      *(__int64 *)v43);
  *v54 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x1800e5e00  mov     [rsp-8+arg_18], r9
0x1800e5e05  mov     [rsp-8+arg_8], rdx
0x1800e5e0a  push    rbp
0x1800e5e0b  push    rbx
0x1800e5e0c  push    rsi
0x1800e5e0d  push    rdi
0x1800e5e0e  push    r12
0x1800e5e10  push    r14
0x1800e5e12  push    r15
0x1800e5e14  lea     rbp, [rsp-27h]
0x1800e5e19  sub     rsp, 0F0h
0x1800e5e20  xor     r15d, r15d
0x1800e5e23  mov     rsi, rdx
0x1800e5e26  mov     r12, rcx
0x1800e5e29  cmp     [rcx], r15
0x1800e5e2c  jz      loc_1800E6280
0x1800e5e32  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800e5e37  test    al, al
0x1800e5e39  jz      short loc_1800E5E4A
0x1800e5e3b  mov     ebx, 8067000Bh
0x1800e5e40  mov     edx, 23Ah
0x1800e5e45  jmp     loc_1800E628A
0x1800e5e4a  cmp     [rsi], r15
0x1800e5e4d  jz      loc_1800E6279
0x1800e5e53  lea     rdx, [rsp+120h+var_D8]; struct StateRepository::Statement *
0x1800e5e58  mov     qword ptr [rbp+57h+var_D0], r15
0x1800e5e5c  mov     rcx, r12; struct StateRepository::Database *
0x1800e5e5f  mov     [rbp+57h+var_C8], r15
0x1800e5e63  mov     [rsp+120h+var_D8], r15
0x1800e5e68  call    ?Find@CacheProtocol@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheProtocol::Find(StateRepository::Database &,StateRepository::Statement &)
0x1800e5e6d  mov     ebx, eax
0x1800e5e6f  test    eax, eax
0x1800e5e71  jns     short loc_1800E5E90
0x1800e5e73  mov     rcx, [rbp+5Fh]; this
0x1800e5e77  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e5e7e  mov     r9d, eax; char *
0x1800e5e81  mov     edx, 246h; void *
0x1800e5e86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5e8b  jmp     loc_1800E6000
0x1800e5e90  xorps   xmm0, xmm0
0x1800e5e93  mov     [rbp+57h+arg_0], r15b
0x1800e5e97  xorps   xmm1, xmm1
0x1800e5e9a  lea     r8, [rbp+57h+arg_0]; bool *
0x1800e5e9e  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheProtocol *
0x1800e5ea2  lea     rcx, [rsp+120h+var_D8]; this
0x1800e5ea7  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800e5eac  movdqu  [rbp+57h+var_B0], xmm1
0x1800e5eb1  movdqu  [rbp+57h+var_A0], xmm0
0x1800e5eb6  call    ?FindNext@CacheProtocol@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheProtocol::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheProtocol &,bool &)
0x1800e5ebb  mov     ebx, eax
0x1800e5ebd  test    eax, eax
0x1800e5ebf  jns     short loc_1800E5EE7
0x1800e5ec1  mov     rcx, [rbp+5Fh]; this
0x1800e5ec5  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e5ecc  mov     r9d, eax; char *
0x1800e5ecf  mov     edx, 249h; void *
0x1800e5ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5ed9  lea     rcx, [rbp+57h+var_C0]; this
0x1800e5edd  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x1800e5ee2  jmp     loc_1800E6000
0x1800e5ee7  mov     rbx, r15
0x1800e5eea  mov     rdi, r15
0x1800e5eed  mov     r14, r15
0x1800e5ef0  cmp     [rbp+57h+arg_0], r15b
0x1800e5ef4  jz      loc_1800E600F
0x1800e5efa  mov     rdx, [rbp+57h+var_C0]
0x1800e5efe  lea     rax, [rbp+57h+arg_0]
0x1800e5f02  xorps   xmm0, xmm0
0x1800e5f05  mov     [rsp+120h+var_100], rax; int
0x1800e5f0a  xorps   xmm1, xmm1
0x1800e5f0d  lea     r9, [rbp+57h+var_88]
0x1800e5f11  mov     rcx, rsi
0x1800e5f14  movdqu  [rbp+57h+var_88], xmm0
0x1800e5f19  movdqu  [rbp+57h+var_78], xmm1
0x1800e5f1e  call    ?Get@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Protocol_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800e5f23  mov     esi, eax
0x1800e5f25  test    eax, eax
0x1800e5f27  js      loc_1800E5FD4
0x1800e5f2d  cmp     [rbp+57h+arg_0], r15b
0x1800e5f31  jz      short loc_1800E5F75
0x1800e5f33  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x1800e5f37  mov     [rbp+57h+var_90], r15
0x1800e5f3b  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Cache::Entity::Protocol_NoThrow *
0x1800e5f3f  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheProtocol *
0x1800e5f43  call    ?Cache_Check@CacheProtocol@Entity@StateRepository@@CAJAEBV123@AEBVProtocol_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheProtocol::Cache_Check(StateRepository::Entity::CacheProtocol const &,StateRepository::Cache::Entity::Protocol_NoThrow const &,unsigned __int64 &)
0x1800e5f48  mov     esi, eax
0x1800e5f4a  test    eax, eax
0x1800e5f4c  js      short loc_1800E5FBF
0x1800e5f4e  mov     r15, [rbp+57h+var_90]
0x1800e5f52  test    r15, r15
0x1800e5f55  jz      short loc_1800E5F6D
0x1800e5f57  mov     rdx, [rbp+57h+var_C0]; __int64
0x1800e5f5b  lea     rcx, [rbp+57h+var_D0]; this
0x1800e5f5f  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800e5f64  mov     esi, eax
0x1800e5f66  test    eax, eax
0x1800e5f68  js      short loc_1800E5FB8
0x1800e5f6a  add     rbx, r15
0x1800e5f6d  inc     r14
0x1800e5f70  xor     r15d, r15d
0x1800e5f73  jmp     short loc_1800E5F8B
0x1800e5f75  mov     rdx, [rbp+57h+var_C0]; __int64
0x1800e5f79  lea     rcx, [rbp+57h+var_D0]; this
0x1800e5f7d  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800e5f82  mov     esi, eax
0x1800e5f84  test    eax, eax
0x1800e5f86  js      short loc_1800E5FCD
0x1800e5f88  inc     rbx
0x1800e5f8b  lea     r8, [rbp+57h+arg_0]; bool *
0x1800e5f8f  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheProtocol *
0x1800e5f93  lea     rcx, [rsp+120h+var_D8]; this
0x1800e5f98  call    ?FindNext@CacheProtocol@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheProtocol::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheProtocol &,bool &)
0x1800e5f9d  mov     esi, eax
0x1800e5f9f  test    eax, eax
0x1800e5fa1  js      short loc_1800E5FC6
0x1800e5fa3  inc     rdi
0x1800e5fa6  lea     rcx, [rbp+57h+var_88]; this
0x1800e5faa  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x1800e5faf  mov     rsi, [rbp+57h+arg_8]
0x1800e5fb3  jmp     loc_1800E5EF0
0x1800e5fb8  mov     edx, 257h
0x1800e5fbd  jmp     short loc_1800E5FD9
0x1800e5fbf  mov     edx, 253h
0x1800e5fc4  jmp     short loc_1800E5FD9
0x1800e5fc6  mov     edx, 25Fh
0x1800e5fcb  jmp     short loc_1800E5FD9
0x1800e5fcd  mov     edx, 25Dh
0x1800e5fd2  jmp     short loc_1800E5FD9
0x1800e5fd4  mov     edx, 24Eh; void *
0x1800e5fd9  mov     rcx, [rbp+5Fh]; this
0x1800e5fdd  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e5fe4  mov     r9d, esi; char *
0x1800e5fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5fec  lea     rcx, [rbp+57h+var_88]; this
0x1800e5ff0  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x1800e5ff5  lea     rcx, [rbp+57h+var_C0]; this
0x1800e5ff9  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x1800e5ffe  mov     ebx, esi
0x1800e6000  lea     rcx, [rsp+120h+var_D8]; this
0x1800e6005  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800e600a  jmp     loc_1800E620C
0x1800e600f  sub     rdi, r14
0x1800e6012  jz      short loc_1800E603C
0x1800e6014  test    cs:byte_1804DF881, 20h
0x1800e601b  jz      short loc_1800E603C
0x1800e601d  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800e6021  lea     r8, aCacheprotocol; "CacheProtocol"
0x1800e6028  mov     r9, rdi
0x1800e602b  mov     [rsp+120h+var_100], rax; int
0x1800e6030  lea     rdx, CacheIntegrity_MissingCacheEntries
0x1800e6037  call    McTemplateU0sxs_EventWriteTransfer
0x1800e603c  lea     rcx, [rbp+57h+var_C0]; this
0x1800e6040  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x1800e6045  lea     rcx, [rsp+120h+var_D8]; this
0x1800e604a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800e604f  lea     rcx, [rbp+57h+var_D0]; this
0x1800e6053  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x1800e6058  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800e605b  mov     [rsp+120h+var_F0], r15
0x1800e6060  lea     rcx, [rsp+120h+var_F0]; this
0x1800e6065  mov     [rsp+120h+var_E8], r15d
0x1800e606a  mov     [rsp+120h+var_E0], r15
0x1800e606f  call    ?Open@ProtocolIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::ProtocolIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x1800e6074  mov     edi, eax
0x1800e6076  test    eax, eax
0x1800e6078  jns     short loc_1800E60C6
0x1800e607a  mov     rcx, [rbp+5Fh]; this
0x1800e607e  lea     r8, aOnecoreBaseApp_166; "onecore\\base\\appmodel\\StateRepositor"...
0x1800e6085  mov     r9d, eax; char *
0x1800e6088  mov     edx, 323h; void *
0x1800e608d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6092  mov     rcx, [rbp+5Fh]; this
0x1800e6096  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e609d  mov     r9d, edi; char *
0x1800e60a0  mov     edx, 270h; void *
0x1800e60a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e60aa  mov     rcx, [rsp+120h+var_F0]
0x1800e60af  mov     [rsp+120h+var_F0], r15
0x1800e60b4  test    rcx, rcx
0x1800e60b7  jz      short loc_1800E60BF
0x1800e60b9  call    cs:__imp_SRCacheContext_Close
0x1800e60bf  mov     ebx, edi
0x1800e60c1  jmp     loc_1800E620C
0x1800e60c6  xorps   xmm0, xmm0
0x1800e60c9  mov     [rbp+57h+arg_0], r15b
0x1800e60cd  xorps   xmm1, xmm1
0x1800e60d0  lea     r9, [rbp+57h+arg_0]
0x1800e60d4  lea     r8, [rbp+57h+var_C0]
0x1800e60d8  lea     rcx, [rsp+120h+var_F0]
0x1800e60dd  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800e60e2  movdqu  [rbp+57h+var_B0], xmm1
0x1800e60e7  call    ?Get@ProtocolIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800e60ec  mov     edi, eax
0x1800e60ee  test    eax, eax
0x1800e60f0  jns     short loc_1800E6115
0x1800e60f2  mov     rcx, [rbp+5Fh]; this
0x1800e60f6  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e60fd  mov     r9d, eax; char *
0x1800e6100  mov     edx, 273h; void *
0x1800e6105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e610a  lea     rcx, [rbp+57h+var_C0]; this
0x1800e610e  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x1800e6113  jmp     short loc_1800E60AA
0x1800e6115  mov     rdi, r15
0x1800e6118  cmp     [rbp+57h+arg_0], r15b
0x1800e611c  jz      loc_1800E621A
0x1800e6122  mov     r9, [rbp+57h+var_C0]; char *
0x1800e6126  lea     rax, [rbp+57h+arg_0]
0x1800e612a  xorps   xmm0, xmm0
0x1800e612d  mov     [rsp+120h+var_100], rax; int
0x1800e6132  xorps   xmm1, xmm1
0x1800e6135  lea     rdx, aSelectExistsSe_495; "SELECT EXISTS(SELECT 1 FROM CacheProtoc"...
0x1800e613c  xor     r8d, r8d; char *
0x1800e613f  mov     rcx, r12; this
0x1800e6142  movdqu  [rbp+57h+var_68], xmm0
0x1800e6147  movdqu  [rbp+57h+var_58], xmm1
0x1800e614c  movdqu  [rbp+57h+var_48], xmm0
0x1800e6151  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x1800e6156  mov     esi, eax
0x1800e6158  test    eax, eax
0x1800e615a  js      short loc_1800E61B3
0x1800e615c  cmp     [rbp+57h+arg_0], r15b
0x1800e6160  jnz     short loc_1800E617B
0x1800e6162  mov     rdx, [rbp+57h+var_C0]; __int64
0x1800e6166  lea     rcx, [rbp+57h+var_D0]; this
0x1800e616a  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800e616f  mov     esi, eax
0x1800e6171  test    eax, eax
0x1800e6173  js      short loc_1800E61A5
0x1800e6175  inc     rdi
0x1800e6178  inc     rbx
0x1800e617b  inc     [rsp+120h+var_E8]
0x1800e617f  lea     r9, [rbp+57h+arg_0]
0x1800e6183  lea     r8, [rbp+57h+var_C0]
0x1800e6187  lea     rcx, [rsp+120h+var_F0]
0x1800e618c  call    ?Get@ProtocolIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800e6191  mov     esi, eax
0x1800e6193  test    eax, eax
0x1800e6195  js      short loc_1800E61AC
0x1800e6197  lea     rcx, [rbp+57h+var_68]; this
0x1800e619b  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x1800e61a0  jmp     loc_1800E6118
0x1800e61a5  mov     edx, 27Ch
0x1800e61aa  jmp     short loc_1800E61D0
0x1800e61ac  mov     edx, 27Eh
0x1800e61b1  jmp     short loc_1800E61D0
0x1800e61b3  mov     rcx, [rbp+5Fh]; this
0x1800e61b7  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e61be  mov     r9d, esi; char *
0x1800e61c1  mov     edx, 5Dh ; ']'; void *
0x1800e61c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e61cb  mov     edx, 277h; void *
0x1800e61d0  mov     rcx, [rbp+5Fh]; this
0x1800e61d4  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e61db  mov     r9d, esi; char *
0x1800e61de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e61e3  lea     rcx, [rbp+57h+var_68]; this
0x1800e61e7  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x1800e61ec  lea     rcx, [rbp+57h+var_C0]; this
0x1800e61f0  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x1800e61f5  mov     rcx, [rsp+120h+var_F0]
0x1800e61fa  mov     [rsp+120h+var_F0], r15
0x1800e61ff  test    rcx, rcx
0x1800e6202  jz      short loc_1800E620A
0x1800e6204  call    cs:__imp_SRCacheContext_Close
0x1800e620a  mov     ebx, esi
0x1800e620c  lea     rcx, [rbp+57h+var_D0]; this
0x1800e6210  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800e6215  jmp     loc_1800E629D
0x1800e621a  lea     rcx, [rbp+57h+var_C0]; this
0x1800e621e  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x1800e6223  mov     rcx, [rsp+120h+var_F0]
0x1800e6228  mov     [rsp+120h+var_F0], r15
0x1800e622d  test    rcx, rcx
0x1800e6230  jz      short loc_1800E6238
0x1800e6232  call    cs:__imp_SRCacheContext_Close
0x1800e6238  test    rdi, rdi
0x1800e623b  jz      short loc_1800E6265
0x1800e623d  test    cs:byte_1804DF881, 20h
0x1800e6244  jz      short loc_1800E6265
0x1800e6246  mov     rax, qword ptr [rbp+57h+var_D0]
0x1800e624a  lea     r8, aCacheprotocol; "CacheProtocol"
0x1800e6251  mov     r9, rdi
0x1800e6254  mov     [rsp+120h+var_100], rax
0x1800e6259  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x1800e6260  call    McTemplateU0sxs_EventWriteTransfer
0x1800e6265  mov     rax, [rbp+57h+arg_18]
0x1800e6269  lea     rcx, [rbp+57h+var_D0]; this
0x1800e626d  mov     [rax], rbx
0x1800e6270  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800e6275  xor     eax, eax
0x1800e6277  jmp     short loc_1800E629F
0x1800e6279  mov     edx, 23Bh
0x1800e627e  jmp     short loc_1800E6285
0x1800e6280  mov     edx, 239h; void *
0x1800e6285  mov     ebx, 8007139Fh
0x1800e628a  mov     rcx, [rbp+5Fh]; this
0x1800e628e  lea     r8, aOnecoreBaseApp_455; "onecore\\base\\appmodel\\staterepositor"...
0x1800e6295  mov     r9d, ebx; char *
0x1800e6298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
