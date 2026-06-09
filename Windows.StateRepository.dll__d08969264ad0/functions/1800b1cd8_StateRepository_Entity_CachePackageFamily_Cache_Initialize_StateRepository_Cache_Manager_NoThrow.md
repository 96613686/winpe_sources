# StateRepository::Entity::CachePackageFamily::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x1800b1cd8`
- end: `0x1800b2061`
- name: `?Cache_Initialize@CachePackageFamily@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `905`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18006bd10`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x1800b1cd8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1d2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1d76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1dfe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1e84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1f0a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b2017`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b202a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b203d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b2050`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1d2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1d76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1dfe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1e84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b1f0a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b2017`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b202a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b203d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b2050`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1d0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1da8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1e2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1eb4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1f53`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1d0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1da8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1e2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1eb4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800b1f53`

## string_xrefs

- `0x1800b1d3d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b1dc1`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b1e47`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b1ecd`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b1f6c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b1d55`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800b1dd9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800b1e5f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800b1eea`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800b1f48`: `PackageFamily\Index\PackageSID`
- `0x1800b1f8a`: `PackageFamily\Index\PackageSID`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageFamily::Cache_Initialize(
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
  v3 = SRCacheContext_Create(v2, L"PackageFamily", 0, &v26);
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
      (void *)0x136,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
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
  v3 = SRCacheContext_Create(v11, L"PackageFamily\\Data", 0, &v26);
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
      (void *)0x139,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
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
  v3 = SRCacheContext_Create(v13, L"PackageFamily\\Index", 0, &v26);
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
      (void *)0x13C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
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
  v3 = SRCacheContext_Create(v15, L"PackageFamily\\Index\\PackageFamilyName", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    v16 = 318;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v31,
         L"PackageFamily\\Index\\PackageFamilyName");
  if ( v3 < 0 )
  {
    v16 = 319;
    goto LABEL_19;
  }
  v18 = *(_QWORD *)a1;
  v25 = &v31;
  v26 = 0;
  v27 = 1;
  v3 = SRCacheContext_Create(v18, L"PackageFamily\\Index\\PackageSID", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    v16 = 321;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v31,
         L"PackageFamily\\Index\\PackageSID");
  if ( v3 < 0 )
  {
    v16 = 322;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v32,
         L"PackageFamily\\Index");
  if ( v3 < 0 )
  {
    v16 = 324;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v30,
         L"PackageFamily\\Data");
  if ( v3 < 0 )
  {
    v16 = 325;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v29,
         L"PackageFamily");
  if ( v3 < 0 )
  {
    v16 = 326;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
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
0x1800b1cd8  push    rbp
0x1800b1cda  push    rbx
0x1800b1cdb  push    rsi
0x1800b1cdc  push    rdi
0x1800b1cdd  mov     rbp, rsp
0x1800b1ce0  sub     rsp, 48h
0x1800b1ce4  mov     rdi, rcx
0x1800b1ce7  mov     [rbp+var_18], 1
0x1800b1ceb  mov     rcx, [rcx]
0x1800b1cee  lea     rax, [rbp+arg_0]
0x1800b1cf2  xor     esi, esi
0x1800b1cf4  mov     [rbp+var_28], rax
0x1800b1cf8  lea     r9, [rbp+var_20]
0x1800b1cfc  mov     [rbp+arg_0], rsi
0x1800b1d00  xor     r8d, r8d
0x1800b1d03  mov     [rbp+var_20], rsi
0x1800b1d07  lea     rdx, aPackagefamily; "PackageFamily"
0x1800b1d0e  call    cs:__imp_SRCacheContext_Create
0x1800b1d14  mov     ebx, eax
0x1800b1d16  cmp     [rbp+var_18], sil
0x1800b1d1a  jz      short loc_1800B1D35
0x1800b1d1c  mov     r8, [rbp+var_28]
0x1800b1d20  mov     rdx, [rbp+var_20]
0x1800b1d24  mov     rcx, [r8]
0x1800b1d27  mov     [r8], rdx
0x1800b1d2a  test    rcx, rcx
0x1800b1d2d  jz      short loc_1800B1D35
0x1800b1d2f  call    cs:__imp_SRCacheContext_Close
0x1800b1d35  test    ebx, ebx
0x1800b1d37  jns     short loc_1800B1D83
0x1800b1d39  mov     rcx, [rbp+20h]; this
0x1800b1d3d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b1d44  mov     r9d, ebx; char *
0x1800b1d47  mov     edx, 1C2h; void *
0x1800b1d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1d51  mov     rcx, [rbp+20h]; this
0x1800b1d55  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800b1d5c  mov     r9d, ebx; char *
0x1800b1d5f  mov     edx, 136h; void *
0x1800b1d64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1d69  mov     rcx, [rbp+arg_0]
0x1800b1d6d  mov     [rbp+arg_0], rsi
0x1800b1d71  test    rcx, rcx
0x1800b1d74  jz      short loc_1800B1D7C
0x1800b1d76  call    cs:__imp_SRCacheContext_Close
0x1800b1d7c  mov     eax, ebx
0x1800b1d7e  jmp     loc_1800B2058
0x1800b1d83  mov     rcx, [rdi]
0x1800b1d86  lea     rax, [rbp+arg_8]
0x1800b1d8a  lea     r9, [rbp+var_20]
0x1800b1d8e  mov     [rbp+var_28], rax
0x1800b1d92  xor     r8d, r8d
0x1800b1d95  mov     [rbp+arg_8], rsi
0x1800b1d99  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x1800b1da0  mov     [rbp+var_20], rsi
0x1800b1da4  mov     [rbp+var_18], 1
0x1800b1da8  call    cs:__imp_SRCacheContext_Create
0x1800b1dae  lea     rcx, [rbp+var_28]
0x1800b1db2  mov     ebx, eax
0x1800b1db4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b1db9  test    ebx, ebx
0x1800b1dbb  jns     short loc_1800B1E09
0x1800b1dbd  mov     rcx, [rbp+20h]; this
0x1800b1dc1  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b1dc8  mov     r9d, ebx; char *
0x1800b1dcb  mov     edx, 1C2h; void *
0x1800b1dd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1dd5  mov     rcx, [rbp+20h]; this
0x1800b1dd9  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800b1de0  mov     r9d, ebx; char *
0x1800b1de3  mov     edx, 139h; void *
0x1800b1de8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1ded  mov     rcx, [rbp+arg_8]
0x1800b1df1  mov     [rbp+arg_8], rsi
0x1800b1df5  test    rcx, rcx
0x1800b1df8  jz      loc_1800B1D69
0x1800b1dfe  call    cs:__imp_SRCacheContext_Close
0x1800b1e04  jmp     loc_1800B1D69
0x1800b1e09  mov     rcx, [rdi]
0x1800b1e0c  lea     rax, [rbp+arg_18]
0x1800b1e10  lea     r9, [rbp+var_20]
0x1800b1e14  mov     [rbp+var_28], rax
0x1800b1e18  xor     r8d, r8d
0x1800b1e1b  mov     [rbp+arg_18], rsi
0x1800b1e1f  lea     rdx, aPackagefamilyI_1; "PackageFamily\\Index"
0x1800b1e26  mov     [rbp+var_20], rsi
0x1800b1e2a  mov     [rbp+var_18], 1
0x1800b1e2e  call    cs:__imp_SRCacheContext_Create
0x1800b1e34  lea     rcx, [rbp+var_28]
0x1800b1e38  mov     ebx, eax
0x1800b1e3a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b1e3f  test    ebx, ebx
0x1800b1e41  jns     short loc_1800B1E8F
0x1800b1e43  mov     rcx, [rbp+20h]; this
0x1800b1e47  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b1e4e  mov     r9d, ebx; char *
0x1800b1e51  mov     edx, 1C2h; void *
0x1800b1e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1e5b  mov     rcx, [rbp+20h]; this
0x1800b1e5f  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800b1e66  mov     r9d, ebx; char *
0x1800b1e69  mov     edx, 13Ch; void *
0x1800b1e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1e73  mov     rcx, [rbp+arg_18]
0x1800b1e77  mov     [rbp+arg_18], rsi
0x1800b1e7b  test    rcx, rcx
0x1800b1e7e  jz      loc_1800B1DED
0x1800b1e84  call    cs:__imp_SRCacheContext_Close
0x1800b1e8a  jmp     loc_1800B1DED
0x1800b1e8f  mov     rcx, [rdi]
0x1800b1e92  lea     rax, [rbp+arg_10]
0x1800b1e96  lea     r9, [rbp+var_20]
0x1800b1e9a  mov     [rbp+var_28], rax
0x1800b1e9e  xor     r8d, r8d
0x1800b1ea1  mov     [rbp+arg_10], rsi
0x1800b1ea5  lea     rdx, aPackagefamilyI_0; "PackageFamily\\Index\\PackageFamilyName"
0x1800b1eac  mov     [rbp+var_20], rsi
0x1800b1eb0  mov     [rbp+var_18], 1
0x1800b1eb4  call    cs:__imp_SRCacheContext_Create
0x1800b1eba  lea     rcx, [rbp+var_28]
0x1800b1ebe  mov     ebx, eax
0x1800b1ec0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b1ec5  test    ebx, ebx
0x1800b1ec7  jns     short loc_1800B1F15
0x1800b1ec9  mov     rcx, [rbp+20h]; this
0x1800b1ecd  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b1ed4  mov     r9d, ebx; char *
0x1800b1ed7  mov     edx, 1C2h; void *
0x1800b1edc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1ee1  mov     edx, 13Eh; void *
0x1800b1ee6  mov     rcx, [rbp+20h]; this
0x1800b1eea  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800b1ef1  mov     r9d, ebx; char *
0x1800b1ef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1ef9  mov     rcx, [rbp+arg_10]
0x1800b1efd  mov     [rbp+arg_10], rsi
0x1800b1f01  test    rcx, rcx
0x1800b1f04  jz      loc_1800B1E73
0x1800b1f0a  call    cs:__imp_SRCacheContext_Close
0x1800b1f10  jmp     loc_1800B1E73
0x1800b1f15  lea     rdx, aPackagefamilyI_0; "PackageFamily\\Index\\PackageFamilyName"
0x1800b1f1c  lea     rcx, [rbp+arg_10]; this
0x1800b1f20  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b1f25  mov     ebx, eax
0x1800b1f27  test    eax, eax
0x1800b1f29  jns     short loc_1800B1F32
0x1800b1f2b  mov     edx, 13Fh
0x1800b1f30  jmp     short loc_1800B1EE6
0x1800b1f32  mov     rcx, [rdi]
0x1800b1f35  lea     rax, [rbp+arg_10]
0x1800b1f39  lea     r9, [rbp+var_20]
0x1800b1f3d  mov     [rbp+var_28], rax
0x1800b1f41  xor     r8d, r8d
0x1800b1f44  mov     [rbp+var_20], rsi
0x1800b1f48  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageSID"
0x1800b1f4f  mov     [rbp+var_18], 1
0x1800b1f53  call    cs:__imp_SRCacheContext_Create
0x1800b1f59  lea     rcx, [rbp+var_28]
0x1800b1f5d  mov     ebx, eax
0x1800b1f5f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b1f64  test    ebx, ebx
0x1800b1f66  jns     short loc_1800B1F8A
0x1800b1f68  mov     rcx, [rbp+20h]; this
0x1800b1f6c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b1f73  mov     r9d, ebx; char *
0x1800b1f76  mov     edx, 1C2h; void *
0x1800b1f7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1f80  mov     edx, 141h
0x1800b1f85  jmp     loc_1800B1EE6
0x1800b1f8a  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageSID"
0x1800b1f91  lea     rcx, [rbp+arg_10]; this
0x1800b1f95  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b1f9a  mov     ebx, eax
0x1800b1f9c  test    eax, eax
0x1800b1f9e  jns     short loc_1800B1FAA
0x1800b1fa0  mov     edx, 142h
0x1800b1fa5  jmp     loc_1800B1EE6
0x1800b1faa  lea     rdx, aPackagefamilyI_1; "PackageFamily\\Index"
0x1800b1fb1  lea     rcx, [rbp+arg_18]; this
0x1800b1fb5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b1fba  mov     ebx, eax
0x1800b1fbc  test    eax, eax
0x1800b1fbe  jns     short loc_1800B1FCA
0x1800b1fc0  mov     edx, 144h
0x1800b1fc5  jmp     loc_1800B1EE6
0x1800b1fca  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x1800b1fd1  lea     rcx, [rbp+arg_8]; this
0x1800b1fd5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b1fda  mov     ebx, eax
0x1800b1fdc  test    eax, eax
0x1800b1fde  jns     short loc_1800B1FEA
0x1800b1fe0  mov     edx, 145h
0x1800b1fe5  jmp     loc_1800B1EE6
0x1800b1fea  lea     rdx, aPackagefamily; "PackageFamily"
0x1800b1ff1  lea     rcx, [rbp+arg_0]; this
0x1800b1ff5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b1ffa  mov     ebx, eax
0x1800b1ffc  test    eax, eax
0x1800b1ffe  jns     short loc_1800B200A
0x1800b2000  mov     edx, 146h
0x1800b2005  jmp     loc_1800B1EE6
0x1800b200a  mov     rcx, [rbp+arg_10]
0x1800b200e  mov     [rbp+arg_10], rsi
0x1800b2012  test    rcx, rcx
0x1800b2015  jz      short loc_1800B201D
0x1800b2017  call    cs:__imp_SRCacheContext_Close
0x1800b201d  mov     rcx, [rbp+arg_18]
0x1800b2021  mov     [rbp+arg_18], rsi
0x1800b2025  test    rcx, rcx
0x1800b2028  jz      short loc_1800B2030
0x1800b202a  call    cs:__imp_SRCacheContext_Close
0x1800b2030  mov     rcx, [rbp+arg_8]
0x1800b2034  mov     [rbp+arg_8], rsi
0x1800b2038  test    rcx, rcx
0x1800b203b  jz      short loc_1800B2043
0x1800b203d  call    cs:__imp_SRCacheContext_Close
0x1800b2043  mov     rcx, [rbp+arg_0]
0x1800b2047  mov     [rbp+arg_0], rsi
0x1800b204b  test    rcx, rcx
0x1800b204e  jz      short loc_1800B2056
0x1800b2050  call    cs:__imp_SRCacheContext_Close
0x1800b2056  xor     eax, eax
0x1800b2058  add     rsp, 48h
0x1800b205c  pop     rdi
0x1800b205d  pop     rsi
0x1800b205e  pop     rbx
0x1800b205f  pop     rbp
0x1800b2060  retn
```
