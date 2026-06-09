# StateRepository::Entity::CachePkgExtension::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x18014f538`
- end: `0x18014f8ab`
- name: `?Cache_Initialize@CachePkgExtension@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `883`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180200320`
- `0x1802723f0`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x18014f538`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f5c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f648`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f6ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f754`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f861`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f874`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f887`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f89a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f5c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f648`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f6ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f754`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f861`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f874`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f887`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f89a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f56e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f5f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f678`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f6fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f79d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f56e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f5f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f678`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f6fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18014f79d`

## string_xrefs

- `0x18014f587`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014f60b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014f691`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014f717`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014f7b6`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014f669`: `PkgExtension\Index`
- `0x18014f7f4`: `PkgExtension\Index`
- `0x18014f567`: `PkgExtension`
- `0x18014f834`: `PkgExtension`
- `0x18014f5e3`: `PkgExtension\Data`
- `0x18014f814`: `PkgExtension\Data`
- `0x18014f59f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18014f623`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18014f6a9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18014f734`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18014f6ef`: `PkgExtension\Index\ExtensionAndName`
- `0x18014f75f`: `PkgExtension\Index\ExtensionAndName`
- `0x18014f792`: `PkgExtension\Index\Name`
- `0x18014f7d4`: `PkgExtension\Index\Name`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePkgExtension::Cache_Initialize(
        struct StateRepository::Cache::Manager_NoThrow *a1)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 *v18; // [rsp+20h] [rbp-28h] BYREF
  __int64 v19; // [rsp+28h] [rbp-20h] BYREF
  char v20; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v22; // [rsp+70h] [rbp+28h] BYREF
  __int64 v23; // [rsp+78h] [rbp+30h] BYREF
  __int64 v24; // [rsp+80h] [rbp+38h] BYREF
  __int64 v25; // [rsp+88h] [rbp+40h] BYREF

  v20 = 1;
  v2 = *(_QWORD *)a1;
  v18 = &v22;
  v22 = 0;
  v19 = 0;
  v3 = SRCacheContext_Create(v2, L"PkgExtension", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
LABEL_3:
    v4 = v22;
    v22 = 0;
    if ( v4 )
      SRCacheContext_Close(v4);
    return (unsigned int)v3;
  }
  v6 = *(_QWORD *)a1;
  v18 = &v23;
  v23 = 0;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v6, L"PkgExtension\\Data", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
LABEL_8:
    v7 = v23;
    v23 = 0;
    if ( v7 )
      SRCacheContext_Close(v7);
    goto LABEL_3;
  }
  v8 = *(_QWORD *)a1;
  v18 = &v25;
  v25 = 0;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v8, L"PkgExtension\\Index", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
LABEL_12:
    v9 = v25;
    v25 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    goto LABEL_8;
  }
  v10 = *(_QWORD *)a1;
  v18 = &v24;
  v24 = 0;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v10, L"PkgExtension\\Index\\ExtensionAndName", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    v11 = 450;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"PkgExtension\\Index\\ExtensionAndName");
  if ( v3 < 0 )
  {
    v11 = 451;
    goto LABEL_16;
  }
  v13 = *(_QWORD *)a1;
  v18 = &v24;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v13, L"PkgExtension\\Index\\Name", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    v11 = 453;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"PkgExtension\\Index\\Name");
  if ( v3 < 0 )
  {
    v11 = 454;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"PkgExtension\\Index");
  if ( v3 < 0 )
  {
    v11 = 456;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v23,
         L"PkgExtension\\Data");
  if ( v3 < 0 )
  {
    v11 = 457;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v22,
         L"PkgExtension");
  if ( v3 < 0 )
  {
    v11 = 458;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    v12 = v24;
    v24 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_12;
  }
  v14 = v24;
  v24 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v25;
  v25 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  v16 = v23;
  v23 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v22;
  v22 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x18014f538  push    rbp
0x18014f53a  push    rbx
0x18014f53b  push    rsi
0x18014f53c  push    rdi
0x18014f53d  mov     rbp, rsp
0x18014f540  sub     rsp, 48h
0x18014f544  mov     rdi, rcx
0x18014f547  mov     [rbp+var_18], 1
0x18014f54b  mov     rcx, [rcx]
0x18014f54e  lea     rax, [rbp+arg_0]
0x18014f552  xor     esi, esi
0x18014f554  mov     [rbp+var_28], rax
0x18014f558  lea     r9, [rbp+var_20]
0x18014f55c  mov     [rbp+arg_0], rsi
0x18014f560  xor     r8d, r8d
0x18014f563  mov     [rbp+var_20], rsi
0x18014f567  lea     rdx, aPkgextension; "PkgExtension"
0x18014f56e  call    cs:__imp_SRCacheContext_Create
0x18014f574  lea     rcx, [rbp+var_28]
0x18014f578  mov     ebx, eax
0x18014f57a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014f57f  test    ebx, ebx
0x18014f581  jns     short loc_18014F5CD
0x18014f583  mov     rcx, [rbp+20h]; this
0x18014f587  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f58e  mov     r9d, ebx; char *
0x18014f591  mov     edx, 1C2h; void *
0x18014f596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f59b  mov     rcx, [rbp+20h]; this
0x18014f59f  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18014f5a6  mov     r9d, ebx; char *
0x18014f5a9  mov     edx, 1BAh; void *
0x18014f5ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f5b3  mov     rcx, [rbp+arg_0]
0x18014f5b7  mov     [rbp+arg_0], rsi
0x18014f5bb  test    rcx, rcx
0x18014f5be  jz      short loc_18014F5C6
0x18014f5c0  call    cs:__imp_SRCacheContext_Close
0x18014f5c6  mov     eax, ebx
0x18014f5c8  jmp     loc_18014F8A2
0x18014f5cd  mov     rcx, [rdi]
0x18014f5d0  lea     rax, [rbp+arg_8]
0x18014f5d4  lea     r9, [rbp+var_20]
0x18014f5d8  mov     [rbp+var_28], rax
0x18014f5dc  xor     r8d, r8d
0x18014f5df  mov     [rbp+arg_8], rsi
0x18014f5e3  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x18014f5ea  mov     [rbp+var_20], rsi
0x18014f5ee  mov     [rbp+var_18], 1
0x18014f5f2  call    cs:__imp_SRCacheContext_Create
0x18014f5f8  lea     rcx, [rbp+var_28]
0x18014f5fc  mov     ebx, eax
0x18014f5fe  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014f603  test    ebx, ebx
0x18014f605  jns     short loc_18014F653
0x18014f607  mov     rcx, [rbp+20h]; this
0x18014f60b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f612  mov     r9d, ebx; char *
0x18014f615  mov     edx, 1C2h; void *
0x18014f61a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f61f  mov     rcx, [rbp+20h]; this
0x18014f623  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18014f62a  mov     r9d, ebx; char *
0x18014f62d  mov     edx, 1BDh; void *
0x18014f632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f637  mov     rcx, [rbp+arg_8]
0x18014f63b  mov     [rbp+arg_8], rsi
0x18014f63f  test    rcx, rcx
0x18014f642  jz      loc_18014F5B3
0x18014f648  call    cs:__imp_SRCacheContext_Close
0x18014f64e  jmp     loc_18014F5B3
0x18014f653  mov     rcx, [rdi]
0x18014f656  lea     rax, [rbp+arg_18]
0x18014f65a  lea     r9, [rbp+var_20]
0x18014f65e  mov     [rbp+var_28], rax
0x18014f662  xor     r8d, r8d
0x18014f665  mov     [rbp+arg_18], rsi
0x18014f669  lea     rdx, aPkgextensionIn; "PkgExtension\\Index"
0x18014f670  mov     [rbp+var_20], rsi
0x18014f674  mov     [rbp+var_18], 1
0x18014f678  call    cs:__imp_SRCacheContext_Create
0x18014f67e  lea     rcx, [rbp+var_28]
0x18014f682  mov     ebx, eax
0x18014f684  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014f689  test    ebx, ebx
0x18014f68b  jns     short loc_18014F6D9
0x18014f68d  mov     rcx, [rbp+20h]; this
0x18014f691  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f698  mov     r9d, ebx; char *
0x18014f69b  mov     edx, 1C2h; void *
0x18014f6a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f6a5  mov     rcx, [rbp+20h]; this
0x18014f6a9  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18014f6b0  mov     r9d, ebx; char *
0x18014f6b3  mov     edx, 1C0h; void *
0x18014f6b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f6bd  mov     rcx, [rbp+arg_18]
0x18014f6c1  mov     [rbp+arg_18], rsi
0x18014f6c5  test    rcx, rcx
0x18014f6c8  jz      loc_18014F637
0x18014f6ce  call    cs:__imp_SRCacheContext_Close
0x18014f6d4  jmp     loc_18014F637
0x18014f6d9  mov     rcx, [rdi]
0x18014f6dc  lea     rax, [rbp+arg_10]
0x18014f6e0  lea     r9, [rbp+var_20]
0x18014f6e4  mov     [rbp+var_28], rax
0x18014f6e8  xor     r8d, r8d
0x18014f6eb  mov     [rbp+arg_10], rsi
0x18014f6ef  lea     rdx, aPkgextensionIn_1; "PkgExtension\\Index\\ExtensionAndName"
0x18014f6f6  mov     [rbp+var_20], rsi
0x18014f6fa  mov     [rbp+var_18], 1
0x18014f6fe  call    cs:__imp_SRCacheContext_Create
0x18014f704  lea     rcx, [rbp+var_28]
0x18014f708  mov     ebx, eax
0x18014f70a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014f70f  test    ebx, ebx
0x18014f711  jns     short loc_18014F75F
0x18014f713  mov     rcx, [rbp+20h]; this
0x18014f717  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f71e  mov     r9d, ebx; char *
0x18014f721  mov     edx, 1C2h; void *
0x18014f726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f72b  mov     edx, 1C2h; void *
0x18014f730  mov     rcx, [rbp+20h]; this
0x18014f734  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18014f73b  mov     r9d, ebx; char *
0x18014f73e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f743  mov     rcx, [rbp+arg_10]
0x18014f747  mov     [rbp+arg_10], rsi
0x18014f74b  test    rcx, rcx
0x18014f74e  jz      loc_18014F6BD
0x18014f754  call    cs:__imp_SRCacheContext_Close
0x18014f75a  jmp     loc_18014F6BD
0x18014f75f  lea     rdx, aPkgextensionIn_1; "PkgExtension\\Index\\ExtensionAndName"
0x18014f766  lea     rcx, [rbp+arg_10]; this
0x18014f76a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18014f76f  mov     ebx, eax
0x18014f771  test    eax, eax
0x18014f773  jns     short loc_18014F77C
0x18014f775  mov     edx, 1C3h
0x18014f77a  jmp     short loc_18014F730
0x18014f77c  mov     rcx, [rdi]
0x18014f77f  lea     rax, [rbp+arg_10]
0x18014f783  lea     r9, [rbp+var_20]
0x18014f787  mov     [rbp+var_28], rax
0x18014f78b  xor     r8d, r8d
0x18014f78e  mov     [rbp+var_20], rsi
0x18014f792  lea     rdx, aPkgextensionIn_0; "PkgExtension\\Index\\Name"
0x18014f799  mov     [rbp+var_18], 1
0x18014f79d  call    cs:__imp_SRCacheContext_Create
0x18014f7a3  lea     rcx, [rbp+var_28]
0x18014f7a7  mov     ebx, eax
0x18014f7a9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014f7ae  test    ebx, ebx
0x18014f7b0  jns     short loc_18014F7D4
0x18014f7b2  mov     rcx, [rbp+20h]; this
0x18014f7b6  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f7bd  mov     r9d, ebx; char *
0x18014f7c0  mov     edx, 1C2h; void *
0x18014f7c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f7ca  mov     edx, 1C5h
0x18014f7cf  jmp     loc_18014F730
0x18014f7d4  lea     rdx, aPkgextensionIn_0; "PkgExtension\\Index\\Name"
0x18014f7db  lea     rcx, [rbp+arg_10]; this
0x18014f7df  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18014f7e4  mov     ebx, eax
0x18014f7e6  test    eax, eax
0x18014f7e8  jns     short loc_18014F7F4
0x18014f7ea  mov     edx, 1C6h
0x18014f7ef  jmp     loc_18014F730
0x18014f7f4  lea     rdx, aPkgextensionIn; "PkgExtension\\Index"
0x18014f7fb  lea     rcx, [rbp+arg_18]; this
0x18014f7ff  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18014f804  mov     ebx, eax
0x18014f806  test    eax, eax
0x18014f808  jns     short loc_18014F814
0x18014f80a  mov     edx, 1C8h
0x18014f80f  jmp     loc_18014F730
0x18014f814  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x18014f81b  lea     rcx, [rbp+arg_8]; this
0x18014f81f  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18014f824  mov     ebx, eax
0x18014f826  test    eax, eax
0x18014f828  jns     short loc_18014F834
0x18014f82a  mov     edx, 1C9h
0x18014f82f  jmp     loc_18014F730
0x18014f834  lea     rdx, aPkgextension; "PkgExtension"
0x18014f83b  lea     rcx, [rbp+arg_0]; this
0x18014f83f  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18014f844  mov     ebx, eax
0x18014f846  test    eax, eax
0x18014f848  jns     short loc_18014F854
0x18014f84a  mov     edx, 1CAh
0x18014f84f  jmp     loc_18014F730
0x18014f854  mov     rcx, [rbp+arg_10]
0x18014f858  mov     [rbp+arg_10], rsi
0x18014f85c  test    rcx, rcx
0x18014f85f  jz      short loc_18014F867
0x18014f861  call    cs:__imp_SRCacheContext_Close
0x18014f867  mov     rcx, [rbp+arg_18]
0x18014f86b  mov     [rbp+arg_18], rsi
0x18014f86f  test    rcx, rcx
0x18014f872  jz      short loc_18014F87A
0x18014f874  call    cs:__imp_SRCacheContext_Close
0x18014f87a  mov     rcx, [rbp+arg_8]
0x18014f87e  mov     [rbp+arg_8], rsi
0x18014f882  test    rcx, rcx
0x18014f885  jz      short loc_18014F88D
0x18014f887  call    cs:__imp_SRCacheContext_Close
0x18014f88d  mov     rcx, [rbp+arg_0]
0x18014f891  mov     [rbp+arg_0], rsi
0x18014f895  test    rcx, rcx
0x18014f898  jz      short loc_18014F8A0
0x18014f89a  call    cs:__imp_SRCacheContext_Close
0x18014f8a0  xor     eax, eax
0x18014f8a2  add     rsp, 48h
0x18014f8a6  pop     rdi
0x18014f8a7  pop     rsi
0x18014f8a8  pop     rbx
0x18014f8a9  pop     rbp
0x18014f8aa  retn
```
