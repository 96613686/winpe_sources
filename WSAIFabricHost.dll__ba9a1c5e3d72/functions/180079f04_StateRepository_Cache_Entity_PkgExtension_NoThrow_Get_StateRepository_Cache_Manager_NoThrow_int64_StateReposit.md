# StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)

- ea: `0x180079f04`
- end: `0x18007a18c`
- name: `?Get@PkgExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180079e24`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x18000b064`
- `0x180078f4c`
- `0x180079430`
- `0x180079f04`
- `0x18007a43c`
- `0x18007a754`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a0ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a111`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a0ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007a111`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a0c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a0f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a126`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a163`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a0c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a0f7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a126`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a163`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18007a059`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18007a059`

## string_xrefs

- `0x18007a070`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180079f8a`: `PkgExtension\Data`
- `0x18007a052`: `PkgExtension\Data`
- `0x180079f4e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x180079fab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x18007a093`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`
- `0x18007a0d5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PkgExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  unsigned int v8; // ebx
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  bool v25[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v27[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v29[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+248h] [rbp+148h]
  __int64 v31; // [rsp+250h] [rbp+150h]
  wchar_t *v32; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)0x80070057LL,
      *(int *)v25);
    return v8;
  }
  v27[0] = 0;
  v26 = 0;
  v25[0] = 0;
  v10 = StateRepository::Cache::Context_NoThrow::Open(
          (StateRepository::Cache::Context_NoThrow *)&v26,
          a1,
          L"PkgExtension\\Data",
          v25);
  v8 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 311;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)v11,
      *(int *)v25);
LABEL_17:
    v19 = v26;
    v26 = 0;
    if ( v19 )
      SRCacheContext_Close();
    v20 = 220;
    goto LABEL_20;
  }
  if ( !v25[0] )
  {
    v8 = -2140733422;
    v12 = 312;
    v11 = 2154233874LL;
    goto LABEL_6;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = (wchar_t *)v29;
  v31 = 256;
  v13 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a2);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
    v15 = 315;
    goto LABEL_15;
  }
  v16 = StateRepository::Cache::Context_NoThrow::OpenSubContext(
          (StateRepository::Cache::Context_NoThrow *)v27,
          (struct StateRepository::Cache::Context_NoThrow *)&v26,
          v32,
          a5);
  v8 = v16;
  if ( v16 < 0 )
  {
    v14 = (unsigned int)v16;
    v15 = 316;
    goto LABEL_15;
  }
  v17 = SRCacheContext_AddToCache(v26, L"PkgExtension\\Data");
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      *(int *)v25);
    v14 = v8;
    v15 = 318;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
      (const char *)v14,
      *(int *)v25);
    v18 = v28;
    v28 = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_17;
  }
  v22 = v28;
  v28 = 0;
  if ( v22 )
    SRCache_Free();
  v23 = v26;
  v26 = 0;
  if ( v23 )
    SRCacheContext_Close();
  if ( *a5 )
  {
    v8 = StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(v27, a4, a3, a2);
    if ( (v8 & 0x80000000) != 0 )
    {
      v20 = 225;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PkgExtension.hpp",
        (const char *)v8,
        *(int *)v25);
      v21 = v27[0];
      v27[0] = 0;
      if ( v21 )
        SRCacheContext_Close();
      return v8;
    }
  }
  v24 = v27[0];
  v27[0] = 0;
  if ( v24 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x180079f04  push    rbp
0x180079f06  push    rbx
0x180079f07  push    rsi
0x180079f08  push    rdi
0x180079f09  push    r12
0x180079f0b  push    r14
0x180079f0d  push    r15
0x180079f0f  lea     rbp, [rsp-170h]
0x180079f17  sub     rsp, 270h
0x180079f1e  mov     rax, cs:__security_cookie
0x180079f25  xor     rax, rsp
0x180079f28  mov     [rbp+1A0h+var_40], rax
0x180079f2f  mov     rdi, [rbp+1A0h+arg_20]
0x180079f36  xor     r12d, r12d
0x180079f39  mov     r15, r9
0x180079f3c  mov     r14, r8
0x180079f3f  mov     rsi, rdx
0x180079f42  test    rdx, rdx
0x180079f45  jnz     short loc_180079F6E
0x180079f47  mov     rcx, [rbp+1A8h]; this
0x180079f4e  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079f55  mov     ebx, 80070057h
0x180079f5a  mov     edx, 0D9h; void *
0x180079f5f  mov     r9d, ebx; char *
0x180079f62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079f67  mov     eax, ebx
0x180079f69  jmp     loc_18007A16B
0x180079f6e  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x180079f71  mov     [rsp+2A0h+var_270], r12
0x180079f76  lea     rcx, [rsp+2A0h+var_278]; this
0x180079f7b  mov     [rsp+2A0h+var_278], r12
0x180079f80  lea     r9, [rsp+2A0h+var_280]; bool *
0x180079f85  mov     [rsp+2A0h+var_280], r12b; int
0x180079f8a  lea     r8, aPkgextensionDa; "PkgExtension\\Data"
0x180079f91  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)
0x180079f96  mov     ebx, eax
0x180079f98  test    eax, eax
0x180079f9a  jns     short loc_180079FBC
0x180079f9c  mov     r9d, eax; char *
0x180079f9f  mov     edx, 137h; void *
0x180079fa4  mov     rcx, [rbp+1A8h]; this
0x180079fab  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180079fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079fb7  jmp     loc_18007A0B4
0x180079fbc  cmp     [rsp+2A0h+var_280], r12b
0x180079fc1  jnz     short loc_180079FD2
0x180079fc3  mov     ebx, 80670012h
0x180079fc8  mov     edx, 138h
0x180079fcd  mov     r9d, ebx
0x180079fd0  jmp     short loc_180079FA4
0x180079fd2  xor     edx, edx; Val
0x180079fd4  mov     [rsp+2A0h+var_260], r12
0x180079fd9  mov     r8d, 200h; Size
0x180079fdf  lea     rcx, [rsp+2A0h+var_258]; void *
0x180079fe4  call    memset_0
0x180079fe9  lea     rax, [rsp+2A0h+var_258]
0x180079fee  mov     [rbp+1A0h+var_58], r12
0x180079ff5  mov     rdx, rsi; __int64
0x180079ff8  mov     [rbp+1A0h+var_48], rax
0x180079fff  lea     rcx, [rsp+2A0h+var_260]; this
0x18007a004  mov     [rbp+1A0h+var_50], 100h
0x18007a00f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::Key_NoThrow::Append(__int64)
0x18007a014  mov     ebx, eax
0x18007a016  test    eax, eax
0x18007a018  jns     short loc_18007A024
0x18007a01a  mov     r9d, eax
0x18007a01d  mov     edx, 13Bh
0x18007a022  jmp     short loc_18007A08C
0x18007a024  mov     r8, [rbp+1A0h+var_48]; wchar_t *
0x18007a02b  lea     rdx, [rsp+2A0h+var_278]; struct StateRepository::Cache::Context_NoThrow *
0x18007a030  mov     r9, rdi; bool *
0x18007a033  lea     rcx, [rsp+2A0h+var_270]; this
0x18007a038  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEB_WAEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,wchar_t const *,bool &)
0x18007a03d  mov     ebx, eax
0x18007a03f  test    eax, eax
0x18007a041  jns     short loc_18007A04D
0x18007a043  mov     r9d, eax
0x18007a046  mov     edx, 13Ch
0x18007a04b  jmp     short loc_18007A08C
0x18007a04d  mov     rcx, [rsp+2A0h+var_278]
0x18007a052  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x18007a059  call    cs:__imp_SRCacheContext_AddToCache
0x18007a05f  mov     ebx, eax
0x18007a061  test    eax, eax
0x18007a063  jns     loc_18007A102
0x18007a069  mov     rcx, [rbp+1A8h]; this
0x18007a070  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a077  mov     r9d, eax; char *
0x18007a07a  mov     edx, 1A6h; void *
0x18007a07f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a084  mov     r9d, ebx; char *
0x18007a087  mov     edx, 13Eh; void *
0x18007a08c  mov     rcx, [rbp+1A8h]; this
0x18007a093  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a09a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a09f  mov     rcx, [rsp+2A0h+var_260]
0x18007a0a4  mov     [rsp+2A0h+var_260], r12
0x18007a0a9  test    rcx, rcx
0x18007a0ac  jz      short loc_18007A0B4
0x18007a0ae  call    cs:__imp_SRCache_Free
0x18007a0b4  mov     rcx, [rsp+2A0h+var_278]
0x18007a0b9  mov     [rsp+2A0h+var_278], r12
0x18007a0be  test    rcx, rcx
0x18007a0c1  jz      short loc_18007A0C9
0x18007a0c3  call    cs:__imp_SRCacheContext_Close
0x18007a0c9  mov     edx, 0DCh; void *
0x18007a0ce  mov     rcx, [rbp+1A8h]; this
0x18007a0d5  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a0dc  mov     r9d, ebx; char *
0x18007a0df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a0e4  mov     rcx, [rsp+2A0h+var_270]
0x18007a0e9  mov     [rsp+2A0h+var_270], r12
0x18007a0ee  test    rcx, rcx
0x18007a0f1  jz      loc_180079F67
0x18007a0f7  call    cs:__imp_SRCacheContext_Close
0x18007a0fd  jmp     loc_180079F67
0x18007a102  mov     rcx, [rsp+2A0h+var_260]
0x18007a107  mov     [rsp+2A0h+var_260], r12
0x18007a10c  test    rcx, rcx
0x18007a10f  jz      short loc_18007A117
0x18007a111  call    cs:__imp_SRCache_Free
0x18007a117  mov     rcx, [rsp+2A0h+var_278]
0x18007a11c  mov     [rsp+2A0h+var_278], r12
0x18007a121  test    rcx, rcx
0x18007a124  jz      short loc_18007A12C
0x18007a126  call    cs:__imp_SRCacheContext_Close
0x18007a12c  cmp     [rdi], r12b
0x18007a12f  jz      short loc_18007A154
0x18007a131  mov     r9, rsi
0x18007a134  lea     rcx, [rsp+2A0h+var_270]
0x18007a139  mov     r8, r14
0x18007a13c  mov     rdx, r15
0x18007a13f  call    ?ContextToObject@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,__int64)
0x18007a144  mov     ebx, eax
0x18007a146  test    eax, eax
0x18007a148  jns     short loc_18007A154
0x18007a14a  mov     edx, 0E1h
0x18007a14f  jmp     loc_18007A0CE
0x18007a154  mov     rcx, [rsp+2A0h+var_270]
0x18007a159  mov     [rsp+2A0h+var_270], r12
0x18007a15e  test    rcx, rcx
0x18007a161  jz      short loc_18007A169
0x18007a163  call    cs:__imp_SRCacheContext_Close
0x18007a169  xor     eax, eax
0x18007a16b  mov     rcx, [rbp+1A0h+var_40]
0x18007a172  xor     rcx, rsp; StackCookie
0x18007a175  call    __security_check_cookie
0x18007a17a  add     rsp, 270h
0x18007a181  pop     r15
0x18007a183  pop     r14
0x18007a185  pop     r12
0x18007a187  pop     rdi
0x18007a188  pop     rsi
0x18007a189  pop     rbx
0x18007a18a  pop     rbp
0x18007a18b  retn
```
