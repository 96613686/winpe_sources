# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)

- ea: `0x180002cb0`
- end: `0x180002d92`
- name: `?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z`
- size: `226`
- prototype: `char __fastcall(_QWORD *, _WORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800028c0`
- `0x180004b80`

## callees

- `0x180001178`
- `0x180002c0c`
- `0x180002cb0`
- `0x18000a142`
- `0x18000a14e`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        _QWORD *a1,
        _WORD *a2)
{
  unsigned __int64 v4; // rbx
  _QWORD *v5; // r14
  char v6; // r15
  unsigned __int64 v7; // rax
  size_t v8; // rbx
  _WORD *v9; // rcx
  char *v10; // rsi
  size_t v11; // rbx
  void *v12; // rbp
  void *v14[9]; // [rsp+20h] [rbp-48h] BYREF

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
  v5 = a1 + 2;
  v6 = 1;
  if ( (_QWORD *)*a1 == a1 + 2 )
    v7 = 7;
  else
    v7 = (__int64)(*v5 - *a1) >> 1;
  if ( v4 > v7 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      a1,
      v14,
      v4);
    v10 = (char *)v14[0];
    if ( v14[0] )
    {
      v11 = 2 * v4;
      memcpy_0(v14[0], a2, v11);
      v12 = v14[1];
      *(_WORD *)&v10[v11] = 0;
      if ( (_QWORD *)*a1 != v5 )
        operator delete((void *)*a1);
      *a1 = v10;
      a1[1] = &v10[v11];
      *v5 = &v10[2 * ((__int64)v12 - 1)];
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v8 = 2 * v4;
    memmove_0((void *)*a1, a2, v8);
    v9 = (_WORD *)(v8 + *a1);
    a1[1] = v9;
    *v9 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180002cb0  push    rbx
0x180002cb2  push    rbp
0x180002cb3  push    rsi
0x180002cb4  push    rdi
0x180002cb5  push    r12
0x180002cb7  push    r14
0x180002cb9  push    r15
0x180002cbb  sub     rsp, 30h
0x180002cbf  xor     r12d, r12d
0x180002cc2  mov     rbp, rdx
0x180002cc5  mov     rdi, rcx
0x180002cc8  test    rdx, rdx
0x180002ccb  jz      short loc_180002CDD
0x180002ccd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002cd1  inc     rbx
0x180002cd4  cmp     [rdx+rbx*2], r12w
0x180002cd9  jnz     short loc_180002CD1
0x180002cdb  jmp     short loc_180002CE0
0x180002cdd  mov     rbx, r12
0x180002ce0  lea     r14, [rcx+10h]
0x180002ce4  mov     r15b, 1
0x180002ce7  cmp     [rcx], r14
0x180002cea  jnz     short loc_180002CF3
0x180002cec  mov     eax, 7
0x180002cf1  jmp     short loc_180002CFC
0x180002cf3  mov     rax, [r14]
0x180002cf6  sub     rax, [rcx]
0x180002cf9  sar     rax, 1
0x180002cfc  cmp     rbx, rax
0x180002cff  ja      short loc_180002D1F
0x180002d01  mov     rcx, [rcx]; void *
0x180002d04  add     rbx, rbx
0x180002d07  mov     r8, rbx; Size
0x180002d0a  call    memmove_0
0x180002d0f  mov     rcx, [rdi]
0x180002d12  add     rcx, rbx
0x180002d15  mov     [rdi+8], rcx
0x180002d19  mov     [rcx], r12w
0x180002d1d  jmp     short loc_180002D80
0x180002d1f  mov     r8, rbx
0x180002d22  lea     rdx, [rsp+68h+var_48]
0x180002d27  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x180002d2c  mov     rsi, [rsp+68h+var_48]
0x180002d31  test    rsi, rsi
0x180002d34  jz      short loc_180002D7D
0x180002d36  add     rbx, rbx
0x180002d39  mov     rdx, rbp; Src
0x180002d3c  mov     r8, rbx; Size
0x180002d3f  mov     rcx, rsi; void *
0x180002d42  call    memcpy_0
0x180002d47  mov     rbp, [rsp+68h+var_40]
0x180002d4c  mov     [rbx+rsi], r12w
0x180002d51  cmp     [rdi], r14
0x180002d54  jz      short loc_180002D65
0x180002d56  mov     rcx, [rdi]; Block
0x180002d59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180002d60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002d65  lea     rax, [rbx+rsi]
0x180002d69  mov     [rdi], rsi
0x180002d6c  mov     [rdi+8], rax
0x180002d70  lea     rax, [rbp-1]
0x180002d74  lea     rax, [rsi+rax*2]
0x180002d78  mov     [r14], rax
0x180002d7b  jmp     short loc_180002D80
0x180002d7d  mov     r15b, r12b
0x180002d80  mov     al, r15b
0x180002d83  add     rsp, 30h
0x180002d87  pop     r15
0x180002d89  pop     r14
0x180002d8b  pop     r12
0x180002d8d  pop     rdi
0x180002d8e  pop     rsi
0x180002d8f  pop     rbp
0x180002d90  pop     rbx
0x180002d91  retn
```
