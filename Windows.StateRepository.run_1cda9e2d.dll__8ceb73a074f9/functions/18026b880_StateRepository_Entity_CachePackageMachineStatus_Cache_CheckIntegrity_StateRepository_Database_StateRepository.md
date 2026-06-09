# StateRepository::Entity::CachePackageMachineStatus::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18026b880`
- end: `0x18026bd81`
- name: `?Cache_CheckIntegrity@CachePackageMachineStatus@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1281`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800a6b88`
- `0x1800ae890`
- `0x18011ee98`
- `0x18026544c`
- `0x18026b718`
- `0x18026b880`
- `0x18026c28c`
- `0x18026c2fc`
- `0x18026c3c4`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026bb6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026bcca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026bd02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026bb6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026bcca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026bd02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026ba3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026baa5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bbca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bcb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bced`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026ba3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026baa5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bbca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bcb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bced`

## string_xrefs

- `0x18026bb31`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x18026b8f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026b941`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026ba49`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026ba89`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bb49`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bba9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bc73`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bc90`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bd5e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bad6`: `CachePackageMachineStatus`
- `0x18026bd1a`: `CachePackageMachineStatus`
- `0x18026bbf9`: `SELECT EXISTS(SELECT 1 FROM CachePackageMachineStatus WHERE _CachePackageMachineStatusID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageMachineStatus::Cache_CheckIntegrity(
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
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rdx
  char v32; // r8
  int v33; // esi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  bool *v40; // [rsp+20h] [rbp-99h]
  int v41; // [rsp+20h] [rbp-99h]
  int v42; // [rsp+20h] [rbp-99h]
  bool *v43; // [rsp+28h] [rbp-91h]
  __int64 v44; // [rsp+30h] [rbp-89h] BYREF
  int v45; // [rsp+38h] [rbp-81h]
  __int64 v46; // [rsp+40h] [rbp-79h]
  char *v47[2]; // [rsp+48h] [rbp-71h] BYREF
  __int128 v48; // [rsp+58h] [rbp-61h] BYREF
  int v49; // [rsp+68h] [rbp-51h]
  __int64 v50; // [rsp+70h] [rbp-49h] BYREF
  int v51[2]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v52; // [rsp+80h] [rbp-39h]
  __int128 v53; // [rsp+88h] [rbp-31h] BYREF
  __int64 v54; // [rsp+98h] [rbp-21h]
  int v55; // [rsp+A0h] [rbp-19h]
  unsigned __int64 v56; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v57; // [rsp+B0h] [rbp-9h]
  __int128 v58; // [rsp+C0h] [rbp+7h] BYREF
  int v59; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  bool v61; // [rsp+120h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v62; // [rsp+128h] [rbp+6Fh]
  _QWORD *v63; // [rsp+138h] [rbp+7Fh]

  v63 = a4;
  v62 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 432;
    goto LABEL_71;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 433;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)v6,
      (int)v40);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 434;
LABEL_71:
    v6 = -2147019873;
    goto LABEL_72;
  }
  *(_QWORD *)v51 = 0;
  v52 = 0;
  v50 = 0;
  v8 = StateRepository::Entity::CachePackageMachineStatus::Find(a1, (struct StateRepository::Statement *)&v50);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)v8,
      (int)v40);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v50);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v51);
    return v6;
  }
  v49 = 0;
  v61 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  Next = StateRepository::Entity::CachePackageMachineStatus::FindNext(
           (struct StateRepository::Statement *)&v50,
           (struct StateRepository::Entity::CachePackageMachineStatus *)v47,
           &v61);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)Next,
      (int)v40);
    StateRepository::TextA::Reset((StateRepository::TextA *)&v48);
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v61 )
  {
    v40 = &v61;
    v54 = 0;
    v55 = 0;
    v53 = 0;
    v15 = StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Get(v4, v47[0], v11, &v53);
    if ( v15 < 0 )
    {
      v21 = 453;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
        (const char *)(unsigned int)v15,
        (int)&v61);
      v20 = v54;
      v54 = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)&v48);
      v6 = v15;
      goto LABEL_32;
    }
    if ( v61 )
    {
      v56 = 0;
      v15 = StateRepository::Entity::CachePackageMachineStatus::Cache_Check(
              (const struct StateRepository::Entity::CachePackageMachineStatus *)v47,
              (const struct StateRepository::Cache::Entity::PackageMachineStatus_NoThrow *)&v53,
              &v56);
      if ( v15 < 0 )
      {
        v21 = 458;
        goto LABEL_28;
      }
      v18 = v56;
      if ( v56 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CE,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
            (const char *)(unsigned int)appended,
            (int)&v61);
          v20 = v54;
          v54 = 0;
          goto LABEL_29;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      v15 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v16);
      if ( v15 < 0 )
      {
        v21 = 468;
        goto LABEL_28;
      }
      ++v12;
    }
    v15 = StateRepository::Entity::CachePackageMachineStatus::FindNext(
            (struct StateRepository::Statement *)&v50,
            (struct StateRepository::Entity::CachePackageMachineStatus *)v47,
            &v61);
    if ( v15 < 0 )
    {
      v21 = 470;
      goto LABEL_28;
    }
    v10 = v54;
    ++v13;
    v4 = v62;
    v54 = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)&CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackageMachineStatus",
      v22,
      *(__int64 *)v51);
  StateRepository::TextA::Reset((StateRepository::TextA *)&v48);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v50);
  StateRepository::TextA::Clear((StateRepository::TextA *)v51);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v23 = StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow *)&v44,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v23,
      (int)v40);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)v25,
      v41);
LABEL_38:
    v26 = v44;
    v44 = 0;
    if ( v26 )
      SRCacheContext_Close(v26);
    v6 = v25;
    goto LABEL_60;
  }
  *(_QWORD *)&v48 = 0;
  DWORD2(v48) = 0;
  v61 = 0;
  *(_OWORD *)v47 = 0;
  v27 = StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow::Get(&v44, v24, v47, &v61);
  v25 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)v27,
      (int)v40);
    v28 = v48;
    *(_QWORD *)&v48 = 0;
    if ( v28 )
      SRCache_Free(v28);
    goto LABEL_38;
  }
  v29 = 0;
  while ( v61 )
  {
    v59 = 0;
    v57 = 0;
    v58 = 0;
    v30 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackageMachineStatus WHERE _CachePackag"
                                                "eMachineStatusID=? LIMIT 1);",
            0,
            v47[0],
            (__int64)&v61,
            v43);
    v33 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
        (const char *)(unsigned int)v30,
        v42);
      v34 = 494;
      goto LABEL_55;
    }
    if ( !v61 )
    {
      v33 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v32);
      if ( v33 < 0 )
      {
        v34 = 499;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
          (const char *)(unsigned int)v33,
          v42);
        StateRepository::TextA::Reset((StateRepository::TextA *)&v58);
        v35 = v48;
        *(_QWORD *)&v48 = 0;
        if ( v35 )
          SRCache_Free(v35);
        v36 = v44;
        v44 = 0;
        if ( v36 )
          SRCacheContext_Close(v36);
        v6 = v33;
        goto LABEL_60;
      }
      ++v29;
      ++v12;
    }
    ++v45;
    v33 = StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow::Get(&v44, v31, v47, &v61);
    if ( v33 < 0 )
    {
      v34 = 501;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)&v58);
  }
  v37 = v48;
  *(_QWORD *)&v48 = 0;
  if ( v37 )
    SRCache_Free(v37);
  v38 = v44;
  v44 = 0;
  if ( v38 )
    SRCacheContext_Close(v38);
  if ( v29 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v38,
      (unsigned int)&CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CachePackageMachineStatus",
      v29,
      *(__int64 *)v51);
  *v63 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v51);
  return 0;
}

```

## disassembly

```asm
0x18026b880  mov     [rsp-8+arg_18], r9
0x18026b885  mov     [rsp-8+arg_8], rdx
0x18026b88a  push    rbp
0x18026b88b  push    rbx
0x18026b88c  push    rsi
0x18026b88d  push    rdi
0x18026b88e  push    r13
0x18026b890  push    r14
0x18026b892  push    r15
0x18026b894  lea     rbp, [rsp-27h]
0x18026b899  sub     rsp, 0E0h
0x18026b8a0  xor     r15d, r15d
0x18026b8a3  mov     rsi, rdx
0x18026b8a6  mov     r13, rcx
0x18026b8a9  cmp     [rcx], r15
0x18026b8ac  jz      loc_18026BD50
0x18026b8b2  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18026b8b7  test    al, al
0x18026b8b9  jz      short loc_18026B8CA
0x18026b8bb  mov     ebx, 8067000Bh
0x18026b8c0  mov     edx, 1B1h
0x18026b8c5  jmp     loc_18026BD5A
0x18026b8ca  cmp     [rsi], r15
0x18026b8cd  jz      loc_18026BD49
0x18026b8d3  lea     rdx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026b8d7  mov     qword ptr [rbp+57h+var_98], r15
0x18026b8db  mov     rcx, r13; struct StateRepository::Database *
0x18026b8de  mov     [rbp+57h+var_90], r15
0x18026b8e2  mov     [rbp+57h+var_A0], r15
0x18026b8e6  call    ?Find@CachePackageMachineStatus@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackageMachineStatus::Find(StateRepository::Database &,StateRepository::Statement &)
0x18026b8eb  mov     ebx, eax
0x18026b8ed  test    eax, eax
0x18026b8ef  jns     short loc_18026B90E
0x18026b8f1  mov     rcx, [rbp+5Fh]; this
0x18026b8f5  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026b8fc  mov     r9d, eax; char *
0x18026b8ff  mov     edx, 1BDh; void *
0x18026b904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b909  jmp     loc_18026BAB6
0x18026b90e  xorps   xmm0, xmm0
0x18026b911  mov     [rbp+57h+var_A8], r15d
0x18026b915  xorps   xmm1, xmm1
0x18026b918  mov     [rbp+57h+arg_0], r15b
0x18026b91c  lea     r8, [rbp+57h+arg_0]; bool *
0x18026b920  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CachePackageMachineStatus *
0x18026b924  lea     rcx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026b928  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18026b92d  movdqu  [rbp+57h+var_B8], xmm1
0x18026b932  call    ?FindNext@CachePackageMachineStatus@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageMachineStatus::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageMachineStatus &,bool &)
0x18026b937  mov     ebx, eax
0x18026b939  test    eax, eax
0x18026b93b  jns     short loc_18026B963
0x18026b93d  mov     rcx, [rbp+5Fh]; this
0x18026b941  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026b948  mov     r9d, eax; char *
0x18026b94b  mov     edx, 1C0h; void *
0x18026b950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b955  lea     rcx, [rbp+57h+var_B8]; this
0x18026b959  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026b95e  jmp     loc_18026BAB6
0x18026b963  mov     rbx, r15
0x18026b966  mov     rdi, r15
0x18026b969  mov     r14, r15
0x18026b96c  cmp     [rbp+57h+arg_0], r15b
0x18026b970  jz      loc_18026BAC4
0x18026b976  mov     rdx, [rbp+57h+var_C8]
0x18026b97a  lea     rax, [rbp+57h+arg_0]
0x18026b97e  xorps   xmm0, xmm0
0x18026b981  mov     [rsp+110h+var_F0], rax; int
0x18026b986  lea     r9, [rbp+57h+var_88]
0x18026b98a  mov     [rbp+57h+var_78], r15
0x18026b98e  mov     rcx, rsi
0x18026b991  mov     [rbp+57h+var_70], r15d
0x18026b995  movdqu  [rbp+57h+var_88], xmm0
0x18026b99a  call    ?Get@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow &,bool &)
0x18026b99f  mov     esi, eax
0x18026b9a1  test    eax, eax
0x18026b9a3  js      loc_18026BA80
0x18026b9a9  cmp     [rbp+57h+arg_0], r15b
0x18026b9ad  jz      short loc_18026B9F5
0x18026b9af  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18026b9b3  mov     [rbp+57h+var_68], r15
0x18026b9b7  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Cache::Entity::PackageMachineStatus_NoThrow *
0x18026b9bb  lea     rcx, [rbp+57h+var_C8]; struct StateRepository::Entity::CachePackageMachineStatus *
0x18026b9bf  call    ?Cache_Check@CachePackageMachineStatus@Entity@StateRepository@@CAJAEBV123@AEBVPackageMachineStatus_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackageMachineStatus::Cache_Check(StateRepository::Entity::CachePackageMachineStatus const &,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow const &,unsigned __int64 &)
0x18026b9c4  mov     esi, eax
0x18026b9c6  test    eax, eax
0x18026b9c8  js      loc_18026BA6B
0x18026b9ce  mov     r15, [rbp+57h+var_68]
0x18026b9d2  test    r15, r15
0x18026b9d5  jz      short loc_18026B9ED
0x18026b9d7  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026b9db  lea     rcx, [rbp+57h+var_98]; this
0x18026b9df  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026b9e4  mov     esi, eax
0x18026b9e6  test    eax, eax
0x18026b9e8  js      short loc_18026BA45
0x18026b9ea  add     rbx, r15
0x18026b9ed  inc     r14
0x18026b9f0  xor     r15d, r15d
0x18026b9f3  jmp     short loc_18026BA0B
0x18026b9f5  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026b9f9  lea     rcx, [rbp+57h+var_98]; this
0x18026b9fd  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026ba02  mov     esi, eax
0x18026ba04  test    eax, eax
0x18026ba06  js      short loc_18026BA79
0x18026ba08  inc     rbx
0x18026ba0b  lea     r8, [rbp+57h+arg_0]; bool *
0x18026ba0f  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CachePackageMachineStatus *
0x18026ba13  lea     rcx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026ba17  call    ?FindNext@CachePackageMachineStatus@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageMachineStatus::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageMachineStatus &,bool &)
0x18026ba1c  mov     esi, eax
0x18026ba1e  test    eax, eax
0x18026ba20  js      short loc_18026BA72
0x18026ba22  mov     rcx, [rbp+57h+var_78]
0x18026ba26  inc     rdi
0x18026ba29  mov     rsi, [rbp+57h+arg_8]
0x18026ba2d  mov     [rbp+57h+var_78], r15
0x18026ba31  test    rcx, rcx
0x18026ba34  jz      loc_18026B96C
0x18026ba3a  call    cs:__imp_SRCache_Free
0x18026ba40  jmp     loc_18026B96C
0x18026ba45  mov     rcx, [rbp+5Fh]; this
0x18026ba49  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026ba50  mov     r9d, esi; char *
0x18026ba53  mov     edx, 1CEh; void *
0x18026ba58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ba5d  mov     rcx, [rbp+57h+var_78]
0x18026ba61  mov     [rbp+57h+var_78], 0
0x18026ba69  jmp     short loc_18026BAA0
0x18026ba6b  mov     edx, 1CAh
0x18026ba70  jmp     short loc_18026BA85
0x18026ba72  mov     edx, 1D6h
0x18026ba77  jmp     short loc_18026BA85
0x18026ba79  mov     edx, 1D4h
0x18026ba7e  jmp     short loc_18026BA85
0x18026ba80  mov     edx, 1C5h; void *
0x18026ba85  mov     rcx, [rbp+5Fh]; this
0x18026ba89  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026ba90  mov     r9d, esi; char *
0x18026ba93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ba98  mov     rcx, [rbp+57h+var_78]
0x18026ba9c  mov     [rbp+57h+var_78], r15
0x18026baa0  test    rcx, rcx
0x18026baa3  jz      short loc_18026BAAB
0x18026baa5  call    cs:__imp_SRCache_Free
0x18026baab  lea     rcx, [rbp+57h+var_B8]; this
0x18026baaf  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026bab4  mov     ebx, esi
0x18026bab6  lea     rcx, [rbp+57h+var_A0]; this
0x18026baba  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026babf  jmp     loc_18026BCD2
0x18026bac4  sub     rdi, r14
0x18026bac7  jz      short loc_18026BAF1
0x18026bac9  test    cs:byte_1804DF881, 20h
0x18026bad0  jz      short loc_18026BAF1
0x18026bad2  mov     rax, qword ptr [rbp+57h+var_98]
0x18026bad6  lea     r8, aCachepackagema; "CachePackageMachineStatus"
0x18026badd  mov     r9, rdi
0x18026bae0  mov     [rsp+110h+var_F0], rax; int
0x18026bae5  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18026baec  call    McTemplateU0sxs_EventWriteTransfer
0x18026baf1  lea     rcx, [rbp+57h+var_B8]; this
0x18026baf5  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026bafa  lea     rcx, [rbp+57h+var_A0]; this
0x18026bafe  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026bb03  lea     rcx, [rbp+57h+var_98]; this
0x18026bb07  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18026bb0c  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18026bb0f  mov     [rsp+110h+var_E0], r15
0x18026bb14  lea     rcx, [rsp+110h+var_E0]; this
0x18026bb19  mov     [rsp+110h+var_D8], r15d
0x18026bb1e  mov     [rbp+57h+var_D0], r15
0x18026bb22  call    ?Open@PackageMachineStatusIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18026bb27  mov     edi, eax
0x18026bb29  test    eax, eax
0x18026bb2b  jns     short loc_18026BB79
0x18026bb2d  mov     rcx, [rbp+5Fh]; this
0x18026bb31  lea     r8, aOnecoreBaseApp_98; "onecore\\base\\appmodel\\StateRepositor"...
0x18026bb38  mov     r9d, eax; char *
0x18026bb3b  mov     edx, 2A1h; void *
0x18026bb40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bb45  mov     rcx, [rbp+5Fh]; this
0x18026bb49  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026bb50  mov     r9d, edi; char *
0x18026bb53  mov     edx, 1E7h; void *
0x18026bb58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bb5d  mov     rcx, [rsp+110h+var_E0]
0x18026bb62  mov     [rsp+110h+var_E0], r15
0x18026bb67  test    rcx, rcx
0x18026bb6a  jz      short loc_18026BB72
0x18026bb6c  call    cs:__imp_SRCacheContext_Close
0x18026bb72  mov     ebx, edi
0x18026bb74  jmp     loc_18026BCD2
0x18026bb79  xorps   xmm0, xmm0
0x18026bb7c  mov     qword ptr [rbp+57h+var_B8], r15
0x18026bb80  lea     r9, [rbp+57h+arg_0]
0x18026bb84  mov     dword ptr [rbp+57h+var_B8+8], r15d
0x18026bb88  lea     r8, [rbp+57h+var_C8]
0x18026bb8c  mov     [rbp+57h+arg_0], r15b
0x18026bb90  lea     rcx, [rsp+110h+var_E0]
0x18026bb95  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18026bb9a  call    ?Get@PackageMachineStatusIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageMachineStatus_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow &,bool &)
0x18026bb9f  mov     edi, eax
0x18026bba1  test    eax, eax
0x18026bba3  jns     short loc_18026BBD2
0x18026bba5  mov     rcx, [rbp+5Fh]; this
0x18026bba9  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026bbb0  mov     r9d, eax; char *
0x18026bbb3  mov     edx, 1EAh; void *
0x18026bbb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bbbd  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18026bbc1  mov     qword ptr [rbp+57h+var_B8], r15
0x18026bbc5  test    rcx, rcx
0x18026bbc8  jz      short loc_18026BB5D
0x18026bbca  call    cs:__imp_SRCache_Free
0x18026bbd0  jmp     short loc_18026BB5D
0x18026bbd2  mov     rdi, r15
0x18026bbd5  cmp     [rbp+57h+arg_0], r15b
0x18026bbd9  jz      loc_18026BCE0
0x18026bbdf  mov     r9, [rbp+57h+var_C8]; char *
0x18026bbe3  lea     rax, [rbp+57h+arg_0]
0x18026bbe7  xorps   xmm0, xmm0
0x18026bbea  mov     [rsp+110h+var_F0], rax; int
0x18026bbef  xorps   xmm1, xmm1
0x18026bbf2  mov     [rbp+57h+var_40], r15d
0x18026bbf6  xor     r8d, r8d; char *
0x18026bbf9  lea     rdx, aSelectExistsSe_247; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x18026bc00  mov     rcx, r13; this
0x18026bc03  movdqu  [rbp+57h+var_60], xmm0
0x18026bc08  movdqu  [rbp+57h+var_50], xmm1
0x18026bc0d  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026bc12  mov     esi, eax
0x18026bc14  test    eax, eax
0x18026bc16  js      short loc_18026BC6F
0x18026bc18  cmp     [rbp+57h+arg_0], r15b
0x18026bc1c  jnz     short loc_18026BC37
0x18026bc1e  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026bc22  lea     rcx, [rbp+57h+var_98]; this
0x18026bc26  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026bc2b  mov     esi, eax
0x18026bc2d  test    eax, eax
0x18026bc2f  js      short loc_18026BC61
0x18026bc31  inc     rdi
0x18026bc34  inc     rbx
0x18026bc37  inc     [rsp+110h+var_D8]
0x18026bc3b  lea     r9, [rbp+57h+arg_0]
0x18026bc3f  lea     r8, [rbp+57h+var_C8]
0x18026bc43  lea     rcx, [rsp+110h+var_E0]
0x18026bc48  call    ?Get@PackageMachineStatusIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageMachineStatus_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatusIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow &,bool &)
0x18026bc4d  mov     esi, eax
0x18026bc4f  test    eax, eax
0x18026bc51  js      short loc_18026BC68
0x18026bc53  lea     rcx, [rbp+57h+var_50]; this
0x18026bc57  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026bc5c  jmp     loc_18026BBD5
0x18026bc61  mov     edx, 1F3h
0x18026bc66  jmp     short loc_18026BC8C
0x18026bc68  mov     edx, 1F5h
0x18026bc6d  jmp     short loc_18026BC8C
0x18026bc6f  mov     rcx, [rbp+5Fh]; this
0x18026bc73  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026bc7a  mov     r9d, esi; char *
0x18026bc7d  mov     edx, 52h ; 'R'; void *
0x18026bc82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bc87  mov     edx, 1EEh; void *
0x18026bc8c  mov     rcx, [rbp+5Fh]; this
0x18026bc90  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026bc97  mov     r9d, esi; char *
0x18026bc9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bc9f  lea     rcx, [rbp+57h+var_50]; this
0x18026bca3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026bca8  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18026bcac  mov     qword ptr [rbp+57h+var_B8], r15
0x18026bcb0  test    rcx, rcx
0x18026bcb3  jz      short loc_18026BCBB
0x18026bcb5  call    cs:__imp_SRCache_Free
0x18026bcbb  mov     rcx, [rsp+110h+var_E0]
0x18026bcc0  mov     [rsp+110h+var_E0], r15
0x18026bcc5  test    rcx, rcx
0x18026bcc8  jz      short loc_18026BCD0
0x18026bcca  call    cs:__imp_SRCacheContext_Close
0x18026bcd0  mov     ebx, esi
0x18026bcd2  lea     rcx, [rbp+57h+var_98]; this
0x18026bcd6  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026bcdb  jmp     loc_18026BD6D
0x18026bce0  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18026bce4  mov     qword ptr [rbp+57h+var_B8], r15
0x18026bce8  test    rcx, rcx
0x18026bceb  jz      short loc_18026BCF3
0x18026bced  call    cs:__imp_SRCache_Free
0x18026bcf3  mov     rcx, [rsp+110h+var_E0]
0x18026bcf8  mov     [rsp+110h+var_E0], r15
0x18026bcfd  test    rcx, rcx
0x18026bd00  jz      short loc_18026BD08
0x18026bd02  call    cs:__imp_SRCacheContext_Close
0x18026bd08  test    rdi, rdi
0x18026bd0b  jz      short loc_18026BD35
0x18026bd0d  test    cs:byte_1804DF881, 20h
  ... truncated ...
```
