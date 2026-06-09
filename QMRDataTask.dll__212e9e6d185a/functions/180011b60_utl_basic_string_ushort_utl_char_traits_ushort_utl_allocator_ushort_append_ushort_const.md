# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)

- ea: `0x180011b60`
- end: `0x180011c77`
- name: `?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009494`
- `0x18000a1c0`
- `0x18000b290`
- `0x18000ebf8`
- `0x18000ef08`
- `0x18000f418`

## callees

- `0x180001d06`
- `0x180001d12`
- `0x180002178`
- `0x1800114e8`
- `0x180011b60`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        __int64 a1,
        _WORD *a2)
{
  unsigned __int64 v4; // rsi
  void *v5; // rcx
  __int64 v6; // rbx
  unsigned __int64 v7; // r15
  char v8; // bp
  _QWORD *v9; // r13
  unsigned __int64 v10; // rax
  _WORD *v11; // r14
  size_t v12; // rbx
  void *v13; // rbx
  void *v15[11]; // [rsp+20h] [rbp-58h] BYREF

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
  v5 = *(void **)(a1 + 8);
  v6 = ((__int64)v5 - *(_QWORD *)a1) >> 1;
  v7 = v6 + v4;
  if ( v6 + v4 < v4 )
    return 0;
  v9 = (_QWORD *)(a1 + 16);
  v8 = 1;
  if ( *(_QWORD *)a1 == a1 + 16 )
    v10 = 7;
  else
    v10 = (__int64)(*v9 - *(_QWORD *)a1) >> 1;
  if ( v7 > v10 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      a1,
      v15);
    v11 = v15[0];
    if ( v15[0] )
    {
      v12 = v6;
      memcpy_0(v15[0], *(const void **)a1, v12 * 2);
      memcpy_0(&v11[v12], a2, 2 * v4);
      v13 = v15[1];
      v11[v7] = 0;
      if ( *(_QWORD **)a1 != v9 )
        operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)a1 = v11;
      *(_QWORD *)(a1 + 8) = &v11[v7];
      *v9 = &v11[(__int64)v13 - 1];
    }
    else
    {
      return 0;
    }
  }
  else
  {
    memmove_0(v5, a2, 2 * v4);
    *(_QWORD *)(a1 + 8) += 2 * v4;
    **(_WORD **)(a1 + 8) = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180011b60  push    rbx
0x180011b62  push    rbp
0x180011b63  push    rsi
0x180011b64  push    rdi
0x180011b65  push    r12
0x180011b67  push    r13
0x180011b69  push    r14
0x180011b6b  push    r15
0x180011b6d  sub     rsp, 38h
0x180011b71  xor     r14d, r14d
0x180011b74  mov     r12, rdx
0x180011b77  mov     rdi, rcx
0x180011b7a  test    rdx, rdx
0x180011b7d  jz      short loc_180011B8F
0x180011b7f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011b83  inc     rsi
0x180011b86  cmp     [rdx+rsi*2], r14w
0x180011b8b  jnz     short loc_180011B83
0x180011b8d  jmp     short loc_180011B92
0x180011b8f  mov     rsi, r14
0x180011b92  mov     rcx, [rcx+8]; void *
0x180011b96  mov     rbx, rcx
0x180011b99  sub     rbx, [rdi]
0x180011b9c  sar     rbx, 1
0x180011b9f  lea     r15, [rbx+rsi]
0x180011ba3  cmp     r15, rsi
0x180011ba6  jnb     short loc_180011BB0
0x180011ba8  mov     bpl, r14b
0x180011bab  jmp     loc_180011C63
0x180011bb0  lea     r13, [rdi+10h]
0x180011bb4  mov     bpl, 1
0x180011bb7  cmp     [rdi], r13
0x180011bba  jnz     short loc_180011BC3
0x180011bbc  mov     eax, 7
0x180011bc1  jmp     short loc_180011BCD
0x180011bc3  mov     rax, [r13+0]
0x180011bc7  sub     rax, [rdi]
0x180011bca  sar     rax, 1
0x180011bcd  cmp     r15, rax
0x180011bd0  ja      short loc_180011BEC
0x180011bd2  lea     rbx, [rsi+rsi]
0x180011bd6  mov     r8, rbx; Size
0x180011bd9  call    memmove_0
0x180011bde  add     [rdi+8], rbx
0x180011be2  mov     rcx, [rdi+8]
0x180011be6  mov     [rcx], r14w
0x180011bea  jmp     short loc_180011C63
0x180011bec  mov     r8, r15
0x180011bef  lea     rdx, [rsp+78h+var_58]
0x180011bf4  mov     rcx, rdi
0x180011bf7  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x180011bfc  mov     r14, [rsp+78h+var_58]
0x180011c01  test    r14, r14
0x180011c04  jz      short loc_180011C60
0x180011c06  mov     rdx, [rdi]; Src
0x180011c09  add     rbx, rbx
0x180011c0c  mov     r8, rbx; Size
0x180011c0f  mov     rcx, r14; void *
0x180011c12  call    memcpy_0
0x180011c17  lea     r8, [rsi+rsi]; Size
0x180011c1b  mov     rdx, r12; Src
0x180011c1e  lea     rcx, [rbx+r14]; void *
0x180011c22  call    memcpy_0
0x180011c27  mov     rbx, [rsp+78h+var_50]
0x180011c2c  xor     eax, eax
0x180011c2e  mov     [r14+r15*2], ax
0x180011c33  cmp     [rdi], r13
0x180011c36  jz      short loc_180011C47
0x180011c38  mov     rcx, [rdi]; void *
0x180011c3b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011c42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011c47  lea     rax, [r14+r15*2]
0x180011c4b  mov     [rdi], r14
0x180011c4e  mov     [rdi+8], rax
0x180011c52  lea     rax, [rbx-1]
0x180011c56  lea     rax, [r14+rax*2]
0x180011c5a  mov     [r13+0], rax
0x180011c5e  jmp     short loc_180011C63
0x180011c60  xor     bpl, bpl
0x180011c63  mov     al, bpl
0x180011c66  add     rsp, 38h
0x180011c6a  pop     r15
0x180011c6c  pop     r14
0x180011c6e  pop     r13
0x180011c70  pop     r12
0x180011c72  pop     rdi
0x180011c73  pop     rsi
0x180011c74  pop     rbp
0x180011c75  pop     rbx
0x180011c76  retn
```
