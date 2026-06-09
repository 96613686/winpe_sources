# StateRepository::Entity::CacheDependencyGraph::Cache_Initialize(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x18004dd70`
- end: `0x18004e0c0`
- name: `?Cache_Initialize@CacheDependencyGraph@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@@Z`
- size: `848`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18004db00`
- `0x180200320`

## callees

- `0x18001a9e0`
- `0x18004dd70`
- `0x18007b950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ddc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004de0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004de61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004deac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004defd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004dfe4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e076`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e089`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e09c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e0af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ddc7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004de0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004de61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004deac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004defd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004df99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004dfe4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e076`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e089`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e09c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004e0af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004dda6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004de40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004dedc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004df78`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004dda6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004de40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004dedc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Create` at `0x18004df78`

## string_xrefs

- `0x18004ddd5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004de6f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004df0b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004dfa7`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004dded`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x18004de87`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x18004df23`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x18004dfc4`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheDependencyGraph::Cache_Initialize(
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
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // [rsp+20h] [rbp-28h]
  int v22; // [rsp+20h] [rbp-28h]
  int v23; // [rsp+20h] [rbp-28h]
  __int64 *v24; // [rsp+20h] [rbp-28h]
  __int64 v25; // [rsp+28h] [rbp-20h] BYREF
  char v26; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v28; // [rsp+70h] [rbp+28h] BYREF
  __int64 v29; // [rsp+78h] [rbp+30h] BYREF
  __int64 v30; // [rsp+80h] [rbp+38h] BYREF
  __int64 v31; // [rsp+88h] [rbp+40h] BYREF

  v26 = 1;
  v2 = *(_QWORD *)a1;
  v28 = 0;
  v25 = 0;
  v3 = SRCacheContext_Create(v2, L"DependencyGraph", 0, &v25);
  if ( v26 )
  {
    v4 = v28;
    v28 = v25;
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
      (int)&v28);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)(unsigned int)v3,
      v21);
LABEL_6:
    v5 = v28;
    v28 = 0;
    if ( v5 )
      SRCacheContext_Close(v5);
    return (unsigned int)v3;
  }
  v7 = *(_QWORD *)a1;
  v29 = 0;
  v25 = 0;
  v26 = 1;
  v3 = SRCacheContext_Create(v7, L"DependencyGraph\\Data", 0, &v25);
  if ( v26 )
  {
    v8 = v29;
    v29 = v25;
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
      (int)&v29);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)(unsigned int)v3,
      v22);
LABEL_14:
    v9 = v29;
    v29 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    goto LABEL_6;
  }
  v10 = *(_QWORD *)a1;
  v30 = 0;
  v25 = 0;
  v26 = 1;
  v3 = SRCacheContext_Create(v10, L"DependencyGraph\\Index", 0, &v25);
  if ( v26 )
  {
    v11 = v30;
    v30 = v25;
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
      (int)&v30);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)(unsigned int)v3,
      v23);
LABEL_21:
    v12 = v30;
    v30 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_14;
  }
  v13 = *(_QWORD *)a1;
  v24 = &v31;
  v31 = 0;
  v25 = 0;
  v26 = 1;
  v3 = SRCacheContext_Create(v13, L"DependencyGraph\\Index\\UserAndDependentPackageAndDependencyType", 0, &v25);
  if ( v26 )
  {
    v14 = v31;
    v31 = v25;
    if ( v14 )
      SRCacheContext_Close(v14);
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v3,
      (int)&v31);
    v15 = 189;
    goto LABEL_28;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v31,
         L"DependencyGraph\\Index\\UserAndDependentPackageAndDependencyType");
  if ( v3 < 0 )
  {
    v15 = 190;
    goto LABEL_28;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v30,
         L"DependencyGraph\\Index");
  if ( v3 < 0 )
  {
    v15 = 192;
    goto LABEL_28;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v29,
         L"DependencyGraph\\Data");
  if ( v3 < 0 )
  {
    v15 = 193;
    goto LABEL_28;
  }
  v3 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v28,
         L"DependencyGraph");
  if ( v3 < 0 )
  {
    v15 = 194;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)(unsigned int)v3,
      (int)v24);
    v16 = v31;
    v31 = 0;
    if ( v16 )
      SRCacheContext_Close(v16);
    goto LABEL_21;
  }
  v17 = v31;
  v31 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v30;
  v30 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v29;
  v29 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  v20 = v28;
  v28 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x18004dd70  push    rbp
0x18004dd72  push    rbx
0x18004dd73  push    rsi
0x18004dd74  push    rdi
0x18004dd75  mov     rbp, rsp
0x18004dd78  sub     rsp, 48h
0x18004dd7c  mov     rdi, rcx
0x18004dd7f  mov     [rbp+var_18], 1
0x18004dd83  mov     rcx, [rcx]
0x18004dd86  lea     rax, [rbp+arg_0]
0x18004dd8a  xor     esi, esi
0x18004dd8c  mov     [rbp+var_28], rax
0x18004dd90  lea     r9, [rbp+var_20]
0x18004dd94  mov     [rbp+arg_0], rsi
0x18004dd98  xor     r8d, r8d
0x18004dd9b  mov     [rbp+var_20], rsi
0x18004dd9f  lea     rdx, aDependencygrap_23; "DependencyGraph"
0x18004dda6  call    cs:__imp_SRCacheContext_Create
0x18004ddac  mov     ebx, eax
0x18004ddae  cmp     [rbp+var_18], sil
0x18004ddb2  jz      short loc_18004DDCD
0x18004ddb4  mov     r8, [rbp+var_28]
0x18004ddb8  mov     rdx, [rbp+var_20]
0x18004ddbc  mov     rcx, [r8]
0x18004ddbf  mov     [r8], rdx
0x18004ddc2  test    rcx, rcx
0x18004ddc5  jz      short loc_18004DDCD
0x18004ddc7  call    cs:__imp_SRCacheContext_Close
0x18004ddcd  test    ebx, ebx
0x18004ddcf  jns     short loc_18004DE1B
0x18004ddd1  mov     rcx, [rbp+20h]; this
0x18004ddd5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18004dddc  mov     r9d, ebx; char *
0x18004dddf  mov     edx, 1C2h; void *
0x18004dde4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dde9  mov     rcx, [rbp+20h]; this
0x18004dded  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x18004ddf4  mov     r9d, ebx; char *
0x18004ddf7  mov     edx, 0B5h; void *
0x18004ddfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004de01  mov     rcx, [rbp+arg_0]
0x18004de05  mov     [rbp+arg_0], rsi
0x18004de09  test    rcx, rcx
0x18004de0c  jz      short loc_18004DE14
0x18004de0e  call    cs:__imp_SRCacheContext_Close
0x18004de14  mov     eax, ebx
0x18004de16  jmp     loc_18004E0B7
0x18004de1b  mov     rcx, [rdi]
0x18004de1e  lea     rax, [rbp+arg_8]
0x18004de22  lea     r9, [rbp+var_20]
0x18004de26  mov     [rbp+var_28], rax
0x18004de2a  xor     r8d, r8d
0x18004de2d  mov     [rbp+arg_8], rsi
0x18004de31  lea     rdx, aDependencygrap_16; "DependencyGraph\\Data"
0x18004de38  mov     [rbp+var_20], rsi
0x18004de3c  mov     [rbp+var_18], 1
0x18004de40  call    cs:__imp_SRCacheContext_Create
0x18004de46  mov     ebx, eax
0x18004de48  cmp     [rbp+var_18], sil
0x18004de4c  jz      short loc_18004DE67
0x18004de4e  mov     r8, [rbp+var_28]
0x18004de52  mov     rdx, [rbp+var_20]
0x18004de56  mov     rcx, [r8]
0x18004de59  mov     [r8], rdx
0x18004de5c  test    rcx, rcx
0x18004de5f  jz      short loc_18004DE67
0x18004de61  call    cs:__imp_SRCacheContext_Close
0x18004de67  test    ebx, ebx
0x18004de69  jns     short loc_18004DEB7
0x18004de6b  mov     rcx, [rbp+20h]; this
0x18004de6f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18004de76  mov     r9d, ebx; char *
0x18004de79  mov     edx, 1C2h; void *
0x18004de7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004de83  mov     rcx, [rbp+20h]; this
0x18004de87  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x18004de8e  mov     r9d, ebx; char *
0x18004de91  mov     edx, 0B8h; void *
0x18004de96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004de9b  mov     rcx, [rbp+arg_8]
0x18004de9f  mov     [rbp+arg_8], rsi
0x18004dea3  test    rcx, rcx
0x18004dea6  jz      loc_18004DE01
0x18004deac  call    cs:__imp_SRCacheContext_Close
0x18004deb2  jmp     loc_18004DE01
0x18004deb7  mov     rcx, [rdi]
0x18004deba  lea     rax, [rbp+arg_10]
0x18004debe  lea     r9, [rbp+var_20]
0x18004dec2  mov     [rbp+var_28], rax
0x18004dec6  xor     r8d, r8d
0x18004dec9  mov     [rbp+arg_10], rsi
0x18004decd  lea     rdx, aDependencygrap_13; "DependencyGraph\\Index"
0x18004ded4  mov     [rbp+var_20], rsi
0x18004ded8  mov     [rbp+var_18], 1
0x18004dedc  call    cs:__imp_SRCacheContext_Create
0x18004dee2  mov     ebx, eax
0x18004dee4  cmp     [rbp+var_18], sil
0x18004dee8  jz      short loc_18004DF03
0x18004deea  mov     r8, [rbp+var_28]
0x18004deee  mov     rdx, [rbp+var_20]
0x18004def2  mov     rcx, [r8]
0x18004def5  mov     [r8], rdx
0x18004def8  test    rcx, rcx
0x18004defb  jz      short loc_18004DF03
0x18004defd  call    cs:__imp_SRCacheContext_Close
0x18004df03  test    ebx, ebx
0x18004df05  jns     short loc_18004DF53
0x18004df07  mov     rcx, [rbp+20h]; this
0x18004df0b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18004df12  mov     r9d, ebx; char *
0x18004df15  mov     edx, 1C2h; void *
0x18004df1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004df1f  mov     rcx, [rbp+20h]; this
0x18004df23  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x18004df2a  mov     r9d, ebx; char *
0x18004df2d  mov     edx, 0BBh; void *
0x18004df32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004df37  mov     rcx, [rbp+arg_10]
0x18004df3b  mov     [rbp+arg_10], rsi
0x18004df3f  test    rcx, rcx
0x18004df42  jz      loc_18004DE9B
0x18004df48  call    cs:__imp_SRCacheContext_Close
0x18004df4e  jmp     loc_18004DE9B
0x18004df53  mov     rcx, [rdi]
0x18004df56  lea     rax, [rbp+arg_18]
0x18004df5a  lea     r9, [rbp+var_20]
0x18004df5e  mov     [rbp+var_28], rax
0x18004df62  xor     r8d, r8d
0x18004df65  mov     [rbp+arg_18], rsi
0x18004df69  lea     rdx, aDependencygrap_6; "DependencyGraph\\Index\\UserAndDependen"...
0x18004df70  mov     [rbp+var_20], rsi
0x18004df74  mov     [rbp+var_18], 1
0x18004df78  call    cs:__imp_SRCacheContext_Create
0x18004df7e  mov     ebx, eax
0x18004df80  cmp     [rbp+var_18], sil
0x18004df84  jz      short loc_18004DF9F
0x18004df86  mov     r8, [rbp+var_28]
0x18004df8a  mov     rdx, [rbp+var_20]
0x18004df8e  mov     rcx, [r8]
0x18004df91  mov     [r8], rdx
0x18004df94  test    rcx, rcx
0x18004df97  jz      short loc_18004DF9F
0x18004df99  call    cs:__imp_SRCacheContext_Close
0x18004df9f  test    ebx, ebx
0x18004dfa1  jns     short loc_18004DFEF
0x18004dfa3  mov     rcx, [rbp+20h]; this
0x18004dfa7  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18004dfae  mov     r9d, ebx; char *
0x18004dfb1  mov     edx, 1C2h; void *
0x18004dfb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dfbb  mov     edx, 0BDh; void *
0x18004dfc0  mov     rcx, [rbp+20h]; this
0x18004dfc4  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x18004dfcb  mov     r9d, ebx; char *
0x18004dfce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dfd3  mov     rcx, [rbp+arg_18]
0x18004dfd7  mov     [rbp+arg_18], rsi
0x18004dfdb  test    rcx, rcx
0x18004dfde  jz      loc_18004DF37
0x18004dfe4  call    cs:__imp_SRCacheContext_Close
0x18004dfea  jmp     loc_18004DF37
0x18004dfef  lea     rdx, aDependencygrap_6; "DependencyGraph\\Index\\UserAndDependen"...
0x18004dff6  lea     rcx, [rbp+arg_18]; this
0x18004dffa  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18004dfff  mov     ebx, eax
0x18004e001  test    eax, eax
0x18004e003  jns     short loc_18004E00C
0x18004e005  mov     edx, 0BEh
0x18004e00a  jmp     short loc_18004DFC0
0x18004e00c  lea     rdx, aDependencygrap_13; "DependencyGraph\\Index"
0x18004e013  lea     rcx, [rbp+arg_10]; this
0x18004e017  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18004e01c  mov     ebx, eax
0x18004e01e  test    eax, eax
0x18004e020  jns     short loc_18004E029
0x18004e022  mov     edx, 0C0h
0x18004e027  jmp     short loc_18004DFC0
0x18004e029  lea     rdx, aDependencygrap_16; "DependencyGraph\\Data"
0x18004e030  lea     rcx, [rbp+arg_8]; this
0x18004e034  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18004e039  mov     ebx, eax
0x18004e03b  test    eax, eax
0x18004e03d  jns     short loc_18004E049
0x18004e03f  mov     edx, 0C1h
0x18004e044  jmp     loc_18004DFC0
0x18004e049  lea     rdx, aDependencygrap_23; "DependencyGraph"
0x18004e050  lea     rcx, [rbp+arg_0]; this
0x18004e054  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18004e059  mov     ebx, eax
0x18004e05b  test    eax, eax
0x18004e05d  jns     short loc_18004E069
0x18004e05f  mov     edx, 0C2h
0x18004e064  jmp     loc_18004DFC0
0x18004e069  mov     rcx, [rbp+arg_18]
0x18004e06d  mov     [rbp+arg_18], rsi
0x18004e071  test    rcx, rcx
0x18004e074  jz      short loc_18004E07C
0x18004e076  call    cs:__imp_SRCacheContext_Close
0x18004e07c  mov     rcx, [rbp+arg_10]
0x18004e080  mov     [rbp+arg_10], rsi
0x18004e084  test    rcx, rcx
0x18004e087  jz      short loc_18004E08F
0x18004e089  call    cs:__imp_SRCacheContext_Close
0x18004e08f  mov     rcx, [rbp+arg_8]
0x18004e093  mov     [rbp+arg_8], rsi
0x18004e097  test    rcx, rcx
0x18004e09a  jz      short loc_18004E0A2
0x18004e09c  call    cs:__imp_SRCacheContext_Close
0x18004e0a2  mov     rcx, [rbp+arg_0]
0x18004e0a6  mov     [rbp+arg_0], rsi
0x18004e0aa  test    rcx, rcx
0x18004e0ad  jz      short loc_18004E0B5
0x18004e0af  call    cs:__imp_SRCacheContext_Close
0x18004e0b5  xor     eax, eax
0x18004e0b7  add     rsp, 48h
0x18004e0bb  pop     rdi
0x18004e0bc  pop     rsi
0x18004e0bd  pop     rbx
0x18004e0be  pop     rbp
0x18004e0bf  retn
```
