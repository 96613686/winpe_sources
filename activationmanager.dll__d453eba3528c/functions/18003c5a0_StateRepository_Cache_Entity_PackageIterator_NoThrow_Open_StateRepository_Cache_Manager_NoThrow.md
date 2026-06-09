# StateRepository::Cache::Entity::PackageIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)

- ea: `0x18003c5a0`
- end: `0x18003c6cd`
- name: `?Open@PackageIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z`
- size: `301`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009d60`

## callees

- `0x18000b5c0`
- `0x18003c5a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18003c62b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18003c62b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c5f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c64f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c5f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003c64f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003c5bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18003c5bf`

## string_xrefs

- `0x18003c5ce`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003c65e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18003c677`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18003c69a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageIterator_NoThrow::Open(
        StateRepository::Cache::Entity::PackageIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  int v11; // [rsp+20h] [rbp-28h]
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF
  char v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = SRCacheContext_AddToCache(*(_QWORD *)this, L"Package\\Data");
  if ( v4 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v4,
      v10);
  v5 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v5 )
    SRCacheContext_Close(v5);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v6 = *(_QWORD *)a2;
  v12 = 0;
  v13 = 1;
  v7 = SRCacheContext_Open(v6, L"Package\\Data", 0, &v12);
  if ( v13 )
  {
    v8 = *(_QWORD *)this;
    *(_QWORD *)this = v12;
    if ( v8 )
      SRCacheContext_Close(v8);
  }
  if ( (v7 & 0x80000000) == 0 )
  {
    if ( *(_QWORD *)this )
    {
      *((_QWORD *)this + 2) = a2;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x717,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)0x80670012LL,
        (int)this);
      return 2154233874LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v7,
      (int)this);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x716,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v7,
      v11);
    return v7;
  }
}

```

## disassembly

```asm
0x18003c5a0  mov     [rsp+arg_0], rbx
0x18003c5a5  mov     [rsp+arg_8], rsi
0x18003c5aa  push    rdi
0x18003c5ab  sub     rsp, 40h
0x18003c5af  mov     rsi, rdx
0x18003c5b2  mov     rbx, rcx
0x18003c5b5  mov     rcx, [rcx]
0x18003c5b8  lea     rdx, aPackageData; "Package\\Data"
0x18003c5bf  call    cs:__imp_SRCacheContext_AddToCache
0x18003c5c5  test    eax, eax
0x18003c5c7  jns     short loc_18003C5E2
0x18003c5c9  mov     rcx, [rsp+48h]; this
0x18003c5ce  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c5d5  mov     r9d, eax; char *
0x18003c5d8  mov     edx, 1A6h; void *
0x18003c5dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5e2  mov     rcx, [rbx]
0x18003c5e5  mov     qword ptr [rbx], 0
0x18003c5ec  test    rcx, rcx
0x18003c5ef  jz      short loc_18003C5F7
0x18003c5f1  call    cs:__imp_SRCacheContext_Close
0x18003c5f7  mov     dword ptr [rbx+8], 0
0x18003c5fe  lea     r9, [rsp+48h+var_20]
0x18003c603  mov     qword ptr [rbx+10h], 0
0x18003c60b  lea     rdx, aPackageData; "Package\\Data"
0x18003c612  mov     rcx, [rsi]
0x18003c615  xor     r8d, r8d
0x18003c618  mov     qword ptr [rsp+48h+var_28], rbx; int
0x18003c61d  mov     [rsp+48h+var_20], 0
0x18003c626  mov     [rsp+48h+var_18], 1
0x18003c62b  call    cs:__imp_SRCacheContext_Open
0x18003c631  cmp     [rsp+48h+var_18], 0
0x18003c636  mov     edi, eax
0x18003c638  jz      short loc_18003C655
0x18003c63a  mov     r9, qword ptr [rsp+48h+var_28]
0x18003c63f  mov     rdx, [rsp+48h+var_20]
0x18003c644  mov     rcx, [r9]
0x18003c647  mov     [r9], rdx
0x18003c64a  test    rcx, rcx
0x18003c64d  jz      short loc_18003C655
0x18003c64f  call    cs:__imp_SRCacheContext_Close
0x18003c655  test    edi, edi
0x18003c657  jns     short loc_18003C68F
0x18003c659  mov     rcx, [rsp+48h]; this
0x18003c65e  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c665  mov     r9d, edi; char *
0x18003c668  mov     edx, 18Ch; void *
0x18003c66d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c672  mov     rcx, [rsp+48h]; this
0x18003c677  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c67e  mov     r9d, edi; char *
0x18003c681  mov     edx, 716h; void *
0x18003c686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c68b  mov     eax, edi
0x18003c68d  jmp     short loc_18003C6BD
0x18003c68f  cmp     qword ptr [rbx], 0
0x18003c693  jnz     short loc_18003C6B7
0x18003c695  mov     rcx, [rsp+48h]; this
0x18003c69a  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c6a1  mov     ebx, 80670012h
0x18003c6a6  mov     edx, 717h; void *
0x18003c6ab  mov     r9d, ebx; char *
0x18003c6ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c6b3  mov     eax, ebx
0x18003c6b5  jmp     short loc_18003C6BD
0x18003c6b7  mov     [rbx+10h], rsi
0x18003c6bb  xor     eax, eax
0x18003c6bd  mov     rbx, [rsp+48h+arg_0]
0x18003c6c2  mov     rsi, [rsp+48h+arg_8]
0x18003c6c7  add     rsp, 40h
0x18003c6cb  pop     rdi
0x18003c6cc  retn
```
