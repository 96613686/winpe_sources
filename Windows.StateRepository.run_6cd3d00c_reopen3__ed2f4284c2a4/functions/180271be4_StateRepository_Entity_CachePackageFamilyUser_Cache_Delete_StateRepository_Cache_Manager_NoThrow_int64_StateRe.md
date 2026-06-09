# StateRepository::Entity::CachePackageFamilyUser::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x180271be4`
- end: `0x180272024`
- name: `?Cache_Delete@CachePackageFamilyUser@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180201bc4`

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
- `0x180271be4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271c9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271d46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271f19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271f7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271fbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271ff6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271c9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271d46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271f19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271f7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271fbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180271ff6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271dd0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271e48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271f91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271fa6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271dd0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271e48`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271f91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180271fa6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180271c44`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180271ce7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180271eba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180271c44`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180271ce7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180271eba`

## string_xrefs

- `0x180271c61`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180271d04`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180271ed7`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180271c81`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x180271d1f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x180271da9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x180271e26`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`
- `0x180271ef7`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamilyuser.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageFamilyUser::Cache_Delete(__int64 *a1, unsigned __int64 a2)
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
  IndexKeys = SRCacheContext_Open(v4, L"PackageFamilyUser", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
    v6 = 477;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
    IndexKeys = SRCacheContext_Open(v9, L"PackageFamilyUser\\Data", 0, &v29);
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
        (void *)0x1E1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
        (void *)0x1E3,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
      v14 = 485;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
      v14 = 486;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v25,
                  L"PackageFamilyUser\\Data");
    if ( IndexKeys < 0 )
    {
      v14 = 488;
      goto LABEL_18;
    }
    v16 = *a1;
    v28 = &v27;
    v27 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v16, L"PackageFamilyUser\\Index", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      v17 = 492;
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
        v17 = 495;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v27,
                    L"PackageFamilyUser\\Index");
      if ( IndexKeys < 0 )
      {
        v17 = 496;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamilyuser.cpp",
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
                    L"PackageFamilyUser");
      if ( IndexKeys < 0 )
      {
        v6 = 501;
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
0x180271be4  mov     [rsp-8+arg_10], rbx
0x180271be9  push    rbp
0x180271bea  push    rsi
0x180271beb  push    rdi
0x180271bec  push    r14
0x180271bee  push    r15
0x180271bf0  lea     rbp, [rsp-190h]
0x180271bf8  sub     rsp, 290h
0x180271bff  mov     rax, cs:__security_cookie
0x180271c06  xor     rax, rsp
0x180271c09  mov     [rbp+1B0h+var_30], rax
0x180271c10  mov     r14, rdx
0x180271c13  mov     [rsp+2B0h+var_260], 1
0x180271c18  mov     rdi, rcx
0x180271c1b  lea     rax, [rsp+2B0h+var_290]
0x180271c20  mov     rcx, [rcx]
0x180271c23  lea     rdx, aPackagefamilyu_10; "PackageFamilyUser"
0x180271c2a  xor     r15d, r15d
0x180271c2d  mov     [rsp+2B0h+var_270], rax
0x180271c32  lea     r9, [rsp+2B0h+var_268]
0x180271c37  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x180271c3c  xor     r8d, r8d
0x180271c3f  mov     [rsp+2B0h+var_268], r15
0x180271c44  call    cs:__imp_SRCacheContext_Open
0x180271c4a  lea     rcx, [rsp+2B0h+var_270]
0x180271c4f  mov     ebx, eax
0x180271c51  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180271c56  test    ebx, ebx
0x180271c58  jns     short loc_180271CAC
0x180271c5a  mov     rcx, [rbp+1B8h]; this
0x180271c61  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180271c68  mov     r9d, ebx; char *
0x180271c6b  mov     edx, 18Ch; void *
0x180271c70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271c75  mov     edx, 1DDh; void *
0x180271c7a  mov     rcx, [rbp+1B8h]; this
0x180271c81  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180271c88  mov     r9d, ebx; char *
0x180271c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271c90  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180271c95  mov     qword ptr [rsp+2B0h+var_290], r15
0x180271c9a  test    rcx, rcx
0x180271c9d  jz      short loc_180271CA5
0x180271c9f  call    cs:__imp_SRCacheContext_Close
0x180271ca5  mov     eax, ebx
0x180271ca7  jmp     loc_180271FFE
0x180271cac  cmp     qword ptr [rsp+2B0h+var_290], r15
0x180271cb1  setnz   al
0x180271cb4  test    al, al
0x180271cb6  jz      loc_180271FE7
0x180271cbc  mov     rcx, [rdi]
0x180271cbf  lea     rax, [rsp+2B0h+var_288]
0x180271cc4  lea     r9, [rsp+2B0h+var_268]
0x180271cc9  mov     [rsp+2B0h+var_270], rax
0x180271cce  xor     r8d, r8d
0x180271cd1  mov     [rsp+2B0h+var_288], r15
0x180271cd6  lea     rdx, aPackagefamilyu_6; "PackageFamilyUser\\Data"
0x180271cdd  mov     [rsp+2B0h+var_268], r15
0x180271ce2  mov     [rsp+2B0h+var_260], 1
0x180271ce7  call    cs:__imp_SRCacheContext_Open
0x180271ced  lea     rcx, [rsp+2B0h+var_270]
0x180271cf2  mov     ebx, eax
0x180271cf4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180271cf9  test    ebx, ebx
0x180271cfb  jns     short loc_180271D51
0x180271cfd  mov     rcx, [rbp+1B8h]; this
0x180271d04  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180271d0b  mov     r9d, ebx; char *
0x180271d0e  mov     edx, 18Ch; void *
0x180271d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271d18  mov     rcx, [rbp+1B8h]; this
0x180271d1f  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180271d26  mov     r9d, ebx; char *
0x180271d29  mov     edx, 1E1h; void *
0x180271d2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271d33  mov     rcx, [rsp+2B0h+var_288]
0x180271d38  mov     [rsp+2B0h+var_288], r15
0x180271d3d  test    rcx, rcx
0x180271d40  jz      loc_180271C90
0x180271d46  call    cs:__imp_SRCacheContext_Close
0x180271d4c  jmp     loc_180271C90
0x180271d51  cmp     [rsp+2B0h+var_288], r15
0x180271d56  lea     rcx, [rsp+2B0h+var_248]; void *
0x180271d5b  mov     r8d, 200h; Size
0x180271d61  mov     [rsp+2B0h+var_250], r15
0x180271d66  setnz   sil
0x180271d6a  xor     edx, edx; Val
0x180271d6c  call    memset_0
0x180271d71  lea     rax, [rsp+2B0h+var_248]
0x180271d76  mov     [rbp+1B0h+var_48], r15
0x180271d7d  mov     rdx, r14; unsigned __int64
0x180271d80  mov     [rbp+1B0h+var_38], rax
0x180271d87  lea     rcx, [rsp+2B0h+var_250]; this
0x180271d8c  mov     [rbp+1B0h+var_40], 100h
0x180271d97  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180271d9c  mov     ebx, eax
0x180271d9e  test    eax, eax
0x180271da0  jns     short loc_180271DDB
0x180271da2  mov     rcx, [rbp+1B8h]; this
0x180271da9  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180271db0  mov     r9d, eax; char *
0x180271db3  mov     edx, 1E3h; void *
0x180271db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271dbd  mov     rcx, [rsp+2B0h+var_250]
0x180271dc2  mov     [rsp+2B0h+var_250], r15
0x180271dc7  test    rcx, rcx
0x180271dca  jz      loc_180271D33
0x180271dd0  call    cs:__imp_SRCache_Free
0x180271dd6  jmp     loc_180271D33
0x180271ddb  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x180271de2  lea     rax, [rsp+2B0h+var_280]
0x180271de7  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x180271dec  mov     [rsp+2B0h+var_270], rax
0x180271df1  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x180271df6  mov     [rsp+2B0h+var_280], r15
0x180271dfb  mov     [rsp+2B0h+var_268], r15
0x180271e00  mov     [rsp+2B0h+var_260], 1
0x180271e05  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x180271e0a  lea     rcx, [rsp+2B0h+var_270]
0x180271e0f  mov     ebx, eax
0x180271e11  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180271e16  test    ebx, ebx
0x180271e18  jns     short loc_180271E53
0x180271e1a  mov     edx, 1E5h; void *
0x180271e1f  mov     rcx, [rbp+1B8h]; this
0x180271e26  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180271e2d  mov     r9d, ebx; char *
0x180271e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271e35  mov     rcx, [rsp+2B0h+var_280]
0x180271e3a  mov     [rsp+2B0h+var_280], r15
0x180271e3f  test    rcx, rcx
0x180271e42  jz      loc_180271DBD
0x180271e48  call    cs:__imp_SRCache_Free
0x180271e4e  jmp     loc_180271DBD
0x180271e53  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x180271e5a  lea     rcx, [rsp+2B0h+var_288]; this
0x180271e5f  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x180271e64  mov     ebx, eax
0x180271e66  test    eax, eax
0x180271e68  jns     short loc_180271E71
0x180271e6a  mov     edx, 1E6h
0x180271e6f  jmp     short loc_180271E1F
0x180271e71  lea     rdx, aPackagefamilyu_6; "PackageFamilyUser\\Data"
0x180271e78  lea     rcx, [rsp+2B0h+var_288]; this
0x180271e7d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180271e82  mov     ebx, eax
0x180271e84  test    eax, eax
0x180271e86  jns     short loc_180271E8F
0x180271e88  mov     edx, 1E8h
0x180271e8d  jmp     short loc_180271E1F
0x180271e8f  mov     rcx, [rdi]
0x180271e92  lea     rax, [rsp+2B0h+var_278]
0x180271e97  lea     r9, [rsp+2B0h+var_268]
0x180271e9c  mov     [rsp+2B0h+var_270], rax
0x180271ea1  xor     r8d, r8d
0x180271ea4  mov     [rsp+2B0h+var_278], r15
0x180271ea9  lea     rdx, aPackagefamilyu_12; "PackageFamilyUser\\Index"
0x180271eb0  mov     [rsp+2B0h+var_268], r15
0x180271eb5  mov     [rsp+2B0h+var_260], 1
0x180271eba  call    cs:__imp_SRCacheContext_Open
0x180271ec0  lea     rcx, [rsp+2B0h+var_270]
0x180271ec5  mov     ebx, eax
0x180271ec7  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180271ecc  test    ebx, ebx
0x180271ece  jns     short loc_180271F24
0x180271ed0  mov     rcx, [rbp+1B8h]; this
0x180271ed7  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180271ede  mov     r9d, ebx; char *
0x180271ee1  mov     edx, 18Ch; void *
0x180271ee6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271eeb  mov     edx, 1ECh; void *
0x180271ef0  mov     rcx, [rbp+1B8h]; this
0x180271ef7  lea     r8, aOnecoreBaseApp_472; "onecore\\base\\appmodel\\staterepositor"...
0x180271efe  mov     r9d, ebx; char *
0x180271f01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180271f06  mov     rcx, [rsp+2B0h+var_278]
0x180271f0b  mov     [rsp+2B0h+var_278], r15
0x180271f10  test    rcx, rcx
0x180271f13  jz      loc_180271E35
0x180271f19  call    cs:__imp_SRCacheContext_Close
0x180271f1f  jmp     loc_180271E35
0x180271f24  mov     rcx, [rsp+2B0h+var_278]
0x180271f29  test    rcx, rcx
0x180271f2c  setnz   al
0x180271f2f  test    al, al
0x180271f31  jz      short loc_180271F72
0x180271f33  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x180271f38  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x180271f3d  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x180271f42  mov     ebx, eax
0x180271f44  test    eax, eax
0x180271f46  jns     short loc_180271F4F
0x180271f48  mov     edx, 1EFh
0x180271f4d  jmp     short loc_180271EF0
0x180271f4f  lea     rdx, aPackagefamilyu_12; "PackageFamilyUser\\Index"
0x180271f56  lea     rcx, [rsp+2B0h+var_278]; this
0x180271f5b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180271f60  mov     ebx, eax
0x180271f62  test    eax, eax
0x180271f64  jns     short loc_180271F6D
0x180271f66  mov     edx, 1F0h
0x180271f6b  jmp     short loc_180271EF0
0x180271f6d  mov     rcx, [rsp+2B0h+var_278]
0x180271f72  mov     [rsp+2B0h+var_278], r15
0x180271f77  test    rcx, rcx
0x180271f7a  jz      short loc_180271F82
0x180271f7c  call    cs:__imp_SRCacheContext_Close
0x180271f82  mov     rcx, [rsp+2B0h+var_280]
0x180271f87  mov     [rsp+2B0h+var_280], r15
0x180271f8c  test    rcx, rcx
0x180271f8f  jz      short loc_180271F97
0x180271f91  call    cs:__imp_SRCache_Free
0x180271f97  mov     rcx, [rsp+2B0h+var_250]
0x180271f9c  mov     [rsp+2B0h+var_250], r15
0x180271fa1  test    rcx, rcx
0x180271fa4  jz      short loc_180271FAC
0x180271fa6  call    cs:__imp_SRCache_Free
0x180271fac  mov     rcx, [rsp+2B0h+var_288]
0x180271fb1  mov     [rsp+2B0h+var_288], r15
0x180271fb6  test    rcx, rcx
0x180271fb9  jz      short loc_180271FC1
0x180271fbb  call    cs:__imp_SRCacheContext_Close
0x180271fc1  test    sil, sil
0x180271fc4  jz      short loc_180271FE7
0x180271fc6  lea     rdx, aPackagefamilyu_10; "PackageFamilyUser"
0x180271fcd  lea     rcx, [rsp+2B0h+var_290]; this
0x180271fd2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180271fd7  mov     ebx, eax
0x180271fd9  test    eax, eax
0x180271fdb  jns     short loc_180271FE7
0x180271fdd  mov     edx, 1F5h
0x180271fe2  jmp     loc_180271C7A
0x180271fe7  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180271fec  mov     qword ptr [rsp+2B0h+var_290], r15
0x180271ff1  test    rcx, rcx
0x180271ff4  jz      short loc_180271FFC
0x180271ff6  call    cs:__imp_SRCacheContext_Close
0x180271ffc  xor     eax, eax
0x180271ffe  mov     rcx, [rbp+1B0h+var_30]
0x180272005  xor     rcx, rsp; StackCookie
0x180272008  call    __security_check_cookie
0x18027200d  mov     rbx, [rsp+2B0h+arg_10]
0x180272015  add     rsp, 290h
0x18027201c  pop     r15
0x18027201e  pop     r14
0x180272020  pop     rdi
0x180272021  pop     rsi
0x180272022  pop     rbp
0x180272023  retn
```
