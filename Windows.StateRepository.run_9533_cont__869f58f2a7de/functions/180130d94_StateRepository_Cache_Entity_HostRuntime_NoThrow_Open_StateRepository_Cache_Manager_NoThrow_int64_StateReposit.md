# StateRepository::Cache::Entity::HostRuntime_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180130d94`
- end: `0x180130fd1`
- name: `?Open@HostRuntime_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18026f4c0`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x180130d94`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180130f1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180130f1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180130e52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180130fa3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180130e52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180130fa3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180130eed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180130f8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180130eed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180130f8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180130df7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180130df7`

## string_xrefs

- `0x180130e14`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180130f38`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180130e34`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-HostRuntime.hpp`
- `0x180130ecb`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-HostRuntime.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::HostRuntime_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v17 = v16;
  v19 = 1;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  v8 = SRCacheContext_Open(v4, L"HostRuntime\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 245;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
LABEL_4:
    v10 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 246;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v8 < 0 )
  {
    v12 = 249;
    goto LABEL_11;
  }
  v17 = (int *)a3;
  v18 = 0;
  v19 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v24, 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 250;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"HostRuntime\\Data");
  if ( v8 < 0 )
  {
    v12 = 252;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x180130d94  mov     [rsp-8+arg_10], rbx
0x180130d99  push    rbp
0x180130d9a  push    rsi
0x180130d9b  push    rdi
0x180130d9c  push    r14
0x180130d9e  push    r15
0x180130da0  lea     rbp, [rsp-170h]
0x180130da8  sub     rsp, 270h
0x180130daf  mov     rax, cs:__security_cookie
0x180130db6  xor     rax, rsp
0x180130db9  mov     [rbp+190h+var_30], rax
0x180130dc0  mov     rcx, [rcx]
0x180130dc3  lea     rax, [rsp+290h+var_270]
0x180130dc8  mov     rsi, r9
0x180130dcb  mov     [rsp+290h+var_268], rax
0x180130dd0  mov     rdi, r8
0x180130dd3  mov     [rsp+290h+var_258], 1
0x180130dd8  mov     r14, rdx
0x180130ddb  lea     r9, [rsp+290h+var_260]
0x180130de0  xor     r15d, r15d
0x180130de3  lea     rdx, aHostruntimeDat; "HostRuntime\\Data"
0x180130dea  xor     r8d, r8d
0x180130ded  mov     qword ptr [rsp+290h+var_270], r15; int
0x180130df2  mov     [rsp+290h+var_260], r15
0x180130df7  call    cs:__imp_SRCacheContext_Open
0x180130dfd  lea     rcx, [rsp+290h+var_268]
0x180130e02  mov     ebx, eax
0x180130e04  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180130e09  test    ebx, ebx
0x180130e0b  jns     short loc_180130E5F
0x180130e0d  mov     rcx, [rbp+198h]; this
0x180130e14  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180130e1b  mov     r9d, ebx; char *
0x180130e1e  mov     edx, 18Ch; void *
0x180130e23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130e28  mov     edx, 0F5h; void *
0x180130e2d  mov     rcx, [rbp+198h]; this
0x180130e34  lea     r8, aOnecoreBaseApp_402; "onecore\\base\\appmodel\\StateRepositor"...
0x180130e3b  mov     r9d, ebx; char *
0x180130e3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130e43  mov     rcx, qword ptr [rsp+290h+var_270]
0x180130e48  mov     qword ptr [rsp+290h+var_270], r15
0x180130e4d  test    rcx, rcx
0x180130e50  jz      short loc_180130E58
0x180130e52  call    cs:__imp_SRCacheContext_Close
0x180130e58  mov     eax, ebx
0x180130e5a  jmp     loc_180130FAB
0x180130e5f  cmp     qword ptr [rsp+290h+var_270], r15
0x180130e64  setnz   al
0x180130e67  test    al, al
0x180130e69  jnz     short loc_180130E77
0x180130e6b  mov     ebx, 80670012h
0x180130e70  mov     edx, 0F6h
0x180130e75  jmp     short loc_180130E2D
0x180130e77  xor     edx, edx; Val
0x180130e79  mov     [rsp+290h+var_250], r15
0x180130e7e  mov     r8d, 200h; Size
0x180130e84  lea     rcx, [rsp+290h+var_248]; void *
0x180130e89  call    memset_0
0x180130e8e  lea     rax, [rsp+290h+var_248]
0x180130e93  mov     [rbp+190h+var_48], r15
0x180130e9a  mov     rdx, r14; unsigned __int64
0x180130e9d  mov     [rbp+190h+var_38], rax
0x180130ea4  lea     rcx, [rsp+290h+var_250]; this
0x180130ea9  mov     [rbp+190h+var_40], 100h
0x180130eb4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180130eb9  mov     ebx, eax
0x180130ebb  test    eax, eax
0x180130ebd  jns     short loc_180130EF8
0x180130ebf  mov     edx, 0F9h; void *
0x180130ec4  mov     rcx, [rbp+198h]; this
0x180130ecb  lea     r8, aOnecoreBaseApp_402; "onecore\\base\\appmodel\\StateRepositor"...
0x180130ed2  mov     r9d, ebx; char *
0x180130ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130eda  mov     rcx, [rsp+290h+var_250]
0x180130edf  mov     [rsp+290h+var_250], r15
0x180130ee4  test    rcx, rcx
0x180130ee7  jz      loc_180130E43
0x180130eed  call    cs:__imp_SRCache_Free
0x180130ef3  jmp     loc_180130E43
0x180130ef8  mov     rdx, [rbp+190h+var_38]
0x180130eff  lea     r9, [rsp+290h+var_260]
0x180130f04  mov     rcx, qword ptr [rsp+290h+var_270]
0x180130f09  xor     r8d, r8d
0x180130f0c  mov     [rsp+290h+var_268], rdi
0x180130f11  mov     [rsp+290h+var_260], r15
0x180130f16  mov     [rsp+290h+var_258], 1
0x180130f1b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180130f21  lea     rcx, [rsp+290h+var_268]
0x180130f26  mov     ebx, eax
0x180130f28  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180130f2d  test    ebx, ebx
0x180130f2f  jns     short loc_180130F56
0x180130f31  mov     rcx, [rbp+198h]; this
0x180130f38  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180130f3f  mov     r9d, ebx; char *
0x180130f42  mov     edx, 1B0h; void *
0x180130f47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130f4c  mov     edx, 0FAh
0x180130f51  jmp     loc_180130EC4
0x180130f56  cmp     [rdi], r15
0x180130f59  lea     rdx, aHostruntimeDat; "HostRuntime\\Data"
0x180130f60  lea     rcx, [rsp+290h+var_270]; this
0x180130f65  setnz   al
0x180130f68  mov     [rsi], al
0x180130f6a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180130f6f  mov     ebx, eax
0x180130f71  test    eax, eax
0x180130f73  jns     short loc_180130F7F
0x180130f75  mov     edx, 0FCh
0x180130f7a  jmp     loc_180130EC4
0x180130f7f  mov     rcx, [rsp+290h+var_250]
0x180130f84  mov     [rsp+290h+var_250], r15
0x180130f89  test    rcx, rcx
0x180130f8c  jz      short loc_180130F94
0x180130f8e  call    cs:__imp_SRCache_Free
0x180130f94  mov     rcx, qword ptr [rsp+290h+var_270]
0x180130f99  mov     qword ptr [rsp+290h+var_270], r15
0x180130f9e  test    rcx, rcx
0x180130fa1  jz      short loc_180130FA9
0x180130fa3  call    cs:__imp_SRCacheContext_Close
0x180130fa9  xor     eax, eax
0x180130fab  mov     rcx, [rbp+190h+var_30]
0x180130fb2  xor     rcx, rsp; StackCookie
0x180130fb5  call    __security_check_cookie
0x180130fba  mov     rbx, [rsp+290h+arg_10]
0x180130fc2  add     rsp, 270h
0x180130fc9  pop     r15
0x180130fcb  pop     r14
0x180130fcd  pop     rdi
0x180130fce  pop     rsi
0x180130fcf  pop     rbp
0x180130fd0  retn
```
