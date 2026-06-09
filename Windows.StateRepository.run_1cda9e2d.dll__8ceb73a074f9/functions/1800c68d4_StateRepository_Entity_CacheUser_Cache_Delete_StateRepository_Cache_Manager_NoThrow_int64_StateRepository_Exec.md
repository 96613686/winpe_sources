# StateRepository::Entity::CacheUser::Cache_Delete(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::ExecutionFlags)

- ea: `0x1800c68d4`
- end: `0x1800c6d14`
- name: `?Cache_Delete@CacheUser@Entity@StateRepository@@SAJAEAVManager_NoThrow@Cache@3@_JW4ExecutionFlags@3@@Z`
- size: `1088`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180202408`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x18005b694`
- `0x18005b7c4`
- `0x180074eb0`
- `0x18007b950`
- `0x1800830fc`
- `0x18008bec0`
- `0x1800c68d4`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c698f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6a36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6c09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6c6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6cab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6ce6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c698f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6a36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6c09`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6c6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6cab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c6ce6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6ac0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6b38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6c81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6c96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6ac0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6b38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6c81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c6c96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c6934`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c69d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c6baa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c6934`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c69d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c6baa`

## string_xrefs

- `0x1800c6951`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c69f4`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c6bc7`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c6971`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x1800c6a0f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x1800c6a99`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x1800c6b16`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`
- `0x1800c6be7`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheuser.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheUser::Cache_Delete(__int64 *a1, __int64 a2)
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
  IndexKeys = SRCacheContext_Open(v4, L"User", 0, &v29);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
  if ( IndexKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)IndexKeys,
      v24[0]);
    v6 = 324;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
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
    IndexKeys = SRCacheContext_Open(v9, L"User\\Data", 0, &v29);
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
        (void *)0x148,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
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
        (void *)0x14A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
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
      v14 = 332;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
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
      v14 = 333;
      goto LABEL_18;
    }
    IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                  (StateRepository::Cache::Context_NoThrow *)&v25,
                  L"User\\Data");
    if ( IndexKeys < 0 )
    {
      v14 = 335;
      goto LABEL_18;
    }
    v16 = *a1;
    v28 = &v27;
    v27 = 0;
    v29 = 0;
    v30 = 1;
    IndexKeys = SRCacheContext_Open(v16, L"User\\Index", 0, &v29);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v28);
    if ( IndexKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)IndexKeys,
        v24[0]);
      v17 = 339;
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
        v17 = 342;
        goto LABEL_27;
      }
      IndexKeys = StateRepository::Cache::Context_NoThrow::AddToCache(
                    (StateRepository::Cache::Context_NoThrow *)&v27,
                    L"User\\Index");
      if ( IndexKeys < 0 )
      {
        v17 = 343;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheuser.cpp",
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
                    L"User");
      if ( IndexKeys < 0 )
      {
        v6 = 348;
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
0x1800c68d4  mov     [rsp-8+arg_10], rbx
0x1800c68d9  push    rbp
0x1800c68da  push    rsi
0x1800c68db  push    rdi
0x1800c68dc  push    r14
0x1800c68de  push    r15
0x1800c68e0  lea     rbp, [rsp-190h]
0x1800c68e8  sub     rsp, 290h
0x1800c68ef  mov     rax, cs:__security_cookie
0x1800c68f6  xor     rax, rsp
0x1800c68f9  mov     [rbp+1B0h+var_30], rax
0x1800c6900  mov     r14, rdx
0x1800c6903  mov     [rsp+2B0h+var_260], 1
0x1800c6908  mov     rdi, rcx
0x1800c690b  lea     rax, [rsp+2B0h+var_290]
0x1800c6910  mov     rcx, [rcx]
0x1800c6913  lea     rdx, aUser_0; "User"
0x1800c691a  xor     r15d, r15d
0x1800c691d  mov     [rsp+2B0h+var_270], rax
0x1800c6922  lea     r9, [rsp+2B0h+var_268]
0x1800c6927  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x1800c692c  xor     r8d, r8d
0x1800c692f  mov     [rsp+2B0h+var_268], r15
0x1800c6934  call    cs:__imp_SRCacheContext_Open
0x1800c693a  lea     rcx, [rsp+2B0h+var_270]
0x1800c693f  mov     ebx, eax
0x1800c6941  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c6946  test    ebx, ebx
0x1800c6948  jns     short loc_1800C699C
0x1800c694a  mov     rcx, [rbp+1B8h]; this
0x1800c6951  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c6958  mov     r9d, ebx; char *
0x1800c695b  mov     edx, 18Ch; void *
0x1800c6960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6965  mov     edx, 144h; void *
0x1800c696a  mov     rcx, [rbp+1B8h]; this
0x1800c6971  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x1800c6978  mov     r9d, ebx; char *
0x1800c697b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6980  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800c6985  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800c698a  test    rcx, rcx
0x1800c698d  jz      short loc_1800C6995
0x1800c698f  call    cs:__imp_SRCacheContext_Close
0x1800c6995  mov     eax, ebx
0x1800c6997  jmp     loc_1800C6CEE
0x1800c699c  cmp     qword ptr [rsp+2B0h+var_290], r15
0x1800c69a1  setnz   al
0x1800c69a4  test    al, al
0x1800c69a6  jz      loc_1800C6CD7
0x1800c69ac  mov     rcx, [rdi]
0x1800c69af  lea     rax, [rsp+2B0h+var_288]
0x1800c69b4  lea     r9, [rsp+2B0h+var_268]
0x1800c69b9  mov     [rsp+2B0h+var_270], rax
0x1800c69be  xor     r8d, r8d
0x1800c69c1  mov     [rsp+2B0h+var_288], r15
0x1800c69c6  lea     rdx, aUserData; "User\\Data"
0x1800c69cd  mov     [rsp+2B0h+var_268], r15
0x1800c69d2  mov     [rsp+2B0h+var_260], 1
0x1800c69d7  call    cs:__imp_SRCacheContext_Open
0x1800c69dd  lea     rcx, [rsp+2B0h+var_270]
0x1800c69e2  mov     ebx, eax
0x1800c69e4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c69e9  test    ebx, ebx
0x1800c69eb  jns     short loc_1800C6A41
0x1800c69ed  mov     rcx, [rbp+1B8h]; this
0x1800c69f4  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c69fb  mov     r9d, ebx; char *
0x1800c69fe  mov     edx, 18Ch; void *
0x1800c6a03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6a08  mov     rcx, [rbp+1B8h]; this
0x1800c6a0f  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x1800c6a16  mov     r9d, ebx; char *
0x1800c6a19  mov     edx, 148h; void *
0x1800c6a1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6a23  mov     rcx, [rsp+2B0h+var_288]
0x1800c6a28  mov     [rsp+2B0h+var_288], r15
0x1800c6a2d  test    rcx, rcx
0x1800c6a30  jz      loc_1800C6980
0x1800c6a36  call    cs:__imp_SRCacheContext_Close
0x1800c6a3c  jmp     loc_1800C6980
0x1800c6a41  cmp     [rsp+2B0h+var_288], r15
0x1800c6a46  lea     rcx, [rsp+2B0h+var_248]; void *
0x1800c6a4b  mov     r8d, 200h; Size
0x1800c6a51  mov     [rsp+2B0h+var_250], r15
0x1800c6a56  setnz   sil
0x1800c6a5a  xor     edx, edx; Val
0x1800c6a5c  call    memset_0
0x1800c6a61  lea     rax, [rsp+2B0h+var_248]
0x1800c6a66  mov     [rbp+1B0h+var_48], r15
0x1800c6a6d  mov     rdx, r14; unsigned __int64
0x1800c6a70  mov     [rbp+1B0h+var_38], rax
0x1800c6a77  lea     rcx, [rsp+2B0h+var_250]; this
0x1800c6a7c  mov     [rbp+1B0h+var_40], 100h
0x1800c6a87  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800c6a8c  mov     ebx, eax
0x1800c6a8e  test    eax, eax
0x1800c6a90  jns     short loc_1800C6ACB
0x1800c6a92  mov     rcx, [rbp+1B8h]; this
0x1800c6a99  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x1800c6aa0  mov     r9d, eax; char *
0x1800c6aa3  mov     edx, 14Ah; void *
0x1800c6aa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6aad  mov     rcx, [rsp+2B0h+var_250]
0x1800c6ab2  mov     [rsp+2B0h+var_250], r15
0x1800c6ab7  test    rcx, rcx
0x1800c6aba  jz      loc_1800C6A23
0x1800c6ac0  call    cs:__imp_SRCache_Free
0x1800c6ac6  jmp     loc_1800C6A23
0x1800c6acb  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x1800c6ad2  lea     rax, [rsp+2B0h+var_280]
0x1800c6ad7  lea     r8, [rsp+2B0h+var_268]; unsigned __int16 **
0x1800c6adc  mov     [rsp+2B0h+var_270], rax
0x1800c6ae1  lea     rcx, [rsp+2B0h+var_288]; struct StateRepository::Cache::Context_NoThrow *
0x1800c6ae6  mov     [rsp+2B0h+var_280], r15
0x1800c6aeb  mov     [rsp+2B0h+var_268], r15
0x1800c6af0  mov     [rsp+2B0h+var_260], 1
0x1800c6af5  call    ?GetIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBGPEAPEAG@Z; StateRepository::CacheManagement::GetIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *,ushort * *)
0x1800c6afa  lea     rcx, [rsp+2B0h+var_270]
0x1800c6aff  mov     ebx, eax
0x1800c6b01  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800c6b06  test    ebx, ebx
0x1800c6b08  jns     short loc_1800C6B43
0x1800c6b0a  mov     edx, 14Ch; void *
0x1800c6b0f  mov     rcx, [rbp+1B8h]; this
0x1800c6b16  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x1800c6b1d  mov     r9d, ebx; char *
0x1800c6b20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6b25  mov     rcx, [rsp+2B0h+var_280]
0x1800c6b2a  mov     [rsp+2B0h+var_280], r15
0x1800c6b2f  test    rcx, rcx
0x1800c6b32  jz      loc_1800C6AAD
0x1800c6b38  call    cs:__imp_SRCache_Free
0x1800c6b3e  jmp     loc_1800C6AAD
0x1800c6b43  mov     rdx, [rbp+1B0h+var_38]; unsigned __int16 *
0x1800c6b4a  lea     rcx, [rsp+2B0h+var_288]; this
0x1800c6b4f  call    ?Delete@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::Delete(ushort const *)
0x1800c6b54  mov     ebx, eax
0x1800c6b56  test    eax, eax
0x1800c6b58  jns     short loc_1800C6B61
0x1800c6b5a  mov     edx, 14Dh
0x1800c6b5f  jmp     short loc_1800C6B0F
0x1800c6b61  lea     rdx, aUserData; "User\\Data"
0x1800c6b68  lea     rcx, [rsp+2B0h+var_288]; this
0x1800c6b6d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800c6b72  mov     ebx, eax
0x1800c6b74  test    eax, eax
0x1800c6b76  jns     short loc_1800C6B7F
0x1800c6b78  mov     edx, 14Fh
0x1800c6b7d  jmp     short loc_1800C6B0F
0x1800c6b7f  mov     rcx, [rdi]
0x1800c6b82  lea     rax, [rsp+2B0h+var_278]
0x1800c6b87  lea     r9, [rsp+2B0h+var_268]
0x1800c6b8c  mov     [rsp+2B0h+var_270], rax
0x1800c6b91  xor     r8d, r8d
0x1800c6b94  mov     [rsp+2B0h+var_278], r15
0x1800c6b99  lea     rdx, aUserIndex; "User\\Index"
0x1800c6ba0  mov     [rsp+2B0h+var_268], r15
0x1800c6ba5  mov     [rsp+2B0h+var_260], 1
0x1800c6baa  call    cs:__imp_SRCacheContext_Open
0x1800c6bb0  lea     rcx, [rsp+2B0h+var_270]
0x1800c6bb5  mov     ebx, eax
0x1800c6bb7  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c6bbc  test    ebx, ebx
0x1800c6bbe  jns     short loc_1800C6C14
0x1800c6bc0  mov     rcx, [rbp+1B8h]; this
0x1800c6bc7  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c6bce  mov     r9d, ebx; char *
0x1800c6bd1  mov     edx, 18Ch; void *
0x1800c6bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6bdb  mov     edx, 153h; void *
0x1800c6be0  mov     rcx, [rbp+1B8h]; this
0x1800c6be7  lea     r8, aOnecoreBaseApp_198; "onecore\\base\\appmodel\\staterepositor"...
0x1800c6bee  mov     r9d, ebx; char *
0x1800c6bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6bf6  mov     rcx, [rsp+2B0h+var_278]
0x1800c6bfb  mov     [rsp+2B0h+var_278], r15
0x1800c6c00  test    rcx, rcx
0x1800c6c03  jz      loc_1800C6B25
0x1800c6c09  call    cs:__imp_SRCacheContext_Close
0x1800c6c0f  jmp     loc_1800C6B25
0x1800c6c14  mov     rcx, [rsp+2B0h+var_278]
0x1800c6c19  test    rcx, rcx
0x1800c6c1c  setnz   al
0x1800c6c1f  test    al, al
0x1800c6c21  jz      short loc_1800C6C62
0x1800c6c23  mov     rdx, [rsp+2B0h+var_280]; unsigned __int16 *
0x1800c6c28  lea     rcx, [rsp+2B0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x1800c6c2d  call    ?DeleteIndexKeys@CacheManagement@StateRepository@@SAJAEAVContext_NoThrow@Cache@2@PEBG@Z; StateRepository::CacheManagement::DeleteIndexKeys(StateRepository::Cache::Context_NoThrow &,ushort const *)
0x1800c6c32  mov     ebx, eax
0x1800c6c34  test    eax, eax
0x1800c6c36  jns     short loc_1800C6C3F
0x1800c6c38  mov     edx, 156h
0x1800c6c3d  jmp     short loc_1800C6BE0
0x1800c6c3f  lea     rdx, aUserIndex; "User\\Index"
0x1800c6c46  lea     rcx, [rsp+2B0h+var_278]; this
0x1800c6c4b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800c6c50  mov     ebx, eax
0x1800c6c52  test    eax, eax
0x1800c6c54  jns     short loc_1800C6C5D
0x1800c6c56  mov     edx, 157h
0x1800c6c5b  jmp     short loc_1800C6BE0
0x1800c6c5d  mov     rcx, [rsp+2B0h+var_278]
0x1800c6c62  mov     [rsp+2B0h+var_278], r15
0x1800c6c67  test    rcx, rcx
0x1800c6c6a  jz      short loc_1800C6C72
0x1800c6c6c  call    cs:__imp_SRCacheContext_Close
0x1800c6c72  mov     rcx, [rsp+2B0h+var_280]
0x1800c6c77  mov     [rsp+2B0h+var_280], r15
0x1800c6c7c  test    rcx, rcx
0x1800c6c7f  jz      short loc_1800C6C87
0x1800c6c81  call    cs:__imp_SRCache_Free
0x1800c6c87  mov     rcx, [rsp+2B0h+var_250]
0x1800c6c8c  mov     [rsp+2B0h+var_250], r15
0x1800c6c91  test    rcx, rcx
0x1800c6c94  jz      short loc_1800C6C9C
0x1800c6c96  call    cs:__imp_SRCache_Free
0x1800c6c9c  mov     rcx, [rsp+2B0h+var_288]
0x1800c6ca1  mov     [rsp+2B0h+var_288], r15
0x1800c6ca6  test    rcx, rcx
0x1800c6ca9  jz      short loc_1800C6CB1
0x1800c6cab  call    cs:__imp_SRCacheContext_Close
0x1800c6cb1  test    sil, sil
0x1800c6cb4  jz      short loc_1800C6CD7
0x1800c6cb6  lea     rdx, aUser_0; "User"
0x1800c6cbd  lea     rcx, [rsp+2B0h+var_290]; this
0x1800c6cc2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800c6cc7  mov     ebx, eax
0x1800c6cc9  test    eax, eax
0x1800c6ccb  jns     short loc_1800C6CD7
0x1800c6ccd  mov     edx, 15Ch
0x1800c6cd2  jmp     loc_1800C696A
0x1800c6cd7  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x1800c6cdc  mov     qword ptr [rsp+2B0h+var_290], r15
0x1800c6ce1  test    rcx, rcx
0x1800c6ce4  jz      short loc_1800C6CEC
0x1800c6ce6  call    cs:__imp_SRCacheContext_Close
0x1800c6cec  xor     eax, eax
0x1800c6cee  mov     rcx, [rbp+1B0h+var_30]
0x1800c6cf5  xor     rcx, rsp; StackCookie
0x1800c6cf8  call    __security_check_cookie
0x1800c6cfd  mov     rbx, [rsp+2B0h+arg_10]
0x1800c6d05  add     rsp, 290h
0x1800c6d0c  pop     r15
0x1800c6d0e  pop     r14
0x1800c6d10  pop     rdi
0x1800c6d11  pop     rsi
0x1800c6d12  pop     rbp
0x1800c6d13  retn
```
