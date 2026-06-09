# StateRepository::Entity::CachePackageProperty::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x1800b5444`
- end: `0x1800b5845`
- name: `?Cache_Initialize@CachePackageProperty@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180090800`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x1800b5444`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b549b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b54e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b556a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b55f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5676`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b57fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b580e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5821`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5834`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b549b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b54e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b556a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b55f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5676`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b57fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b580e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5821`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b5834`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b547a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b5514`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b559a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b5620`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b56bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b5737`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b547a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b5514`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b559a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b5620`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b56bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b5737`

## string_xrefs

- `0x1800b54a9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b552d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b55b3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b5639`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b56d8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b5750`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b54c1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x1800b5545`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x1800b55cb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x1800b5656`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageProperty::Cache_Initialize(
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
  __int64 v19; // rcx
  __int64 *v20; // [rsp+20h] [rbp-28h] BYREF
  __int64 v21; // [rsp+28h] [rbp-20h] BYREF
  char v22; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v24; // [rsp+70h] [rbp+28h] BYREF
  __int64 v25; // [rsp+78h] [rbp+30h] BYREF
  __int64 v26; // [rsp+80h] [rbp+38h] BYREF
  __int64 v27; // [rsp+88h] [rbp+40h] BYREF

  v22 = 1;
  v2 = *(_QWORD *)a1;
  v20 = &v24;
  v24 = 0;
  v21 = 0;
  v3 = SRCacheContext_Create(v2, L"PackageProperty", 0, &v21);
  if ( v22 )
  {
    v4 = *v20;
    *v20 = v21;
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
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
LABEL_6:
    v5 = v24;
    v24 = 0;
    if ( v5 )
      SRCacheContext_Close(v5);
    return (unsigned int)v3;
  }
  v7 = *(_QWORD *)a1;
  v20 = &v26;
  v26 = 0;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v7, L"PackageProperty\\Data", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
LABEL_11:
    v8 = v26;
    v26 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    goto LABEL_6;
  }
  v9 = *(_QWORD *)a1;
  v20 = &v27;
  v27 = 0;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v9, L"PackageProperty\\Index", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
LABEL_15:
    v10 = v27;
    v27 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    goto LABEL_11;
  }
  v11 = *(_QWORD *)a1;
  v20 = &v25;
  v25 = 0;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v11, L"PackageProperty\\Index\\Name", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v12 = 359;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageProperty\\Index\\Name");
  if ( v3 < 0 )
  {
    v12 = 360;
    goto LABEL_19;
  }
  v14 = *(_QWORD *)a1;
  v20 = &v25;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v14, L"PackageProperty\\Index\\Package", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v12 = 362;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageProperty\\Index\\Package");
  if ( v3 < 0 )
  {
    v12 = 363;
    goto LABEL_19;
  }
  v15 = *(_QWORD *)a1;
  v20 = &v25;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v15, L"PackageProperty\\Index\\PackageAndName", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v12 = 365;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageProperty\\Index\\PackageAndName");
  if ( v3 < 0 )
  {
    v12 = 366;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v27,
         L"PackageProperty\\Index");
  if ( v3 < 0 )
  {
    v12 = 368;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         L"PackageProperty\\Data");
  if ( v3 < 0 )
  {
    v12 = 369;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"PackageProperty");
  if ( v3 < 0 )
  {
    v12 = 370;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v13 = v25;
    v25 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_15;
  }
  v16 = v25;
  v25 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v27;
  v27 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v26;
  v26 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v24;
  v24 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x1800b5444  push    rbp
0x1800b5446  push    rbx
0x1800b5447  push    rsi
0x1800b5448  push    rdi
0x1800b5449  mov     rbp, rsp
0x1800b544c  sub     rsp, 48h
0x1800b5450  mov     rdi, rcx
0x1800b5453  mov     [rbp+var_18], 1
0x1800b5457  mov     rcx, [rcx]
0x1800b545a  lea     rax, [rbp+arg_0]
0x1800b545e  xor     esi, esi
0x1800b5460  mov     [rbp+var_28], rax
0x1800b5464  lea     r9, [rbp+var_20]
0x1800b5468  mov     [rbp+arg_0], rsi
0x1800b546c  xor     r8d, r8d
0x1800b546f  mov     [rbp+var_20], rsi
0x1800b5473  lea     rdx, aPackagepropert_12; "PackageProperty"
0x1800b547a  call    cs:__imp_SRCacheContext_Create
0x1800b5480  mov     ebx, eax
0x1800b5482  cmp     [rbp+var_18], sil
0x1800b5486  jz      short loc_1800B54A1
0x1800b5488  mov     r8, [rbp+var_28]
0x1800b548c  mov     rdx, [rbp+var_20]
0x1800b5490  mov     rcx, [r8]
0x1800b5493  mov     [r8], rdx
0x1800b5496  test    rcx, rcx
0x1800b5499  jz      short loc_1800B54A1
0x1800b549b  call    cs:__imp_SRCacheContext_Close
0x1800b54a1  test    ebx, ebx
0x1800b54a3  jns     short loc_1800B54EF
0x1800b54a5  mov     rcx, [rbp+20h]; this
0x1800b54a9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b54b0  mov     r9d, ebx; char *
0x1800b54b3  mov     edx, 1C2h; void *
0x1800b54b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b54bd  mov     rcx, [rbp+20h]; this
0x1800b54c1  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x1800b54c8  mov     r9d, ebx; char *
0x1800b54cb  mov     edx, 15Fh; void *
0x1800b54d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b54d5  mov     rcx, [rbp+arg_0]
0x1800b54d9  mov     [rbp+arg_0], rsi
0x1800b54dd  test    rcx, rcx
0x1800b54e0  jz      short loc_1800B54E8
0x1800b54e2  call    cs:__imp_SRCacheContext_Close
0x1800b54e8  mov     eax, ebx
0x1800b54ea  jmp     loc_1800B583C
0x1800b54ef  mov     rcx, [rdi]
0x1800b54f2  lea     rax, [rbp+arg_10]
0x1800b54f6  lea     r9, [rbp+var_20]
0x1800b54fa  mov     [rbp+var_28], rax
0x1800b54fe  xor     r8d, r8d
0x1800b5501  mov     [rbp+arg_10], rsi
0x1800b5505  lea     rdx, aPackagepropert_7; "PackageProperty\\Data"
0x1800b550c  mov     [rbp+var_20], rsi
0x1800b5510  mov     [rbp+var_18], 1
0x1800b5514  call    cs:__imp_SRCacheContext_Create
0x1800b551a  lea     rcx, [rbp+var_28]
0x1800b551e  mov     ebx, eax
0x1800b5520  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b5525  test    ebx, ebx
0x1800b5527  jns     short loc_1800B5575
0x1800b5529  mov     rcx, [rbp+20h]; this
0x1800b552d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b5534  mov     r9d, ebx; char *
0x1800b5537  mov     edx, 1C2h; void *
0x1800b553c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5541  mov     rcx, [rbp+20h]; this
0x1800b5545  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x1800b554c  mov     r9d, ebx; char *
0x1800b554f  mov     edx, 162h; void *
0x1800b5554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5559  mov     rcx, [rbp+arg_10]
0x1800b555d  mov     [rbp+arg_10], rsi
0x1800b5561  test    rcx, rcx
0x1800b5564  jz      loc_1800B54D5
0x1800b556a  call    cs:__imp_SRCacheContext_Close
0x1800b5570  jmp     loc_1800B54D5
0x1800b5575  mov     rcx, [rdi]
0x1800b5578  lea     rax, [rbp+arg_18]
0x1800b557c  lea     r9, [rbp+var_20]
0x1800b5580  mov     [rbp+var_28], rax
0x1800b5584  xor     r8d, r8d
0x1800b5587  mov     [rbp+arg_18], rsi
0x1800b558b  lea     rdx, aPackagepropert_15; "PackageProperty\\Index"
0x1800b5592  mov     [rbp+var_20], rsi
0x1800b5596  mov     [rbp+var_18], 1
0x1800b559a  call    cs:__imp_SRCacheContext_Create
0x1800b55a0  lea     rcx, [rbp+var_28]
0x1800b55a4  mov     ebx, eax
0x1800b55a6  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b55ab  test    ebx, ebx
0x1800b55ad  jns     short loc_1800B55FB
0x1800b55af  mov     rcx, [rbp+20h]; this
0x1800b55b3  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b55ba  mov     r9d, ebx; char *
0x1800b55bd  mov     edx, 1C2h; void *
0x1800b55c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b55c7  mov     rcx, [rbp+20h]; this
0x1800b55cb  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x1800b55d2  mov     r9d, ebx; char *
0x1800b55d5  mov     edx, 165h; void *
0x1800b55da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b55df  mov     rcx, [rbp+arg_18]
0x1800b55e3  mov     [rbp+arg_18], rsi
0x1800b55e7  test    rcx, rcx
0x1800b55ea  jz      loc_1800B5559
0x1800b55f0  call    cs:__imp_SRCacheContext_Close
0x1800b55f6  jmp     loc_1800B5559
0x1800b55fb  mov     rcx, [rdi]
0x1800b55fe  lea     rax, [rbp+arg_8]
0x1800b5602  lea     r9, [rbp+var_20]
0x1800b5606  mov     [rbp+var_28], rax
0x1800b560a  xor     r8d, r8d
0x1800b560d  mov     [rbp+arg_8], rsi
0x1800b5611  lea     rdx, aPackagepropert_9; "PackageProperty\\Index\\Name"
0x1800b5618  mov     [rbp+var_20], rsi
0x1800b561c  mov     [rbp+var_18], 1
0x1800b5620  call    cs:__imp_SRCacheContext_Create
0x1800b5626  lea     rcx, [rbp+var_28]
0x1800b562a  mov     ebx, eax
0x1800b562c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b5631  test    ebx, ebx
0x1800b5633  jns     short loc_1800B5681
0x1800b5635  mov     rcx, [rbp+20h]; this
0x1800b5639  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b5640  mov     r9d, ebx; char *
0x1800b5643  mov     edx, 1C2h; void *
0x1800b5648  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b564d  mov     edx, 167h; void *
0x1800b5652  mov     rcx, [rbp+20h]; this
0x1800b5656  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x1800b565d  mov     r9d, ebx; char *
0x1800b5660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5665  mov     rcx, [rbp+arg_8]
0x1800b5669  mov     [rbp+arg_8], rsi
0x1800b566d  test    rcx, rcx
0x1800b5670  jz      loc_1800B55DF
0x1800b5676  call    cs:__imp_SRCacheContext_Close
0x1800b567c  jmp     loc_1800B55DF
0x1800b5681  lea     rdx, aPackagepropert_9; "PackageProperty\\Index\\Name"
0x1800b5688  lea     rcx, [rbp+arg_8]; this
0x1800b568c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b5691  mov     ebx, eax
0x1800b5693  test    eax, eax
0x1800b5695  jns     short loc_1800B569E
0x1800b5697  mov     edx, 168h
0x1800b569c  jmp     short loc_1800B5652
0x1800b569e  mov     rcx, [rdi]
0x1800b56a1  lea     rax, [rbp+arg_8]
0x1800b56a5  lea     r9, [rbp+var_20]
0x1800b56a9  mov     [rbp+var_28], rax
0x1800b56ad  xor     r8d, r8d
0x1800b56b0  mov     [rbp+var_20], rsi
0x1800b56b4  lea     rdx, aPackagepropert_11; "PackageProperty\\Index\\Package"
0x1800b56bb  mov     [rbp+var_18], 1
0x1800b56bf  call    cs:__imp_SRCacheContext_Create
0x1800b56c5  lea     rcx, [rbp+var_28]
0x1800b56c9  mov     ebx, eax
0x1800b56cb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b56d0  test    ebx, ebx
0x1800b56d2  jns     short loc_1800B56F6
0x1800b56d4  mov     rcx, [rbp+20h]; this
0x1800b56d8  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b56df  mov     r9d, ebx; char *
0x1800b56e2  mov     edx, 1C2h; void *
0x1800b56e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b56ec  mov     edx, 16Ah
0x1800b56f1  jmp     loc_1800B5652
0x1800b56f6  lea     rdx, aPackagepropert_11; "PackageProperty\\Index\\Package"
0x1800b56fd  lea     rcx, [rbp+arg_8]; this
0x1800b5701  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b5706  mov     ebx, eax
0x1800b5708  test    eax, eax
0x1800b570a  jns     short loc_1800B5716
0x1800b570c  mov     edx, 16Bh
0x1800b5711  jmp     loc_1800B5652
0x1800b5716  mov     rcx, [rdi]
0x1800b5719  lea     rax, [rbp+arg_8]
0x1800b571d  lea     r9, [rbp+var_20]
0x1800b5721  mov     [rbp+var_28], rax
0x1800b5725  xor     r8d, r8d
0x1800b5728  mov     [rbp+var_20], rsi
0x1800b572c  lea     rdx, aPackagepropert_6; "PackageProperty\\Index\\PackageAndName"
0x1800b5733  mov     [rbp+var_18], 1
0x1800b5737  call    cs:__imp_SRCacheContext_Create
0x1800b573d  lea     rcx, [rbp+var_28]
0x1800b5741  mov     ebx, eax
0x1800b5743  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b5748  test    ebx, ebx
0x1800b574a  jns     short loc_1800B576E
0x1800b574c  mov     rcx, [rbp+20h]; this
0x1800b5750  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b5757  mov     r9d, ebx; char *
0x1800b575a  mov     edx, 1C2h; void *
0x1800b575f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5764  mov     edx, 16Dh
0x1800b5769  jmp     loc_1800B5652
0x1800b576e  lea     rdx, aPackagepropert_6; "PackageProperty\\Index\\PackageAndName"
0x1800b5775  lea     rcx, [rbp+arg_8]; this
0x1800b5779  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b577e  mov     ebx, eax
0x1800b5780  test    eax, eax
0x1800b5782  jns     short loc_1800B578E
0x1800b5784  mov     edx, 16Eh
0x1800b5789  jmp     loc_1800B5652
0x1800b578e  lea     rdx, aPackagepropert_15; "PackageProperty\\Index"
0x1800b5795  lea     rcx, [rbp+arg_18]; this
0x1800b5799  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b579e  mov     ebx, eax
0x1800b57a0  test    eax, eax
0x1800b57a2  jns     short loc_1800B57AE
0x1800b57a4  mov     edx, 170h
0x1800b57a9  jmp     loc_1800B5652
0x1800b57ae  lea     rdx, aPackagepropert_7; "PackageProperty\\Data"
0x1800b57b5  lea     rcx, [rbp+arg_10]; this
0x1800b57b9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b57be  mov     ebx, eax
0x1800b57c0  test    eax, eax
0x1800b57c2  jns     short loc_1800B57CE
0x1800b57c4  mov     edx, 171h
0x1800b57c9  jmp     loc_1800B5652
0x1800b57ce  lea     rdx, aPackagepropert_12; "PackageProperty"
0x1800b57d5  lea     rcx, [rbp+arg_0]; this
0x1800b57d9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b57de  mov     ebx, eax
0x1800b57e0  test    eax, eax
0x1800b57e2  jns     short loc_1800B57EE
0x1800b57e4  mov     edx, 172h
0x1800b57e9  jmp     loc_1800B5652
0x1800b57ee  mov     rcx, [rbp+arg_8]
0x1800b57f2  mov     [rbp+arg_8], rsi
0x1800b57f6  test    rcx, rcx
0x1800b57f9  jz      short loc_1800B5801
0x1800b57fb  call    cs:__imp_SRCacheContext_Close
0x1800b5801  mov     rcx, [rbp+arg_18]
0x1800b5805  mov     [rbp+arg_18], rsi
0x1800b5809  test    rcx, rcx
0x1800b580c  jz      short loc_1800B5814
0x1800b580e  call    cs:__imp_SRCacheContext_Close
0x1800b5814  mov     rcx, [rbp+arg_10]
0x1800b5818  mov     [rbp+arg_10], rsi
0x1800b581c  test    rcx, rcx
0x1800b581f  jz      short loc_1800B5827
0x1800b5821  call    cs:__imp_SRCacheContext_Close
0x1800b5827  mov     rcx, [rbp+arg_0]
0x1800b582b  mov     [rbp+arg_0], rsi
0x1800b582f  test    rcx, rcx
0x1800b5832  jz      short loc_1800B583A
0x1800b5834  call    cs:__imp_SRCacheContext_Close
0x1800b583a  xor     eax, eax
0x1800b583c  add     rsp, 48h
0x1800b5840  pop     rdi
0x1800b5841  pop     rsi
0x1800b5842  pop     rbx
0x1800b5843  pop     rbp
0x1800b5844  retn
```
