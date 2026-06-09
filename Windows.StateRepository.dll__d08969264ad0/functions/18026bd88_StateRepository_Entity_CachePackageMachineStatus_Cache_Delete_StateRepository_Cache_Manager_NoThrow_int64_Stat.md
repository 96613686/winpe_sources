# StateRepository::Entity::CachePackageMachineStatus::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x18026bd88`
- end: `0x18026c1c8`
- name: `?Cache_Delete@CachePackageMachineStatus@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180201cfc`

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
- `0x18026bd88`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026be43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026beea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c0bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c120`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c15f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c19a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026be43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026beea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c0bd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c120`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c15f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026c19a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bf74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bfec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026c135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026c14a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bf74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026bfec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026c135`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026c14a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026bde8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026be8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026c05e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026bde8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026be8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18026c05e`

## string_xrefs

- `0x18026be05`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18026bea8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18026c07b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18026be25`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bec3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bf4d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026bfca`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`
- `0x18026c09b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagemachinestatus.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageMachineStatus::Cache_Delete(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  int IndexKeys; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  bool v15; // si
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int16 *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v33; // [rsp+48h] [rbp-B8h] BYREF
  char v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v36[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+268h] [rbp+168h]
  __int64 v38; // [rsp+270h] [rbp+170h]
  unsigned __int16 *v39; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v34 = 1;
  v4 = *a1;
  v32 = (__int64 *)v28;
  *(_QWORD *)v28 = 0;
  v33 = 0;
  IndexKeys = SRCacheContext_Open(v4, L"PackageMachineStatus", 0, &v33);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v28[0]);
    v8 = 386;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
      (const char *)(unsigned int)IndexKeys,
      v28[0]);
LABEL_4:
    v11 = *(_QWORD *)v28;
    *(_QWORD *)v28 = 0;
    if ( v11 )
      SRCacheContext_Close(v11, v9, v10);
    return (unsigned int)IndexKeys;
  }
  if ( *(_QWORD *)v28 )
  {
    v13 = *a1;
    v32 = &v29;
    v29 = 0;
    v33 = 0;
    v34 = 1;
    IndexKeys = SRCacheContext_Open(v13, L"PackageMachineStatus\\Data", 0, &v33);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v28[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
        (const char *)(unsigned int)IndexKeys,
        v28[0]);
LABEL_10:
      v14 = v29;
      v29 = 0;
      if ( v14 )
        SRCacheContext_Close(v14, v9, v10);
      goto LABEL_4;
    }
    v35 = 0;
    v15 = v29 != 0;
    memset_0(v36, 0, sizeof(v36));
    v37 = 0;
    v39 = (unsigned __int16 *)v36;
    v38 = 256;
    v16 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v35, a2);
    IndexKeys = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
        (const char *)(unsigned int)v16,
        v28[0]);
LABEL_14:
      v17 = v35;
      v35 = 0;
      if ( v17 )
        SRCache_Free(v17);
      goto LABEL_10;
    }
    v32 = (__int64 *)&v30;
    v30 = 0;
    v33 = 0;
    v34 = 1;
    IndexKeys = StateRepository::CacheManagement::GetIndexKeys(
                  (struct StateRepository::Cache::Context_NoThrow *)&v29,
                  v39,
                  &v33);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v32);
    if ( IndexKeys < 0 )
    {
      v18 = 394;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
        (const char *)(unsigned int)IndexKeys,
        v28[0]);
LABEL_19:
      v19 = v30;
      v30 = 0;
      if ( v19 )
        SRCache_Free(v19);
      goto LABEL_14;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::Delete((StateRepository::Cache::Context_NoThrow *)&v29, v39);
    if ( IndexKeys < 0 )
    {
      v18 = 395;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v29,
                  L"PackageMachineStatus\\Data");
    if ( IndexKeys < 0 )
    {
      v18 = 397;
      goto LABEL_18;
    }
    v20 = *a1;
    v32 = &v31;
    v31 = 0;
    v33 = 0;
    v34 = 1;
    IndexKeys = SRCacheContext_Open(v20, L"PackageMachineStatus\\Index", 0, &v33);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v28[0]);
      v21 = 401;
      goto LABEL_27;
    }
    v23 = v31;
    if ( v31 )
    {
      IndexKeys = StateRepository::CacheManagement::DeleteIndexKeys(
                    (struct StateRepository::Cache::Context_NoThrow *)&v31,
                    v30);
      if ( IndexKeys < 0 )
      {
        v21 = 404;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v31,
                    L"PackageMachineStatus\\Index");
      if ( IndexKeys < 0 )
      {
        v21 = 405;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagemachinestatus.cpp",
          (const char *)(unsigned int)IndexKeys,
          v28[0]);
        v22 = v31;
        v31 = 0;
        if ( v22 )
          SRCacheContext_Close(v22, v9, v10);
        goto LABEL_19;
      }
      v23 = v31;
    }
    v31 = 0;
    if ( v23 )
      SRCacheContext_Close(v23, v6, v7);
    v24 = v30;
    v30 = 0;
    if ( v24 )
      SRCache_Free(v24);
    v25 = v35;
    v35 = 0;
    if ( v25 )
      SRCache_Free(v25);
    v26 = v29;
    v29 = 0;
    if ( v26 )
      SRCacheContext_Close(v26, v6, v7);
    if ( v15 )
    {
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)v28,
                    L"PackageMachineStatus");
      if ( IndexKeys < 0 )
      {
        v8 = 410;
        goto LABEL_3;
      }
    }
  }
  v27 = *(_QWORD *)v28;
  *(_QWORD *)v28 = 0;
  if ( v27 )
    SRCacheContext_Close(v27, v6, v7);
  return 0;
}

```

## disassembly

```asm
0x18026bd88  mov     [rsp-8+arg_10], rbx
0x18026bd8d  push    rbp
0x18026bd8e  push    rsi
0x18026bd8f  push    rdi
0x18026bd90  push    r14
0x18026bd92  push    r15
0x18026bd94  lea     rbp, [rsp-190h]
0x18026bd9c  sub     rsp, 290h
0x18026bda3  mov     rax, cs:__security_cookie
0x18026bdaa  xor     rax, rsp
0x18026bdad  mov     [rbp+1B0h+var_30], rax
0x18026bdb4  mov     r14, rdx
0x18026bdb7  mov     [rsp+2B0h+var_260], 1
0x18026bdbc  mov     rdi, rcx
0x18026bdbf  lea     rax, [rsp+2B0h+var_290]
0x18026bdc4  mov     rcx, [rcx]
0x18026bdc7  lea     rdx, aPackagemachine_7; "PackageMachineStatus"
0x18026bdce  xor     r15d, r15d
0x18026bdd1  mov     [rsp+2B0h+var_270], rax
0x18026bdd6  lea     r9, [rsp+2B0h+var_268]
0x18026bddb  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18026bde0  xor     r8d, r8d
0x18026bde3  mov     [rsp+2B0h+var_268], r15
0x18026bde8  call    cs:__imp_SRCacheContext_Open
0x18026bdee  lea     rcx, [rsp+2B0h+var_270]
0x18026bdf3  mov     ebx, eax
0x18026bdf5  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18026bdfa  test    ebx, ebx
0x18026bdfc  jns     short loc_18026BE50
0x18026bdfe  mov     rcx, [rbp+1B8h]; this
0x18026be05  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18026be0c  mov     r9d, ebx; char *
0x18026be0f  mov     edx, 18Ch; void *
0x18026be14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026be19  mov     edx, 182h; void *
0x18026be1e  mov     rcx, [rbp+1B8h]; this
0x18026be25  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026be2c  mov     r9d, ebx; char *
0x18026be2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026be34  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18026be39  mov     qword ptr [rsp+2B0h+var_290], r15
0x18026be3e  test    rcx, rcx
0x18026be41  jz      short loc_18026BE49
0x18026be43  call    cs:__imp_SRCacheContext_Close
0x18026be49  mov     eax, ebx
0x18026be4b  jmp     loc_18026C1A2
0x18026be50  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18026be55  setnz   al
0x18026be58  test    al, al
0x18026be5a  jz      loc_18026C18B
0x18026be60  mov     rcx, [rdi]
0x18026be63  lea     rax, [rsp+2B0h+var_288]
0x18026be68  lea     r9, [rsp+2B0h+var_268]
0x18026be6d  mov     [rsp+2B0h+var_270], rax
0x18026be72  xor     r8d, r8d
0x18026be75  mov     [rsp+2B0h+var_288], r15
0x18026be7a  lea     rdx, aPackagemachine_8; "PackageMachineStatus\\Data"
0x18026be81  mov     [rsp+2B0h+var_268], r15
0x18026be86  mov     [rsp+2B0h+var_260], 1
0x18026be8b  call    cs:__imp_SRCacheContext_Open
0x18026be91  lea     rcx, [rsp+2B0h+var_270]
0x18026be96  mov     ebx, eax
0x18026be98  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18026be9d  test    ebx, ebx
0x18026be9f  jns     short loc_18026BEF5
0x18026bea1  mov     rcx, [rbp+1B8h]; this
0x18026bea8  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18026beaf  mov     r9d, ebx; char *
0x18026beb2  mov     edx, 18Ch; void *
0x18026beb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bebc  mov     rcx, [rbp+1B8h]; this
0x18026bec3  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026beca  mov     r9d, ebx; char *
0x18026becd  mov     edx, 186h; void *
0x18026bed2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bed7  mov     rcx, [rsp+2B0h+var_288]
0x18026bedc  mov     [rsp+2B0h+var_288], r15
0x18026bee1  test    rcx, rcx
0x18026bee4  jz      loc_18026BE34
0x18026beea  call    cs:__imp_SRCacheContext_Close
0x18026bef0  jmp     loc_18026BE34
0x18026bef5  cmp     [rsp+2B0h+var_288], r15
0x18026befa  lea     rcx, [rsp+2B0h+var_248]; void *
0x18026beff  mov     r8d, 200h; Size
0x18026bf05  mov     [rsp+2B0h+var_250], r15
0x18026bf0a  setnz   sil
0x18026bf0e  xor     edx, edx; Val
0x18026bf10  call    memset_0
0x18026bf15  lea     rax, [rsp+2B0h+var_248]
0x18026bf1a  mov     [rbp+1B0h+var_48], r15
0x18026bf21  mov     rdx, r14; unsigned __int64
0x18026bf24  mov     [rbp+1B0h+var_38], rax
0x18026bf2b  lea     rcx, [rsp+2B0h+var_250]; this
0x18026bf30  mov     [rbp+1B0h+var_40], 100h
0x18026bf3b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18026bf40  mov     ebx, eax
0x18026bf42  test    eax, eax
0x18026bf44  jns     short loc_18026BF7F
0x18026bf46  mov     rcx, [rbp+1B8h]; this
0x18026bf4d  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026bf54  mov     r9d, eax; char *
0x18026bf57  mov     edx, 188h; void *
0x18026bf5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bf61  mov     rcx, [rsp+2B0h+var_250]
0x18026bf66  mov     [rsp+2B0h+var_250], r15
0x18026bf6b  test    rcx, rcx
0x18026bf6e  jz      loc_18026BED7
0x18026bf74  call    cs:__imp_SRCache_Free
0x18026bf7a  jmp     loc_18026BED7
0x18026bf7f  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18026bf86  lea     rax, [rsp+2B0h+var_280]
0x18026bf8b  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x18026bf90  mov     [rsp+2B0h+var_270], rax
0x18026bf95  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x18026bf9a  mov     [rsp+2B0h+var_280], r15
0x18026bf9f  mov     [rsp+2B0h+var_268], r15
0x18026bfa4  mov     [rsp+2B0h+var_260], 1
0x18026bfa9  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x18026bfae  lea     rcx, [rsp+2B0h+var_270]
0x18026bfb3  mov     ebx, eax
0x18026bfb5  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18026bfba  test    ebx, ebx
0x18026bfbc  jns     short loc_18026BFF7
0x18026bfbe  mov     edx, 18Ah; void *
0x18026bfc3  mov     rcx, [rbp+1B8h]; this
0x18026bfca  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026bfd1  mov     r9d, ebx; char *
0x18026bfd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026bfd9  mov     rcx, [rsp+2B0h+var_280]
0x18026bfde  mov     [rsp+2B0h+var_280], r15
0x18026bfe3  test    rcx, rcx
0x18026bfe6  jz      loc_18026BF61
0x18026bfec  call    cs:__imp_SRCache_Free
0x18026bff2  jmp     loc_18026BF61
0x18026bff7  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18026bffe  lea     rcx, [rsp+2B0h+var_288]; this
0x18026c003  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x18026c008  mov     ebx, eax
0x18026c00a  test    eax, eax
0x18026c00c  jns     short loc_18026C015
0x18026c00e  mov     edx, 18Bh
0x18026c013  jmp     short loc_18026BFC3
0x18026c015  lea     rdx, aPackagemachine_8; "PackageMachineStatus\\Data"
0x18026c01c  lea     rcx, [rsp+2B0h+var_288]; this
0x18026c021  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18026c026  mov     ebx, eax
0x18026c028  test    eax, eax
0x18026c02a  jns     short loc_18026C033
0x18026c02c  mov     edx, 18Dh
0x18026c031  jmp     short loc_18026BFC3
0x18026c033  mov     rcx, [rdi]
0x18026c036  lea     rax, [rsp+2B0h+var_278]
0x18026c03b  lea     r9, [rsp+2B0h+var_268]
0x18026c040  mov     [rsp+2B0h+var_270], rax
0x18026c045  xor     r8d, r8d
0x18026c048  mov     [rsp+2B0h+var_278], r15
0x18026c04d  lea     rdx, aPackagemachine_3; "PackageMachineStatus\\Index"
0x18026c054  mov     [rsp+2B0h+var_268], r15
0x18026c059  mov     [rsp+2B0h+var_260], 1
0x18026c05e  call    cs:__imp_SRCacheContext_Open
0x18026c064  lea     rcx, [rsp+2B0h+var_270]
0x18026c069  mov     ebx, eax
0x18026c06b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18026c070  test    ebx, ebx
0x18026c072  jns     short loc_18026C0C8
0x18026c074  mov     rcx, [rbp+1B8h]; this
0x18026c07b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18026c082  mov     r9d, ebx; char *
0x18026c085  mov     edx, 18Ch; void *
0x18026c08a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026c08f  mov     edx, 191h; void *
0x18026c094  mov     rcx, [rbp+1B8h]; this
0x18026c09b  lea     r8, aOnecoreBaseApp_479; "onecore\\base\\appmodel\\staterepositor"...
0x18026c0a2  mov     r9d, ebx; char *
0x18026c0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026c0aa  mov     rcx, [rsp+2B0h+var_278]
0x18026c0af  mov     [rsp+2B0h+var_278], r15
0x18026c0b4  test    rcx, rcx
0x18026c0b7  jz      loc_18026BFD9
0x18026c0bd  call    cs:__imp_SRCacheContext_Close
0x18026c0c3  jmp     loc_18026BFD9
0x18026c0c8  mov     rcx, [rsp+2B0h+var_278]
0x18026c0cd  test    rcx, rcx
0x18026c0d0  setnz   al
0x18026c0d3  test    al, al
0x18026c0d5  jz      short loc_18026C116
0x18026c0d7  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x18026c0dc  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18026c0e1  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x18026c0e6  mov     ebx, eax
0x18026c0e8  test    eax, eax
0x18026c0ea  jns     short loc_18026C0F3
0x18026c0ec  mov     edx, 194h
0x18026c0f1  jmp     short loc_18026C094
0x18026c0f3  lea     rdx, aPackagemachine_3; "PackageMachineStatus\\Index"
0x18026c0fa  lea     rcx, [rsp+2B0h+var_278]; this
0x18026c0ff  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18026c104  mov     ebx, eax
0x18026c106  test    eax, eax
0x18026c108  jns     short loc_18026C111
0x18026c10a  mov     edx, 195h
0x18026c10f  jmp     short loc_18026C094
0x18026c111  mov     rcx, [rsp+2B0h+var_278]
0x18026c116  mov     [rsp+2B0h+var_278], r15
0x18026c11b  test    rcx, rcx
0x18026c11e  jz      short loc_18026C126
0x18026c120  call    cs:__imp_SRCacheContext_Close
0x18026c126  mov     rcx, [rsp+2B0h+var_280]
0x18026c12b  mov     [rsp+2B0h+var_280], r15
0x18026c130  test    rcx, rcx
0x18026c133  jz      short loc_18026C13B
0x18026c135  call    cs:__imp_SRCache_Free
0x18026c13b  mov     rcx, [rsp+2B0h+var_250]
0x18026c140  mov     [rsp+2B0h+var_250], r15
0x18026c145  test    rcx, rcx
0x18026c148  jz      short loc_18026C150
0x18026c14a  call    cs:__imp_SRCache_Free
0x18026c150  mov     rcx, [rsp+2B0h+var_288]
0x18026c155  mov     [rsp+2B0h+var_288], r15
0x18026c15a  test    rcx, rcx
0x18026c15d  jz      short loc_18026C165
0x18026c15f  call    cs:__imp_SRCacheContext_Close
0x18026c165  test    sil, sil
0x18026c168  jz      short loc_18026C18B
0x18026c16a  lea     rdx, aPackagemachine_7; "PackageMachineStatus"
0x18026c171  lea     rcx, [rsp+2B0h+var_290]; this
0x18026c176  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18026c17b  mov     ebx, eax
0x18026c17d  test    eax, eax
0x18026c17f  jns     short loc_18026C18B
0x18026c181  mov     edx, 19Ah
0x18026c186  jmp     loc_18026BE1E
0x18026c18b  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18026c190  mov     qword ptr [rsp+2B0h+var_290], r15
0x18026c195  test    rcx, rcx
0x18026c198  jz      short loc_18026C1A0
0x18026c19a  call    cs:__imp_SRCacheContext_Close
0x18026c1a0  xor     eax, eax
0x18026c1a2  mov     rcx, [rbp+1B0h+var_30]
0x18026c1a9  xor     rcx, rsp; StackCookie
0x18026c1ac  call    __security_check_cookie
0x18026c1b1  mov     rbx, [rsp+2B0h+arg_10]
0x18026c1b9  add     rsp, 290h
0x18026c1c0  pop     r15
0x18026c1c2  pop     r14
0x18026c1c4  pop     rdi
0x18026c1c5  pop     rsi
0x18026c1c6  pop     rbp
0x18026c1c7  retn
```
