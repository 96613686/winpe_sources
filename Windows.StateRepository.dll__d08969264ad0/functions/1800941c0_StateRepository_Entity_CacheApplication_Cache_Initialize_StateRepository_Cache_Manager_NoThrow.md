# StateRepository::Entity::CacheApplication::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x1800941c0`
- end: `0x180094549`
- name: `?Cache_Initialize@CacheApplication@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `905`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180093f10`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x1800941c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094217`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009425e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800942e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009436c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800943f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800944ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094512`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094525`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094538`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094217`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009425e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800942e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009436c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800943f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800944ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094512`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094525`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180094538`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800941f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180094290`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180094316`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009439c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009443b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800941f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180094290`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180094316`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009439c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009443b`

## string_xrefs

- `0x18009423d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x1800942c1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180094347`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x1800943d2`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180094225`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800942a9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18009432f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800943b5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180094454`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheApplication::Cache_Initialize(
        struct StateRepository::Cache::Manager_NoThrow *a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 *v25; // [rsp+20h] [rbp-28h] BYREF
  __int64 v26; // [rsp+28h] [rbp-20h] BYREF
  char v27; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v29; // [rsp+70h] [rbp+28h] BYREF
  __int64 v30; // [rsp+78h] [rbp+30h] BYREF
  __int64 v31; // [rsp+80h] [rbp+38h] BYREF
  __int64 v32; // [rsp+88h] [rbp+40h] BYREF

  v27 = 1;
  v2 = *(_QWORD *)a1;
  v25 = &v29;
  v29 = 0;
  v26 = 0;
  v3 = SRCacheContext_Create(v2, L"Application", 0, &v26);
  if ( v27 )
  {
    v4 = v25;
    v5 = v26;
    v6 = *v25;
    *v25 = v26;
    if ( v6 )
      SRCacheContext_Close(v6, v5, v4);
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)v3,
      (int)v25);
LABEL_6:
    v9 = v29;
    v29 = 0;
    if ( v9 )
      SRCacheContext_Close(v9, v7, v8);
    return (unsigned int)v3;
  }
  v11 = *(_QWORD *)a1;
  v25 = &v30;
  v30 = 0;
  v26 = 0;
  v27 = 1;
  v3 = SRCacheContext_Create(v11, L"Application\\Data", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)v3,
      (int)v25);
LABEL_11:
    v12 = v30;
    v30 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v7, v8);
    goto LABEL_6;
  }
  v13 = *(_QWORD *)a1;
  v25 = &v32;
  v32 = 0;
  v26 = 0;
  v27 = 1;
  v3 = SRCacheContext_Create(v13, L"Application\\Index", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)v3,
      (int)v25);
LABEL_15:
    v14 = v32;
    v32 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v7, v8);
    goto LABEL_11;
  }
  v15 = *(_QWORD *)a1;
  v25 = &v31;
  v31 = 0;
  v26 = 0;
  v27 = 1;
  v3 = SRCacheContext_Create(v15, L"Application\\Index\\Package", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    v16 = 594;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v31,
         L"Application\\Index\\Package");
  if ( v3 < 0 )
  {
    v16 = 595;
    goto LABEL_19;
  }
  v18 = *(_QWORD *)a1;
  v25 = &v31;
  v26 = 0;
  v27 = 1;
  v3 = SRCacheContext_Create(v18, L"Application\\Index\\PackageAndPackageRelativeApplicationId", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    v16 = 597;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v31,
         L"Application\\Index\\PackageAndPackageRelativeApplicationId");
  if ( v3 < 0 )
  {
    v16 = 598;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v32,
         L"Application\\Index");
  if ( v3 < 0 )
  {
    v16 = 600;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v30,
         L"Application\\Data");
  if ( v3 < 0 )
  {
    v16 = 601;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v29,
         L"Application");
  if ( v3 < 0 )
  {
    v16 = 602;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    v17 = v31;
    v31 = 0;
    if ( v17 )
      SRCacheContext_Close(v17, v7, v8);
    goto LABEL_15;
  }
  v21 = v31;
  v31 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v19, v20);
  v22 = v32;
  v32 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v19, v20);
  v23 = v30;
  v30 = 0;
  if ( v23 )
    SRCacheContext_Close(v23, v19, v20);
  v24 = v29;
  v29 = 0;
  if ( v24 )
    SRCacheContext_Close(v24, v19, v20);
  return 0;
}

```

## disassembly

```asm
0x1800941c0  push    rbp
0x1800941c2  push    rbx
0x1800941c3  push    rsi
0x1800941c4  push    rdi
0x1800941c5  mov     rbp, rsp
0x1800941c8  sub     rsp, 48h
0x1800941cc  mov     rdi, rcx
0x1800941cf  mov     [rbp+var_18], 1
0x1800941d3  mov     rcx, [rcx]
0x1800941d6  lea     rax, [rbp+arg_0]
0x1800941da  xor     esi, esi
0x1800941dc  mov     [rbp+var_28], rax
0x1800941e0  lea     r9, [rbp+var_20]
0x1800941e4  mov     [rbp+arg_0], rsi
0x1800941e8  xor     r8d, r8d
0x1800941eb  mov     [rbp+var_20], rsi
0x1800941ef  lea     rdx, aApplication_0; "Application"
0x1800941f6  call    cs:__imp_SRCacheContext_Create
0x1800941fc  mov     ebx, eax
0x1800941fe  cmp     [rbp+var_18], sil
0x180094202  jz      short loc_18009421D
0x180094204  mov     r8, [rbp+var_28]
0x180094208  mov     rdx, [rbp+var_20]
0x18009420c  mov     rcx, [r8]
0x18009420f  mov     [r8], rdx
0x180094212  test    rcx, rcx
0x180094215  jz      short loc_18009421D
0x180094217  call    cs:__imp_SRCacheContext_Close
0x18009421d  test    ebx, ebx
0x18009421f  jns     short loc_18009426B
0x180094221  mov     rcx, [rbp+20h]; this
0x180094225  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009422c  mov     r9d, ebx; char *
0x18009422f  mov     edx, 1C2h; void *
0x180094234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094239  mov     rcx, [rbp+20h]; this
0x18009423d  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180094244  mov     r9d, ebx; char *
0x180094247  mov     edx, 24Ah; void *
0x18009424c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094251  mov     rcx, [rbp+arg_0]
0x180094255  mov     [rbp+arg_0], rsi
0x180094259  test    rcx, rcx
0x18009425c  jz      short loc_180094264
0x18009425e  call    cs:__imp_SRCacheContext_Close
0x180094264  mov     eax, ebx
0x180094266  jmp     loc_180094540
0x18009426b  mov     rcx, [rdi]
0x18009426e  lea     rax, [rbp+arg_8]
0x180094272  lea     r9, [rbp+var_20]
0x180094276  mov     [rbp+var_28], rax
0x18009427a  xor     r8d, r8d
0x18009427d  mov     [rbp+arg_8], rsi
0x180094281  lea     rdx, aApplicationDat; "Application\\Data"
0x180094288  mov     [rbp+var_20], rsi
0x18009428c  mov     [rbp+var_18], 1
0x180094290  call    cs:__imp_SRCacheContext_Create
0x180094296  lea     rcx, [rbp+var_28]
0x18009429a  mov     ebx, eax
0x18009429c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800942a1  test    ebx, ebx
0x1800942a3  jns     short loc_1800942F1
0x1800942a5  mov     rcx, [rbp+20h]; this
0x1800942a9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800942b0  mov     r9d, ebx; char *
0x1800942b3  mov     edx, 1C2h; void *
0x1800942b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800942bd  mov     rcx, [rbp+20h]; this
0x1800942c1  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x1800942c8  mov     r9d, ebx; char *
0x1800942cb  mov     edx, 24Dh; void *
0x1800942d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800942d5  mov     rcx, [rbp+arg_8]
0x1800942d9  mov     [rbp+arg_8], rsi
0x1800942dd  test    rcx, rcx
0x1800942e0  jz      loc_180094251
0x1800942e6  call    cs:__imp_SRCacheContext_Close
0x1800942ec  jmp     loc_180094251
0x1800942f1  mov     rcx, [rdi]
0x1800942f4  lea     rax, [rbp+arg_18]
0x1800942f8  lea     r9, [rbp+var_20]
0x1800942fc  mov     [rbp+var_28], rax
0x180094300  xor     r8d, r8d
0x180094303  mov     [rbp+arg_18], rsi
0x180094307  lea     rdx, aApplicationInd_1; "Application\\Index"
0x18009430e  mov     [rbp+var_20], rsi
0x180094312  mov     [rbp+var_18], 1
0x180094316  call    cs:__imp_SRCacheContext_Create
0x18009431c  lea     rcx, [rbp+var_28]
0x180094320  mov     ebx, eax
0x180094322  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180094327  test    ebx, ebx
0x180094329  jns     short loc_180094377
0x18009432b  mov     rcx, [rbp+20h]; this
0x18009432f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180094336  mov     r9d, ebx; char *
0x180094339  mov     edx, 1C2h; void *
0x18009433e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094343  mov     rcx, [rbp+20h]; this
0x180094347  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x18009434e  mov     r9d, ebx; char *
0x180094351  mov     edx, 250h; void *
0x180094356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009435b  mov     rcx, [rbp+arg_18]
0x18009435f  mov     [rbp+arg_18], rsi
0x180094363  test    rcx, rcx
0x180094366  jz      loc_1800942D5
0x18009436c  call    cs:__imp_SRCacheContext_Close
0x180094372  jmp     loc_1800942D5
0x180094377  mov     rcx, [rdi]
0x18009437a  lea     rax, [rbp+arg_10]
0x18009437e  lea     r9, [rbp+var_20]
0x180094382  mov     [rbp+var_28], rax
0x180094386  xor     r8d, r8d
0x180094389  mov     [rbp+arg_10], rsi
0x18009438d  lea     rdx, aApplicationInd_0; "Application\\Index\\Package"
0x180094394  mov     [rbp+var_20], rsi
0x180094398  mov     [rbp+var_18], 1
0x18009439c  call    cs:__imp_SRCacheContext_Create
0x1800943a2  lea     rcx, [rbp+var_28]
0x1800943a6  mov     ebx, eax
0x1800943a8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800943ad  test    ebx, ebx
0x1800943af  jns     short loc_1800943FD
0x1800943b1  mov     rcx, [rbp+20h]; this
0x1800943b5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800943bc  mov     r9d, ebx; char *
0x1800943bf  mov     edx, 1C2h; void *
0x1800943c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943c9  mov     edx, 252h; void *
0x1800943ce  mov     rcx, [rbp+20h]; this
0x1800943d2  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x1800943d9  mov     r9d, ebx; char *
0x1800943dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943e1  mov     rcx, [rbp+arg_10]
0x1800943e5  mov     [rbp+arg_10], rsi
0x1800943e9  test    rcx, rcx
0x1800943ec  jz      loc_18009435B
0x1800943f2  call    cs:__imp_SRCacheContext_Close
0x1800943f8  jmp     loc_18009435B
0x1800943fd  lea     rdx, aApplicationInd_0; "Application\\Index\\Package"
0x180094404  lea     rcx, [rbp+arg_10]; this
0x180094408  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18009440d  mov     ebx, eax
0x18009440f  test    eax, eax
0x180094411  jns     short loc_18009441A
0x180094413  mov     edx, 253h
0x180094418  jmp     short loc_1800943CE
0x18009441a  mov     rcx, [rdi]
0x18009441d  lea     rax, [rbp+arg_10]
0x180094421  lea     r9, [rbp+var_20]
0x180094425  mov     [rbp+var_28], rax
0x180094429  xor     r8d, r8d
0x18009442c  mov     [rbp+var_20], rsi
0x180094430  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x180094437  mov     [rbp+var_18], 1
0x18009443b  call    cs:__imp_SRCacheContext_Create
0x180094441  lea     rcx, [rbp+var_28]
0x180094445  mov     ebx, eax
0x180094447  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18009444c  test    ebx, ebx
0x18009444e  jns     short loc_180094472
0x180094450  mov     rcx, [rbp+20h]; this
0x180094454  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009445b  mov     r9d, ebx; char *
0x18009445e  mov     edx, 1C2h; void *
0x180094463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094468  mov     edx, 255h
0x18009446d  jmp     loc_1800943CE
0x180094472  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x180094479  lea     rcx, [rbp+arg_10]; this
0x18009447d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180094482  mov     ebx, eax
0x180094484  test    eax, eax
0x180094486  jns     short loc_180094492
0x180094488  mov     edx, 256h
0x18009448d  jmp     loc_1800943CE
0x180094492  lea     rdx, aApplicationInd_1; "Application\\Index"
0x180094499  lea     rcx, [rbp+arg_18]; this
0x18009449d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800944a2  mov     ebx, eax
0x1800944a4  test    eax, eax
0x1800944a6  jns     short loc_1800944B2
0x1800944a8  mov     edx, 258h
0x1800944ad  jmp     loc_1800943CE
0x1800944b2  lea     rdx, aApplicationDat; "Application\\Data"
0x1800944b9  lea     rcx, [rbp+arg_8]; this
0x1800944bd  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800944c2  mov     ebx, eax
0x1800944c4  test    eax, eax
0x1800944c6  jns     short loc_1800944D2
0x1800944c8  mov     edx, 259h
0x1800944cd  jmp     loc_1800943CE
0x1800944d2  lea     rdx, aApplication_0; "Application"
0x1800944d9  lea     rcx, [rbp+arg_0]; this
0x1800944dd  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800944e2  mov     ebx, eax
0x1800944e4  test    eax, eax
0x1800944e6  jns     short loc_1800944F2
0x1800944e8  mov     edx, 25Ah
0x1800944ed  jmp     loc_1800943CE
0x1800944f2  mov     rcx, [rbp+arg_10]
0x1800944f6  mov     [rbp+arg_10], rsi
0x1800944fa  test    rcx, rcx
0x1800944fd  jz      short loc_180094505
0x1800944ff  call    cs:__imp_SRCacheContext_Close
0x180094505  mov     rcx, [rbp+arg_18]
0x180094509  mov     [rbp+arg_18], rsi
0x18009450d  test    rcx, rcx
0x180094510  jz      short loc_180094518
0x180094512  call    cs:__imp_SRCacheContext_Close
0x180094518  mov     rcx, [rbp+arg_8]
0x18009451c  mov     [rbp+arg_8], rsi
0x180094520  test    rcx, rcx
0x180094523  jz      short loc_18009452B
0x180094525  call    cs:__imp_SRCacheContext_Close
0x18009452b  mov     rcx, [rbp+arg_0]
0x18009452f  mov     [rbp+arg_0], rsi
0x180094533  test    rcx, rcx
0x180094536  jz      short loc_18009453E
0x180094538  call    cs:__imp_SRCacheContext_Close
0x18009453e  xor     eax, eax
0x180094540  add     rsp, 48h
0x180094544  pop     rdi
0x180094545  pop     rsi
0x180094546  pop     rbx
0x180094547  pop     rbp
0x180094548  retn
```
