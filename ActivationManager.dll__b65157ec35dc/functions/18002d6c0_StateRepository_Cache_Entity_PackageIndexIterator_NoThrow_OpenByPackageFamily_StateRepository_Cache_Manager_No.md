# StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x18002d6c0`
- end: `0x18002d9f0`
- name: `?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `816`
- prototype: `int(StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002ce50`
- `0x18002d678`

## callees

- `0x180008be0`
- `0x18000b5c0`
- `0x18002d6c0`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002d8d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18002d8d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002d768`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18002d768`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d72f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d78c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d7db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d827`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d8fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d9c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d72f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d78c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d7db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d827`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d8fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d9c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d8a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d993`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d9ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d8a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d993`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002d9ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002d93e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002d93e`

## string_xrefs

- `0x18002d79d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002d90b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002d951`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002d704`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002d7b8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002d7fb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002d886`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002d96c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
        StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
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
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x792,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v6;
  }
  v8 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v8 )
    SRCacheContext_Close(v8);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v9 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v10 = SRCacheContext_Open(v9, L"Package\\Index\\PackageFamily", 0, &v23);
  if ( v24 )
  {
    v11 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v11 )
      SRCacheContext_Close(v11);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
LABEL_11:
    v12 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v10;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x799,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_16:
    v13 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
  if ( v10 < 0 )
  {
    v14 = 1948;
    goto LABEL_20;
  }
  v22 = (int *)this;
  v23 = 0;
  v24 = 1;
  v10 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
  if ( v24 )
  {
    v16 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v16 )
      SRCacheContext_Close(v16);
  }
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    v14 = 1951;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_11;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Package\\Index\\PackageFamily");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_16;
  }
  v19 = v25;
  v25 = 0;
  if ( v19 )
    SRCache_Free();
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x18002d6c0  mov     [rsp-8+arg_18], rbx
0x18002d6c5  push    rbp
0x18002d6c6  push    rsi
0x18002d6c7  push    rdi
0x18002d6c8  push    r14
0x18002d6ca  push    r15
0x18002d6cc  lea     rbp, [rsp-170h]
0x18002d6d4  sub     rsp, 270h
0x18002d6db  mov     rax, cs:__security_cookie
0x18002d6e2  xor     rax, rsp
0x18002d6e5  mov     [rbp+190h+var_30], rax
0x18002d6ec  xor     r15d, r15d
0x18002d6ef  mov     r14, r8
0x18002d6f2  mov     rsi, rdx
0x18002d6f5  mov     rbx, rcx
0x18002d6f8  test    r8, r8
0x18002d6fb  jnz     short loc_18002D724
0x18002d6fd  mov     rcx, [rbp+198h]; this
0x18002d704  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d70b  mov     ebx, 80070057h
0x18002d710  mov     edx, 792h; void *
0x18002d715  mov     r9d, ebx; char *
0x18002d718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d71d  mov     eax, ebx
0x18002d71f  jmp     loc_18002D9CA
0x18002d724  mov     rcx, [rcx]
0x18002d727  mov     [rbx], r15
0x18002d72a  test    rcx, rcx
0x18002d72d  jz      short loc_18002D735
0x18002d72f  call    cs:__imp_SRCacheContext_Close
0x18002d735  mov     [rbx+8], r15d
0x18002d739  lea     rax, [rsp+290h+var_270]
0x18002d73e  mov     [rbx+10h], r15
0x18002d742  lea     r9, [rsp+290h+var_260]
0x18002d747  mov     rcx, [rsi]
0x18002d74a  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18002d751  xor     r8d, r8d
0x18002d754  mov     [rsp+290h+var_268], rax
0x18002d759  mov     qword ptr [rsp+290h+var_270], r15; int
0x18002d75e  mov     [rsp+290h+var_260], r15
0x18002d763  mov     [rsp+290h+var_258], 1
0x18002d768  call    cs:__imp_SRCacheContext_Open
0x18002d76e  mov     edi, eax
0x18002d770  cmp     [rsp+290h+var_258], r15b
0x18002d775  jz      short loc_18002D792
0x18002d777  mov     r8, [rsp+290h+var_268]
0x18002d77c  mov     rdx, [rsp+290h+var_260]
0x18002d781  mov     rcx, [r8]
0x18002d784  mov     [r8], rdx
0x18002d787  test    rcx, rcx
0x18002d78a  jz      short loc_18002D792
0x18002d78c  call    cs:__imp_SRCacheContext_Close
0x18002d792  test    edi, edi
0x18002d794  jns     short loc_18002D7E8
0x18002d796  mov     rcx, [rbp+198h]; this
0x18002d79d  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d7a4  mov     r9d, edi; char *
0x18002d7a7  mov     edx, 18Ch; void *
0x18002d7ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d7b1  mov     rcx, [rbp+198h]; this
0x18002d7b8  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d7bf  mov     r9d, edi; char *
0x18002d7c2  mov     edx, 798h; void *
0x18002d7c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d7cc  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002d7d1  mov     qword ptr [rsp+290h+var_270], r15
0x18002d7d6  test    rcx, rcx
0x18002d7d9  jz      short loc_18002D7E1
0x18002d7db  call    cs:__imp_SRCacheContext_Close
0x18002d7e1  mov     eax, edi
0x18002d7e3  jmp     loc_18002D9CA
0x18002d7e8  cmp     qword ptr [rsp+290h+var_270], r15
0x18002d7ed  setnz   al
0x18002d7f0  test    al, al
0x18002d7f2  jnz     short loc_18002D832
0x18002d7f4  mov     rcx, [rbp+198h]; this
0x18002d7fb  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d802  mov     ebx, 80670012h
0x18002d807  mov     edx, 799h; void *
0x18002d80c  mov     r9d, ebx; char *
0x18002d80f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d814  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002d819  mov     qword ptr [rsp+290h+var_270], r15
0x18002d81e  test    rcx, rcx
0x18002d821  jz      loc_18002D71D
0x18002d827  call    cs:__imp_SRCacheContext_Close
0x18002d82d  jmp     loc_18002D71D
0x18002d832  xor     edx, edx; Val
0x18002d834  mov     [rsp+290h+var_250], r15
0x18002d839  mov     r8d, 200h; Size
0x18002d83f  lea     rcx, [rsp+290h+var_248]; void *
0x18002d844  call    memset_0
0x18002d849  lea     rax, [rsp+290h+var_248]
0x18002d84e  mov     [rbp+190h+var_48], r15
0x18002d855  mov     rdx, r14; unsigned __int64
0x18002d858  mov     [rbp+190h+var_38], rax
0x18002d85f  lea     rcx, [rsp+290h+var_250]; this
0x18002d864  mov     [rbp+190h+var_40], 100h
0x18002d86f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18002d874  mov     edi, eax
0x18002d876  test    eax, eax
0x18002d878  jns     short loc_18002D8B3
0x18002d87a  mov     edx, 79Ch; void *
0x18002d87f  mov     rcx, [rbp+198h]; this
0x18002d886  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d88d  mov     r9d, edi; char *
0x18002d890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d895  mov     rcx, [rsp+290h+var_250]
0x18002d89a  mov     [rsp+290h+var_250], r15
0x18002d89f  test    rcx, rcx
0x18002d8a2  jz      loc_18002D7CC
0x18002d8a8  call    cs:__imp_SRCache_Free
0x18002d8ae  jmp     loc_18002D7CC
0x18002d8b3  mov     rdx, [rbp+190h+var_38]
0x18002d8ba  lea     r9, [rsp+290h+var_260]
0x18002d8bf  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002d8c4  xor     r8d, r8d
0x18002d8c7  mov     [rsp+290h+var_268], rbx
0x18002d8cc  mov     [rsp+290h+var_260], r15
0x18002d8d1  mov     [rsp+290h+var_258], 1
0x18002d8d6  call    cs:__imp_SRCacheContext_OpenSubContext
0x18002d8dc  mov     edi, eax
0x18002d8de  cmp     [rsp+290h+var_258], r15b
0x18002d8e3  jz      short loc_18002D900
0x18002d8e5  mov     r8, [rsp+290h+var_268]
0x18002d8ea  mov     rdx, [rsp+290h+var_260]
0x18002d8ef  mov     rcx, [r8]
0x18002d8f2  mov     [r8], rdx
0x18002d8f5  test    rcx, rcx
0x18002d8f8  jz      short loc_18002D900
0x18002d8fa  call    cs:__imp_SRCacheContext_Close
0x18002d900  test    edi, edi
0x18002d902  jns     short loc_18002D929
0x18002d904  mov     rcx, [rbp+198h]; this
0x18002d90b  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d912  mov     r9d, edi; char *
0x18002d915  mov     edx, 1B0h; void *
0x18002d91a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d91f  mov     edx, 79Fh
0x18002d924  jmp     loc_18002D87F
0x18002d929  cmp     [rbx], r15
0x18002d92c  jz      short loc_18002D932
0x18002d92e  mov     [rbx+10h], rsi
0x18002d932  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002d937  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFamily"
0x18002d93e  call    cs:__imp_SRCacheContext_AddToCache
0x18002d944  mov     ebx, eax
0x18002d946  test    eax, eax
0x18002d948  jns     short loc_18002D99E
0x18002d94a  mov     rcx, [rbp+198h]; this
0x18002d951  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d958  mov     r9d, eax; char *
0x18002d95b  mov     edx, 1A6h; void *
0x18002d960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d965  mov     rcx, [rbp+198h]; this
0x18002d96c  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d973  mov     r9d, ebx; char *
0x18002d976  mov     edx, 7A5h; void *
0x18002d97b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d980  mov     rcx, [rsp+290h+var_250]
0x18002d985  mov     [rsp+290h+var_250], r15
0x18002d98a  test    rcx, rcx
0x18002d98d  jz      loc_18002D814
0x18002d993  call    cs:__imp_SRCache_Free
0x18002d999  jmp     loc_18002D814
0x18002d99e  mov     rcx, [rsp+290h+var_250]
0x18002d9a3  mov     [rsp+290h+var_250], r15
0x18002d9a8  test    rcx, rcx
0x18002d9ab  jz      short loc_18002D9B3
0x18002d9ad  call    cs:__imp_SRCache_Free
0x18002d9b3  mov     rcx, qword ptr [rsp+290h+var_270]
0x18002d9b8  mov     qword ptr [rsp+290h+var_270], r15
0x18002d9bd  test    rcx, rcx
0x18002d9c0  jz      short loc_18002D9C8
0x18002d9c2  call    cs:__imp_SRCacheContext_Close
0x18002d9c8  xor     eax, eax
0x18002d9ca  mov     rcx, [rbp+190h+var_30]
0x18002d9d1  xor     rcx, rsp; StackCookie
0x18002d9d4  call    __security_check_cookie
0x18002d9d9  mov     rbx, [rsp+290h+arg_18]
0x18002d9e1  add     rsp, 270h
0x18002d9e8  pop     r15
0x18002d9ea  pop     r14
0x18002d9ec  pop     rdi
0x18002d9ed  pop     rsi
0x18002d9ee  pop     rbp
0x18002d9ef  retn
```
