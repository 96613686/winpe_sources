# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800c4698`
- end: `0x1800c48d5`
- name: `?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18026d998`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1800c4698`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800c481f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800c481f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c4756`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c48a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c4756`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c48a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c47f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c4892`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c47f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800c4892`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c46fb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800c46fb`

## string_xrefs

- `0x1800c4718`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c483c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800c4738`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-ApplicationUser.hpp`
- `0x1800c47cf`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"ApplicationUser\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 505;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-ApplicationUser.hpp",
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
    v9 = 506;
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
    v12 = 509;
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
    v12 = 510;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationUser\\Data");
  if ( v8 < 0 )
  {
    v12 = 512;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-ApplicationUser.hpp",
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
0x1800c4698  mov     [rsp-8+arg_10], rbx
0x1800c469d  push    rbp
0x1800c469e  push    rsi
0x1800c469f  push    rdi
0x1800c46a0  push    r14
0x1800c46a2  push    r15
0x1800c46a4  lea     rbp, [rsp-170h]
0x1800c46ac  sub     rsp, 270h
0x1800c46b3  mov     rax, cs:__security_cookie
0x1800c46ba  xor     rax, rsp
0x1800c46bd  mov     [rbp+190h+var_30], rax
0x1800c46c4  mov     rcx, [rcx]
0x1800c46c7  lea     rax, [rsp+290h+var_270]
0x1800c46cc  mov     rsi, r9
0x1800c46cf  mov     [rsp+290h+var_268], rax
0x1800c46d4  mov     rdi, r8
0x1800c46d7  mov     [rsp+290h+var_258], 1
0x1800c46dc  mov     r14, rdx
0x1800c46df  lea     r9, [rsp+290h+var_260]
0x1800c46e4  xor     r15d, r15d
0x1800c46e7  lea     rdx, aApplicationuse_3; "ApplicationUser\\Data"
0x1800c46ee  xor     r8d, r8d
0x1800c46f1  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800c46f6  mov     [rsp+290h+var_260], r15
0x1800c46fb  call    cs:__imp_SRCacheContext_Open
0x1800c4701  lea     rcx, [rsp+290h+var_268]
0x1800c4706  mov     ebx, eax
0x1800c4708  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c470d  test    ebx, ebx
0x1800c470f  jns     short loc_1800C4763
0x1800c4711  mov     rcx, [rbp+198h]; this
0x1800c4718  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c471f  mov     r9d, ebx; char *
0x1800c4722  mov     edx, 18Ch; void *
0x1800c4727  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c472c  mov     edx, 1F9h; void *
0x1800c4731  mov     rcx, [rbp+198h]; this
0x1800c4738  lea     r8, aOnecoreBaseApp_227; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c473f  mov     r9d, ebx; char *
0x1800c4742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4747  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800c474c  mov     qword ptr [rsp+290h+var_270], r15
0x1800c4751  test    rcx, rcx
0x1800c4754  jz      short loc_1800C475C
0x1800c4756  call    cs:__imp_SRCacheContext_Close
0x1800c475c  mov     eax, ebx
0x1800c475e  jmp     loc_1800C48AF
0x1800c4763  cmp     qword ptr [rsp+290h+var_270], r15
0x1800c4768  setnz   al
0x1800c476b  test    al, al
0x1800c476d  jnz     short loc_1800C477B
0x1800c476f  mov     ebx, 80670012h
0x1800c4774  mov     edx, 1FAh
0x1800c4779  jmp     short loc_1800C4731
0x1800c477b  xor     edx, edx; Val
0x1800c477d  mov     [rsp+290h+var_250], r15
0x1800c4782  mov     r8d, 200h; Size
0x1800c4788  lea     rcx, [rsp+290h+var_248]; void *
0x1800c478d  call    memset_0
0x1800c4792  lea     rax, [rsp+290h+var_248]
0x1800c4797  mov     [rbp+190h+var_48], r15
0x1800c479e  mov     rdx, r14; unsigned __int64
0x1800c47a1  mov     [rbp+190h+var_38], rax
0x1800c47a8  lea     rcx, [rsp+290h+var_250]; this
0x1800c47ad  mov     [rbp+190h+var_40], 100h
0x1800c47b8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800c47bd  mov     ebx, eax
0x1800c47bf  test    eax, eax
0x1800c47c1  jns     short loc_1800C47FC
0x1800c47c3  mov     edx, 1FDh; void *
0x1800c47c8  mov     rcx, [rbp+198h]; this
0x1800c47cf  lea     r8, aOnecoreBaseApp_227; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c47d6  mov     r9d, ebx; char *
0x1800c47d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c47de  mov     rcx, [rsp+290h+var_250]
0x1800c47e3  mov     [rsp+290h+var_250], r15
0x1800c47e8  test    rcx, rcx
0x1800c47eb  jz      loc_1800C4747
0x1800c47f1  call    cs:__imp_SRCache_Free
0x1800c47f7  jmp     loc_1800C4747
0x1800c47fc  mov     rdx, [rbp+190h+var_38]
0x1800c4803  lea     r9, [rsp+290h+var_260]
0x1800c4808  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800c480d  xor     r8d, r8d
0x1800c4810  mov     [rsp+290h+var_268], rdi
0x1800c4815  mov     [rsp+290h+var_260], r15
0x1800c481a  mov     [rsp+290h+var_258], 1
0x1800c481f  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800c4825  lea     rcx, [rsp+290h+var_268]
0x1800c482a  mov     ebx, eax
0x1800c482c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800c4831  test    ebx, ebx
0x1800c4833  jns     short loc_1800C485A
0x1800c4835  mov     rcx, [rbp+198h]; this
0x1800c483c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c4843  mov     r9d, ebx; char *
0x1800c4846  mov     edx, 1B0h; void *
0x1800c484b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4850  mov     edx, 1FEh
0x1800c4855  jmp     loc_1800C47C8
0x1800c485a  cmp     [rdi], r15
0x1800c485d  lea     rdx, aApplicationuse_3; "ApplicationUser\\Data"
0x1800c4864  lea     rcx, [rsp+290h+var_270]; this
0x1800c4869  setnz   al
0x1800c486c  mov     [rsi], al
0x1800c486e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800c4873  mov     ebx, eax
0x1800c4875  test    eax, eax
0x1800c4877  jns     short loc_1800C4883
0x1800c4879  mov     edx, 200h
0x1800c487e  jmp     loc_1800C47C8
0x1800c4883  mov     rcx, [rsp+290h+var_250]
0x1800c4888  mov     [rsp+290h+var_250], r15
0x1800c488d  test    rcx, rcx
0x1800c4890  jz      short loc_1800C4898
0x1800c4892  call    cs:__imp_SRCache_Free
0x1800c4898  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800c489d  mov     qword ptr [rsp+290h+var_270], r15
0x1800c48a2  test    rcx, rcx
0x1800c48a5  jz      short loc_1800C48AD
0x1800c48a7  call    cs:__imp_SRCacheContext_Close
0x1800c48ad  xor     eax, eax
0x1800c48af  mov     rcx, [rbp+190h+var_30]
0x1800c48b6  xor     rcx, rsp; StackCookie
0x1800c48b9  call    __security_check_cookie
0x1800c48be  mov     rbx, [rsp+290h+arg_10]
0x1800c48c6  add     rsp, 270h
0x1800c48cd  pop     r15
0x1800c48cf  pop     r14
0x1800c48d1  pop     rdi
0x1800c48d2  pop     rsi
0x1800c48d3  pop     rbp
0x1800c48d4  retn
```
