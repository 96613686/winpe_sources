# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800d29c8`
- end: `0x1800d2c05`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18026e0cc`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1800d29c8`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800d2b4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800d2b4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d2a86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d2bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d2a86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d2bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2b21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2bc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2b21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800d2bc2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d2a2b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800d2a2b`

## string_xrefs

- `0x1800d2a48`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800d2b6c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800d2a68`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Activation.hpp`
- `0x1800d2aff`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v21 = v20;
  v23 = 1;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v8 = SRCacheContext_Open(v4, L"Activation\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 391;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
LABEL_4:
    v12 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v10, v11);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v20 )
  {
    v8 = -2140733422;
    v9 = 392;
    goto LABEL_3;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  if ( v8 < 0 )
  {
    v14 = 395;
    goto LABEL_11;
  }
  v21 = (int *)a3;
  v22 = 0;
  v23 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v14 = 396;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"Activation\\Data");
  if ( v8 < 0 )
  {
    v14 = 398;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v15 = v24;
    v24 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_4;
  }
  v18 = v24;
  v24 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19, v16, v17);
  return 0;
}

```

## disassembly

```asm
0x1800d29c8  mov     [rsp-8+arg_10], rbx
0x1800d29cd  push    rbp
0x1800d29ce  push    rsi
0x1800d29cf  push    rdi
0x1800d29d0  push    r14
0x1800d29d2  push    r15
0x1800d29d4  lea     rbp, [rsp-170h]
0x1800d29dc  sub     rsp, 270h
0x1800d29e3  mov     rax, cs:__security_cookie
0x1800d29ea  xor     rax, rsp
0x1800d29ed  mov     [rbp+190h+var_30], rax
0x1800d29f4  mov     rcx, [rcx]
0x1800d29f7  lea     rax, [rsp+290h+var_270]
0x1800d29fc  mov     rsi, r9
0x1800d29ff  mov     [rsp+290h+var_268], rax
0x1800d2a04  mov     rdi, r8
0x1800d2a07  mov     [rsp+290h+var_258], 1
0x1800d2a0c  mov     r14, rdx
0x1800d2a0f  lea     r9, [rsp+290h+var_260]
0x1800d2a14  xor     r15d, r15d
0x1800d2a17  lea     rdx, aActivationData; "Activation\\Data"
0x1800d2a1e  xor     r8d, r8d
0x1800d2a21  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800d2a26  mov     [rsp+290h+var_260], r15
0x1800d2a2b  call    cs:__imp_SRCacheContext_Open
0x1800d2a31  lea     rcx, [rsp+290h+var_268]
0x1800d2a36  mov     ebx, eax
0x1800d2a38  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d2a3d  test    ebx, ebx
0x1800d2a3f  jns     short loc_1800D2A93
0x1800d2a41  mov     rcx, [rbp+198h]; this
0x1800d2a48  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d2a4f  mov     r9d, ebx; char *
0x1800d2a52  mov     edx, 18Ch; void *
0x1800d2a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2a5c  mov     edx, 187h; void *
0x1800d2a61  mov     rcx, [rbp+198h]; this
0x1800d2a68  lea     r8, aOnecoreBaseApp_110; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d2a6f  mov     r9d, ebx; char *
0x1800d2a72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2a77  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800d2a7c  mov     qword ptr [rsp+290h+var_270], r15
0x1800d2a81  test    rcx, rcx
0x1800d2a84  jz      short loc_1800D2A8C
0x1800d2a86  call    cs:__imp_SRCacheContext_Close
0x1800d2a8c  mov     eax, ebx
0x1800d2a8e  jmp     loc_1800D2BDF
0x1800d2a93  cmp     qword ptr [rsp+290h+var_270], r15
0x1800d2a98  setnz   al
0x1800d2a9b  test    al, al
0x1800d2a9d  jnz     short loc_1800D2AAB
0x1800d2a9f  mov     ebx, 80670012h
0x1800d2aa4  mov     edx, 188h
0x1800d2aa9  jmp     short loc_1800D2A61
0x1800d2aab  xor     edx, edx; Val
0x1800d2aad  mov     [rsp+290h+var_250], r15
0x1800d2ab2  mov     r8d, 200h; Size
0x1800d2ab8  lea     rcx, [rsp+290h+var_248]; void *
0x1800d2abd  call    memset_0
0x1800d2ac2  lea     rax, [rsp+290h+var_248]
0x1800d2ac7  mov     [rbp+190h+var_48], r15
0x1800d2ace  mov     rdx, r14; unsigned __int64
0x1800d2ad1  mov     [rbp+190h+var_38], rax
0x1800d2ad8  lea     rcx, [rsp+290h+var_250]; this
0x1800d2add  mov     [rbp+190h+var_40], 100h
0x1800d2ae8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800d2aed  mov     ebx, eax
0x1800d2aef  test    eax, eax
0x1800d2af1  jns     short loc_1800D2B2C
0x1800d2af3  mov     edx, 18Bh; void *
0x1800d2af8  mov     rcx, [rbp+198h]; this
0x1800d2aff  lea     r8, aOnecoreBaseApp_110; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d2b06  mov     r9d, ebx; char *
0x1800d2b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2b0e  mov     rcx, [rsp+290h+var_250]
0x1800d2b13  mov     [rsp+290h+var_250], r15
0x1800d2b18  test    rcx, rcx
0x1800d2b1b  jz      loc_1800D2A77
0x1800d2b21  call    cs:__imp_SRCache_Free
0x1800d2b27  jmp     loc_1800D2A77
0x1800d2b2c  mov     rdx, [rbp+190h+var_38]
0x1800d2b33  lea     r9, [rsp+290h+var_260]
0x1800d2b38  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800d2b3d  xor     r8d, r8d
0x1800d2b40  mov     [rsp+290h+var_268], rdi
0x1800d2b45  mov     [rsp+290h+var_260], r15
0x1800d2b4a  mov     [rsp+290h+var_258], 1
0x1800d2b4f  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800d2b55  lea     rcx, [rsp+290h+var_268]
0x1800d2b5a  mov     ebx, eax
0x1800d2b5c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800d2b61  test    ebx, ebx
0x1800d2b63  jns     short loc_1800D2B8A
0x1800d2b65  mov     rcx, [rbp+198h]; this
0x1800d2b6c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d2b73  mov     r9d, ebx; char *
0x1800d2b76  mov     edx, 1B0h; void *
0x1800d2b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2b80  mov     edx, 18Ch
0x1800d2b85  jmp     loc_1800D2AF8
0x1800d2b8a  cmp     [rdi], r15
0x1800d2b8d  lea     rdx, aActivationData; "Activation\\Data"
0x1800d2b94  lea     rcx, [rsp+290h+var_270]; this
0x1800d2b99  setnz   al
0x1800d2b9c  mov     [rsi], al
0x1800d2b9e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800d2ba3  mov     ebx, eax
0x1800d2ba5  test    eax, eax
0x1800d2ba7  jns     short loc_1800D2BB3
0x1800d2ba9  mov     edx, 18Eh
0x1800d2bae  jmp     loc_1800D2AF8
0x1800d2bb3  mov     rcx, [rsp+290h+var_250]
0x1800d2bb8  mov     [rsp+290h+var_250], r15
0x1800d2bbd  test    rcx, rcx
0x1800d2bc0  jz      short loc_1800D2BC8
0x1800d2bc2  call    cs:__imp_SRCache_Free
0x1800d2bc8  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800d2bcd  mov     qword ptr [rsp+290h+var_270], r15
0x1800d2bd2  test    rcx, rcx
0x1800d2bd5  jz      short loc_1800D2BDD
0x1800d2bd7  call    cs:__imp_SRCacheContext_Close
0x1800d2bdd  xor     eax, eax
0x1800d2bdf  mov     rcx, [rbp+190h+var_30]
0x1800d2be6  xor     rcx, rsp; StackCookie
0x1800d2be9  call    __security_check_cookie
0x1800d2bee  mov     rbx, [rsp+290h+arg_10]
0x1800d2bf6  add     rsp, 270h
0x1800d2bfd  pop     r15
0x1800d2bff  pop     r14
0x1800d2c01  pop     rdi
0x1800d2c02  pop     rsi
0x1800d2c03  pop     rbp
0x1800d2c04  retn
```
