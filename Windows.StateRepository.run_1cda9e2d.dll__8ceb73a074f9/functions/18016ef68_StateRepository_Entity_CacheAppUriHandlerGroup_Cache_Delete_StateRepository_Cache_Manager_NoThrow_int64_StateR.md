# StateRepository::Entity::CacheAppUriHandlerGroup::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x18016ef68`
- end: `0x18016f3a8`
- name: `?Cache_Delete@CacheAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180200b38`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x18016ef68`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f023`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f0ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f29d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f300`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f33f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f37a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f023`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f0ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f29d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f300`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f33f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016f37a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f154`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f1cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f315`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f32a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f154`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f1cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f315`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016f32a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016efc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016f06b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016f23e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016efc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016f06b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016f23e`

## string_xrefs

- `0x18016efe5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016f088`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016f25b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016efa7`: `AppUriHandlerGroup`
- `0x18016f34a`: `AppUriHandlerGroup`
- `0x18016f22d`: `AppUriHandlerGroup\Index`
- `0x18016f2d3`: `AppUriHandlerGroup\Index`
- `0x18016f05a`: `AppUriHandlerGroup\Data`
- `0x18016f1f5`: `AppUriHandlerGroup\Data`
- `0x18016f005`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x18016f0a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x18016f12d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x18016f1aa`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x18016f27b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheAppUriHandlerGroup::Cache_Delete(__int64 *a1, __int64 a2)
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
  IndexKeys = SRCacheContext_Open(v4, L"AppUriHandlerGroup", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
    v6 = 460;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
    IndexKeys = SRCacheContext_Open(v9, L"AppUriHandlerGroup\\Data", 0, &v29);
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
        (void *)0x1D0,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
        (void *)0x1D2,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
      v14 = 468;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
      v14 = 469;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v25,
                  L"AppUriHandlerGroup\\Data");
    if ( IndexKeys < 0 )
    {
      v14 = 471;
      goto LABEL_18;
    }
    v16 = *a1;
    v28 = &v27;
    v27 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v16, L"AppUriHandlerGroup\\Index", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      v17 = 475;
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
        v17 = 478;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v27,
                    L"AppUriHandlerGroup\\Index");
      if ( IndexKeys < 0 )
      {
        v17 = 479;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
                    L"AppUriHandlerGroup");
      if ( IndexKeys < 0 )
      {
        v6 = 484;
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
0x18016ef68  mov     [rsp-8+arg_10], rbx
0x18016ef6d  push    rbp
0x18016ef6e  push    rsi
0x18016ef6f  push    rdi
0x18016ef70  push    r14
0x18016ef72  push    r15
0x18016ef74  lea     rbp, [rsp-190h]
0x18016ef7c  sub     rsp, 290h
0x18016ef83  mov     rax, cs:__security_cookie
0x18016ef8a  xor     rax, rsp
0x18016ef8d  mov     [rbp+1B0h+var_30], rax
0x18016ef94  mov     r14, rdx
0x18016ef97  mov     [rsp+2B0h+var_260], 1
0x18016ef9c  mov     rdi, rcx
0x18016ef9f  lea     rax, [rsp+2B0h+var_290]
0x18016efa4  mov     rcx, [rcx]
0x18016efa7  lea     rdx, aAppurihandlerg_10; "AppUriHandlerGroup"
0x18016efae  xor     r15d, r15d
0x18016efb1  mov     [rsp+2B0h+var_270], rax
0x18016efb6  lea     r9, [rsp+2B0h+var_268]
0x18016efbb  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18016efc0  xor     r8d, r8d
0x18016efc3  mov     [rsp+2B0h+var_268], r15
0x18016efc8  call    cs:__imp_SRCacheContext_Open
0x18016efce  lea     rcx, [rsp+2B0h+var_270]
0x18016efd3  mov     ebx, eax
0x18016efd5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016efda  test    ebx, ebx
0x18016efdc  jns     short loc_18016F030
0x18016efde  mov     rcx, [rbp+1B8h]; this
0x18016efe5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016efec  mov     r9d, ebx; char *
0x18016efef  mov     edx, 18Ch; void *
0x18016eff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016eff9  mov     edx, 1CCh; void *
0x18016effe  mov     rcx, [rbp+1B8h]; this
0x18016f005  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18016f00c  mov     r9d, ebx; char *
0x18016f00f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f014  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18016f019  mov     qword ptr [rsp+2B0h+var_290], r15
0x18016f01e  test    rcx, rcx
0x18016f021  jz      short loc_18016F029
0x18016f023  call    cs:__imp_SRCacheContext_Close
0x18016f029  mov     eax, ebx
0x18016f02b  jmp     loc_18016F382
0x18016f030  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18016f035  setnz   al
0x18016f038  test    al, al
0x18016f03a  jz      loc_18016F36B
0x18016f040  mov     rcx, [rdi]
0x18016f043  lea     rax, [rsp+2B0h+var_288]
0x18016f048  lea     r9, [rsp+2B0h+var_268]
0x18016f04d  mov     [rsp+2B0h+var_270], rax
0x18016f052  xor     r8d, r8d
0x18016f055  mov     [rsp+2B0h+var_288], r15
0x18016f05a  lea     rdx, aAppurihandlerg_3; "AppUriHandlerGroup\\Data"
0x18016f061  mov     [rsp+2B0h+var_268], r15
0x18016f066  mov     [rsp+2B0h+var_260], 1
0x18016f06b  call    cs:__imp_SRCacheContext_Open
0x18016f071  lea     rcx, [rsp+2B0h+var_270]
0x18016f076  mov     ebx, eax
0x18016f078  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016f07d  test    ebx, ebx
0x18016f07f  jns     short loc_18016F0D5
0x18016f081  mov     rcx, [rbp+1B8h]; this
0x18016f088  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016f08f  mov     r9d, ebx; char *
0x18016f092  mov     edx, 18Ch; void *
0x18016f097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f09c  mov     rcx, [rbp+1B8h]; this
0x18016f0a3  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18016f0aa  mov     r9d, ebx; char *
0x18016f0ad  mov     edx, 1D0h; void *
0x18016f0b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f0b7  mov     rcx, [rsp+2B0h+var_288]
0x18016f0bc  mov     [rsp+2B0h+var_288], r15
0x18016f0c1  test    rcx, rcx
0x18016f0c4  jz      loc_18016F014
0x18016f0ca  call    cs:__imp_SRCacheContext_Close
0x18016f0d0  jmp     loc_18016F014
0x18016f0d5  cmp     [rsp+2B0h+var_288], r15
0x18016f0da  lea     rcx, [rsp+2B0h+var_248]; void *
0x18016f0df  mov     r8d, 200h; Size
0x18016f0e5  mov     [rsp+2B0h+var_250], r15
0x18016f0ea  setnz   sil
0x18016f0ee  xor     edx, edx; Val
0x18016f0f0  call    memset_0
0x18016f0f5  lea     rax, [rsp+2B0h+var_248]
0x18016f0fa  mov     [rbp+1B0h+var_48], r15
0x18016f101  mov     rdx, r14; unsigned __int64
0x18016f104  mov     [rbp+1B0h+var_38], rax
0x18016f10b  lea     rcx, [rsp+2B0h+var_250]; this
0x18016f110  mov     [rbp+1B0h+var_40], 100h
0x18016f11b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18016f120  mov     ebx, eax
0x18016f122  test    eax, eax
0x18016f124  jns     short loc_18016F15F
0x18016f126  mov     rcx, [rbp+1B8h]; this
0x18016f12d  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18016f134  mov     r9d, eax; char *
0x18016f137  mov     edx, 1D2h; void *
0x18016f13c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f141  mov     rcx, [rsp+2B0h+var_250]
0x18016f146  mov     [rsp+2B0h+var_250], r15
0x18016f14b  test    rcx, rcx
0x18016f14e  jz      loc_18016F0B7
0x18016f154  call    cs:__imp_SRCache_Free
0x18016f15a  jmp     loc_18016F0B7
0x18016f15f  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18016f166  lea     rax, [rsp+2B0h+var_280]
0x18016f16b  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x18016f170  mov     [rsp+2B0h+var_270], rax
0x18016f175  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x18016f17a  mov     [rsp+2B0h+var_280], r15
0x18016f17f  mov     [rsp+2B0h+var_268], r15
0x18016f184  mov     [rsp+2B0h+var_260], 1
0x18016f189  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x18016f18e  lea     rcx, [rsp+2B0h+var_270]
0x18016f193  mov     ebx, eax
0x18016f195  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18016f19a  test    ebx, ebx
0x18016f19c  jns     short loc_18016F1D7
0x18016f19e  mov     edx, 1D4h; void *
0x18016f1a3  mov     rcx, [rbp+1B8h]; this
0x18016f1aa  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18016f1b1  mov     r9d, ebx; char *
0x18016f1b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f1b9  mov     rcx, [rsp+2B0h+var_280]
0x18016f1be  mov     [rsp+2B0h+var_280], r15
0x18016f1c3  test    rcx, rcx
0x18016f1c6  jz      loc_18016F141
0x18016f1cc  call    cs:__imp_SRCache_Free
0x18016f1d2  jmp     loc_18016F141
0x18016f1d7  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18016f1de  lea     rcx, [rsp+2B0h+var_288]; this
0x18016f1e3  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x18016f1e8  mov     ebx, eax
0x18016f1ea  test    eax, eax
0x18016f1ec  jns     short loc_18016F1F5
0x18016f1ee  mov     edx, 1D5h
0x18016f1f3  jmp     short loc_18016F1A3
0x18016f1f5  lea     rdx, aAppurihandlerg_3; "AppUriHandlerGroup\\Data"
0x18016f1fc  lea     rcx, [rsp+2B0h+var_288]; this
0x18016f201  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18016f206  mov     ebx, eax
0x18016f208  test    eax, eax
0x18016f20a  jns     short loc_18016F213
0x18016f20c  mov     edx, 1D7h
0x18016f211  jmp     short loc_18016F1A3
0x18016f213  mov     rcx, [rdi]
0x18016f216  lea     rax, [rsp+2B0h+var_278]
0x18016f21b  lea     r9, [rsp+2B0h+var_268]
0x18016f220  mov     [rsp+2B0h+var_270], rax
0x18016f225  xor     r8d, r8d
0x18016f228  mov     [rsp+2B0h+var_278], r15
0x18016f22d  lea     rdx, aAppurihandlerg_0; "AppUriHandlerGroup\\Index"
0x18016f234  mov     [rsp+2B0h+var_268], r15
0x18016f239  mov     [rsp+2B0h+var_260], 1
0x18016f23e  call    cs:__imp_SRCacheContext_Open
0x18016f244  lea     rcx, [rsp+2B0h+var_270]
0x18016f249  mov     ebx, eax
0x18016f24b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016f250  test    ebx, ebx
0x18016f252  jns     short loc_18016F2A8
0x18016f254  mov     rcx, [rbp+1B8h]; this
0x18016f25b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016f262  mov     r9d, ebx; char *
0x18016f265  mov     edx, 18Ch; void *
0x18016f26a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f26f  mov     edx, 1DBh; void *
0x18016f274  mov     rcx, [rbp+1B8h]; this
0x18016f27b  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18016f282  mov     r9d, ebx; char *
0x18016f285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016f28a  mov     rcx, [rsp+2B0h+var_278]
0x18016f28f  mov     [rsp+2B0h+var_278], r15
0x18016f294  test    rcx, rcx
0x18016f297  jz      loc_18016F1B9
0x18016f29d  call    cs:__imp_SRCacheContext_Close
0x18016f2a3  jmp     loc_18016F1B9
0x18016f2a8  mov     rcx, [rsp+2B0h+var_278]
0x18016f2ad  test    rcx, rcx
0x18016f2b0  setnz   al
0x18016f2b3  test    al, al
0x18016f2b5  jz      short loc_18016F2F6
0x18016f2b7  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x18016f2bc  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18016f2c1  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x18016f2c6  mov     ebx, eax
0x18016f2c8  test    eax, eax
0x18016f2ca  jns     short loc_18016F2D3
0x18016f2cc  mov     edx, 1DEh
0x18016f2d1  jmp     short loc_18016F274
0x18016f2d3  lea     rdx, aAppurihandlerg_0; "AppUriHandlerGroup\\Index"
0x18016f2da  lea     rcx, [rsp+2B0h+var_278]; this
0x18016f2df  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18016f2e4  mov     ebx, eax
0x18016f2e6  test    eax, eax
0x18016f2e8  jns     short loc_18016F2F1
0x18016f2ea  mov     edx, 1DFh
0x18016f2ef  jmp     short loc_18016F274
0x18016f2f1  mov     rcx, [rsp+2B0h+var_278]
0x18016f2f6  mov     [rsp+2B0h+var_278], r15
0x18016f2fb  test    rcx, rcx
0x18016f2fe  jz      short loc_18016F306
0x18016f300  call    cs:__imp_SRCacheContext_Close
0x18016f306  mov     rcx, [rsp+2B0h+var_280]
0x18016f30b  mov     [rsp+2B0h+var_280], r15
0x18016f310  test    rcx, rcx
0x18016f313  jz      short loc_18016F31B
0x18016f315  call    cs:__imp_SRCache_Free
0x18016f31b  mov     rcx, [rsp+2B0h+var_250]
0x18016f320  mov     [rsp+2B0h+var_250], r15
0x18016f325  test    rcx, rcx
0x18016f328  jz      short loc_18016F330
0x18016f32a  call    cs:__imp_SRCache_Free
0x18016f330  mov     rcx, [rsp+2B0h+var_288]
0x18016f335  mov     [rsp+2B0h+var_288], r15
0x18016f33a  test    rcx, rcx
0x18016f33d  jz      short loc_18016F345
0x18016f33f  call    cs:__imp_SRCacheContext_Close
0x18016f345  test    sil, sil
0x18016f348  jz      short loc_18016F36B
0x18016f34a  lea     rdx, aAppurihandlerg_10; "AppUriHandlerGroup"
0x18016f351  lea     rcx, [rsp+2B0h+var_290]; this
0x18016f356  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18016f35b  mov     ebx, eax
0x18016f35d  test    eax, eax
0x18016f35f  jns     short loc_18016F36B
0x18016f361  mov     edx, 1E4h
0x18016f366  jmp     loc_18016EFFE
0x18016f36b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18016f370  mov     qword ptr [rsp+2B0h+var_290], r15
0x18016f375  test    rcx, rcx
0x18016f378  jz      short loc_18016F380
0x18016f37a  call    cs:__imp_SRCacheContext_Close
0x18016f380  xor     eax, eax
0x18016f382  mov     rcx, [rbp+1B0h+var_30]
0x18016f389  xor     rcx, rsp; StackCookie
0x18016f38c  call    __security_check_cookie
0x18016f391  mov     rbx, [rsp+2B0h+arg_10]
0x18016f399  add     rsp, 290h
0x18016f3a0  pop     r15
0x18016f3a2  pop     r14
0x18016f3a4  pop     rdi
0x18016f3a5  pop     rsi
0x18016f3a6  pop     rbp
0x18016f3a7  retn
```
