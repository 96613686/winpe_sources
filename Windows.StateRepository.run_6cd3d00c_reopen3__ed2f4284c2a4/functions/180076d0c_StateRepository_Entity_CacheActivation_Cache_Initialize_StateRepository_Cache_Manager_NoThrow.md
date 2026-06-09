# StateRepository::Entity::CacheActivation::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x180076d0c`
- end: `0x18007701a`
- name: `?Cache_Initialize@CacheActivation@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `782`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18004b060`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x180076d0c`
- `0x18007b950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076d63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076daa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076e32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076eb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076f3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076fd0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076fe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076ff6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180077009`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076d63`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076daa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076e32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076eb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076f3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076fd0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076fe3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180076ff6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180077009`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076d42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076ddc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076e62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076ee8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076d42`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076ddc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076e62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180076ee8`

## string_xrefs

- `0x180076d89`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180076e0d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180076e93`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180076f1e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180076d71`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180076df5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180076e7b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180076f01`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheActivation::Cache_Initialize(
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
  v3 = SRCacheContext_Create(v2, L"Activation", 0, &v19);
  if ( v20 )
  {
    v4 = *v18;
    *v18 = v19;
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
      (int)v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
LABEL_6:
    v5 = v22;
    v22 = 0;
    if ( v5 )
      SRCacheContext_Close(v5);
    return (unsigned int)v3;
  }
  v7 = *(_QWORD *)a1;
  v18 = &v23;
  v23 = 0;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v7, L"Activation\\Data", 0, &v19);
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
      (void *)0x1C1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
LABEL_11:
    v8 = v23;
    v23 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    goto LABEL_6;
  }
  v9 = *(_QWORD *)a1;
  v18 = &v24;
  v24 = 0;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v9, L"Activation\\Index", 0, &v19);
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
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
LABEL_15:
    v10 = v24;
    v24 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    goto LABEL_11;
  }
  v11 = *(_QWORD *)a1;
  v18 = &v25;
  v25 = 0;
  v19 = 0;
  v20 = 1;
  v3 = SRCacheContext_Create(v11, L"Activation\\Index\\ActivationKey", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    v12 = 454;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v25,
         L"Activation\\Index\\ActivationKey");
  if ( v3 < 0 )
  {
    v12 = 455;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"Activation\\Index");
  if ( v3 < 0 )
  {
    v12 = 457;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v23,
         L"Activation\\Data");
  if ( v3 < 0 )
  {
    v12 = 458;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v22,
         L"Activation");
  if ( v3 < 0 )
  {
    v12 = 459;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)(unsigned int)v3,
      (int)v18);
    v13 = v25;
    v25 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_15;
  }
  v14 = v25;
  v25 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v24;
  v24 = 0;
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
0x180076d0c  push    rbp
0x180076d0e  push    rbx
0x180076d0f  push    rsi
0x180076d10  push    rdi
0x180076d11  mov     rbp, rsp
0x180076d14  sub     rsp, 48h
0x180076d18  mov     rdi, rcx
0x180076d1b  mov     [rbp+var_18], 1
0x180076d1f  mov     rcx, [rcx]
0x180076d22  lea     rax, [rbp+arg_0]
0x180076d26  xor     esi, esi
0x180076d28  mov     [rbp+var_28], rax
0x180076d2c  lea     r9, [rbp+var_20]
0x180076d30  mov     [rbp+arg_0], rsi
0x180076d34  xor     r8d, r8d
0x180076d37  mov     [rbp+var_20], rsi
0x180076d3b  lea     rdx, aActivation_0; "Activation"
0x180076d42  call    cs:__imp_SRCacheContext_Create
0x180076d48  mov     ebx, eax
0x180076d4a  cmp     [rbp+var_18], sil
0x180076d4e  jz      short loc_180076D69
0x180076d50  mov     r8, [rbp+var_28]
0x180076d54  mov     rdx, [rbp+var_20]
0x180076d58  mov     rcx, [r8]
0x180076d5b  mov     [r8], rdx
0x180076d5e  test    rcx, rcx
0x180076d61  jz      short loc_180076D69
0x180076d63  call    cs:__imp_SRCacheContext_Close
0x180076d69  test    ebx, ebx
0x180076d6b  jns     short loc_180076DB7
0x180076d6d  mov     rcx, [rbp+20h]; this
0x180076d71  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180076d78  mov     r9d, ebx; char *
0x180076d7b  mov     edx, 1C2h; void *
0x180076d80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076d85  mov     rcx, [rbp+20h]; this
0x180076d89  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180076d90  mov     r9d, ebx; char *
0x180076d93  mov     edx, 1BEh; void *
0x180076d98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076d9d  mov     rcx, [rbp+arg_0]
0x180076da1  mov     [rbp+arg_0], rsi
0x180076da5  test    rcx, rcx
0x180076da8  jz      short loc_180076DB0
0x180076daa  call    cs:__imp_SRCacheContext_Close
0x180076db0  mov     eax, ebx
0x180076db2  jmp     loc_180077011
0x180076db7  mov     rcx, [rdi]
0x180076dba  lea     rax, [rbp+arg_8]
0x180076dbe  lea     r9, [rbp+var_20]
0x180076dc2  mov     [rbp+var_28], rax
0x180076dc6  xor     r8d, r8d
0x180076dc9  mov     [rbp+arg_8], rsi
0x180076dcd  lea     rdx, aActivationData; "Activation\\Data"
0x180076dd4  mov     [rbp+var_20], rsi
0x180076dd8  mov     [rbp+var_18], 1
0x180076ddc  call    cs:__imp_SRCacheContext_Create
0x180076de2  lea     rcx, [rbp+var_28]
0x180076de6  mov     ebx, eax
0x180076de8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180076ded  test    ebx, ebx
0x180076def  jns     short loc_180076E3D
0x180076df1  mov     rcx, [rbp+20h]; this
0x180076df5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180076dfc  mov     r9d, ebx; char *
0x180076dff  mov     edx, 1C2h; void *
0x180076e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076e09  mov     rcx, [rbp+20h]; this
0x180076e0d  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180076e14  mov     r9d, ebx; char *
0x180076e17  mov     edx, 1C1h; void *
0x180076e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076e21  mov     rcx, [rbp+arg_8]
0x180076e25  mov     [rbp+arg_8], rsi
0x180076e29  test    rcx, rcx
0x180076e2c  jz      loc_180076D9D
0x180076e32  call    cs:__imp_SRCacheContext_Close
0x180076e38  jmp     loc_180076D9D
0x180076e3d  mov     rcx, [rdi]
0x180076e40  lea     rax, [rbp+arg_10]
0x180076e44  lea     r9, [rbp+var_20]
0x180076e48  mov     [rbp+var_28], rax
0x180076e4c  xor     r8d, r8d
0x180076e4f  mov     [rbp+arg_10], rsi
0x180076e53  lea     rdx, aActivationInde_0; "Activation\\Index"
0x180076e5a  mov     [rbp+var_20], rsi
0x180076e5e  mov     [rbp+var_18], 1
0x180076e62  call    cs:__imp_SRCacheContext_Create
0x180076e68  lea     rcx, [rbp+var_28]
0x180076e6c  mov     ebx, eax
0x180076e6e  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180076e73  test    ebx, ebx
0x180076e75  jns     short loc_180076EC3
0x180076e77  mov     rcx, [rbp+20h]; this
0x180076e7b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180076e82  mov     r9d, ebx; char *
0x180076e85  mov     edx, 1C2h; void *
0x180076e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076e8f  mov     rcx, [rbp+20h]; this
0x180076e93  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180076e9a  mov     r9d, ebx; char *
0x180076e9d  mov     edx, 1C4h; void *
0x180076ea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076ea7  mov     rcx, [rbp+arg_10]
0x180076eab  mov     [rbp+arg_10], rsi
0x180076eaf  test    rcx, rcx
0x180076eb2  jz      loc_180076E21
0x180076eb8  call    cs:__imp_SRCacheContext_Close
0x180076ebe  jmp     loc_180076E21
0x180076ec3  mov     rcx, [rdi]
0x180076ec6  lea     rax, [rbp+arg_18]
0x180076eca  lea     r9, [rbp+var_20]
0x180076ece  mov     [rbp+var_28], rax
0x180076ed2  xor     r8d, r8d
0x180076ed5  mov     [rbp+arg_18], rsi
0x180076ed9  lea     rdx, aActivationInde; "Activation\\Index\\ActivationKey"
0x180076ee0  mov     [rbp+var_20], rsi
0x180076ee4  mov     [rbp+var_18], 1
0x180076ee8  call    cs:__imp_SRCacheContext_Create
0x180076eee  lea     rcx, [rbp+var_28]
0x180076ef2  mov     ebx, eax
0x180076ef4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180076ef9  test    ebx, ebx
0x180076efb  jns     short loc_180076F49
0x180076efd  mov     rcx, [rbp+20h]; this
0x180076f01  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180076f08  mov     r9d, ebx; char *
0x180076f0b  mov     edx, 1C2h; void *
0x180076f10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076f15  mov     edx, 1C6h; void *
0x180076f1a  mov     rcx, [rbp+20h]; this
0x180076f1e  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180076f25  mov     r9d, ebx; char *
0x180076f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076f2d  mov     rcx, [rbp+arg_18]
0x180076f31  mov     [rbp+arg_18], rsi
0x180076f35  test    rcx, rcx
0x180076f38  jz      loc_180076EA7
0x180076f3e  call    cs:__imp_SRCacheContext_Close
0x180076f44  jmp     loc_180076EA7
0x180076f49  lea     rdx, aActivationInde; "Activation\\Index\\ActivationKey"
0x180076f50  lea     rcx, [rbp+arg_18]; this
0x180076f54  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180076f59  mov     ebx, eax
0x180076f5b  test    eax, eax
0x180076f5d  jns     short loc_180076F66
0x180076f5f  mov     edx, 1C7h
0x180076f64  jmp     short loc_180076F1A
0x180076f66  lea     rdx, aActivationInde_0; "Activation\\Index"
0x180076f6d  lea     rcx, [rbp+arg_10]; this
0x180076f71  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180076f76  mov     ebx, eax
0x180076f78  test    eax, eax
0x180076f7a  jns     short loc_180076F83
0x180076f7c  mov     edx, 1C9h
0x180076f81  jmp     short loc_180076F1A
0x180076f83  lea     rdx, aActivationData; "Activation\\Data"
0x180076f8a  lea     rcx, [rbp+arg_8]; this
0x180076f8e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180076f93  mov     ebx, eax
0x180076f95  test    eax, eax
0x180076f97  jns     short loc_180076FA3
0x180076f99  mov     edx, 1CAh
0x180076f9e  jmp     loc_180076F1A
0x180076fa3  lea     rdx, aActivation_0; "Activation"
0x180076faa  lea     rcx, [rbp+arg_0]; this
0x180076fae  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180076fb3  mov     ebx, eax
0x180076fb5  test    eax, eax
0x180076fb7  jns     short loc_180076FC3
0x180076fb9  mov     edx, 1CBh
0x180076fbe  jmp     loc_180076F1A
0x180076fc3  mov     rcx, [rbp+arg_18]
0x180076fc7  mov     [rbp+arg_18], rsi
0x180076fcb  test    rcx, rcx
0x180076fce  jz      short loc_180076FD6
0x180076fd0  call    cs:__imp_SRCacheContext_Close
0x180076fd6  mov     rcx, [rbp+arg_10]
0x180076fda  mov     [rbp+arg_10], rsi
0x180076fde  test    rcx, rcx
0x180076fe1  jz      short loc_180076FE9
0x180076fe3  call    cs:__imp_SRCacheContext_Close
0x180076fe9  mov     rcx, [rbp+arg_8]
0x180076fed  mov     [rbp+arg_8], rsi
0x180076ff1  test    rcx, rcx
0x180076ff4  jz      short loc_180076FFC
0x180076ff6  call    cs:__imp_SRCacheContext_Close
0x180076ffc  mov     rcx, [rbp+arg_0]
0x180077000  mov     [rbp+arg_0], rsi
0x180077004  test    rcx, rcx
0x180077007  jz      short loc_18007700F
0x180077009  call    cs:__imp_SRCacheContext_Close
0x18007700f  xor     eax, eax
0x180077011  add     rsp, 48h
0x180077015  pop     rdi
0x180077016  pop     rsi
0x180077017  pop     rbx
0x180077018  pop     rbp
0x180077019  retn
```
