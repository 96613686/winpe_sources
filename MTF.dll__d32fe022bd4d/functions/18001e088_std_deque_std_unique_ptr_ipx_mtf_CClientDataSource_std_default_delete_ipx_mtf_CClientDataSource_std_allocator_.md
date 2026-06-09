# std::deque<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>,std::allocator<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>>>::_Growmap(unsigned __int64)

- ea: `0x18001e088`
- end: `0x18001e1ee`
- name: `?_Growmap@?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180014a00`

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180002972`
- `0x18001e088`
- `0x18001e244`
- `0x18002bc62`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e1c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e1c5`

## pseudocode

```c
void __fastcall std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rbp
  unsigned __int64 v5; // r12
  char *v6; // rax
  char *v7; // r15
  unsigned __int64 v8; // r12
  size_t v9; // rbx
  char *v10; // rax
  const void *v11; // rdx
  char *v12; // rcx
  char *v13; // rax
  char *v14; // rcx
  size_t v15; // r8
  size_t v16; // rsi
  char *v17; // rax
  void *v18; // rcx

  v1 = a1[2];
  v3 = 1;
  if ( v1 )
    v3 = v1;
  while ( 1 )
  {
    v4 = v3 - v1;
    if ( v3 != v1 && v3 >= 8 )
      break;
    if ( 0xFFFFFFFFFFFFFFFLL - v3 < v3 )
      std::deque<ipx::mtf::MtfTransportClientCoreUI::RESULTITEM>::_Xlen();
    v3 *= 2LL;
  }
  if ( v3 > 0x1FFFFFFFFFFFFFFFLL || (v5 = a1[3], v6 = (char *)operator new(8 * v3), (v7 = v6) == 0) )
    std::_Xbad_alloc();
  v8 = v5 >> 1;
  v9 = (8LL * a1[2] - 8 * v8) & 0xFFFFFFFFFFFFFFF8uLL;
  v10 = (char *)memmove_0(&v6[8 * v8], (const void *)(8 * v8 + a1[1]), v9);
  v11 = (const void *)a1[1];
  v12 = &v10[v9];
  if ( v8 > v4 )
  {
    memmove_0(v12, v11, 8 * v4);
    v16 = (8 * v8 - 8 * v4) & 0xFFFFFFFFFFFFFFF8uLL;
    v17 = (char *)memmove_0(v7, (const void *)(8 * v4 + a1[1]), v16);
    v15 = 8 * v4;
    v14 = &v17[v16];
    goto LABEL_15;
  }
  v13 = (char *)memmove_0(v12, v11, 8 * v8) + 8 * v8;
  if ( v4 != v8 )
    memset_0(v13, 0, 8 * (v4 - v8));
  if ( v8 )
  {
    v14 = v7;
    v15 = 8 * v8;
LABEL_15:
    memset_0(v14, 0, v15);
  }
  v18 = (void *)a1[1];
  if ( v18 )
    operator delete(v18);
  a1[2] += v4;
  a1[1] = v7;
}

```

## disassembly

```asm
0x18001e088  push    rbx
0x18001e08a  push    rbp
0x18001e08b  push    rsi
0x18001e08c  push    rdi
0x18001e08d  push    r12
0x18001e08f  push    r14
0x18001e091  push    r15
0x18001e093  sub     rsp, 20h
0x18001e097  mov     rdx, [rcx+10h]
0x18001e09b  mov     rdi, rcx
0x18001e09e  test    rdx, rdx
0x18001e0a1  mov     ecx, 1
0x18001e0a6  cmovnz  rcx, rdx
0x18001e0aa  mov     rbp, rcx
0x18001e0ad  sub     rbp, rdx
0x18001e0b0  cmp     rbp, 1
0x18001e0b4  jb      short loc_18001E0BC
0x18001e0b6  cmp     rcx, 8
0x18001e0ba  jnb     short loc_18001E0D7
0x18001e0bc  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001e0c6  sub     rax, rcx
0x18001e0c9  cmp     rax, rcx
0x18001e0cc  jb      loc_18001E1E2
0x18001e0d2  add     rcx, rcx
0x18001e0d5  jmp     short loc_18001E0AA
0x18001e0d7  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001e0e1  cmp     rcx, rax
0x18001e0e4  ja      loc_18001E1E8
0x18001e0ea  mov     r12, [rdi+18h]
0x18001e0ee  shl     rcx, 3; Size
0x18001e0f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e0f7  mov     r15, rax
0x18001e0fa  test    rax, rax
0x18001e0fd  jz      loc_18001E1E8
0x18001e103  mov     rcx, [rdi+8]
0x18001e107  mov     rbx, [rdi+10h]
0x18001e10b  shl     rbx, 3
0x18001e10f  shr     r12, 1
0x18001e112  lea     rsi, ds:0[r12*8]
0x18001e11a  lea     rdx, [rsi+rcx]; Src
0x18001e11e  sub     rbx, rdx
0x18001e121  add     rbx, rcx
0x18001e124  lea     rcx, [rsi+rax]; void *
0x18001e128  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001e12c  mov     r8, rbx; Size
0x18001e12f  call    memmove_0
0x18001e134  mov     rdx, [rdi+8]; Src
0x18001e138  lea     rcx, [rax+rbx]; void *
0x18001e13c  cmp     r12, rbp
0x18001e13f  ja      short loc_18001E17D
0x18001e141  mov     rbx, rsi
0x18001e144  mov     r14, rbp
0x18001e147  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001e14b  mov     r8, rbx; Size
0x18001e14e  call    memmove_0
0x18001e153  add     rax, rbx
0x18001e156  sub     r14, r12
0x18001e159  jz      short loc_18001E16C
0x18001e15b  shl     r14, 3
0x18001e15f  xor     edx, edx; Val
0x18001e161  mov     r8, r14; Size
0x18001e164  mov     rcx, rax; void *
0x18001e167  call    memset_0
0x18001e16c  test    r12, r12
0x18001e16f  jz      short loc_18001E1BC
0x18001e171  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18001e175  mov     rcx, r15
0x18001e178  mov     r8, rsi
0x18001e17b  jmp     short loc_18001E1B5
0x18001e17d  lea     rbx, ds:0[rbp*8]
0x18001e185  mov     r8, rbx; Size
0x18001e188  call    memmove_0
0x18001e18d  mov     rax, [rdi+8]
0x18001e191  mov     rcx, r15; void *
0x18001e194  lea     rdx, [rbx+rax]; Src
0x18001e198  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001e19c  sub     rsi, rdx
0x18001e19f  add     rsi, rax
0x18001e1a2  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18001e1a6  mov     r8, rsi; Size
0x18001e1a9  call    memmove_0
0x18001e1ae  mov     r8, rbx; Size
0x18001e1b1  lea     rcx, [rsi+rax]; void *
0x18001e1b5  xor     edx, edx; Val
0x18001e1b7  call    memset_0
0x18001e1bc  mov     rcx, [rdi+8]
0x18001e1c0  test    rcx, rcx
0x18001e1c3  jz      short loc_18001E1CB
0x18001e1c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e1cb  add     [rdi+10h], rbp
0x18001e1cf  mov     [rdi+8], r15
0x18001e1d3  add     rsp, 20h
0x18001e1d7  pop     r15
0x18001e1d9  pop     r14
0x18001e1db  pop     r12
0x18001e1dd  pop     rdi
0x18001e1de  pop     rsi
0x18001e1df  pop     rbp
0x18001e1e0  pop     rbx
0x18001e1e1  retn
0x18001e1e2  call    ?_Xlen@?$deque@URESULTITEM@MtfTransportClientCoreUI@mtf@ipx@@V?$allocator@URESULTITEM@MtfTransportClientCoreUI@mtf@ipx@@@std@@@std@@IEBAXXZ; std::deque<ipx::mtf::MtfTransportClientCoreUI::RESULTITEM>::_Xlen(void)
0x18001e1e8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
