# StateRepository::Entity::CachePackageUserStatus::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x180096574`
- end: `0x180096929`
- name: `?Cache_Initialize@CachePackageUserStatus@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `949`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180096330`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x180096574`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800965cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096612`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800966b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096701`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009674c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800967d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800968df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800968f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096905`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096918`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800965cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096612`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800966b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096701`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009674c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800967d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800968df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800968f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096905`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180096918`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800965aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180096644`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800966e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009677c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009681b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800965aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180096644`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800966e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009677c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009681b`

## string_xrefs

- `0x1800965f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x18009668b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x180096727`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x1800967b2`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageuserstatus.cpp`
- `0x1800965d9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180096673`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18009670f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180096795`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180096834`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageUserStatus::Cache_Initialize(
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
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 *v21; // [rsp+20h] [rbp-28h] BYREF
  __int64 v22; // [rsp+28h] [rbp-20h] BYREF
  char v23; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v25; // [rsp+70h] [rbp+28h] BYREF
  __int64 v26; // [rsp+78h] [rbp+30h] BYREF
  __int64 v27; // [rsp+80h] [rbp+38h] BYREF
  __int64 v28; // [rsp+88h] [rbp+40h] BYREF

  v23 = 1;
  v2 = *(_QWORD *)a1;
  v21 = &v25;
  v25 = 0;
  v22 = 0;
  v3 = SRCacheContext_Create(v2, L"PackageUserStatus", 0, &v22);
  if ( v23 )
  {
    v4 = *v21;
    *v21 = v22;
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
      (int)v21);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v21);
LABEL_6:
    v5 = v25;
    v25 = 0;
    if ( v5 )
      SRCacheContext_Close(v5);
    return (unsigned int)v3;
  }
  v7 = *(_QWORD *)a1;
  v21 = &v26;
  v26 = 0;
  v22 = 0;
  v23 = 1;
  v3 = SRCacheContext_Create(v7, L"PackageUserStatus\\Data", 0, &v22);
  if ( v23 )
  {
    v8 = *v21;
    *v21 = v22;
    if ( v8 )
      SRCacheContext_Close(v8);
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v21);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v21);
LABEL_14:
    v9 = v26;
    v26 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    goto LABEL_6;
  }
  v10 = *(_QWORD *)a1;
  v21 = &v28;
  v28 = 0;
  v22 = 0;
  v23 = 1;
  v3 = SRCacheContext_Create(v10, L"PackageUserStatus\\Index", 0, &v22);
  if ( v23 )
  {
    v11 = *v21;
    *v21 = v22;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v21);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v21);
LABEL_21:
    v12 = v28;
    v28 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_14;
  }
  v13 = *(_QWORD *)a1;
  v21 = &v27;
  v27 = 0;
  v22 = 0;
  v23 = 1;
  v3 = SRCacheContext_Create(v13, L"PackageUserStatus\\Index\\UserAndPackageFullName", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v21);
    v14 = 360;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v27,
         L"PackageUserStatus\\Index\\UserAndPackageFullName");
  if ( v3 < 0 )
  {
    v14 = 361;
    goto LABEL_25;
  }
  v16 = *(_QWORD *)a1;
  v21 = &v27;
  v22 = 0;
  v23 = 1;
  v3 = SRCacheContext_Create(v16, L"PackageUserStatus\\Index\\UserAndPackageIdentity", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v21);
    v14 = 363;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v27,
         L"PackageUserStatus\\Index\\UserAndPackageIdentity");
  if ( v3 < 0 )
  {
    v14 = 364;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v28,
         L"PackageUserStatus\\Index");
  if ( v3 < 0 )
  {
    v14 = 366;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         L"PackageUserStatus\\Data");
  if ( v3 < 0 )
  {
    v14 = 367;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageUserStatus");
  if ( v3 < 0 )
  {
    v14 = 368;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageuserstatus.cpp",
      (const char *)(unsigned int)v3,
      (int)v21);
    v15 = v27;
    v27 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_21;
  }
  v17 = v27;
  v27 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v28;
  v28 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v26;
  v26 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  v20 = v25;
  v25 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x180096574  push    rbp
0x180096576  push    rbx
0x180096577  push    rsi
0x180096578  push    rdi
0x180096579  mov     rbp, rsp
0x18009657c  sub     rsp, 48h
0x180096580  mov     rdi, rcx
0x180096583  mov     [rbp+var_18], 1
0x180096587  mov     rcx, [rcx]
0x18009658a  lea     rax, [rbp+arg_0]
0x18009658e  xor     esi, esi
0x180096590  mov     [rbp+var_28], rax
0x180096594  lea     r9, [rbp+var_20]
0x180096598  mov     [rbp+arg_0], rsi
0x18009659c  xor     r8d, r8d
0x18009659f  mov     [rbp+var_20], rsi
0x1800965a3  lea     rdx, aPackageusersta_2; "PackageUserStatus"
0x1800965aa  call    cs:__imp_SRCacheContext_Create
0x1800965b0  mov     ebx, eax
0x1800965b2  cmp     [rbp+var_18], sil
0x1800965b6  jz      short loc_1800965D1
0x1800965b8  mov     r8, [rbp+var_28]
0x1800965bc  mov     rdx, [rbp+var_20]
0x1800965c0  mov     rcx, [r8]
0x1800965c3  mov     [r8], rdx
0x1800965c6  test    rcx, rcx
0x1800965c9  jz      short loc_1800965D1
0x1800965cb  call    cs:__imp_SRCacheContext_Close
0x1800965d1  test    ebx, ebx
0x1800965d3  jns     short loc_18009661F
0x1800965d5  mov     rcx, [rbp+20h]; this
0x1800965d9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800965e0  mov     r9d, ebx; char *
0x1800965e3  mov     edx, 1C2h; void *
0x1800965e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800965ed  mov     rcx, [rbp+20h]; this
0x1800965f1  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x1800965f8  mov     r9d, ebx; char *
0x1800965fb  mov     edx, 160h; void *
0x180096600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096605  mov     rcx, [rbp+arg_0]
0x180096609  mov     [rbp+arg_0], rsi
0x18009660d  test    rcx, rcx
0x180096610  jz      short loc_180096618
0x180096612  call    cs:__imp_SRCacheContext_Close
0x180096618  mov     eax, ebx
0x18009661a  jmp     loc_180096920
0x18009661f  mov     rcx, [rdi]
0x180096622  lea     rax, [rbp+arg_8]
0x180096626  lea     r9, [rbp+var_20]
0x18009662a  mov     [rbp+var_28], rax
0x18009662e  xor     r8d, r8d
0x180096631  mov     [rbp+arg_8], rsi
0x180096635  lea     rdx, aPackageusersta_30; "PackageUserStatus\\Data"
0x18009663c  mov     [rbp+var_20], rsi
0x180096640  mov     [rbp+var_18], 1
0x180096644  call    cs:__imp_SRCacheContext_Create
0x18009664a  mov     ebx, eax
0x18009664c  cmp     [rbp+var_18], sil
0x180096650  jz      short loc_18009666B
0x180096652  mov     r8, [rbp+var_28]
0x180096656  mov     rdx, [rbp+var_20]
0x18009665a  mov     rcx, [r8]
0x18009665d  mov     [r8], rdx
0x180096660  test    rcx, rcx
0x180096663  jz      short loc_18009666B
0x180096665  call    cs:__imp_SRCacheContext_Close
0x18009666b  test    ebx, ebx
0x18009666d  jns     short loc_1800966BB
0x18009666f  mov     rcx, [rbp+20h]; this
0x180096673  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009667a  mov     r9d, ebx; char *
0x18009667d  mov     edx, 1C2h; void *
0x180096682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096687  mov     rcx, [rbp+20h]; this
0x18009668b  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x180096692  mov     r9d, ebx; char *
0x180096695  mov     edx, 163h; void *
0x18009669a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009669f  mov     rcx, [rbp+arg_8]
0x1800966a3  mov     [rbp+arg_8], rsi
0x1800966a7  test    rcx, rcx
0x1800966aa  jz      loc_180096605
0x1800966b0  call    cs:__imp_SRCacheContext_Close
0x1800966b6  jmp     loc_180096605
0x1800966bb  mov     rcx, [rdi]
0x1800966be  lea     rax, [rbp+arg_18]
0x1800966c2  lea     r9, [rbp+var_20]
0x1800966c6  mov     [rbp+var_28], rax
0x1800966ca  xor     r8d, r8d
0x1800966cd  mov     [rbp+arg_18], rsi
0x1800966d1  lea     rdx, aPackageusersta_38; "PackageUserStatus\\Index"
0x1800966d8  mov     [rbp+var_20], rsi
0x1800966dc  mov     [rbp+var_18], 1
0x1800966e0  call    cs:__imp_SRCacheContext_Create
0x1800966e6  mov     ebx, eax
0x1800966e8  cmp     [rbp+var_18], sil
0x1800966ec  jz      short loc_180096707
0x1800966ee  mov     r8, [rbp+var_28]
0x1800966f2  mov     rdx, [rbp+var_20]
0x1800966f6  mov     rcx, [r8]
0x1800966f9  mov     [r8], rdx
0x1800966fc  test    rcx, rcx
0x1800966ff  jz      short loc_180096707
0x180096701  call    cs:__imp_SRCacheContext_Close
0x180096707  test    ebx, ebx
0x180096709  jns     short loc_180096757
0x18009670b  mov     rcx, [rbp+20h]; this
0x18009670f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180096716  mov     r9d, ebx; char *
0x180096719  mov     edx, 1C2h; void *
0x18009671e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096723  mov     rcx, [rbp+20h]; this
0x180096727  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x18009672e  mov     r9d, ebx; char *
0x180096731  mov     edx, 166h; void *
0x180096736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009673b  mov     rcx, [rbp+arg_18]
0x18009673f  mov     [rbp+arg_18], rsi
0x180096743  test    rcx, rcx
0x180096746  jz      loc_18009669F
0x18009674c  call    cs:__imp_SRCacheContext_Close
0x180096752  jmp     loc_18009669F
0x180096757  mov     rcx, [rdi]
0x18009675a  lea     rax, [rbp+arg_10]
0x18009675e  lea     r9, [rbp+var_20]
0x180096762  mov     [rbp+var_28], rax
0x180096766  xor     r8d, r8d
0x180096769  mov     [rbp+arg_10], rsi
0x18009676d  lea     rdx, aPackageusersta_33; "PackageUserStatus\\Index\\UserAndPackag"...
0x180096774  mov     [rbp+var_20], rsi
0x180096778  mov     [rbp+var_18], 1
0x18009677c  call    cs:__imp_SRCacheContext_Create
0x180096782  lea     rcx, [rbp+var_28]
0x180096786  mov     ebx, eax
0x180096788  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18009678d  test    ebx, ebx
0x18009678f  jns     short loc_1800967DD
0x180096791  mov     rcx, [rbp+20h]; this
0x180096795  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009679c  mov     r9d, ebx; char *
0x18009679f  mov     edx, 1C2h; void *
0x1800967a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800967a9  mov     edx, 168h; void *
0x1800967ae  mov     rcx, [rbp+20h]; this
0x1800967b2  lea     r8, aOnecoreBaseApp_354; "onecore\\base\\appmodel\\staterepositor"...
0x1800967b9  mov     r9d, ebx; char *
0x1800967bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800967c1  mov     rcx, [rbp+arg_10]
0x1800967c5  mov     [rbp+arg_10], rsi
0x1800967c9  test    rcx, rcx
0x1800967cc  jz      loc_18009673B
0x1800967d2  call    cs:__imp_SRCacheContext_Close
0x1800967d8  jmp     loc_18009673B
0x1800967dd  lea     rdx, aPackageusersta_33; "PackageUserStatus\\Index\\UserAndPackag"...
0x1800967e4  lea     rcx, [rbp+arg_10]; this
0x1800967e8  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800967ed  mov     ebx, eax
0x1800967ef  test    eax, eax
0x1800967f1  jns     short loc_1800967FA
0x1800967f3  mov     edx, 169h
0x1800967f8  jmp     short loc_1800967AE
0x1800967fa  mov     rcx, [rdi]
0x1800967fd  lea     rax, [rbp+arg_10]
0x180096801  lea     r9, [rbp+var_20]
0x180096805  mov     [rbp+var_28], rax
0x180096809  xor     r8d, r8d
0x18009680c  mov     [rbp+var_20], rsi
0x180096810  lea     rdx, aPackageusersta_55; "PackageUserStatus\\Index\\UserAndPackag"...
0x180096817  mov     [rbp+var_18], 1
0x18009681b  call    cs:__imp_SRCacheContext_Create
0x180096821  lea     rcx, [rbp+var_28]
0x180096825  mov     ebx, eax
0x180096827  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18009682c  test    ebx, ebx
0x18009682e  jns     short loc_180096852
0x180096830  mov     rcx, [rbp+20h]; this
0x180096834  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009683b  mov     r9d, ebx; char *
0x18009683e  mov     edx, 1C2h; void *
0x180096843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096848  mov     edx, 16Bh
0x18009684d  jmp     loc_1800967AE
0x180096852  lea     rdx, aPackageusersta_55; "PackageUserStatus\\Index\\UserAndPackag"...
0x180096859  lea     rcx, [rbp+arg_10]; this
0x18009685d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180096862  mov     ebx, eax
0x180096864  test    eax, eax
0x180096866  jns     short loc_180096872
0x180096868  mov     edx, 16Ch
0x18009686d  jmp     loc_1800967AE
0x180096872  lea     rdx, aPackageusersta_38; "PackageUserStatus\\Index"
0x180096879  lea     rcx, [rbp+arg_18]; this
0x18009687d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180096882  mov     ebx, eax
0x180096884  test    eax, eax
0x180096886  jns     short loc_180096892
0x180096888  mov     edx, 16Eh
0x18009688d  jmp     loc_1800967AE
0x180096892  lea     rdx, aPackageusersta_30; "PackageUserStatus\\Data"
0x180096899  lea     rcx, [rbp+arg_8]; this
0x18009689d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800968a2  mov     ebx, eax
0x1800968a4  test    eax, eax
0x1800968a6  jns     short loc_1800968B2
0x1800968a8  mov     edx, 16Fh
0x1800968ad  jmp     loc_1800967AE
0x1800968b2  lea     rdx, aPackageusersta_2; "PackageUserStatus"
0x1800968b9  lea     rcx, [rbp+arg_0]; this
0x1800968bd  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800968c2  mov     ebx, eax
0x1800968c4  test    eax, eax
0x1800968c6  jns     short loc_1800968D2
0x1800968c8  mov     edx, 170h
0x1800968cd  jmp     loc_1800967AE
0x1800968d2  mov     rcx, [rbp+arg_10]
0x1800968d6  mov     [rbp+arg_10], rsi
0x1800968da  test    rcx, rcx
0x1800968dd  jz      short loc_1800968E5
0x1800968df  call    cs:__imp_SRCacheContext_Close
0x1800968e5  mov     rcx, [rbp+arg_18]
0x1800968e9  mov     [rbp+arg_18], rsi
0x1800968ed  test    rcx, rcx
0x1800968f0  jz      short loc_1800968F8
0x1800968f2  call    cs:__imp_SRCacheContext_Close
0x1800968f8  mov     rcx, [rbp+arg_8]
0x1800968fc  mov     [rbp+arg_8], rsi
0x180096900  test    rcx, rcx
0x180096903  jz      short loc_18009690B
0x180096905  call    cs:__imp_SRCacheContext_Close
0x18009690b  mov     rcx, [rbp+arg_0]
0x18009690f  mov     [rbp+arg_0], rsi
0x180096913  test    rcx, rcx
0x180096916  jz      short loc_18009691E
0x180096918  call    cs:__imp_SRCacheContext_Close
0x18009691e  xor     eax, eax
0x180096920  add     rsp, 48h
0x180096924  pop     rdi
0x180096925  pop     rsi
0x180096926  pop     rbx
0x180096927  pop     rbp
0x180096928  retn
```
