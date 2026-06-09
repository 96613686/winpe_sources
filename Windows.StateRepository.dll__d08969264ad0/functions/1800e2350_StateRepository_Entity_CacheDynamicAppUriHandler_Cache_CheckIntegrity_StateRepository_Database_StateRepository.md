# StateRepository::Entity::CacheDynamicAppUriHandler::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1800e2350`
- end: `0x1800e2831`
- name: `?Cache_CheckIntegrity@CacheDynamicAppUriHandler@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1249`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800ae890`
- `0x1800e2350`
- `0x1800e2838`
- `0x1800e2894`
- `0x18026544c`
- `0x180269674`
- `0x180269934`
- `0x180269980`
- `0x1802699f0`
- `0x180269ab8`
- `0x180269b98`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e2623`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e2780`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e27b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e2623`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e2780`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800e27b0`

## string_xrefs

- `0x1800e25e8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x1800e23c9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e241f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e2543`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e2600`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e2667`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e2732`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e274f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e280e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler.cpp`
- `0x1800e2589`: `CacheDynamicAppUriHandler`
- `0x1800e27c9`: `CacheDynamicAppUriHandler`
- `0x1800e26b5`: `SELECT EXISTS(SELECT 1 FROM CacheDynamicAppUriHandler WHERE _CacheDynamicAppUriHandlerID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheDynamicAppUriHandler::Cache_CheckIntegrity(
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
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rdi
  int v29; // eax
  __int64 v30; // rdx
  char v31; // r8
  int v32; // esi
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rcx
  bool *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  bool *v44; // [rsp+28h] [rbp-D8h]
  __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  int v46; // [rsp+38h] [rbp-C8h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  int v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h]
  char *v51[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v52; // [rsp+70h] [rbp-90h]
  __int128 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+90h] [rbp-70h]
  unsigned __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v56[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  _OWORD v58[7]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  bool v60; // [rsp+150h] [rbp+50h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v61; // [rsp+158h] [rbp+58h]
  _QWORD *v62; // [rsp+168h] [rbp+68h]

  v62 = a4;
  v61 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 758;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 759;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
      (const char *)v6,
      (int)v41);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 760;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v49 = 0;
  v50 = 0;
  v48 = 0;
  v8 = StateRepository::Entity::CacheDynamicAppUriHandler::Find(a1, (struct StateRepository::Statement *)&v48);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x303,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v49);
    return v6;
  }
  v60 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  Next = StateRepository::Entity::CacheDynamicAppUriHandler::FindNext(
           (struct StateRepository::Statement *)&v48,
           (struct StateRepository::Entity::CacheDynamicAppUriHandler *)v51,
           &v60);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
      (const char *)(unsigned int)Next,
      (int)v41);
    StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler((StateRepository::Entity::CacheDynamicAppUriHandler *)v51);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v60 )
  {
    v41 = &v60;
    v57 = 0;
    memset(v56, 0, sizeof(v56));
    appended = StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Get(v4, v51[0], v11, v56);
    if ( appended < 0 )
    {
      v19 = 779;
      goto LABEL_27;
    }
    if ( v60 )
    {
      v55 = 0;
      appended = StateRepository::Entity::CacheDynamicAppUriHandler::Cache_Check(
                   (const struct StateRepository::Entity::CacheDynamicAppUriHandler *)v51,
                   (const struct StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v56,
                   &v55);
      if ( appended < 0 )
      {
        v19 = 784;
        goto LABEL_27;
      }
      v18 = v55;
      if ( v55 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v51[0], v17);
        if ( appended < 0 )
        {
          v19 = 788;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
            (const char *)(unsigned int)appended,
            (int)&v60);
          StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v56);
          StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler((StateRepository::Entity::CacheDynamicAppUriHandler *)v51);
          v6 = appended;
          goto LABEL_28;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v51[0], v16);
      if ( appended < 0 )
      {
        v19 = 794;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheDynamicAppUriHandler::FindNext(
                 (struct StateRepository::Statement *)&v48,
                 (struct StateRepository::Entity::CacheDynamicAppUriHandler *)v51,
                 &v60);
    if ( appended < 0 )
    {
      v19 = 796;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v56);
    v4 = v61;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheDynamicAppUriHandler",
      v20,
      *(__int64 *)v49);
  StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler((StateRepository::Entity::CacheDynamicAppUriHandler *)v51);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
  StateRepository::TextA::Clear((StateRepository::TextA *)v49);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v21 = StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow *)&v45,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v21,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
      (const char *)v23,
      v42);
LABEL_34:
    v26 = v45;
    v45 = 0;
    if ( v26 )
      SRCacheContext_Close(v26, v24, v25);
    v6 = v23;
    goto LABEL_53;
  }
  *(_QWORD *)&v53 = 0;
  v60 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  v27 = StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Get(&v45, v22, v51, &v60);
  v23 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x330,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
    StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v51);
    goto LABEL_34;
  }
  v28 = 0;
  while ( v60 )
  {
    memset(v58, 0, 64);
    v29 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheDynamicAppUriHandler WHERE _CacheDynami"
                                                "cAppUriHandlerID=? LIMIT 1);",
            0,
            v51[0],
            (__int64)&v60,
            v44);
    v32 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
        (const char *)(unsigned int)v29,
        v43);
      v33 = 820;
      goto LABEL_50;
    }
    if ( !v60 )
    {
      v32 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v51[0], v31);
      if ( v32 < 0 )
      {
        v33 = 825;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler.cpp",
          (const char *)(unsigned int)v32,
          v43);
        StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler((StateRepository::Entity::CacheDynamicAppUriHandler *)v58);
        StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v51);
        v36 = v45;
        v45 = 0;
        if ( v36 )
          SRCacheContext_Close(v36, v34, v35);
        v6 = v32;
        goto LABEL_53;
      }
      ++v28;
      ++v12;
    }
    ++v46;
    v32 = StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Get(&v45, v30, v51, &v60);
    if ( v32 < 0 )
    {
      v33 = 827;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler((StateRepository::Entity::CacheDynamicAppUriHandler *)v58);
  }
  StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)v51);
  v39 = v45;
  v45 = 0;
  if ( v39 )
    SRCacheContext_Close(v39, v37, v38);
  if ( v28 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v39,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheDynamicAppUriHandler",
      v28,
      *(__int64 *)v49);
  *v62 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v49);
  return 0;
}

```

## disassembly

```asm
0x1800e2350  mov     [rsp-8+arg_18], r9
0x1800e2355  mov     [rsp-8+arg_8], rdx
0x1800e235a  push    rbp
0x1800e235b  push    rbx
0x1800e235c  push    rsi
0x1800e235d  push    rdi
0x1800e235e  push    r12
0x1800e2360  push    r14
0x1800e2362  push    r15
0x1800e2364  lea     rbp, [rsp-10h]
0x1800e2369  sub     rsp, 110h
0x1800e2370  xor     r15d, r15d
0x1800e2373  mov     rsi, rdx
0x1800e2376  mov     r12, rcx
0x1800e2379  cmp     [rcx], r15
0x1800e237c  jz      loc_1800E2800
0x1800e2382  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800e2387  test    al, al
0x1800e2389  jz      short loc_1800E239A
0x1800e238b  mov     ebx, 8067000Bh
0x1800e2390  mov     edx, 2F7h
0x1800e2395  jmp     loc_1800E280A
0x1800e239a  cmp     [rsi], r15
0x1800e239d  jz      loc_1800E27F9
0x1800e23a3  lea     rdx, [rsp+140h+var_F8]; struct StateRepository::Statement *
0x1800e23a8  mov     qword ptr [rsp+140h+var_F0], r15
0x1800e23ad  mov     rcx, r12; struct StateRepository::Database *
0x1800e23b0  mov     [rsp+140h+var_E8], r15
0x1800e23b5  mov     [rsp+140h+var_F8], r15
0x1800e23ba  call    ?Find@CacheDynamicAppUriHandler@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheDynamicAppUriHandler::Find(StateRepository::Database &,StateRepository::Statement &)
0x1800e23bf  mov     ebx, eax
0x1800e23c1  test    eax, eax
0x1800e23c3  jns     short loc_1800E23E2
0x1800e23c5  mov     rcx, [rbp+48h]; this
0x1800e23c9  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e23d0  mov     r9d, eax; char *
0x1800e23d3  mov     edx, 303h; void *
0x1800e23d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e23dd  jmp     loc_1800E2567
0x1800e23e2  xorps   xmm0, xmm0
0x1800e23e5  mov     [rbp+40h+arg_0], r15b
0x1800e23e9  xorps   xmm1, xmm1
0x1800e23ec  movdqa  xmmword ptr [rsp+140h+var_E0], xmm0
0x1800e23f2  lea     r8, [rbp+40h+arg_0]; bool *
0x1800e23f6  movdqa  [rsp+140h+var_D0], xmm1
0x1800e23fc  lea     rdx, [rsp+140h+var_E0]; struct StateRepository::Entity::CacheDynamicAppUriHandler *
0x1800e2401  movdqa  [rbp+40h+var_C0], xmm0
0x1800e2406  lea     rcx, [rsp+140h+var_F8]; struct StateRepository::Statement *
0x1800e240b  movdqa  [rbp+40h+var_B0], xmm1
0x1800e2410  call    ?FindNext@CacheDynamicAppUriHandler@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheDynamicAppUriHandler::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheDynamicAppUriHandler &,bool &)
0x1800e2415  mov     ebx, eax
0x1800e2417  test    eax, eax
0x1800e2419  jns     short loc_1800E2442
0x1800e241b  mov     rcx, [rbp+48h]; this
0x1800e241f  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e2426  mov     r9d, eax; char *
0x1800e2429  mov     edx, 306h; void *
0x1800e242e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2433  lea     rcx, [rsp+140h+var_E0]; this
0x1800e2438  call    ??1CacheDynamicAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler(void)
0x1800e243d  jmp     loc_1800E2567
0x1800e2442  mov     rbx, r15
0x1800e2445  mov     rdi, r15
0x1800e2448  mov     r14, r15
0x1800e244b  cmp     [rbp+40h+arg_0], r15b
0x1800e244f  jz      loc_1800E2576
0x1800e2455  mov     rdx, [rsp+140h+var_E0]
0x1800e245a  lea     rax, [rbp+40h+arg_0]
0x1800e245e  xorps   xmm0, xmm0
0x1800e2461  mov     [rsp+140h+var_120], rax; int
0x1800e2466  xorps   xmm1, xmm1
0x1800e2469  mov     [rbp+40h+var_78], r15
0x1800e246d  lea     r9, [rbp+40h+var_98]
0x1800e2471  mov     rcx, rsi
0x1800e2474  movdqu  [rbp+40h+var_98], xmm0
0x1800e2479  movdqu  [rbp+40h+var_88], xmm1
0x1800e247e  call    ?Get@DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow &,bool &)
0x1800e2483  mov     esi, eax
0x1800e2485  test    eax, eax
0x1800e2487  js      loc_1800E253A
0x1800e248d  cmp     [rbp+40h+arg_0], r15b
0x1800e2491  jz      short loc_1800E24D8
0x1800e2493  lea     r8, [rbp+40h+var_A0]; unsigned __int64 *
0x1800e2497  mov     [rbp+40h+var_A0], r15
0x1800e249b  lea     rdx, [rbp+40h+var_98]; struct StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *
0x1800e249f  lea     rcx, [rsp+140h+var_E0]; struct StateRepository::Entity::CacheDynamicAppUriHandler *
0x1800e24a4  call    ?Cache_Check@CacheDynamicAppUriHandler@Entity@StateRepository@@CAJAEBV123@AEBVDynamicAppUriHandler_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheDynamicAppUriHandler::Cache_Check(StateRepository::Entity::CacheDynamicAppUriHandler const &,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow const &,unsigned __int64 &)
0x1800e24a9  mov     esi, eax
0x1800e24ab  test    eax, eax
0x1800e24ad  js      short loc_1800E2525
0x1800e24af  mov     r15, [rbp+40h+var_A0]
0x1800e24b3  test    r15, r15
0x1800e24b6  jz      short loc_1800E24D0
0x1800e24b8  mov     rdx, [rsp+140h+var_E0]; __int64
0x1800e24bd  lea     rcx, [rsp+140h+var_F0]; this
0x1800e24c2  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800e24c7  mov     esi, eax
0x1800e24c9  test    eax, eax
0x1800e24cb  js      short loc_1800E251E
0x1800e24cd  add     rbx, r15
0x1800e24d0  inc     r14
0x1800e24d3  xor     r15d, r15d
0x1800e24d6  jmp     short loc_1800E24F0
0x1800e24d8  mov     rdx, [rsp+140h+var_E0]; __int64
0x1800e24dd  lea     rcx, [rsp+140h+var_F0]; this
0x1800e24e2  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800e24e7  mov     esi, eax
0x1800e24e9  test    eax, eax
0x1800e24eb  js      short loc_1800E2533
0x1800e24ed  inc     rbx
0x1800e24f0  lea     r8, [rbp+40h+arg_0]; bool *
0x1800e24f4  lea     rdx, [rsp+140h+var_E0]; struct StateRepository::Entity::CacheDynamicAppUriHandler *
0x1800e24f9  lea     rcx, [rsp+140h+var_F8]; struct StateRepository::Statement *
0x1800e24fe  call    ?FindNext@CacheDynamicAppUriHandler@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheDynamicAppUriHandler::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheDynamicAppUriHandler &,bool &)
0x1800e2503  mov     esi, eax
0x1800e2505  test    eax, eax
0x1800e2507  js      short loc_1800E252C
0x1800e2509  inc     rdi
0x1800e250c  lea     rcx, [rbp+40h+var_98]; this
0x1800e2510  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x1800e2515  mov     rsi, [rbp+40h+arg_8]
0x1800e2519  jmp     loc_1800E244B
0x1800e251e  mov     edx, 314h
0x1800e2523  jmp     short loc_1800E253F
0x1800e2525  mov     edx, 310h
0x1800e252a  jmp     short loc_1800E253F
0x1800e252c  mov     edx, 31Ch
0x1800e2531  jmp     short loc_1800E253F
0x1800e2533  mov     edx, 31Ah
0x1800e2538  jmp     short loc_1800E253F
0x1800e253a  mov     edx, 30Bh; void *
0x1800e253f  mov     rcx, [rbp+48h]; this
0x1800e2543  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e254a  mov     r9d, esi; char *
0x1800e254d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2552  lea     rcx, [rbp+40h+var_98]; this
0x1800e2556  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x1800e255b  lea     rcx, [rsp+140h+var_E0]; this
0x1800e2560  call    ??1CacheDynamicAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler(void)
0x1800e2565  mov     ebx, esi
0x1800e2567  lea     rcx, [rsp+140h+var_F8]; this
0x1800e256c  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800e2571  jmp     loc_1800E2788
0x1800e2576  sub     rdi, r14
0x1800e2579  jz      short loc_1800E25A4
0x1800e257b  test    cs:byte_1804DF881, 20h
0x1800e2582  jz      short loc_1800E25A4
0x1800e2584  mov     rax, qword ptr [rsp+140h+var_F0]
0x1800e2589  lea     r8, aCachedynamicap; "CacheDynamicAppUriHandler"
0x1800e2590  mov     r9, rdi
0x1800e2593  mov     [rsp+140h+var_120], rax; int
0x1800e2598  lea     rdx, CacheIntegrity_MissingCacheEntries
0x1800e259f  call    McTemplateU0sxs_EventWriteTransfer
0x1800e25a4  lea     rcx, [rsp+140h+var_E0]; this
0x1800e25a9  call    ??1CacheDynamicAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler(void)
0x1800e25ae  lea     rcx, [rsp+140h+var_F8]; this
0x1800e25b3  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800e25b8  lea     rcx, [rsp+140h+var_F0]; this
0x1800e25bd  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x1800e25c2  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800e25c5  mov     [rsp+140h+var_110], r15
0x1800e25ca  lea     rcx, [rsp+140h+var_110]; this
0x1800e25cf  mov     [rsp+140h+var_108], r15d
0x1800e25d4  mov     [rsp+140h+var_100], r15
0x1800e25d9  call    ?Open@DynamicAppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x1800e25de  mov     edi, eax
0x1800e25e0  test    eax, eax
0x1800e25e2  jns     short loc_1800E2630
0x1800e25e4  mov     rcx, [rbp+48h]; this
0x1800e25e8  lea     r8, aOnecoreBaseApp_344; "onecore\\base\\appmodel\\StateRepositor"...
0x1800e25ef  mov     r9d, eax; char *
0x1800e25f2  mov     edx, 3A3h; void *
0x1800e25f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e25fc  mov     rcx, [rbp+48h]; this
0x1800e2600  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e2607  mov     r9d, edi; char *
0x1800e260a  mov     edx, 32Dh; void *
0x1800e260f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2614  mov     rcx, [rsp+140h+var_110]
0x1800e2619  mov     [rsp+140h+var_110], r15
0x1800e261e  test    rcx, rcx
0x1800e2621  jz      short loc_1800E2629
0x1800e2623  call    cs:__imp_SRCacheContext_Close
0x1800e2629  mov     ebx, edi
0x1800e262b  jmp     loc_1800E2788
0x1800e2630  xorps   xmm0, xmm0
0x1800e2633  mov     qword ptr [rbp+40h+var_C0], r15
0x1800e2637  xorps   xmm1, xmm1
0x1800e263a  mov     [rbp+40h+arg_0], r15b
0x1800e263e  lea     r9, [rbp+40h+arg_0]
0x1800e2642  lea     r8, [rsp+140h+var_E0]
0x1800e2647  lea     rcx, [rsp+140h+var_110]
0x1800e264c  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x1800e2652  movdqu  [rsp+140h+var_D0], xmm1
0x1800e2658  call    ?Get@DynamicAppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow &,bool &)
0x1800e265d  mov     edi, eax
0x1800e265f  test    eax, eax
0x1800e2661  jns     short loc_1800E2687
0x1800e2663  mov     rcx, [rbp+48h]; this
0x1800e2667  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e266e  mov     r9d, eax; char *
0x1800e2671  mov     edx, 330h; void *
0x1800e2676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e267b  lea     rcx, [rsp+140h+var_E0]; this
0x1800e2680  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x1800e2685  jmp     short loc_1800E2614
0x1800e2687  mov     rdi, r15
0x1800e268a  cmp     [rbp+40h+arg_0], r15b
0x1800e268e  jz      loc_1800E2797
0x1800e2694  mov     r9, [rsp+140h+var_E0]; char *
0x1800e2699  lea     rax, [rbp+40h+arg_0]
0x1800e269d  xorps   xmm0, xmm0
0x1800e26a0  mov     [rsp+140h+var_120], rax; int
0x1800e26a5  xorps   xmm1, xmm1
0x1800e26a8  movdqa  [rbp+40h+var_70], xmm0
0x1800e26ad  xor     r8d, r8d; char *
0x1800e26b0  movdqa  [rbp+40h+var_60], xmm1
0x1800e26b5  lea     rdx, aSelectExistsSe_145; "SELECT EXISTS(SELECT 1 FROM CacheDynami"...
0x1800e26bc  movdqa  [rbp+40h+var_50], xmm0
0x1800e26c1  mov     rcx, r12; this
0x1800e26c4  movdqa  [rbp+40h+var_40], xmm1
0x1800e26c9  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x1800e26ce  mov     esi, eax
0x1800e26d0  test    eax, eax
0x1800e26d2  js      short loc_1800E272E
0x1800e26d4  cmp     [rbp+40h+arg_0], r15b
0x1800e26d8  jnz     short loc_1800E26F5
0x1800e26da  mov     rdx, [rsp+140h+var_E0]; __int64
0x1800e26df  lea     rcx, [rsp+140h+var_F0]; this
0x1800e26e4  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800e26e9  mov     esi, eax
0x1800e26eb  test    eax, eax
0x1800e26ed  js      short loc_1800E2720
0x1800e26ef  inc     rdi
0x1800e26f2  inc     rbx
0x1800e26f5  inc     [rsp+140h+var_108]
0x1800e26f9  lea     r9, [rbp+40h+arg_0]
0x1800e26fd  lea     r8, [rsp+140h+var_E0]
0x1800e2702  lea     rcx, [rsp+140h+var_110]
0x1800e2707  call    ?Get@DynamicAppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DynamicAppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Get(StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow &,bool &)
0x1800e270c  mov     esi, eax
0x1800e270e  test    eax, eax
0x1800e2710  js      short loc_1800E2727
0x1800e2712  lea     rcx, [rbp+40h+var_70]; this
0x1800e2716  call    ??1CacheDynamicAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler(void)
0x1800e271b  jmp     loc_1800E268A
0x1800e2720  mov     edx, 339h
0x1800e2725  jmp     short loc_1800E274B
0x1800e2727  mov     edx, 33Bh
0x1800e272c  jmp     short loc_1800E274B
0x1800e272e  mov     rcx, [rbp+48h]; this
0x1800e2732  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e2739  mov     r9d, esi; char *
0x1800e273c  mov     edx, 74h ; 't'; void *
0x1800e2741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2746  mov     edx, 334h; void *
0x1800e274b  mov     rcx, [rbp+48h]; this
0x1800e274f  lea     r8, aOnecoreBaseApp_190; "onecore\\base\\appmodel\\staterepositor"...
0x1800e2756  mov     r9d, esi; char *
0x1800e2759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e275e  lea     rcx, [rbp+40h+var_70]; this
0x1800e2762  call    ??1CacheDynamicAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheDynamicAppUriHandler::~CacheDynamicAppUriHandler(void)
0x1800e2767  lea     rcx, [rsp+140h+var_E0]; this
0x1800e276c  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x1800e2771  mov     rcx, [rsp+140h+var_110]
0x1800e2776  mov     [rsp+140h+var_110], r15
0x1800e277b  test    rcx, rcx
0x1800e277e  jz      short loc_1800E2786
0x1800e2780  call    cs:__imp_SRCacheContext_Close
0x1800e2786  mov     ebx, esi
0x1800e2788  lea     rcx, [rsp+140h+var_F0]; this
0x1800e278d  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800e2792  jmp     loc_1800E281D
0x1800e2797  lea     rcx, [rsp+140h+var_E0]; this
0x1800e279c  call    ??1DynamicAppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow(void)
0x1800e27a1  mov     rcx, [rsp+140h+var_110]
0x1800e27a6  mov     [rsp+140h+var_110], r15
0x1800e27ab  test    rcx, rcx
0x1800e27ae  jz      short loc_1800E27B6
0x1800e27b0  call    cs:__imp_SRCacheContext_Close
0x1800e27b6  test    rdi, rdi
0x1800e27b9  jz      short loc_1800E27E4
0x1800e27bb  test    cs:byte_1804DF881, 20h
0x1800e27c2  jz      short loc_1800E27E4
0x1800e27c4  mov     rax, qword ptr [rsp+140h+var_F0]
0x1800e27c9  lea     r8, aCachedynamicap; "CacheDynamicAppUriHandler"
0x1800e27d0  mov     r9, rdi
0x1800e27d3  mov     [rsp+140h+var_120], rax
0x1800e27d8  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x1800e27df  call    McTemplateU0sxs_EventWriteTransfer
0x1800e27e4  mov     rax, [rbp+40h+arg_18]
0x1800e27e8  lea     rcx, [rsp+140h+var_F0]; this
0x1800e27ed  mov     [rax], rbx
0x1800e27f0  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800e27f5  xor     eax, eax
0x1800e27f7  jmp     short loc_1800E281F
0x1800e27f9  mov     edx, 2F8h
0x1800e27fe  jmp     short loc_1800E2805
0x1800e2800  mov     edx, 2F6h; void *
0x1800e2805  mov     ebx, 8007139Fh
  ... truncated ...
```
