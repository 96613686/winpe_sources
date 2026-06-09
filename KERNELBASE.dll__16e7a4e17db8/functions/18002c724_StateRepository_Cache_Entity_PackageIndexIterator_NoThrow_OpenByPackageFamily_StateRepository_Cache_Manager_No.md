# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18002c724`
- end: `0x18002ca56`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `818`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002af0c`
- `0x18002c6dc`
- `0x18002d000`

## callees

- `0x18002c724`
- `0x18002f340`
- `0x180058768`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002c85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002c85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002c7a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002c7a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c770`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c7cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c87e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c8d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c97b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c9c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c770`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c7cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c87e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c8d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c97b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c9c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c8bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c944`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c9b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c8bc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c944`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c9b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002c8a1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002c8a1`

## string_xrefs

- `0x18002c921`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002c953`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002c994`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002c9db`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002ca3d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002c906`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002c9fd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002ca22`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v12;
  }
  v6 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v6 )
    SRCacheContext_Close(v6);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_Open(v7, L"Package\\Index\\PackageFamily", 0, &v23);
  if ( v24 )
  {
    v9 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
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
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
  }
  else
  {
    if ( !*(_QWORD *)v21 )
    {
      v12 = -2140733422;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x799,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)0x80670012LL,
        0);
LABEL_25:
      v17 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
      if ( v17 )
        SRCacheContext_Close(v17);
      return v12;
    }
    v25 = 0;
    memset_0(v26, 0, sizeof(v26));
    v27 = 0;
    v29 = v26;
    v28 = 256;
    v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
    if ( v8 < 0 )
    {
      v18 = 1948;
    }
    else
    {
      v22 = (int *)this;
      v23 = 0;
      v24 = 1;
      v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
      if ( v24 )
      {
        v10 = *(_QWORD *)v22;
        *(_QWORD *)v22 = v23;
        if ( v10 )
          SRCacheContext_Close(v10);
      }
      if ( v8 >= 0 )
      {
        if ( *(_QWORD *)this )
          *((_QWORD *)this + 2) = a2;
        v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Package\\Index\\PackageFamily");
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = v25;
          v25 = 0;
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
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A5,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
          (const char *)v12,
          v21[0]);
        v16 = v25;
        v25 = 0;
        if ( v16 )
          SRCache_Free(v16);
        goto LABEL_25;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v21[0]);
      v18 = 1951;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    v19 = v25;
    v25 = 0;
    if ( v19 )
      SRCache_Free(v19);
  }
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c724  mov     [rsp-8+arg_18], rbx
0x18002c729  push    rbp
0x18002c72a  push    rsi
0x18002c72b  push    rdi
0x18002c72c  push    r14
0x18002c72e  push    r15
0x18002c730  lea     rbp, [rsp-170h]
0x18002c738  sub     rsp, 270h
0x18002c73f  mov     rax, cs:__security_cookie
0x18002c746  xor     rax, rsp
0x18002c749  mov     [rbp+190h+var_30], rax
0x18002c750  xor     r15d, r15d
0x18002c753  mov     r14, r8
0x18002c756  mov     rsi, rdx
0x18002c759  mov     rbx, rcx
0x18002c75c  test    r8, r8
0x18002c75f  jz      loc_18002C9D4
0x18002c765  mov     rcx, [rcx]
0x18002c768  mov     [rbx], r15
0x18002c76b  test    rcx, rcx
0x18002c76e  jz      short loc_18002C776
0x18002c770  call    cs:__imp_SRCacheContext_Close
0x18002c776  mov     [rbx+8], r15d
0x18002c77a  lea     rax, [rsp+290h+var_270]
0x18002c77f  mov     [rbx+10h], r15
0x18002c783  lea     r9, [rsp+290h+var_260]
0x18002c788  mov     rcx, [rsi]
0x18002c78b  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18002c792  xor     r8d, r8d
0x18002c795  mov     [rsp+290h+var_268], rax
0x18002c79a  mov     qword ptr [rsp+290h+var_270], r15; int
0x18002c79f  mov     [rsp+290h+var_260], r15
0x18002c7a4  mov     [rsp+290h+var_258], 1
0x18002c7a9  call    cs:__imp_SRCacheContext_Open
0x18002c7af  mov     edi, eax
0x18002c7b1  cmp     [rsp+290h+var_258], r15b
0x18002c7b6  jz      short loc_18002C7D3
0x18002c7b8  mov     r8, [rsp+290h+var_268]
0x18002c7bd  mov     rdx, [rsp+290h+var_260]
0x18002c7c2  mov     rcx, [r8]
0x18002c7c5  mov     [r8], rdx
0x18002c7c8  test    rcx, rcx
0x18002c7cb  jz      short loc_18002C7D3
0x18002c7cd  call    cs:__imp_SRCacheContext_Close
0x18002c7d3  test    edi, edi
0x18002c7d5  js      loc_18002CA1B
0x18002c7db  cmp     qword ptr [rsp+290h+var_270], r15
0x18002c7e0  setnz   al
0x18002c7e3  test    al, al
0x18002c7e5  jz      loc_18002C94C
0x18002c7eb  xor     edx, edx; Val
0x18002c7ed  mov     [rsp+290h+var_250], r15
0x18002c7f2  mov     r8d, 200h; Size
0x18002c7f8  lea     rcx, [rsp+290h+var_248]; void *
0x18002c7fd  call    memset_0
0x18002c802  lea     rax, [rsp+290h+var_248]
0x18002c807  mov     [rbp+190h+var_48], r15
0x18002c80e  mov     rdx, r14; unsigned __int64
0x18002c811  mov     [rbp+190h+var_38], rax
0x18002c818  lea     rcx, [rsp+290h+var_250]; this
0x18002c81d  mov     [rbp+190h+var_40], 100h
0x18002c828  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002c82d  mov     edi, eax
0x18002c82f  test    eax, eax
0x18002c831  js      loc_18002C988
0x18002c837  mov     rdx, [rbp+190h+var_38]
0x18002c83e  lea     r9, [rsp+290h+var_260]
0x18002c843  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002c848  xor     r8d, r8d
0x18002c84b  mov     [rsp+290h+var_268], rbx
0x18002c850  mov     [rsp+290h+var_260], r15
0x18002c855  mov     [rsp+290h+var_258], 1
0x18002c85a  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002c860  mov     edi, eax
0x18002c862  cmp     [rsp+290h+var_258], r15b
0x18002c867  jz      short loc_18002C884
0x18002c869  mov     r8, [rsp+290h+var_268]
0x18002c86e  mov     rdx, [rsp+290h+var_260]
0x18002c873  mov     rcx, [r8]
0x18002c876  mov     [r8], rdx
0x18002c879  test    rcx, rcx
0x18002c87c  jz      short loc_18002C884
0x18002c87e  call    cs:__imp_SRCacheContext_Close
0x18002c884  test    edi, edi
0x18002c886  js      loc_18002C9F6
0x18002c88c  cmp     [rbx], r15
0x18002c88f  jz      short loc_18002C895
0x18002c891  mov     [rbx+10h], rsi
0x18002c895  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002c89a  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18002c8a1  call    cs:__imp_SRCacheContext_AddToCache
0x18002c8a7  mov     ebx, eax
0x18002c8a9  test    eax, eax
0x18002c8ab  js      short loc_18002C8FF
0x18002c8ad  mov     rcx, [rsp+290h+var_250]
0x18002c8b2  mov     [rsp+290h+var_250], r15
0x18002c8b7  test    rcx, rcx
0x18002c8ba  jz      short loc_18002C8C2
0x18002c8bc  call    cs:__imp_SRCache_Free
0x18002c8c2  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002c8c7  mov     qword ptr [rsp+290h+var_270], r15
0x18002c8cc  test    rcx, rcx
0x18002c8cf  jz      short loc_18002C8D7
0x18002c8d1  call    cs:__imp_SRCacheContext_Close
0x18002c8d7  xor     eax, eax
0x18002c8d9  mov     rcx, [rbp+190h+var_30]
0x18002c8e0  xor     rcx, rsp; StackCookie
0x18002c8e3  call    __security_check_cookie
0x18002c8e8  mov     rbx, [rsp+290h+arg_18]
0x18002c8f0  add     rsp, 270h
0x18002c8f7  pop     r15
0x18002c8f9  pop     r14
0x18002c8fb  pop     rdi
0x18002c8fc  pop     rsi
0x18002c8fd  pop     rbp
0x18002c8fe  retn
0x18002c8ff  mov     rcx, [rbp+198h]; this
0x18002c906  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c90d  mov     r9d, ebx; char *
0x18002c910  mov     edx, 1A6h; void *
0x18002c915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c91a  mov     rcx, [rbp+198h]; this
0x18002c921  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c928  mov     r9d, ebx; char *
0x18002c92b  mov     edx, 7A5h; void *
0x18002c930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c935  mov     rcx, [rsp+290h+var_250]
0x18002c93a  mov     [rsp+290h+var_250], r15
0x18002c93f  test    rcx, rcx
0x18002c942  jz      short loc_18002C96C
0x18002c944  call    cs:__imp_SRCache_Free
0x18002c94a  jmp     short loc_18002C96C
0x18002c94c  mov     rcx, [rbp+198h]; this
0x18002c953  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c95a  mov     ebx, 80670012h
0x18002c95f  mov     edx, 799h; void *
0x18002c964  mov     r9d, ebx; char *
0x18002c967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c96c  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002c971  mov     qword ptr [rsp+290h+var_270], r15
0x18002c976  test    rcx, rcx
0x18002c979  jz      short loc_18002C981
0x18002c97b  call    cs:__imp_SRCacheContext_Close
0x18002c981  mov     eax, ebx
0x18002c983  jmp     loc_18002C8D9
0x18002c988  mov     edx, 79Ch; void *
0x18002c98d  mov     rcx, [rbp+198h]; this
0x18002c994  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c99b  mov     r9d, edi; char *
0x18002c99e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9a3  mov     rcx, [rsp+290h+var_250]
0x18002c9a8  mov     [rsp+290h+var_250], r15
0x18002c9ad  test    rcx, rcx
0x18002c9b0  jz      short loc_18002C9B8
0x18002c9b2  call    cs:__imp_SRCache_Free
0x18002c9b8  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002c9bd  mov     qword ptr [rsp+290h+var_270], r15
0x18002c9c2  test    rcx, rcx
0x18002c9c5  jz      short loc_18002C9CD
0x18002c9c7  call    cs:__imp_SRCacheContext_Close
0x18002c9cd  mov     eax, edi
0x18002c9cf  jmp     loc_18002C8D9
0x18002c9d4  mov     rcx, [rbp+198h]; this
0x18002c9db  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c9e2  mov     ebx, 80070057h
0x18002c9e7  mov     edx, 792h; void *
0x18002c9ec  mov     r9d, ebx; char *
0x18002c9ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9f4  jmp     short loc_18002C981
0x18002c9f6  mov     rcx, [rbp+198h]; this
0x18002c9fd  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ca04  mov     r9d, edi; char *
0x18002ca07  mov     edx, 1B0h; void *
0x18002ca0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca11  mov     edx, 79Fh
0x18002ca16  jmp     loc_18002C98D
0x18002ca1b  mov     rcx, [rbp+198h]; this
0x18002ca22  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ca29  mov     r9d, edi; char *
0x18002ca2c  mov     edx, 18Ch; void *
0x18002ca31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca36  mov     rcx, [rbp+198h]; this
0x18002ca3d  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ca44  mov     r9d, edi; char *
0x18002ca47  mov     edx, 798h; void *
0x18002ca4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca51  jmp     loc_18002C9B8
```
