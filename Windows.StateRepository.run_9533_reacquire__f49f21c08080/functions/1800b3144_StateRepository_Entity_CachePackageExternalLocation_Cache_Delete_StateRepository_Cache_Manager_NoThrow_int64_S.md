# StateRepository::Entity::CachePackageExternalLocation::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x1800b3144`
- end: `0x1800b359f`
- name: `?Cache_Delete@CachePackageExternalLocation@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1115`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180201904`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x1800b3144`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b31cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b321a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b32c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3494`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b34f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3536`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3571`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b31cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b321a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b32c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3494`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b34f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3536`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b3571`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b334b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b33c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b350c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3521`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b334b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b33c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b350c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b3521`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b31a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b3262`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b3435`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b31a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b3262`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800b3435`

## string_xrefs

- `0x1800b31dc`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b327f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b3452`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800b31fc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x1800b329a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x1800b3324`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x1800b33a1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`
- `0x1800b3472`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageexternallocation.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageExternalLocation::Cache_Delete(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v4; // rcx
  int IndexKeys; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v12; // si
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned __int16 *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int16 *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v30; // [rsp+48h] [rbp-B8h] BYREF
  char v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+268h] [rbp+168h]
  __int64 v35; // [rsp+270h] [rbp+170h]
  unsigned __int16 *v36; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v31 = 1;
  v4 = *a1;
  v29 = (__int64 *)v25;
  *(_QWORD *)v25 = 0;
  v30 = 0;
  IndexKeys = SRCacheContext_Open(v4, L"PackageExternalLocation", 0, &v30);
  if ( v31 )
  {
    v6 = *v29;
    *v29 = (__int64)v30;
    if ( v6 )
      SRCacheContext_Close(v6);
  }
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v25[0]);
    v7 = 387;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
      (const char *)(unsigned int)IndexKeys,
      v25[0]);
LABEL_7:
    v8 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)IndexKeys;
  }
  if ( *(_QWORD *)v25 )
  {
    v10 = *a1;
    v29 = &v26;
    v26 = 0;
    v30 = 0;
    v31 = 1;
    IndexKeys = SRCacheContext_Open(v10, L"PackageExternalLocation\\Data", 0, &v30);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v29);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v25[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
        (const char *)(unsigned int)IndexKeys,
        v25[0]);
LABEL_13:
      v11 = v26;
      v26 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      goto LABEL_7;
    }
    v32 = 0;
    v12 = v26 != 0;
    memset_0(v33, 0, sizeof(v33));
    v34 = 0;
    v36 = (unsigned __int16 *)v33;
    v35 = 256;
    v13 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v32, a2);
    IndexKeys = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
        (const char *)(unsigned int)v13,
        v25[0]);
LABEL_17:
      v14 = v32;
      v32 = 0;
      if ( v14 )
        SRCache_Free(v14);
      goto LABEL_13;
    }
    v29 = (__int64 *)&v27;
    v27 = 0;
    v30 = 0;
    v31 = 1;
    IndexKeys = StateRepository::CacheManagement::GetIndexKeys(
                  (struct StateRepository::Cache::Context_NoThrow *)&v26,
                  v36,
                  &v30);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v29);
    if ( IndexKeys < 0 )
    {
      v15 = 395;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
        (const char *)(unsigned int)IndexKeys,
        v25[0]);
LABEL_22:
      v16 = v27;
      v27 = 0;
      if ( v16 )
        SRCache_Free(v16);
      goto LABEL_17;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::Delete((StateRepository::Cache::Context_NoThrow *)&v26, v36);
    if ( IndexKeys < 0 )
    {
      v15 = 396;
      goto LABEL_21;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v26,
                  L"PackageExternalLocation\\Data");
    if ( IndexKeys < 0 )
    {
      v15 = 398;
      goto LABEL_21;
    }
    v17 = *a1;
    v29 = &v28;
    v28 = 0;
    v30 = 0;
    v31 = 1;
    IndexKeys = SRCacheContext_Open(v17, L"PackageExternalLocation\\Index", 0, &v30);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v29);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v25[0]);
      v18 = 402;
      goto LABEL_30;
    }
    v20 = v28;
    if ( v28 )
    {
      IndexKeys = StateRepository::CacheManagement::DeleteIndexKeys(
                    (struct StateRepository::Cache::Context_NoThrow *)&v28,
                    v27);
      if ( IndexKeys < 0 )
      {
        v18 = 405;
        goto LABEL_30;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v28,
                    L"PackageExternalLocation\\Index");
      if ( IndexKeys < 0 )
      {
        v18 = 406;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageexternallocation.cpp",
          (const char *)(unsigned int)IndexKeys,
          v25[0]);
        v19 = v28;
        v28 = 0;
        if ( v19 )
          SRCacheContext_Close(v19);
        goto LABEL_22;
      }
      v20 = v28;
    }
    v28 = 0;
    if ( v20 )
      SRCacheContext_Close(v20);
    v21 = v27;
    v27 = 0;
    if ( v21 )
      SRCache_Free(v21);
    v22 = v32;
    v32 = 0;
    if ( v22 )
      SRCache_Free(v22);
    v23 = v26;
    v26 = 0;
    if ( v23 )
      SRCacheContext_Close(v23);
    if ( v12 )
    {
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)v25,
                    L"PackageExternalLocation");
      if ( IndexKeys < 0 )
      {
        v7 = 411;
        goto LABEL_6;
      }
    }
  }
  v24 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v24 )
    SRCacheContext_Close(v24);
  return 0;
}

```

## disassembly

```asm
0x1800b3144  mov     [rsp-8+arg_10], rbx
0x1800b3149  push    rbp
0x1800b314a  push    rsi
0x1800b314b  push    rdi
0x1800b314c  push    r14
0x1800b314e  push    r15
0x1800b3150  lea     rbp, [rsp-190h]
0x1800b3158  sub     rsp, 290h
0x1800b315f  mov     rax, cs:__security_cookie
0x1800b3166  xor     rax, rsp
0x1800b3169  mov     [rbp+1B0h+var_30], rax
0x1800b3170  mov     r14, rdx
0x1800b3173  mov     [rsp+2B0h+var_260], 1
0x1800b3178  mov     rdi, rcx
0x1800b317b  lea     rax, [rsp+2B0h+var_290]
0x1800b3180  mov     rcx, [rcx]
0x1800b3183  lea     rdx, aPackageexterna_12; "PackageExternalLocation"
0x1800b318a  xor     r15d, r15d
0x1800b318d  mov     [rsp+2B0h+var_270], rax
0x1800b3192  lea     r9, [rsp+2B0h+var_268]
0x1800b3197  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800b319c  xor     r8d, r8d
0x1800b319f  mov     [rsp+2B0h+var_268], r15
0x1800b31a4  call    cs:__imp_SRCacheContext_Open
0x1800b31aa  mov     ebx, eax
0x1800b31ac  cmp     [rsp+2B0h+var_260], r15b
0x1800b31b1  jz      short loc_1800B31D1
0x1800b31b3  mov     rdx, [rsp+2B0h+var_270]
0x1800b31b8  mov     rcx, [rsp+2B0h+var_268]
0x1800b31bd  mov     rax, [rdx]
0x1800b31c0  mov     [rdx], rcx
0x1800b31c3  test    rax, rax
0x1800b31c6  jz      short loc_1800B31D1
0x1800b31c8  mov     rcx, rax
0x1800b31cb  call    cs:__imp_SRCacheContext_Close
0x1800b31d1  test    ebx, ebx
0x1800b31d3  jns     short loc_1800B3227
0x1800b31d5  mov     rcx, [rbp+1B8h]; this
0x1800b31dc  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b31e3  mov     r9d, ebx; char *
0x1800b31e6  mov     edx, 18Ch; void *
0x1800b31eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b31f0  mov     edx, 183h; void *
0x1800b31f5  mov     rcx, [rbp+1B8h]; this
0x1800b31fc  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x1800b3203  mov     r9d, ebx; char *
0x1800b3206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b320b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800b3210  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800b3215  test    rcx, rcx
0x1800b3218  jz      short loc_1800B3220
0x1800b321a  call    cs:__imp_SRCacheContext_Close
0x1800b3220  mov     eax, ebx
0x1800b3222  jmp     loc_1800B3579
0x1800b3227  cmp     qword ptr [rsp+2B0h+var_290], r15
0x1800b322c  setnz   al
0x1800b322f  test    al, al
0x1800b3231  jz      loc_1800B3562
0x1800b3237  mov     rcx, [rdi]
0x1800b323a  lea     rax, [rsp+2B0h+var_288]
0x1800b323f  lea     r9, [rsp+2B0h+var_268]
0x1800b3244  mov     [rsp+2B0h+var_270], rax
0x1800b3249  xor     r8d, r8d
0x1800b324c  mov     [rsp+2B0h+var_288], r15
0x1800b3251  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800b3258  mov     [rsp+2B0h+var_268], r15
0x1800b325d  mov     [rsp+2B0h+var_260], 1
0x1800b3262  call    cs:__imp_SRCacheContext_Open
0x1800b3268  lea     rcx, [rsp+2B0h+var_270]
0x1800b326d  mov     ebx, eax
0x1800b326f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b3274  test    ebx, ebx
0x1800b3276  jns     short loc_1800B32CC
0x1800b3278  mov     rcx, [rbp+1B8h]; this
0x1800b327f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b3286  mov     r9d, ebx; char *
0x1800b3289  mov     edx, 18Ch; void *
0x1800b328e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3293  mov     rcx, [rbp+1B8h]; this
0x1800b329a  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x1800b32a1  mov     r9d, ebx; char *
0x1800b32a4  mov     edx, 187h; void *
0x1800b32a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b32ae  mov     rcx, [rsp+2B0h+var_288]
0x1800b32b3  mov     [rsp+2B0h+var_288], r15
0x1800b32b8  test    rcx, rcx
0x1800b32bb  jz      loc_1800B320B
0x1800b32c1  call    cs:__imp_SRCacheContext_Close
0x1800b32c7  jmp     loc_1800B320B
0x1800b32cc  cmp     [rsp+2B0h+var_288], r15
0x1800b32d1  lea     rcx, [rsp+2B0h+var_248]; void *
0x1800b32d6  mov     r8d, 200h; Size
0x1800b32dc  mov     [rsp+2B0h+var_250], r15
0x1800b32e1  setnz   sil
0x1800b32e5  xor     edx, edx; Val
0x1800b32e7  call    memset_0
0x1800b32ec  lea     rax, [rsp+2B0h+var_248]
0x1800b32f1  mov     [rbp+1B0h+var_48], r15
0x1800b32f8  mov     rdx, r14; unsigned __int64
0x1800b32fb  mov     [rbp+1B0h+var_38], rax
0x1800b3302  lea     rcx, [rsp+2B0h+var_250]; this
0x1800b3307  mov     [rbp+1B0h+var_40], 100h
0x1800b3312  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800b3317  mov     ebx, eax
0x1800b3319  test    eax, eax
0x1800b331b  jns     short loc_1800B3356
0x1800b331d  mov     rcx, [rbp+1B8h]; this
0x1800b3324  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x1800b332b  mov     r9d, eax; char *
0x1800b332e  mov     edx, 189h; void *
0x1800b3333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3338  mov     rcx, [rsp+2B0h+var_250]
0x1800b333d  mov     [rsp+2B0h+var_250], r15
0x1800b3342  test    rcx, rcx
0x1800b3345  jz      loc_1800B32AE
0x1800b334b  call    cs:__imp_SRCache_Free
0x1800b3351  jmp     loc_1800B32AE
0x1800b3356  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x1800b335d  lea     rax, [rsp+2B0h+var_280]
0x1800b3362  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x1800b3367  mov     [rsp+2B0h+var_270], rax
0x1800b336c  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x1800b3371  mov     [rsp+2B0h+var_280], r15
0x1800b3376  mov     [rsp+2B0h+var_268], r15
0x1800b337b  mov     [rsp+2B0h+var_260], 1
0x1800b3380  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x1800b3385  lea     rcx, [rsp+2B0h+var_270]
0x1800b338a  mov     ebx, eax
0x1800b338c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800b3391  test    ebx, ebx
0x1800b3393  jns     short loc_1800B33CE
0x1800b3395  mov     edx, 18Bh; void *
0x1800b339a  mov     rcx, [rbp+1B8h]; this
0x1800b33a1  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x1800b33a8  mov     r9d, ebx; char *
0x1800b33ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b33b0  mov     rcx, [rsp+2B0h+var_280]
0x1800b33b5  mov     [rsp+2B0h+var_280], r15
0x1800b33ba  test    rcx, rcx
0x1800b33bd  jz      loc_1800B3338
0x1800b33c3  call    cs:__imp_SRCache_Free
0x1800b33c9  jmp     loc_1800B3338
0x1800b33ce  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x1800b33d5  lea     rcx, [rsp+2B0h+var_288]; this
0x1800b33da  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x1800b33df  mov     ebx, eax
0x1800b33e1  test    eax, eax
0x1800b33e3  jns     short loc_1800B33EC
0x1800b33e5  mov     edx, 18Ch
0x1800b33ea  jmp     short loc_1800B339A
0x1800b33ec  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800b33f3  lea     rcx, [rsp+2B0h+var_288]; this
0x1800b33f8  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b33fd  mov     ebx, eax
0x1800b33ff  test    eax, eax
0x1800b3401  jns     short loc_1800B340A
0x1800b3403  mov     edx, 18Eh
0x1800b3408  jmp     short loc_1800B339A
0x1800b340a  mov     rcx, [rdi]
0x1800b340d  lea     rax, [rsp+2B0h+var_278]
0x1800b3412  lea     r9, [rsp+2B0h+var_268]
0x1800b3417  mov     [rsp+2B0h+var_270], rax
0x1800b341c  xor     r8d, r8d
0x1800b341f  mov     [rsp+2B0h+var_278], r15
0x1800b3424  lea     rdx, aPackageexterna_7; "PackageExternalLocation\\Index"
0x1800b342b  mov     [rsp+2B0h+var_268], r15
0x1800b3430  mov     [rsp+2B0h+var_260], 1
0x1800b3435  call    cs:__imp_SRCacheContext_Open
0x1800b343b  lea     rcx, [rsp+2B0h+var_270]
0x1800b3440  mov     ebx, eax
0x1800b3442  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800b3447  test    ebx, ebx
0x1800b3449  jns     short loc_1800B349F
0x1800b344b  mov     rcx, [rbp+1B8h]; this
0x1800b3452  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800b3459  mov     r9d, ebx; char *
0x1800b345c  mov     edx, 18Ch; void *
0x1800b3461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3466  mov     edx, 192h; void *
0x1800b346b  mov     rcx, [rbp+1B8h]; this
0x1800b3472  lea     r8, aOnecoreBaseApp_218; "onecore\\base\\appmodel\\staterepositor"...
0x1800b3479  mov     r9d, ebx; char *
0x1800b347c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3481  mov     rcx, [rsp+2B0h+var_278]
0x1800b3486  mov     [rsp+2B0h+var_278], r15
0x1800b348b  test    rcx, rcx
0x1800b348e  jz      loc_1800B33B0
0x1800b3494  call    cs:__imp_SRCacheContext_Close
0x1800b349a  jmp     loc_1800B33B0
0x1800b349f  mov     rcx, [rsp+2B0h+var_278]
0x1800b34a4  test    rcx, rcx
0x1800b34a7  setnz   al
0x1800b34aa  test    al, al
0x1800b34ac  jz      short loc_1800B34ED
0x1800b34ae  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x1800b34b3  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x1800b34b8  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x1800b34bd  mov     ebx, eax
0x1800b34bf  test    eax, eax
0x1800b34c1  jns     short loc_1800B34CA
0x1800b34c3  mov     edx, 195h
0x1800b34c8  jmp     short loc_1800B346B
0x1800b34ca  lea     rdx, aPackageexterna_7; "PackageExternalLocation\\Index"
0x1800b34d1  lea     rcx, [rsp+2B0h+var_278]; this
0x1800b34d6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b34db  mov     ebx, eax
0x1800b34dd  test    eax, eax
0x1800b34df  jns     short loc_1800B34E8
0x1800b34e1  mov     edx, 196h
0x1800b34e6  jmp     short loc_1800B346B
0x1800b34e8  mov     rcx, [rsp+2B0h+var_278]
0x1800b34ed  mov     [rsp+2B0h+var_278], r15
0x1800b34f2  test    rcx, rcx
0x1800b34f5  jz      short loc_1800B34FD
0x1800b34f7  call    cs:__imp_SRCacheContext_Close
0x1800b34fd  mov     rcx, [rsp+2B0h+var_280]
0x1800b3502  mov     [rsp+2B0h+var_280], r15
0x1800b3507  test    rcx, rcx
0x1800b350a  jz      short loc_1800B3512
0x1800b350c  call    cs:__imp_SRCache_Free
0x1800b3512  mov     rcx, [rsp+2B0h+var_250]
0x1800b3517  mov     [rsp+2B0h+var_250], r15
0x1800b351c  test    rcx, rcx
0x1800b351f  jz      short loc_1800B3527
0x1800b3521  call    cs:__imp_SRCache_Free
0x1800b3527  mov     rcx, [rsp+2B0h+var_288]
0x1800b352c  mov     [rsp+2B0h+var_288], r15
0x1800b3531  test    rcx, rcx
0x1800b3534  jz      short loc_1800B353C
0x1800b3536  call    cs:__imp_SRCacheContext_Close
0x1800b353c  test    sil, sil
0x1800b353f  jz      short loc_1800B3562
0x1800b3541  lea     rdx, aPackageexterna_12; "PackageExternalLocation"
0x1800b3548  lea     rcx, [rsp+2B0h+var_290]; this
0x1800b354d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800b3552  mov     ebx, eax
0x1800b3554  test    eax, eax
0x1800b3556  jns     short loc_1800B3562
0x1800b3558  mov     edx, 19Bh
0x1800b355d  jmp     loc_1800B31F5
0x1800b3562  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800b3567  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800b356c  test    rcx, rcx
0x1800b356f  jz      short loc_1800B3577
0x1800b3571  call    cs:__imp_SRCacheContext_Close
0x1800b3577  xor     eax, eax
0x1800b3579  mov     rcx, [rbp+1B0h+var_30]
0x1800b3580  xor     rcx, rsp; StackCookie
0x1800b3583  call    __security_check_cookie
0x1800b3588  mov     rbx, [rsp+2B0h+arg_10]
0x1800b3590  add     rsp, 290h
0x1800b3597  pop     r15
0x1800b3599  pop     r14
0x1800b359b  pop     rdi
0x1800b359c  pop     rsi
0x1800b359d  pop     rbp
0x1800b359e  retn
```
