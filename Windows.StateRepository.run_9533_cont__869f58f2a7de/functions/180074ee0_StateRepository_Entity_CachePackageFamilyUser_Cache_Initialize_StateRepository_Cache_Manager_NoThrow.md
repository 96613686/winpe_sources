# StateRepository::Entity::CachePackageFamilyUser::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x180074ee0`
- end: `0x1800752e1`
- name: `?Cache_Initialize@CachePackageFamilyUser@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800882a0`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x180074ee0`
- `0x18007b950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074f37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074f7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180075006`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007508c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180075112`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180075297`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800752aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800752bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800752d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074f37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074f7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180075006`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007508c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180075112`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180075297`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800752aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800752bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800752d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180074f16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180074fb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180075036`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800750bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18007515b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800751d3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180074f16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180074fb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180075036`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800750bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18007515b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1800751d3`

## string_xrefs

- `0x180074f45`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180074fc9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18007504f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800750d5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180075174`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800751ec`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180074f5d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x180074fe1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x180075067`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x1800750f2`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageFamilyUser::Cache_Initialize(
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
  v3 = SRCacheContext_Create(v2, L"PackageFamilyUser", 0, &v21);
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
      (void *)0x14E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
  v3 = SRCacheContext_Create(v7, L"PackageFamilyUser\\Data", 0, &v21);
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
      (void *)0x151,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
  v3 = SRCacheContext_Create(v9, L"PackageFamilyUser\\Index", 0, &v21);
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
      (void *)0x154,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
  v3 = SRCacheContext_Create(v11, L"PackageFamilyUser\\Index\\PackageFamily", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v12 = 342;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageFamilyUser\\Index\\PackageFamily");
  if ( v3 < 0 )
  {
    v12 = 343;
    goto LABEL_19;
  }
  v14 = *(_QWORD *)a1;
  v20 = &v25;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v14, L"PackageFamilyUser\\Index\\User", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v12 = 345;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageFamilyUser\\Index\\User");
  if ( v3 < 0 )
  {
    v12 = 346;
    goto LABEL_19;
  }
  v15 = *(_QWORD *)a1;
  v20 = &v25;
  v21 = 0;
  v22 = 1;
  v3 = SRCacheContext_Create(v15, L"PackageFamilyUser\\Index\\UserAndPackageFamily", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v20);
    v12 = 348;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PackageFamilyUser\\Index\\UserAndPackageFamily");
  if ( v3 < 0 )
  {
    v12 = 349;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v27,
         L"PackageFamilyUser\\Index");
  if ( v3 < 0 )
  {
    v12 = 351;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         L"PackageFamilyUser\\Data");
  if ( v3 < 0 )
  {
    v12 = 352;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"PackageFamilyUser");
  if ( v3 < 0 )
  {
    v12 = 353;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
0x180074ee0  push    rbp
0x180074ee2  push    rbx
0x180074ee3  push    rsi
0x180074ee4  push    rdi
0x180074ee5  mov     rbp, rsp
0x180074ee8  sub     rsp, 48h
0x180074eec  mov     rdi, rcx
0x180074eef  mov     [rbp+var_18], 1
0x180074ef3  mov     rcx, [rcx]
0x180074ef6  lea     rax, [rbp+arg_0]
0x180074efa  xor     esi, esi
0x180074efc  mov     [rbp+var_28], rax
0x180074f00  lea     r9, [rbp+var_20]
0x180074f04  mov     [rbp+arg_0], rsi
0x180074f08  xor     r8d, r8d
0x180074f0b  mov     [rbp+var_20], rsi
0x180074f0f  lea     rdx, aPackagefamilyu_10; "PackageFamilyUser"
0x180074f16  call    cs:__imp_SRCacheContext_Create
0x180074f1c  mov     ebx, eax
0x180074f1e  cmp     [rbp+var_18], sil
0x180074f22  jz      short loc_180074F3D
0x180074f24  mov     r8, [rbp+var_28]
0x180074f28  mov     rdx, [rbp+var_20]
0x180074f2c  mov     rcx, [r8]
0x180074f2f  mov     [r8], rdx
0x180074f32  test    rcx, rcx
0x180074f35  jz      short loc_180074F3D
0x180074f37  call    cs:__imp_SRCacheContext_Close
0x180074f3d  test    ebx, ebx
0x180074f3f  jns     short loc_180074F8B
0x180074f41  mov     rcx, [rbp+20h]; this
0x180074f45  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180074f4c  mov     r9d, ebx; char *
0x180074f4f  mov     edx, 1C2h; void *
0x180074f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074f59  mov     rcx, [rbp+20h]; this
0x180074f5d  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180074f64  mov     r9d, ebx; char *
0x180074f67  mov     edx, 14Eh; void *
0x180074f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074f71  mov     rcx, [rbp+arg_0]
0x180074f75  mov     [rbp+arg_0], rsi
0x180074f79  test    rcx, rcx
0x180074f7c  jz      short loc_180074F84
0x180074f7e  call    cs:__imp_SRCacheContext_Close
0x180074f84  mov     eax, ebx
0x180074f86  jmp     loc_1800752D8
0x180074f8b  mov     rcx, [rdi]
0x180074f8e  lea     rax, [rbp+arg_10]
0x180074f92  lea     r9, [rbp+var_20]
0x180074f96  mov     [rbp+var_28], rax
0x180074f9a  xor     r8d, r8d
0x180074f9d  mov     [rbp+arg_10], rsi
0x180074fa1  lea     rdx, aPackagefamilyu_6; "PackageFamilyUser\\Data"
0x180074fa8  mov     [rbp+var_20], rsi
0x180074fac  mov     [rbp+var_18], 1
0x180074fb0  call    cs:__imp_SRCacheContext_Create
0x180074fb6  lea     rcx, [rbp+var_28]
0x180074fba  mov     ebx, eax
0x180074fbc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180074fc1  test    ebx, ebx
0x180074fc3  jns     short loc_180075011
0x180074fc5  mov     rcx, [rbp+20h]; this
0x180074fc9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180074fd0  mov     r9d, ebx; char *
0x180074fd3  mov     edx, 1C2h; void *
0x180074fd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074fdd  mov     rcx, [rbp+20h]; this
0x180074fe1  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180074fe8  mov     r9d, ebx; char *
0x180074feb  mov     edx, 151h; void *
0x180074ff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074ff5  mov     rcx, [rbp+arg_10]
0x180074ff9  mov     [rbp+arg_10], rsi
0x180074ffd  test    rcx, rcx
0x180075000  jz      loc_180074F71
0x180075006  call    cs:__imp_SRCacheContext_Close
0x18007500c  jmp     loc_180074F71
0x180075011  mov     rcx, [rdi]
0x180075014  lea     rax, [rbp+arg_18]
0x180075018  lea     r9, [rbp+var_20]
0x18007501c  mov     [rbp+var_28], rax
0x180075020  xor     r8d, r8d
0x180075023  mov     [rbp+arg_18], rsi
0x180075027  lea     rdx, aPackagefamilyu_12; "PackageFamilyUser\\Index"
0x18007502e  mov     [rbp+var_20], rsi
0x180075032  mov     [rbp+var_18], 1
0x180075036  call    cs:__imp_SRCacheContext_Create
0x18007503c  lea     rcx, [rbp+var_28]
0x180075040  mov     ebx, eax
0x180075042  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180075047  test    ebx, ebx
0x180075049  jns     short loc_180075097
0x18007504b  mov     rcx, [rbp+20h]; this
0x18007504f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180075056  mov     r9d, ebx; char *
0x180075059  mov     edx, 1C2h; void *
0x18007505e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075063  mov     rcx, [rbp+20h]; this
0x180075067  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x18007506e  mov     r9d, ebx; char *
0x180075071  mov     edx, 154h; void *
0x180075076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007507b  mov     rcx, [rbp+arg_18]
0x18007507f  mov     [rbp+arg_18], rsi
0x180075083  test    rcx, rcx
0x180075086  jz      loc_180074FF5
0x18007508c  call    cs:__imp_SRCacheContext_Close
0x180075092  jmp     loc_180074FF5
0x180075097  mov     rcx, [rdi]
0x18007509a  lea     rax, [rbp+arg_8]
0x18007509e  lea     r9, [rbp+var_20]
0x1800750a2  mov     [rbp+var_28], rax
0x1800750a6  xor     r8d, r8d
0x1800750a9  mov     [rbp+arg_8], rsi
0x1800750ad  lea     rdx, aPackagefamilyu_33; "PackageFamilyUser\\Index\\PackageFamily"
0x1800750b4  mov     [rbp+var_20], rsi
0x1800750b8  mov     [rbp+var_18], 1
0x1800750bc  call    cs:__imp_SRCacheContext_Create
0x1800750c2  lea     rcx, [rbp+var_28]
0x1800750c6  mov     ebx, eax
0x1800750c8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800750cd  test    ebx, ebx
0x1800750cf  jns     short loc_18007511D
0x1800750d1  mov     rcx, [rbp+20h]; this
0x1800750d5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800750dc  mov     r9d, ebx; char *
0x1800750df  mov     edx, 1C2h; void *
0x1800750e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800750e9  mov     edx, 156h; void *
0x1800750ee  mov     rcx, [rbp+20h]; this
0x1800750f2  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x1800750f9  mov     r9d, ebx; char *
0x1800750fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075101  mov     rcx, [rbp+arg_8]
0x180075105  mov     [rbp+arg_8], rsi
0x180075109  test    rcx, rcx
0x18007510c  jz      loc_18007507B
0x180075112  call    cs:__imp_SRCacheContext_Close
0x180075118  jmp     loc_18007507B
0x18007511d  lea     rdx, aPackagefamilyu_33; "PackageFamilyUser\\Index\\PackageFamily"
0x180075124  lea     rcx, [rbp+arg_8]; this
0x180075128  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007512d  mov     ebx, eax
0x18007512f  test    eax, eax
0x180075131  jns     short loc_18007513A
0x180075133  mov     edx, 157h
0x180075138  jmp     short loc_1800750EE
0x18007513a  mov     rcx, [rdi]
0x18007513d  lea     rax, [rbp+arg_8]
0x180075141  lea     r9, [rbp+var_20]
0x180075145  mov     [rbp+var_28], rax
0x180075149  xor     r8d, r8d
0x18007514c  mov     [rbp+var_20], rsi
0x180075150  lea     rdx, aPackagefamilyu_32; "PackageFamilyUser\\Index\\User"
0x180075157  mov     [rbp+var_18], 1
0x18007515b  call    cs:__imp_SRCacheContext_Create
0x180075161  lea     rcx, [rbp+var_28]
0x180075165  mov     ebx, eax
0x180075167  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18007516c  test    ebx, ebx
0x18007516e  jns     short loc_180075192
0x180075170  mov     rcx, [rbp+20h]; this
0x180075174  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18007517b  mov     r9d, ebx; char *
0x18007517e  mov     edx, 1C2h; void *
0x180075183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075188  mov     edx, 159h
0x18007518d  jmp     loc_1800750EE
0x180075192  lea     rdx, aPackagefamilyu_32; "PackageFamilyUser\\Index\\User"
0x180075199  lea     rcx, [rbp+arg_8]; this
0x18007519d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800751a2  mov     ebx, eax
0x1800751a4  test    eax, eax
0x1800751a6  jns     short loc_1800751B2
0x1800751a8  mov     edx, 15Ah
0x1800751ad  jmp     loc_1800750EE
0x1800751b2  mov     rcx, [rdi]
0x1800751b5  lea     rax, [rbp+arg_8]
0x1800751b9  lea     r9, [rbp+var_20]
0x1800751bd  mov     [rbp+var_28], rax
0x1800751c1  xor     r8d, r8d
0x1800751c4  mov     [rbp+var_20], rsi
0x1800751c8  lea     rdx, aPackagefamilyu_26; "PackageFamilyUser\\Index\\UserAndPackag"...
0x1800751cf  mov     [rbp+var_18], 1
0x1800751d3  call    cs:__imp_SRCacheContext_Create
0x1800751d9  lea     rcx, [rbp+var_28]
0x1800751dd  mov     ebx, eax
0x1800751df  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800751e4  test    ebx, ebx
0x1800751e6  jns     short loc_18007520A
0x1800751e8  mov     rcx, [rbp+20h]; this
0x1800751ec  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800751f3  mov     r9d, ebx; char *
0x1800751f6  mov     edx, 1C2h; void *
0x1800751fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075200  mov     edx, 15Ch
0x180075205  jmp     loc_1800750EE
0x18007520a  lea     rdx, aPackagefamilyu_26; "PackageFamilyUser\\Index\\UserAndPackag"...
0x180075211  lea     rcx, [rbp+arg_8]; this
0x180075215  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007521a  mov     ebx, eax
0x18007521c  test    eax, eax
0x18007521e  jns     short loc_18007522A
0x180075220  mov     edx, 15Dh
0x180075225  jmp     loc_1800750EE
0x18007522a  lea     rdx, aPackagefamilyu_12; "PackageFamilyUser\\Index"
0x180075231  lea     rcx, [rbp+arg_18]; this
0x180075235  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007523a  mov     ebx, eax
0x18007523c  test    eax, eax
0x18007523e  jns     short loc_18007524A
0x180075240  mov     edx, 15Fh
0x180075245  jmp     loc_1800750EE
0x18007524a  lea     rdx, aPackagefamilyu_6; "PackageFamilyUser\\Data"
0x180075251  lea     rcx, [rbp+arg_10]; this
0x180075255  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007525a  mov     ebx, eax
0x18007525c  test    eax, eax
0x18007525e  jns     short loc_18007526A
0x180075260  mov     edx, 160h
0x180075265  jmp     loc_1800750EE
0x18007526a  lea     rdx, aPackagefamilyu_10; "PackageFamilyUser"
0x180075271  lea     rcx, [rbp+arg_0]; this
0x180075275  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18007527a  mov     ebx, eax
0x18007527c  test    eax, eax
0x18007527e  jns     short loc_18007528A
0x180075280  mov     edx, 161h
0x180075285  jmp     loc_1800750EE
0x18007528a  mov     rcx, [rbp+arg_8]
0x18007528e  mov     [rbp+arg_8], rsi
0x180075292  test    rcx, rcx
0x180075295  jz      short loc_18007529D
0x180075297  call    cs:__imp_SRCacheContext_Close
0x18007529d  mov     rcx, [rbp+arg_18]
0x1800752a1  mov     [rbp+arg_18], rsi
0x1800752a5  test    rcx, rcx
0x1800752a8  jz      short loc_1800752B0
0x1800752aa  call    cs:__imp_SRCacheContext_Close
0x1800752b0  mov     rcx, [rbp+arg_10]
0x1800752b4  mov     [rbp+arg_10], rsi
0x1800752b8  test    rcx, rcx
0x1800752bb  jz      short loc_1800752C3
0x1800752bd  call    cs:__imp_SRCacheContext_Close
0x1800752c3  mov     rcx, [rbp+arg_0]
0x1800752c7  mov     [rbp+arg_0], rsi
0x1800752cb  test    rcx, rcx
0x1800752ce  jz      short loc_1800752D6
0x1800752d0  call    cs:__imp_SRCacheContext_Close
0x1800752d6  xor     eax, eax
0x1800752d8  add     rsp, 48h
0x1800752dc  pop     rdi
0x1800752dd  pop     rsi
0x1800752de  pop     rbx
0x1800752df  pop     rbp
0x1800752e0  retn
```
