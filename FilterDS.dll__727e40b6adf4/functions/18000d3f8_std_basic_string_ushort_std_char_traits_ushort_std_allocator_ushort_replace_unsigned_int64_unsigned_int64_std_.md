# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000d3f8`
- end: `0x18000d757`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `863`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c238`

## callees

- `0x180002326`
- `0x180002332`
- `0x180006c54`
- `0x180006c6c`
- `0x18000c534`
- `0x18000d3f8`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *Src,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  _QWORD *v7; // r15
  unsigned __int64 v8; // r8
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // r14
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdx
  char *v25; // rdx
  char *v26; // rcx
  size_t v27; // r8
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rbp
  _QWORD *v33; // rcx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  size_t v37; // r8
  char *v38; // rdx
  char *v39; // rcx
  _QWORD *v40; // rax
  _QWORD *v41; // rcx
  __int64 v42; // rbp
  _QWORD *v43; // rax
  _QWORD *v44; // rcx
  _QWORD *v45; // rcx
  _QWORD *v46; // rdx
  _QWORD *v47; // rcx
  unsigned __int64 v49; // [rsp+60h] [rbp+8h]
  unsigned __int64 v50; // [rsp+68h] [rbp+10h]

  v7 = a4;
  v8 = Src[2];
  v10 = Src;
  if ( v8 < a2 || (v11 = a4[2], v11 < a5) )
    std::wstring::_Xran();
  v12 = a6;
  v13 = v8 - a2;
  if ( v8 - a2 < a3 )
    a3 = v8 - a2;
  v14 = v11 - a5;
  if ( v14 < a6 )
    v12 = v14;
  if ( ~v12 <= v8 - a3 )
    std::wstring::_Xlen();
  v50 = v12 - a3;
  v15 = v12 - a3 + v8;
  v49 = v15;
  if ( v8 < v15 )
  {
    if ( v15 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( Src[3] >= v15 )
    {
      if ( !v15 )
      {
        if ( Src[3] >= 8u )
          Src = (_QWORD *)*Src;
        v10[2] = 0;
        *(_WORD *)Src = 0;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)Src, v12 - a3 + v8, v8);
    }
  }
  v16 = v10[3];
  v17 = v13 - a3;
  if ( v10 != v7 )
  {
    if ( v16 < 8 )
    {
      v18 = v10;
      v19 = v10;
    }
    else
    {
      v18 = (_QWORD *)*v10;
      v19 = (_QWORD *)*v10;
    }
    if ( v17 )
    {
      memmove_0((char *)v18 + 2 * a2 + 2 * v12, (char *)v19 + 2 * a2 + 2 * a3, 2 * v17);
      v16 = v10[3];
    }
    if ( v7[3] >= 8u )
      v7 = (_QWORD *)*v7;
    if ( v16 < 8 )
      v20 = v10;
    else
      v20 = (_QWORD *)*v10;
    if ( v12 )
      memcpy_0((char *)v20 + 2 * a2, (char *)v7 + 2 * a5, 2 * v12);
    goto LABEL_80;
  }
  if ( v12 <= a3 )
  {
    if ( v16 < 8 )
    {
      v21 = v10;
      v22 = v10;
    }
    else
    {
      v21 = (_QWORD *)*v10;
      v22 = (_QWORD *)*v10;
    }
    if ( v12 )
      memmove_0((char *)v21 + 2 * a2, (char *)v22 + 2 * a5, 2 * v12);
    if ( v10[3] < 8u )
    {
      v23 = v10;
      v24 = v10;
    }
    else
    {
      v23 = (_QWORD *)*v10;
      v24 = (_QWORD *)*v10;
    }
    if ( v17 )
    {
      v25 = (char *)v24 + 2 * a2 + 2 * a3;
      v26 = (char *)v23 + 2 * a2 + 2 * v12;
      v27 = 2 * v17;
LABEL_51:
      memmove_0(v26, v25, v27);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  if ( a5 > a2 )
  {
    v32 = a2 + a3;
    if ( a2 + a3 > a5 )
    {
      if ( v16 < 8 )
      {
        v40 = v10;
        v41 = v10;
      }
      else
      {
        v40 = (_QWORD *)*v10;
        v41 = (_QWORD *)*v10;
      }
      if ( a3 )
        memmove_0((char *)v40 + 2 * a2, (char *)v41 + 2 * a5, 2 * a3);
      v42 = 2 * v32;
      if ( v10[3] < 8u )
      {
        v44 = v10;
        v43 = v10;
      }
      else
      {
        v43 = (_QWORD *)*v10;
        v44 = (_QWORD *)*v10;
      }
      if ( v17 )
        memmove_0((char *)v44 + 2 * a2 + 2 * v12, (char *)v43 + v42, 2 * v17);
      if ( v10[3] < 8u )
      {
        v45 = v10;
        v46 = v10;
      }
      else
      {
        v45 = (_QWORD *)*v10;
        v46 = (_QWORD *)*v10;
      }
      if ( !v50 )
        goto LABEL_79;
      v37 = 2 * v50;
      v38 = (char *)v46 + 2 * v12 + 2 * a5;
      v39 = (char *)v45 + v42;
    }
    else
    {
      if ( v16 < 8 )
      {
        v33 = v10;
        v34 = v10;
      }
      else
      {
        v33 = (_QWORD *)*v10;
        v34 = (_QWORD *)*v10;
      }
      if ( v17 )
        memmove_0((char *)v33 + 2 * a2 + 2 * v12, (char *)v34 + 2 * v32, 2 * v17);
      if ( v10[3] < 8u )
      {
        v35 = v10;
        v36 = v10;
      }
      else
      {
        v35 = (_QWORD *)*v10;
        v36 = (_QWORD *)*v10;
      }
      if ( !v12 )
        goto LABEL_79;
      v37 = 2 * v12;
      v38 = (char *)v36 + 2 * v12 + 2 * (a5 - a3);
      v39 = (char *)v35 + 2 * a2;
    }
    memmove_0(v39, v38, v37);
LABEL_79:
    v15 = v49;
    goto LABEL_80;
  }
  if ( v16 < 8 )
  {
    v28 = v10;
    v29 = v10;
  }
  else
  {
    v28 = (_QWORD *)*v10;
    v29 = (_QWORD *)*v10;
  }
  if ( v17 )
    memmove_0((char *)v28 + 2 * a2 + 2 * v12, (char *)v29 + 2 * a2 + 2 * a3, 2 * v17);
  if ( v10[3] < 8u )
  {
    v30 = v10;
    v31 = v10;
  }
  else
  {
    v30 = (_QWORD *)*v10;
    v31 = (_QWORD *)*v10;
  }
  if ( v12 )
  {
    v25 = (char *)v31 + 2 * a5;
    v26 = (char *)v30 + 2 * a2;
    v27 = 2 * v12;
    goto LABEL_51;
  }
LABEL_80:
  if ( v10[3] < 8u )
    v47 = v10;
  else
    v47 = (_QWORD *)*v10;
  v10[2] = v15;
  *((_WORD *)v47 + v15) = 0;
  return v10;
}

```

## disassembly

```asm
0x18000d3f8  mov     [rsp+arg_10], rbx
0x18000d3fd  push    rbp
0x18000d3fe  push    rsi
0x18000d3ff  push    rdi
0x18000d400  push    r12
0x18000d402  push    r13
0x18000d404  push    r14
0x18000d406  push    r15
0x18000d408  sub     rsp, 20h
0x18000d40c  mov     r12, r8
0x18000d40f  mov     r15, r9
0x18000d412  mov     r8, [rcx+10h]
0x18000d416  mov     rsi, rdx
0x18000d419  mov     rbx, rcx
0x18000d41c  cmp     r8, rdx
0x18000d41f  jb      loc_18000D745
0x18000d425  mov     rax, [r9+10h]
0x18000d429  mov     r13, [rsp+58h+arg_20]
0x18000d431  cmp     rax, r13
0x18000d434  jb      loc_18000D745
0x18000d43a  mov     rdi, [rsp+58h+arg_28]
0x18000d442  mov     r14, r8
0x18000d445  sub     r14, rdx
0x18000d448  mov     rcx, r8
0x18000d44b  cmp     r14, r12
0x18000d44e  cmovb   r12, r14
0x18000d452  sub     rax, r13
0x18000d455  cmp     rax, rdi
0x18000d458  cmovb   rdi, rax
0x18000d45c  sub     rcx, r12
0x18000d45f  mov     rax, rdi
0x18000d462  not     rax
0x18000d465  cmp     rax, rcx
0x18000d468  jbe     loc_18000D74B
0x18000d46e  mov     rax, rdi
0x18000d471  sub     rax, r12
0x18000d474  mov     [rsp+58h+arg_8], rax
0x18000d479  lea     rbp, [rax+r8]
0x18000d47d  mov     [rsp+58h+arg_0], rbp
0x18000d482  cmp     r8, rbp
0x18000d485  jnb     short loc_18000D4CE
0x18000d487  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000d491  cmp     rbp, rax
0x18000d494  ja      loc_18000D751
0x18000d49a  cmp     [rbx+18h], rbp
0x18000d49e  jnb     short loc_18000D4AD
0x18000d4a0  mov     rdx, rbp
0x18000d4a3  mov     rcx, rbx; Src
0x18000d4a6  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000d4ab  jmp     short loc_18000D4CE
0x18000d4ad  test    rbp, rbp
0x18000d4b0  jnz     short loc_18000D4CE
0x18000d4b2  cmp     qword ptr [rbx+18h], 8
0x18000d4b7  jb      short loc_18000D4BE
0x18000d4b9  mov     rcx, [rbx]
0x18000d4bc  jmp     short loc_18000D4C1
0x18000d4be  mov     rcx, rbx
0x18000d4c1  xor     eax, eax
0x18000d4c3  mov     qword ptr [rbx+10h], 0
0x18000d4cb  mov     [rcx], ax
0x18000d4ce  mov     rax, [rbx+18h]
0x18000d4d2  sub     r14, r12
0x18000d4d5  cmp     rbx, r15
0x18000d4d8  jz      short loc_18000D547
0x18000d4da  cmp     rax, 8
0x18000d4de  jb      short loc_18000D4E8
0x18000d4e0  mov     rcx, [rbx]
0x18000d4e3  mov     rdx, rcx
0x18000d4e6  jmp     short loc_18000D4EE
0x18000d4e8  mov     rcx, rbx
0x18000d4eb  mov     rdx, rbx
0x18000d4ee  test    r14, r14
0x18000d4f1  jz      short loc_18000D510
0x18000d4f3  lea     rax, [rsi+r12]
0x18000d4f7  lea     rdx, [rdx+rax*2]; Src
0x18000d4fb  lea     rax, [rsi+rdi]
0x18000d4ff  lea     rcx, [rcx+rax*2]; void *
0x18000d503  lea     r8, [r14+r14]; Size
0x18000d507  call    memmove_0
0x18000d50c  mov     rax, [rbx+18h]
0x18000d510  cmp     qword ptr [r15+18h], 8
0x18000d515  jb      short loc_18000D51A
0x18000d517  mov     r15, [r15]
0x18000d51a  cmp     rax, 8
0x18000d51e  jb      short loc_18000D525
0x18000d520  mov     rax, [rbx]
0x18000d523  jmp     short loc_18000D528
0x18000d525  mov     rax, rbx
0x18000d528  test    rdi, rdi
0x18000d52b  jz      loc_18000D714
0x18000d531  lea     r8, [rdi+rdi]; Size
0x18000d535  lea     rdx, [r15+r13*2]; Src
0x18000d539  lea     rcx, [rax+rsi*2]; void *
0x18000d53d  call    memcpy_0
0x18000d542  jmp     loc_18000D714
0x18000d547  cmp     rdi, r12
0x18000d54a  ja      short loc_18000D5AA
0x18000d54c  cmp     rax, 8
0x18000d550  jb      short loc_18000D55A
0x18000d552  mov     rax, [rbx]
0x18000d555  mov     rcx, rax
0x18000d558  jmp     short loc_18000D560
0x18000d55a  mov     rax, rbx
0x18000d55d  mov     rcx, rbx
0x18000d560  test    rdi, rdi
0x18000d563  jz      short loc_18000D576
0x18000d565  lea     rdx, [rcx+r13*2]; Src
0x18000d569  lea     rcx, [rax+rsi*2]; void *
0x18000d56d  lea     r8, [rdi+rdi]; Size
0x18000d571  call    memmove_0
0x18000d576  cmp     qword ptr [rbx+18h], 8
0x18000d57b  jb      short loc_18000D585
0x18000d57d  mov     rcx, [rbx]
0x18000d580  mov     rdx, rcx
0x18000d583  jmp     short loc_18000D58B
0x18000d585  mov     rcx, rbx
0x18000d588  mov     rdx, rbx
0x18000d58b  test    r14, r14
0x18000d58e  jz      loc_18000D714
0x18000d594  lea     rax, [rsi+r12]
0x18000d598  lea     rdx, [rdx+rax*2]
0x18000d59c  lea     rax, [rsi+rdi]
0x18000d5a0  lea     rcx, [rcx+rax*2]
0x18000d5a4  lea     r8, [r14+r14]
0x18000d5a8  jmp     short loc_18000D60B
0x18000d5aa  cmp     r13, rsi
0x18000d5ad  ja      short loc_18000D615
0x18000d5af  cmp     rax, 8
0x18000d5b3  jb      short loc_18000D5BD
0x18000d5b5  mov     rcx, [rbx]
0x18000d5b8  mov     rdx, rcx
0x18000d5bb  jmp     short loc_18000D5C3
0x18000d5bd  mov     rcx, rbx
0x18000d5c0  mov     rdx, rbx
0x18000d5c3  test    r14, r14
0x18000d5c6  jz      short loc_18000D5E1
0x18000d5c8  lea     rax, [rsi+r12]
0x18000d5cc  lea     rdx, [rdx+rax*2]; Src
0x18000d5d0  lea     rax, [rsi+rdi]
0x18000d5d4  lea     rcx, [rcx+rax*2]; void *
0x18000d5d8  lea     r8, [r14+r14]; Size
0x18000d5dc  call    memmove_0
0x18000d5e1  cmp     qword ptr [rbx+18h], 8
0x18000d5e6  jb      short loc_18000D5F0
0x18000d5e8  mov     rax, [rbx]
0x18000d5eb  mov     rcx, rax
0x18000d5ee  jmp     short loc_18000D5F6
0x18000d5f0  mov     rax, rbx
0x18000d5f3  mov     rcx, rbx
0x18000d5f6  test    rdi, rdi
0x18000d5f9  jz      loc_18000D714
0x18000d5ff  lea     rdx, [rcx+r13*2]; Src
0x18000d603  lea     rcx, [rax+rsi*2]; void *
0x18000d607  lea     r8, [rdi+rdi]; Size
0x18000d60b  call    memmove_0
0x18000d610  jmp     loc_18000D714
0x18000d615  lea     rbp, [rsi+r12]
0x18000d619  cmp     rbp, r13
0x18000d61c  ja      short loc_18000D681
0x18000d61e  cmp     rax, 8
0x18000d622  jb      short loc_18000D62C
0x18000d624  mov     rcx, [rbx]
0x18000d627  mov     rax, rcx
0x18000d62a  jmp     short loc_18000D632
0x18000d62c  mov     rcx, rbx
0x18000d62f  mov     rax, rbx
0x18000d632  test    r14, r14
0x18000d635  jz      short loc_18000D64C
0x18000d637  lea     rdx, [rax+rbp*2]; Src
0x18000d63b  lea     rax, [rsi+rdi]
0x18000d63f  lea     rcx, [rcx+rax*2]; void *
0x18000d643  lea     r8, [r14+r14]; Size
0x18000d647  call    memmove_0
0x18000d64c  cmp     qword ptr [rbx+18h], 8
0x18000d651  jb      short loc_18000D65B
0x18000d653  mov     rax, [rbx]
0x18000d656  mov     rcx, rax
0x18000d659  jmp     short loc_18000D661
0x18000d65b  mov     rax, rbx
0x18000d65e  mov     rcx, rbx
0x18000d661  test    rdi, rdi
0x18000d664  jz      loc_18000D70F
0x18000d66a  sub     r13, r12
0x18000d66d  lea     r8, [rdi+rdi]
0x18000d671  add     r13, rdi
0x18000d674  lea     rdx, [rcx+r13*2]
0x18000d678  lea     rcx, [rax+rsi*2]
0x18000d67c  jmp     loc_18000D70A
0x18000d681  cmp     rax, 8
0x18000d685  jb      short loc_18000D68F
0x18000d687  mov     rax, [rbx]
0x18000d68a  mov     rcx, rax
0x18000d68d  jmp     short loc_18000D695
0x18000d68f  mov     rax, rbx
0x18000d692  mov     rcx, rbx
0x18000d695  test    r12, r12
0x18000d698  jz      short loc_18000D6AB
0x18000d69a  lea     rdx, [rcx+r13*2]; Src
0x18000d69e  lea     rcx, [rax+rsi*2]; void *
0x18000d6a2  lea     r8, [r12+r12]; Size
0x18000d6a6  call    memmove_0
0x18000d6ab  add     rbp, rbp
0x18000d6ae  cmp     qword ptr [rbx+18h], 8
0x18000d6b3  jb      short loc_18000D6BD
0x18000d6b5  mov     rax, [rbx]
0x18000d6b8  mov     rcx, rax
0x18000d6bb  jmp     short loc_18000D6C3
0x18000d6bd  mov     rcx, rbx
0x18000d6c0  mov     rax, rbx
0x18000d6c3  test    r14, r14
0x18000d6c6  jz      short loc_18000D6DD
0x18000d6c8  lea     rdx, [rax+rbp]; Src
0x18000d6cc  lea     rax, [rsi+rdi]
0x18000d6d0  lea     rcx, [rcx+rax*2]; void *
0x18000d6d4  lea     r8, [r14+r14]; Size
0x18000d6d8  call    memmove_0
0x18000d6dd  cmp     qword ptr [rbx+18h], 8
0x18000d6e2  jb      short loc_18000D6EC
0x18000d6e4  mov     rcx, [rbx]
0x18000d6e7  mov     rdx, rcx
0x18000d6ea  jmp     short loc_18000D6F2
0x18000d6ec  mov     rcx, rbx
0x18000d6ef  mov     rdx, rbx
0x18000d6f2  mov     r8, [rsp+58h+arg_8]
0x18000d6f7  test    r8, r8
0x18000d6fa  jz      short loc_18000D70F
0x18000d6fc  add     r8, r8; Size
0x18000d6ff  lea     rax, [rdi+r13]
0x18000d703  lea     rdx, [rdx+rax*2]; Src
0x18000d707  add     rcx, rbp; void *
0x18000d70a  call    memmove_0
0x18000d70f  mov     rbp, [rsp+58h+arg_0]
0x18000d714  cmp     qword ptr [rbx+18h], 8
0x18000d719  jb      short loc_18000D720
0x18000d71b  mov     rcx, [rbx]
0x18000d71e  jmp     short loc_18000D723
0x18000d720  mov     rcx, rbx
0x18000d723  xor     eax, eax
0x18000d725  mov     [rbx+10h], rbp
0x18000d729  mov     [rcx+rbp*2], ax
0x18000d72d  mov     rax, rbx
0x18000d730  mov     rbx, [rsp+58h+arg_10]
0x18000d735  add     rsp, 20h
0x18000d739  pop     r15
0x18000d73b  pop     r14
0x18000d73d  pop     r13
0x18000d73f  pop     r12
0x18000d741  pop     rdi
0x18000d742  pop     rsi
0x18000d743  pop     rbp
0x18000d744  retn
0x18000d745  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000d74b  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18000d751  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
