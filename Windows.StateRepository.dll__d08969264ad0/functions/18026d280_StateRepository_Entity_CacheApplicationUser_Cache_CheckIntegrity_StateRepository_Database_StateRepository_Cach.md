# StateRepository::Entity::CacheApplicationUser::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18026d280`
- end: `0x18026d7b4`
- name: `?Cache_CheckIntegrity@CacheApplicationUser@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1332`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x180091c60`
- `0x1800a5e50`
- `0x1800ae890`
- `0x18026544c`
- `0x18026d0c8`
- `0x18026d280`
- `0x18026d8d0`
- `0x18026d998`
- `0x18026da78`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026d58b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026d6fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026d733`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026d58b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026d6fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026d733`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d454`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d4bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d5f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d6e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d71e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d454`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d4bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d5f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d6e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026d71e`

## string_xrefs

- `0x18026d2f9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d34e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d463`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d4a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d568`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d5d0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d6a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d6c0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d791`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationuser.cpp`
- `0x18026d550`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-ApplicationUser.hpp`
- `0x18026d4f2`: `CacheApplicationUser`
- `0x18026d74c`: `CacheApplicationUser`
- `0x18026d621`: `SELECT EXISTS(SELECT 1 FROM CacheApplicationUser WHERE _CacheApplicationUserID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheApplicationUser::Cache_CheckIntegrity(
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
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  int v15; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r15
  int appended; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdi
  int v34; // eax
  __int64 v35; // rdx
  char v36; // r8
  int v37; // esi
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  bool *v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  bool *v49; // [rsp+28h] [rbp-D8h]
  __int64 v50; // [rsp+30h] [rbp-D0h] BYREF
  int v51; // [rsp+38h] [rbp-C8h]
  __int64 v52; // [rsp+40h] [rbp-C0h]
  __int64 v53; // [rsp+48h] [rbp-B8h] BYREF
  int v54[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h]
  char *v56[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v57; // [rsp+70h] [rbp-90h]
  __int128 v58; // [rsp+80h] [rbp-80h] BYREF
  __int64 v59; // [rsp+90h] [rbp-70h]
  unsigned __int64 v60; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v61[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v62; // [rsp+C0h] [rbp-40h]
  __int128 v63; // [rsp+D0h] [rbp-30h]
  __int128 v64; // [rsp+E0h] [rbp-20h]
  __int128 v65; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v66; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  bool v68; // [rsp+150h] [rbp+50h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v69; // [rsp+158h] [rbp+58h]
  _QWORD *v70; // [rsp+168h] [rbp+68h]

  v70 = a4;
  v69 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 767;
    goto LABEL_71;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 768;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
      (const char *)v6,
      (int)v46);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 769;
LABEL_71:
    v6 = -2147019873;
    goto LABEL_72;
  }
  *(_QWORD *)v54 = 0;
  v55 = 0;
  v53 = 0;
  v8 = StateRepository::Entity::CacheApplicationUser::Find(a1, (struct StateRepository::Statement *)&v53);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
      (const char *)(unsigned int)v8,
      (int)v46);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v53);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v54);
    return v6;
  }
  v59 = 0;
  v68 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  v58 = 0;
  Next = StateRepository::Entity::CacheApplicationUser::FindNext(
           (struct StateRepository::Statement *)&v53,
           (struct StateRepository::Entity::CacheApplicationUser *)v56,
           &v68);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
      (const char *)(unsigned int)Next,
      (int)v46);
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v58 + 8));
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v68 )
  {
    v46 = &v68;
    memset(v61, 0, sizeof(v61));
    v62 = 0;
    v15 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(v4, v56[0], v11, v61);
    if ( v15 < 0 )
    {
      v21 = 788;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
        (const char *)(unsigned int)v15,
        (int)&v68);
      v20 = *((_QWORD *)&v62 + 1);
      *((_QWORD *)&v62 + 1) = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v58 + 8));
      v6 = v15;
      goto LABEL_32;
    }
    if ( v68 )
    {
      v60 = 0;
      v15 = StateRepository::Entity::CacheApplicationUser::Cache_Check(
              (const struct StateRepository::Entity::CacheApplicationUser *)v56,
              (const struct StateRepository::Cache::Entity::ApplicationUser_NoThrow *)v61,
              &v60);
      if ( v15 < 0 )
      {
        v21 = 793;
        goto LABEL_28;
      }
      v18 = v60;
      if ( v60 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v54, (__int64)v56[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x31D,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
            (const char *)(unsigned int)appended,
            (int)&v68);
          v20 = *((_QWORD *)&v62 + 1);
          *((_QWORD *)&v62 + 1) = 0;
          goto LABEL_29;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      v15 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v54, (__int64)v56[0], v16);
      if ( v15 < 0 )
      {
        v21 = 803;
        goto LABEL_28;
      }
      ++v12;
    }
    v15 = StateRepository::Entity::CacheApplicationUser::FindNext(
            (struct StateRepository::Statement *)&v53,
            (struct StateRepository::Entity::CacheApplicationUser *)v56,
            &v68);
    if ( v15 < 0 )
    {
      v21 = 805;
      goto LABEL_28;
    }
    v10 = *((_QWORD *)&v62 + 1);
    ++v13;
    v4 = v69;
    *((_QWORD *)&v62 + 1) = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheApplicationUser",
      v22,
      *(__int64 *)v54);
  StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v58 + 8));
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v53);
  StateRepository::TextA::Clear((StateRepository::TextA *)v54);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v23 = StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow *)&v50,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v23,
      (int)v46);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
      (const char *)v25,
      v47);
LABEL_38:
    v28 = v50;
    v50 = 0;
    if ( v28 )
      SRCacheContext_Close(v28, v26, v27);
    v6 = v25;
    goto LABEL_60;
  }
  v68 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  v58 = 0;
  v29 = StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow::Get(&v50, v24, v56, &v68);
  v25 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x339,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
    v32 = *((_QWORD *)&v58 + 1);
    *((_QWORD *)&v58 + 1) = 0;
    if ( v32 )
      SRCache_Free(v32);
    goto LABEL_38;
  }
  v33 = 0;
  while ( v68 )
  {
    v66 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v34 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheApplicationUser WHERE _CacheApplication"
                                                "UserID=? LIMIT 1);",
            0,
            v56[0],
            (__int64)&v68,
            v49);
    v37 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
        (const char *)(unsigned int)v34,
        v48);
      v38 = 829;
      goto LABEL_55;
    }
    if ( !v68 )
    {
      v37 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v54, (__int64)v56[0], v36);
      if ( v37 < 0 )
      {
        v38 = 834;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationuser.cpp",
          (const char *)(unsigned int)v37,
          v48);
        StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v65 + 8));
        v41 = *((_QWORD *)&v58 + 1);
        *((_QWORD *)&v58 + 1) = 0;
        if ( v41 )
          SRCache_Free(v41);
        v42 = v50;
        v50 = 0;
        if ( v42 )
          SRCacheContext_Close(v42, v39, v40);
        v6 = v37;
        goto LABEL_60;
      }
      ++v33;
      ++v12;
    }
    ++v51;
    v37 = StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow::Get(&v50, v35, v56, &v68);
    if ( v37 < 0 )
    {
      v38 = 836;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v65 + 8));
  }
  v43 = *((_QWORD *)&v58 + 1);
  *((_QWORD *)&v58 + 1) = 0;
  if ( v43 )
    SRCache_Free(v43);
  v44 = v50;
  v50 = 0;
  if ( v44 )
    SRCacheContext_Close(v44, v30, v31);
  if ( v33 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v44,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheApplicationUser",
      v33,
      *(__int64 *)v54);
  *v70 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v54);
  return 0;
}

```

## disassembly

```asm
0x18026d280  mov     [rsp-8+arg_18], r9
0x18026d285  mov     [rsp-8+arg_8], rdx
0x18026d28a  push    rbp
0x18026d28b  push    rbx
0x18026d28c  push    rsi
0x18026d28d  push    rdi
0x18026d28e  push    r12
0x18026d290  push    r14
0x18026d292  push    r15
0x18026d294  lea     rbp, [rsp-10h]
0x18026d299  sub     rsp, 110h
0x18026d2a0  xor     r15d, r15d
0x18026d2a3  mov     rsi, rdx
0x18026d2a6  mov     r12, rcx
0x18026d2a9  cmp     [rcx], r15
0x18026d2ac  jz      loc_18026D783
0x18026d2b2  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18026d2b7  test    al, al
0x18026d2b9  jz      short loc_18026D2CA
0x18026d2bb  mov     ebx, 8067000Bh
0x18026d2c0  mov     edx, 300h
0x18026d2c5  jmp     loc_18026D78D
0x18026d2ca  cmp     [rsi], r15
0x18026d2cd  jz      loc_18026D77C
0x18026d2d3  lea     rdx, [rsp+140h+var_F8]; struct StateRepository::Statement *
0x18026d2d8  mov     qword ptr [rsp+140h+var_F0], r15
0x18026d2dd  mov     rcx, r12; struct StateRepository::Database *
0x18026d2e0  mov     [rsp+140h+var_E8], r15
0x18026d2e5  mov     [rsp+140h+var_F8], r15
0x18026d2ea  call    ?Find@CacheApplicationUser@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheApplicationUser::Find(StateRepository::Database &,StateRepository::Statement &)
0x18026d2ef  mov     ebx, eax
0x18026d2f1  test    eax, eax
0x18026d2f3  jns     short loc_18026D312
0x18026d2f5  mov     rcx, [rbp+48h]; this
0x18026d2f9  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d300  mov     r9d, eax; char *
0x18026d303  mov     edx, 30Ch; void *
0x18026d308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d30d  jmp     loc_18026D4D0
0x18026d312  xorps   xmm0, xmm0
0x18026d315  mov     [rbp+40h+var_B0], r15
0x18026d319  xorps   xmm1, xmm1
0x18026d31c  mov     [rbp+40h+arg_0], r15b
0x18026d320  lea     r8, [rbp+40h+arg_0]; bool *
0x18026d324  lea     rdx, [rsp+140h+var_E0]; struct StateRepository::Entity::CacheApplicationUser *
0x18026d329  lea     rcx, [rsp+140h+var_F8]; this
0x18026d32e  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18026d334  movdqu  [rsp+140h+var_D0], xmm1
0x18026d33a  movdqu  [rbp+40h+var_C0], xmm0
0x18026d33f  call    ?FindNext@CacheApplicationUser@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheApplicationUser::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheApplicationUser &,bool &)
0x18026d344  mov     ebx, eax
0x18026d346  test    eax, eax
0x18026d348  jns     short loc_18026D370
0x18026d34a  mov     rcx, [rbp+48h]; this
0x18026d34e  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d355  mov     r9d, eax; char *
0x18026d358  mov     edx, 30Fh; void *
0x18026d35d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d362  lea     rcx, [rbp+40h+var_C0+8]; this
0x18026d366  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026d36b  jmp     loc_18026D4D0
0x18026d370  mov     rbx, r15
0x18026d373  mov     rdi, r15
0x18026d376  mov     r14, r15
0x18026d379  cmp     [rbp+40h+arg_0], r15b
0x18026d37d  jz      loc_18026D4DF
0x18026d383  mov     rdx, [rsp+140h+var_E0]
0x18026d388  lea     rax, [rbp+40h+arg_0]
0x18026d38c  xorps   xmm0, xmm0
0x18026d38f  mov     [rsp+140h+var_120], rax; int
0x18026d394  xorps   xmm1, xmm1
0x18026d397  lea     r9, [rbp+40h+var_A0]
0x18026d39b  mov     rcx, rsi
0x18026d39e  movdqu  [rbp+40h+var_A0], xmm0
0x18026d3a3  movdqu  [rbp+40h+var_90], xmm1
0x18026d3a8  movdqu  [rbp+40h+var_80], xmm0
0x18026d3ad  call    ?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x18026d3b2  mov     esi, eax
0x18026d3b4  test    eax, eax
0x18026d3b6  js      loc_18026D49A
0x18026d3bc  cmp     [rbp+40h+arg_0], r15b
0x18026d3c0  jz      short loc_18026D40B
0x18026d3c2  lea     r8, [rbp+40h+var_A8]; unsigned __int64 *
0x18026d3c6  mov     [rbp+40h+var_A8], r15
0x18026d3ca  lea     rdx, [rbp+40h+var_A0]; struct StateRepository::Cache::Entity::ApplicationUser_NoThrow *
0x18026d3ce  lea     rcx, [rsp+140h+var_E0]; struct StateRepository::Entity::CacheApplicationUser *
0x18026d3d3  call    ?Cache_Check@CacheApplicationUser@Entity@StateRepository@@CAJAEBV123@AEBVApplicationUser_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheApplicationUser::Cache_Check(StateRepository::Entity::CacheApplicationUser const &,StateRepository::Cache::Entity::ApplicationUser_NoThrow const &,unsigned __int64 &)
0x18026d3d8  mov     esi, eax
0x18026d3da  test    eax, eax
0x18026d3dc  js      loc_18026D485
0x18026d3e2  mov     r15, [rbp+40h+var_A8]
0x18026d3e6  test    r15, r15
0x18026d3e9  jz      short loc_18026D403
0x18026d3eb  mov     rdx, [rsp+140h+var_E0]; __int64
0x18026d3f0  lea     rcx, [rsp+140h+var_F0]; this
0x18026d3f5  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026d3fa  mov     esi, eax
0x18026d3fc  test    eax, eax
0x18026d3fe  js      short loc_18026D45F
0x18026d400  add     rbx, r15
0x18026d403  inc     r14
0x18026d406  xor     r15d, r15d
0x18026d409  jmp     short loc_18026D423
0x18026d40b  mov     rdx, [rsp+140h+var_E0]; __int64
0x18026d410  lea     rcx, [rsp+140h+var_F0]; this
0x18026d415  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026d41a  mov     esi, eax
0x18026d41c  test    eax, eax
0x18026d41e  js      short loc_18026D493
0x18026d420  inc     rbx
0x18026d423  lea     r8, [rbp+40h+arg_0]; bool *
0x18026d427  lea     rdx, [rsp+140h+var_E0]; struct StateRepository::Entity::CacheApplicationUser *
0x18026d42c  lea     rcx, [rsp+140h+var_F8]; this
0x18026d431  call    ?FindNext@CacheApplicationUser@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheApplicationUser::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheApplicationUser &,bool &)
0x18026d436  mov     esi, eax
0x18026d438  test    eax, eax
0x18026d43a  js      short loc_18026D48C
0x18026d43c  mov     rcx, qword ptr [rbp+40h+var_80+8]
0x18026d440  inc     rdi
0x18026d443  mov     rsi, [rbp+40h+arg_8]
0x18026d447  mov     qword ptr [rbp+40h+var_80+8], r15
0x18026d44b  test    rcx, rcx
0x18026d44e  jz      loc_18026D379
0x18026d454  call    cs:__imp_SRCache_Free
0x18026d45a  jmp     loc_18026D379
0x18026d45f  mov     rcx, [rbp+48h]; this
0x18026d463  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d46a  mov     r9d, esi; char *
0x18026d46d  mov     edx, 31Dh; void *
0x18026d472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d477  mov     rcx, qword ptr [rbp+40h+var_80+8]
0x18026d47b  mov     qword ptr [rbp+40h+var_80+8], 0
0x18026d483  jmp     short loc_18026D4BA
0x18026d485  mov     edx, 319h
0x18026d48a  jmp     short loc_18026D49F
0x18026d48c  mov     edx, 325h
0x18026d491  jmp     short loc_18026D49F
0x18026d493  mov     edx, 323h
0x18026d498  jmp     short loc_18026D49F
0x18026d49a  mov     edx, 314h; void *
0x18026d49f  mov     rcx, [rbp+48h]; this
0x18026d4a3  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d4aa  mov     r9d, esi; char *
0x18026d4ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d4b2  mov     rcx, qword ptr [rbp+40h+var_80+8]
0x18026d4b6  mov     qword ptr [rbp+40h+var_80+8], r15
0x18026d4ba  test    rcx, rcx
0x18026d4bd  jz      short loc_18026D4C5
0x18026d4bf  call    cs:__imp_SRCache_Free
0x18026d4c5  lea     rcx, [rbp+40h+var_C0+8]; this
0x18026d4c9  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026d4ce  mov     ebx, esi
0x18026d4d0  lea     rcx, [rsp+140h+var_F8]; this
0x18026d4d5  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026d4da  jmp     loc_18026D702
0x18026d4df  sub     rdi, r14
0x18026d4e2  jz      short loc_18026D50D
0x18026d4e4  test    cs:byte_1804DF881, 20h
0x18026d4eb  jz      short loc_18026D50D
0x18026d4ed  mov     rax, qword ptr [rsp+140h+var_F0]
0x18026d4f2  lea     r8, aCacheapplicati_1; "CacheApplicationUser"
0x18026d4f9  mov     r9, rdi
0x18026d4fc  mov     [rsp+140h+var_120], rax; int
0x18026d501  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18026d508  call    McTemplateU0sxs_EventWriteTransfer
0x18026d50d  lea     rcx, [rbp+40h+var_C0+8]; this
0x18026d511  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026d516  lea     rcx, [rsp+140h+var_F8]; this
0x18026d51b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026d520  lea     rcx, [rsp+140h+var_F0]; this
0x18026d525  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18026d52a  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18026d52d  mov     [rsp+140h+var_110], r15
0x18026d532  lea     rcx, [rsp+140h+var_110]; this
0x18026d537  mov     [rsp+140h+var_108], r15d
0x18026d53c  mov     [rsp+140h+var_100], r15
0x18026d541  call    ?Open@ApplicationUserIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18026d546  mov     edi, eax
0x18026d548  test    eax, eax
0x18026d54a  jns     short loc_18026D598
0x18026d54c  mov     rcx, [rbp+48h]; this
0x18026d550  lea     r8, aOnecoreBaseApp_227; "onecore\\base\\appmodel\\StateRepositor"...
0x18026d557  mov     r9d, eax; char *
0x18026d55a  mov     edx, 42Eh; void *
0x18026d55f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d564  mov     rcx, [rbp+48h]; this
0x18026d568  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d56f  mov     r9d, edi; char *
0x18026d572  mov     edx, 336h; void *
0x18026d577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d57c  mov     rcx, [rsp+140h+var_110]
0x18026d581  mov     [rsp+140h+var_110], r15
0x18026d586  test    rcx, rcx
0x18026d589  jz      short loc_18026D591
0x18026d58b  call    cs:__imp_SRCacheContext_Close
0x18026d591  mov     ebx, edi
0x18026d593  jmp     loc_18026D702
0x18026d598  xorps   xmm0, xmm0
0x18026d59b  mov     [rbp+40h+arg_0], r15b
0x18026d59f  xorps   xmm1, xmm1
0x18026d5a2  lea     r9, [rbp+40h+arg_0]
0x18026d5a6  lea     r8, [rsp+140h+var_E0]
0x18026d5ab  lea     rcx, [rsp+140h+var_110]
0x18026d5b0  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18026d5b6  movdqu  [rsp+140h+var_D0], xmm1
0x18026d5bc  movdqu  [rbp+40h+var_C0], xmm0
0x18026d5c1  call    ?Get@ApplicationUserIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationUser_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x18026d5c6  mov     edi, eax
0x18026d5c8  test    eax, eax
0x18026d5ca  jns     short loc_18026D5F9
0x18026d5cc  mov     rcx, [rbp+48h]; this
0x18026d5d0  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d5d7  mov     r9d, eax; char *
0x18026d5da  mov     edx, 339h; void *
0x18026d5df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d5e4  mov     rcx, qword ptr [rbp+40h+var_C0+8]
0x18026d5e8  mov     qword ptr [rbp+40h+var_C0+8], r15
0x18026d5ec  test    rcx, rcx
0x18026d5ef  jz      short loc_18026D57C
0x18026d5f1  call    cs:__imp_SRCache_Free
0x18026d5f7  jmp     short loc_18026D57C
0x18026d5f9  mov     rdi, r15
0x18026d5fc  cmp     [rbp+40h+arg_0], r15b
0x18026d600  jz      loc_18026D711
0x18026d606  mov     r9, [rsp+140h+var_E0]; char *
0x18026d60b  lea     rax, [rbp+40h+arg_0]
0x18026d60f  xorps   xmm0, xmm0
0x18026d612  mov     [rsp+140h+var_120], rax; int
0x18026d617  xorps   xmm1, xmm1
0x18026d61a  mov     [rbp+40h+var_40], r15
0x18026d61e  xor     r8d, r8d; char *
0x18026d621  lea     rdx, aSelectExistsSe_258; "SELECT EXISTS(SELECT 1 FROM CacheApplic"...
0x18026d628  mov     rcx, r12; this
0x18026d62b  movdqu  [rbp+40h+var_70], xmm0
0x18026d630  movdqu  [rbp+40h+var_60], xmm1
0x18026d635  movdqu  [rbp+40h+var_50], xmm0
0x18026d63a  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026d63f  mov     esi, eax
0x18026d641  test    eax, eax
0x18026d643  js      short loc_18026D69F
0x18026d645  cmp     [rbp+40h+arg_0], r15b
0x18026d649  jnz     short loc_18026D666
0x18026d64b  mov     rdx, [rsp+140h+var_E0]; __int64
0x18026d650  lea     rcx, [rsp+140h+var_F0]; this
0x18026d655  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026d65a  mov     esi, eax
0x18026d65c  test    eax, eax
0x18026d65e  js      short loc_18026D691
0x18026d660  inc     rdi
0x18026d663  inc     rbx
0x18026d666  inc     [rsp+140h+var_108]
0x18026d66a  lea     r9, [rbp+40h+arg_0]
0x18026d66e  lea     r8, [rsp+140h+var_E0]
0x18026d673  lea     rcx, [rsp+140h+var_110]
0x18026d678  call    ?Get@ApplicationUserIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationUser_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUserIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x18026d67d  mov     esi, eax
0x18026d67f  test    eax, eax
0x18026d681  js      short loc_18026D698
0x18026d683  lea     rcx, [rbp+40h+var_50+8]; this
0x18026d687  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026d68c  jmp     loc_18026D5FC
0x18026d691  mov     edx, 342h
0x18026d696  jmp     short loc_18026D6BC
0x18026d698  mov     edx, 344h
0x18026d69d  jmp     short loc_18026D6BC
0x18026d69f  mov     rcx, [rbp+48h]; this
0x18026d6a3  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d6aa  mov     r9d, esi; char *
0x18026d6ad  mov     edx, 6Ah ; 'j'; void *
0x18026d6b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d6b7  mov     edx, 33Dh; void *
0x18026d6bc  mov     rcx, [rbp+48h]; this
0x18026d6c0  lea     r8, aOnecoreBaseApp_318; "onecore\\base\\appmodel\\staterepositor"...
0x18026d6c7  mov     r9d, esi; char *
0x18026d6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d6cf  lea     rcx, [rbp+40h+var_50+8]; this
0x18026d6d3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026d6d8  mov     rcx, qword ptr [rbp+40h+var_C0+8]
0x18026d6dc  mov     qword ptr [rbp+40h+var_C0+8], r15
0x18026d6e0  test    rcx, rcx
0x18026d6e3  jz      short loc_18026D6EB
0x18026d6e5  call    cs:__imp_SRCache_Free
0x18026d6eb  mov     rcx, [rsp+140h+var_110]
0x18026d6f0  mov     [rsp+140h+var_110], r15
0x18026d6f5  test    rcx, rcx
0x18026d6f8  jz      short loc_18026D700
0x18026d6fa  call    cs:__imp_SRCacheContext_Close
0x18026d700  mov     ebx, esi
0x18026d702  lea     rcx, [rsp+140h+var_F0]; this
0x18026d707  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026d70c  jmp     loc_18026D7A0
0x18026d711  mov     rcx, qword ptr [rbp+40h+var_C0+8]
0x18026d715  mov     qword ptr [rbp+40h+var_C0+8], r15
0x18026d719  test    rcx, rcx
0x18026d71c  jz      short loc_18026D724
0x18026d71e  call    cs:__imp_SRCache_Free
0x18026d724  mov     rcx, [rsp+140h+var_110]
0x18026d729  mov     [rsp+140h+var_110], r15
0x18026d72e  test    rcx, rcx
0x18026d731  jz      short loc_18026D739
  ... truncated ...
```
