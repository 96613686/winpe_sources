# StateRepository::Entity::CachePackageUserStatus::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18026c820`
- end: `0x18026cd38`
- name: `?Cache_CheckIntegrity@CachePackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1304`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x180098bb4`
- `0x1800ae890`
- `0x1800b2e80`
- `0x18026544c`
- `0x18026c68c`
- `0x18026c820`
- `0x18026ce24`
- `0x18026ceec`
- `0x18026cfcc`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026cb1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026cc81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ccb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026cb1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026cc81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ccb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026c9e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026ca51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026cb7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026cc6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026cca4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026c9e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026ca51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026cb7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026cc6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026cca4`

## string_xrefs

- `0x18026c897`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026c8e8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026c9f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026ca35`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026caf8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026cb5c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026cc2a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026cc47`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026cd15`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18026cae0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x18026ca83`: `CachePackageUserStatus`
- `0x18026ccd1`: `CachePackageUserStatus`
- `0x18026cbb0`: `SELECT EXISTS(SELECT 1 FROM CachePackageUserStatus WHERE _CachePackageUserStatusID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageUserStatus::Cache_CheckIntegrity(
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
  bool *v46; // [rsp+20h] [rbp-A9h]
  int v47; // [rsp+20h] [rbp-A9h]
  int v48; // [rsp+20h] [rbp-A9h]
  bool *v49; // [rsp+28h] [rbp-A1h]
  __int64 v50; // [rsp+30h] [rbp-99h] BYREF
  int v51; // [rsp+38h] [rbp-91h]
  __int64 v52; // [rsp+40h] [rbp-89h]
  __int64 v53; // [rsp+48h] [rbp-81h] BYREF
  char *v54[2]; // [rsp+50h] [rbp-79h] BYREF
  __int128 v55; // [rsp+60h] [rbp-69h] BYREF
  __int64 v56; // [rsp+70h] [rbp-59h]
  int v57; // [rsp+78h] [rbp-51h]
  int v58[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v59; // [rsp+88h] [rbp-41h]
  __int128 v60; // [rsp+90h] [rbp-39h] BYREF
  __int128 v61; // [rsp+A0h] [rbp-29h]
  int v62; // [rsp+B0h] [rbp-19h]
  unsigned __int64 v63; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v64; // [rsp+C0h] [rbp-9h]
  __int128 v65; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v66; // [rsp+E0h] [rbp+17h]
  int v67; // [rsp+E8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  bool v69; // [rsp+130h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v70; // [rsp+138h] [rbp+6Fh]
  _QWORD *v71; // [rsp+148h] [rbp+7Fh]

  v71 = a4;
  v70 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 526;
    goto LABEL_71;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 527;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)v6,
      (int)v46);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 528;
LABEL_71:
    v6 = -2147019873;
    goto LABEL_72;
  }
  *(_QWORD *)v58 = 0;
  v59 = 0;
  v53 = 0;
  v8 = StateRepository::Entity::CachePackageUserStatus::Find(a1, (struct StateRepository::Statement *)&v53);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)v8,
      (int)v46);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v53);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v58);
    return v6;
  }
  v56 = 0;
  v57 = 0;
  v69 = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  Next = StateRepository::Entity::CachePackageUserStatus::FindNext(
           (struct StateRepository::Statement *)&v53,
           (struct StateRepository::Entity::CachePackageUserStatus *)v54,
           &v69);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)Next,
      (int)v46);
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v55 + 8));
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v69 )
  {
    v46 = &v69;
    v62 = 0;
    v60 = 0;
    v61 = 0;
    v15 = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Get(v4, v54[0], v11, &v60);
    if ( v15 < 0 )
    {
      v21 = 547;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
        (const char *)(unsigned int)v15,
        (int)&v69);
      v20 = *((_QWORD *)&v61 + 1);
      *((_QWORD *)&v61 + 1) = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v55 + 8));
      v6 = v15;
      goto LABEL_32;
    }
    if ( v69 )
    {
      v63 = 0;
      v15 = StateRepository::Entity::CachePackageUserStatus::Cache_Check(
              (const struct StateRepository::Entity::CachePackageUserStatus *)v54,
              (const struct StateRepository::Cache::Entity::PackageUserStatus_NoThrow *)&v60,
              &v63);
      if ( v15 < 0 )
      {
        v21 = 552;
        goto LABEL_28;
      }
      v18 = v63;
      if ( v63 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v54[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22C,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
            (const char *)(unsigned int)appended,
            (int)&v69);
          v20 = *((_QWORD *)&v61 + 1);
          *((_QWORD *)&v61 + 1) = 0;
          goto LABEL_29;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      v15 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v54[0], v16);
      if ( v15 < 0 )
      {
        v21 = 562;
        goto LABEL_28;
      }
      ++v12;
    }
    v15 = StateRepository::Entity::CachePackageUserStatus::FindNext(
            (struct StateRepository::Statement *)&v53,
            (struct StateRepository::Entity::CachePackageUserStatus *)v54,
            &v69);
    if ( v15 < 0 )
    {
      v21 = 564;
      goto LABEL_28;
    }
    v10 = *((_QWORD *)&v61 + 1);
    ++v13;
    v4 = v70;
    *((_QWORD *)&v61 + 1) = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackageUserStatus",
      v22,
      *(__int64 *)v58);
  StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v55 + 8));
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v53);
  StateRepository::TextA::Clear((StateRepository::TextA *)v58);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v23 = StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow *)&v50,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageUserStatus.hpp",
      (const char *)(unsigned int)v23,
      (int)v46);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x245,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
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
  LODWORD(v56) = 0;
  v69 = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  v29 = StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow::Get(&v50, v24, v54, &v69);
  v25 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
    v32 = *((_QWORD *)&v55 + 1);
    *((_QWORD *)&v55 + 1) = 0;
    if ( v32 )
      SRCache_Free(v32);
    goto LABEL_38;
  }
  v33 = 0;
  while ( v69 )
  {
    v66 = 0;
    v67 = 0;
    v64 = 0;
    v65 = 0;
    v34 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackageUserStatus WHERE _CachePackageUs"
                                                "erStatusID=? LIMIT 1);",
            0,
            v54[0],
            (__int64)&v69,
            v49);
    v37 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
        (const char *)(unsigned int)v34,
        v48);
      v38 = 588;
      goto LABEL_55;
    }
    if ( !v69 )
    {
      v37 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v54[0], v36);
      if ( v37 < 0 )
      {
        v38 = 593;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
          (const char *)(unsigned int)v37,
          v48);
        StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v65 + 8));
        v41 = *((_QWORD *)&v55 + 1);
        *((_QWORD *)&v55 + 1) = 0;
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
    v37 = StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow::Get(&v50, v35, v54, &v69);
    if ( v37 < 0 )
    {
      v38 = 595;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v65 + 8));
  }
  v43 = *((_QWORD *)&v55 + 1);
  *((_QWORD *)&v55 + 1) = 0;
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
      (unsigned int)"CachePackageUserStatus",
      v33,
      *(__int64 *)v58);
  *v71 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v58);
  return 0;
}

```

## disassembly

```asm
0x18026c820  mov     [rsp-8+arg_18], r9
0x18026c825  mov     [rsp-8+arg_8], rdx
0x18026c82a  push    rbp
0x18026c82b  push    rbx
0x18026c82c  push    rsi
0x18026c82d  push    rdi
0x18026c82e  push    r12
0x18026c830  push    r14
0x18026c832  push    r15
0x18026c834  lea     rbp, [rsp-27h]
0x18026c839  sub     rsp, 0F0h
0x18026c840  xor     r15d, r15d
0x18026c843  mov     rsi, rdx
0x18026c846  mov     r12, rcx
0x18026c849  cmp     [rcx], r15
0x18026c84c  jz      loc_18026CD07
0x18026c852  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18026c857  test    al, al
0x18026c859  jz      short loc_18026C86A
0x18026c85b  mov     ebx, 8067000Bh
0x18026c860  mov     edx, 20Fh
0x18026c865  jmp     loc_18026CD11
0x18026c86a  cmp     [rsi], r15
0x18026c86d  jz      loc_18026CD00
0x18026c873  lea     rdx, [rsp+120h+var_D8]; struct StateRepository::Statement *
0x18026c878  mov     qword ptr [rbp+57h+var_A0], r15
0x18026c87c  mov     rcx, r12; struct StateRepository::Database *
0x18026c87f  mov     [rbp+57h+var_98], r15
0x18026c883  mov     [rsp+120h+var_D8], r15
0x18026c888  call    ?Find@CachePackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackageUserStatus::Find(StateRepository::Database &,StateRepository::Statement &)
0x18026c88d  mov     ebx, eax
0x18026c88f  test    eax, eax
0x18026c891  jns     short loc_18026C8B0
0x18026c893  mov     rcx, [rbp+5Fh]; this
0x18026c897  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026c89e  mov     r9d, eax; char *
0x18026c8a1  mov     edx, 21Bh; void *
0x18026c8a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026c8ab  jmp     loc_18026CA62
0x18026c8b0  xorps   xmm0, xmm0
0x18026c8b3  mov     [rbp+57h+var_B0], r15
0x18026c8b7  xorps   xmm1, xmm1
0x18026c8ba  mov     [rbp+57h+var_A8], r15d
0x18026c8be  lea     r8, [rbp+57h+arg_0]; bool *
0x18026c8c2  mov     [rbp+57h+arg_0], r15b
0x18026c8c6  lea     rdx, [rbp+57h+var_D0]; struct StateRepository::Entity::CachePackageUserStatus *
0x18026c8ca  lea     rcx, [rsp+120h+var_D8]; this
0x18026c8cf  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18026c8d4  movdqu  [rbp+57h+var_C0], xmm1
0x18026c8d9  call    ?FindNext@CachePackageUserStatus@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageUserStatus::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageUserStatus &,bool &)
0x18026c8de  mov     ebx, eax
0x18026c8e0  test    eax, eax
0x18026c8e2  jns     short loc_18026C90A
0x18026c8e4  mov     rcx, [rbp+5Fh]; this
0x18026c8e8  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026c8ef  mov     r9d, eax; char *
0x18026c8f2  mov     edx, 21Eh; void *
0x18026c8f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026c8fc  lea     rcx, [rbp+57h+var_C0+8]; this
0x18026c900  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026c905  jmp     loc_18026CA62
0x18026c90a  mov     rbx, r15
0x18026c90d  mov     rdi, r15
0x18026c910  mov     r14, r15
0x18026c913  cmp     [rbp+57h+arg_0], r15b
0x18026c917  jz      loc_18026CA71
0x18026c91d  mov     rdx, [rbp+57h+var_D0]
0x18026c921  lea     rax, [rbp+57h+arg_0]
0x18026c925  xorps   xmm0, xmm0
0x18026c928  mov     [rsp+120h+var_100], rax; int
0x18026c92d  xorps   xmm1, xmm1
0x18026c930  mov     [rbp+57h+var_70], r15d
0x18026c934  lea     r9, [rbp+57h+var_90]
0x18026c938  mov     rcx, rsi
0x18026c93b  movdqu  [rbp+57h+var_90], xmm0
0x18026c940  movdqu  [rbp+57h+var_80], xmm1
0x18026c945  call    ?Get@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageUserStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUserStatus_NoThrow &,bool &)
0x18026c94a  mov     esi, eax
0x18026c94c  test    eax, eax
0x18026c94e  js      loc_18026CA2C
0x18026c954  cmp     [rbp+57h+arg_0], r15b
0x18026c958  jz      short loc_18026C9A0
0x18026c95a  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18026c95e  mov     [rbp+57h+var_68], r15
0x18026c962  lea     rdx, [rbp+57h+var_90]; struct StateRepository::Cache::Entity::PackageUserStatus_NoThrow *
0x18026c966  lea     rcx, [rbp+57h+var_D0]; struct StateRepository::Entity::CachePackageUserStatus *
0x18026c96a  call    ?Cache_Check@CachePackageUserStatus@Entity@StateRepository@@CAJAEBV123@AEBVPackageUserStatus_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackageUserStatus::Cache_Check(StateRepository::Entity::CachePackageUserStatus const &,StateRepository::Cache::Entity::PackageUserStatus_NoThrow const &,unsigned __int64 &)
0x18026c96f  mov     esi, eax
0x18026c971  test    eax, eax
0x18026c973  js      loc_18026CA17
0x18026c979  mov     r15, [rbp+57h+var_68]
0x18026c97d  test    r15, r15
0x18026c980  jz      short loc_18026C998
0x18026c982  mov     rdx, [rbp+57h+var_D0]; __int64
0x18026c986  lea     rcx, [rbp+57h+var_A0]; this
0x18026c98a  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026c98f  mov     esi, eax
0x18026c991  test    eax, eax
0x18026c993  js      short loc_18026C9F1
0x18026c995  add     rbx, r15
0x18026c998  inc     r14
0x18026c99b  xor     r15d, r15d
0x18026c99e  jmp     short loc_18026C9B6
0x18026c9a0  mov     rdx, [rbp+57h+var_D0]; __int64
0x18026c9a4  lea     rcx, [rbp+57h+var_A0]; this
0x18026c9a8  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026c9ad  mov     esi, eax
0x18026c9af  test    eax, eax
0x18026c9b1  js      short loc_18026CA25
0x18026c9b3  inc     rbx
0x18026c9b6  lea     r8, [rbp+57h+arg_0]; bool *
0x18026c9ba  lea     rdx, [rbp+57h+var_D0]; struct StateRepository::Entity::CachePackageUserStatus *
0x18026c9be  lea     rcx, [rsp+120h+var_D8]; this
0x18026c9c3  call    ?FindNext@CachePackageUserStatus@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageUserStatus::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageUserStatus &,bool &)
0x18026c9c8  mov     esi, eax
0x18026c9ca  test    eax, eax
0x18026c9cc  js      short loc_18026CA1E
0x18026c9ce  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x18026c9d2  inc     rdi
0x18026c9d5  mov     rsi, [rbp+57h+arg_8]
0x18026c9d9  mov     qword ptr [rbp+57h+var_80+8], r15
0x18026c9dd  test    rcx, rcx
0x18026c9e0  jz      loc_18026C913
0x18026c9e6  call    cs:__imp_SRCache_Free
0x18026c9ec  jmp     loc_18026C913
0x18026c9f1  mov     rcx, [rbp+5Fh]; this
0x18026c9f5  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026c9fc  mov     r9d, esi; char *
0x18026c9ff  mov     edx, 22Ch; void *
0x18026ca04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ca09  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x18026ca0d  mov     qword ptr [rbp+57h+var_80+8], 0
0x18026ca15  jmp     short loc_18026CA4C
0x18026ca17  mov     edx, 228h
0x18026ca1c  jmp     short loc_18026CA31
0x18026ca1e  mov     edx, 234h
0x18026ca23  jmp     short loc_18026CA31
0x18026ca25  mov     edx, 232h
0x18026ca2a  jmp     short loc_18026CA31
0x18026ca2c  mov     edx, 223h; void *
0x18026ca31  mov     rcx, [rbp+5Fh]; this
0x18026ca35  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026ca3c  mov     r9d, esi; char *
0x18026ca3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ca44  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x18026ca48  mov     qword ptr [rbp+57h+var_80+8], r15
0x18026ca4c  test    rcx, rcx
0x18026ca4f  jz      short loc_18026CA57
0x18026ca51  call    cs:__imp_SRCache_Free
0x18026ca57  lea     rcx, [rbp+57h+var_C0+8]; this
0x18026ca5b  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026ca60  mov     ebx, esi
0x18026ca62  lea     rcx, [rsp+120h+var_D8]; this
0x18026ca67  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026ca6c  jmp     loc_18026CC89
0x18026ca71  sub     rdi, r14
0x18026ca74  jz      short loc_18026CA9E
0x18026ca76  test    cs:byte_1804DF881, 20h
0x18026ca7d  jz      short loc_18026CA9E
0x18026ca7f  mov     rax, qword ptr [rbp+57h+var_A0]
0x18026ca83  lea     r8, aCachepackageus_0; "CachePackageUserStatus"
0x18026ca8a  mov     r9, rdi
0x18026ca8d  mov     [rsp+120h+var_100], rax; int
0x18026ca92  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18026ca99  call    McTemplateU0sxs_EventWriteTransfer
0x18026ca9e  lea     rcx, [rbp+57h+var_C0+8]; this
0x18026caa2  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026caa7  lea     rcx, [rsp+120h+var_D8]; this
0x18026caac  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026cab1  lea     rcx, [rbp+57h+var_A0]; this
0x18026cab5  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18026caba  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18026cabd  mov     [rsp+120h+var_F0], r15
0x18026cac2  lea     rcx, [rsp+120h+var_F0]; this
0x18026cac7  mov     [rsp+120h+var_E8], r15d
0x18026cacc  mov     [rsp+120h+var_E0], r15
0x18026cad1  call    ?Open@PackageUserStatusIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18026cad6  mov     edi, eax
0x18026cad8  test    eax, eax
0x18026cada  jns     short loc_18026CB28
0x18026cadc  mov     rcx, [rbp+5Fh]; this
0x18026cae0  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\StateRepositor"...
0x18026cae7  mov     r9d, eax; char *
0x18026caea  mov     edx, 2EDh; void *
0x18026caef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026caf4  mov     rcx, [rbp+5Fh]; this
0x18026caf8  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026caff  mov     r9d, edi; char *
0x18026cb02  mov     edx, 245h; void *
0x18026cb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cb0c  mov     rcx, [rsp+120h+var_F0]
0x18026cb11  mov     [rsp+120h+var_F0], r15
0x18026cb16  test    rcx, rcx
0x18026cb19  jz      short loc_18026CB21
0x18026cb1b  call    cs:__imp_SRCacheContext_Close
0x18026cb21  mov     ebx, edi
0x18026cb23  jmp     loc_18026CC89
0x18026cb28  xorps   xmm0, xmm0
0x18026cb2b  mov     dword ptr [rbp+57h+var_B0], r15d
0x18026cb2f  xorps   xmm1, xmm1
0x18026cb32  mov     [rbp+57h+arg_0], r15b
0x18026cb36  lea     r9, [rbp+57h+arg_0]
0x18026cb3a  lea     r8, [rbp+57h+var_D0]
0x18026cb3e  lea     rcx, [rsp+120h+var_F0]
0x18026cb43  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x18026cb48  movdqu  [rbp+57h+var_C0], xmm1
0x18026cb4d  call    ?Get@PackageUserStatusIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageUserStatus_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageUserStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUserStatus_NoThrow &,bool &)
0x18026cb52  mov     edi, eax
0x18026cb54  test    eax, eax
0x18026cb56  jns     short loc_18026CB85
0x18026cb58  mov     rcx, [rbp+5Fh]; this
0x18026cb5c  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026cb63  mov     r9d, eax; char *
0x18026cb66  mov     edx, 248h; void *
0x18026cb6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cb70  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18026cb74  mov     qword ptr [rbp+57h+var_C0+8], r15
0x18026cb78  test    rcx, rcx
0x18026cb7b  jz      short loc_18026CB0C
0x18026cb7d  call    cs:__imp_SRCache_Free
0x18026cb83  jmp     short loc_18026CB0C
0x18026cb85  mov     rdi, r15
0x18026cb88  cmp     [rbp+57h+arg_0], r15b
0x18026cb8c  jz      loc_18026CC97
0x18026cb92  mov     r9, [rbp+57h+var_D0]; char *
0x18026cb96  lea     rax, [rbp+57h+arg_0]
0x18026cb9a  xorps   xmm0, xmm0
0x18026cb9d  mov     [rsp+120h+var_100], rax; int
0x18026cba2  xorps   xmm1, xmm1
0x18026cba5  mov     [rbp+57h+var_40], r15
0x18026cba9  xor     r8d, r8d; char *
0x18026cbac  mov     [rbp+57h+var_38], r15d
0x18026cbb0  lea     rdx, aSelectExistsSe_649; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x18026cbb7  mov     rcx, r12; this
0x18026cbba  movdqu  [rbp+57h+var_60], xmm0
0x18026cbbf  movdqu  [rbp+57h+var_50], xmm1
0x18026cbc4  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026cbc9  mov     esi, eax
0x18026cbcb  test    eax, eax
0x18026cbcd  js      short loc_18026CC26
0x18026cbcf  cmp     [rbp+57h+arg_0], r15b
0x18026cbd3  jnz     short loc_18026CBEE
0x18026cbd5  mov     rdx, [rbp+57h+var_D0]; __int64
0x18026cbd9  lea     rcx, [rbp+57h+var_A0]; this
0x18026cbdd  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026cbe2  mov     esi, eax
0x18026cbe4  test    eax, eax
0x18026cbe6  js      short loc_18026CC18
0x18026cbe8  inc     rdi
0x18026cbeb  inc     rbx
0x18026cbee  inc     [rsp+120h+var_E8]
0x18026cbf2  lea     r9, [rbp+57h+arg_0]
0x18026cbf6  lea     r8, [rbp+57h+var_D0]
0x18026cbfa  lea     rcx, [rsp+120h+var_F0]
0x18026cbff  call    ?Get@PackageUserStatusIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageUserStatus_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageUserStatusIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageUserStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUserStatus_NoThrow &,bool &)
0x18026cc04  mov     esi, eax
0x18026cc06  test    eax, eax
0x18026cc08  js      short loc_18026CC1F
0x18026cc0a  lea     rcx, [rbp+57h+var_50+8]; this
0x18026cc0e  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026cc13  jmp     loc_18026CB88
0x18026cc18  mov     edx, 251h
0x18026cc1d  jmp     short loc_18026CC43
0x18026cc1f  mov     edx, 253h
0x18026cc24  jmp     short loc_18026CC43
0x18026cc26  mov     rcx, [rbp+5Fh]; this
0x18026cc2a  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026cc31  mov     r9d, esi; char *
0x18026cc34  mov     edx, 5Eh ; '^'; void *
0x18026cc39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cc3e  mov     edx, 24Ch; void *
0x18026cc43  mov     rcx, [rbp+5Fh]; this
0x18026cc47  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18026cc4e  mov     r9d, esi; char *
0x18026cc51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cc56  lea     rcx, [rbp+57h+var_50+8]; this
0x18026cc5a  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026cc5f  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18026cc63  mov     qword ptr [rbp+57h+var_C0+8], r15
0x18026cc67  test    rcx, rcx
0x18026cc6a  jz      short loc_18026CC72
0x18026cc6c  call    cs:__imp_SRCache_Free
0x18026cc72  mov     rcx, [rsp+120h+var_F0]
0x18026cc77  mov     [rsp+120h+var_F0], r15
0x18026cc7c  test    rcx, rcx
0x18026cc7f  jz      short loc_18026CC87
0x18026cc81  call    cs:__imp_SRCacheContext_Close
0x18026cc87  mov     ebx, esi
0x18026cc89  lea     rcx, [rbp+57h+var_A0]; this
0x18026cc8d  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026cc92  jmp     loc_18026CD24
0x18026cc97  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18026cc9b  mov     qword ptr [rbp+57h+var_C0+8], r15
0x18026cc9f  test    rcx, rcx
0x18026cca2  jz      short loc_18026CCAA
0x18026cca4  call    cs:__imp_SRCache_Free
0x18026ccaa  mov     rcx, [rsp+120h+var_F0]
0x18026ccaf  mov     [rsp+120h+var_F0], r15
0x18026ccb4  test    rcx, rcx
0x18026ccb7  jz      short loc_18026CCBF
  ... truncated ...
```
