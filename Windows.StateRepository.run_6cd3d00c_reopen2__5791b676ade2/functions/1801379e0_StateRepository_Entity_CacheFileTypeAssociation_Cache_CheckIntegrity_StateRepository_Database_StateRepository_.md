# StateRepository::Entity::CacheFileTypeAssociation::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1801379e0`
- end: `0x180137e91`
- name: `?Cache_CheckIntegrity@CacheFileTypeAssociation@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
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
- `0x1800936b0`
- `0x1800a5df0`
- `0x1800ae890`
- `0x1800e62b8`
- `0x1801379e0`
- `0x18026544c`
- `0x18026f69c`
- `0x18026f8e8`
- `0x18026f9b0`
- `0x18026fa90`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180137c99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180137de4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180137e12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180137c99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180137de4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180137e12`

## string_xrefs

- `0x180137a57`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137aa5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137bbd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137c76`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137cd6`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137d97`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137db4`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137e6e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachefiletypeassociation.cpp`
- `0x180137c5e`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-FileTypeAssociation.hpp`
- `0x180137c01`: `CacheFileTypeAssociation`
- `0x180137e2a`: `CacheFileTypeAssociation`
- `0x180137d15`: `SELECT EXISTS(SELECT 1 FROM CacheFileTypeAssociation WHERE _CacheFileTypeAssociationID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheFileTypeAssociation::Cache_CheckIntegrity(
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
  v8 = StateRepository::Entity::CacheFileTypeAssociation::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
  Next = StateRepository::Entity::CacheFileTypeAssociation::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CacheFileTypeAssociation *)v45,
           &v52);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
    appended = StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Get(v4, v45[0], v11, v49);
    if ( appended < 0 )
    {
      v19 = 590;
      goto LABEL_27;
    }
    if ( v52 )
    {
      v48 = 0;
      appended = StateRepository::Entity::CacheFileTypeAssociation::Cache_Check(
                   (const struct StateRepository::Entity::CacheFileTypeAssociation *)v45,
                   (const struct StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v49,
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
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
    appended = StateRepository::Entity::CacheFileTypeAssociation::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CacheFileTypeAssociation *)v45,
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
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheFileTypeAssociation",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation((StateRepository::Entity::CacheFileTypeAssociation *)v45);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow *)&v39,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-FileTypeAssociation.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
  v25 = StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow::Get(&v39, v22, v45, &v52);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheFileTypeAssociation WHERE _CacheFileTyp"
                                                "eAssociationID=? LIMIT 1);",
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
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachefiletypeassociation.cpp",
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
    v30 = StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow::Get(&v39, v28, v45, &v52);
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
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheFileTypeAssociation",
      v26,
      *(__int64 *)v43);
  *v54 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x1801379e0  mov     [rsp-8+arg_18], r9
0x1801379e5  mov     [rsp-8+arg_8], rdx
0x1801379ea  push    rbp
0x1801379eb  push    rbx
0x1801379ec  push    rsi
0x1801379ed  push    rdi
0x1801379ee  push    r12
0x1801379f0  push    r14
0x1801379f2  push    r15
0x1801379f4  lea     rbp, [rsp-27h]
0x1801379f9  sub     rsp, 0F0h
0x180137a00  xor     r15d, r15d
0x180137a03  mov     rsi, rdx
0x180137a06  mov     r12, rcx
0x180137a09  cmp     [rcx], r15
0x180137a0c  jz      loc_180137E60
0x180137a12  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180137a17  test    al, al
0x180137a19  jz      short loc_180137A2A
0x180137a1b  mov     ebx, 8067000Bh
0x180137a20  mov     edx, 23Ah
0x180137a25  jmp     loc_180137E6A
0x180137a2a  cmp     [rsi], r15
0x180137a2d  jz      loc_180137E59
0x180137a33  lea     rdx, [rsp+120h+var_D8]; struct StateRepository::Statement *
0x180137a38  mov     qword ptr [rbp+57h+var_D0], r15
0x180137a3c  mov     rcx, r12; struct StateRepository::Database *
0x180137a3f  mov     [rbp+57h+var_C8], r15
0x180137a43  mov     [rsp+120h+var_D8], r15
0x180137a48  call    ?Find@CacheFileTypeAssociation@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheFileTypeAssociation::Find(StateRepository::Database &,StateRepository::Statement &)
0x180137a4d  mov     ebx, eax
0x180137a4f  test    eax, eax
0x180137a51  jns     short loc_180137A70
0x180137a53  mov     rcx, [rbp+5Fh]; this
0x180137a57  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137a5e  mov     r9d, eax; char *
0x180137a61  mov     edx, 246h; void *
0x180137a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137a6b  jmp     loc_180137BE0
0x180137a70  xorps   xmm0, xmm0
0x180137a73  mov     [rbp+57h+arg_0], r15b
0x180137a77  xorps   xmm1, xmm1
0x180137a7a  lea     r8, [rbp+57h+arg_0]; bool *
0x180137a7e  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheFileTypeAssociation *
0x180137a82  lea     rcx, [rsp+120h+var_D8]; this
0x180137a87  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180137a8c  movdqu  [rbp+57h+var_B0], xmm1
0x180137a91  movdqu  [rbp+57h+var_A0], xmm0
0x180137a96  call    ?FindNext@CacheFileTypeAssociation@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheFileTypeAssociation::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheFileTypeAssociation &,bool &)
0x180137a9b  mov     ebx, eax
0x180137a9d  test    eax, eax
0x180137a9f  jns     short loc_180137AC7
0x180137aa1  mov     rcx, [rbp+5Fh]; this
0x180137aa5  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137aac  mov     r9d, eax; char *
0x180137aaf  mov     edx, 249h; void *
0x180137ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137ab9  lea     rcx, [rbp+57h+var_C0]; this
0x180137abd  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x180137ac2  jmp     loc_180137BE0
0x180137ac7  mov     rbx, r15
0x180137aca  mov     rdi, r15
0x180137acd  mov     r14, r15
0x180137ad0  cmp     [rbp+57h+arg_0], r15b
0x180137ad4  jz      loc_180137BEF
0x180137ada  mov     rdx, [rbp+57h+var_C0]
0x180137ade  lea     rax, [rbp+57h+arg_0]
0x180137ae2  xorps   xmm0, xmm0
0x180137ae5  mov     [rsp+120h+var_100], rax; int
0x180137aea  xorps   xmm1, xmm1
0x180137aed  lea     r9, [rbp+57h+var_88]
0x180137af1  mov     rcx, rsi
0x180137af4  movdqu  [rbp+57h+var_88], xmm0
0x180137af9  movdqu  [rbp+57h+var_78], xmm1
0x180137afe  call    ?Get@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x180137b03  mov     esi, eax
0x180137b05  test    eax, eax
0x180137b07  js      loc_180137BB4
0x180137b0d  cmp     [rbp+57h+arg_0], r15b
0x180137b11  jz      short loc_180137B55
0x180137b13  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x180137b17  mov     [rbp+57h+var_90], r15
0x180137b1b  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *
0x180137b1f  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheFileTypeAssociation *
0x180137b23  call    ?Cache_Check@CacheFileTypeAssociation@Entity@StateRepository@@CAJAEBV123@AEBVFileTypeAssociation_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheFileTypeAssociation::Cache_Check(StateRepository::Entity::CacheFileTypeAssociation const &,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow const &,unsigned __int64 &)
0x180137b28  mov     esi, eax
0x180137b2a  test    eax, eax
0x180137b2c  js      short loc_180137B9F
0x180137b2e  mov     r15, [rbp+57h+var_90]
0x180137b32  test    r15, r15
0x180137b35  jz      short loc_180137B4D
0x180137b37  mov     rdx, [rbp+57h+var_C0]; __int64
0x180137b3b  lea     rcx, [rbp+57h+var_D0]; this
0x180137b3f  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180137b44  mov     esi, eax
0x180137b46  test    eax, eax
0x180137b48  js      short loc_180137B98
0x180137b4a  add     rbx, r15
0x180137b4d  inc     r14
0x180137b50  xor     r15d, r15d
0x180137b53  jmp     short loc_180137B6B
0x180137b55  mov     rdx, [rbp+57h+var_C0]; __int64
0x180137b59  lea     rcx, [rbp+57h+var_D0]; this
0x180137b5d  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180137b62  mov     esi, eax
0x180137b64  test    eax, eax
0x180137b66  js      short loc_180137BAD
0x180137b68  inc     rbx
0x180137b6b  lea     r8, [rbp+57h+arg_0]; bool *
0x180137b6f  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheFileTypeAssociation *
0x180137b73  lea     rcx, [rsp+120h+var_D8]; this
0x180137b78  call    ?FindNext@CacheFileTypeAssociation@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheFileTypeAssociation::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheFileTypeAssociation &,bool &)
0x180137b7d  mov     esi, eax
0x180137b7f  test    eax, eax
0x180137b81  js      short loc_180137BA6
0x180137b83  inc     rdi
0x180137b86  lea     rcx, [rbp+57h+var_88]; this
0x180137b8a  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x180137b8f  mov     rsi, [rbp+57h+arg_8]
0x180137b93  jmp     loc_180137AD0
0x180137b98  mov     edx, 257h
0x180137b9d  jmp     short loc_180137BB9
0x180137b9f  mov     edx, 253h
0x180137ba4  jmp     short loc_180137BB9
0x180137ba6  mov     edx, 25Fh
0x180137bab  jmp     short loc_180137BB9
0x180137bad  mov     edx, 25Dh
0x180137bb2  jmp     short loc_180137BB9
0x180137bb4  mov     edx, 24Eh; void *
0x180137bb9  mov     rcx, [rbp+5Fh]; this
0x180137bbd  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137bc4  mov     r9d, esi; char *
0x180137bc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137bcc  lea     rcx, [rbp+57h+var_88]; this
0x180137bd0  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x180137bd5  lea     rcx, [rbp+57h+var_C0]; this
0x180137bd9  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x180137bde  mov     ebx, esi
0x180137be0  lea     rcx, [rsp+120h+var_D8]; this
0x180137be5  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180137bea  jmp     loc_180137DEC
0x180137bef  sub     rdi, r14
0x180137bf2  jz      short loc_180137C1C
0x180137bf4  test    cs:byte_1804DF881, 20h
0x180137bfb  jz      short loc_180137C1C
0x180137bfd  mov     rax, qword ptr [rbp+57h+var_D0]
0x180137c01  lea     r8, aCachefiletypea; "CacheFileTypeAssociation"
0x180137c08  mov     r9, rdi
0x180137c0b  mov     [rsp+120h+var_100], rax; int
0x180137c10  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180137c17  call    McTemplateU0sxs_EventWriteTransfer
0x180137c1c  lea     rcx, [rbp+57h+var_C0]; this
0x180137c20  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x180137c25  lea     rcx, [rsp+120h+var_D8]; this
0x180137c2a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180137c2f  lea     rcx, [rbp+57h+var_D0]; this
0x180137c33  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180137c38  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180137c3b  mov     [rsp+120h+var_F0], r15
0x180137c40  lea     rcx, [rsp+120h+var_F0]; this
0x180137c45  mov     [rsp+120h+var_E8], r15d
0x180137c4a  mov     [rsp+120h+var_E0], r15
0x180137c4f  call    ?Open@FileTypeAssociationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180137c54  mov     edi, eax
0x180137c56  test    eax, eax
0x180137c58  jns     short loc_180137CA6
0x180137c5a  mov     rcx, [rbp+5Fh]; this
0x180137c5e  lea     r8, aOnecoreBaseApp_287; "onecore\\base\\appmodel\\StateRepositor"...
0x180137c65  mov     r9d, eax; char *
0x180137c68  mov     edx, 323h; void *
0x180137c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137c72  mov     rcx, [rbp+5Fh]; this
0x180137c76  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137c7d  mov     r9d, edi; char *
0x180137c80  mov     edx, 270h; void *
0x180137c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137c8a  mov     rcx, [rsp+120h+var_F0]
0x180137c8f  mov     [rsp+120h+var_F0], r15
0x180137c94  test    rcx, rcx
0x180137c97  jz      short loc_180137C9F
0x180137c99  call    cs:__imp_SRCacheContext_Close
0x180137c9f  mov     ebx, edi
0x180137ca1  jmp     loc_180137DEC
0x180137ca6  xorps   xmm0, xmm0
0x180137ca9  mov     [rbp+57h+arg_0], r15b
0x180137cad  xorps   xmm1, xmm1
0x180137cb0  lea     r9, [rbp+57h+arg_0]
0x180137cb4  lea     r8, [rbp+57h+var_C0]
0x180137cb8  lea     rcx, [rsp+120h+var_F0]
0x180137cbd  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180137cc2  movdqu  [rbp+57h+var_B0], xmm1
0x180137cc7  call    ?Get@FileTypeAssociationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@FileTypeAssociation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow::Get(StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x180137ccc  mov     edi, eax
0x180137cce  test    eax, eax
0x180137cd0  jns     short loc_180137CF5
0x180137cd2  mov     rcx, [rbp+5Fh]; this
0x180137cd6  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137cdd  mov     r9d, eax; char *
0x180137ce0  mov     edx, 273h; void *
0x180137ce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137cea  lea     rcx, [rbp+57h+var_C0]; this
0x180137cee  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x180137cf3  jmp     short loc_180137C8A
0x180137cf5  mov     rdi, r15
0x180137cf8  cmp     [rbp+57h+arg_0], r15b
0x180137cfc  jz      loc_180137DFA
0x180137d02  mov     r9, [rbp+57h+var_C0]; char *
0x180137d06  lea     rax, [rbp+57h+arg_0]
0x180137d0a  xorps   xmm0, xmm0
0x180137d0d  mov     [rsp+120h+var_100], rax; int
0x180137d12  xorps   xmm1, xmm1
0x180137d15  lea     rdx, aSelectExistsSe_613; "SELECT EXISTS(SELECT 1 FROM CacheFileTy"...
0x180137d1c  xor     r8d, r8d; char *
0x180137d1f  mov     rcx, r12; this
0x180137d22  movdqu  [rbp+57h+var_68], xmm0
0x180137d27  movdqu  [rbp+57h+var_58], xmm1
0x180137d2c  movdqu  [rbp+57h+var_48], xmm0
0x180137d31  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180137d36  mov     esi, eax
0x180137d38  test    eax, eax
0x180137d3a  js      short loc_180137D93
0x180137d3c  cmp     [rbp+57h+arg_0], r15b
0x180137d40  jnz     short loc_180137D5B
0x180137d42  mov     rdx, [rbp+57h+var_C0]; __int64
0x180137d46  lea     rcx, [rbp+57h+var_D0]; this
0x180137d4a  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180137d4f  mov     esi, eax
0x180137d51  test    eax, eax
0x180137d53  js      short loc_180137D85
0x180137d55  inc     rdi
0x180137d58  inc     rbx
0x180137d5b  inc     [rsp+120h+var_E8]
0x180137d5f  lea     r9, [rbp+57h+arg_0]
0x180137d63  lea     r8, [rbp+57h+var_C0]
0x180137d67  lea     rcx, [rsp+120h+var_F0]
0x180137d6c  call    ?Get@FileTypeAssociationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@FileTypeAssociation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociationIterator_NoThrow::Get(StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x180137d71  mov     esi, eax
0x180137d73  test    eax, eax
0x180137d75  js      short loc_180137D8C
0x180137d77  lea     rcx, [rbp+57h+var_68]; this
0x180137d7b  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x180137d80  jmp     loc_180137CF8
0x180137d85  mov     edx, 27Ch
0x180137d8a  jmp     short loc_180137DB0
0x180137d8c  mov     edx, 27Eh
0x180137d91  jmp     short loc_180137DB0
0x180137d93  mov     rcx, [rbp+5Fh]; this
0x180137d97  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137d9e  mov     r9d, esi; char *
0x180137da1  mov     edx, 5Dh ; ']'; void *
0x180137da6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137dab  mov     edx, 277h; void *
0x180137db0  mov     rcx, [rbp+5Fh]; this
0x180137db4  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137dbb  mov     r9d, esi; char *
0x180137dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137dc3  lea     rcx, [rbp+57h+var_68]; this
0x180137dc7  call    ??1CacheFileTypeAssociation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheFileTypeAssociation::~CacheFileTypeAssociation(void)
0x180137dcc  lea     rcx, [rbp+57h+var_C0]; this
0x180137dd0  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x180137dd5  mov     rcx, [rsp+120h+var_F0]
0x180137dda  mov     [rsp+120h+var_F0], r15
0x180137ddf  test    rcx, rcx
0x180137de2  jz      short loc_180137DEA
0x180137de4  call    cs:__imp_SRCacheContext_Close
0x180137dea  mov     ebx, esi
0x180137dec  lea     rcx, [rbp+57h+var_D0]; this
0x180137df0  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180137df5  jmp     loc_180137E7D
0x180137dfa  lea     rcx, [rbp+57h+var_C0]; this
0x180137dfe  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x180137e03  mov     rcx, [rsp+120h+var_F0]
0x180137e08  mov     [rsp+120h+var_F0], r15
0x180137e0d  test    rcx, rcx
0x180137e10  jz      short loc_180137E18
0x180137e12  call    cs:__imp_SRCacheContext_Close
0x180137e18  test    rdi, rdi
0x180137e1b  jz      short loc_180137E45
0x180137e1d  test    cs:byte_1804DF881, 20h
0x180137e24  jz      short loc_180137E45
0x180137e26  mov     rax, qword ptr [rbp+57h+var_D0]
0x180137e2a  lea     r8, aCachefiletypea; "CacheFileTypeAssociation"
0x180137e31  mov     r9, rdi
0x180137e34  mov     [rsp+120h+var_100], rax
0x180137e39  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x180137e40  call    McTemplateU0sxs_EventWriteTransfer
0x180137e45  mov     rax, [rbp+57h+arg_18]
0x180137e49  lea     rcx, [rbp+57h+var_D0]; this
0x180137e4d  mov     [rax], rbx
0x180137e50  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180137e55  xor     eax, eax
0x180137e57  jmp     short loc_180137E7F
0x180137e59  mov     edx, 23Bh
0x180137e5e  jmp     short loc_180137E65
0x180137e60  mov     edx, 239h; void *
0x180137e65  mov     ebx, 8007139Fh
0x180137e6a  mov     rcx, [rbp+5Fh]; this
0x180137e6e  lea     r8, aOnecoreBaseApp_500; "onecore\\base\\appmodel\\staterepositor"...
0x180137e75  mov     r9d, ebx; char *
0x180137e78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
