# StateRepository::Cache::Entity::DependencyGraph_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18018a450`
- end: `0x18018a68d`
- name: `?Open@DependencyGraph_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180270814`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18018a450`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018a5d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18018a5d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018a50e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018a65f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018a50e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18018a65f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018a5a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018a64a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018a5a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18018a64a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018a4b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18018a4b3`

## string_xrefs

- `0x18018a4d0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18018a5f4`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18018a4f0`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DependencyGraph.hpp`
- `0x18018a587`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DependencyGraph_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"DependencyGraph\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 189;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DependencyGraph.hpp",
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
    v9 = 190;
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
    v14 = 193;
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
    v14 = 194;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"DependencyGraph\\Data");
  if ( v8 < 0 )
  {
    v14 = 196;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DependencyGraph.hpp",
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
0x18018a450  mov     [rsp-8+arg_10], rbx
0x18018a455  push    rbp
0x18018a456  push    rsi
0x18018a457  push    rdi
0x18018a458  push    r14
0x18018a45a  push    r15
0x18018a45c  lea     rbp, [rsp-170h]
0x18018a464  sub     rsp, 270h
0x18018a46b  mov     rax, cs:__security_cookie
0x18018a472  xor     rax, rsp
0x18018a475  mov     [rbp+190h+var_30], rax
0x18018a47c  mov     rcx, [rcx]
0x18018a47f  lea     rax, [rsp+290h+var_270]
0x18018a484  mov     rsi, r9
0x18018a487  mov     [rsp+290h+var_268], rax
0x18018a48c  mov     rdi, r8
0x18018a48f  mov     [rsp+290h+var_258], 1
0x18018a494  mov     r14, rdx
0x18018a497  lea     r9, [rsp+290h+var_260]
0x18018a49c  xor     r15d, r15d
0x18018a49f  lea     rdx, aDependencygrap_16; "DependencyGraph\\Data"
0x18018a4a6  xor     r8d, r8d
0x18018a4a9  mov     qword ptr [rsp+290h+var_270], r15; int
0x18018a4ae  mov     [rsp+290h+var_260], r15
0x18018a4b3  call    cs:__imp_SRCacheContext_Open
0x18018a4b9  lea     rcx, [rsp+290h+var_268]
0x18018a4be  mov     ebx, eax
0x18018a4c0  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018a4c5  test    ebx, ebx
0x18018a4c7  jns     short loc_18018A51B
0x18018a4c9  mov     rcx, [rbp+198h]; this
0x18018a4d0  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18018a4d7  mov     r9d, ebx; char *
0x18018a4da  mov     edx, 18Ch; void *
0x18018a4df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018a4e4  mov     edx, 0BDh; void *
0x18018a4e9  mov     rcx, [rbp+198h]; this
0x18018a4f0  lea     r8, aOnecoreBaseApp_296; "onecore\\base\\appmodel\\StateRepositor"...
0x18018a4f7  mov     r9d, ebx; char *
0x18018a4fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018a4ff  mov     rcx, qword ptr [rsp+290h+var_270]
0x18018a504  mov     qword ptr [rsp+290h+var_270], r15
0x18018a509  test    rcx, rcx
0x18018a50c  jz      short loc_18018A514
0x18018a50e  call    cs:__imp_SRCacheContext_Close
0x18018a514  mov     eax, ebx
0x18018a516  jmp     loc_18018A667
0x18018a51b  cmp     qword ptr [rsp+290h+var_270], r15
0x18018a520  setnz   al
0x18018a523  test    al, al
0x18018a525  jnz     short loc_18018A533
0x18018a527  mov     ebx, 80670012h
0x18018a52c  mov     edx, 0BEh
0x18018a531  jmp     short loc_18018A4E9
0x18018a533  xor     edx, edx; Val
0x18018a535  mov     [rsp+290h+var_250], r15
0x18018a53a  mov     r8d, 200h; Size
0x18018a540  lea     rcx, [rsp+290h+var_248]; void *
0x18018a545  call    memset_0
0x18018a54a  lea     rax, [rsp+290h+var_248]
0x18018a54f  mov     [rbp+190h+var_48], r15
0x18018a556  mov     rdx, r14; unsigned __int64
0x18018a559  mov     [rbp+190h+var_38], rax
0x18018a560  lea     rcx, [rsp+290h+var_250]; this
0x18018a565  mov     [rbp+190h+var_40], 100h
0x18018a570  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18018a575  mov     ebx, eax
0x18018a577  test    eax, eax
0x18018a579  jns     short loc_18018A5B4
0x18018a57b  mov     edx, 0C1h; void *
0x18018a580  mov     rcx, [rbp+198h]; this
0x18018a587  lea     r8, aOnecoreBaseApp_296; "onecore\\base\\appmodel\\StateRepositor"...
0x18018a58e  mov     r9d, ebx; char *
0x18018a591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018a596  mov     rcx, [rsp+290h+var_250]
0x18018a59b  mov     [rsp+290h+var_250], r15
0x18018a5a0  test    rcx, rcx
0x18018a5a3  jz      loc_18018A4FF
0x18018a5a9  call    cs:__imp_SRCache_Free
0x18018a5af  jmp     loc_18018A4FF
0x18018a5b4  mov     rdx, [rbp+190h+var_38]
0x18018a5bb  lea     r9, [rsp+290h+var_260]
0x18018a5c0  mov     rcx, qword ptr [rsp+290h+var_270]
0x18018a5c5  xor     r8d, r8d
0x18018a5c8  mov     [rsp+290h+var_268], rdi
0x18018a5cd  mov     [rsp+290h+var_260], r15
0x18018a5d2  mov     [rsp+290h+var_258], 1
0x18018a5d7  call    cs:__imp_SRCacheContext_OpenSubContext
0x18018a5dd  lea     rcx, [rsp+290h+var_268]
0x18018a5e2  mov     ebx, eax
0x18018a5e4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18018a5e9  test    ebx, ebx
0x18018a5eb  jns     short loc_18018A612
0x18018a5ed  mov     rcx, [rbp+198h]; this
0x18018a5f4  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18018a5fb  mov     r9d, ebx; char *
0x18018a5fe  mov     edx, 1B0h; void *
0x18018a603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018a608  mov     edx, 0C2h
0x18018a60d  jmp     loc_18018A580
0x18018a612  cmp     [rdi], r15
0x18018a615  lea     rdx, aDependencygrap_16; "DependencyGraph\\Data"
0x18018a61c  lea     rcx, [rsp+290h+var_270]; this
0x18018a621  setnz   al
0x18018a624  mov     [rsi], al
0x18018a626  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18018a62b  mov     ebx, eax
0x18018a62d  test    eax, eax
0x18018a62f  jns     short loc_18018A63B
0x18018a631  mov     edx, 0C4h
0x18018a636  jmp     loc_18018A580
0x18018a63b  mov     rcx, [rsp+290h+var_250]
0x18018a640  mov     [rsp+290h+var_250], r15
0x18018a645  test    rcx, rcx
0x18018a648  jz      short loc_18018A650
0x18018a64a  call    cs:__imp_SRCache_Free
0x18018a650  mov     rcx, qword ptr [rsp+290h+var_270]
0x18018a655  mov     qword ptr [rsp+290h+var_270], r15
0x18018a65a  test    rcx, rcx
0x18018a65d  jz      short loc_18018A665
0x18018a65f  call    cs:__imp_SRCacheContext_Close
0x18018a665  xor     eax, eax
0x18018a667  mov     rcx, [rbp+190h+var_30]
0x18018a66e  xor     rcx, rsp; StackCookie
0x18018a671  call    __security_check_cookie
0x18018a676  mov     rbx, [rsp+290h+arg_10]
0x18018a67e  add     rsp, 270h
0x18018a685  pop     r15
0x18018a687  pop     r14
0x18018a689  pop     rdi
0x18018a68a  pop     rsi
0x18018a68b  pop     rbp
0x18018a68c  retn
```
