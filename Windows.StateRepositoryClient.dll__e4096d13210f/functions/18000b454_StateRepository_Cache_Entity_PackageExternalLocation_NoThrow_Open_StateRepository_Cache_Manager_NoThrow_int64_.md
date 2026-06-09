# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18000b454`
- end: `0x18000b6e8`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009fa4`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x18000b454`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b51c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b6ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b51c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b6ba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b5fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b6a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b5fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000b6a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b4bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b4bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b630`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b630`

## string_xrefs

- `0x18000b59a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18000b4de`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000b64f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000b4fe`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18000b5d8`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageExternalLocation\\Data", 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>((__int64 **)v23);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v9 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v9 = 251;
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
    v13 = 254;
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
    v13 = 255;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"PackageExternalLocation\\Data");
  if ( v8 < 0 )
  {
    v13 = 257;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x18000b454  mov     [rsp-8+arg_10], rbx
0x18000b459  push    rbp
0x18000b45a  push    rsi
0x18000b45b  push    rdi
0x18000b45c  push    r14
0x18000b45e  push    r15
0x18000b460  lea     rbp, [rsp-180h]
0x18000b468  sub     rsp, 280h
0x18000b46f  mov     rax, cs:__security_cookie
0x18000b476  xor     rax, rsp
0x18000b479  mov     [rbp+1A0h+var_28], rax
0x18000b480  mov     rcx, [rcx]
0x18000b483  lea     rax, [rsp+2A0h+var_280]
0x18000b488  mov     rsi, r9
0x18000b48b  mov     qword ptr [rbp+1A0h+var_50], rax
0x18000b492  mov     rdi, r8
0x18000b495  mov     [rbp+1A0h+var_40], 1
0x18000b49c  mov     r14, rdx
0x18000b49f  lea     r9, [rbp+1A0h+var_48]
0x18000b4a6  xor     r15d, r15d
0x18000b4a9  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18000b4b0  xor     r8d, r8d
0x18000b4b3  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18000b4b8  mov     [rbp+1A0h+var_48], r15
0x18000b4bf  call    cs:__imp_SRCacheContext_Open
0x18000b4c5  lea     rcx, [rbp+1A0h+var_50]
0x18000b4cc  mov     ebx, eax
0x18000b4ce  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000b4d3  test    ebx, ebx
0x18000b4d5  jns     short loc_18000B529
0x18000b4d7  mov     rcx, [rbp+1A8h]; this
0x18000b4de  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b4e5  mov     r9d, ebx; char *
0x18000b4e8  mov     edx, 18Ch; void *
0x18000b4ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4f2  mov     edx, 0FAh; void *
0x18000b4f7  mov     rcx, [rbp+1A8h]; this
0x18000b4fe  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b505  mov     r9d, ebx; char *
0x18000b508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b50d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000b512  mov     qword ptr [rsp+2A0h+var_280], r15
0x18000b517  test    rcx, rcx
0x18000b51a  jz      short loc_18000B522
0x18000b51c  call    cs:__imp_SRCacheContext_Close
0x18000b522  mov     eax, ebx
0x18000b524  jmp     loc_18000B6C2
0x18000b529  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18000b52e  setnz   al
0x18000b531  test    al, al
0x18000b533  jnz     short loc_18000B541
0x18000b535  mov     ebx, 80670012h
0x18000b53a  mov     edx, 0FBh
0x18000b53f  jmp     short loc_18000B4F7
0x18000b541  xor     edx, edx; Val
0x18000b543  mov     [rsp+2A0h+var_270], r15
0x18000b548  mov     r8d, 200h; Size
0x18000b54e  lea     rcx, [rsp+2A0h+var_268]; void *
0x18000b553  call    memset_0
0x18000b558  mov     r9d, 10h
0x18000b55e  mov     [rbp+1A0h+var_68], r15
0x18000b565  lea     rax, [rsp+2A0h+var_268]
0x18000b56a  mov     [rbp+1A0h+var_60], 100h
0x18000b575  lea     rdx, [rbp+1A0h+var_50]
0x18000b57c  mov     [rbp+1A0h+var_58], rax
0x18000b583  mov     rcx, r14
0x18000b586  lea     r8d, [r9+1]
0x18000b58a  call    _o__ui64tow_s_0
0x18000b58f  test    eax, eax
0x18000b591  jz      short loc_18000B5B5
0x18000b593  mov     rcx, [rbp+1A8h]; this
0x18000b59a  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b5a1  mov     ebx, 8000FFFFh
0x18000b5a6  mov     edx, 166h; void *
0x18000b5ab  mov     r9d, ebx; char *
0x18000b5ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5b3  jmp     short loc_18000B5CC
0x18000b5b5  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x18000b5bc  lea     rcx, [rsp+2A0h+var_270]; this
0x18000b5c1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000b5c6  mov     ebx, eax
0x18000b5c8  test    eax, eax
0x18000b5ca  jns     short loc_18000B605
0x18000b5cc  mov     edx, 0FEh; void *
0x18000b5d1  mov     rcx, [rbp+1A8h]; this
0x18000b5d8  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b5df  mov     r9d, ebx; char *
0x18000b5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5e7  mov     rcx, [rsp+2A0h+var_270]
0x18000b5ec  mov     [rsp+2A0h+var_270], r15
0x18000b5f1  test    rcx, rcx
0x18000b5f4  jz      loc_18000B50D
0x18000b5fa  call    cs:__imp_SRCache_Free
0x18000b600  jmp     loc_18000B50D
0x18000b605  mov     rdx, [rbp+1A0h+var_58]
0x18000b60c  lea     r9, [rbp+1A0h+var_48]
0x18000b613  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000b618  xor     r8d, r8d
0x18000b61b  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18000b622  mov     [rbp+1A0h+var_48], r15
0x18000b629  mov     [rbp+1A0h+var_40], 1
0x18000b630  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000b636  lea     rcx, [rbp+1A0h+var_50]
0x18000b63d  mov     ebx, eax
0x18000b63f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000b644  test    ebx, ebx
0x18000b646  jns     short loc_18000B66D
0x18000b648  mov     rcx, [rbp+1A8h]; this
0x18000b64f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b656  mov     r9d, ebx; char *
0x18000b659  mov     edx, 1B0h; void *
0x18000b65e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b663  mov     edx, 0FFh
0x18000b668  jmp     loc_18000B5D1
0x18000b66d  cmp     [rdi], r15
0x18000b670  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18000b677  lea     rcx, [rsp+2A0h+var_280]; this
0x18000b67c  setnz   al
0x18000b67f  mov     [rsi], al
0x18000b681  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000b686  mov     ebx, eax
0x18000b688  test    eax, eax
0x18000b68a  jns     short loc_18000B696
0x18000b68c  mov     edx, 101h
0x18000b691  jmp     loc_18000B5D1
0x18000b696  mov     rcx, [rsp+2A0h+var_270]
0x18000b69b  mov     [rsp+2A0h+var_270], r15
0x18000b6a0  test    rcx, rcx
0x18000b6a3  jz      short loc_18000B6AB
0x18000b6a5  call    cs:__imp_SRCache_Free
0x18000b6ab  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000b6b0  mov     qword ptr [rsp+2A0h+var_280], r15
0x18000b6b5  test    rcx, rcx
0x18000b6b8  jz      short loc_18000B6C0
0x18000b6ba  call    cs:__imp_SRCacheContext_Close
0x18000b6c0  xor     eax, eax
0x18000b6c2  mov     rcx, [rbp+1A0h+var_28]
0x18000b6c9  xor     rcx, rsp; StackCookie
0x18000b6cc  call    __security_check_cookie
0x18000b6d1  mov     rbx, [rsp+2A0h+arg_10]
0x18000b6d9  add     rsp, 280h
0x18000b6e0  pop     r15
0x18000b6e2  pop     r14
0x18000b6e4  pop     rdi
0x18000b6e5  pop     rsi
0x18000b6e6  pop     rbp
0x18000b6e7  retn
```
