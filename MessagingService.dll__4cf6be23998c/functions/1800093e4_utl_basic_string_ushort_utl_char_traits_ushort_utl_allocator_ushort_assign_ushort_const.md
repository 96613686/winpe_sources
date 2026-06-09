# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)

- ea: `0x1800093e4`
- end: `0x18000951e`
- name: `?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z`
- size: `314`
- prototype: `char __fastcall(__int64, _WORD *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008168`
- `0x180009524`
- `0x180009e58`
- `0x18000a328`
- `0x18000a78c`

## callees

- `0x18000266c`
- `0x180002678`
- `0x180002706`
- `0x180002712`
- `0x1800093e4`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        __int64 a1,
        _WORD *a2)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rsi
  char v6; // r15
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  size_t v9; // rbx
  _WORD *v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r12
  char *v15; // rax
  char *v16; // rbp
  size_t v17; // rbx
  char *v18; // rbx

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = (_QWORD *)(a1 + 16);
  v6 = 1;
  v7 = 7;
  if ( *(_QWORD *)a1 == a1 + 16 )
    v8 = 7;
  else
    v8 = (__int64)(*v5 - *(_QWORD *)a1) >> 1;
  if ( v4 <= v8 )
  {
    v9 = 2 * v4;
    memmove_0(*(void **)a1, a2, v9);
    v10 = (_WORD *)(v9 + *(_QWORD *)a1);
    *(_QWORD *)(a1 + 8) = v10;
    *v10 = 0;
    return v6;
  }
  if ( *(_QWORD **)a1 != v5 )
    v7 = (__int64)(*v5 - *(_QWORD *)a1) >> 1;
  v11 = 2 * v7 + 1;
  v12 = v4;
  if ( v11 >= v4 )
    v12 = v11;
  if ( v12 > 0x3FFFFFFFFFFFFFF7LL )
  {
    if ( v4 <= 0x3FFFFFFFFFFFFFF7LL )
    {
      v13 = 0x3FFFFFFFFFFFFFF8LL;
      goto LABEL_19;
    }
    return 0;
  }
  v13 = v12 + 1;
  if ( v12 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    return 0;
LABEL_19:
  v14 = 2 * v13;
  v15 = (char *)operator new(2 * v13, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
    return 0;
  v17 = 2 * v4;
  memcpy_0(v15, a2, v17);
  v18 = &v16[v17];
  *(_WORD *)v18 = 0;
  if ( *(_QWORD **)a1 != v5 )
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)a1 = v16;
  *(_QWORD *)(a1 + 8) = v18;
  *v5 = &v16[v14 - 2];
  return v6;
}

```

## disassembly

```asm
0x1800093e4  push    rbx
0x1800093e6  push    rbp
0x1800093e7  push    rsi
0x1800093e8  push    rdi
0x1800093e9  push    r12
0x1800093eb  push    r13
0x1800093ed  push    r14
0x1800093ef  push    r15
0x1800093f1  sub     rsp, 28h
0x1800093f5  xor     r13d, r13d
0x1800093f8  mov     r14, rdx
0x1800093fb  mov     rdi, rcx
0x1800093fe  test    rdx, rdx
0x180009401  jz      short loc_180009413
0x180009403  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009407  inc     rbx
0x18000940a  cmp     [rdx+rbx*2], r13w
0x18000940f  jnz     short loc_180009407
0x180009411  jmp     short loc_180009416
0x180009413  mov     rbx, r13
0x180009416  lea     rsi, [rcx+10h]
0x18000941a  mov     r15b, 1
0x18000941d  mov     eax, 7
0x180009422  cmp     [rcx], rsi
0x180009425  jnz     short loc_18000942B
0x180009427  mov     ecx, eax
0x180009429  jmp     short loc_180009434
0x18000942b  mov     rcx, [rsi]
0x18000942e  sub     rcx, [rdi]
0x180009431  sar     rcx, 1
0x180009434  cmp     rbx, rcx
0x180009437  ja      short loc_18000945A
0x180009439  mov     rcx, [rdi]; void *
0x18000943c  add     rbx, rbx
0x18000943f  mov     r8, rbx; Size
0x180009442  call    memmove_0
0x180009447  mov     rcx, [rdi]
0x18000944a  add     rcx, rbx
0x18000944d  mov     [rdi+8], rcx
0x180009451  mov     [rcx], r13w
0x180009455  jmp     loc_18000950A
0x18000945a  cmp     [rdi], rsi
0x18000945d  jz      short loc_180009468
0x18000945f  mov     rax, [rsi]
0x180009462  sub     rax, [rdi]
0x180009465  sar     rax, 1
0x180009468  lea     rax, ds:1[rax*2]
0x180009470  mov     rcx, rbx
0x180009473  cmp     rax, rbx
0x180009476  cmovnb  rcx, rax
0x18000947a  mov     rax, 3FFFFFFFFFFFFFF7h
0x180009484  cmp     rcx, rax
0x180009487  jbe     short loc_18000949A
0x180009489  cmp     rbx, rax
0x18000948c  ja      short loc_180009507
0x18000948e  mov     rax, 3FFFFFFFFFFFFFF8h
0x180009498  jmp     short loc_1800094AD
0x18000949a  lea     rax, [rcx+1]
0x18000949e  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1800094a8  cmp     rax, rcx
0x1800094ab  ja      short loc_180009507
0x1800094ad  lea     r12, [rax+rax]
0x1800094b1  mov     rcx, r12; unsigned __int64
0x1800094b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800094bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800094c0  mov     rbp, rax
0x1800094c3  test    rax, rax
0x1800094c6  jz      short loc_180009507
0x1800094c8  add     rbx, rbx
0x1800094cb  mov     rdx, r14; Src
0x1800094ce  mov     r8, rbx; Size
0x1800094d1  mov     rcx, rax; void *
0x1800094d4  call    memcpy_0
0x1800094d9  add     rbx, rbp
0x1800094dc  mov     [rbx], r13w
0x1800094e0  cmp     [rdi], rsi
0x1800094e3  jz      short loc_1800094F4
0x1800094e5  mov     rcx, [rdi]; void *
0x1800094e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800094ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800094f4  lea     rax, [rbp-2]
0x1800094f8  mov     [rdi], rbp
0x1800094fb  add     rax, r12
0x1800094fe  mov     [rdi+8], rbx
0x180009502  mov     [rsi], rax
0x180009505  jmp     short loc_18000950A
0x180009507  mov     r15b, r13b
0x18000950a  mov     al, r15b
0x18000950d  add     rsp, 28h
0x180009511  pop     r15
0x180009513  pop     r14
0x180009515  pop     r13
0x180009517  pop     r12
0x180009519  pop     rdi
0x18000951a  pop     rsi
0x18000951b  pop     rbp
0x18000951c  pop     rbx
0x18000951d  retn
```
