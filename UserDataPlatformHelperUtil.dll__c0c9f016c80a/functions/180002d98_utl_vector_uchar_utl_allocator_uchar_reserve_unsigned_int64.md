# utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)

- ea: `0x180002d98`
- end: `0x180002e4b`
- name: `?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z`
- size: `179`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002980`
- `0x180003930`
- `0x180003a80`

## callees

- `0x180001178`
- `0x1800016e8`
- `0x180002d98`
- `0x18000a142`

## pseudocode

```c
char __fastcall utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(__int64 a1, size_t a2)
{
  size_t v3; // rax
  size_t v4; // rdi
  char *v5; // rax
  char *v6; // rsi
  char *v7; // rdi
  void *v8; // rcx
  char *v9; // rbp

  v3 = *(_QWORD *)(a1 + 16) - *(_QWORD *)a1;
  if ( a2 <= v3 )
    return 1;
  v4 = 7 * (v3 >> 2) + 8;
  if ( v4 < a2 )
    v4 = a2;
  if ( v4 > 0x7FFFFFFFFFFFFFFFLL )
    v4 = 0x7FFFFFFFFFFFFFFFLL;
  if ( a2 <= v4 )
  {
    v5 = (char *)operator new(v4, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v7 = &v5[v4];
      memcpy_0(v5, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
      v8 = *(void **)a1;
      v9 = &v6[*(_QWORD *)(a1 + 8) - *(_QWORD *)a1];
      if ( *(_QWORD *)a1 != -1 )
      {
        *(_QWORD *)(a1 + 8) = v8;
        operator delete(v8);
      }
      *(_QWORD *)a1 = v6;
      *(_QWORD *)(a1 + 8) = v9;
      *(_QWORD *)(a1 + 16) = v7;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002d98  push    rbx
0x180002d9a  push    rbp
0x180002d9b  push    rsi
0x180002d9c  push    rdi
0x180002d9d  sub     rsp, 28h
0x180002da1  mov     rax, [rcx+10h]
0x180002da5  mov     rbx, rcx
0x180002da8  sub     rax, [rcx]
0x180002dab  cmp     rdx, rax
0x180002dae  jbe     loc_180002E3C
0x180002db4  shr     rax, 2
0x180002db8  imul    rdi, rax, 7
0x180002dbc  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002dc6  add     rdi, 8
0x180002dca  cmp     rdi, rdx
0x180002dcd  cmovb   rdi, rdx
0x180002dd1  cmp     rdi, rax
0x180002dd4  cmova   rdi, rax
0x180002dd8  cmp     rdx, rdi
0x180002ddb  ja      short loc_180002E47
0x180002ddd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002de4  mov     rcx, rdi; unsigned __int64
0x180002de7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002dec  mov     rsi, rax
0x180002def  lea     rcx, [rax-1]
0x180002df3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180002df7  ja      short loc_180002E47
0x180002df9  mov     r8, [rbx+8]
0x180002dfd  mov     rcx, rax; void *
0x180002e00  sub     r8, [rbx]; Size
0x180002e03  add     rdi, rax
0x180002e06  mov     rdx, [rbx]; Src
0x180002e09  call    memcpy_0
0x180002e0e  mov     rcx, [rbx]; Block
0x180002e11  mov     rbp, [rbx+8]
0x180002e15  sub     rbp, rcx
0x180002e18  add     rbp, rsi
0x180002e1b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002e1f  jz      short loc_180002E31
0x180002e21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180002e28  mov     [rbx+8], rcx
0x180002e2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002e31  mov     [rbx], rsi
0x180002e34  mov     [rbx+8], rbp
0x180002e38  mov     [rbx+10h], rdi
0x180002e3c  mov     al, 1
0x180002e3e  add     rsp, 28h
0x180002e42  pop     rdi
0x180002e43  pop     rsi
0x180002e44  pop     rbp
0x180002e45  pop     rbx
0x180002e46  retn
0x180002e47  xor     al, al
0x180002e49  jmp     short loc_180002E3E
```
