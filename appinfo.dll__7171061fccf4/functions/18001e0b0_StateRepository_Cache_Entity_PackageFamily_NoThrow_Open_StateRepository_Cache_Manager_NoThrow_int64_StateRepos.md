# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001e0b0`
- end: `0x18001e2a0`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `496`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180031ccc`

## callees

- `0x180004cb0`
- `0x18000720c`
- `0x18000b840`
- `0x18000bb40`
- `0x18000dee0`
- `0x18001e0b0`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e206`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e264`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e206`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001e264`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001e16b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001e279`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001e16b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001e279`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001e110`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001e110`

## string_xrefs

- `0x18001e12d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001e14d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18001e1e4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // esi
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  char v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h]
  __int64 v24; // [rsp+260h] [rbp+160h]
  _BYTE *v25; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v18 = &v17;
  v20 = 1;
  v17 = 0;
  v19 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageFamily\\Data", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16);
    v9 = 257;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v16);
LABEL_4:
    v10 = v17;
    v17 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !v17 )
  {
    v8 = -2140733422;
    v9 = 258;
    goto LABEL_3;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a2);
  if ( v8 < 0 )
  {
    v12 = 261;
    goto LABEL_11;
  }
  v16 = v5;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v17, v25);
  if ( v8 < 0 )
  {
    v12 = 262;
    goto LABEL_11;
  }
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         L"PackageFamily\\Data");
  if ( v8 < 0 )
  {
    v12 = 264;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v16);
    v13 = v21;
    v21 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v21;
  v21 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = v17;
  v17 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18001e0b0  push    rbp
0x18001e0b2  push    rbx
0x18001e0b3  push    rsi
0x18001e0b4  push    rdi
0x18001e0b5  push    r14
0x18001e0b7  push    r15
0x18001e0b9  lea     rbp, [rsp-188h]
0x18001e0c1  sub     rsp, 288h
0x18001e0c8  mov     rax, cs:__security_cookie
0x18001e0cf  xor     rax, rsp
0x18001e0d2  mov     [rbp+1B0h+var_40], rax
0x18001e0d9  mov     rcx, [rcx]
0x18001e0dc  lea     rax, [rsp+2B0h+var_280]
0x18001e0e1  mov     rsi, r9
0x18001e0e4  mov     [rsp+2B0h+var_278], rax
0x18001e0e9  mov     rdi, r8
0x18001e0ec  mov     [rsp+2B0h+var_268], 1
0x18001e0f1  mov     r14, rdx
0x18001e0f4  lea     r9, [rsp+2B0h+var_270]
0x18001e0f9  xor     r15d, r15d
0x18001e0fc  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18001e103  xor     r8d, r8d
0x18001e106  mov     [rsp+2B0h+var_280], r15
0x18001e10b  mov     [rsp+2B0h+var_270], r15
0x18001e110  call    cs:__imp_SRCacheContext_Open
0x18001e116  lea     rcx, [rsp+2B0h+var_278]
0x18001e11b  mov     ebx, eax
0x18001e11d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001e122  test    ebx, ebx
0x18001e124  jns     short loc_18001E178
0x18001e126  mov     rcx, [rbp+1B8h]; this
0x18001e12d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001e134  mov     r9d, ebx; char *
0x18001e137  mov     edx, 18Ch; void *
0x18001e13c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e141  mov     edx, 101h; void *
0x18001e146  mov     rcx, [rbp+1B8h]; this
0x18001e14d  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001e154  mov     r9d, ebx; char *
0x18001e157  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e15c  mov     rcx, [rsp+2B0h+var_280]
0x18001e161  mov     [rsp+2B0h+var_280], r15
0x18001e166  test    rcx, rcx
0x18001e169  jz      short loc_18001E171
0x18001e16b  call    cs:__imp_SRCacheContext_Close
0x18001e171  mov     eax, ebx
0x18001e173  jmp     loc_18001E281
0x18001e178  cmp     [rsp+2B0h+var_280], r15
0x18001e17d  setnz   al
0x18001e180  test    al, al
0x18001e182  jnz     short loc_18001E190
0x18001e184  mov     ebx, 80670012h
0x18001e189  mov     edx, 102h
0x18001e18e  jmp     short loc_18001E146
0x18001e190  xor     edx, edx; Val
0x18001e192  mov     [rsp+2B0h+var_260], r15
0x18001e197  mov     r8d, 200h; Size
0x18001e19d  lea     rcx, [rsp+2B0h+var_258]; void *
0x18001e1a2  call    memset_0
0x18001e1a7  lea     rax, [rsp+2B0h+var_258]
0x18001e1ac  mov     [rbp+1B0h+var_58], r15
0x18001e1b3  mov     rdx, r14; unsigned __int64
0x18001e1b6  mov     [rbp+1B0h+var_48], rax
0x18001e1bd  lea     rcx, [rsp+2B0h+var_260]; this
0x18001e1c2  mov     [rbp+1B0h+var_50], 100h
0x18001e1cd  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001e1d2  mov     ebx, eax
0x18001e1d4  test    eax, eax
0x18001e1d6  jns     short loc_18001E211
0x18001e1d8  mov     edx, 105h; void *
0x18001e1dd  mov     rcx, [rbp+1B8h]; this
0x18001e1e4  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001e1eb  mov     r9d, ebx; char *
0x18001e1ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e1f3  mov     rcx, [rsp+2B0h+var_260]
0x18001e1f8  mov     [rsp+2B0h+var_260], r15
0x18001e1fd  test    rcx, rcx
0x18001e200  jz      loc_18001E15C
0x18001e206  call    cs:__imp_SRCache_Free
0x18001e20c  jmp     loc_18001E15C
0x18001e211  mov     r8, [rbp+1B0h+var_48]
0x18001e218  lea     rdx, [rsp+2B0h+var_280]
0x18001e21d  mov     rcx, rdi
0x18001e220  mov     qword ptr [rsp+2B0h+var_290], rsi
0x18001e225  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18001e22a  mov     ebx, eax
0x18001e22c  test    eax, eax
0x18001e22e  jns     short loc_18001E237
0x18001e230  mov     edx, 106h
0x18001e235  jmp     short loc_18001E1DD
0x18001e237  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18001e23e  lea     rcx, [rsp+2B0h+var_280]; this
0x18001e243  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001e248  mov     ebx, eax
0x18001e24a  test    eax, eax
0x18001e24c  jns     short loc_18001E255
0x18001e24e  mov     edx, 108h
0x18001e253  jmp     short loc_18001E1DD
0x18001e255  mov     rcx, [rsp+2B0h+var_260]
0x18001e25a  mov     [rsp+2B0h+var_260], r15
0x18001e25f  test    rcx, rcx
0x18001e262  jz      short loc_18001E26A
0x18001e264  call    cs:__imp_SRCache_Free
0x18001e26a  mov     rcx, [rsp+2B0h+var_280]
0x18001e26f  mov     [rsp+2B0h+var_280], r15
0x18001e274  test    rcx, rcx
0x18001e277  jz      short loc_18001E27F
0x18001e279  call    cs:__imp_SRCacheContext_Close
0x18001e27f  xor     eax, eax
0x18001e281  mov     rcx, [rbp+1B0h+var_40]
0x18001e288  xor     rcx, rsp; StackCookie
0x18001e28b  call    __security_check_cookie
0x18001e290  add     rsp, 288h
0x18001e297  pop     r15
0x18001e299  pop     r14
0x18001e29b  pop     rdi
0x18001e29c  pop     rsi
0x18001e29d  pop     rbx
0x18001e29e  pop     rbp
0x18001e29f  retn
```
