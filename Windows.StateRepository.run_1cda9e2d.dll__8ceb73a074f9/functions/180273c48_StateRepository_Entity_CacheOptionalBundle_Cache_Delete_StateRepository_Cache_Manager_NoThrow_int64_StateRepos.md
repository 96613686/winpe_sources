# StateRepository::Entity::CacheOptionalBundle::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x180273c48`
- end: `0x180274088`
- name: `?Cache_Delete@CacheOptionalBundle@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18020163c`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x18018f650`
- `0x180190234`
- `0x180273c48`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273d03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273daa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273f7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273fe0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027401f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027405a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273d03`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273daa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273f7d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180273fe0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027401f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027405a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180273e34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180273eac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180273ff5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18027400a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180273e34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180273eac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180273ff5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18027400a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180273ca8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180273d4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180273f1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180273ca8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180273d4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180273f1e`

## string_xrefs

- `0x180273cc5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180273d68`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180273f3b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180273ce5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x180273d83`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x180273e0d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x180273e8a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`
- `0x180273f5b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheoptionalbundle.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheOptionalBundle::Cache_Delete(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  int IndexKeys; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  bool v11; // si
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int16 *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int16 *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-B8h] BYREF
  char v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+268h] [rbp+168h]
  __int64 v34; // [rsp+270h] [rbp+170h]
  unsigned __int16 *v35; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v30 = 1;
  v4 = *a1;
  v28 = (__int64 *)v24;
  *(_QWORD *)v24 = 0;
  v29 = 0;
  IndexKeys = SRCacheContext_Open(v4, L"OptionalBundle", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
    v6 = 230;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
LABEL_4:
    v7 = *(_QWORD *)v24;
    *(_QWORD *)v24 = 0;
    if ( v7 )
      SRCacheContext_Close(v7);
    return (unsigned int)IndexKeys;
  }
  if ( *(_QWORD *)v24 )
  {
    v9 = *a1;
    v28 = &v25;
    v25 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v9, L"OptionalBundle\\Data", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
LABEL_10:
      v10 = v25;
      v25 = 0;
      if ( v10 )
        SRCacheContext_Close(v10);
      goto LABEL_4;
    }
    v31 = 0;
    v11 = v25 != 0;
    memset_0(v32, 0, sizeof(v32));
    v33 = 0;
    v35 = (unsigned __int16 *)v32;
    v34 = 256;
    v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, a2);
    IndexKeys = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
        (const char *)(unsigned int)v12,
        v24[0]);
LABEL_14:
      v13 = v31;
      v31 = 0;
      if ( v13 )
        SRCache_Free(v13);
      goto LABEL_10;
    }
    v28 = (__int64 *)&v26;
    v26 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = StateRepository::CacheManagement::GetIndexKeys(
                  (struct StateRepository::Cache::Context_NoThrow *)&v25,
                  v35,
                  &v29);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v28);
    if ( IndexKeys < 0 )
    {
      v14 = 238;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
LABEL_19:
      v15 = v26;
      v26 = 0;
      if ( v15 )
        SRCache_Free(v15);
      goto LABEL_14;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::Delete((StateRepository::Cache::Context_NoThrow *)&v25, v35);
    if ( IndexKeys < 0 )
    {
      v14 = 239;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v25,
                  L"OptionalBundle\\Data");
    if ( IndexKeys < 0 )
    {
      v14 = 241;
      goto LABEL_18;
    }
    v16 = *a1;
    v28 = &v27;
    v27 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v16, L"OptionalBundle\\Index", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      v17 = 245;
      goto LABEL_27;
    }
    v19 = v27;
    if ( v27 )
    {
      IndexKeys = StateRepository::CacheManagement::DeleteIndexKeys(
                    (struct StateRepository::Cache::Context_NoThrow *)&v27,
                    v26);
      if ( IndexKeys < 0 )
      {
        v17 = 248;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v27,
                    L"OptionalBundle\\Index");
      if ( IndexKeys < 0 )
      {
        v17 = 249;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheoptionalbundle.cpp",
          (const char *)(unsigned int)IndexKeys,
          v24[0]);
        v18 = v27;
        v27 = 0;
        if ( v18 )
          SRCacheContext_Close(v18);
        goto LABEL_19;
      }
      v19 = v27;
    }
    v27 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    v20 = v26;
    v26 = 0;
    if ( v20 )
      SRCache_Free(v20);
    v21 = v31;
    v31 = 0;
    if ( v21 )
      SRCache_Free(v21);
    v22 = v25;
    v25 = 0;
    if ( v22 )
      SRCacheContext_Close(v22);
    if ( v11 )
    {
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)v24,
                    L"OptionalBundle");
      if ( IndexKeys < 0 )
      {
        v6 = 254;
        goto LABEL_3;
      }
    }
  }
  v23 = *(_QWORD *)v24;
  *(_QWORD *)v24 = 0;
  if ( v23 )
    SRCacheContext_Close(v23);
  return 0;
}

```

## disassembly

```asm
0x180273c48  mov     [rsp-8+arg_10], rbx
0x180273c4d  push    rbp
0x180273c4e  push    rsi
0x180273c4f  push    rdi
0x180273c50  push    r14
0x180273c52  push    r15
0x180273c54  lea     rbp, [rsp-190h]
0x180273c5c  sub     rsp, 290h
0x180273c63  mov     rax, cs:__security_cookie
0x180273c6a  xor     rax, rsp
0x180273c6d  mov     [rbp+1B0h+var_30], rax
0x180273c74  mov     r14, rdx
0x180273c77  mov     [rsp+2B0h+var_260], 1
0x180273c7c  mov     rdi, rcx
0x180273c7f  lea     rax, [rsp+2B0h+var_290]
0x180273c84  mov     rcx, [rcx]
0x180273c87  lea     rdx, aOptionalbundle_4; "OptionalBundle"
0x180273c8e  xor     r15d, r15d
0x180273c91  mov     [rsp+2B0h+var_270], rax
0x180273c96  lea     r9, [rsp+2B0h+var_268]
0x180273c9b  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x180273ca0  xor     r8d, r8d
0x180273ca3  mov     [rsp+2B0h+var_268], r15
0x180273ca8  call    cs:__imp_SRCacheContext_Open
0x180273cae  lea     rcx, [rsp+2B0h+var_270]
0x180273cb3  mov     ebx, eax
0x180273cb5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180273cba  test    ebx, ebx
0x180273cbc  jns     short loc_180273D10
0x180273cbe  mov     rcx, [rbp+1B8h]; this
0x180273cc5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180273ccc  mov     r9d, ebx; char *
0x180273ccf  mov     edx, 18Ch; void *
0x180273cd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273cd9  mov     edx, 0E6h; void *
0x180273cde  mov     rcx, [rbp+1B8h]; this
0x180273ce5  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180273cec  mov     r9d, ebx; char *
0x180273cef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273cf4  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180273cf9  mov     qword ptr [rsp+2B0h+var_290], r15
0x180273cfe  test    rcx, rcx
0x180273d01  jz      short loc_180273D09
0x180273d03  call    cs:__imp_SRCacheContext_Close
0x180273d09  mov     eax, ebx
0x180273d0b  jmp     loc_180274062
0x180273d10  cmp     qword ptr [rsp+2B0h+var_290], r15
0x180273d15  setnz   al
0x180273d18  test    al, al
0x180273d1a  jz      loc_18027404B
0x180273d20  mov     rcx, [rdi]
0x180273d23  lea     rax, [rsp+2B0h+var_288]
0x180273d28  lea     r9, [rsp+2B0h+var_268]
0x180273d2d  mov     [rsp+2B0h+var_270], rax
0x180273d32  xor     r8d, r8d
0x180273d35  mov     [rsp+2B0h+var_288], r15
0x180273d3a  lea     rdx, aOptionalbundle_0; "OptionalBundle\\Data"
0x180273d41  mov     [rsp+2B0h+var_268], r15
0x180273d46  mov     [rsp+2B0h+var_260], 1
0x180273d4b  call    cs:__imp_SRCacheContext_Open
0x180273d51  lea     rcx, [rsp+2B0h+var_270]
0x180273d56  mov     ebx, eax
0x180273d58  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180273d5d  test    ebx, ebx
0x180273d5f  jns     short loc_180273DB5
0x180273d61  mov     rcx, [rbp+1B8h]; this
0x180273d68  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180273d6f  mov     r9d, ebx; char *
0x180273d72  mov     edx, 18Ch; void *
0x180273d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273d7c  mov     rcx, [rbp+1B8h]; this
0x180273d83  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180273d8a  mov     r9d, ebx; char *
0x180273d8d  mov     edx, 0EAh; void *
0x180273d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273d97  mov     rcx, [rsp+2B0h+var_288]
0x180273d9c  mov     [rsp+2B0h+var_288], r15
0x180273da1  test    rcx, rcx
0x180273da4  jz      loc_180273CF4
0x180273daa  call    cs:__imp_SRCacheContext_Close
0x180273db0  jmp     loc_180273CF4
0x180273db5  cmp     [rsp+2B0h+var_288], r15
0x180273dba  lea     rcx, [rsp+2B0h+var_248]; void *
0x180273dbf  mov     r8d, 200h; Size
0x180273dc5  mov     [rsp+2B0h+var_250], r15
0x180273dca  setnz   sil
0x180273dce  xor     edx, edx; Val
0x180273dd0  call    memset_0
0x180273dd5  lea     rax, [rsp+2B0h+var_248]
0x180273dda  mov     [rbp+1B0h+var_48], r15
0x180273de1  mov     rdx, r14; unsigned __int64
0x180273de4  mov     [rbp+1B0h+var_38], rax
0x180273deb  lea     rcx, [rsp+2B0h+var_250]; this
0x180273df0  mov     [rbp+1B0h+var_40], 100h
0x180273dfb  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180273e00  mov     ebx, eax
0x180273e02  test    eax, eax
0x180273e04  jns     short loc_180273E3F
0x180273e06  mov     rcx, [rbp+1B8h]; this
0x180273e0d  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180273e14  mov     r9d, eax; char *
0x180273e17  mov     edx, 0ECh; void *
0x180273e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273e21  mov     rcx, [rsp+2B0h+var_250]
0x180273e26  mov     [rsp+2B0h+var_250], r15
0x180273e2b  test    rcx, rcx
0x180273e2e  jz      loc_180273D97
0x180273e34  call    cs:__imp_SRCache_Free
0x180273e3a  jmp     loc_180273D97
0x180273e3f  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x180273e46  lea     rax, [rsp+2B0h+var_280]
0x180273e4b  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x180273e50  mov     [rsp+2B0h+var_270], rax
0x180273e55  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x180273e5a  mov     [rsp+2B0h+var_280], r15
0x180273e5f  mov     [rsp+2B0h+var_268], r15
0x180273e64  mov     [rsp+2B0h+var_260], 1
0x180273e69  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x180273e6e  lea     rcx, [rsp+2B0h+var_270]
0x180273e73  mov     ebx, eax
0x180273e75  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180273e7a  test    ebx, ebx
0x180273e7c  jns     short loc_180273EB7
0x180273e7e  mov     edx, 0EEh; void *
0x180273e83  mov     rcx, [rbp+1B8h]; this
0x180273e8a  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180273e91  mov     r9d, ebx; char *
0x180273e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273e99  mov     rcx, [rsp+2B0h+var_280]
0x180273e9e  mov     [rsp+2B0h+var_280], r15
0x180273ea3  test    rcx, rcx
0x180273ea6  jz      loc_180273E21
0x180273eac  call    cs:__imp_SRCache_Free
0x180273eb2  jmp     loc_180273E21
0x180273eb7  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x180273ebe  lea     rcx, [rsp+2B0h+var_288]; this
0x180273ec3  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x180273ec8  mov     ebx, eax
0x180273eca  test    eax, eax
0x180273ecc  jns     short loc_180273ED5
0x180273ece  mov     edx, 0EFh
0x180273ed3  jmp     short loc_180273E83
0x180273ed5  lea     rdx, aOptionalbundle_0; "OptionalBundle\\Data"
0x180273edc  lea     rcx, [rsp+2B0h+var_288]; this
0x180273ee1  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180273ee6  mov     ebx, eax
0x180273ee8  test    eax, eax
0x180273eea  jns     short loc_180273EF3
0x180273eec  mov     edx, 0F1h
0x180273ef1  jmp     short loc_180273E83
0x180273ef3  mov     rcx, [rdi]
0x180273ef6  lea     rax, [rsp+2B0h+var_278]
0x180273efb  lea     r9, [rsp+2B0h+var_268]
0x180273f00  mov     [rsp+2B0h+var_270], rax
0x180273f05  xor     r8d, r8d
0x180273f08  mov     [rsp+2B0h+var_278], r15
0x180273f0d  lea     rdx, aOptionalbundle_18; "OptionalBundle\\Index"
0x180273f14  mov     [rsp+2B0h+var_268], r15
0x180273f19  mov     [rsp+2B0h+var_260], 1
0x180273f1e  call    cs:__imp_SRCacheContext_Open
0x180273f24  lea     rcx, [rsp+2B0h+var_270]
0x180273f29  mov     ebx, eax
0x180273f2b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180273f30  test    ebx, ebx
0x180273f32  jns     short loc_180273F88
0x180273f34  mov     rcx, [rbp+1B8h]; this
0x180273f3b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180273f42  mov     r9d, ebx; char *
0x180273f45  mov     edx, 18Ch; void *
0x180273f4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273f4f  mov     edx, 0F5h; void *
0x180273f54  mov     rcx, [rbp+1B8h]; this
0x180273f5b  lea     r8, aOnecoreBaseApp_432; "onecore\\base\\appmodel\\staterepositor"...
0x180273f62  mov     r9d, ebx; char *
0x180273f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180273f6a  mov     rcx, [rsp+2B0h+var_278]
0x180273f6f  mov     [rsp+2B0h+var_278], r15
0x180273f74  test    rcx, rcx
0x180273f77  jz      loc_180273E99
0x180273f7d  call    cs:__imp_SRCacheContext_Close
0x180273f83  jmp     loc_180273E99
0x180273f88  mov     rcx, [rsp+2B0h+var_278]
0x180273f8d  test    rcx, rcx
0x180273f90  setnz   al
0x180273f93  test    al, al
0x180273f95  jz      short loc_180273FD6
0x180273f97  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x180273f9c  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x180273fa1  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x180273fa6  mov     ebx, eax
0x180273fa8  test    eax, eax
0x180273faa  jns     short loc_180273FB3
0x180273fac  mov     edx, 0F8h
0x180273fb1  jmp     short loc_180273F54
0x180273fb3  lea     rdx, aOptionalbundle_18; "OptionalBundle\\Index"
0x180273fba  lea     rcx, [rsp+2B0h+var_278]; this
0x180273fbf  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180273fc4  mov     ebx, eax
0x180273fc6  test    eax, eax
0x180273fc8  jns     short loc_180273FD1
0x180273fca  mov     edx, 0F9h
0x180273fcf  jmp     short loc_180273F54
0x180273fd1  mov     rcx, [rsp+2B0h+var_278]
0x180273fd6  mov     [rsp+2B0h+var_278], r15
0x180273fdb  test    rcx, rcx
0x180273fde  jz      short loc_180273FE6
0x180273fe0  call    cs:__imp_SRCacheContext_Close
0x180273fe6  mov     rcx, [rsp+2B0h+var_280]
0x180273feb  mov     [rsp+2B0h+var_280], r15
0x180273ff0  test    rcx, rcx
0x180273ff3  jz      short loc_180273FFB
0x180273ff5  call    cs:__imp_SRCache_Free
0x180273ffb  mov     rcx, [rsp+2B0h+var_250]
0x180274000  mov     [rsp+2B0h+var_250], r15
0x180274005  test    rcx, rcx
0x180274008  jz      short loc_180274010
0x18027400a  call    cs:__imp_SRCache_Free
0x180274010  mov     rcx, [rsp+2B0h+var_288]
0x180274015  mov     [rsp+2B0h+var_288], r15
0x18027401a  test    rcx, rcx
0x18027401d  jz      short loc_180274025
0x18027401f  call    cs:__imp_SRCacheContext_Close
0x180274025  test    sil, sil
0x180274028  jz      short loc_18027404B
0x18027402a  lea     rdx, aOptionalbundle_4; "OptionalBundle"
0x180274031  lea     rcx, [rsp+2B0h+var_290]; this
0x180274036  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18027403b  mov     ebx, eax
0x18027403d  test    eax, eax
0x18027403f  jns     short loc_18027404B
0x180274041  mov     edx, 0FEh
0x180274046  jmp     loc_180273CDE
0x18027404b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180274050  mov     qword ptr [rsp+2B0h+var_290], r15
0x180274055  test    rcx, rcx
0x180274058  jz      short loc_180274060
0x18027405a  call    cs:__imp_SRCacheContext_Close
0x180274060  xor     eax, eax
0x180274062  mov     rcx, [rbp+1B0h+var_30]
0x180274069  xor     rcx, rsp; StackCookie
0x18027406c  call    __security_check_cookie
0x180274071  mov     rbx, [rsp+2B0h+arg_10]
0x180274079  add     rsp, 290h
0x180274080  pop     r15
0x180274082  pop     r14
0x180274084  pop     rdi
0x180274085  pop     rsi
0x180274086  pop     rbp
0x180274087  retn
```
