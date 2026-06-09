# StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x18026ad88`
- end: `0x18026b1c8`
- name: `?Cache_Delete@CacheDynamicAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180201224`

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
- `0x18026ad88`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ae43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026aeea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b0bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b120`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b15f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b19a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026ae43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026aeea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b0bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b120`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b15f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026b19a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026af74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026afec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026b135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026b14a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026af74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026afec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026b135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026b14a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026ade8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026ae8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026b05e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026ade8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026ae8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026b05e`

## string_xrefs

- `0x18026ae05`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18026aea8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18026b07b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18026ae25`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026aec3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026af4d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026afca`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026b09b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandlergroup.cpp`
- `0x18026adc7`: `DynamicAppUriHandlerGroup`
- `0x18026b16a`: `DynamicAppUriHandlerGroup`
- `0x18026ae7a`: `DynamicAppUriHandlerGroup\Data`
- `0x18026b015`: `DynamicAppUriHandlerGroup\Data`
- `0x18026b04d`: `DynamicAppUriHandlerGroup\Index`
- `0x18026b0f3`: `DynamicAppUriHandlerGroup\Index`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheDynamicAppUriHandlerGroup::Cache_Delete(__int64 *a1, __int64 a2)
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
  IndexKeys = SRCacheContext_Open(v4, L"DynamicAppUriHandlerGroup", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
    v6 = 467;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
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
    IndexKeys = SRCacheContext_Open(v9, L"DynamicAppUriHandlerGroup\\Data", 0, &v29);
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
        (void *)0x1D7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
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
        (void *)0x1D9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
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
      v14 = 475;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
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
      v14 = 476;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v25,
                  L"DynamicAppUriHandlerGroup\\Data");
    if ( IndexKeys < 0 )
    {
      v14 = 478;
      goto LABEL_18;
    }
    v16 = *a1;
    v28 = &v27;
    v27 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v16, L"DynamicAppUriHandlerGroup\\Index", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      v17 = 482;
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
        v17 = 485;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v27,
                    L"DynamicAppUriHandlerGroup\\Index");
      if ( IndexKeys < 0 )
      {
        v17 = 486;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandlergroup.cpp",
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
                    L"DynamicAppUriHandlerGroup");
      if ( IndexKeys < 0 )
      {
        v6 = 491;
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
0x18026ad88  mov     [rsp-8+arg_10], rbx
0x18026ad8d  push    rbp
0x18026ad8e  push    rsi
0x18026ad8f  push    rdi
0x18026ad90  push    r14
0x18026ad92  push    r15
0x18026ad94  lea     rbp, [rsp-190h]
0x18026ad9c  sub     rsp, 290h
0x18026ada3  mov     rax, cs:__security_cookie
0x18026adaa  xor     rax, rsp
0x18026adad  mov     [rbp+1B0h+var_30], rax
0x18026adb4  mov     r14, rdx
0x18026adb7  mov     [rsp+2B0h+var_260], 1
0x18026adbc  mov     rdi, rcx
0x18026adbf  lea     rax, [rsp+2B0h+var_290]
0x18026adc4  mov     rcx, [rcx]
0x18026adc7  lea     rdx, aDynamicappurih_10; "DynamicAppUriHandlerGroup"
0x18026adce  xor     r15d, r15d
0x18026add1  mov     [rsp+2B0h+var_270], rax
0x18026add6  lea     r9, [rsp+2B0h+var_268]
0x18026addb  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18026ade0  xor     r8d, r8d
0x18026ade3  mov     [rsp+2B0h+var_268], r15
0x18026ade8  call    cs:__imp_SRCacheContext_Open
0x18026adee  lea     rcx, [rsp+2B0h+var_270]
0x18026adf3  mov     ebx, eax
0x18026adf5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18026adfa  test    ebx, ebx
0x18026adfc  jns     short loc_18026AE50
0x18026adfe  mov     rcx, [rbp+1B8h]; this
0x18026ae05  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18026ae0c  mov     r9d, ebx; char *
0x18026ae0f  mov     edx, 18Ch; void *
0x18026ae14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ae19  mov     edx, 1D3h; void *
0x18026ae1e  mov     rcx, [rbp+1B8h]; this
0x18026ae25  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026ae2c  mov     r9d, ebx; char *
0x18026ae2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ae34  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18026ae39  mov     qword ptr [rsp+2B0h+var_290], r15
0x18026ae3e  test    rcx, rcx
0x18026ae41  jz      short loc_18026AE49
0x18026ae43  call    cs:__imp_SRCacheContext_Close
0x18026ae49  mov     eax, ebx
0x18026ae4b  jmp     loc_18026B1A2
0x18026ae50  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18026ae55  setnz   al
0x18026ae58  test    al, al
0x18026ae5a  jz      loc_18026B18B
0x18026ae60  mov     rcx, [rdi]
0x18026ae63  lea     rax, [rsp+2B0h+var_288]
0x18026ae68  lea     r9, [rsp+2B0h+var_268]
0x18026ae6d  mov     [rsp+2B0h+var_270], rax
0x18026ae72  xor     r8d, r8d
0x18026ae75  mov     [rsp+2B0h+var_288], r15
0x18026ae7a  lea     rdx, aDynamicappurih_6; "DynamicAppUriHandlerGroup\\Data"
0x18026ae81  mov     [rsp+2B0h+var_268], r15
0x18026ae86  mov     [rsp+2B0h+var_260], 1
0x18026ae8b  call    cs:__imp_SRCacheContext_Open
0x18026ae91  lea     rcx, [rsp+2B0h+var_270]
0x18026ae96  mov     ebx, eax
0x18026ae98  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18026ae9d  test    ebx, ebx
0x18026ae9f  jns     short loc_18026AEF5
0x18026aea1  mov     rcx, [rbp+1B8h]; this
0x18026aea8  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18026aeaf  mov     r9d, ebx; char *
0x18026aeb2  mov     edx, 18Ch; void *
0x18026aeb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026aebc  mov     rcx, [rbp+1B8h]; this
0x18026aec3  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026aeca  mov     r9d, ebx; char *
0x18026aecd  mov     edx, 1D7h; void *
0x18026aed2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026aed7  mov     rcx, [rsp+2B0h+var_288]
0x18026aedc  mov     [rsp+2B0h+var_288], r15
0x18026aee1  test    rcx, rcx
0x18026aee4  jz      loc_18026AE34
0x18026aeea  call    cs:__imp_SRCacheContext_Close
0x18026aef0  jmp     loc_18026AE34
0x18026aef5  cmp     [rsp+2B0h+var_288], r15
0x18026aefa  lea     rcx, [rsp+2B0h+var_248]; void *
0x18026aeff  mov     r8d, 200h; Size
0x18026af05  mov     [rsp+2B0h+var_250], r15
0x18026af0a  setnz   sil
0x18026af0e  xor     edx, edx; Val
0x18026af10  call    memset_0
0x18026af15  lea     rax, [rsp+2B0h+var_248]
0x18026af1a  mov     [rbp+1B0h+var_48], r15
0x18026af21  mov     rdx, r14; unsigned __int64
0x18026af24  mov     [rbp+1B0h+var_38], rax
0x18026af2b  lea     rcx, [rsp+2B0h+var_250]; this
0x18026af30  mov     [rbp+1B0h+var_40], 100h
0x18026af3b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18026af40  mov     ebx, eax
0x18026af42  test    eax, eax
0x18026af44  jns     short loc_18026AF7F
0x18026af46  mov     rcx, [rbp+1B8h]; this
0x18026af4d  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026af54  mov     r9d, eax; char *
0x18026af57  mov     edx, 1D9h; void *
0x18026af5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026af61  mov     rcx, [rsp+2B0h+var_250]
0x18026af66  mov     [rsp+2B0h+var_250], r15
0x18026af6b  test    rcx, rcx
0x18026af6e  jz      loc_18026AED7
0x18026af74  call    cs:__imp_SRCache_Free
0x18026af7a  jmp     loc_18026AED7
0x18026af7f  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18026af86  lea     rax, [rsp+2B0h+var_280]
0x18026af8b  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x18026af90  mov     [rsp+2B0h+var_270], rax
0x18026af95  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x18026af9a  mov     [rsp+2B0h+var_280], r15
0x18026af9f  mov     [rsp+2B0h+var_268], r15
0x18026afa4  mov     [rsp+2B0h+var_260], 1
0x18026afa9  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x18026afae  lea     rcx, [rsp+2B0h+var_270]
0x18026afb3  mov     ebx, eax
0x18026afb5  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18026afba  test    ebx, ebx
0x18026afbc  jns     short loc_18026AFF7
0x18026afbe  mov     edx, 1DBh; void *
0x18026afc3  mov     rcx, [rbp+1B8h]; this
0x18026afca  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026afd1  mov     r9d, ebx; char *
0x18026afd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026afd9  mov     rcx, [rsp+2B0h+var_280]
0x18026afde  mov     [rsp+2B0h+var_280], r15
0x18026afe3  test    rcx, rcx
0x18026afe6  jz      loc_18026AF61
0x18026afec  call    cs:__imp_SRCache_Free
0x18026aff2  jmp     loc_18026AF61
0x18026aff7  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18026affe  lea     rcx, [rsp+2B0h+var_288]; this
0x18026b003  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x18026b008  mov     ebx, eax
0x18026b00a  test    eax, eax
0x18026b00c  jns     short loc_18026B015
0x18026b00e  mov     edx, 1DCh
0x18026b013  jmp     short loc_18026AFC3
0x18026b015  lea     rdx, aDynamicappurih_6; "DynamicAppUriHandlerGroup\\Data"
0x18026b01c  lea     rcx, [rsp+2B0h+var_288]; this
0x18026b021  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18026b026  mov     ebx, eax
0x18026b028  test    eax, eax
0x18026b02a  jns     short loc_18026B033
0x18026b02c  mov     edx, 1DEh
0x18026b031  jmp     short loc_18026AFC3
0x18026b033  mov     rcx, [rdi]
0x18026b036  lea     rax, [rsp+2B0h+var_278]
0x18026b03b  lea     r9, [rsp+2B0h+var_268]
0x18026b040  mov     [rsp+2B0h+var_270], rax
0x18026b045  xor     r8d, r8d
0x18026b048  mov     [rsp+2B0h+var_278], r15
0x18026b04d  lea     rdx, aDynamicappurih_7; "DynamicAppUriHandlerGroup\\Index"
0x18026b054  mov     [rsp+2B0h+var_268], r15
0x18026b059  mov     [rsp+2B0h+var_260], 1
0x18026b05e  call    cs:__imp_SRCacheContext_Open
0x18026b064  lea     rcx, [rsp+2B0h+var_270]
0x18026b069  mov     ebx, eax
0x18026b06b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18026b070  test    ebx, ebx
0x18026b072  jns     short loc_18026B0C8
0x18026b074  mov     rcx, [rbp+1B8h]; this
0x18026b07b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18026b082  mov     r9d, ebx; char *
0x18026b085  mov     edx, 18Ch; void *
0x18026b08a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b08f  mov     edx, 1E2h; void *
0x18026b094  mov     rcx, [rbp+1B8h]; this
0x18026b09b  lea     r8, aOnecoreBaseApp_317; "onecore\\base\\appmodel\\staterepositor"...
0x18026b0a2  mov     r9d, ebx; char *
0x18026b0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b0aa  mov     rcx, [rsp+2B0h+var_278]
0x18026b0af  mov     [rsp+2B0h+var_278], r15
0x18026b0b4  test    rcx, rcx
0x18026b0b7  jz      loc_18026AFD9
0x18026b0bd  call    cs:__imp_SRCacheContext_Close
0x18026b0c3  jmp     loc_18026AFD9
0x18026b0c8  mov     rcx, [rsp+2B0h+var_278]
0x18026b0cd  test    rcx, rcx
0x18026b0d0  setnz   al
0x18026b0d3  test    al, al
0x18026b0d5  jz      short loc_18026B116
0x18026b0d7  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x18026b0dc  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18026b0e1  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x18026b0e6  mov     ebx, eax
0x18026b0e8  test    eax, eax
0x18026b0ea  jns     short loc_18026B0F3
0x18026b0ec  mov     edx, 1E5h
0x18026b0f1  jmp     short loc_18026B094
0x18026b0f3  lea     rdx, aDynamicappurih_7; "DynamicAppUriHandlerGroup\\Index"
0x18026b0fa  lea     rcx, [rsp+2B0h+var_278]; this
0x18026b0ff  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18026b104  mov     ebx, eax
0x18026b106  test    eax, eax
0x18026b108  jns     short loc_18026B111
0x18026b10a  mov     edx, 1E6h
0x18026b10f  jmp     short loc_18026B094
0x18026b111  mov     rcx, [rsp+2B0h+var_278]
0x18026b116  mov     [rsp+2B0h+var_278], r15
0x18026b11b  test    rcx, rcx
0x18026b11e  jz      short loc_18026B126
0x18026b120  call    cs:__imp_SRCacheContext_Close
0x18026b126  mov     rcx, [rsp+2B0h+var_280]
0x18026b12b  mov     [rsp+2B0h+var_280], r15
0x18026b130  test    rcx, rcx
0x18026b133  jz      short loc_18026B13B
0x18026b135  call    cs:__imp_SRCache_Free
0x18026b13b  mov     rcx, [rsp+2B0h+var_250]
0x18026b140  mov     [rsp+2B0h+var_250], r15
0x18026b145  test    rcx, rcx
0x18026b148  jz      short loc_18026B150
0x18026b14a  call    cs:__imp_SRCache_Free
0x18026b150  mov     rcx, [rsp+2B0h+var_288]
0x18026b155  mov     [rsp+2B0h+var_288], r15
0x18026b15a  test    rcx, rcx
0x18026b15d  jz      short loc_18026B165
0x18026b15f  call    cs:__imp_SRCacheContext_Close
0x18026b165  test    sil, sil
0x18026b168  jz      short loc_18026B18B
0x18026b16a  lea     rdx, aDynamicappurih_10; "DynamicAppUriHandlerGroup"
0x18026b171  lea     rcx, [rsp+2B0h+var_290]; this
0x18026b176  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18026b17b  mov     ebx, eax
0x18026b17d  test    eax, eax
0x18026b17f  jns     short loc_18026B18B
0x18026b181  mov     edx, 1EBh
0x18026b186  jmp     loc_18026AE1E
0x18026b18b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18026b190  mov     qword ptr [rsp+2B0h+var_290], r15
0x18026b195  test    rcx, rcx
0x18026b198  jz      short loc_18026B1A0
0x18026b19a  call    cs:__imp_SRCacheContext_Close
0x18026b1a0  xor     eax, eax
0x18026b1a2  mov     rcx, [rbp+1B0h+var_30]
0x18026b1a9  xor     rcx, rsp; StackCookie
0x18026b1ac  call    __security_check_cookie
0x18026b1b1  mov     rbx, [rsp+2B0h+arg_10]
0x18026b1b9  add     rsp, 290h
0x18026b1c0  pop     r15
0x18026b1c2  pop     r14
0x18026b1c4  pop     rdi
0x18026b1c5  pop     rsi
0x18026b1c6  pop     rbp
0x18026b1c7  retn
```
