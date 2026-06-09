# CClassAccess::SetClassStorePath(ushort const *,void *)

- ea: `0x18001e690`
- end: `0x18001e713`
- name: `?SetClassStorePath@CClassAccess@@UEAAJPEBGPEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(CClassAccess *this, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002aa0`
- `0x18001e690`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e6de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e6de`

## pseudocode

```c
__int64 __fastcall CClassAccess::SetClassStorePath(CClassAccess *this, const unsigned __int16 *a2, void *a3)
{
  __int64 v7; // rax
  unsigned __int64 v8; // rbp
  SIZE_T v9; // rax
  unsigned __int16 *v10; // rax

  if ( *((_QWORD *)this + 3) )
    return 2147942487LL;
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = (unsigned int)(v7 + 1);
    v9 = 2 * v8;
    if ( !is_mul_ok(v8, 2u) )
      v9 = -1;
    v10 = (unsigned __int16 *)LocalAlloc(0, v9);
    *((_QWORD *)this + 3) = v10;
    if ( !v10 )
      return 2147942414LL;
    StringCchCopyW(v10, v8, a2);
    *((_QWORD *)this + 4) = a3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e690  push    rbx
0x18001e692  push    rbp
0x18001e693  push    rsi
0x18001e694  push    rdi
0x18001e695  push    r14
0x18001e697  sub     rsp, 20h
0x18001e69b  xor     r14d, r14d
0x18001e69e  mov     rsi, r8
0x18001e6a1  mov     rbx, rdx
0x18001e6a4  mov     rdi, rcx
0x18001e6a7  cmp     [rcx+18h], r14
0x18001e6ab  jz      short loc_18001E6B4
0x18001e6ad  mov     eax, 80070057h
0x18001e6b2  jmp     short loc_18001E708
0x18001e6b4  test    rbx, rbx
0x18001e6b7  jz      short loc_18001E706
0x18001e6b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e6bd  mov     rax, rcx
0x18001e6c0  inc     rax
0x18001e6c3  cmp     [rdx+rax*2], r14w
0x18001e6c8  jnz     short loc_18001E6C0
0x18001e6ca  lea     ebp, [rax+1]
0x18001e6cd  mov     eax, 2
0x18001e6d2  mul     rbp
0x18001e6d5  cmovb   rax, rcx
0x18001e6d9  xor     ecx, ecx; uFlags
0x18001e6db  mov     rdx, rax; uBytes
0x18001e6de  call    cs:__imp_LocalAlloc
0x18001e6e4  mov     [rdi+18h], rax
0x18001e6e8  test    rax, rax
0x18001e6eb  jnz     short loc_18001E6F4
0x18001e6ed  mov     eax, 8007000Eh
0x18001e6f2  jmp     short loc_18001E708
0x18001e6f4  mov     r8, rbx; unsigned __int16 *
0x18001e6f7  mov     rdx, rbp; unsigned __int64
0x18001e6fa  mov     rcx, rax; unsigned __int16 *
0x18001e6fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e702  mov     [rdi+20h], rsi
0x18001e706  xor     eax, eax
0x18001e708  add     rsp, 20h
0x18001e70c  pop     r14
0x18001e70e  pop     rdi
0x18001e70f  pop     rsi
0x18001e710  pop     rbp
0x18001e711  pop     rbx
0x18001e712  retn
```
