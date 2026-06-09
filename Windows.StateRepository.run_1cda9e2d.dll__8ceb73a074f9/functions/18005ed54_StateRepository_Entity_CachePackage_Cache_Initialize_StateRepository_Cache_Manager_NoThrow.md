# StateRepository::Entity::CachePackage::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x18005ed54`
- end: `0x18005f0dd`
- name: `?Cache_Initialize@CachePackage@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `905`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18005dbf0`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x18005ed54`
- `0x180074eb0`
- `0x18007b950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005edab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005edf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005ee7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005ef00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005ef86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f093`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f0a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f0b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f0cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005edab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005edf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005ee7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005ef00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005ef86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f093`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f0a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f0b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18005f0cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005ed8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005ee24`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005eeaa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005ef30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005efcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005ed8a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005ee24`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005eeaa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005ef30`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18005efcf`

## string_xrefs

- `0x18005edb9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005ee3d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005eec3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005ef49`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005efe8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18005edd1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x18005ee55`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x18005eedb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x18005ef66`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackage::Cache_Initialize(
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
  v3 = SRCacheContext_Create(v2, L"Package", 0, &v20);
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
      (void *)0x4BF,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
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
  v3 = SRCacheContext_Create(v7, L"Package\\Data", 0, &v20);
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
      (void *)0x4C2,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
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
  v3 = SRCacheContext_Create(v9, L"Package\\Index", 0, &v20);
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
      (void *)0x4C5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
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
  v3 = SRCacheContext_Create(v11, L"Package\\Index\\PackageFamily", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    v12 = 1223;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"Package\\Index\\PackageFamily");
  if ( v3 < 0 )
  {
    v12 = 1224;
    goto LABEL_19;
  }
  v14 = *(_QWORD *)a1;
  v19 = &v25;
  v20 = 0;
  v21 = 1;
  v3 = SRCacheContext_Create(v14, L"Package\\Index\\PackageFullName", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v19);
    v12 = 1226;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"Package\\Index\\PackageFullName");
  if ( v3 < 0 )
  {
    v12 = 1227;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v26,
         L"Package\\Index");
  if ( v3 < 0 )
  {
    v12 = 1229;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"Package\\Data");
  if ( v3 < 0 )
  {
    v12 = 1230;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache((StateRepository::Cache::Context_NoThrow *)&v23, L"Package");
  if ( v3 < 0 )
  {
    v12 = 1231;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
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
0x18005ed54  push    rbp
0x18005ed56  push    rbx
0x18005ed57  push    rsi
0x18005ed58  push    rdi
0x18005ed59  mov     rbp, rsp
0x18005ed5c  sub     rsp, 48h
0x18005ed60  mov     rdi, rcx
0x18005ed63  mov     [rbp+var_18], 1
0x18005ed67  mov     rcx, [rcx]
0x18005ed6a  lea     rax, [rbp+arg_0]
0x18005ed6e  xor     esi, esi
0x18005ed70  mov     [rbp+var_28], rax
0x18005ed74  lea     r9, [rbp+var_20]
0x18005ed78  mov     [rbp+arg_0], rsi
0x18005ed7c  xor     r8d, r8d
0x18005ed7f  mov     [rbp+var_20], rsi
0x18005ed83  lea     rdx, aPackage_0; "Package"
0x18005ed8a  call    cs:__imp_SRCacheContext_Create
0x18005ed90  mov     ebx, eax
0x18005ed92  cmp     [rbp+var_18], sil
0x18005ed96  jz      short loc_18005EDB1
0x18005ed98  mov     r8, [rbp+var_28]
0x18005ed9c  mov     rdx, [rbp+var_20]
0x18005eda0  mov     rcx, [r8]
0x18005eda3  mov     [r8], rdx
0x18005eda6  test    rcx, rcx
0x18005eda9  jz      short loc_18005EDB1
0x18005edab  call    cs:__imp_SRCacheContext_Close
0x18005edb1  test    ebx, ebx
0x18005edb3  jns     short loc_18005EDFF
0x18005edb5  mov     rcx, [rbp+20h]; this
0x18005edb9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005edc0  mov     r9d, ebx; char *
0x18005edc3  mov     edx, 1C2h; void *
0x18005edc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005edcd  mov     rcx, [rbp+20h]; this
0x18005edd1  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x18005edd8  mov     r9d, ebx; char *
0x18005eddb  mov     edx, 4BFh; void *
0x18005ede0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ede5  mov     rcx, [rbp+arg_0]
0x18005ede9  mov     [rbp+arg_0], rsi
0x18005eded  test    rcx, rcx
0x18005edf0  jz      short loc_18005EDF8
0x18005edf2  call    cs:__imp_SRCacheContext_Close
0x18005edf8  mov     eax, ebx
0x18005edfa  jmp     loc_18005F0D4
0x18005edff  mov     rcx, [rdi]
0x18005ee02  lea     rax, [rbp+arg_8]
0x18005ee06  lea     r9, [rbp+var_20]
0x18005ee0a  mov     [rbp+var_28], rax
0x18005ee0e  xor     r8d, r8d
0x18005ee11  mov     [rbp+arg_8], rsi
0x18005ee15  lea     rdx, aPackageData; "Package\\Data"
0x18005ee1c  mov     [rbp+var_20], rsi
0x18005ee20  mov     [rbp+var_18], 1
0x18005ee24  call    cs:__imp_SRCacheContext_Create
0x18005ee2a  lea     rcx, [rbp+var_28]
0x18005ee2e  mov     ebx, eax
0x18005ee30  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18005ee35  test    ebx, ebx
0x18005ee37  jns     short loc_18005EE85
0x18005ee39  mov     rcx, [rbp+20h]; this
0x18005ee3d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005ee44  mov     r9d, ebx; char *
0x18005ee47  mov     edx, 1C2h; void *
0x18005ee4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ee51  mov     rcx, [rbp+20h]; this
0x18005ee55  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x18005ee5c  mov     r9d, ebx; char *
0x18005ee5f  mov     edx, 4C2h; void *
0x18005ee64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ee69  mov     rcx, [rbp+arg_8]
0x18005ee6d  mov     [rbp+arg_8], rsi
0x18005ee71  test    rcx, rcx
0x18005ee74  jz      loc_18005EDE5
0x18005ee7a  call    cs:__imp_SRCacheContext_Close
0x18005ee80  jmp     loc_18005EDE5
0x18005ee85  mov     rcx, [rdi]
0x18005ee88  lea     rax, [rbp+arg_18]
0x18005ee8c  lea     r9, [rbp+var_20]
0x18005ee90  mov     [rbp+var_28], rax
0x18005ee94  xor     r8d, r8d
0x18005ee97  mov     [rbp+arg_18], rsi
0x18005ee9b  lea     rdx, aPackageIndex; "Package\\Index"
0x18005eea2  mov     [rbp+var_20], rsi
0x18005eea6  mov     [rbp+var_18], 1
0x18005eeaa  call    cs:__imp_SRCacheContext_Create
0x18005eeb0  lea     rcx, [rbp+var_28]
0x18005eeb4  mov     ebx, eax
0x18005eeb6  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18005eebb  test    ebx, ebx
0x18005eebd  jns     short loc_18005EF0B
0x18005eebf  mov     rcx, [rbp+20h]; this
0x18005eec3  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005eeca  mov     r9d, ebx; char *
0x18005eecd  mov     edx, 1C2h; void *
0x18005eed2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eed7  mov     rcx, [rbp+20h]; this
0x18005eedb  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x18005eee2  mov     r9d, ebx; char *
0x18005eee5  mov     edx, 4C5h; void *
0x18005eeea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eeef  mov     rcx, [rbp+arg_18]
0x18005eef3  mov     [rbp+arg_18], rsi
0x18005eef7  test    rcx, rcx
0x18005eefa  jz      loc_18005EE69
0x18005ef00  call    cs:__imp_SRCacheContext_Close
0x18005ef06  jmp     loc_18005EE69
0x18005ef0b  mov     rcx, [rdi]
0x18005ef0e  lea     rax, [rbp+arg_10]
0x18005ef12  lea     r9, [rbp+var_20]
0x18005ef16  mov     [rbp+var_28], rax
0x18005ef1a  xor     r8d, r8d
0x18005ef1d  mov     [rbp+arg_10], rsi
0x18005ef21  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18005ef28  mov     [rbp+var_20], rsi
0x18005ef2c  mov     [rbp+var_18], 1
0x18005ef30  call    cs:__imp_SRCacheContext_Create
0x18005ef36  lea     rcx, [rbp+var_28]
0x18005ef3a  mov     ebx, eax
0x18005ef3c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18005ef41  test    ebx, ebx
0x18005ef43  jns     short loc_18005EF91
0x18005ef45  mov     rcx, [rbp+20h]; this
0x18005ef49  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005ef50  mov     r9d, ebx; char *
0x18005ef53  mov     edx, 1C2h; void *
0x18005ef58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef5d  mov     edx, 4C7h; void *
0x18005ef62  mov     rcx, [rbp+20h]; this
0x18005ef66  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x18005ef6d  mov     r9d, ebx; char *
0x18005ef70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef75  mov     rcx, [rbp+arg_10]
0x18005ef79  mov     [rbp+arg_10], rsi
0x18005ef7d  test    rcx, rcx
0x18005ef80  jz      loc_18005EEEF
0x18005ef86  call    cs:__imp_SRCacheContext_Close
0x18005ef8c  jmp     loc_18005EEEF
0x18005ef91  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18005ef98  lea     rcx, [rbp+arg_10]; this
0x18005ef9c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18005efa1  mov     ebx, eax
0x18005efa3  test    eax, eax
0x18005efa5  jns     short loc_18005EFAE
0x18005efa7  mov     edx, 4C8h
0x18005efac  jmp     short loc_18005EF62
0x18005efae  mov     rcx, [rdi]
0x18005efb1  lea     rax, [rbp+arg_10]
0x18005efb5  lea     r9, [rbp+var_20]
0x18005efb9  mov     [rbp+var_28], rax
0x18005efbd  xor     r8d, r8d
0x18005efc0  mov     [rbp+var_20], rsi
0x18005efc4  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18005efcb  mov     [rbp+var_18], 1
0x18005efcf  call    cs:__imp_SRCacheContext_Create
0x18005efd5  lea     rcx, [rbp+var_28]
0x18005efd9  mov     ebx, eax
0x18005efdb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18005efe0  test    ebx, ebx
0x18005efe2  jns     short loc_18005F006
0x18005efe4  mov     rcx, [rbp+20h]; this
0x18005efe8  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18005efef  mov     r9d, ebx; char *
0x18005eff2  mov     edx, 1C2h; void *
0x18005eff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005effc  mov     edx, 4CAh
0x18005f001  jmp     loc_18005EF62
0x18005f006  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18005f00d  lea     rcx, [rbp+arg_10]; this
0x18005f011  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18005f016  mov     ebx, eax
0x18005f018  test    eax, eax
0x18005f01a  jns     short loc_18005F026
0x18005f01c  mov     edx, 4CBh
0x18005f021  jmp     loc_18005EF62
0x18005f026  lea     rdx, aPackageIndex; "Package\\Index"
0x18005f02d  lea     rcx, [rbp+arg_18]; this
0x18005f031  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18005f036  mov     ebx, eax
0x18005f038  test    eax, eax
0x18005f03a  jns     short loc_18005F046
0x18005f03c  mov     edx, 4CDh
0x18005f041  jmp     loc_18005EF62
0x18005f046  lea     rdx, aPackageData; "Package\\Data"
0x18005f04d  lea     rcx, [rbp+arg_8]; this
0x18005f051  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18005f056  mov     ebx, eax
0x18005f058  test    eax, eax
0x18005f05a  jns     short loc_18005F066
0x18005f05c  mov     edx, 4CEh
0x18005f061  jmp     loc_18005EF62
0x18005f066  lea     rdx, aPackage_0; "Package"
0x18005f06d  lea     rcx, [rbp+arg_0]; this
0x18005f071  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18005f076  mov     ebx, eax
0x18005f078  test    eax, eax
0x18005f07a  jns     short loc_18005F086
0x18005f07c  mov     edx, 4CFh
0x18005f081  jmp     loc_18005EF62
0x18005f086  mov     rcx, [rbp+arg_10]
0x18005f08a  mov     [rbp+arg_10], rsi
0x18005f08e  test    rcx, rcx
0x18005f091  jz      short loc_18005F099
0x18005f093  call    cs:__imp_SRCacheContext_Close
0x18005f099  mov     rcx, [rbp+arg_18]
0x18005f09d  mov     [rbp+arg_18], rsi
0x18005f0a1  test    rcx, rcx
0x18005f0a4  jz      short loc_18005F0AC
0x18005f0a6  call    cs:__imp_SRCacheContext_Close
0x18005f0ac  mov     rcx, [rbp+arg_8]
0x18005f0b0  mov     [rbp+arg_8], rsi
0x18005f0b4  test    rcx, rcx
0x18005f0b7  jz      short loc_18005F0BF
0x18005f0b9  call    cs:__imp_SRCacheContext_Close
0x18005f0bf  mov     rcx, [rbp+arg_0]
0x18005f0c3  mov     [rbp+arg_0], rsi
0x18005f0c7  test    rcx, rcx
0x18005f0ca  jz      short loc_18005F0D2
0x18005f0cc  call    cs:__imp_SRCacheContext_Close
0x18005f0d2  xor     eax, eax
0x18005f0d4  add     rsp, 48h
0x18005f0d8  pop     rdi
0x18005f0d9  pop     rsi
0x18005f0da  pop     rbx
0x18005f0db  pop     rbp
0x18005f0dc  retn
```
