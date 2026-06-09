# StateRepository::Entity::CachePackageExternalLocation::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x18008b158`
- end: `0x18008b492`
- name: `?Cache_Initialize@CachePackageExternalLocation@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `826`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18008a5c0`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x18008b158`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b1af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b1f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b249`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b294`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b2e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b330`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b3b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b45b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b46e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b481`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b1af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b1f6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b249`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b294`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b2e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b330`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b3b6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b45b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b46e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008b481`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b18e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b228`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b2c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b360`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b18e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b228`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b2c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18008b360`

## string_xrefs

- `0x18008b1bd`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18008b257`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18008b2f3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18008b379`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18008b1d5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18008b26f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18008b30b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x18008b396`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageExternalLocation::Cache_Initialize(
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
  v3 = SRCacheContext_Create(v2, L"PackageExternalLocation", 0, &v21);
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
      (void *)0x119,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
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
  v20 = &v25;
  v25 = 0;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v7, L"PackageExternalLocation\\Data", 0, &v21);
  if ( v22 )
  {
    v8 = *v20;
    *v20 = v21;
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
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
LABEL_14:
    v9 = v25;
    v25 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    goto LABEL_6;
  }
  v10 = *(_QWORD *)a1;
  v20 = &v26;
  v26 = 0;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v10, L"PackageExternalLocation\\Index", 0, &v21);
  if ( v22 )
  {
    v11 = *v20;
    *v20 = v21;
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
      (int)v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
LABEL_21:
    v12 = v26;
    v26 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_14;
  }
  v13 = *(_QWORD *)a1;
  v20 = &v27;
  v27 = 0;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v13, L"PackageExternalLocation\\Index\\UserAndPackage", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v14 = 289;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v27,
         L"PackageExternalLocation\\Index\\UserAndPackage");
  if ( v3 < 0 )
  {
    v14 = 290;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         L"PackageExternalLocation\\Index");
  if ( v3 < 0 )
  {
    v14 = 292;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageExternalLocation\\Data");
  if ( v3 < 0 )
  {
    v14 = 293;
    goto LABEL_25;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"PackageExternalLocation");
  if ( v3 < 0 )
  {
    v14 = 294;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v15 = v27;
    v27 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_21;
  }
  v16 = v27;
  v27 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v26;
  v26 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v25;
  v25 = 0;
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
0x18008b158  push    rbp
0x18008b15a  push    rbx
0x18008b15b  push    rsi
0x18008b15c  push    rdi
0x18008b15d  mov     rbp, rsp
0x18008b160  sub     rsp, 48h
0x18008b164  mov     rdi, rcx
0x18008b167  mov     [rbp+var_18], 1
0x18008b16b  mov     rcx, [rcx]
0x18008b16e  lea     rax, [rbp+arg_0]
0x18008b172  xor     esi, esi
0x18008b174  mov     [rbp+var_28], rax
0x18008b178  lea     r9, [rbp+var_20]
0x18008b17c  mov     [rbp+arg_0], rsi
0x18008b180  xor     r8d, r8d
0x18008b183  mov     [rbp+var_20], rsi
0x18008b187  lea     rdx, aPackageexterna_12; "PackageExternalLocation"
0x18008b18e  call    cs:__imp_SRCacheContext_Create
0x18008b194  mov     ebx, eax
0x18008b196  cmp     [rbp+var_18], sil
0x18008b19a  jz      short loc_18008B1B5
0x18008b19c  mov     r8, [rbp+var_28]
0x18008b1a0  mov     rdx, [rbp+var_20]
0x18008b1a4  mov     rcx, [r8]
0x18008b1a7  mov     [r8], rdx
0x18008b1aa  test    rcx, rcx
0x18008b1ad  jz      short loc_18008B1B5
0x18008b1af  call    cs:__imp_SRCacheContext_Close
0x18008b1b5  test    ebx, ebx
0x18008b1b7  jns     short loc_18008B203
0x18008b1b9  mov     rcx, [rbp+20h]; this
0x18008b1bd  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18008b1c4  mov     r9d, ebx; char *
0x18008b1c7  mov     edx, 1C2h; void *
0x18008b1cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b1d1  mov     rcx, [rbp+20h]; this
0x18008b1d5  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18008b1dc  mov     r9d, ebx; char *
0x18008b1df  mov     edx, 119h; void *
0x18008b1e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b1e9  mov     rcx, [rbp+arg_0]
0x18008b1ed  mov     [rbp+arg_0], rsi
0x18008b1f1  test    rcx, rcx
0x18008b1f4  jz      short loc_18008B1FC
0x18008b1f6  call    cs:__imp_SRCacheContext_Close
0x18008b1fc  mov     eax, ebx
0x18008b1fe  jmp     loc_18008B489
0x18008b203  mov     rcx, [rdi]
0x18008b206  lea     rax, [rbp+arg_8]
0x18008b20a  lea     r9, [rbp+var_20]
0x18008b20e  mov     [rbp+var_28], rax
0x18008b212  xor     r8d, r8d
0x18008b215  mov     [rbp+arg_8], rsi
0x18008b219  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18008b220  mov     [rbp+var_20], rsi
0x18008b224  mov     [rbp+var_18], 1
0x18008b228  call    cs:__imp_SRCacheContext_Create
0x18008b22e  mov     ebx, eax
0x18008b230  cmp     [rbp+var_18], sil
0x18008b234  jz      short loc_18008B24F
0x18008b236  mov     r8, [rbp+var_28]
0x18008b23a  mov     rdx, [rbp+var_20]
0x18008b23e  mov     rcx, [r8]
0x18008b241  mov     [r8], rdx
0x18008b244  test    rcx, rcx
0x18008b247  jz      short loc_18008B24F
0x18008b249  call    cs:__imp_SRCacheContext_Close
0x18008b24f  test    ebx, ebx
0x18008b251  jns     short loc_18008B29F
0x18008b253  mov     rcx, [rbp+20h]; this
0x18008b257  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18008b25e  mov     r9d, ebx; char *
0x18008b261  mov     edx, 1C2h; void *
0x18008b266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b26b  mov     rcx, [rbp+20h]; this
0x18008b26f  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18008b276  mov     r9d, ebx; char *
0x18008b279  mov     edx, 11Ch; void *
0x18008b27e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b283  mov     rcx, [rbp+arg_8]
0x18008b287  mov     [rbp+arg_8], rsi
0x18008b28b  test    rcx, rcx
0x18008b28e  jz      loc_18008B1E9
0x18008b294  call    cs:__imp_SRCacheContext_Close
0x18008b29a  jmp     loc_18008B1E9
0x18008b29f  mov     rcx, [rdi]
0x18008b2a2  lea     rax, [rbp+arg_10]
0x18008b2a6  lea     r9, [rbp+var_20]
0x18008b2aa  mov     [rbp+var_28], rax
0x18008b2ae  xor     r8d, r8d
0x18008b2b1  mov     [rbp+arg_10], rsi
0x18008b2b5  lea     rdx, aPackageexterna_7; "PackageExternalLocation\\Index"
0x18008b2bc  mov     [rbp+var_20], rsi
0x18008b2c0  mov     [rbp+var_18], 1
0x18008b2c4  call    cs:__imp_SRCacheContext_Create
0x18008b2ca  mov     ebx, eax
0x18008b2cc  cmp     [rbp+var_18], sil
0x18008b2d0  jz      short loc_18008B2EB
0x18008b2d2  mov     r8, [rbp+var_28]
0x18008b2d6  mov     rdx, [rbp+var_20]
0x18008b2da  mov     rcx, [r8]
0x18008b2dd  mov     [r8], rdx
0x18008b2e0  test    rcx, rcx
0x18008b2e3  jz      short loc_18008B2EB
0x18008b2e5  call    cs:__imp_SRCacheContext_Close
0x18008b2eb  test    ebx, ebx
0x18008b2ed  jns     short loc_18008B33B
0x18008b2ef  mov     rcx, [rbp+20h]; this
0x18008b2f3  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18008b2fa  mov     r9d, ebx; char *
0x18008b2fd  mov     edx, 1C2h; void *
0x18008b302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b307  mov     rcx, [rbp+20h]; this
0x18008b30b  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18008b312  mov     r9d, ebx; char *
0x18008b315  mov     edx, 11Fh; void *
0x18008b31a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b31f  mov     rcx, [rbp+arg_10]
0x18008b323  mov     [rbp+arg_10], rsi
0x18008b327  test    rcx, rcx
0x18008b32a  jz      loc_18008B283
0x18008b330  call    cs:__imp_SRCacheContext_Close
0x18008b336  jmp     loc_18008B283
0x18008b33b  mov     rcx, [rdi]
0x18008b33e  lea     rax, [rbp+arg_18]
0x18008b342  lea     r9, [rbp+var_20]
0x18008b346  mov     [rbp+var_28], rax
0x18008b34a  xor     r8d, r8d
0x18008b34d  mov     [rbp+arg_18], rsi
0x18008b351  lea     rdx, aPackageexterna_8; "PackageExternalLocation\\Index\\UserAnd"...
0x18008b358  mov     [rbp+var_20], rsi
0x18008b35c  mov     [rbp+var_18], 1
0x18008b360  call    cs:__imp_SRCacheContext_Create
0x18008b366  lea     rcx, [rbp+var_28]
0x18008b36a  mov     ebx, eax
0x18008b36c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18008b371  test    ebx, ebx
0x18008b373  jns     short loc_18008B3C1
0x18008b375  mov     rcx, [rbp+20h]; this
0x18008b379  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18008b380  mov     r9d, ebx; char *
0x18008b383  mov     edx, 1C2h; void *
0x18008b388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b38d  mov     edx, 121h; void *
0x18008b392  mov     rcx, [rbp+20h]; this
0x18008b396  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x18008b39d  mov     r9d, ebx; char *
0x18008b3a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b3a5  mov     rcx, [rbp+arg_18]
0x18008b3a9  mov     [rbp+arg_18], rsi
0x18008b3ad  test    rcx, rcx
0x18008b3b0  jz      loc_18008B31F
0x18008b3b6  call    cs:__imp_SRCacheContext_Close
0x18008b3bc  jmp     loc_18008B31F
0x18008b3c1  lea     rdx, aPackageexterna_8; "PackageExternalLocation\\Index\\UserAnd"...
0x18008b3c8  lea     rcx, [rbp+arg_18]; this
0x18008b3cc  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18008b3d1  mov     ebx, eax
0x18008b3d3  test    eax, eax
0x18008b3d5  jns     short loc_18008B3DE
0x18008b3d7  mov     edx, 122h
0x18008b3dc  jmp     short loc_18008B392
0x18008b3de  lea     rdx, aPackageexterna_7; "PackageExternalLocation\\Index"
0x18008b3e5  lea     rcx, [rbp+arg_10]; this
0x18008b3e9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18008b3ee  mov     ebx, eax
0x18008b3f0  test    eax, eax
0x18008b3f2  jns     short loc_18008B3FB
0x18008b3f4  mov     edx, 124h
0x18008b3f9  jmp     short loc_18008B392
0x18008b3fb  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18008b402  lea     rcx, [rbp+arg_8]; this
0x18008b406  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18008b40b  mov     ebx, eax
0x18008b40d  test    eax, eax
0x18008b40f  jns     short loc_18008B41B
0x18008b411  mov     edx, 125h
0x18008b416  jmp     loc_18008B392
0x18008b41b  lea     rdx, aPackageexterna_12; "PackageExternalLocation"
0x18008b422  lea     rcx, [rbp+arg_0]; this
0x18008b426  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18008b42b  mov     ebx, eax
0x18008b42d  test    eax, eax
0x18008b42f  jns     short loc_18008B43B
0x18008b431  mov     edx, 126h
0x18008b436  jmp     loc_18008B392
0x18008b43b  mov     rcx, [rbp+arg_18]
0x18008b43f  mov     [rbp+arg_18], rsi
0x18008b443  test    rcx, rcx
0x18008b446  jz      short loc_18008B44E
0x18008b448  call    cs:__imp_SRCacheContext_Close
0x18008b44e  mov     rcx, [rbp+arg_10]
0x18008b452  mov     [rbp+arg_10], rsi
0x18008b456  test    rcx, rcx
0x18008b459  jz      short loc_18008B461
0x18008b45b  call    cs:__imp_SRCacheContext_Close
0x18008b461  mov     rcx, [rbp+arg_8]
0x18008b465  mov     [rbp+arg_8], rsi
0x18008b469  test    rcx, rcx
0x18008b46c  jz      short loc_18008B474
0x18008b46e  call    cs:__imp_SRCacheContext_Close
0x18008b474  mov     rcx, [rbp+arg_0]
0x18008b478  mov     [rbp+arg_0], rsi
0x18008b47c  test    rcx, rcx
0x18008b47f  jz      short loc_18008B487
0x18008b481  call    cs:__imp_SRCacheContext_Close
0x18008b487  xor     eax, eax
0x18008b489  add     rsp, 48h
0x18008b48d  pop     rdi
0x18008b48e  pop     rsi
0x18008b48f  pop     rbx
0x18008b490  pop     rbp
0x18008b491  retn
```
