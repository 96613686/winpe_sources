# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000b6f0`
- end: `0x18000b984`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a0d0`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x18000b6f0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b7b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b956`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b7b8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b956`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b941`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b896`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b941`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b75b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b75b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b8cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b8cc`

## string_xrefs

- `0x18000b836`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18000b77a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000b8eb`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000b79a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`
- `0x18000b874`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  bool v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+238h] [rbp+138h]
  __int64 v21; // [rsp+240h] [rbp+140h]
  _BYTE *v22; // [rsp+248h] [rbp+148h]
  unsigned __int16 v23[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v24; // [rsp+258h] [rbp+158h] BYREF
  char v25; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v23 = v17;
  v25 = 1;
  *(_QWORD *)v17 = 0;
  v24 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>((__int64 **)v23);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v9 = 1192;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
LABEL_4:
    v10 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v17 )
  {
    v8 = -2140733422;
    v9 = 1193;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v21 = 256;
  v22 = v19;
  if ( (unsigned int)o__ui64tow_s_0(a2, v23, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v17[0]);
LABEL_12:
    v13 = 1196;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, v23, v12);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v23 = a3;
  v24 = 0;
  v25 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v17, v22, 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>((__int64 **)v23);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v13 = 1197;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"Package\\Data");
  if ( v8 < 0 )
  {
    v13 = 1199;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v14 = v18;
    v18 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_4;
  }
  v15 = v18;
  v18 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x18000b6f0  mov     [rsp-8+arg_10], rbx
0x18000b6f5  push    rbp
0x18000b6f6  push    rsi
0x18000b6f7  push    rdi
0x18000b6f8  push    r14
0x18000b6fa  push    r15
0x18000b6fc  lea     rbp, [rsp-180h]
0x18000b704  sub     rsp, 280h
0x18000b70b  mov     rax, cs:__security_cookie
0x18000b712  xor     rax, rsp
0x18000b715  mov     [rbp+1A0h+var_28], rax
0x18000b71c  mov     rcx, [rcx]
0x18000b71f  lea     rax, [rsp+2A0h+var_280]
0x18000b724  mov     rsi, r9
0x18000b727  mov     qword ptr [rbp+1A0h+var_50], rax
0x18000b72e  mov     rdi, r8
0x18000b731  mov     [rbp+1A0h+var_40], 1
0x18000b738  mov     r14, rdx
0x18000b73b  lea     r9, [rbp+1A0h+var_48]
0x18000b742  xor     r15d, r15d
0x18000b745  lea     rdx, aPackageData; "Package\\Data"
0x18000b74c  xor     r8d, r8d
0x18000b74f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18000b754  mov     [rbp+1A0h+var_48], r15
0x18000b75b  call    cs:__imp_SRCacheContext_Open
0x18000b761  lea     rcx, [rbp+1A0h+var_50]
0x18000b768  mov     ebx, eax
0x18000b76a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000b76f  test    ebx, ebx
0x18000b771  jns     short loc_18000B7C5
0x18000b773  mov     rcx, [rbp+1A8h]; this
0x18000b77a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b781  mov     r9d, ebx; char *
0x18000b784  mov     edx, 18Ch; void *
0x18000b789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b78e  mov     edx, 4A8h; void *
0x18000b793  mov     rcx, [rbp+1A8h]; this
0x18000b79a  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b7a1  mov     r9d, ebx; char *
0x18000b7a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7a9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000b7ae  mov     qword ptr [rsp+2A0h+var_280], r15
0x18000b7b3  test    rcx, rcx
0x18000b7b6  jz      short loc_18000B7BE
0x18000b7b8  call    cs:__imp_SRCacheContext_Close
0x18000b7be  mov     eax, ebx
0x18000b7c0  jmp     loc_18000B95E
0x18000b7c5  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18000b7ca  setnz   al
0x18000b7cd  test    al, al
0x18000b7cf  jnz     short loc_18000B7DD
0x18000b7d1  mov     ebx, 80670012h
0x18000b7d6  mov     edx, 4A9h
0x18000b7db  jmp     short loc_18000B793
0x18000b7dd  xor     edx, edx; Val
0x18000b7df  mov     [rsp+2A0h+var_270], r15
0x18000b7e4  mov     r8d, 200h; Size
0x18000b7ea  lea     rcx, [rsp+2A0h+var_268]; void *
0x18000b7ef  call    memset_0
0x18000b7f4  mov     r9d, 10h
0x18000b7fa  mov     [rbp+1A0h+var_68], r15
0x18000b801  lea     rax, [rsp+2A0h+var_268]
0x18000b806  mov     [rbp+1A0h+var_60], 100h
0x18000b811  lea     rdx, [rbp+1A0h+var_50]
0x18000b818  mov     [rbp+1A0h+var_58], rax
0x18000b81f  mov     rcx, r14
0x18000b822  lea     r8d, [r9+1]
0x18000b826  call    _o__ui64tow_s_0
0x18000b82b  test    eax, eax
0x18000b82d  jz      short loc_18000B851
0x18000b82f  mov     rcx, [rbp+1A8h]; this
0x18000b836  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b83d  mov     ebx, 8000FFFFh
0x18000b842  mov     edx, 166h; void *
0x18000b847  mov     r9d, ebx; char *
0x18000b84a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b84f  jmp     short loc_18000B868
0x18000b851  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18000b858  lea     rcx, [rsp+2A0h+var_270]; this
0x18000b85d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000b862  mov     ebx, eax
0x18000b864  test    eax, eax
0x18000b866  jns     short loc_18000B8A1
0x18000b868  mov     edx, 4ACh; void *
0x18000b86d  mov     rcx, [rbp+1A8h]; this
0x18000b874  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b87b  mov     r9d, ebx; char *
0x18000b87e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b883  mov     rcx, [rsp+2A0h+var_270]
0x18000b888  mov     [rsp+2A0h+var_270], r15
0x18000b88d  test    rcx, rcx
0x18000b890  jz      loc_18000B7A9
0x18000b896  call    cs:__imp_SRCache_Free
0x18000b89c  jmp     loc_18000B7A9
0x18000b8a1  mov     rdx, [rbp+1A0h+var_58]
0x18000b8a8  lea     r9, [rbp+1A0h+var_48]
0x18000b8af  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000b8b4  xor     r8d, r8d
0x18000b8b7  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18000b8be  mov     [rbp+1A0h+var_48], r15
0x18000b8c5  mov     [rbp+1A0h+var_40], 1
0x18000b8cc  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000b8d2  lea     rcx, [rbp+1A0h+var_50]
0x18000b8d9  mov     ebx, eax
0x18000b8db  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000b8e0  test    ebx, ebx
0x18000b8e2  jns     short loc_18000B909
0x18000b8e4  mov     rcx, [rbp+1A8h]; this
0x18000b8eb  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b8f2  mov     r9d, ebx; char *
0x18000b8f5  mov     edx, 1B0h; void *
0x18000b8fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8ff  mov     edx, 4ADh
0x18000b904  jmp     loc_18000B86D
0x18000b909  cmp     [rdi], r15
0x18000b90c  lea     rdx, aPackageData; "Package\\Data"
0x18000b913  lea     rcx, [rsp+2A0h+var_280]; this
0x18000b918  setnz   al
0x18000b91b  mov     [rsi], al
0x18000b91d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000b922  mov     ebx, eax
0x18000b924  test    eax, eax
0x18000b926  jns     short loc_18000B932
0x18000b928  mov     edx, 4AFh
0x18000b92d  jmp     loc_18000B86D
0x18000b932  mov     rcx, [rsp+2A0h+var_270]
0x18000b937  mov     [rsp+2A0h+var_270], r15
0x18000b93c  test    rcx, rcx
0x18000b93f  jz      short loc_18000B947
0x18000b941  call    cs:__imp_SRCache_Free
0x18000b947  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000b94c  mov     qword ptr [rsp+2A0h+var_280], r15
0x18000b951  test    rcx, rcx
0x18000b954  jz      short loc_18000B95C
0x18000b956  call    cs:__imp_SRCacheContext_Close
0x18000b95c  xor     eax, eax
0x18000b95e  mov     rcx, [rbp+1A0h+var_28]
0x18000b965  xor     rcx, rsp; StackCookie
0x18000b968  call    __security_check_cookie
0x18000b96d  mov     rbx, [rsp+2A0h+arg_10]
0x18000b975  add     rsp, 280h
0x18000b97c  pop     r15
0x18000b97e  pop     r14
0x18000b980  pop     rdi
0x18000b981  pop     rsi
0x18000b982  pop     rbp
0x18000b983  retn
```
