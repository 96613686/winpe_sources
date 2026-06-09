# StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x180079a98`
- end: `0x180079e1e`
- name: `?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `902`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180078fd0`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x18000b064`
- `0x180078f4c`
- `0x180079a98`
- `0x18007a43c`
- `0x18007a754`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079c40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079ca3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079d35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079daf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079c40`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079ca3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079d35`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180079daf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079ceb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079d6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079ceb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180079d6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079c55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079c89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079cb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079df0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079c55`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079c89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079cb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180079df0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180079beb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180079beb`

## string_xrefs

- `0x180079c02`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079d03`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079d7d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079ae0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180079b3d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180079c25`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180079c67`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180079dc5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180079d59`: `InstalledLocation`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  unsigned int v7; // ebx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int Field_String; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // rcx
  bool v29[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v30; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v32; // [rsp+38h] [rbp-C8h]
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  char v34; // [rsp+48h] [rbp-B8h]
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+258h] [rbp+158h]
  __int64 v38; // [rsp+260h] [rbp+160h]
  wchar_t *v39; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x453,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      *(int *)v29);
    return v7;
  }
  v31 = 0;
  v30 = 0;
  v29[0] = 0;
  v9 = StateRepository::Cache::Context_NoThrow::Open(
         (StateRepository::Cache::Context_NoThrow *)&v30,
         a1,
         L"Package\\Data",
         v29);
  v7 = v9;
  if ( v9 < 0 )
  {
    v10 = (unsigned int)v9;
    v11 = 1192;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v10,
      *(int *)v29);
LABEL_17:
    v18 = v30;
    v30 = 0;
    if ( v18 )
      SRCacheContext_Close();
    v19 = 1110;
    goto LABEL_20;
  }
  if ( !v29[0] )
  {
    v7 = -2140733422;
    v11 = 1193;
    v10 = 2154233874LL;
    goto LABEL_6;
  }
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v37 = 0;
  v39 = (wchar_t *)v36;
  v38 = 256;
  v12 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v35, a2);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v14 = 1196;
    goto LABEL_15;
  }
  v15 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
          (StateRepository::Cache::Context_NoThrow *)&v31,
          (struct StateRepository::Cache::Context_NoThrow *)&v30,
          v39,
          a5);
  v7 = v15;
  if ( v15 < 0 )
  {
    v13 = (unsigned int)v15;
    v14 = 1197;
    goto LABEL_15;
  }
  v16 = SRCacheContext_AddToCache(v30, L"Package\\Data");
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v16,
      *(int *)v29);
    v13 = v7;
    v14 = 1199;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v13,
      *(int *)v29);
    v17 = v35;
    v35 = 0;
    if ( v17 )
      SRCache_Free();
    goto LABEL_17;
  }
  v21 = v35;
  v35 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = v30;
  v30 = 0;
  if ( v22 )
    SRCacheContext_Close();
  v23 = v31;
  if ( *a5 )
  {
    v33 = 0;
    v32 = a4 + 1;
    v34 = 1;
    Field_String = SRCacheContext_GetField_String(v31, L"PackageFullName", &v33);
    v7 = Field_String;
    if ( Field_String >= 0 )
      v7 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_String,
        *(int *)v29);
    if ( v34 )
    {
      v25 = *v32;
      *v32 = v33;
      if ( v25 )
        SRCache_Free();
    }
    if ( (v7 & 0x80000000) != 0 )
    {
      v26 = 2091;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)v7,
        *(int *)v29);
      v19 = 1115;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)v7,
        *(int *)v29);
      v20 = v31;
      v31 = 0;
      if ( v20 )
        SRCacheContext_Close();
      return v7;
    }
    v32 = a4 + 7;
    v33 = 0;
    v34 = 1;
    v27 = SRCacheContext_GetField_String(v31, L"InstalledLocation", &v33);
    v7 = v27;
    if ( v27 >= 0 )
      v7 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v27,
        *(int *)v29);
    if ( v34 )
    {
      v28 = *v32;
      *v32 = v33;
      if ( v28 )
        SRCache_Free();
    }
    if ( (v7 & 0x80000000) != 0 )
    {
      v26 = 2123;
      goto LABEL_43;
    }
    v23 = v31;
    *a4 = a2;
  }
  v31 = 0;
  if ( v23 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x180079a98  mov     [rsp-8+arg_10], rbx
0x180079a9d  push    rbp
0x180079a9e  push    rsi
0x180079a9f  push    rdi
0x180079aa0  push    r14
0x180079aa2  push    r15
0x180079aa4  lea     rbp, [rsp-180h]
0x180079aac  sub     rsp, 280h
0x180079ab3  mov     rax, cs:__security_cookie
0x180079aba  xor     rax, rsp
0x180079abd  mov     [rbp+1A0h+var_30], rax
0x180079ac4  mov     rdi, [rbp+1A0h+arg_20]
0x180079acb  xor     r15d, r15d
0x180079ace  mov     rsi, r9
0x180079ad1  mov     r14, rdx
0x180079ad4  test    rdx, rdx
0x180079ad7  jnz     short loc_180079B00
0x180079ad9  mov     rcx, [rbp+1A8h]; this
0x180079ae0  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079ae7  mov     ebx, 80070057h
0x180079aec  mov     edx, 453h; void *
0x180079af1  mov     r9d, ebx; char *
0x180079af4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079af9  mov     eax, ebx
0x180079afb  jmp     loc_180079DF8
0x180079b00  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x180079b03  mov     [rsp+2A0h+var_270], r15
0x180079b08  lea     rcx, [rsp+2A0h+var_278]; this
0x180079b0d  mov     [rsp+2A0h+var_278], r15
0x180079b12  lea     r9, [rsp+2A0h+var_280]; bool *
0x180079b17  mov     [rsp+2A0h+var_280], r15b; int
0x180079b1c  lea     r8, aPackageData; "Package\\Data"
0x180079b23  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)
0x180079b28  mov     ebx, eax
0x180079b2a  test    eax, eax
0x180079b2c  jns     short loc_180079B4E
0x180079b2e  mov     r9d, eax; char *
0x180079b31  mov     edx, 4A8h; void *
0x180079b36  mov     rcx, [rbp+1A8h]; this
0x180079b3d  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079b44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079b49  jmp     loc_180079C46
0x180079b4e  cmp     [rsp+2A0h+var_280], r15b
0x180079b53  jnz     short loc_180079B64
0x180079b55  mov     ebx, 80670012h
0x180079b5a  mov     edx, 4A9h
0x180079b5f  mov     r9d, ebx
0x180079b62  jmp     short loc_180079B36
0x180079b64  xor     edx, edx; Val
0x180079b66  mov     [rsp+2A0h+var_250], r15
0x180079b6b  mov     r8d, 200h; Size
0x180079b71  lea     rcx, [rsp+2A0h+var_248]; void *
0x180079b76  call    memset_0
0x180079b7b  lea     rax, [rsp+2A0h+var_248]
0x180079b80  mov     [rbp+1A0h+var_48], r15
0x180079b87  mov     rdx, r14; __int64
0x180079b8a  mov     [rbp+1A0h+var_38], rax
0x180079b91  lea     rcx, [rsp+2A0h+var_250]; this
0x180079b96  mov     [rbp+1A0h+var_40], 100h
0x180079ba1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x180079ba6  mov     ebx, eax
0x180079ba8  test    eax, eax
0x180079baa  jns     short loc_180079BB6
0x180079bac  mov     r9d, eax
0x180079baf  mov     edx, 4ACh
0x180079bb4  jmp     short loc_180079C1E
0x180079bb6  mov     r8, [rbp+1A0h+var_38]; wchar_t *
0x180079bbd  lea     rdx, [rsp+2A0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x180079bc2  mov     r9, rdi; bool *
0x180079bc5  lea     rcx, [rsp+2A0h+var_270]; this
0x180079bca  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,wchar_t const *,bool &)
0x180079bcf  mov     ebx, eax
0x180079bd1  test    eax, eax
0x180079bd3  jns     short loc_180079BDF
0x180079bd5  mov     r9d, eax
0x180079bd8  mov     edx, 4ADh
0x180079bdd  jmp     short loc_180079C1E
0x180079bdf  mov     rcx, [rsp+2A0h+var_278]
0x180079be4  lea     rdx, aPackageData; "Package\\Data"
0x180079beb  call    cs:__imp_SRCacheContext_AddToCache
0x180079bf1  mov     ebx, eax
0x180079bf3  test    eax, eax
0x180079bf5  jns     loc_180079C94
0x180079bfb  mov     rcx, [rbp+1A8h]; this
0x180079c02  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079c09  mov     r9d, eax; char *
0x180079c0c  mov     edx, 1A6h; void *
0x180079c11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079c16  mov     r9d, ebx; char *
0x180079c19  mov     edx, 4AFh; void *
0x180079c1e  mov     rcx, [rbp+1A8h]; this
0x180079c25  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079c31  mov     rcx, [rsp+2A0h+var_250]
0x180079c36  mov     [rsp+2A0h+var_250], r15
0x180079c3b  test    rcx, rcx
0x180079c3e  jz      short loc_180079C46
0x180079c40  call    cs:__imp_SRCache_Free
0x180079c46  mov     rcx, [rsp+2A0h+var_278]
0x180079c4b  mov     [rsp+2A0h+var_278], r15
0x180079c50  test    rcx, rcx
0x180079c53  jz      short loc_180079C5B
0x180079c55  call    cs:__imp_SRCacheContext_Close
0x180079c5b  mov     edx, 456h; void *
0x180079c60  mov     rcx, [rbp+1A8h]; this
0x180079c67  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079c6e  mov     r9d, ebx; char *
0x180079c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079c76  mov     rcx, [rsp+2A0h+var_270]
0x180079c7b  mov     [rsp+2A0h+var_270], r15
0x180079c80  test    rcx, rcx
0x180079c83  jz      loc_180079AF9
0x180079c89  call    cs:__imp_SRCacheContext_Close
0x180079c8f  jmp     loc_180079AF9
0x180079c94  mov     rcx, [rsp+2A0h+var_250]
0x180079c99  mov     [rsp+2A0h+var_250], r15
0x180079c9e  test    rcx, rcx
0x180079ca1  jz      short loc_180079CA9
0x180079ca3  call    cs:__imp_SRCache_Free
0x180079ca9  mov     rcx, [rsp+2A0h+var_278]
0x180079cae  mov     [rsp+2A0h+var_278], r15
0x180079cb3  test    rcx, rcx
0x180079cb6  jz      short loc_180079CBE
0x180079cb8  call    cs:__imp_SRCacheContext_Close
0x180079cbe  mov     rcx, [rsp+2A0h+var_270]
0x180079cc3  cmp     [rdi], r15b
0x180079cc6  jz      loc_180079DE6
0x180079ccc  lea     rax, [rsi+8]
0x180079cd0  mov     [rsp+2A0h+var_260], r15
0x180079cd5  lea     r8, [rsp+2A0h+var_260]
0x180079cda  mov     [rsp+2A0h+var_268], rax
0x180079cdf  lea     rdx, aPackagefullnam; "PackageFullName"
0x180079ce6  mov     [rsp+2A0h+var_258], 1
0x180079ceb  call    cs:__imp_SRCacheContext_GetField_String
0x180079cf1  mov     ebx, eax
0x180079cf3  mov     edi, 246h
0x180079cf8  test    eax, eax
0x180079cfa  jns     short loc_180079D16
0x180079cfc  mov     rcx, [rbp+1A8h]; this
0x180079d03  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079d0a  mov     r9d, eax; char *
0x180079d0d  mov     edx, edi; void *
0x180079d0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079d14  jmp     short loc_180079D19
0x180079d16  mov     ebx, r15d
0x180079d19  cmp     [rsp+2A0h+var_258], r15b
0x180079d1e  jz      short loc_180079D3B
0x180079d20  mov     rdx, [rsp+2A0h+var_268]
0x180079d25  mov     rax, [rsp+2A0h+var_260]
0x180079d2a  mov     rcx, [rdx]
0x180079d2d  mov     [rdx], rax
0x180079d30  test    rcx, rcx
0x180079d33  jz      short loc_180079D3B
0x180079d35  call    cs:__imp_SRCache_Free
0x180079d3b  test    ebx, ebx
0x180079d3d  jns     short loc_180079D46
0x180079d3f  mov     edx, 82Bh
0x180079d44  jmp     short loc_180079DBE
0x180079d46  mov     rcx, [rsp+2A0h+var_270]
0x180079d4b  lea     rax, [rsi+38h]
0x180079d4f  lea     r8, [rsp+2A0h+var_260]
0x180079d54  mov     [rsp+2A0h+var_268], rax
0x180079d59  lea     rdx, aInstalledlocat; "InstalledLocation"
0x180079d60  mov     [rsp+2A0h+var_260], r15
0x180079d65  mov     [rsp+2A0h+var_258], 1
0x180079d6a  call    cs:__imp_SRCacheContext_GetField_String
0x180079d70  mov     ebx, eax
0x180079d72  test    eax, eax
0x180079d74  jns     short loc_180079D90
0x180079d76  mov     rcx, [rbp+1A8h]; this
0x180079d7d  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079d84  mov     r9d, eax; char *
0x180079d87  mov     edx, edi; void *
0x180079d89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079d8e  jmp     short loc_180079D93
0x180079d90  mov     ebx, r15d
0x180079d93  cmp     [rsp+2A0h+var_258], r15b
0x180079d98  jz      short loc_180079DB5
0x180079d9a  mov     rdx, [rsp+2A0h+var_268]
0x180079d9f  mov     rax, [rsp+2A0h+var_260]
0x180079da4  mov     rcx, [rdx]
0x180079da7  mov     [rdx], rax
0x180079daa  test    rcx, rcx
0x180079dad  jz      short loc_180079DB5
0x180079daf  call    cs:__imp_SRCache_Free
0x180079db5  test    ebx, ebx
0x180079db7  jns     short loc_180079DDE
0x180079db9  mov     edx, 84Bh; void *
0x180079dbe  mov     rcx, [rbp+1A8h]; this
0x180079dc5  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079dcc  mov     r9d, ebx; char *
0x180079dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079dd4  mov     edx, 45Bh
0x180079dd9  jmp     loc_180079C60
0x180079dde  mov     rcx, [rsp+2A0h+var_270]
0x180079de3  mov     [rsi], r14
0x180079de6  mov     [rsp+2A0h+var_270], r15
0x180079deb  test    rcx, rcx
0x180079dee  jz      short loc_180079DF6
0x180079df0  call    cs:__imp_SRCacheContext_Close
0x180079df6  xor     eax, eax
0x180079df8  mov     rcx, [rbp+1A0h+var_30]
0x180079dff  xor     rcx, rsp; StackCookie
0x180079e02  call    __security_check_cookie
0x180079e07  mov     rbx, [rsp+2A0h+arg_10]
0x180079e0f  add     rsp, 280h
0x180079e16  pop     r15
0x180079e18  pop     r14
0x180079e1a  pop     rdi
0x180079e1b  pop     rsi
0x180079e1c  pop     rbp
0x180079e1d  retn
```
