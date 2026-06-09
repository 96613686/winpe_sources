# StateRepository::Cache::Entity::Package_NoThrow::ExistsByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)

- ea: `0x1800302f4`
- end: `0x1800305a0`
- name: `?ExistsByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_N@Z`
- size: `684`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18005ac6c`

## callees

- `0x180016b10`
- `0x18001ffa0`
- `0x18002f59c`
- `0x1800302f4`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`
- `0x18005a610`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180030480`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180030480`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180030352`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180030352`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800303ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800304df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030551`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003057b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800303ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800304df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030551`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003057b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030566`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030448`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030566`

## string_xrefs

- `0x18003038f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180030421`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800304bd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003036f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003049d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::ExistsByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        bool *a3)
{
  __int64 v3; // rcx
  int IsEmpty; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v22 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  v18 = 0;
  v20 = &v18;
  v21 = 0;
  IsEmpty = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v17);
    v7 = 1065;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)IsEmpty,
      v17);
LABEL_4:
    v8 = v18;
    v18 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)IsEmpty;
  }
  if ( !v18 )
  {
    IsEmpty = -2140733422;
    v7 = 1066;
    goto LABEL_3;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  IsEmpty = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v17);
LABEL_11:
    v11 = v23;
    v23 = 0;
    if ( v11 )
      SRCache_Free();
    goto LABEL_4;
  }
  v20 = &v19;
  v19 = 0;
  v21 = 0;
  v22 = 1;
  IsEmpty = SRCacheContext_OpenSubContext(v18, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v17);
    v12 = 1073;
    goto LABEL_15;
  }
  if ( v19 )
  {
    LOBYTE(v17) = 0;
    IsEmpty = StateRepository::Cache::Context_NoThrow::IsEmpty(
                (StateRepository::Cache::Context_NoThrow *)&v19,
                (bool *)&v17);
    if ( IsEmpty < 0 )
    {
      v12 = 1077;
      goto LABEL_15;
    }
    *a3 = (_BYTE)v17 == 0;
  }
  IsEmpty = StateRepository::Cache::Context_NoThrow::AddToCache(
              (StateRepository::Cache::Context_NoThrow *)&v18,
              L"Package\\Index\\PackageFullName");
  if ( IsEmpty < 0 )
  {
    v12 = 1081;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)IsEmpty,
      v17);
    v13 = v19;
    v19 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_11;
  }
  v14 = v19;
  v19 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v23;
  v23 = 0;
  if ( v15 )
    SRCache_Free();
  v16 = v18;
  v18 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x1800302f4  push    rbp
0x1800302f6  push    rbx
0x1800302f7  push    rsi
0x1800302f8  push    rdi
0x1800302f9  push    r14
0x1800302fb  lea     rbp, [rsp-180h]
0x180030303  sub     rsp, 280h
0x18003030a  mov     rax, cs:__security_cookie
0x180030311  xor     rax, rsp
0x180030314  mov     [rbp+1A0h+var_30], rax
0x18003031b  xor     r14d, r14d
0x18003031e  mov     [rsp+2A0h+var_258], 1
0x180030323  mov     [r8], r14b
0x180030326  lea     rax, [rsp+2A0h+var_278]
0x18003032b  mov     rcx, [rcx]
0x18003032e  lea     r9, [rsp+2A0h+var_260]
0x180030333  mov     rdi, r8
0x180030336  mov     [rsp+2A0h+var_278], r14
0x18003033b  mov     rsi, rdx
0x18003033e  mov     [rsp+2A0h+var_268], rax
0x180030343  xor     r8d, r8d
0x180030346  mov     [rsp+2A0h+var_260], r14
0x18003034b  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180030352  call    cs:__imp_SRCacheContext_Open
0x180030358  lea     rcx, [rsp+2A0h+var_268]
0x18003035d  mov     ebx, eax
0x18003035f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180030364  test    ebx, ebx
0x180030366  jns     short loc_1800303BA
0x180030368  mov     rcx, [rbp+1A8h]; this
0x18003036f  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030376  mov     r9d, ebx; char *
0x180030379  mov     edx, 18Ch; void *
0x18003037e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030383  mov     edx, 429h; void *
0x180030388  mov     rcx, [rbp+1A8h]; this
0x18003038f  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030396  mov     r9d, ebx; char *
0x180030399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003039e  mov     rcx, [rsp+2A0h+var_278]
0x1800303a3  mov     [rsp+2A0h+var_278], r14
0x1800303a8  test    rcx, rcx
0x1800303ab  jz      short loc_1800303B3
0x1800303ad  call    cs:__imp_SRCacheContext_Close
0x1800303b3  mov     eax, ebx
0x1800303b5  jmp     loc_180030583
0x1800303ba  cmp     [rsp+2A0h+var_278], r14
0x1800303bf  setnz   al
0x1800303c2  test    al, al
0x1800303c4  jnz     short loc_1800303D2
0x1800303c6  mov     ebx, 80670012h
0x1800303cb  mov     edx, 42Ah
0x1800303d0  jmp     short loc_180030388
0x1800303d2  xor     edx, edx; Val
0x1800303d4  mov     [rsp+2A0h+var_250], r14
0x1800303d9  mov     r8d, 200h; Size
0x1800303df  lea     rcx, [rsp+2A0h+var_248]; void *
0x1800303e4  call    memset_0
0x1800303e9  lea     rax, [rsp+2A0h+var_248]
0x1800303ee  mov     [rbp+1A0h+var_48], r14
0x1800303f5  mov     rdx, rsi; unsigned __int16 *
0x1800303f8  mov     [rbp+1A0h+var_38], rax
0x1800303ff  lea     rcx, [rsp+2A0h+var_250]; this
0x180030404  mov     [rbp+1A0h+var_40], 100h
0x18003040f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180030414  mov     ebx, eax
0x180030416  test    eax, eax
0x180030418  jns     short loc_180030453
0x18003041a  mov     rcx, [rbp+1A8h]; this
0x180030421  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030428  mov     r9d, eax; char *
0x18003042b  mov     edx, 42Dh; void *
0x180030430  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030435  mov     rcx, [rsp+2A0h+var_250]
0x18003043a  mov     [rsp+2A0h+var_250], r14
0x18003043f  test    rcx, rcx
0x180030442  jz      loc_18003039E
0x180030448  call    cs:__imp_SRCache_Free
0x18003044e  jmp     loc_18003039E
0x180030453  mov     rdx, [rbp+1A0h+var_38]
0x18003045a  lea     rax, [rsp+2A0h+var_270]
0x18003045f  mov     rcx, [rsp+2A0h+var_278]
0x180030464  lea     r9, [rsp+2A0h+var_260]
0x180030469  xor     r8d, r8d
0x18003046c  mov     [rsp+2A0h+var_268], rax
0x180030471  mov     [rsp+2A0h+var_270], r14
0x180030476  mov     [rsp+2A0h+var_260], r14
0x18003047b  mov     [rsp+2A0h+var_258], 1
0x180030480  call    cs:__imp_SRCacheContext_OpenSubContext
0x180030486  lea     rcx, [rsp+2A0h+var_268]
0x18003048b  mov     ebx, eax
0x18003048d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180030492  test    ebx, ebx
0x180030494  jns     short loc_1800304EA
0x180030496  mov     rcx, [rbp+1A8h]; this
0x18003049d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800304a4  mov     r9d, ebx; char *
0x1800304a7  mov     edx, 1B0h; void *
0x1800304ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304b1  mov     edx, 431h; void *
0x1800304b6  mov     rcx, [rbp+1A8h]; this
0x1800304bd  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800304c4  mov     r9d, ebx; char *
0x1800304c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304cc  mov     rcx, [rsp+2A0h+var_270]
0x1800304d1  mov     [rsp+2A0h+var_270], r14
0x1800304d6  test    rcx, rcx
0x1800304d9  jz      loc_180030435
0x1800304df  call    cs:__imp_SRCacheContext_Close
0x1800304e5  jmp     loc_180030435
0x1800304ea  cmp     [rsp+2A0h+var_270], r14
0x1800304ef  setnz   al
0x1800304f2  test    al, al
0x1800304f4  jz      short loc_180030521
0x1800304f6  lea     rdx, [rsp+2A0h+var_280]; bool *
0x1800304fb  mov     byte ptr [rsp+2A0h+var_280], r14b
0x180030500  lea     rcx, [rsp+2A0h+var_270]; this
0x180030505  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x18003050a  mov     ebx, eax
0x18003050c  test    eax, eax
0x18003050e  jns     short loc_180030517
0x180030510  mov     edx, 435h
0x180030515  jmp     short loc_1800304B6
0x180030517  cmp     byte ptr [rsp+2A0h+var_280], r14b
0x18003051c  setz    al
0x18003051f  mov     [rdi], al
0x180030521  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180030528  lea     rcx, [rsp+2A0h+var_278]; this
0x18003052d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180030532  mov     ebx, eax
0x180030534  test    eax, eax
0x180030536  jns     short loc_180030542
0x180030538  mov     edx, 439h
0x18003053d  jmp     loc_1800304B6
0x180030542  mov     rcx, [rsp+2A0h+var_270]
0x180030547  mov     [rsp+2A0h+var_270], r14
0x18003054c  test    rcx, rcx
0x18003054f  jz      short loc_180030557
0x180030551  call    cs:__imp_SRCacheContext_Close
0x180030557  mov     rcx, [rsp+2A0h+var_250]
0x18003055c  mov     [rsp+2A0h+var_250], r14
0x180030561  test    rcx, rcx
0x180030564  jz      short loc_18003056C
0x180030566  call    cs:__imp_SRCache_Free
0x18003056c  mov     rcx, [rsp+2A0h+var_278]
0x180030571  mov     [rsp+2A0h+var_278], r14
0x180030576  test    rcx, rcx
0x180030579  jz      short loc_180030581
0x18003057b  call    cs:__imp_SRCacheContext_Close
0x180030581  xor     eax, eax
0x180030583  mov     rcx, [rbp+1A0h+var_30]
0x18003058a  xor     rcx, rsp; StackCookie
0x18003058d  call    __security_check_cookie
0x180030592  add     rsp, 280h
0x180030599  pop     r14
0x18003059b  pop     rdi
0x18003059c  pop     rsi
0x18003059d  pop     rbx
0x18003059e  pop     rbp
0x18003059f  retn
```
