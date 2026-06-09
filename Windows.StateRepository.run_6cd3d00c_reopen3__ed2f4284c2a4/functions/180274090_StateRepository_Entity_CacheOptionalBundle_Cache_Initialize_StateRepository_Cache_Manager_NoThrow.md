# StateRepository::Entity::CacheOptionalBundle::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x180274090`
- end: `0x180274388`
- name: `?Cache_Initialize@CacheOptionalBundle@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `760`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180200320`
- `0x180273650`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x180274090`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274118`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802741a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802742ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027433e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274351`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274377`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274118`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802741a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274226`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802742ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027433e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274351`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180274377`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1802740c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18027414a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1802741d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180274256`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1802740c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18027414a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x1802741d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x180274256`

## string_xrefs

- `0x1802740df`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180274163`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1802741e9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18027426f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1802740f7`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x18027417b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x180274201`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x18027428c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheOptionalBundle::Cache_Initialize(
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
  __int64 *v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+28h] [rbp-20h] BYREF
  char v19; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v21; // [rsp+70h] [rbp+28h] BYREF
  __int64 v22; // [rsp+78h] [rbp+30h] BYREF
  __int64 v23; // [rsp+80h] [rbp+38h] BYREF
  __int64 v24; // [rsp+88h] [rbp+40h] BYREF

  v19 = 1;
  v2 = *(_QWORD *)a1;
  v17 = &v21;
  v21 = 0;
  v18 = 0;
  v3 = SRCacheContext_Create(v2, L"OptionalBundle", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
      (const char *)(unsigned int)v3,
      (int)v17);
LABEL_3:
    v4 = v21;
    v21 = 0;
    if ( v4 )
      SRCacheContext_Close(v4);
    return (unsigned int)v3;
  }
  v6 = *(_QWORD *)a1;
  v17 = &v22;
  v22 = 0;
  v18 = 0;
  v19 = 1;
  v3 = SRCacheContext_Create(v6, L"OptionalBundle\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
      (const char *)(unsigned int)v3,
      (int)v17);
LABEL_8:
    v7 = v22;
    v22 = 0;
    if ( v7 )
      SRCacheContext_Close(v7);
    goto LABEL_3;
  }
  v8 = *(_QWORD *)a1;
  v17 = &v23;
  v23 = 0;
  v18 = 0;
  v19 = 1;
  v3 = SRCacheContext_Create(v8, L"OptionalBundle\\Index", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
      (const char *)(unsigned int)v3,
      (int)v17);
LABEL_12:
    v9 = v23;
    v23 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    goto LABEL_8;
  }
  v10 = *(_QWORD *)a1;
  v17 = &v24;
  v24 = 0;
  v18 = 0;
  v19 = 1;
  v3 = SRCacheContext_Create(v10, L"OptionalBundle\\Index\\MainBundle", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v17);
    v11 = 136;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v24,
         L"OptionalBundle\\Index\\MainBundle");
  if ( v3 < 0 )
  {
    v11 = 137;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v23,
         L"OptionalBundle\\Index");
  if ( v3 < 0 )
  {
    v11 = 139;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v22,
         L"OptionalBundle\\Data");
  if ( v3 < 0 )
  {
    v11 = 140;
    goto LABEL_16;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v21,
         L"OptionalBundle");
  if ( v3 < 0 )
  {
    v11 = 141;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
      (const char *)(unsigned int)v3,
      (int)v17);
    v12 = v24;
    v24 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_12;
  }
  v13 = v24;
  v24 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  v14 = v23;
  v23 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v22;
  v22 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  v16 = v21;
  v21 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x180274090  push    rbp
0x180274092  push    rbx
0x180274093  push    rsi
0x180274094  push    rdi
0x180274095  mov     rbp, rsp
0x180274098  sub     rsp, 48h
0x18027409c  mov     rdi, rcx
0x18027409f  mov     [rbp+var_18], 1
0x1802740a3  mov     rcx, [rcx]
0x1802740a6  lea     rax, [rbp+arg_0]
0x1802740aa  xor     esi, esi
0x1802740ac  mov     [rbp+var_28], rax
0x1802740b0  lea     r9, [rbp+var_20]
0x1802740b4  mov     [rbp+arg_0], rsi
0x1802740b8  xor     r8d, r8d
0x1802740bb  mov     [rbp+var_20], rsi
0x1802740bf  lea     rdx, aOptionalbundle_4; "OptionalBundle"
0x1802740c6  call    cs:__imp_SRCacheContext_Create
0x1802740cc  lea     rcx, [rbp+var_28]
0x1802740d0  mov     ebx, eax
0x1802740d2  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802740d7  test    ebx, ebx
0x1802740d9  jns     short loc_180274125
0x1802740db  mov     rcx, [rbp+20h]; this
0x1802740df  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1802740e6  mov     r9d, ebx; char *
0x1802740e9  mov     edx, 1C2h; void *
0x1802740ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802740f3  mov     rcx, [rbp+20h]; this
0x1802740f7  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x1802740fe  mov     r9d, ebx; char *
0x180274101  mov     edx, 80h; void *
0x180274106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027410b  mov     rcx, [rbp+arg_0]
0x18027410f  mov     [rbp+arg_0], rsi
0x180274113  test    rcx, rcx
0x180274116  jz      short loc_18027411E
0x180274118  call    cs:__imp_SRCacheContext_Close
0x18027411e  mov     eax, ebx
0x180274120  jmp     loc_18027437F
0x180274125  mov     rcx, [rdi]
0x180274128  lea     rax, [rbp+arg_8]
0x18027412c  lea     r9, [rbp+var_20]
0x180274130  mov     [rbp+var_28], rax
0x180274134  xor     r8d, r8d
0x180274137  mov     [rbp+arg_8], rsi
0x18027413b  lea     rdx, aOptionalbundle_0; "OptionalBundle\\Data"
0x180274142  mov     [rbp+var_20], rsi
0x180274146  mov     [rbp+var_18], 1
0x18027414a  call    cs:__imp_SRCacheContext_Create
0x180274150  lea     rcx, [rbp+var_28]
0x180274154  mov     ebx, eax
0x180274156  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18027415b  test    ebx, ebx
0x18027415d  jns     short loc_1802741AB
0x18027415f  mov     rcx, [rbp+20h]; this
0x180274163  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18027416a  mov     r9d, ebx; char *
0x18027416d  mov     edx, 1C2h; void *
0x180274172  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274177  mov     rcx, [rbp+20h]; this
0x18027417b  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180274182  mov     r9d, ebx; char *
0x180274185  mov     edx, 83h; void *
0x18027418a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027418f  mov     rcx, [rbp+arg_8]
0x180274193  mov     [rbp+arg_8], rsi
0x180274197  test    rcx, rcx
0x18027419a  jz      loc_18027410B
0x1802741a0  call    cs:__imp_SRCacheContext_Close
0x1802741a6  jmp     loc_18027410B
0x1802741ab  mov     rcx, [rdi]
0x1802741ae  lea     rax, [rbp+arg_10]
0x1802741b2  lea     r9, [rbp+var_20]
0x1802741b6  mov     [rbp+var_28], rax
0x1802741ba  xor     r8d, r8d
0x1802741bd  mov     [rbp+arg_10], rsi
0x1802741c1  lea     rdx, aOptionalbundle_18; "OptionalBundle\\Index"
0x1802741c8  mov     [rbp+var_20], rsi
0x1802741cc  mov     [rbp+var_18], 1
0x1802741d0  call    cs:__imp_SRCacheContext_Create
0x1802741d6  lea     rcx, [rbp+var_28]
0x1802741da  mov     ebx, eax
0x1802741dc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802741e1  test    ebx, ebx
0x1802741e3  jns     short loc_180274231
0x1802741e5  mov     rcx, [rbp+20h]; this
0x1802741e9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1802741f0  mov     r9d, ebx; char *
0x1802741f3  mov     edx, 1C2h; void *
0x1802741f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802741fd  mov     rcx, [rbp+20h]; this
0x180274201  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180274208  mov     r9d, ebx; char *
0x18027420b  mov     edx, 86h; void *
0x180274210  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274215  mov     rcx, [rbp+arg_10]
0x180274219  mov     [rbp+arg_10], rsi
0x18027421d  test    rcx, rcx
0x180274220  jz      loc_18027418F
0x180274226  call    cs:__imp_SRCacheContext_Close
0x18027422c  jmp     loc_18027418F
0x180274231  mov     rcx, [rdi]
0x180274234  lea     rax, [rbp+arg_18]
0x180274238  lea     r9, [rbp+var_20]
0x18027423c  mov     [rbp+var_28], rax
0x180274240  xor     r8d, r8d
0x180274243  mov     [rbp+arg_18], rsi
0x180274247  lea     rdx, aOptionalbundle_22; "OptionalBundle\\Index\\MainBundle"
0x18027424e  mov     [rbp+var_20], rsi
0x180274252  mov     [rbp+var_18], 1
0x180274256  call    cs:__imp_SRCacheContext_Create
0x18027425c  lea     rcx, [rbp+var_28]
0x180274260  mov     ebx, eax
0x180274262  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180274267  test    ebx, ebx
0x180274269  jns     short loc_1802742B7
0x18027426b  mov     rcx, [rbp+20h]; this
0x18027426f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180274276  mov     r9d, ebx; char *
0x180274279  mov     edx, 1C2h; void *
0x18027427e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274283  mov     edx, 88h; void *
0x180274288  mov     rcx, [rbp+20h]; this
0x18027428c  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180274293  mov     r9d, ebx; char *
0x180274296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027429b  mov     rcx, [rbp+arg_18]
0x18027429f  mov     [rbp+arg_18], rsi
0x1802742a3  test    rcx, rcx
0x1802742a6  jz      loc_180274215
0x1802742ac  call    cs:__imp_SRCacheContext_Close
0x1802742b2  jmp     loc_180274215
0x1802742b7  lea     rdx, aOptionalbundle_22; "OptionalBundle\\Index\\MainBundle"
0x1802742be  lea     rcx, [rbp+arg_18]; this
0x1802742c2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1802742c7  mov     ebx, eax
0x1802742c9  test    eax, eax
0x1802742cb  jns     short loc_1802742D4
0x1802742cd  mov     edx, 89h
0x1802742d2  jmp     short loc_180274288
0x1802742d4  lea     rdx, aOptionalbundle_18; "OptionalBundle\\Index"
0x1802742db  lea     rcx, [rbp+arg_10]; this
0x1802742df  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1802742e4  mov     ebx, eax
0x1802742e6  test    eax, eax
0x1802742e8  jns     short loc_1802742F1
0x1802742ea  mov     edx, 8Bh
0x1802742ef  jmp     short loc_180274288
0x1802742f1  lea     rdx, aOptionalbundle_0; "OptionalBundle\\Data"
0x1802742f8  lea     rcx, [rbp+arg_8]; this
0x1802742fc  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180274301  mov     ebx, eax
0x180274303  test    eax, eax
0x180274305  jns     short loc_180274311
0x180274307  mov     edx, 8Ch
0x18027430c  jmp     loc_180274288
0x180274311  lea     rdx, aOptionalbundle_4; "OptionalBundle"
0x180274318  lea     rcx, [rbp+arg_0]; this
0x18027431c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180274321  mov     ebx, eax
0x180274323  test    eax, eax
0x180274325  jns     short loc_180274331
0x180274327  mov     edx, 8Dh
0x18027432c  jmp     loc_180274288
0x180274331  mov     rcx, [rbp+arg_18]
0x180274335  mov     [rbp+arg_18], rsi
0x180274339  test    rcx, rcx
0x18027433c  jz      short loc_180274344
0x18027433e  call    cs:__imp_SRCacheContext_Close
0x180274344  mov     rcx, [rbp+arg_10]
0x180274348  mov     [rbp+arg_10], rsi
0x18027434c  test    rcx, rcx
0x18027434f  jz      short loc_180274357
0x180274351  call    cs:__imp_SRCacheContext_Close
0x180274357  mov     rcx, [rbp+arg_8]
0x18027435b  mov     [rbp+arg_8], rsi
0x18027435f  test    rcx, rcx
0x180274362  jz      short loc_18027436A
0x180274364  call    cs:__imp_SRCacheContext_Close
0x18027436a  mov     rcx, [rbp+arg_0]
0x18027436e  mov     [rbp+arg_0], rsi
0x180274372  test    rcx, rcx
0x180274375  jz      short loc_18027437D
0x180274377  call    cs:__imp_SRCacheContext_Close
0x18027437d  xor     eax, eax
0x18027437f  add     rsp, 48h
0x180274383  pop     rdi
0x180274384  pop     rsi
0x180274385  pop     rbx
0x180274386  pop     rbp
0x180274387  retn
```
