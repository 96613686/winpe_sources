# StateRepository::Entity::CacheActivation::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x1801535a0`
- end: `0x1801539e0`
- name: `?Cache_Delete@CacheActivation@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1802006e4`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x1801535a0`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015365b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180153702`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801538d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180153938`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180153977`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801539b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015365b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180153702`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801538d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180153938`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180153977`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801539b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015378c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180153804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015394d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180153962`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015378c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180153804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015394d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180153962`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180153600`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801536a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180153876`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180153600`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801536a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180153876`

## string_xrefs

- `0x18015363d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x1801536db`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180153765`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x1801537e2`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x1801538b3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x18015361d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1801536c0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180153893`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheActivation::Cache_Delete(__int64 *a1, __int64 a2)
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
  IndexKeys = SRCacheContext_Open(v4, L"Activation", 0, &v33);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v28[0]);
    v8 = 555;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
    IndexKeys = SRCacheContext_Open(v13, L"Activation\\Data", 0, &v33);
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
        (void *)0x22F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
        (void *)0x231,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
      v18 = 563;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
      v18 = 564;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v29,
                  L"Activation\\Data");
    if ( IndexKeys < 0 )
    {
      v18 = 566;
      goto LABEL_18;
    }
    v20 = *a1;
    v32 = &v31;
    v31 = 0;
    v33 = 0;
    v34 = 1;
    IndexKeys = SRCacheContext_Open(v20, L"Activation\\Index", 0, &v33);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v32);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v28[0]);
      v21 = 570;
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
        v21 = 573;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v31,
                    L"Activation\\Index");
      if ( IndexKeys < 0 )
      {
        v21 = 574;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
                    L"Activation");
      if ( IndexKeys < 0 )
      {
        v8 = 579;
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
0x1801535a0  mov     [rsp-8+arg_10], rbx
0x1801535a5  push    rbp
0x1801535a6  push    rsi
0x1801535a7  push    rdi
0x1801535a8  push    r14
0x1801535aa  push    r15
0x1801535ac  lea     rbp, [rsp-190h]
0x1801535b4  sub     rsp, 290h
0x1801535bb  mov     rax, cs:__security_cookie
0x1801535c2  xor     rax, rsp
0x1801535c5  mov     [rbp+1B0h+var_30], rax
0x1801535cc  mov     r14, rdx
0x1801535cf  mov     [rsp+2B0h+var_260], 1
0x1801535d4  mov     rdi, rcx
0x1801535d7  lea     rax, [rsp+2B0h+var_290]
0x1801535dc  mov     rcx, [rcx]
0x1801535df  lea     rdx, aActivation_0; "Activation"
0x1801535e6  xor     r15d, r15d
0x1801535e9  mov     [rsp+2B0h+var_270], rax
0x1801535ee  lea     r9, [rsp+2B0h+var_268]
0x1801535f3  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1801535f8  xor     r8d, r8d
0x1801535fb  mov     [rsp+2B0h+var_268], r15
0x180153600  call    cs:__imp_SRCacheContext_Open
0x180153606  lea     rcx, [rsp+2B0h+var_270]
0x18015360b  mov     ebx, eax
0x18015360d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180153612  test    ebx, ebx
0x180153614  jns     short loc_180153668
0x180153616  mov     rcx, [rbp+1B8h]; this
0x18015361d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180153624  mov     r9d, ebx; char *
0x180153627  mov     edx, 18Ch; void *
0x18015362c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153631  mov     edx, 22Bh; void *
0x180153636  mov     rcx, [rbp+1B8h]; this
0x18015363d  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180153644  mov     r9d, ebx; char *
0x180153647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015364c  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180153651  mov     qword ptr [rsp+2B0h+var_290], r15
0x180153656  test    rcx, rcx
0x180153659  jz      short loc_180153661
0x18015365b  call    cs:__imp_SRCacheContext_Close
0x180153661  mov     eax, ebx
0x180153663  jmp     loc_1801539BA
0x180153668  cmp     qword ptr [rsp+2B0h+var_290], r15
0x18015366d  setnz   al
0x180153670  test    al, al
0x180153672  jz      loc_1801539A3
0x180153678  mov     rcx, [rdi]
0x18015367b  lea     rax, [rsp+2B0h+var_288]
0x180153680  lea     r9, [rsp+2B0h+var_268]
0x180153685  mov     [rsp+2B0h+var_270], rax
0x18015368a  xor     r8d, r8d
0x18015368d  mov     [rsp+2B0h+var_288], r15
0x180153692  lea     rdx, aActivationData; "Activation\\Data"
0x180153699  mov     [rsp+2B0h+var_268], r15
0x18015369e  mov     [rsp+2B0h+var_260], 1
0x1801536a3  call    cs:__imp_SRCacheContext_Open
0x1801536a9  lea     rcx, [rsp+2B0h+var_270]
0x1801536ae  mov     ebx, eax
0x1801536b0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1801536b5  test    ebx, ebx
0x1801536b7  jns     short loc_18015370D
0x1801536b9  mov     rcx, [rbp+1B8h]; this
0x1801536c0  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1801536c7  mov     r9d, ebx; char *
0x1801536ca  mov     edx, 18Ch; void *
0x1801536cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801536d4  mov     rcx, [rbp+1B8h]; this
0x1801536db  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1801536e2  mov     r9d, ebx; char *
0x1801536e5  mov     edx, 22Fh; void *
0x1801536ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801536ef  mov     rcx, [rsp+2B0h+var_288]
0x1801536f4  mov     [rsp+2B0h+var_288], r15
0x1801536f9  test    rcx, rcx
0x1801536fc  jz      loc_18015364C
0x180153702  call    cs:__imp_SRCacheContext_Close
0x180153708  jmp     loc_18015364C
0x18015370d  cmp     [rsp+2B0h+var_288], r15
0x180153712  lea     rcx, [rsp+2B0h+var_248]; void *
0x180153717  mov     r8d, 200h; Size
0x18015371d  mov     [rsp+2B0h+var_250], r15
0x180153722  setnz   sil
0x180153726  xor     edx, edx; Val
0x180153728  call    memset_0
0x18015372d  lea     rax, [rsp+2B0h+var_248]
0x180153732  mov     [rbp+1B0h+var_48], r15
0x180153739  mov     rdx, r14; unsigned __int64
0x18015373c  mov     [rbp+1B0h+var_38], rax
0x180153743  lea     rcx, [rsp+2B0h+var_250]; this
0x180153748  mov     [rbp+1B0h+var_40], 100h
0x180153753  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180153758  mov     ebx, eax
0x18015375a  test    eax, eax
0x18015375c  jns     short loc_180153797
0x18015375e  mov     rcx, [rbp+1B8h]; this
0x180153765  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x18015376c  mov     r9d, eax; char *
0x18015376f  mov     edx, 231h; void *
0x180153774  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153779  mov     rcx, [rsp+2B0h+var_250]
0x18015377e  mov     [rsp+2B0h+var_250], r15
0x180153783  test    rcx, rcx
0x180153786  jz      loc_1801536EF
0x18015378c  call    cs:__imp_SRCache_Free
0x180153792  jmp     loc_1801536EF
0x180153797  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x18015379e  lea     rax, [rsp+2B0h+var_280]
0x1801537a3  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x1801537a8  mov     [rsp+2B0h+var_270], rax
0x1801537ad  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x1801537b2  mov     [rsp+2B0h+var_280], r15
0x1801537b7  mov     [rsp+2B0h+var_268], r15
0x1801537bc  mov     [rsp+2B0h+var_260], 1
0x1801537c1  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x1801537c6  lea     rcx, [rsp+2B0h+var_270]
0x1801537cb  mov     ebx, eax
0x1801537cd  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1801537d2  test    ebx, ebx
0x1801537d4  jns     short loc_18015380F
0x1801537d6  mov     edx, 233h; void *
0x1801537db  mov     rcx, [rbp+1B8h]; this
0x1801537e2  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1801537e9  mov     r9d, ebx; char *
0x1801537ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801537f1  mov     rcx, [rsp+2B0h+var_280]
0x1801537f6  mov     [rsp+2B0h+var_280], r15
0x1801537fb  test    rcx, rcx
0x1801537fe  jz      loc_180153779
0x180153804  call    cs:__imp_SRCache_Free
0x18015380a  jmp     loc_180153779
0x18015380f  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x180153816  lea     rcx, [rsp+2B0h+var_288]; this
0x18015381b  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x180153820  mov     ebx, eax
0x180153822  test    eax, eax
0x180153824  jns     short loc_18015382D
0x180153826  mov     edx, 234h
0x18015382b  jmp     short loc_1801537DB
0x18015382d  lea     rdx, aActivationData; "Activation\\Data"
0x180153834  lea     rcx, [rsp+2B0h+var_288]; this
0x180153839  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18015383e  mov     ebx, eax
0x180153840  test    eax, eax
0x180153842  jns     short loc_18015384B
0x180153844  mov     edx, 236h
0x180153849  jmp     short loc_1801537DB
0x18015384b  mov     rcx, [rdi]
0x18015384e  lea     rax, [rsp+2B0h+var_278]
0x180153853  lea     r9, [rsp+2B0h+var_268]
0x180153858  mov     [rsp+2B0h+var_270], rax
0x18015385d  xor     r8d, r8d
0x180153860  mov     [rsp+2B0h+var_278], r15
0x180153865  lea     rdx, aActivationInde_0; "Activation\\Index"
0x18015386c  mov     [rsp+2B0h+var_268], r15
0x180153871  mov     [rsp+2B0h+var_260], 1
0x180153876  call    cs:__imp_SRCacheContext_Open
0x18015387c  lea     rcx, [rsp+2B0h+var_270]
0x180153881  mov     ebx, eax
0x180153883  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180153888  test    ebx, ebx
0x18015388a  jns     short loc_1801538E0
0x18015388c  mov     rcx, [rbp+1B8h]; this
0x180153893  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18015389a  mov     r9d, ebx; char *
0x18015389d  mov     edx, 18Ch; void *
0x1801538a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801538a7  mov     edx, 23Ah; void *
0x1801538ac  mov     rcx, [rbp+1B8h]; this
0x1801538b3  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1801538ba  mov     r9d, ebx; char *
0x1801538bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801538c2  mov     rcx, [rsp+2B0h+var_278]
0x1801538c7  mov     [rsp+2B0h+var_278], r15
0x1801538cc  test    rcx, rcx
0x1801538cf  jz      loc_1801537F1
0x1801538d5  call    cs:__imp_SRCacheContext_Close
0x1801538db  jmp     loc_1801537F1
0x1801538e0  mov     rcx, [rsp+2B0h+var_278]
0x1801538e5  test    rcx, rcx
0x1801538e8  setnz   al
0x1801538eb  test    al, al
0x1801538ed  jz      short loc_18015392E
0x1801538ef  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x1801538f4  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x1801538f9  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x1801538fe  mov     ebx, eax
0x180153900  test    eax, eax
0x180153902  jns     short loc_18015390B
0x180153904  mov     edx, 23Dh
0x180153909  jmp     short loc_1801538AC
0x18015390b  lea     rdx, aActivationInde_0; "Activation\\Index"
0x180153912  lea     rcx, [rsp+2B0h+var_278]; this
0x180153917  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18015391c  mov     ebx, eax
0x18015391e  test    eax, eax
0x180153920  jns     short loc_180153929
0x180153922  mov     edx, 23Eh
0x180153927  jmp     short loc_1801538AC
0x180153929  mov     rcx, [rsp+2B0h+var_278]
0x18015392e  mov     [rsp+2B0h+var_278], r15
0x180153933  test    rcx, rcx
0x180153936  jz      short loc_18015393E
0x180153938  call    cs:__imp_SRCacheContext_Close
0x18015393e  mov     rcx, [rsp+2B0h+var_280]
0x180153943  mov     [rsp+2B0h+var_280], r15
0x180153948  test    rcx, rcx
0x18015394b  jz      short loc_180153953
0x18015394d  call    cs:__imp_SRCache_Free
0x180153953  mov     rcx, [rsp+2B0h+var_250]
0x180153958  mov     [rsp+2B0h+var_250], r15
0x18015395d  test    rcx, rcx
0x180153960  jz      short loc_180153968
0x180153962  call    cs:__imp_SRCache_Free
0x180153968  mov     rcx, [rsp+2B0h+var_288]
0x18015396d  mov     [rsp+2B0h+var_288], r15
0x180153972  test    rcx, rcx
0x180153975  jz      short loc_18015397D
0x180153977  call    cs:__imp_SRCacheContext_Close
0x18015397d  test    sil, sil
0x180153980  jz      short loc_1801539A3
0x180153982  lea     rdx, aActivation_0; "Activation"
0x180153989  lea     rcx, [rsp+2B0h+var_290]; this
0x18015398e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180153993  mov     ebx, eax
0x180153995  test    eax, eax
0x180153997  jns     short loc_1801539A3
0x180153999  mov     edx, 243h
0x18015399e  jmp     loc_180153636
0x1801539a3  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1801539a8  mov     qword ptr [rsp+2B0h+var_290], r15
0x1801539ad  test    rcx, rcx
0x1801539b0  jz      short loc_1801539B8
0x1801539b2  call    cs:__imp_SRCacheContext_Close
0x1801539b8  xor     eax, eax
0x1801539ba  mov     rcx, [rbp+1B0h+var_30]
0x1801539c1  xor     rcx, rsp; StackCookie
0x1801539c4  call    __security_check_cookie
0x1801539c9  mov     rbx, [rsp+2B0h+arg_10]
0x1801539d1  add     rsp, 290h
0x1801539d8  pop     r15
0x1801539da  pop     r14
0x1801539dc  pop     rdi
0x1801539dd  pop     rsi
0x1801539de  pop     rbp
0x1801539df  retn
```
