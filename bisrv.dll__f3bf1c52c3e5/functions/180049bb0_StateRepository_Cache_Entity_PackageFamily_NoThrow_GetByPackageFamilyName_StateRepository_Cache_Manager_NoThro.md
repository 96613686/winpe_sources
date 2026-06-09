# StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180049bb0`
- end: `0x180049eb3`
- name: `?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `771`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800526e0`

## callees

- `0x180019f90`
- `0x18001a1f0`
- `0x180049bb0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180049dea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180049dea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180049c0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180049c0e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049c32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049c81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049d78`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049dcb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049e64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049e8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049c32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049c81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049d78`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049dcb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049e64`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049e8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180049d54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180049d54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049d1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049e79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049d1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049e79`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180049e24`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180049e24`

## string_xrefs

- `0x180049c43`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180049d89`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180049dfd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180049e37`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180049c63`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180049cf5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180049da9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

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
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
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
    v8 = 193;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v21[0]);
LABEL_7:
    v9 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return v6;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v8 = 194;
    goto LABEL_6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
LABEL_14:
    v12 = v26;
    v26 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_7;
  }
  v23 = (int *)&v22;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
  if ( v25 )
  {
    v13 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v14 = 201;
    goto LABEL_21;
  }
  if ( v22 )
  {
    v16 = SRCacheContext_EnumerateData(v22, 0, a3);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v16,
        v21[0]);
      v14 = 204;
      goto LABEL_21;
    }
  }
  v17 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"PackageFamily\\Index\\PackageFamilyName");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    v14 = 207;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)v6,
      v21[0]);
    v15 = v22;
    v22 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v26;
  v26 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x180049bb0  push    rbp
0x180049bb2  push    rbx
0x180049bb3  push    rsi
0x180049bb4  push    rdi
0x180049bb5  push    r14
0x180049bb7  lea     rbp, [rsp-180h]
0x180049bbf  sub     rsp, 280h
0x180049bc6  mov     rax, cs:__security_cookie
0x180049bcd  xor     rax, rsp
0x180049bd0  mov     [rbp+1A0h+var_30], rax
0x180049bd7  xor     r14d, r14d
0x180049bda  mov     [rsp+2A0h+var_260], 1
0x180049bdf  mov     [r8], r14
0x180049be2  lea     rax, [rsp+2A0h+var_280]
0x180049be7  mov     rcx, [rcx]
0x180049bea  lea     r9, [rsp+2A0h+var_268]
0x180049bef  mov     rdi, r8
0x180049bf2  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x180049bf7  mov     rsi, rdx
0x180049bfa  mov     [rsp+2A0h+var_270], rax
0x180049bff  xor     r8d, r8d
0x180049c02  mov     [rsp+2A0h+var_268], r14
0x180049c07  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x180049c0e  call    cs:__imp_SRCacheContext_Open
0x180049c14  mov     ebx, eax
0x180049c16  cmp     [rsp+2A0h+var_260], r14b
0x180049c1b  jz      short loc_180049C38
0x180049c1d  mov     r8, [rsp+2A0h+var_270]
0x180049c22  mov     rdx, [rsp+2A0h+var_268]
0x180049c27  mov     rcx, [r8]
0x180049c2a  mov     [r8], rdx
0x180049c2d  test    rcx, rcx
0x180049c30  jz      short loc_180049C38
0x180049c32  call    cs:__imp_SRCacheContext_Close
0x180049c38  test    ebx, ebx
0x180049c3a  jns     short loc_180049C8E
0x180049c3c  mov     rcx, [rbp+1A8h]; this
0x180049c43  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049c4a  mov     r9d, ebx; char *
0x180049c4d  mov     edx, 18Ch; void *
0x180049c52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c57  mov     edx, 0C1h; void *
0x180049c5c  mov     rcx, [rbp+1A8h]; this
0x180049c63  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049c6a  mov     r9d, ebx; char *
0x180049c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c72  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180049c77  mov     qword ptr [rsp+2A0h+var_280], r14
0x180049c7c  test    rcx, rcx
0x180049c7f  jz      short loc_180049C87
0x180049c81  call    cs:__imp_SRCacheContext_Close
0x180049c87  mov     eax, ebx
0x180049c89  jmp     loc_180049E96
0x180049c8e  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180049c93  setnz   al
0x180049c96  test    al, al
0x180049c98  jnz     short loc_180049CA6
0x180049c9a  mov     ebx, 80670012h
0x180049c9f  mov     edx, 0C2h
0x180049ca4  jmp     short loc_180049C5C
0x180049ca6  xor     edx, edx; Val
0x180049ca8  mov     [rsp+2A0h+var_250], r14
0x180049cad  mov     r8d, 200h; Size
0x180049cb3  lea     rcx, [rsp+2A0h+var_248]; void *
0x180049cb8  call    memset_0
0x180049cbd  lea     rax, [rsp+2A0h+var_248]
0x180049cc2  mov     [rbp+1A0h+var_48], r14
0x180049cc9  mov     rdx, rsi; unsigned __int16 *
0x180049ccc  mov     [rbp+1A0h+var_38], rax
0x180049cd3  lea     rcx, [rsp+2A0h+var_250]; this
0x180049cd8  mov     [rbp+1A0h+var_40], 100h
0x180049ce3  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180049ce8  mov     ebx, eax
0x180049cea  test    eax, eax
0x180049cec  jns     short loc_180049D27
0x180049cee  mov     rcx, [rbp+1A8h]; this
0x180049cf5  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049cfc  mov     r9d, eax; char *
0x180049cff  mov     edx, 0C5h; void *
0x180049d04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d09  mov     rcx, [rsp+2A0h+var_250]
0x180049d0e  mov     [rsp+2A0h+var_250], r14
0x180049d13  test    rcx, rcx
0x180049d16  jz      loc_180049C72
0x180049d1c  call    cs:__imp_SRCache_Free
0x180049d22  jmp     loc_180049C72
0x180049d27  mov     rdx, [rbp+1A0h+var_38]
0x180049d2e  lea     rax, [rsp+2A0h+var_278]
0x180049d33  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180049d38  lea     r9, [rsp+2A0h+var_268]
0x180049d3d  xor     r8d, r8d
0x180049d40  mov     [rsp+2A0h+var_270], rax
0x180049d45  mov     [rsp+2A0h+var_278], r14
0x180049d4a  mov     [rsp+2A0h+var_268], r14
0x180049d4f  mov     [rsp+2A0h+var_260], 1
0x180049d54  call    cs:__imp_SRCacheContext_OpenSubContext
0x180049d5a  mov     ebx, eax
0x180049d5c  cmp     [rsp+2A0h+var_260], r14b
0x180049d61  jz      short loc_180049D7E
0x180049d63  mov     r8, [rsp+2A0h+var_270]
0x180049d68  mov     rdx, [rsp+2A0h+var_268]
0x180049d6d  mov     rcx, [r8]
0x180049d70  mov     [r8], rdx
0x180049d73  test    rcx, rcx
0x180049d76  jz      short loc_180049D7E
0x180049d78  call    cs:__imp_SRCacheContext_Close
0x180049d7e  test    ebx, ebx
0x180049d80  jns     short loc_180049DD6
0x180049d82  mov     rcx, [rbp+1A8h]; this
0x180049d89  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049d90  mov     r9d, ebx; char *
0x180049d93  mov     edx, 1B0h; void *
0x180049d98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d9d  mov     edx, 0C9h; void *
0x180049da2  mov     rcx, [rbp+1A8h]; this
0x180049da9  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049db0  mov     r9d, ebx; char *
0x180049db3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049db8  mov     rcx, [rsp+2A0h+var_278]
0x180049dbd  mov     [rsp+2A0h+var_278], r14
0x180049dc2  test    rcx, rcx
0x180049dc5  jz      loc_180049D09
0x180049dcb  call    cs:__imp_SRCacheContext_Close
0x180049dd1  jmp     loc_180049D09
0x180049dd6  mov     rcx, [rsp+2A0h+var_278]
0x180049ddb  test    rcx, rcx
0x180049dde  setnz   al
0x180049de1  test    al, al
0x180049de3  jz      short loc_180049E18
0x180049de5  mov     r8, rdi
0x180049de8  xor     edx, edx
0x180049dea  call    cs:__imp_SRCacheContext_EnumerateData
0x180049df0  mov     ebx, eax
0x180049df2  test    eax, eax
0x180049df4  jns     short loc_180049E18
0x180049df6  mov     rcx, [rbp+1A8h]; this
0x180049dfd  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049e04  mov     r9d, eax; char *
0x180049e07  mov     edx, 2A6h; void *
0x180049e0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e11  mov     edx, 0CCh
0x180049e16  jmp     short loc_180049DA2
0x180049e18  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180049e1d  lea     rdx, aPackagefamilyI; "PackageFamily\\Index\\PackageFamilyName"
0x180049e24  call    cs:__imp_SRCacheContext_AddToCache
0x180049e2a  mov     ebx, eax
0x180049e2c  test    eax, eax
0x180049e2e  jns     short loc_180049E55
0x180049e30  mov     rcx, [rbp+1A8h]; this
0x180049e37  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049e3e  mov     r9d, eax; char *
0x180049e41  mov     edx, 1A6h; void *
0x180049e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e4b  mov     edx, 0CFh
0x180049e50  jmp     loc_180049DA2
0x180049e55  mov     rcx, [rsp+2A0h+var_278]
0x180049e5a  mov     [rsp+2A0h+var_278], r14
0x180049e5f  test    rcx, rcx
0x180049e62  jz      short loc_180049E6A
0x180049e64  call    cs:__imp_SRCacheContext_Close
0x180049e6a  mov     rcx, [rsp+2A0h+var_250]
0x180049e6f  mov     [rsp+2A0h+var_250], r14
0x180049e74  test    rcx, rcx
0x180049e77  jz      short loc_180049E7F
0x180049e79  call    cs:__imp_SRCache_Free
0x180049e7f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180049e84  mov     qword ptr [rsp+2A0h+var_280], r14
0x180049e89  test    rcx, rcx
0x180049e8c  jz      short loc_180049E94
0x180049e8e  call    cs:__imp_SRCacheContext_Close
0x180049e94  xor     eax, eax
0x180049e96  mov     rcx, [rbp+1A0h+var_30]
0x180049e9d  xor     rcx, rsp; StackCookie
0x180049ea0  call    __security_check_cookie
0x180049ea5  add     rsp, 280h
0x180049eac  pop     r14
0x180049eae  pop     rdi
0x180049eaf  pop     rsi
0x180049eb0  pop     rbx
0x180049eb1  pop     rbp
0x180049eb2  retn
```
