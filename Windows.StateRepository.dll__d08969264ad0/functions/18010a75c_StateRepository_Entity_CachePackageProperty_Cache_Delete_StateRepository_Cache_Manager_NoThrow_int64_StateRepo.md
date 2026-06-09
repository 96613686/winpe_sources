# StateRepository::Entity::CachePackageProperty::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x18010a75c`
- end: `0x18010ab9c`
- name: `?Cache_Delete@CachePackageProperty@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180201e60`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x18010a75c`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010a817`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010a8be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010aa91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010aaf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010ab33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010ab6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010a817`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010a8be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010aa91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010aaf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010ab33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18010ab6e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010a948`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010a9c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010ab09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010ab1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010a948`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010a9c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010ab09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18010ab1e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010a7bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010a85f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010aa32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010a7bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010a85f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18010aa32`

## string_xrefs

- `0x18010a7d9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18010a87c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18010aa4f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18010a7f9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x18010a897`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x18010a921`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x18010a99e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x18010aa6f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageProperty::Cache_Delete(__int64 *a1, __int64 a2)
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
  IndexKeys = SRCacheContext_Open(v4, L"PackageProperty", 0, &v33);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v28[0]);
    v8 = 497;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
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
    IndexKeys = SRCacheContext_Open(v13, L"PackageProperty\\Data", 0, &v33);
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
        (void *)0x1F5,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
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
        (void *)0x1F7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
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
      v18 = 505;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
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
      v18 = 506;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v29,
                  L"PackageProperty\\Data");
    if ( IndexKeys < 0 )
    {
      v18 = 508;
      goto LABEL_18;
    }
    v20 = *a1;
    v32 = &v31;
    v31 = 0;
    v33 = 0;
    v34 = 1;
    IndexKeys = SRCacheContext_Open(v20, L"PackageProperty\\Index", 0, &v33);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v28[0]);
      v21 = 512;
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
        v21 = 515;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v31,
                    L"PackageProperty\\Index");
      if ( IndexKeys < 0 )
      {
        v21 = 516;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
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
                    L"PackageProperty");
      if ( IndexKeys < 0 )
      {
        v8 = 521;
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
0x18010a75c  mov     [rsp-8+arg_10], rbx
0x18010a761  push    rbp
0x18010a762  push    rsi
0x18010a763  push    rdi
0x18010a764  push    r14
0x18010a766  push    r15
0x18010a768  lea     rbp, [rsp-190h]
0x18010a770  sub     rsp, 290h
0x18010a777  mov     rax, cs:__security_cookie
0x18010a77e  xor     rax, rsp
0x18010a781  mov     [rbp+1B0h+var_30], rax
0x18010a788  mov     r14, rdx
0x18010a78b  mov     [rsp+2B0h+var_260], 1
0x18010a790  mov     rdi, rcx
0x18010a793  lea     rax, [rsp+2B0h+var_290]
0x18010a798  mov     rcx, [rcx]
0x18010a79b  lea     rdx, aPackagepropert_12; "PackageProperty"
0x18010a7a2  xor     r15d, r15d
0x18010a7a5  mov     [rsp+2B0h+var_270], rax
0x18010a7aa  lea     r9, [rsp+2B0h+var_268]
0x18010a7af  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18010a7b4  xor     r8d, r8d
0x18010a7b7  mov     [rsp+2B0h+var_268], r15
0x18010a7bc  call    cs:__imp_SRCacheContext_Open
0x18010a7c2  lea     rcx, [rsp+2B0h+var_270]
0x18010a7c7  mov     ebx, eax
0x18010a7c9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18010a7ce  test    ebx, ebx
0x18010a7d0  jns     short loc_18010A824
0x18010a7d2  mov     rcx, [rbp+1B8h]; this
0x18010a7d9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18010a7e0  mov     r9d, ebx; char *
0x18010a7e3  mov     edx, 18Ch; void *
0x18010a7e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a7ed  mov     edx, 1F1h; void *
0x18010a7f2  mov     rcx, [rbp+1B8h]; this
0x18010a7f9  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x18010a800  mov     r9d, ebx; char *
0x18010a803  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a808  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18010a80d  mov     qword ptr [rsp+2B0h+var_290], r15
0x18010a812  test    rcx, rcx
0x18010a815  jz      short loc_18010A81D
0x18010a817  call    cs:__imp_SRCacheContext_Close
0x18010a81d  mov     eax, ebx
0x18010a81f  jmp     loc_18010AB76
0x18010a824  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18010a829  setnz   al
0x18010a82c  test    al, al
0x18010a82e  jz      loc_18010AB5F
0x18010a834  mov     rcx, [rdi]
0x18010a837  lea     rax, [rsp+2B0h+var_288]
0x18010a83c  lea     r9, [rsp+2B0h+var_268]
0x18010a841  mov     [rsp+2B0h+var_270], rax
0x18010a846  xor     r8d, r8d
0x18010a849  mov     [rsp+2B0h+var_288], r15
0x18010a84e  lea     rdx, aPackagepropert_7; "PackageProperty\\Data"
0x18010a855  mov     [rsp+2B0h+var_268], r15
0x18010a85a  mov     [rsp+2B0h+var_260], 1
0x18010a85f  call    cs:__imp_SRCacheContext_Open
0x18010a865  lea     rcx, [rsp+2B0h+var_270]
0x18010a86a  mov     ebx, eax
0x18010a86c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18010a871  test    ebx, ebx
0x18010a873  jns     short loc_18010A8C9
0x18010a875  mov     rcx, [rbp+1B8h]; this
0x18010a87c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18010a883  mov     r9d, ebx; char *
0x18010a886  mov     edx, 18Ch; void *
0x18010a88b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a890  mov     rcx, [rbp+1B8h]; this
0x18010a897  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x18010a89e  mov     r9d, ebx; char *
0x18010a8a1  mov     edx, 1F5h; void *
0x18010a8a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a8ab  mov     rcx, [rsp+2B0h+var_288]
0x18010a8b0  mov     [rsp+2B0h+var_288], r15
0x18010a8b5  test    rcx, rcx
0x18010a8b8  jz      loc_18010A808
0x18010a8be  call    cs:__imp_SRCacheContext_Close
0x18010a8c4  jmp     loc_18010A808
0x18010a8c9  cmp     [rsp+2B0h+var_288], r15
0x18010a8ce  lea     rcx, [rsp+2B0h+var_248]; void *
0x18010a8d3  mov     r8d, 200h; Size
0x18010a8d9  mov     [rsp+2B0h+var_250], r15
0x18010a8de  setnz   sil
0x18010a8e2  xor     edx, edx; Val
0x18010a8e4  call    memset_0
0x18010a8e9  lea     rax, [rsp+2B0h+var_248]
0x18010a8ee  mov     [rbp+1B0h+var_48], r15
0x18010a8f5  mov     rdx, r14; unsigned __int64
0x18010a8f8  mov     [rbp+1B0h+var_38], rax
0x18010a8ff  lea     rcx, [rsp+2B0h+var_250]; this
0x18010a904  mov     [rbp+1B0h+var_40], 100h
0x18010a90f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18010a914  mov     ebx, eax
0x18010a916  test    eax, eax
0x18010a918  jns     short loc_18010A953
0x18010a91a  mov     rcx, [rbp+1B8h]; this
0x18010a921  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x18010a928  mov     r9d, eax; char *
0x18010a92b  mov     edx, 1F7h; void *
0x18010a930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a935  mov     rcx, [rsp+2B0h+var_250]
0x18010a93a  mov     [rsp+2B0h+var_250], r15
0x18010a93f  test    rcx, rcx
0x18010a942  jz      loc_18010A8AB
0x18010a948  call    cs:__imp_SRCache_Free
0x18010a94e  jmp     loc_18010A8AB
0x18010a953  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18010a95a  lea     rax, [rsp+2B0h+var_280]
0x18010a95f  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x18010a964  mov     [rsp+2B0h+var_270], rax
0x18010a969  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x18010a96e  mov     [rsp+2B0h+var_280], r15
0x18010a973  mov     [rsp+2B0h+var_268], r15
0x18010a978  mov     [rsp+2B0h+var_260], 1
0x18010a97d  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x18010a982  lea     rcx, [rsp+2B0h+var_270]
0x18010a987  mov     ebx, eax
0x18010a989  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18010a98e  test    ebx, ebx
0x18010a990  jns     short loc_18010A9CB
0x18010a992  mov     edx, 1F9h; void *
0x18010a997  mov     rcx, [rbp+1B8h]; this
0x18010a99e  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x18010a9a5  mov     r9d, ebx; char *
0x18010a9a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a9ad  mov     rcx, [rsp+2B0h+var_280]
0x18010a9b2  mov     [rsp+2B0h+var_280], r15
0x18010a9b7  test    rcx, rcx
0x18010a9ba  jz      loc_18010A935
0x18010a9c0  call    cs:__imp_SRCache_Free
0x18010a9c6  jmp     loc_18010A935
0x18010a9cb  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18010a9d2  lea     rcx, [rsp+2B0h+var_288]; this
0x18010a9d7  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x18010a9dc  mov     ebx, eax
0x18010a9de  test    eax, eax
0x18010a9e0  jns     short loc_18010A9E9
0x18010a9e2  mov     edx, 1FAh
0x18010a9e7  jmp     short loc_18010A997
0x18010a9e9  lea     rdx, aPackagepropert_7; "PackageProperty\\Data"
0x18010a9f0  lea     rcx, [rsp+2B0h+var_288]; this
0x18010a9f5  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18010a9fa  mov     ebx, eax
0x18010a9fc  test    eax, eax
0x18010a9fe  jns     short loc_18010AA07
0x18010aa00  mov     edx, 1FCh
0x18010aa05  jmp     short loc_18010A997
0x18010aa07  mov     rcx, [rdi]
0x18010aa0a  lea     rax, [rsp+2B0h+var_278]
0x18010aa0f  lea     r9, [rsp+2B0h+var_268]
0x18010aa14  mov     [rsp+2B0h+var_270], rax
0x18010aa19  xor     r8d, r8d
0x18010aa1c  mov     [rsp+2B0h+var_278], r15
0x18010aa21  lea     rdx, aPackagepropert_15; "PackageProperty\\Index"
0x18010aa28  mov     [rsp+2B0h+var_268], r15
0x18010aa2d  mov     [rsp+2B0h+var_260], 1
0x18010aa32  call    cs:__imp_SRCacheContext_Open
0x18010aa38  lea     rcx, [rsp+2B0h+var_270]
0x18010aa3d  mov     ebx, eax
0x18010aa3f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18010aa44  test    ebx, ebx
0x18010aa46  jns     short loc_18010AA9C
0x18010aa48  mov     rcx, [rbp+1B8h]; this
0x18010aa4f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18010aa56  mov     r9d, ebx; char *
0x18010aa59  mov     edx, 18Ch; void *
0x18010aa5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010aa63  mov     edx, 200h; void *
0x18010aa68  mov     rcx, [rbp+1B8h]; this
0x18010aa6f  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x18010aa76  mov     r9d, ebx; char *
0x18010aa79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010aa7e  mov     rcx, [rsp+2B0h+var_278]
0x18010aa83  mov     [rsp+2B0h+var_278], r15
0x18010aa88  test    rcx, rcx
0x18010aa8b  jz      loc_18010A9AD
0x18010aa91  call    cs:__imp_SRCacheContext_Close
0x18010aa97  jmp     loc_18010A9AD
0x18010aa9c  mov     rcx, [rsp+2B0h+var_278]
0x18010aaa1  test    rcx, rcx
0x18010aaa4  setnz   al
0x18010aaa7  test    al, al
0x18010aaa9  jz      short loc_18010AAEA
0x18010aaab  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x18010aab0  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18010aab5  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x18010aaba  mov     ebx, eax
0x18010aabc  test    eax, eax
0x18010aabe  jns     short loc_18010AAC7
0x18010aac0  mov     edx, 203h
0x18010aac5  jmp     short loc_18010AA68
0x18010aac7  lea     rdx, aPackagepropert_15; "PackageProperty\\Index"
0x18010aace  lea     rcx, [rsp+2B0h+var_278]; this
0x18010aad3  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18010aad8  mov     ebx, eax
0x18010aada  test    eax, eax
0x18010aadc  jns     short loc_18010AAE5
0x18010aade  mov     edx, 204h
0x18010aae3  jmp     short loc_18010AA68
0x18010aae5  mov     rcx, [rsp+2B0h+var_278]
0x18010aaea  mov     [rsp+2B0h+var_278], r15
0x18010aaef  test    rcx, rcx
0x18010aaf2  jz      short loc_18010AAFA
0x18010aaf4  call    cs:__imp_SRCacheContext_Close
0x18010aafa  mov     rcx, [rsp+2B0h+var_280]
0x18010aaff  mov     [rsp+2B0h+var_280], r15
0x18010ab04  test    rcx, rcx
0x18010ab07  jz      short loc_18010AB0F
0x18010ab09  call    cs:__imp_SRCache_Free
0x18010ab0f  mov     rcx, [rsp+2B0h+var_250]
0x18010ab14  mov     [rsp+2B0h+var_250], r15
0x18010ab19  test    rcx, rcx
0x18010ab1c  jz      short loc_18010AB24
0x18010ab1e  call    cs:__imp_SRCache_Free
0x18010ab24  mov     rcx, [rsp+2B0h+var_288]
0x18010ab29  mov     [rsp+2B0h+var_288], r15
0x18010ab2e  test    rcx, rcx
0x18010ab31  jz      short loc_18010AB39
0x18010ab33  call    cs:__imp_SRCacheContext_Close
0x18010ab39  test    sil, sil
0x18010ab3c  jz      short loc_18010AB5F
0x18010ab3e  lea     rdx, aPackagepropert_12; "PackageProperty"
0x18010ab45  lea     rcx, [rsp+2B0h+var_290]; this
0x18010ab4a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18010ab4f  mov     ebx, eax
0x18010ab51  test    eax, eax
0x18010ab53  jns     short loc_18010AB5F
0x18010ab55  mov     edx, 209h
0x18010ab5a  jmp     loc_18010A7F2
0x18010ab5f  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18010ab64  mov     qword ptr [rsp+2B0h+var_290], r15
0x18010ab69  test    rcx, rcx
0x18010ab6c  jz      short loc_18010AB74
0x18010ab6e  call    cs:__imp_SRCacheContext_Close
0x18010ab74  xor     eax, eax
0x18010ab76  mov     rcx, [rbp+1B0h+var_30]
0x18010ab7d  xor     rcx, rsp; StackCookie
0x18010ab80  call    __security_check_cookie
0x18010ab85  mov     rbx, [rsp+2B0h+arg_10]
0x18010ab8d  add     rsp, 290h
0x18010ab94  pop     r15
0x18010ab96  pop     r14
0x18010ab98  pop     rdi
0x18010ab99  pop     rsi
0x18010ab9a  pop     rbp
0x18010ab9b  retn
```
