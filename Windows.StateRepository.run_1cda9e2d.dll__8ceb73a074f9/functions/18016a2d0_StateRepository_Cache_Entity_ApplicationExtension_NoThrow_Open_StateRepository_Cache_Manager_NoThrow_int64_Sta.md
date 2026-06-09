# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18016a2d0`
- end: `0x18016a50d`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180268408`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18016a2d0`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18016a457`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18016a457`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016a38e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016a4df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016a38e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016a4df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016a429`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016a4ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016a429`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016a4ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016a333`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016a333`

## string_xrefs

- `0x18016a31f`: `ApplicationExtension\Data`
- `0x18016a495`: `ApplicationExtension\Data`
- `0x18016a350`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016a474`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016a370`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x18016a407`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
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
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-ApplicationExtension.hpp",
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
    v9 = 365;
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
    v12 = 368;
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
    v12 = 369;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 371;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-ApplicationExtension.hpp",
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
0x18016a2d0  mov     [rsp-8+arg_10], rbx
0x18016a2d5  push    rbp
0x18016a2d6  push    rsi
0x18016a2d7  push    rdi
0x18016a2d8  push    r14
0x18016a2da  push    r15
0x18016a2dc  lea     rbp, [rsp-170h]
0x18016a2e4  sub     rsp, 270h
0x18016a2eb  mov     rax, cs:__security_cookie
0x18016a2f2  xor     rax, rsp
0x18016a2f5  mov     [rbp+190h+var_30], rax
0x18016a2fc  mov     rcx, [rcx]
0x18016a2ff  lea     rax, [rsp+290h+var_270]
0x18016a304  mov     rsi, r9
0x18016a307  mov     [rsp+290h+var_268], rax
0x18016a30c  mov     rdi, r8
0x18016a30f  mov     [rsp+290h+var_258], 1
0x18016a314  mov     r14, rdx
0x18016a317  lea     r9, [rsp+290h+var_260]
0x18016a31c  xor     r15d, r15d
0x18016a31f  lea     rdx, aApplicationext_30; "ApplicationExtension\\Data"
0x18016a326  xor     r8d, r8d
0x18016a329  mov     qword ptr [rsp+290h+var_270], r15; int
0x18016a32e  mov     [rsp+290h+var_260], r15
0x18016a333  call    cs:__imp_SRCacheContext_Open
0x18016a339  lea     rcx, [rsp+290h+var_268]
0x18016a33e  mov     ebx, eax
0x18016a340  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016a345  test    ebx, ebx
0x18016a347  jns     short loc_18016A39B
0x18016a349  mov     rcx, [rbp+198h]; this
0x18016a350  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016a357  mov     r9d, ebx; char *
0x18016a35a  mov     edx, 18Ch; void *
0x18016a35f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016a364  mov     edx, 16Ch; void *
0x18016a369  mov     rcx, [rbp+198h]; this
0x18016a370  lea     r8, aOnecoreBaseApp_294; "onecore\\base\\appmodel\\StateRepositor"...
0x18016a377  mov     r9d, ebx; char *
0x18016a37a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016a37f  mov     rcx, qword ptr [rsp+290h+var_270]
0x18016a384  mov     qword ptr [rsp+290h+var_270], r15
0x18016a389  test    rcx, rcx
0x18016a38c  jz      short loc_18016A394
0x18016a38e  call    cs:__imp_SRCacheContext_Close
0x18016a394  mov     eax, ebx
0x18016a396  jmp     loc_18016A4E7
0x18016a39b  cmp     qword ptr [rsp+290h+var_270], r15
0x18016a3a0  setnz   al
0x18016a3a3  test    al, al
0x18016a3a5  jnz     short loc_18016A3B3
0x18016a3a7  mov     ebx, 80670012h
0x18016a3ac  mov     edx, 16Dh
0x18016a3b1  jmp     short loc_18016A369
0x18016a3b3  xor     edx, edx; Val
0x18016a3b5  mov     [rsp+290h+var_250], r15
0x18016a3ba  mov     r8d, 200h; Size
0x18016a3c0  lea     rcx, [rsp+290h+var_248]; void *
0x18016a3c5  call    memset_0
0x18016a3ca  lea     rax, [rsp+290h+var_248]
0x18016a3cf  mov     [rbp+190h+var_48], r15
0x18016a3d6  mov     rdx, r14; unsigned __int64
0x18016a3d9  mov     [rbp+190h+var_38], rax
0x18016a3e0  lea     rcx, [rsp+290h+var_250]; this
0x18016a3e5  mov     [rbp+190h+var_40], 100h
0x18016a3f0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18016a3f5  mov     ebx, eax
0x18016a3f7  test    eax, eax
0x18016a3f9  jns     short loc_18016A434
0x18016a3fb  mov     edx, 170h; void *
0x18016a400  mov     rcx, [rbp+198h]; this
0x18016a407  lea     r8, aOnecoreBaseApp_294; "onecore\\base\\appmodel\\StateRepositor"...
0x18016a40e  mov     r9d, ebx; char *
0x18016a411  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016a416  mov     rcx, [rsp+290h+var_250]
0x18016a41b  mov     [rsp+290h+var_250], r15
0x18016a420  test    rcx, rcx
0x18016a423  jz      loc_18016A37F
0x18016a429  call    cs:__imp_SRCache_Free
0x18016a42f  jmp     loc_18016A37F
0x18016a434  mov     rdx, [rbp+190h+var_38]
0x18016a43b  lea     r9, [rsp+290h+var_260]
0x18016a440  mov     rcx, qword ptr [rsp+290h+var_270]
0x18016a445  xor     r8d, r8d
0x18016a448  mov     [rsp+290h+var_268], rdi
0x18016a44d  mov     [rsp+290h+var_260], r15
0x18016a452  mov     [rsp+290h+var_258], 1
0x18016a457  call    cs:__imp_SRCacheContext_OpenSubContext
0x18016a45d  lea     rcx, [rsp+290h+var_268]
0x18016a462  mov     ebx, eax
0x18016a464  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016a469  test    ebx, ebx
0x18016a46b  jns     short loc_18016A492
0x18016a46d  mov     rcx, [rbp+198h]; this
0x18016a474  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016a47b  mov     r9d, ebx; char *
0x18016a47e  mov     edx, 1B0h; void *
0x18016a483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016a488  mov     edx, 171h
0x18016a48d  jmp     loc_18016A400
0x18016a492  cmp     [rdi], r15
0x18016a495  lea     rdx, aApplicationext_30; "ApplicationExtension\\Data"
0x18016a49c  lea     rcx, [rsp+290h+var_270]; this
0x18016a4a1  setnz   al
0x18016a4a4  mov     [rsi], al
0x18016a4a6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18016a4ab  mov     ebx, eax
0x18016a4ad  test    eax, eax
0x18016a4af  jns     short loc_18016A4BB
0x18016a4b1  mov     edx, 173h
0x18016a4b6  jmp     loc_18016A400
0x18016a4bb  mov     rcx, [rsp+290h+var_250]
0x18016a4c0  mov     [rsp+290h+var_250], r15
0x18016a4c5  test    rcx, rcx
0x18016a4c8  jz      short loc_18016A4D0
0x18016a4ca  call    cs:__imp_SRCache_Free
0x18016a4d0  mov     rcx, qword ptr [rsp+290h+var_270]
0x18016a4d5  mov     qword ptr [rsp+290h+var_270], r15
0x18016a4da  test    rcx, rcx
0x18016a4dd  jz      short loc_18016A4E5
0x18016a4df  call    cs:__imp_SRCacheContext_Close
0x18016a4e5  xor     eax, eax
0x18016a4e7  mov     rcx, [rbp+190h+var_30]
0x18016a4ee  xor     rcx, rsp; StackCookie
0x18016a4f1  call    __security_check_cookie
0x18016a4f6  mov     rbx, [rsp+290h+arg_10]
0x18016a4fe  add     rsp, 270h
0x18016a505  pop     r15
0x18016a507  pop     r14
0x18016a509  pop     rdi
0x18016a50a  pop     rsi
0x18016a50b  pop     rbp
0x18016a50c  retn
```
