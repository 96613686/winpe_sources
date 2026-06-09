# StateRepository::CacheContextEntry::Attach(SRCacheContext &,ushort const *)

- ea: `0x18000f6a4`
- end: `0x18000f75a`
- name: `?Attach@CacheContextEntry@StateRepository@@QEAAJAEAUSRCacheContext@@PEBG@Z`
- size: `182`
- prototype: `int(StateRepository::CacheContextEntry *__hidden this, struct SRCacheContext *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000f5c8`

## callees

- `0x1800022a0`
- `0x1800029b8`
- `0x18000940c`
- `0x18000e69c`
- `0x18000ebec`
- `0x18000f580`
- `0x18000f6a4`

## string_xrefs

- `0x18000f716`: `onecore\base\appmodel\staterepository\core\lib\SRCacheContextCache.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::CacheContextEntry::Attach(
        unsigned __int16 **this,
        struct SRCacheContext *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  unsigned __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  StateRepository::Time *v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  SRCacheContext::operator=(this + 1, a2);
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  v6 = 2 * (v5 + 1);
  if ( !is_mul_ok(v5 + 1, 2u) )
    v6 = -1;
  v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v9 = *this;
  *this = v7;
  if ( v9 )
    operator delete(v9, v8);
  if ( !*this )
  {
    v10 = -2147024882;
    v11 = 38;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\SRCacheContextCache.hpp",
      (const char *)(unsigned int)v10,
      v14);
    return (unsigned int)v10;
  }
  v10 = StringCchCopyNW(*this, v5 + 1, a3, v5);
  if ( v10 < 0 )
  {
    v11 = 39;
    goto LABEL_9;
  }
  this[2] = (unsigned __int16 *)StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v13);
  return 0;
}

```

## disassembly

```asm
0x18000f6a4  push    rbx
0x18000f6a6  push    rbp
0x18000f6a7  push    rsi
0x18000f6a8  push    rdi
0x18000f6a9  push    r14; int
0x18000f6ab  sub     rsp, 20h
0x18000f6af  mov     rdi, rcx
0x18000f6b2  mov     rsi, r8
0x18000f6b5  add     rcx, 8
0x18000f6b9  call    ??4SRCacheContext@@QEAAAEAU0@$$QEAU0@@Z; SRCacheContext::operator=(SRCacheContext &&)
0x18000f6be  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f6c2  mov     rbx, rcx
0x18000f6c5  xor     r14d, r14d
0x18000f6c8  inc     rbx
0x18000f6cb  cmp     [rsi+rbx*2], r14w
0x18000f6d0  jnz     short loc_18000F6C8
0x18000f6d2  lea     rbp, [rbx+1]
0x18000f6d6  mov     eax, 2
0x18000f6db  mul     rbp
0x18000f6de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f6e5  cmovb   rax, rcx
0x18000f6e9  mov     rcx, rax; unsigned __int64
0x18000f6ec  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f6f1  mov     rcx, [rdi]; void *
0x18000f6f4  mov     [rdi], rax
0x18000f6f7  test    rcx, rcx
0x18000f6fa  jz      short loc_18000F701
0x18000f6fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f701  mov     rcx, [rdi]; unsigned __int16 *
0x18000f704  test    rcx, rcx
0x18000f707  jnz     short loc_18000F729
0x18000f709  mov     ebx, 8007000Eh
0x18000f70e  lea     edx, [rcx+26h]; void *
0x18000f711  mov     rcx, [rsp+48h]; this
0x18000f716  lea     r8, aOnecoreBaseApp_6; "onecore\\base\\appmodel\\staterepositor"...
0x18000f71d  mov     r9d, ebx; char *
0x18000f720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f725  mov     eax, ebx
0x18000f727  jmp     short loc_18000F74F
0x18000f729  mov     r9, rbx; unsigned __int64
0x18000f72c  mov     r8, rsi; unsigned __int16 *
0x18000f72f  mov     rdx, rbp; unsigned __int64
0x18000f732  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000f737  mov     ebx, eax
0x18000f739  test    eax, eax
0x18000f73b  jns     short loc_18000F744
0x18000f73d  mov     edx, 27h ; '''
0x18000f742  jmp     short loc_18000F711
0x18000f744  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18000f749  mov     [rdi+10h], rax
0x18000f74d  xor     eax, eax
0x18000f74f  add     rsp, 20h
0x18000f753  pop     r14
0x18000f755  pop     rdi
0x18000f756  pop     rsi
0x18000f757  pop     rbp
0x18000f758  pop     rbx
0x18000f759  retn
```
