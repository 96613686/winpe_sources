# StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18026a880`
- end: `0x18026ad81`
- name: `?Cache_CheckIntegrity@CacheDynamicAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1281`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800a7a78`
- `0x1800ae890`
- `0x1800b8814`
- `0x18026544c`
- `0x18026a71c`
- `0x18026a880`
- `0x18026b28c`
- `0x18026b354`
- `0x18026b434`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ab6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026acca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ad02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ab6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026acca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ad02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026aa3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026aaa5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026abca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026acb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026aced`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026aa3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026aaa5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026abca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026acb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026aced`

## string_xrefs

- `0x18026a8f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026a941`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026aa49`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026aa89`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026ab49`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026aba9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026ac73`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026ac90`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026ad5e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026ab31`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x18026aad6`: `CacheDynamicAppUriHandlerGroup`
- `0x18026ad1a`: `CacheDynamicAppUriHandlerGroup`
- `0x18026abf9`: `SELECT EXISTS(SELECT 1 FROM CacheDynamicAppUriHandlerGroup WHERE _CacheDynamicAppUriHandlerGroupID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Cache_CheckIntegrity(
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
  __int64 v49; // [rsp+68h] [rbp-51h]
  __int64 v50; // [rsp+70h] [rbp-49h] BYREF
  int v51[2]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v52; // [rsp+80h] [rbp-39h]
  __int128 v53; // [rsp+88h] [rbp-31h] BYREF
  __int128 v54; // [rsp+98h] [rbp-21h]
  unsigned __int64 v55; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-9h]
  __int128 v57; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v58; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  bool v60; // [rsp+120h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v61; // [rsp+128h] [rbp+6Fh]
  _QWORD *v62; // [rsp+138h] [rbp+7Fh]

  v62 = a4;
  v61 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 513;
    goto LABEL_71;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 514;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
      (const char *)v6,
      (int)v40);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 515;
LABEL_71:
    v6 = -2147019873;
    goto LABEL_72;
  }
  *(_QWORD *)v51 = 0;
  v52 = 0;
  v50 = 0;
  v8 = StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Find(a1, (struct StateRepository::Statement *)&v50);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
      (const char *)(unsigned int)v8,
      (int)v40);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v50);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v51);
    return v6;
  }
  v49 = 0;
  v60 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  Next = StateRepository::Entity::CacheDynamicAppUriHandlerGroup::FindNext(
           (struct StateRepository::Statement *)&v50,
           (struct StateRepository::Entity::CacheDynamicAppUriHandlerGroup *)v47,
           &v60);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
      (const char *)(unsigned int)Next,
      (int)v40);
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v48 + 8));
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v60 )
  {
    v40 = &v60;
    v53 = 0;
    v54 = 0;
    v15 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Get(v4, v47[0], v11, &v53);
    if ( v15 < 0 )
    {
      v21 = 534;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
        (const char *)(unsigned int)v15,
        (int)&v60);
      v20 = *((_QWORD *)&v54 + 1);
      *((_QWORD *)&v54 + 1) = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v48 + 8));
      v6 = v15;
      goto LABEL_32;
    }
    if ( v60 )
    {
      v55 = 0;
      v15 = StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Cache_Check(
              (const struct StateRepository::Entity::CacheDynamicAppUriHandlerGroup *)v47,
              (const struct StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow *)&v53,
              &v55);
      if ( v15 < 0 )
      {
        v21 = 539;
        goto LABEL_28;
      }
      v18 = v55;
      if ( v55 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
            (const char *)(unsigned int)appended,
            (int)&v60);
          v20 = *((_QWORD *)&v54 + 1);
          *((_QWORD *)&v54 + 1) = 0;
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
        v21 = 549;
        goto LABEL_28;
      }
      ++v12;
    }
    v15 = StateRepository::Entity::CacheDynamicAppUriHandlerGroup::FindNext(
            (struct StateRepository::Statement *)&v50,
            (struct StateRepository::Entity::CacheDynamicAppUriHandlerGroup *)v47,
            &v60);
    if ( v15 < 0 )
    {
      v21 = 551;
      goto LABEL_28;
    }
    v10 = *((_QWORD *)&v54 + 1);
    ++v13;
    v4 = v61;
    *((_QWORD *)&v54 + 1) = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheDynamicAppUriHandlerGroup",
      v22,
      *(__int64 *)v51);
  StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v48 + 8));
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v50);
  StateRepository::TextA::Clear((StateRepository::TextA *)v51);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v23 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow *)&v44,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v23,
      (int)v40);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
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
  v60 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v27 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(&v44, v24, v47, &v60);
  v25 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
      (const char *)(unsigned int)v27,
      (int)v40);
    v28 = *((_QWORD *)&v48 + 1);
    *((_QWORD *)&v48 + 1) = 0;
    if ( v28 )
      SRCache_Free(v28);
    goto LABEL_38;
  }
  v29 = 0;
  while ( v60 )
  {
    v58 = 0;
    v56 = 0;
    v57 = 0;
    v30 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheDynamicAppUriHandlerGroup WHERE _CacheD"
                                                "ynamicAppUriHandlerGroupID=? LIMIT 1);",
            0,
            v47[0],
            (__int64)&v60,
            v43);
    v33 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
        (const char *)(unsigned int)v30,
        v42);
      v34 = 575;
      goto LABEL_55;
    }
    if ( !v60 )
    {
      v33 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v51, (__int64)v47[0], v32);
      if ( v33 < 0 )
      {
        v34 = 580;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
          (const char *)(unsigned int)v33,
          v42);
        StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v57 + 8));
        v35 = *((_QWORD *)&v48 + 1);
        *((_QWORD *)&v48 + 1) = 0;
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
    v33 = StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(&v44, v31, v47, &v60);
    if ( v33 < 0 )
    {
      v34 = 582;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v57 + 8));
  }
  v37 = *((_QWORD *)&v48 + 1);
  *((_QWORD *)&v48 + 1) = 0;
  if ( v37 )
    SRCache_Free(v37);
  v38 = v44;
  v44 = 0;
  if ( v38 )
    SRCacheContext_Close(v38);
  if ( v29 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v38,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheDynamicAppUriHandlerGroup",
      v29,
      *(__int64 *)v51);
  *v62 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v51);
  return 0;
}

```

## disassembly

```asm
0x18026a880  mov     [rsp-8+arg_18], r9
0x18026a885  mov     [rsp-8+arg_8], rdx
0x18026a88a  push    rbp
0x18026a88b  push    rbx
0x18026a88c  push    rsi
0x18026a88d  push    rdi
0x18026a88e  push    r12
0x18026a890  push    r14
0x18026a892  push    r15
0x18026a894  lea     rbp, [rsp-27h]
0x18026a899  sub     rsp, 0E0h
0x18026a8a0  xor     r15d, r15d
0x18026a8a3  mov     rsi, rdx
0x18026a8a6  mov     r12, rcx
0x18026a8a9  cmp     [rcx], r15
0x18026a8ac  jz      loc_18026AD50
0x18026a8b2  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18026a8b7  test    al, al
0x18026a8b9  jz      short loc_18026A8CA
0x18026a8bb  mov     ebx, 8067000Bh
0x18026a8c0  mov     edx, 202h
0x18026a8c5  jmp     loc_18026AD5A
0x18026a8ca  cmp     [rsi], r15
0x18026a8cd  jz      loc_18026AD49
0x18026a8d3  lea     rdx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026a8d7  mov     qword ptr [rbp+57h+var_98], r15
0x18026a8db  mov     rcx, r12; struct StateRepository::Database *
0x18026a8de  mov     [rbp+57h+var_90], r15
0x18026a8e2  mov     [rbp+57h+var_A0], r15
0x18026a8e6  call    ?Find@CacheDynamicAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Find(StateRepository::Database &,StateRepository::Statement &)
0x18026a8eb  mov     ebx, eax
0x18026a8ed  test    eax, eax
0x18026a8ef  jns     short loc_18026A90E
0x18026a8f1  mov     rcx, [rbp+5Fh]; this
0x18026a8f5  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026a8fc  mov     r9d, eax; char *
0x18026a8ff  mov     edx, 20Eh; void *
0x18026a904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a909  jmp     loc_18026AAB6
0x18026a90e  xorps   xmm0, xmm0
0x18026a911  mov     [rbp+57h+var_A8], r15
0x18026a915  xorps   xmm1, xmm1
0x18026a918  mov     [rbp+57h+arg_0], r15b
0x18026a91c  lea     r8, [rbp+57h+arg_0]; bool *
0x18026a920  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CacheDynamicAppUriHandlerGroup *
0x18026a924  lea     rcx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026a928  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18026a92d  movdqu  [rbp+57h+var_B8], xmm1
0x18026a932  call    ?FindNext@CacheDynamicAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheDynamicAppUriHandlerGroup::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheDynamicAppUriHandlerGroup &,bool &)
0x18026a937  mov     ebx, eax
0x18026a939  test    eax, eax
0x18026a93b  jns     short loc_18026A963
0x18026a93d  mov     rcx, [rbp+5Fh]; this
0x18026a941  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026a948  mov     r9d, eax; char *
0x18026a94b  mov     edx, 211h; void *
0x18026a950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a955  lea     rcx, [rbp+57h+var_B8+8]; this
0x18026a959  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026a95e  jmp     loc_18026AAB6
0x18026a963  mov     rbx, r15
0x18026a966  mov     rdi, r15
0x18026a969  mov     r14, r15
0x18026a96c  cmp     [rbp+57h+arg_0], r15b
0x18026a970  jz      loc_18026AAC4
0x18026a976  mov     rdx, [rbp+57h+var_C8]
0x18026a97a  lea     rax, [rbp+57h+arg_0]
0x18026a97e  xorps   xmm0, xmm0
0x18026a981  mov     [rsp+110h+var_F0], rax; int
0x18026a986  xorps   xmm1, xmm1
0x18026a989  lea     r9, [rbp+57h+var_88]
0x18026a98d  mov     rcx, rsi
0x18026a990  movdqu  [rbp+57h+var_88], xmm0
0x18026a995  movdqu  [rbp+57h+var_78], xmm1
0x18026a99a  call    ?Get@DynamicAppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow &,bool &)
0x18026a99f  mov     esi, eax
0x18026a9a1  test    eax, eax
0x18026a9a3  js      loc_18026AA80
0x18026a9a9  cmp     [rbp+57h+arg_0], r15b
0x18026a9ad  jz      short loc_18026A9F5
0x18026a9af  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18026a9b3  mov     [rbp+57h+var_68], r15
0x18026a9b7  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow *
0x18026a9bb  lea     rcx, [rbp+57h+var_C8]; struct StateRepository::Entity::CacheDynamicAppUriHandlerGroup *
0x18026a9bf  call    ?Cache_Check@CacheDynamicAppUriHandlerGroup@Entity@StateRepository@@CAJAEBV123@AEBVDynamicAppUriHandlerGroup_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Cache_Check(StateRepository::Entity::CacheDynamicAppUriHandlerGroup const &,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow const &,unsigned __int64 &)
0x18026a9c4  mov     esi, eax
0x18026a9c6  test    eax, eax
0x18026a9c8  js      loc_18026AA6B
0x18026a9ce  mov     r15, [rbp+57h+var_68]
0x18026a9d2  test    r15, r15
0x18026a9d5  jz      short loc_18026A9ED
0x18026a9d7  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026a9db  lea     rcx, [rbp+57h+var_98]; this
0x18026a9df  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026a9e4  mov     esi, eax
0x18026a9e6  test    eax, eax
0x18026a9e8  js      short loc_18026AA45
0x18026a9ea  add     rbx, r15
0x18026a9ed  inc     r14
0x18026a9f0  xor     r15d, r15d
0x18026a9f3  jmp     short loc_18026AA0B
0x18026a9f5  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026a9f9  lea     rcx, [rbp+57h+var_98]; this
0x18026a9fd  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026aa02  mov     esi, eax
0x18026aa04  test    eax, eax
0x18026aa06  js      short loc_18026AA79
0x18026aa08  inc     rbx
0x18026aa0b  lea     r8, [rbp+57h+arg_0]; bool *
0x18026aa0f  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CacheDynamicAppUriHandlerGroup *
0x18026aa13  lea     rcx, [rbp+57h+var_A0]; struct StateRepository::Statement *
0x18026aa17  call    ?FindNext@CacheDynamicAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheDynamicAppUriHandlerGroup::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheDynamicAppUriHandlerGroup &,bool &)
0x18026aa1c  mov     esi, eax
0x18026aa1e  test    eax, eax
0x18026aa20  js      short loc_18026AA72
0x18026aa22  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026aa26  inc     rdi
0x18026aa29  mov     rsi, [rbp+57h+arg_8]
0x18026aa2d  mov     qword ptr [rbp+57h+var_78+8], r15
0x18026aa31  test    rcx, rcx
0x18026aa34  jz      loc_18026A96C
0x18026aa3a  call    cs:__imp_SRCache_Free
0x18026aa40  jmp     loc_18026A96C
0x18026aa45  mov     rcx, [rbp+5Fh]; this
0x18026aa49  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026aa50  mov     r9d, esi; char *
0x18026aa53  mov     edx, 21Fh; void *
0x18026aa58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026aa5d  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026aa61  mov     qword ptr [rbp+57h+var_78+8], 0
0x18026aa69  jmp     short loc_18026AAA0
0x18026aa6b  mov     edx, 21Bh
0x18026aa70  jmp     short loc_18026AA85
0x18026aa72  mov     edx, 227h
0x18026aa77  jmp     short loc_18026AA85
0x18026aa79  mov     edx, 225h
0x18026aa7e  jmp     short loc_18026AA85
0x18026aa80  mov     edx, 216h; void *
0x18026aa85  mov     rcx, [rbp+5Fh]; this
0x18026aa89  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026aa90  mov     r9d, esi; char *
0x18026aa93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026aa98  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x18026aa9c  mov     qword ptr [rbp+57h+var_78+8], r15
0x18026aaa0  test    rcx, rcx
0x18026aaa3  jz      short loc_18026AAAB
0x18026aaa5  call    cs:__imp_SRCache_Free
0x18026aaab  lea     rcx, [rbp+57h+var_B8+8]; this
0x18026aaaf  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026aab4  mov     ebx, esi
0x18026aab6  lea     rcx, [rbp+57h+var_A0]; this
0x18026aaba  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026aabf  jmp     loc_18026ACD2
0x18026aac4  sub     rdi, r14
0x18026aac7  jz      short loc_18026AAF1
0x18026aac9  test    cs:byte_1804DF881, 20h
0x18026aad0  jz      short loc_18026AAF1
0x18026aad2  mov     rax, qword ptr [rbp+57h+var_98]
0x18026aad6  lea     r8, aCachedynamicap_0; "CacheDynamicAppUriHandlerGroup"
0x18026aadd  mov     r9, rdi
0x18026aae0  mov     [rsp+110h+var_F0], rax; int
0x18026aae5  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18026aaec  call    McTemplateU0sxs_EventWriteTransfer
0x18026aaf1  lea     rcx, [rbp+57h+var_B8+8]; this
0x18026aaf5  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026aafa  lea     rcx, [rbp+57h+var_A0]; this
0x18026aafe  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026ab03  lea     rcx, [rbp+57h+var_98]; this
0x18026ab07  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18026ab0c  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18026ab0f  mov     [rsp+110h+var_E0], r15
0x18026ab14  lea     rcx, [rsp+110h+var_E0]; this
0x18026ab19  mov     [rsp+110h+var_D8], r15d
0x18026ab1e  mov     [rbp+57h+var_D0], r15
0x18026ab22  call    ?Open@DynamicAppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18026ab27  mov     edi, eax
0x18026ab29  test    eax, eax
0x18026ab2b  jns     short loc_18026AB79
0x18026ab2d  mov     rcx, [rbp+5Fh]; this
0x18026ab31  lea     r8, aOnecoreBaseApp_133; "onecore\\base\\appmodel\\StateRepositor"...
0x18026ab38  mov     r9d, eax; char *
0x18026ab3b  mov     edx, 264h; void *
0x18026ab40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ab45  mov     rcx, [rbp+5Fh]; this
0x18026ab49  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026ab50  mov     r9d, edi; char *
0x18026ab53  mov     edx, 238h; void *
0x18026ab58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ab5d  mov     rcx, [rsp+110h+var_E0]
0x18026ab62  mov     [rsp+110h+var_E0], r15
0x18026ab67  test    rcx, rcx
0x18026ab6a  jz      short loc_18026AB72
0x18026ab6c  call    cs:__imp_SRCacheContext_Close
0x18026ab72  mov     ebx, edi
0x18026ab74  jmp     loc_18026ACD2
0x18026ab79  xorps   xmm0, xmm0
0x18026ab7c  mov     [rbp+57h+arg_0], r15b
0x18026ab80  xorps   xmm1, xmm1
0x18026ab83  lea     r9, [rbp+57h+arg_0]
0x18026ab87  lea     r8, [rbp+57h+var_C8]
0x18026ab8b  lea     rcx, [rsp+110h+var_E0]
0x18026ab90  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x18026ab95  movdqu  [rbp+57h+var_B8], xmm1
0x18026ab9a  call    ?Get@DynamicAppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandlerGroup_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow &,bool &)
0x18026ab9f  mov     edi, eax
0x18026aba1  test    eax, eax
0x18026aba3  jns     short loc_18026ABD2
0x18026aba5  mov     rcx, [rbp+5Fh]; this
0x18026aba9  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026abb0  mov     r9d, eax; char *
0x18026abb3  mov     edx, 23Bh; void *
0x18026abb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026abbd  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x18026abc1  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18026abc5  test    rcx, rcx
0x18026abc8  jz      short loc_18026AB5D
0x18026abca  call    cs:__imp_SRCache_Free
0x18026abd0  jmp     short loc_18026AB5D
0x18026abd2  mov     rdi, r15
0x18026abd5  cmp     [rbp+57h+arg_0], r15b
0x18026abd9  jz      loc_18026ACE0
0x18026abdf  mov     r9, [rbp+57h+var_C8]; char *
0x18026abe3  lea     rax, [rbp+57h+arg_0]
0x18026abe7  xorps   xmm0, xmm0
0x18026abea  mov     [rsp+110h+var_F0], rax; int
0x18026abef  xorps   xmm1, xmm1
0x18026abf2  mov     [rbp+57h+var_40], r15
0x18026abf6  xor     r8d, r8d; char *
0x18026abf9  lea     rdx, aSelectExistsSe_464; "SELECT EXISTS(SELECT 1 FROM CacheDynami"...
0x18026ac00  mov     rcx, r12; this
0x18026ac03  movdqu  [rbp+57h+var_60], xmm0
0x18026ac08  movdqu  [rbp+57h+var_50], xmm1
0x18026ac0d  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026ac12  mov     esi, eax
0x18026ac14  test    eax, eax
0x18026ac16  js      short loc_18026AC6F
0x18026ac18  cmp     [rbp+57h+arg_0], r15b
0x18026ac1c  jnz     short loc_18026AC37
0x18026ac1e  mov     rdx, [rbp+57h+var_C8]; __int64
0x18026ac22  lea     rcx, [rbp+57h+var_98]; this
0x18026ac26  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026ac2b  mov     esi, eax
0x18026ac2d  test    eax, eax
0x18026ac2f  js      short loc_18026AC61
0x18026ac31  inc     rdi
0x18026ac34  inc     rbx
0x18026ac37  inc     [rsp+110h+var_D8]
0x18026ac3b  lea     r9, [rbp+57h+arg_0]
0x18026ac3f  lea     r8, [rbp+57h+var_C8]
0x18026ac43  lea     rcx, [rsp+110h+var_E0]
0x18026ac48  call    ?Get@DynamicAppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandlerGroup_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerGroupIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow &,bool &)
0x18026ac4d  mov     esi, eax
0x18026ac4f  test    eax, eax
0x18026ac51  js      short loc_18026AC68
0x18026ac53  lea     rcx, [rbp+57h+var_50+8]; this
0x18026ac57  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026ac5c  jmp     loc_18026ABD5
0x18026ac61  mov     edx, 244h
0x18026ac66  jmp     short loc_18026AC8C
0x18026ac68  mov     edx, 246h
0x18026ac6d  jmp     short loc_18026AC8C
0x18026ac6f  mov     rcx, [rbp+5Fh]; this
0x18026ac73  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026ac7a  mov     r9d, esi; char *
0x18026ac7d  mov     edx, 52h ; 'R'; void *
0x18026ac82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ac87  mov     edx, 23Fh; void *
0x18026ac8c  mov     rcx, [rbp+5Fh]; this
0x18026ac90  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026ac97  mov     r9d, esi; char *
0x18026ac9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ac9f  lea     rcx, [rbp+57h+var_50+8]; this
0x18026aca3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026aca8  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x18026acac  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18026acb0  test    rcx, rcx
0x18026acb3  jz      short loc_18026ACBB
0x18026acb5  call    cs:__imp_SRCache_Free
0x18026acbb  mov     rcx, [rsp+110h+var_E0]
0x18026acc0  mov     [rsp+110h+var_E0], r15
0x18026acc5  test    rcx, rcx
0x18026acc8  jz      short loc_18026ACD0
0x18026acca  call    cs:__imp_SRCacheContext_Close
0x18026acd0  mov     ebx, esi
0x18026acd2  lea     rcx, [rbp+57h+var_98]; this
0x18026acd6  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026acdb  jmp     loc_18026AD6D
0x18026ace0  mov     rcx, qword ptr [rbp+57h+var_B8+8]
0x18026ace4  mov     qword ptr [rbp+57h+var_B8+8], r15
0x18026ace8  test    rcx, rcx
0x18026aceb  jz      short loc_18026ACF3
0x18026aced  call    cs:__imp_SRCache_Free
0x18026acf3  mov     rcx, [rsp+110h+var_E0]
0x18026acf8  mov     [rsp+110h+var_E0], r15
0x18026acfd  test    rcx, rcx
0x18026ad00  jz      short loc_18026AD08
0x18026ad02  call    cs:__imp_SRCacheContext_Close
0x18026ad08  test    rdi, rdi
0x18026ad0b  jz      short loc_18026AD35
0x18026ad0d  test    cs:byte_1804DF881, 20h
  ... truncated ...
```
