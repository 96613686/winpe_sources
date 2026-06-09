# StateRepository::Entity::CachePackageMachineStatus::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x1800a251c`
- end: `0x1800a28a5`
- name: `?Cache_Initialize@CachePackageMachineStatus@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `905`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a23d0`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x1800a251c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2573`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a25ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2642`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a26c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a274e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a285b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a286e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2881`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2894`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2573`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a25ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2642`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a26c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a274e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a285b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a286e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2881`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a2894`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a2552`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a25ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a2672`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a26f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a2797`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a2552`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a25ec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a2672`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a26f8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800a2797`

## string_xrefs

- `0x1800a2581`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800a2605`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800a268b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800a2711`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800a27b0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800a2599`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x1800a261d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x1800a26a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x1800a272e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageMachineStatus::Cache_Initialize(
        struct StateRepository::Cache::Manager_NoThrow *a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 *v19; // [rsp+20h] [rbp-28h] BYREF
  __int64 v20; // [rsp+28h] [rbp-20h] BYREF
  char v21; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v23; // [rsp+70h] [rbp+28h] BYREF
  __int64 v24; // [rsp+78h] [rbp+30h] BYREF
  __int64 v25; // [rsp+80h] [rbp+38h] BYREF
  __int64 v26; // [rsp+88h] [rbp+40h] BYREF

  v21 = 1;
  v2 = *(_QWORD *)a1;
  v19 = &v23;
  v23 = 0;
  v20 = 0;
  v3 = SRCacheContext_Create(v2, L"PackageMachineStatus", 0, &v20);
  if ( v21 )
  {
    v4 = *v19;
    *v19 = v20;
    if ( v4 )
      SRCacheContext_Close(v4);
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v19);
LABEL_6:
    v5 = v23;
    v23 = 0;
    if ( v5 )
      SRCacheContext_Close(v5);
    return (unsigned int)v3;
  }
  v7 = *(_QWORD *)a1;
  v19 = &v24;
  v24 = 0;
  v20 = 0;
  v21 = 1;
  v3 = SRCacheContext_Create(v7, L"PackageMachineStatus\\Data", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v19);
LABEL_11:
    v8 = v24;
    v24 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    goto LABEL_6;
  }
  v9 = *(_QWORD *)a1;
  v19 = &v26;
  v26 = 0;
  v20 = 0;
  v21 = 1;
  v3 = SRCacheContext_Create(v9, L"PackageMachineStatus\\Index", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v19);
LABEL_15:
    v10 = v26;
    v26 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    goto LABEL_11;
  }
  v11 = *(_QWORD *)a1;
  v19 = &v25;
  v25 = 0;
  v20 = 0;
  v21 = 1;
  v3 = SRCacheContext_Create(v11, L"PackageMachineStatus\\Index\\PackageFullName", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    v12 = 271;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageMachineStatus\\Index\\PackageFullName");
  if ( v3 < 0 )
  {
    v12 = 272;
    goto LABEL_19;
  }
  v14 = *(_QWORD *)a1;
  v19 = &v25;
  v20 = 0;
  v21 = 1;
  v3 = SRCacheContext_Create(v14, L"PackageMachineStatus\\Index\\PackageIdentity", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    v12 = 274;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageMachineStatus\\Index\\PackageIdentity");
  if ( v3 < 0 )
  {
    v12 = 275;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         L"PackageMachineStatus\\Index");
  if ( v3 < 0 )
  {
    v12 = 277;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"PackageMachineStatus\\Data");
  if ( v3 < 0 )
  {
    v12 = 278;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v23,
         L"PackageMachineStatus");
  if ( v3 < 0 )
  {
    v12 = 279;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    v13 = v25;
    v25 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_15;
  }
  v15 = v25;
  v25 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  v16 = v26;
  v26 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v24;
  v24 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v23;
  v23 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x1800a251c  push    rbp
0x1800a251e  push    rbx
0x1800a251f  push    rsi
0x1800a2520  push    rdi
0x1800a2521  mov     rbp, rsp
0x1800a2524  sub     rsp, 48h
0x1800a2528  mov     rdi, rcx
0x1800a252b  mov     [rbp+var_18], 1
0x1800a252f  mov     rcx, [rcx]
0x1800a2532  lea     rax, [rbp+arg_0]
0x1800a2536  xor     esi, esi
0x1800a2538  mov     [rbp+var_28], rax
0x1800a253c  lea     r9, [rbp+var_20]
0x1800a2540  mov     [rbp+arg_0], rsi
0x1800a2544  xor     r8d, r8d
0x1800a2547  mov     [rbp+var_20], rsi
0x1800a254b  lea     rdx, aPackagemachine_7; "PackageMachineStatus"
0x1800a2552  call    cs:__imp_SRCacheContext_Create
0x1800a2558  mov     ebx, eax
0x1800a255a  cmp     [rbp+var_18], sil
0x1800a255e  jz      short loc_1800A2579
0x1800a2560  mov     r8, [rbp+var_28]
0x1800a2564  mov     rdx, [rbp+var_20]
0x1800a2568  mov     rcx, [r8]
0x1800a256b  mov     [r8], rdx
0x1800a256e  test    rcx, rcx
0x1800a2571  jz      short loc_1800A2579
0x1800a2573  call    cs:__imp_SRCacheContext_Close
0x1800a2579  test    ebx, ebx
0x1800a257b  jns     short loc_1800A25C7
0x1800a257d  mov     rcx, [rbp+20h]; this
0x1800a2581  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800a2588  mov     r9d, ebx; char *
0x1800a258b  mov     edx, 1C2h; void *
0x1800a2590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2595  mov     rcx, [rbp+20h]; this
0x1800a2599  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x1800a25a0  mov     r9d, ebx; char *
0x1800a25a3  mov     edx, 107h; void *
0x1800a25a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a25ad  mov     rcx, [rbp+arg_0]
0x1800a25b1  mov     [rbp+arg_0], rsi
0x1800a25b5  test    rcx, rcx
0x1800a25b8  jz      short loc_1800A25C0
0x1800a25ba  call    cs:__imp_SRCacheContext_Close
0x1800a25c0  mov     eax, ebx
0x1800a25c2  jmp     loc_1800A289C
0x1800a25c7  mov     rcx, [rdi]
0x1800a25ca  lea     rax, [rbp+arg_8]
0x1800a25ce  lea     r9, [rbp+var_20]
0x1800a25d2  mov     [rbp+var_28], rax
0x1800a25d6  xor     r8d, r8d
0x1800a25d9  mov     [rbp+arg_8], rsi
0x1800a25dd  lea     rdx, aPackagemachine_8; "PackageMachineStatus\\Data"
0x1800a25e4  mov     [rbp+var_20], rsi
0x1800a25e8  mov     [rbp+var_18], 1
0x1800a25ec  call    cs:__imp_SRCacheContext_Create
0x1800a25f2  lea     rcx, [rbp+var_28]
0x1800a25f6  mov     ebx, eax
0x1800a25f8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a25fd  test    ebx, ebx
0x1800a25ff  jns     short loc_1800A264D
0x1800a2601  mov     rcx, [rbp+20h]; this
0x1800a2605  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800a260c  mov     r9d, ebx; char *
0x1800a260f  mov     edx, 1C2h; void *
0x1800a2614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2619  mov     rcx, [rbp+20h]; this
0x1800a261d  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x1800a2624  mov     r9d, ebx; char *
0x1800a2627  mov     edx, 10Ah; void *
0x1800a262c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2631  mov     rcx, [rbp+arg_8]
0x1800a2635  mov     [rbp+arg_8], rsi
0x1800a2639  test    rcx, rcx
0x1800a263c  jz      loc_1800A25AD
0x1800a2642  call    cs:__imp_SRCacheContext_Close
0x1800a2648  jmp     loc_1800A25AD
0x1800a264d  mov     rcx, [rdi]
0x1800a2650  lea     rax, [rbp+arg_18]
0x1800a2654  lea     r9, [rbp+var_20]
0x1800a2658  mov     [rbp+var_28], rax
0x1800a265c  xor     r8d, r8d
0x1800a265f  mov     [rbp+arg_18], rsi
0x1800a2663  lea     rdx, aPackagemachine_3; "PackageMachineStatus\\Index"
0x1800a266a  mov     [rbp+var_20], rsi
0x1800a266e  mov     [rbp+var_18], 1
0x1800a2672  call    cs:__imp_SRCacheContext_Create
0x1800a2678  lea     rcx, [rbp+var_28]
0x1800a267c  mov     ebx, eax
0x1800a267e  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a2683  test    ebx, ebx
0x1800a2685  jns     short loc_1800A26D3
0x1800a2687  mov     rcx, [rbp+20h]; this
0x1800a268b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800a2692  mov     r9d, ebx; char *
0x1800a2695  mov     edx, 1C2h; void *
0x1800a269a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a269f  mov     rcx, [rbp+20h]; this
0x1800a26a3  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x1800a26aa  mov     r9d, ebx; char *
0x1800a26ad  mov     edx, 10Dh; void *
0x1800a26b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a26b7  mov     rcx, [rbp+arg_18]
0x1800a26bb  mov     [rbp+arg_18], rsi
0x1800a26bf  test    rcx, rcx
0x1800a26c2  jz      loc_1800A2631
0x1800a26c8  call    cs:__imp_SRCacheContext_Close
0x1800a26ce  jmp     loc_1800A2631
0x1800a26d3  mov     rcx, [rdi]
0x1800a26d6  lea     rax, [rbp+arg_10]
0x1800a26da  lea     r9, [rbp+var_20]
0x1800a26de  mov     [rbp+var_28], rax
0x1800a26e2  xor     r8d, r8d
0x1800a26e5  mov     [rbp+arg_10], rsi
0x1800a26e9  lea     rdx, aPackagemachine_6; "PackageMachineStatus\\Index\\PackageFul"...
0x1800a26f0  mov     [rbp+var_20], rsi
0x1800a26f4  mov     [rbp+var_18], 1
0x1800a26f8  call    cs:__imp_SRCacheContext_Create
0x1800a26fe  lea     rcx, [rbp+var_28]
0x1800a2702  mov     ebx, eax
0x1800a2704  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a2709  test    ebx, ebx
0x1800a270b  jns     short loc_1800A2759
0x1800a270d  mov     rcx, [rbp+20h]; this
0x1800a2711  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800a2718  mov     r9d, ebx; char *
0x1800a271b  mov     edx, 1C2h; void *
0x1800a2720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2725  mov     edx, 10Fh; void *
0x1800a272a  mov     rcx, [rbp+20h]; this
0x1800a272e  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x1800a2735  mov     r9d, ebx; char *
0x1800a2738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a273d  mov     rcx, [rbp+arg_10]
0x1800a2741  mov     [rbp+arg_10], rsi
0x1800a2745  test    rcx, rcx
0x1800a2748  jz      loc_1800A26B7
0x1800a274e  call    cs:__imp_SRCacheContext_Close
0x1800a2754  jmp     loc_1800A26B7
0x1800a2759  lea     rdx, aPackagemachine_6; "PackageMachineStatus\\Index\\PackageFul"...
0x1800a2760  lea     rcx, [rbp+arg_10]; this
0x1800a2764  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a2769  mov     ebx, eax
0x1800a276b  test    eax, eax
0x1800a276d  jns     short loc_1800A2776
0x1800a276f  mov     edx, 110h
0x1800a2774  jmp     short loc_1800A272A
0x1800a2776  mov     rcx, [rdi]
0x1800a2779  lea     rax, [rbp+arg_10]
0x1800a277d  lea     r9, [rbp+var_20]
0x1800a2781  mov     [rbp+var_28], rax
0x1800a2785  xor     r8d, r8d
0x1800a2788  mov     [rbp+var_20], rsi
0x1800a278c  lea     rdx, aPackagemachine_12; "PackageMachineStatus\\Index\\PackageIde"...
0x1800a2793  mov     [rbp+var_18], 1
0x1800a2797  call    cs:__imp_SRCacheContext_Create
0x1800a279d  lea     rcx, [rbp+var_28]
0x1800a27a1  mov     ebx, eax
0x1800a27a3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800a27a8  test    ebx, ebx
0x1800a27aa  jns     short loc_1800A27CE
0x1800a27ac  mov     rcx, [rbp+20h]; this
0x1800a27b0  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800a27b7  mov     r9d, ebx; char *
0x1800a27ba  mov     edx, 1C2h; void *
0x1800a27bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a27c4  mov     edx, 112h
0x1800a27c9  jmp     loc_1800A272A
0x1800a27ce  lea     rdx, aPackagemachine_12; "PackageMachineStatus\\Index\\PackageIde"...
0x1800a27d5  lea     rcx, [rbp+arg_10]; this
0x1800a27d9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a27de  mov     ebx, eax
0x1800a27e0  test    eax, eax
0x1800a27e2  jns     short loc_1800A27EE
0x1800a27e4  mov     edx, 113h
0x1800a27e9  jmp     loc_1800A272A
0x1800a27ee  lea     rdx, aPackagemachine_3; "PackageMachineStatus\\Index"
0x1800a27f5  lea     rcx, [rbp+arg_18]; this
0x1800a27f9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a27fe  mov     ebx, eax
0x1800a2800  test    eax, eax
0x1800a2802  jns     short loc_1800A280E
0x1800a2804  mov     edx, 115h
0x1800a2809  jmp     loc_1800A272A
0x1800a280e  lea     rdx, aPackagemachine_8; "PackageMachineStatus\\Data"
0x1800a2815  lea     rcx, [rbp+arg_8]; this
0x1800a2819  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a281e  mov     ebx, eax
0x1800a2820  test    eax, eax
0x1800a2822  jns     short loc_1800A282E
0x1800a2824  mov     edx, 116h
0x1800a2829  jmp     loc_1800A272A
0x1800a282e  lea     rdx, aPackagemachine_7; "PackageMachineStatus"
0x1800a2835  lea     rcx, [rbp+arg_0]; this
0x1800a2839  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800a283e  mov     ebx, eax
0x1800a2840  test    eax, eax
0x1800a2842  jns     short loc_1800A284E
0x1800a2844  mov     edx, 117h
0x1800a2849  jmp     loc_1800A272A
0x1800a284e  mov     rcx, [rbp+arg_10]
0x1800a2852  mov     [rbp+arg_10], rsi
0x1800a2856  test    rcx, rcx
0x1800a2859  jz      short loc_1800A2861
0x1800a285b  call    cs:__imp_SRCacheContext_Close
0x1800a2861  mov     rcx, [rbp+arg_18]
0x1800a2865  mov     [rbp+arg_18], rsi
0x1800a2869  test    rcx, rcx
0x1800a286c  jz      short loc_1800A2874
0x1800a286e  call    cs:__imp_SRCacheContext_Close
0x1800a2874  mov     rcx, [rbp+arg_8]
0x1800a2878  mov     [rbp+arg_8], rsi
0x1800a287c  test    rcx, rcx
0x1800a287f  jz      short loc_1800A2887
0x1800a2881  call    cs:__imp_SRCacheContext_Close
0x1800a2887  mov     rcx, [rbp+arg_0]
0x1800a288b  mov     [rbp+arg_0], rsi
0x1800a288f  test    rcx, rcx
0x1800a2892  jz      short loc_1800A289A
0x1800a2894  call    cs:__imp_SRCacheContext_Close
0x1800a289a  xor     eax, eax
0x1800a289c  add     rsp, 48h
0x1800a28a0  pop     rdi
0x1800a28a1  pop     rsi
0x1800a28a2  pop     rbx
0x1800a28a3  pop     rbp
0x1800a28a4  retn
```
