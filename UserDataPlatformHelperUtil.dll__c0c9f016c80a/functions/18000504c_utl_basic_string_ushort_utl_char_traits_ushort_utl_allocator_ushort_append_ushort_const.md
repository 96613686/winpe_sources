# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)

- ea: `0x18000504c`
- end: `0x180005163`
- name: `?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z`
- size: `279`
- prototype: `char __fastcall(_QWORD *, _WORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004b80`
- `0x1800061e0`

## callees

- `0x180001178`
- `0x180002c0c`
- `0x18000504c`
- `0x18000a142`
- `0x18000a14e`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        _QWORD *a1,
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
  v5 = (void *)a1[1];
  v6 = ((__int64)v5 - *a1) >> 1;
  v7 = v6 + v4;
  if ( v6 + v4 < v4 )
    return 0;
  v9 = a1 + 2;
  v8 = 1;
  if ( (_QWORD *)*a1 == a1 + 2 )
    v10 = 7;
  else
    v10 = (__int64)(*v9 - *a1) >> 1;
  if ( v7 > v10 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      a1,
      v15,
      v6 + v4);
    v11 = v15[0];
    if ( v15[0] )
    {
      v12 = v6;
      memcpy_0(v15[0], (const void *)*a1, v12 * 2);
      memcpy_0(&v11[v12], a2, 2 * v4);
      v13 = v15[1];
      v11[v7] = 0;
      if ( (_QWORD *)*a1 != v9 )
        operator delete((void *)*a1);
      *a1 = v11;
      a1[1] = &v11[v7];
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
    a1[1] += 2 * v4;
    *(_WORD *)a1[1] = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18000504c  push    rbx
0x18000504e  push    rbp
0x18000504f  push    rsi
0x180005050  push    rdi
0x180005051  push    r12
0x180005053  push    r13
0x180005055  push    r14
0x180005057  push    r15
0x180005059  sub     rsp, 38h
0x18000505d  xor     r14d, r14d
0x180005060  mov     r12, rdx
0x180005063  mov     rdi, rcx
0x180005066  test    rdx, rdx
0x180005069  jz      short loc_18000507B
0x18000506b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000506f  inc     rsi
0x180005072  cmp     [rdx+rsi*2], r14w
0x180005077  jnz     short loc_18000506F
0x180005079  jmp     short loc_18000507E
0x18000507b  mov     rsi, r14
0x18000507e  mov     rcx, [rcx+8]; void *
0x180005082  mov     rbx, rcx
0x180005085  sub     rbx, [rdi]
0x180005088  sar     rbx, 1
0x18000508b  lea     r15, [rbx+rsi]
0x18000508f  cmp     r15, rsi
0x180005092  jnb     short loc_18000509C
0x180005094  mov     bpl, r14b
0x180005097  jmp     loc_18000514F
0x18000509c  lea     r13, [rdi+10h]
0x1800050a0  mov     bpl, 1
0x1800050a3  cmp     [rdi], r13
0x1800050a6  jnz     short loc_1800050AF
0x1800050a8  mov     eax, 7
0x1800050ad  jmp     short loc_1800050B9
0x1800050af  mov     rax, [r13+0]
0x1800050b3  sub     rax, [rdi]
0x1800050b6  sar     rax, 1
0x1800050b9  cmp     r15, rax
0x1800050bc  ja      short loc_1800050D8
0x1800050be  lea     rbx, [rsi+rsi]
0x1800050c2  mov     r8, rbx; Size
0x1800050c5  call    memmove_0
0x1800050ca  add     [rdi+8], rbx
0x1800050ce  mov     rcx, [rdi+8]
0x1800050d2  mov     [rcx], r14w
0x1800050d6  jmp     short loc_18000514F
0x1800050d8  mov     r8, r15
0x1800050db  lea     rdx, [rsp+78h+var_58]
0x1800050e0  mov     rcx, rdi
0x1800050e3  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x1800050e8  mov     r14, [rsp+78h+var_58]
0x1800050ed  test    r14, r14
0x1800050f0  jz      short loc_18000514C
0x1800050f2  mov     rdx, [rdi]; Src
0x1800050f5  add     rbx, rbx
0x1800050f8  mov     r8, rbx; Size
0x1800050fb  mov     rcx, r14; void *
0x1800050fe  call    memcpy_0
0x180005103  lea     r8, [rsi+rsi]; Size
0x180005107  mov     rdx, r12; Src
0x18000510a  lea     rcx, [rbx+r14]; void *
0x18000510e  call    memcpy_0
0x180005113  mov     rbx, [rsp+78h+var_50]
0x180005118  xor     eax, eax
0x18000511a  mov     [r14+r15*2], ax
0x18000511f  cmp     [rdi], r13
0x180005122  jz      short loc_180005133
0x180005124  mov     rcx, [rdi]; Block
0x180005127  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000512e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005133  lea     rax, [r14+r15*2]
0x180005137  mov     [rdi], r14
0x18000513a  mov     [rdi+8], rax
0x18000513e  lea     rax, [rbx-1]
0x180005142  lea     rax, [r14+rax*2]
0x180005146  mov     [r13+0], rax
0x18000514a  jmp     short loc_18000514F
0x18000514c  xor     bpl, bpl
0x18000514f  mov     al, bpl
0x180005152  add     rsp, 38h
0x180005156  pop     r15
0x180005158  pop     r14
0x18000515a  pop     r13
0x18000515c  pop     r12
0x18000515e  pop     rdi
0x18000515f  pop     rsi
0x180005160  pop     rbp
0x180005161  pop     rbx
0x180005162  retn
```
