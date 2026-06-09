# StateRepository::Entity::CacheUser::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x18009a244`
- end: `0x18009a552`
- name: `?Cache_Initialize@CacheUser@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `782`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180099680`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x180074eb0`
- `0x18007b950`
- `0x18009a244`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a29b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a2e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a36a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a3f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a476`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a508`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a51b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a52e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a541`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a29b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a2e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a36a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a3f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a476`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a508`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a51b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a52e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009a541`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a27a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a314`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a39a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a420`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a27a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a314`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a39a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18009a420`

## string_xrefs

- `0x18009a2a9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18009a32d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18009a3b3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18009a439`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18009a2c1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x18009a345`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x18009a3cb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x18009a456`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x18009a411`: `User\Index\UserSid`
- `0x18009a481`: `User\Index\UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheUser::Cache_Initialize(
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
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 *v24; // [rsp+20h] [rbp-28h] BYREF
  __int64 v25; // [rsp+28h] [rbp-20h] BYREF
  char v26; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v28; // [rsp+70h] [rbp+28h] BYREF
  __int64 v29; // [rsp+78h] [rbp+30h] BYREF
  __int64 v30; // [rsp+80h] [rbp+38h] BYREF
  __int64 v31; // [rsp+88h] [rbp+40h] BYREF

  v26 = 1;
  v2 = *(_QWORD *)a1;
  v24 = &v28;
  v28 = 0;
  v25 = 0;
  v3 = SRCacheContext_Create(v2, L"User", 0, &v25);
  if ( v26 )
  {
    v4 = v24;
    v5 = v25;
    v6 = *v24;
    *v24 = v25;
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
      (int)v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)v3,
      (int)v24);
LABEL_6:
    v9 = v28;
    v28 = 0;
    if ( v9 )
      SRCacheContext_Close(v9, v7, v8);
    return (unsigned int)v3;
  }
  v11 = *(_QWORD *)a1;
  v24 = &v29;
  v29 = 0;
  v25 = 0;
  v26 = 1;
  v3 = SRCacheContext_Create(v11, L"User\\Data", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)v3,
      (int)v24);
LABEL_11:
    v12 = v29;
    v29 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v7, v8);
    goto LABEL_6;
  }
  v13 = *(_QWORD *)a1;
  v24 = &v30;
  v30 = 0;
  v25 = 0;
  v26 = 1;
  v3 = SRCacheContext_Create(v13, L"User\\Index", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)v3,
      (int)v24);
LABEL_15:
    v14 = v30;
    v30 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v7, v8);
    goto LABEL_11;
  }
  v15 = *(_QWORD *)a1;
  v24 = &v31;
  v31 = 0;
  v25 = 0;
  v26 = 1;
  v3 = SRCacheContext_Create(v15, L"User\\Index\\UserSid", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v24);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)v24);
    v16 = 220;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v31,
         L"User\\Index\\UserSid");
  if ( v3 < 0 )
  {
    v16 = 221;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v30,
         L"User\\Index");
  if ( v3 < 0 )
  {
    v16 = 223;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v29,
         L"User\\Data");
  if ( v3 < 0 )
  {
    v16 = 224;
    goto LABEL_19;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache((StateRepository::Cache::Context_NoThrow *)&v28, L"User");
  if ( v3 < 0 )
  {
    v16 = 225;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
      (const char *)(unsigned int)v3,
      (int)v24);
    v17 = v31;
    v31 = 0;
    if ( v17 )
      SRCacheContext_Close(v17, v7, v8);
    goto LABEL_15;
  }
  v20 = v31;
  v31 = 0;
  if ( v20 )
    SRCacheContext_Close(v20, v18, v19);
  v21 = v30;
  v30 = 0;
  if ( v21 )
    SRCacheContext_Close(v21, v18, v19);
  v22 = v29;
  v29 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v18, v19);
  v23 = v28;
  v28 = 0;
  if ( v23 )
    SRCacheContext_Close(v23, v18, v19);
  return 0;
}

```

## disassembly

```asm
0x18009a244  push    rbp
0x18009a246  push    rbx
0x18009a247  push    rsi
0x18009a248  push    rdi
0x18009a249  mov     rbp, rsp
0x18009a24c  sub     rsp, 48h
0x18009a250  mov     rdi, rcx
0x18009a253  mov     [rbp+var_18], 1
0x18009a257  mov     rcx, [rcx]
0x18009a25a  lea     rax, [rbp+arg_0]
0x18009a25e  xor     esi, esi
0x18009a260  mov     [rbp+var_28], rax
0x18009a264  lea     r9, [rbp+var_20]
0x18009a268  mov     [rbp+arg_0], rsi
0x18009a26c  xor     r8d, r8d
0x18009a26f  mov     [rbp+var_20], rsi
0x18009a273  lea     rdx, aUser_0; "User"
0x18009a27a  call    cs:__imp_SRCacheContext_Create
0x18009a280  mov     ebx, eax
0x18009a282  cmp     [rbp+var_18], sil
0x18009a286  jz      short loc_18009A2A1
0x18009a288  mov     r8, [rbp+var_28]
0x18009a28c  mov     rdx, [rbp+var_20]
0x18009a290  mov     rcx, [r8]
0x18009a293  mov     [r8], rdx
0x18009a296  test    rcx, rcx
0x18009a299  jz      short loc_18009A2A1
0x18009a29b  call    cs:__imp_SRCacheContext_Close
0x18009a2a1  test    ebx, ebx
0x18009a2a3  jns     short loc_18009A2EF
0x18009a2a5  mov     rcx, [rbp+20h]; this
0x18009a2a9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009a2b0  mov     r9d, ebx; char *
0x18009a2b3  mov     edx, 1C2h; void *
0x18009a2b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a2bd  mov     rcx, [rbp+20h]; this
0x18009a2c1  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x18009a2c8  mov     r9d, ebx; char *
0x18009a2cb  mov     edx, 0D4h; void *
0x18009a2d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a2d5  mov     rcx, [rbp+arg_0]
0x18009a2d9  mov     [rbp+arg_0], rsi
0x18009a2dd  test    rcx, rcx
0x18009a2e0  jz      short loc_18009A2E8
0x18009a2e2  call    cs:__imp_SRCacheContext_Close
0x18009a2e8  mov     eax, ebx
0x18009a2ea  jmp     loc_18009A549
0x18009a2ef  mov     rcx, [rdi]
0x18009a2f2  lea     rax, [rbp+arg_8]
0x18009a2f6  lea     r9, [rbp+var_20]
0x18009a2fa  mov     [rbp+var_28], rax
0x18009a2fe  xor     r8d, r8d
0x18009a301  mov     [rbp+arg_8], rsi
0x18009a305  lea     rdx, aUserData; "User\\Data"
0x18009a30c  mov     [rbp+var_20], rsi
0x18009a310  mov     [rbp+var_18], 1
0x18009a314  call    cs:__imp_SRCacheContext_Create
0x18009a31a  lea     rcx, [rbp+var_28]
0x18009a31e  mov     ebx, eax
0x18009a320  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18009a325  test    ebx, ebx
0x18009a327  jns     short loc_18009A375
0x18009a329  mov     rcx, [rbp+20h]; this
0x18009a32d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009a334  mov     r9d, ebx; char *
0x18009a337  mov     edx, 1C2h; void *
0x18009a33c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a341  mov     rcx, [rbp+20h]; this
0x18009a345  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x18009a34c  mov     r9d, ebx; char *
0x18009a34f  mov     edx, 0D7h; void *
0x18009a354  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a359  mov     rcx, [rbp+arg_8]
0x18009a35d  mov     [rbp+arg_8], rsi
0x18009a361  test    rcx, rcx
0x18009a364  jz      loc_18009A2D5
0x18009a36a  call    cs:__imp_SRCacheContext_Close
0x18009a370  jmp     loc_18009A2D5
0x18009a375  mov     rcx, [rdi]
0x18009a378  lea     rax, [rbp+arg_10]
0x18009a37c  lea     r9, [rbp+var_20]
0x18009a380  mov     [rbp+var_28], rax
0x18009a384  xor     r8d, r8d
0x18009a387  mov     [rbp+arg_10], rsi
0x18009a38b  lea     rdx, aUserIndex; "User\\Index"
0x18009a392  mov     [rbp+var_20], rsi
0x18009a396  mov     [rbp+var_18], 1
0x18009a39a  call    cs:__imp_SRCacheContext_Create
0x18009a3a0  lea     rcx, [rbp+var_28]
0x18009a3a4  mov     ebx, eax
0x18009a3a6  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18009a3ab  test    ebx, ebx
0x18009a3ad  jns     short loc_18009A3FB
0x18009a3af  mov     rcx, [rbp+20h]; this
0x18009a3b3  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009a3ba  mov     r9d, ebx; char *
0x18009a3bd  mov     edx, 1C2h; void *
0x18009a3c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a3c7  mov     rcx, [rbp+20h]; this
0x18009a3cb  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x18009a3d2  mov     r9d, ebx; char *
0x18009a3d5  mov     edx, 0DAh; void *
0x18009a3da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a3df  mov     rcx, [rbp+arg_10]
0x18009a3e3  mov     [rbp+arg_10], rsi
0x18009a3e7  test    rcx, rcx
0x18009a3ea  jz      loc_18009A359
0x18009a3f0  call    cs:__imp_SRCacheContext_Close
0x18009a3f6  jmp     loc_18009A359
0x18009a3fb  mov     rcx, [rdi]
0x18009a3fe  lea     rax, [rbp+arg_18]
0x18009a402  lea     r9, [rbp+var_20]
0x18009a406  mov     [rbp+var_28], rax
0x18009a40a  xor     r8d, r8d
0x18009a40d  mov     [rbp+arg_18], rsi
0x18009a411  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18009a418  mov     [rbp+var_20], rsi
0x18009a41c  mov     [rbp+var_18], 1
0x18009a420  call    cs:__imp_SRCacheContext_Create
0x18009a426  lea     rcx, [rbp+var_28]
0x18009a42a  mov     ebx, eax
0x18009a42c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18009a431  test    ebx, ebx
0x18009a433  jns     short loc_18009A481
0x18009a435  mov     rcx, [rbp+20h]; this
0x18009a439  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18009a440  mov     r9d, ebx; char *
0x18009a443  mov     edx, 1C2h; void *
0x18009a448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a44d  mov     edx, 0DCh; void *
0x18009a452  mov     rcx, [rbp+20h]; this
0x18009a456  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x18009a45d  mov     r9d, ebx; char *
0x18009a460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a465  mov     rcx, [rbp+arg_18]
0x18009a469  mov     [rbp+arg_18], rsi
0x18009a46d  test    rcx, rcx
0x18009a470  jz      loc_18009A3DF
0x18009a476  call    cs:__imp_SRCacheContext_Close
0x18009a47c  jmp     loc_18009A3DF
0x18009a481  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18009a488  lea     rcx, [rbp+arg_18]; this
0x18009a48c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18009a491  mov     ebx, eax
0x18009a493  test    eax, eax
0x18009a495  jns     short loc_18009A49E
0x18009a497  mov     edx, 0DDh
0x18009a49c  jmp     short loc_18009A452
0x18009a49e  lea     rdx, aUserIndex; "User\\Index"
0x18009a4a5  lea     rcx, [rbp+arg_10]; this
0x18009a4a9  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18009a4ae  mov     ebx, eax
0x18009a4b0  test    eax, eax
0x18009a4b2  jns     short loc_18009A4BB
0x18009a4b4  mov     edx, 0DFh
0x18009a4b9  jmp     short loc_18009A452
0x18009a4bb  lea     rdx, aUserData; "User\\Data"
0x18009a4c2  lea     rcx, [rbp+arg_8]; this
0x18009a4c6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18009a4cb  mov     ebx, eax
0x18009a4cd  test    eax, eax
0x18009a4cf  jns     short loc_18009A4DB
0x18009a4d1  mov     edx, 0E0h
0x18009a4d6  jmp     loc_18009A452
0x18009a4db  lea     rdx, aUser_0; "User"
0x18009a4e2  lea     rcx, [rbp+arg_0]; this
0x18009a4e6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18009a4eb  mov     ebx, eax
0x18009a4ed  test    eax, eax
0x18009a4ef  jns     short loc_18009A4FB
0x18009a4f1  mov     edx, 0E1h
0x18009a4f6  jmp     loc_18009A452
0x18009a4fb  mov     rcx, [rbp+arg_18]
0x18009a4ff  mov     [rbp+arg_18], rsi
0x18009a503  test    rcx, rcx
0x18009a506  jz      short loc_18009A50E
0x18009a508  call    cs:__imp_SRCacheContext_Close
0x18009a50e  mov     rcx, [rbp+arg_10]
0x18009a512  mov     [rbp+arg_10], rsi
0x18009a516  test    rcx, rcx
0x18009a519  jz      short loc_18009A521
0x18009a51b  call    cs:__imp_SRCacheContext_Close
0x18009a521  mov     rcx, [rbp+arg_8]
0x18009a525  mov     [rbp+arg_8], rsi
0x18009a529  test    rcx, rcx
0x18009a52c  jz      short loc_18009A534
0x18009a52e  call    cs:__imp_SRCacheContext_Close
0x18009a534  mov     rcx, [rbp+arg_0]
0x18009a538  mov     [rbp+arg_0], rsi
0x18009a53c  test    rcx, rcx
0x18009a53f  jz      short loc_18009A547
0x18009a541  call    cs:__imp_SRCacheContext_Close
0x18009a547  xor     eax, eax
0x18009a549  add     rsp, 48h
0x18009a54d  pop     rdi
0x18009a54e  pop     rsi
0x18009a54f  pop     rbx
0x18009a550  pop     rbp
0x18009a551  retn
```
