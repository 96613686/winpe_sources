# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18004cb90`
- end: `0x18004cdbd`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `557`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18002c020`
- `0x1800496e0`
- `0x1800f5ed4`

## callees

- `0x18002f340`
- `0x18004cb90`
- `0x180058768`
- `0x1800caf60`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18004cbf0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18004cbf0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004cc14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ccdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004cd5e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004cc14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ccdd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004cd5e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ccc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004cd49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ccc8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004cd49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18004ccad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18004ccad`

## string_xrefs

- `0x18004cd2b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18004cd8a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18004cd0b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18004cda2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v20 = &v19;
  v22 = 1;
  v19 = 0;
  v21 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageFamily\\Data", 0, &v21);
  if ( v22 )
  {
    v9 = *v20;
    *v20 = v21;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18);
    v17 = 257;
    goto LABEL_23;
  }
  if ( !v19 )
  {
    v8 = -2140733422;
    v17 = 258;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v18);
    goto LABEL_17;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  if ( v8 < 0 )
  {
    v14 = 261;
  }
  else
  {
    v18 = v5;
    v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v27);
    if ( v8 < 0 )
    {
      v14 = 262;
    }
    else
    {
      v10 = SRCacheContext_AddToCache(v19, L"PackageFamily\\Data");
      v8 = v10;
      if ( v10 >= 0 )
      {
        v11 = v23;
        v23 = 0;
        if ( v11 )
          SRCache_Free(v11);
        v12 = v19;
        v19 = 0;
        if ( v12 )
          SRCacheContext_Close(v12);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v10,
        v5);
      v14 = 264;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
    (const char *)(unsigned int)v8,
    v18);
  v15 = v23;
  v23 = 0;
  if ( v15 )
    SRCache_Free(v15);
LABEL_17:
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004cb90  push    rbp
0x18004cb92  push    rbx
0x18004cb93  push    rsi
0x18004cb94  push    rdi
0x18004cb95  push    r14
0x18004cb97  push    r15
0x18004cb99  lea     rbp, [rsp-188h]
0x18004cba1  sub     rsp, 288h
0x18004cba8  mov     rax, cs:__security_cookie
0x18004cbaf  xor     rax, rsp
0x18004cbb2  mov     [rbp+1B0h+var_40], rax
0x18004cbb9  mov     rcx, [rcx]
0x18004cbbc  lea     rax, [rsp+2B0h+var_280]
0x18004cbc1  mov     rsi, r9
0x18004cbc4  mov     [rsp+2B0h+var_278], rax
0x18004cbc9  mov     rdi, r8
0x18004cbcc  mov     [rsp+2B0h+var_268], 1
0x18004cbd1  mov     r14, rdx
0x18004cbd4  lea     r9, [rsp+2B0h+var_270]
0x18004cbd9  xor     r15d, r15d
0x18004cbdc  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18004cbe3  xor     r8d, r8d
0x18004cbe6  mov     [rsp+2B0h+var_280], r15
0x18004cbeb  mov     [rsp+2B0h+var_270], r15
0x18004cbf0  call    cs:__imp_SRCacheContext_Open
0x18004cbf6  mov     ebx, eax
0x18004cbf8  cmp     [rsp+2B0h+var_268], r15b
0x18004cbfd  jz      short loc_18004CC1A
0x18004cbff  mov     r8, [rsp+2B0h+var_278]
0x18004cc04  mov     rdx, [rsp+2B0h+var_270]
0x18004cc09  mov     rcx, [r8]
0x18004cc0c  mov     [r8], rdx
0x18004cc0f  test    rcx, rcx
0x18004cc12  jz      short loc_18004CC1A
0x18004cc14  call    cs:__imp_SRCacheContext_Close
0x18004cc1a  test    ebx, ebx
0x18004cc1c  js      loc_18004CD9B
0x18004cc22  cmp     [rsp+2B0h+var_280], r15
0x18004cc27  setnz   al
0x18004cc2a  test    al, al
0x18004cc2c  jz      loc_18004CD79
0x18004cc32  xor     edx, edx; Val
0x18004cc34  mov     [rsp+2B0h+var_260], r15
0x18004cc39  mov     r8d, 200h; Size
0x18004cc3f  lea     rcx, [rsp+2B0h+var_258]; void *
0x18004cc44  call    memset_0
0x18004cc49  lea     rax, [rsp+2B0h+var_258]
0x18004cc4e  mov     [rbp+1B0h+var_58], r15
0x18004cc55  mov     rdx, r14; unsigned __int64
0x18004cc58  mov     [rbp+1B0h+var_48], rax
0x18004cc5f  lea     rcx, [rsp+2B0h+var_260]; this
0x18004cc64  mov     [rbp+1B0h+var_50], 100h
0x18004cc6f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18004cc74  mov     ebx, eax
0x18004cc76  test    eax, eax
0x18004cc78  js      loc_18004CD72
0x18004cc7e  mov     r8, [rbp+1B0h+var_48]
0x18004cc85  lea     rdx, [rsp+2B0h+var_280]
0x18004cc8a  mov     rcx, rdi
0x18004cc8d  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x18004cc92  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18004cc97  mov     ebx, eax
0x18004cc99  test    eax, eax
0x18004cc9b  js      loc_18004CD6B
0x18004cca1  mov     rcx, [rsp+2B0h+var_280]
0x18004cca6  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18004ccad  call    cs:__imp_SRCacheContext_AddToCache
0x18004ccb3  mov     ebx, eax
0x18004ccb5  test    eax, eax
0x18004ccb7  js      short loc_18004CD04
0x18004ccb9  mov     rcx, [rsp+2B0h+var_260]
0x18004ccbe  mov     [rsp+2B0h+var_260], r15
0x18004ccc3  test    rcx, rcx
0x18004ccc6  jz      short loc_18004CCCE
0x18004ccc8  call    cs:__imp_SRCache_Free
0x18004ccce  mov     rcx, [rsp+2B0h+var_280]
0x18004ccd3  mov     [rsp+2B0h+var_280], r15
0x18004ccd8  test    rcx, rcx
0x18004ccdb  jz      short loc_18004CCE3
0x18004ccdd  call    cs:__imp_SRCacheContext_Close
0x18004cce3  xor     eax, eax
0x18004cce5  mov     rcx, [rbp+1B0h+var_40]
0x18004ccec  xor     rcx, rsp; StackCookie
0x18004ccef  call    __security_check_cookie
0x18004ccf4  add     rsp, 288h
0x18004ccfb  pop     r15
0x18004ccfd  pop     r14
0x18004ccff  pop     rdi
0x18004cd00  pop     rsi
0x18004cd01  pop     rbx
0x18004cd02  pop     rbp
0x18004cd03  retn
0x18004cd04  mov     rcx, [rbp+1B8h]; this
0x18004cd0b  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004cd12  mov     r9d, ebx; char *
0x18004cd15  mov     edx, 1A6h; void *
0x18004cd1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cd1f  mov     edx, 108h; void *
0x18004cd24  mov     rcx, [rbp+1B8h]; this
0x18004cd2b  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004cd32  mov     r9d, ebx; char *
0x18004cd35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cd3a  mov     rcx, [rsp+2B0h+var_260]
0x18004cd3f  mov     [rsp+2B0h+var_260], r15
0x18004cd44  test    rcx, rcx
0x18004cd47  jz      short loc_18004CD4F
0x18004cd49  call    cs:__imp_SRCache_Free
0x18004cd4f  mov     rcx, [rsp+2B0h+var_280]
0x18004cd54  mov     [rsp+2B0h+var_280], r15
0x18004cd59  test    rcx, rcx
0x18004cd5c  jz      short loc_18004CD64
0x18004cd5e  call    cs:__imp_SRCacheContext_Close
0x18004cd64  mov     eax, ebx
0x18004cd66  jmp     loc_18004CCE5
0x18004cd6b  mov     edx, 106h
0x18004cd70  jmp     short loc_18004CD24
0x18004cd72  mov     edx, 105h
0x18004cd77  jmp     short loc_18004CD24
0x18004cd79  mov     ebx, 80670012h
0x18004cd7e  mov     edx, 102h; void *
0x18004cd83  mov     rcx, [rbp+1B8h]; this
0x18004cd8a  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004cd91  mov     r9d, ebx; char *
0x18004cd94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cd99  jmp     short loc_18004CD4F
0x18004cd9b  mov     rcx, [rbp+1B8h]; this
0x18004cda2  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004cda9  mov     r9d, ebx; char *
0x18004cdac  mov     edx, 18Ch; void *
0x18004cdb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cdb6  mov     edx, 101h
0x18004cdbb  jmp     short loc_18004CD83
```
