# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18002ca5c`
- end: `0x18002cd66`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002af0c`
- `0x18002d000`
- `0x180147b50`

## callees

- `0x18002ca5c`
- `0x180058520`
- `0x180058768`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002cbbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002cbbb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002cb75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002cb75`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002caba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002caba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cade`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cb99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cbf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cc20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cc84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ccd3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cade`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cb99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cbf6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cc20`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002cc84`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002ccd3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002cc0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002cc6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002cc0b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002cc6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002cbd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002cbd7`

## string_xrefs

- `0x18002cc4c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002ccb5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002cd46`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002cc95`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002cce2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002cd04`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002cd26`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  int *v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+258h] [rbp+158h]
  __int64 v29; // [rsp+260h] [rbp+160h]
  _BYTE *v30; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v25 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v21 = 0;
  v23 = v21;
  v24 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageFamily\\Index\\PackageFamilyName", 0, &v24);
  if ( v25 )
  {
    v7 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v20 = 193;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v21[0]);
    goto LABEL_24;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v20 = 194;
    goto LABEL_33;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
  }
  else
  {
    v23 = (int *)&v22;
    v22 = 0;
    v24 = 0;
    v25 = 1;
    v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
    if ( v25 )
    {
      v9 = *(_QWORD *)v23;
      *(_QWORD *)v23 = v24;
      if ( v9 )
        SRCacheContext_Close(v9);
    }
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)v6,
        v21[0]);
      v18 = 201;
    }
    else if ( v22 && (v10 = SRCacheContext_EnumerateData(v22, 0, a3), v6 = v10, v10 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v10,
        v21[0]);
      v18 = 204;
    }
    else
    {
      v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"PackageFamily\\Index\\PackageFamilyName");
      v6 = v11;
      if ( v11 >= 0 )
      {
        v12 = v22;
        v22 = 0;
        if ( v12 )
          SRCacheContext_Close(v12);
        v13 = v26;
        v26 = 0;
        if ( v13 )
          SRCache_Free(v13);
        v14 = *(_QWORD *)v21;
        *(_QWORD *)v21 = 0;
        if ( v14 )
          SRCacheContext_Close(v14);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v11,
        v21[0]);
      v18 = 207;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v21[0]);
    v19 = v22;
    v22 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
  }
  v16 = v26;
  v26 = 0;
  if ( v16 )
    SRCache_Free(v16);
LABEL_24:
  v17 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return v6;
}

```

## disassembly

```asm
0x18002ca5c  push    rbp
0x18002ca5e  push    rbx
0x18002ca5f  push    rsi
0x18002ca60  push    rdi
0x18002ca61  push    r14
0x18002ca63  lea     rbp, [rsp-180h]
0x18002ca6b  sub     rsp, 280h
0x18002ca72  mov     rax, cs:__security_cookie
0x18002ca79  xor     rax, rsp
0x18002ca7c  mov     [rbp+1A0h+var_30], rax
0x18002ca83  xor     r14d, r14d
0x18002ca86  mov     [rsp+2A0h+var_260], 1
0x18002ca8b  mov     [r8], r14
0x18002ca8e  lea     rax, [rsp+2A0h+var_280]
0x18002ca93  mov     rcx, [rcx]
0x18002ca96  lea     r9, [rsp+2A0h+var_268]
0x18002ca9b  mov     rdi, r8
0x18002ca9e  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18002caa3  mov     rsi, rdx
0x18002caa6  mov     [rsp+2A0h+var_270], rax
0x18002caab  xor     r8d, r8d
0x18002caae  mov     [rsp+2A0h+var_268], r14
0x18002cab3  lea     rdx, aPackagefamilyI_0; "PackageFamily\\Index\\PackageFamilyName"
0x18002caba  call    cs:__imp_SRCacheContext_Open
0x18002cac0  mov     ebx, eax
0x18002cac2  cmp     [rsp+2A0h+var_260], r14b
0x18002cac7  jz      short loc_18002CAE4
0x18002cac9  mov     r8, [rsp+2A0h+var_270]
0x18002cace  mov     rdx, [rsp+2A0h+var_268]
0x18002cad3  mov     rcx, [r8]
0x18002cad6  mov     [r8], rdx
0x18002cad9  test    rcx, rcx
0x18002cadc  jz      short loc_18002CAE4
0x18002cade  call    cs:__imp_SRCacheContext_Close
0x18002cae4  test    ebx, ebx
0x18002cae6  js      loc_18002CD1F
0x18002caec  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18002caf1  setnz   al
0x18002caf4  test    al, al
0x18002caf6  jz      loc_18002CD5A
0x18002cafc  xor     edx, edx; Val
0x18002cafe  mov     [rsp+2A0h+var_250], r14
0x18002cb03  mov     r8d, 200h; Size
0x18002cb09  lea     rcx, [rsp+2A0h+var_248]; void *
0x18002cb0e  call    memset_0
0x18002cb13  lea     rax, [rsp+2A0h+var_248]
0x18002cb18  mov     [rbp+1A0h+var_48], r14
0x18002cb1f  mov     rdx, rsi; unsigned __int16 *
0x18002cb22  mov     [rbp+1A0h+var_38], rax
0x18002cb29  lea     rcx, [rsp+2A0h+var_250]; this
0x18002cb2e  mov     [rbp+1A0h+var_40], 100h
0x18002cb39  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18002cb3e  mov     ebx, eax
0x18002cb40  test    eax, eax
0x18002cb42  js      loc_18002CC45
0x18002cb48  mov     rdx, [rbp+1A0h+var_38]
0x18002cb4f  lea     rax, [rsp+2A0h+var_278]
0x18002cb54  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002cb59  lea     r9, [rsp+2A0h+var_268]
0x18002cb5e  xor     r8d, r8d
0x18002cb61  mov     [rsp+2A0h+var_270], rax
0x18002cb66  mov     [rsp+2A0h+var_278], r14
0x18002cb6b  mov     [rsp+2A0h+var_268], r14
0x18002cb70  mov     [rsp+2A0h+var_260], 1
0x18002cb75  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002cb7b  mov     ebx, eax
0x18002cb7d  cmp     [rsp+2A0h+var_260], r14b
0x18002cb82  jz      short loc_18002CB9F
0x18002cb84  mov     r8, [rsp+2A0h+var_270]
0x18002cb89  mov     rdx, [rsp+2A0h+var_268]
0x18002cb8e  mov     rcx, [r8]
0x18002cb91  mov     [r8], rdx
0x18002cb94  test    rcx, rcx
0x18002cb97  jz      short loc_18002CB9F
0x18002cb99  call    cs:__imp_SRCacheContext_Close
0x18002cb9f  test    ebx, ebx
0x18002cba1  js      loc_18002CCDB
0x18002cba7  mov     rcx, [rsp+2A0h+var_278]
0x18002cbac  test    rcx, rcx
0x18002cbaf  setnz   al
0x18002cbb2  test    al, al
0x18002cbb4  jz      short loc_18002CBCB
0x18002cbb6  mov     r8, rdi
0x18002cbb9  xor     edx, edx
0x18002cbbb  call    cs:__imp_SRCacheContext_EnumerateData
0x18002cbc1  mov     ebx, eax
0x18002cbc3  test    eax, eax
0x18002cbc5  js      loc_18002CCFD
0x18002cbcb  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002cbd0  lea     rdx, aPackagefamilyI_0; "PackageFamily\\Index\\PackageFamilyName"
0x18002cbd7  call    cs:__imp_SRCacheContext_AddToCache
0x18002cbdd  mov     ebx, eax
0x18002cbdf  test    eax, eax
0x18002cbe1  js      loc_18002CC8E
0x18002cbe7  mov     rcx, [rsp+2A0h+var_278]
0x18002cbec  mov     [rsp+2A0h+var_278], r14
0x18002cbf1  test    rcx, rcx
0x18002cbf4  jz      short loc_18002CBFC
0x18002cbf6  call    cs:__imp_SRCacheContext_Close
0x18002cbfc  mov     rcx, [rsp+2A0h+var_250]
0x18002cc01  mov     [rsp+2A0h+var_250], r14
0x18002cc06  test    rcx, rcx
0x18002cc09  jz      short loc_18002CC11
0x18002cc0b  call    cs:__imp_SRCache_Free
0x18002cc11  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002cc16  mov     qword ptr [rsp+2A0h+var_280], r14
0x18002cc1b  test    rcx, rcx
0x18002cc1e  jz      short loc_18002CC26
0x18002cc20  call    cs:__imp_SRCacheContext_Close
0x18002cc26  xor     eax, eax
0x18002cc28  mov     rcx, [rbp+1A0h+var_30]
0x18002cc2f  xor     rcx, rsp; StackCookie
0x18002cc32  call    __security_check_cookie
0x18002cc37  add     rsp, 280h
0x18002cc3e  pop     r14
0x18002cc40  pop     rdi
0x18002cc41  pop     rsi
0x18002cc42  pop     rbx
0x18002cc43  pop     rbp
0x18002cc44  retn
0x18002cc45  mov     rcx, [rbp+1A8h]; this
0x18002cc4c  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002cc53  mov     r9d, ebx; char *
0x18002cc56  mov     edx, 0C5h; void *
0x18002cc5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc60  mov     rcx, [rsp+2A0h+var_250]
0x18002cc65  mov     [rsp+2A0h+var_250], r14
0x18002cc6a  test    rcx, rcx
0x18002cc6d  jz      short loc_18002CC75
0x18002cc6f  call    cs:__imp_SRCache_Free
0x18002cc75  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002cc7a  mov     qword ptr [rsp+2A0h+var_280], r14
0x18002cc7f  test    rcx, rcx
0x18002cc82  jz      short loc_18002CC8A
0x18002cc84  call    cs:__imp_SRCacheContext_Close
0x18002cc8a  mov     eax, ebx
0x18002cc8c  jmp     short loc_18002CC28
0x18002cc8e  mov     rcx, [rbp+1A8h]; this
0x18002cc95  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002cc9c  mov     r9d, ebx; char *
0x18002cc9f  mov     edx, 1A6h; void *
0x18002cca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cca9  mov     edx, 0CFh; void *
0x18002ccae  mov     rcx, [rbp+1A8h]; this
0x18002ccb5  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ccbc  mov     r9d, ebx; char *
0x18002ccbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ccc4  mov     rcx, [rsp+2A0h+var_278]
0x18002ccc9  mov     [rsp+2A0h+var_278], r14
0x18002ccce  test    rcx, rcx
0x18002ccd1  jz      short loc_18002CC60
0x18002ccd3  call    cs:__imp_SRCacheContext_Close
0x18002ccd9  jmp     short loc_18002CC60
0x18002ccdb  mov     rcx, [rbp+1A8h]; this
0x18002cce2  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002cce9  mov     r9d, ebx; char *
0x18002ccec  mov     edx, 1B0h; void *
0x18002ccf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ccf6  mov     edx, 0C9h
0x18002ccfb  jmp     short loc_18002CCAE
0x18002ccfd  mov     rcx, [rbp+1A8h]; this
0x18002cd04  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002cd0b  mov     r9d, ebx; char *
0x18002cd0e  mov     edx, 2A6h; void *
0x18002cd13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd18  mov     edx, 0CCh
0x18002cd1d  jmp     short loc_18002CCAE
0x18002cd1f  mov     rcx, [rbp+1A8h]; this
0x18002cd26  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002cd2d  mov     r9d, ebx; char *
0x18002cd30  mov     edx, 18Ch; void *
0x18002cd35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd3a  mov     edx, 0C1h; void *
0x18002cd3f  mov     rcx, [rbp+1A8h]; this
0x18002cd46  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002cd4d  mov     r9d, ebx; char *
0x18002cd50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd55  jmp     loc_18002CC75
0x18002cd5a  mov     ebx, 80670012h
0x18002cd5f  mov     edx, 0C2h
0x18002cd64  jmp     short loc_18002CD3F
```
