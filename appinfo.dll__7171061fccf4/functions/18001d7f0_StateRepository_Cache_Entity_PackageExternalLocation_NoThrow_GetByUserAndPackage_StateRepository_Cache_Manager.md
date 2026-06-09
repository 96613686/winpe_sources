# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,__int64 &)

- ea: `0x18001d7f0`
- end: `0x18001dabd`
- name: `?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_J@Z`
- size: `717`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180031f90`

## callees

- `0x180004cb0`
- `0x18000720c`
- `0x180007780`
- `0x18000b840`
- `0x18000bb40`
- `0x18000d450`
- `0x18000dee0`
- `0x18001d7f0`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d977`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001da81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d977`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001da81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001d8de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001da11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001da6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001da96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001d8de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001da11`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001da6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001da96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001d87f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001d87f`

## string_xrefs

- `0x18001d89c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001d834`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001d8bc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001d955`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001d9ef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[512]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+268h] [rbp+168h]
  __int64 v28; // [rsp+270h] [rbp+170h]
  _BYTE *v29; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)0x80070057LL,
      v18);
    return (unsigned int)v6;
  }
  v8 = *(_QWORD *)a1;
  v22 = &v20;
  v20 = 0;
  v23 = 0;
  v24 = 1;
  v6 = SRCacheContext_Open(v8, L"PackageExternalLocation\\Index\\UserAndPackage", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v18);
    v9 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v6,
      v18);
LABEL_7:
    v10 = v20;
    v20 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v6;
  }
  if ( !v20 )
  {
    v6 = -2140733422;
    v9 = 186;
    goto LABEL_6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  if ( v6 < 0 )
  {
    v11 = 189;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v6,
      v18);
LABEL_14:
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_7;
  }
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25);
  if ( v6 < 0 )
  {
    v11 = 190;
    goto LABEL_13;
  }
  v6 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
  if ( v6 < 0 )
  {
    v11 = 191;
    goto LABEL_13;
  }
  v21 = 0;
  LOBYTE(v19) = 0;
  v6 = StateRepository::Cache::Context_NoThrow::OpenSubContext(&v21, &v20, v29);
  if ( v6 < 0 )
  {
    v13 = 195;
    goto LABEL_22;
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v20,
         L"PackageExternalLocation\\Index\\UserAndPackage");
  if ( v6 < 0 )
  {
    v13 = 201;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v6,
      (int)&v19);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    goto LABEL_14;
  }
  v15 = v21;
  v21 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  v16 = v25;
  v25 = 0;
  if ( v16 )
    SRCache_Free(v16);
  v17 = v20;
  v20 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x18001d7f0  push    rbp
0x18001d7f2  push    rbx
0x18001d7f3  push    rsi
0x18001d7f4  push    rdi
0x18001d7f5  push    r14
0x18001d7f7  push    r15
0x18001d7f9  lea     rbp, [rsp-198h]
0x18001d801  sub     rsp, 298h
0x18001d808  mov     rax, cs:__security_cookie
0x18001d80f  xor     rax, rsp
0x18001d812  mov     [rbp+1C0h+var_40], rax
0x18001d819  xor     r15d, r15d
0x18001d81c  mov     rsi, r9
0x18001d81f  mov     [r9], r15
0x18001d822  mov     rdi, r8
0x18001d825  mov     r14, rdx
0x18001d828  test    r8, r8
0x18001d82b  jnz     short loc_18001D854
0x18001d82d  mov     rcx, [rbp+1C8h]; this
0x18001d834  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d83b  mov     ebx, 80070057h
0x18001d840  mov     edx, 0B5h; void *
0x18001d845  mov     r9d, ebx; char *
0x18001d848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d84d  mov     eax, ebx
0x18001d84f  jmp     loc_18001DA9E
0x18001d854  mov     rcx, [rcx]
0x18001d857  lea     rax, [rsp+2C0h+var_288]
0x18001d85c  lea     r9, [rsp+2C0h+var_270]
0x18001d861  mov     [rsp+2C0h+var_278], rax
0x18001d866  xor     r8d, r8d
0x18001d869  mov     [rsp+2C0h+var_288], r15
0x18001d86e  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18001d875  mov     [rsp+2C0h+var_270], r15
0x18001d87a  mov     [rsp+2C0h+var_268], 1
0x18001d87f  call    cs:__imp_SRCacheContext_Open
0x18001d885  lea     rcx, [rsp+2C0h+var_278]
0x18001d88a  mov     ebx, eax
0x18001d88c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001d891  test    ebx, ebx
0x18001d893  jns     short loc_18001D8E9
0x18001d895  mov     rcx, [rbp+1C8h]; this
0x18001d89c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d8a3  mov     r9d, ebx; char *
0x18001d8a6  mov     edx, 18Ch; void *
0x18001d8ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d8b0  mov     edx, 0B9h; void *
0x18001d8b5  mov     rcx, [rbp+1C8h]; this
0x18001d8bc  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d8c3  mov     r9d, ebx; char *
0x18001d8c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d8cb  mov     rcx, [rsp+2C0h+var_288]
0x18001d8d0  mov     [rsp+2C0h+var_288], r15
0x18001d8d5  test    rcx, rcx
0x18001d8d8  jz      loc_18001D84D
0x18001d8de  call    cs:__imp_SRCacheContext_Close
0x18001d8e4  jmp     loc_18001D84D
0x18001d8e9  cmp     [rsp+2C0h+var_288], r15
0x18001d8ee  setnz   al
0x18001d8f1  test    al, al
0x18001d8f3  jnz     short loc_18001D901
0x18001d8f5  mov     ebx, 80670012h
0x18001d8fa  mov     edx, 0BAh
0x18001d8ff  jmp     short loc_18001D8B5
0x18001d901  xor     edx, edx; Val
0x18001d903  mov     [rsp+2C0h+var_260], r15
0x18001d908  mov     r8d, 200h; Size
0x18001d90e  lea     rcx, [rsp+2C0h+var_258]; void *
0x18001d913  call    memset_0
0x18001d918  lea     rax, [rsp+2C0h+var_258]
0x18001d91d  mov     [rbp+1C0h+var_58], r15
0x18001d924  mov     rdx, r14; unsigned __int64
0x18001d927  mov     [rbp+1C0h+var_48], rax
0x18001d92e  lea     rcx, [rsp+2C0h+var_260]; this
0x18001d933  mov     [rbp+1C0h+var_50], 100h
0x18001d93e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001d943  mov     ebx, eax
0x18001d945  test    eax, eax
0x18001d947  jns     short loc_18001D982
0x18001d949  mov     edx, 0BDh; void *
0x18001d94e  mov     rcx, [rbp+1C8h]; this
0x18001d955  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d95c  mov     r9d, ebx; char *
0x18001d95f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d964  mov     rcx, [rsp+2C0h+var_260]
0x18001d969  mov     [rsp+2C0h+var_260], r15
0x18001d96e  test    rcx, rcx
0x18001d971  jz      loc_18001D8CB
0x18001d977  call    cs:__imp_SRCache_Free
0x18001d97d  jmp     loc_18001D8CB
0x18001d982  lea     rcx, [rsp+2C0h+var_260]; this
0x18001d987  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x18001d98c  mov     ebx, eax
0x18001d98e  test    eax, eax
0x18001d990  jns     short loc_18001D999
0x18001d992  mov     edx, 0BEh
0x18001d997  jmp     short loc_18001D94E
0x18001d999  mov     rdx, rdi; unsigned __int64
0x18001d99c  lea     rcx, [rsp+2C0h+var_260]; this
0x18001d9a1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001d9a6  mov     ebx, eax
0x18001d9a8  test    eax, eax
0x18001d9aa  jns     short loc_18001D9B3
0x18001d9ac  mov     edx, 0BFh
0x18001d9b1  jmp     short loc_18001D94E
0x18001d9b3  mov     r8, [rbp+1C0h+var_48]
0x18001d9ba  lea     rax, [rsp+2C0h+var_290]
0x18001d9bf  lea     rdx, [rsp+2C0h+var_288]
0x18001d9c4  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18001d9c9  lea     rcx, [rsp+2C0h+var_280]
0x18001d9ce  mov     [rsp+2C0h+var_280], r15
0x18001d9d3  mov     byte ptr [rsp+2C0h+var_290], r15b
0x18001d9d8  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18001d9dd  mov     ebx, eax
0x18001d9df  test    eax, eax
0x18001d9e1  jns     short loc_18001DA1C
0x18001d9e3  mov     edx, 0C3h; void *
0x18001d9e8  mov     rcx, [rbp+1C8h]; this
0x18001d9ef  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d9f6  mov     r9d, ebx; char *
0x18001d9f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9fe  mov     rcx, [rsp+2C0h+var_280]
0x18001da03  mov     [rsp+2C0h+var_280], r15
0x18001da08  test    rcx, rcx
0x18001da0b  jz      loc_18001D964
0x18001da11  call    cs:__imp_SRCacheContext_Close
0x18001da17  jmp     loc_18001D964
0x18001da1c  cmp     byte ptr [rsp+2C0h+var_290], r15b
0x18001da21  jz      short loc_18001DA3F
0x18001da23  mov     r8, rsi; __int64 *
0x18001da26  lea     rcx, [rsp+2C0h+var_280]; this
0x18001da2b  xor     edx, edx; int
0x18001da2d  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18001da32  mov     ebx, eax
0x18001da34  test    eax, eax
0x18001da36  jns     short loc_18001DA3F
0x18001da38  mov     edx, 0C6h
0x18001da3d  jmp     short loc_18001D9E8
0x18001da3f  lea     rdx, aPackageexterna_0; "PackageExternalLocation\\Index\\UserAnd"...
0x18001da46  lea     rcx, [rsp+2C0h+var_288]; this
0x18001da4b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001da50  mov     ebx, eax
0x18001da52  test    eax, eax
0x18001da54  jns     short loc_18001DA5D
0x18001da56  mov     edx, 0C9h
0x18001da5b  jmp     short loc_18001D9E8
0x18001da5d  mov     rcx, [rsp+2C0h+var_280]
0x18001da62  mov     [rsp+2C0h+var_280], r15
0x18001da67  test    rcx, rcx
0x18001da6a  jz      short loc_18001DA72
0x18001da6c  call    cs:__imp_SRCacheContext_Close
0x18001da72  mov     rcx, [rsp+2C0h+var_260]
0x18001da77  mov     [rsp+2C0h+var_260], r15
0x18001da7c  test    rcx, rcx
0x18001da7f  jz      short loc_18001DA87
0x18001da81  call    cs:__imp_SRCache_Free
0x18001da87  mov     rcx, [rsp+2C0h+var_288]
0x18001da8c  mov     [rsp+2C0h+var_288], r15
0x18001da91  test    rcx, rcx
0x18001da94  jz      short loc_18001DA9C
0x18001da96  call    cs:__imp_SRCacheContext_Close
0x18001da9c  xor     eax, eax
0x18001da9e  mov     rcx, [rbp+1C0h+var_40]
0x18001daa5  xor     rcx, rsp; StackCookie
0x18001daa8  call    __security_check_cookie
0x18001daad  add     rsp, 298h
0x18001dab4  pop     r15
0x18001dab6  pop     r14
0x18001dab8  pop     rdi
0x18001dab9  pop     rsi
0x18001daba  pop     rbx
0x18001dabb  pop     rbp
0x18001dabc  retn
```
