# DIGEST_CONTEXT_CACHE::AddContextCacheEntry(_SecHandle *)

- ea: `0x1800048d0`
- end: `0x1800049ee`
- name: `?AddContextCacheEntry@DIGEST_CONTEXT_CACHE@@QEAAJPEAU_SecHandle@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(DIGEST_CONTEXT_CACHE *__hidden this, struct _SecHandle *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001a38`
- `0x180003200`

## callees

- `0x1800048d0`
- `0x180006600`
- `0x180007010`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000494d`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000494d`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180004920`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180004920`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004992`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004992`

## pseudocode

```c
__int64 __fastcall DIGEST_CONTEXT_CACHE::AddContextCacheEntry(DIGEST_CONTEXT_CACHE *this, struct _SecHandle *a2)
{
  __int128 v4; // xmm0
  char *v5; // rbx
  unsigned int v6; // edi
  char *v7; // rax
  char *v8; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+28h] [rbp-20h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v4 = (__int128)*a2;
  v8 = 0;
  v9 = v4;
  if ( !(unsigned int)CLKRHashTable::FindKey((char *)this + 8, &v9, &v8) )
  {
    v5 = v8;
    *((_DWORD *)v8 + 4) = 2;
    v6 = -2147467259;
    if ( !v5 )
      return v6;
LABEL_8:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(char *, __int64))v5)(v5, 1);
    return v6;
  }
  v7 = (char *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry);
  v5 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 1162036036;
    *(_QWORD *)v7 = &DIGEST_CONTEXT_CACHE_ENTRY::`vftable';
    *((_DWORD *)v7 + 3) = 1;
    *((_DWORD *)v7 + 4) = 2;
    *((_QWORD *)v7 + 5) = this;
    *(_OWORD *)(v7 + 24) = v9;
    v6 = (unsigned int)CLKRHashTable::InsertRecord((char *)this + 8, v7, 0) != 0 ? 0x80004005 : 0;
    goto LABEL_8;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800048d0  mov     [rsp+arg_8], rbx
0x1800048d5  mov     [rsp+arg_10], rsi
0x1800048da  push    rdi
0x1800048db  sub     rsp, 40h
0x1800048df  mov     rax, cs:__security_cookie
0x1800048e6  xor     rax, rsp
0x1800048e9  mov     [rsp+48h+var_10], rax
0x1800048ee  mov     rdi, rcx
0x1800048f1  test    rdx, rdx
0x1800048f4  jnz     short loc_180004900
0x1800048f6  mov     eax, 80070057h
0x1800048fb  jmp     loc_1800049D1
0x180004900  movups  xmm0, xmmword ptr [rdx]
0x180004903  lea     r8, [rsp+48h+var_28]
0x180004908  mov     [rsp+48h+var_28], 0
0x180004911  lea     rdx, [rsp+48h+var_20]
0x180004916  add     rcx, 8
0x18000491a  movdqu  [rsp+48h+var_20], xmm0
0x180004920  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180004926  test    eax, eax
0x180004928  jnz     short loc_180004946
0x18000492a  mov     rbx, [rsp+48h+var_28]
0x18000492f  mov     dword ptr [rbx+10h], 2
0x180004936  mov     edi, 80004005h
0x18000493b  test    rbx, rbx
0x18000493e  jz      loc_1800049C8
0x180004944  jmp     short loc_1800049A5
0x180004946  mov     rcx, cs:?sm_pachDigestContextCacheEntry@DIGEST_CONTEXT_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry
0x18000494d  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180004953  mov     rbx, rax
0x180004956  test    rax, rax
0x180004959  jz      short loc_1800049CC
0x18000495b  mov     dword ptr [rbx+8], 45434344h
0x180004962  lea     rax, ??_7DIGEST_CONTEXT_CACHE_ENTRY@@6B@; const DIGEST_CONTEXT_CACHE_ENTRY::`vftable'
0x180004969  mov     [rbx], rax
0x18000496c  lea     rcx, [rdi+8]
0x180004970  mov     dword ptr [rbx+0Ch], 1
0x180004977  xor     r8d, r8d
0x18000497a  mov     dword ptr [rbx+10h], 2
0x180004981  mov     rdx, rbx
0x180004984  mov     [rbx+28h], rdi
0x180004988  movups  xmm0, [rsp+48h+var_20]
0x18000498d  movdqu  xmmword ptr [rbx+18h], xmm0
0x180004992  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180004998  neg     eax
0x18000499a  mov     edi, 80004005h
0x18000499f  sbb     r8d, r8d
0x1800049a2  and     edi, r8d
0x1800049a5  or      r8d, 0FFFFFFFFh
0x1800049a9  lock xadd [rbx+0Ch], r8d
0x1800049af  cmp     r8d, 1
0x1800049b3  jnz     short loc_1800049C8
0x1800049b5  mov     r8, [rbx]
0x1800049b8  mov     edx, 1
0x1800049bd  mov     rcx, rbx
0x1800049c0  mov     rax, [r8]
0x1800049c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c8  mov     eax, edi
0x1800049ca  jmp     short loc_1800049D1
0x1800049cc  mov     eax, 80070008h
0x1800049d1  mov     rcx, [rsp+48h+var_10]
0x1800049d6  xor     rcx, rsp; StackCookie
0x1800049d9  call    __security_check_cookie
0x1800049de  mov     rbx, [rsp+48h+arg_8]
0x1800049e3  mov     rsi, [rsp+48h+arg_10]
0x1800049e8  add     rsp, 40h
0x1800049ec  pop     rdi
0x1800049ed  retn
```
