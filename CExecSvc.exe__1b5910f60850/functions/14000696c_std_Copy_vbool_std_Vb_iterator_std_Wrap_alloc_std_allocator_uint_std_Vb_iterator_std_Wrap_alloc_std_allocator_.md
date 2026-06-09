# std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x14000696c`
- end: `0x140006dab`
- name: `??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `1087`
- prototype: `__int64 *__fastcall(__int64 *, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cd1c`

## callees

- `0x140004061`
- `0x14000696c`

## pseudocode

```c
__int64 *__fastcall std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  unsigned int *v4; // rax
  unsigned __int64 *v5; // r13
  unsigned int *v7; // r9
  unsigned __int64 *v8; // r11
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r14
  int *v12; // r8
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  char v20; // cl
  unsigned __int64 v21; // rdx
  int v22; // r9d
  unsigned int v23; // ebp
  unsigned int v24; // r12d
  int v25; // ebx
  int *v26; // rax
  int v27; // r9d
  unsigned __int64 v28; // rcx
  char v29; // cl
  unsigned int v30; // eax
  unsigned int v31; // r10d
  unsigned int v32; // eax
  int v33; // eax
  unsigned __int64 v34; // r11
  char v35; // r11
  unsigned int v36; // eax
  unsigned int v37; // r9d
  unsigned int v38; // eax
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // r15
  _BYTE *v43; // r12
  _BYTE *v44; // rdi
  _BYTE *v45; // r9
  char v46; // dl
  __int64 v47; // rbp
  unsigned int v48; // r9d
  unsigned int *v49; // rdi
  int v50; // ebp
  unsigned __int64 v51; // r11
  char v52; // r15
  int v53; // r9d
  unsigned int v54; // r10d
  unsigned int v55; // eax
  int v56; // eax
  unsigned int v57; // edx
  unsigned __int64 v58; // rdx
  unsigned __int64 v59; // r15
  unsigned int v60; // r9d
  int v61; // ebx
  unsigned int *v63; // [rsp+20h] [rbp-68h]
  __int64 v64; // [rsp+28h] [rbp-60h]
  int *v65; // [rsp+28h] [rbp-60h]
  unsigned __int64 v66; // [rsp+30h] [rbp-58h]
  unsigned int *v67; // [rsp+38h] [rbp-50h]

  v4 = (unsigned int *)*a3;
  v5 = a3 + 1;
  v63 = (unsigned int *)*a3;
  v7 = (unsigned int *)*a2;
  v8 = a2 + 1;
  v67 = (unsigned int *)*a2;
  if ( *a2 == *a3 && *v8 == *v5 )
  {
    *(_OWORD *)a1 = *(_OWORD *)a4;
    return a1;
  }
  v10 = *v8;
  v11 = *v5;
  v12 = *(int **)a4;
  v13 = 32 * (v4 - v7) - *v8;
  v66 = *v8;
  *(_OWORD *)a1 = *(_OWORD *)a4;
  v14 = v13 + v11;
  if ( (__int64)(v13 + v11) >= 0 || (v15 = a1[1], v15 >= -(__int64)v14) )
  {
    a1[1] += v14;
    v16 = a1[1];
    v17 = 4 * (v16 >> 5);
  }
  else
  {
    LOBYTE(v16) = v15 + v14;
    a1[1] = v15 + v14;
    v17 = -4LL - 4 * (~(v15 + v14) >> 5);
  }
  *a1 += v17;
  v18 = *a1;
  v19 = v16 & 0x1F;
  v20 = v10;
  a1[1] = v19;
  v21 = *(_QWORD *)(a4 + 8);
  v22 = -1 << v20;
  v64 = v18;
  if ( v21 )
    v23 = 0xFFFFFFFF >> (32 - v21);
  else
    v23 = 0;
  if ( v11 )
    v24 = 0xFFFFFFFF >> (32 - v11);
  else
    v24 = 0;
  v25 = -1 << v19;
  v26 = (int *)((-(__int64)(v19 == 0) & 0xFFFFFFFFFFFFFFFCuLL) + v18);
  v65 = (int *)((-(__int64)(v19 == 0) & 0xFFFFFFFFFFFFFFFCuLL) + v64);
  if ( v67 == v63 )
  {
    v27 = v24 & v22;
    v28 = *v8;
    if ( v21 >= v66 )
      v29 = v21 - v28;
    else
      v29 = v28 - v21;
    v30 = *v67 & v27;
    v31 = v30 >> v29;
    v32 = v30 << v29;
    if ( v21 >= v66 )
      v31 = v32;
    if ( v12 != v65 )
    {
      *v12 = v31 | *v12 & v23;
      v12[1] = v12[1] & v25 | ((*v67 & v27) >> (v11 - *((_BYTE *)a1 + 8)));
      return a1;
    }
    v33 = v31 | *v12 & (v23 | (v19 != 0 ? v25 : 0));
LABEL_55:
    *v12 = v33;
    return a1;
  }
  v34 = *v8;
  if ( v12 == v26 )
  {
    if ( v21 >= v66 )
      v35 = v21 - v34;
    else
      v35 = v34 - v21;
    v36 = *v67 & v22;
    v37 = v36 >> v35;
    v38 = v36 << v35;
    if ( v21 >= v66 )
      v37 = v38;
    if ( v11 )
      v39 = *v12 & (v23 | (v19 != 0 ? v25 : 0)) | ((v24 & *v63) << (v19 - v11));
    else
      v39 = *v12 & (v23 | (v19 != 0 ? v25 : 0));
    v33 = v37 | v39;
    goto LABEL_55;
  }
  v40 = v34 & 7;
  v41 = v21 & 7;
  if ( v40 == v41 )
  {
    v42 = v11 & 7;
    v43 = (char *)v63 + ((v11 - v42) >> 3);
    v44 = (char *)v12 + ((v21 - v41) >> 3);
    v45 = (char *)v67 + ((v34 - v40) >> 3);
    if ( (v34 & 7) != 0 )
    {
      v46 = *v45++ & (-1 << v40) | *v44 & (255 >> (8 - v40));
      *v44++ = v46;
    }
    v47 = v43 - v45;
    memmove_0(v44, v45, v43 - v45);
    if ( (v11 & 7) != 0 )
      v44[v47] = v44[v47] & (-1 << v42) | *v43 & (255 >> (8 - v42));
    return a1;
  }
  v48 = *v67 & v22;
  v49 = v67 + 1;
  v50 = *v12 & v23;
  if ( v21 >= v66 )
  {
    v58 = v21 - v34;
    v59 = 32 - v58;
    *v12 = v50 | (v48 << v58);
    v60 = *v67 >> (32 - v58);
    ++v12;
    while ( v49 != v63 )
    {
      *v12++ = v60 | (*v49 << v58);
      v60 = *v49++ >> v59;
    }
    if ( v11 < v59 )
    {
      v61 = *v12 & v25;
      if ( !*v5 )
      {
        *v12 = v61 | v60;
        return a1;
      }
      v33 = v61 | v60 | ((v24 & *v49) << v58);
      goto LABEL_55;
    }
    *v12 = v60 | (*v49 << v58);
    if ( *v5 == v59 )
      return a1;
    v57 = ~v25 & (*v49 >> v59);
LABEL_52:
    v12[1] = v25 & v12[1] | v57;
    return a1;
  }
  v51 = v34 - v21;
  v52 = 32 - v51;
  v53 = v50 | (v48 >> v51);
  v54 = 0xFFFFFFFF >> v51;
  for ( *v12 = v53; v49 != v63; *v12 = v53 )
  {
    *v12++ = (*v49 << v52) | v53 & v54;
    v55 = *v49++;
    v53 = (v55 >> v51) | *v12 & ~v54;
  }
  if ( v11 )
  {
    v56 = (v24 & *v49) << v52;
    if ( v11 < v51 )
    {
      *v12 = v56 | *v12 & (v25 | v54);
      return a1;
    }
    *v12 = v56 | *v12 & v54;
    if ( v11 != v51 )
    {
      v57 = (v24 & *v49) >> v51;
      goto LABEL_52;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14000696c  push    rbx
0x14000696e  push    rbp
0x14000696f  push    rsi
0x140006970  push    rdi
0x140006971  push    r12
0x140006973  push    r13
0x140006975  push    r14
0x140006977  push    r15
0x140006979  sub     rsp, 48h
0x14000697d  mov     rax, [r8]
0x140006980  lea     r13, [r8+8]
0x140006984  mov     rbx, r9
0x140006987  mov     [rsp+88h+var_68], rax
0x14000698c  mov     r9, [rdx]
0x14000698f  lea     r11, [rdx+8]
0x140006993  mov     [rsp+88h+var_50], r9
0x140006998  mov     rsi, rcx
0x14000699b  cmp     r9, rax
0x14000699e  jnz     short loc_1400069B5
0x1400069a0  mov     rcx, [r13+0]
0x1400069a4  cmp     [r11], rcx
0x1400069a7  jnz     short loc_1400069B5
0x1400069a9  movaps  xmm0, xmmword ptr [rbx]
0x1400069ac  movdqu  xmmword ptr [rsi], xmm0
0x1400069b0  jmp     loc_140006D97
0x1400069b5  mov     rdx, [r11]
0x1400069b8  sub     rax, r9
0x1400069bb  mov     r14, [r13+0]
0x1400069bf  movaps  xmm0, xmmword ptr [rbx]
0x1400069c2  mov     r8, [rbx]
0x1400069c5  sar     rax, 2
0x1400069c9  shl     rax, 5
0x1400069cd  sub     rax, rdx
0x1400069d0  mov     [rsp+88h+var_58], rdx
0x1400069d5  movdqu  xmmword ptr [rsi], xmm0
0x1400069d9  lea     rcx, [rax+r14]
0x1400069dd  test    rcx, rcx
0x1400069e0  jns     short loc_140006A13
0x1400069e2  mov     r9, [rsi+8]
0x1400069e6  mov     rax, rcx
0x1400069e9  neg     rax
0x1400069ec  cmp     r9, rax
0x1400069ef  jnb     short loc_140006A13
0x1400069f1  lea     rdi, [r9+rcx]
0x1400069f5  mov     rax, 0FFFFFFFFFFFFFFFCh
0x1400069fc  mov     rcx, rdi
0x1400069ff  mov     [rsi+8], rdi
0x140006a03  not     rcx
0x140006a06  shr     rcx, 5
0x140006a0a  shl     rcx, 2
0x140006a0e  sub     rax, rcx
0x140006a11  jmp     short loc_140006A26
0x140006a13  add     [rsi+8], rcx
0x140006a17  mov     rdi, [rsi+8]
0x140006a1b  mov     rax, rdi
0x140006a1e  shr     rax, 5
0x140006a22  shl     rax, 2
0x140006a26  add     [rsi], rax
0x140006a29  or      r10d, 0FFFFFFFFh
0x140006a2d  mov     rax, [rsi]
0x140006a30  and     edi, 1Fh
0x140006a33  mov     rcx, rdx
0x140006a36  mov     [rsi+8], rdi
0x140006a3a  mov     rdx, [rbx+8]
0x140006a3e  mov     r9d, r10d
0x140006a41  shl     r9d, cl
0x140006a44  mov     r15d, 20h ; ' '
0x140006a4a  mov     [rsp+88h+var_60], rax
0x140006a4f  test    rdx, rdx
0x140006a52  jnz     short loc_140006A58
0x140006a54  xor     ebp, ebp
0x140006a56  jmp     short loc_140006A62
0x140006a58  mov     ecx, r15d
0x140006a5b  mov     ebp, r10d
0x140006a5e  sub     cl, dl
0x140006a60  shr     ebp, cl
0x140006a62  test    r14, r14
0x140006a65  jnz     short loc_140006A6C
0x140006a67  xor     r12d, r12d
0x140006a6a  jmp     short loc_140006A78
0x140006a6c  mov     ecx, r15d
0x140006a6f  mov     r12d, r10d
0x140006a72  sub     cl, r14b
0x140006a75  shr     r12d, cl
0x140006a78  mov     rcx, rdi
0x140006a7b  mov     ebx, r10d
0x140006a7e  shl     ebx, cl
0x140006a80  mov     rax, rdi
0x140006a83  neg     rax
0x140006a86  mov     rax, [rsp+88h+var_60]
0x140006a8b  sbb     rcx, rcx
0x140006a8e  not     rcx
0x140006a91  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140006a95  add     rax, rcx
0x140006a98  mov     rcx, [rsp+88h+var_50]
0x140006a9d  mov     [rsp+88h+var_60], rax
0x140006aa2  cmp     rcx, [rsp+88h+var_68]
0x140006aa7  jnz     short loc_140006B21
0x140006aa9  mov     r15, [rsp+88h+var_58]
0x140006aae  and     r9d, r12d
0x140006ab1  mov     rcx, [r11]
0x140006ab4  cmp     rdx, r15
0x140006ab7  jnb     short loc_140006ABE
0x140006ab9  sub     rcx, rdx
0x140006abc  jmp     short loc_140006AC7
0x140006abe  mov     rax, rdx
0x140006ac1  sub     rax, rcx
0x140006ac4  mov     rcx, rax
0x140006ac7  mov     r11, [rsp+88h+var_50]
0x140006acc  mov     r10d, r9d
0x140006acf  and     r10d, [r11]
0x140006ad2  mov     eax, r10d
0x140006ad5  shr     r10d, cl
0x140006ad8  shl     eax, cl
0x140006ada  cmp     rdx, r15
0x140006add  cmovnb  r10d, eax
0x140006ae1  cmp     r8, [rsp+88h+var_60]
0x140006ae6  jnz     short loc_140006AFC
0x140006ae8  neg     rdi
0x140006aeb  sbb     eax, eax
0x140006aed  and     eax, ebx
0x140006aef  or      eax, ebp
0x140006af1  and     eax, [r8]
0x140006af4  or      eax, r10d
0x140006af7  jmp     loc_140006D8C
0x140006afc  and     ebp, [r8]
0x140006aff  mov     cl, r14b
0x140006b02  or      ebp, r10d
0x140006b05  mov     [r8], ebp
0x140006b08  and     r9d, [r11]
0x140006b0b  sub     cl, [rsi+8]
0x140006b0e  and     ebx, [r8+4]
0x140006b12  shr     r9d, cl
0x140006b15  or      r9d, ebx
0x140006b18  mov     [r8+4], r9d
0x140006b1c  jmp     loc_140006D97
0x140006b21  mov     r11, [r11]
0x140006b24  cmp     r8, rax
0x140006b27  jnz     short loc_140006B8A
0x140006b29  mov     r10, [rsp+88h+var_58]
0x140006b2e  cmp     rdx, r10
0x140006b31  jnb     short loc_140006B38
0x140006b33  sub     r11, rdx
0x140006b36  jmp     short loc_140006B41
0x140006b38  mov     rax, rdx
0x140006b3b  sub     rax, r11
0x140006b3e  mov     r11, rax
0x140006b41  and     r9d, [rcx]
0x140006b44  mov     rcx, r11
0x140006b47  mov     eax, r9d
0x140006b4a  shr     r9d, cl
0x140006b4d  shl     eax, cl
0x140006b4f  cmp     rdx, r10
0x140006b52  cmovnb  r9d, eax
0x140006b56  mov     rax, rdi
0x140006b59  neg     rax
0x140006b5c  sbb     edx, edx
0x140006b5e  and     edx, ebx
0x140006b60  or      edx, ebp
0x140006b62  and     edx, [r8]
0x140006b65  test    r14, r14
0x140006b68  jz      short loc_140006B80
0x140006b6a  mov     rax, [rsp+88h+var_68]
0x140006b6f  mov     cl, dil
0x140006b72  sub     cl, r14b
0x140006b75  mov     eax, [rax]
0x140006b77  and     eax, r12d
0x140006b7a  shl     eax, cl
0x140006b7c  or      eax, edx
0x140006b7e  jmp     short loc_140006B82
0x140006b80  mov     eax, edx
0x140006b82  or      eax, r9d
0x140006b85  jmp     loc_140006D8C
0x140006b8a  mov     rax, r11
0x140006b8d  mov     rdi, rdx
0x140006b90  and     eax, 7
0x140006b93  and     edi, 7
0x140006b96  cmp     rax, rdi
0x140006b99  jnz     loc_140006C3C
0x140006b9f  mov     r12, [rsp+88h+var_68]
0x140006ba4  mov     r15, r14
0x140006ba7  sub     rdx, rdi
0x140006baa  and     r15d, 7
0x140006bae  sub     r14, r15
0x140006bb1  shr     rdx, 3
0x140006bb5  shr     r14, 3
0x140006bb9  sub     r11, rax
0x140006bbc  shr     r11, 3
0x140006bc0  add     r12, r14
0x140006bc3  or      r14d, 0FFFFFFFFh
0x140006bc7  mov     ebx, 0FFh
0x140006bcc  lea     rdi, [rdx+r8]
0x140006bd0  mov     r13d, 8
0x140006bd6  lea     r9, [r11+rcx]
0x140006bda  test    rax, rax
0x140006bdd  jz      short loc_140006BFE
0x140006bdf  mov     ecx, r13d
0x140006be2  mov     edx, ebx
0x140006be4  sub     cl, al
0x140006be6  sar     edx, cl
0x140006be8  mov     ecx, eax
0x140006bea  and     dl, [rdi]
0x140006bec  mov     eax, r14d
0x140006bef  shl     al, cl
0x140006bf1  and     al, [r9]
0x140006bf4  or      dl, al
0x140006bf6  inc     r9
0x140006bf9  mov     [rdi], dl
0x140006bfb  inc     rdi
0x140006bfe  mov     rbp, r12
0x140006c01  mov     rdx, r9; Src
0x140006c04  sub     rbp, r9
0x140006c07  mov     rcx, rdi; void *
0x140006c0a  mov     r8, rbp; Size
0x140006c0d  call    memmove_0
0x140006c12  test    r15, r15
0x140006c15  jz      loc_140006D97
0x140006c1b  mov     ecx, r13d
0x140006c1e  sub     cl, r15b
0x140006c21  sar     ebx, cl
0x140006c23  mov     rcx, r15
0x140006c26  and     bl, [r12]
0x140006c2a  shl     r14b, cl
0x140006c2d  and     r14b, [rdi+rbp]
0x140006c31  or      bl, r14b
0x140006c34  mov     [rdi+rbp], bl
0x140006c37  jmp     loc_140006D97
0x140006c3c  and     r9d, [rcx]
0x140006c3f  lea     rdi, [rcx+4]
0x140006c43  and     ebp, [r8]
0x140006c46  cmp     rdx, [rsp+88h+var_58]
0x140006c4b  jnb     loc_140006CF2
0x140006c51  sub     r11, rdx
0x140006c54  mov     rcx, r11
0x140006c57  sub     r15, r11
0x140006c5a  shr     r9d, cl
0x140006c5d  or      r9d, ebp
0x140006c60  shr     r10d, cl
0x140006c63  mov     rbp, [rsp+88h+var_68]
0x140006c68  mov     [r8], r9d
0x140006c6b  cmp     rdi, rbp
0x140006c6e  jz      short loc_140006CA8
0x140006c70  mov     r13d, r10d
0x140006c73  not     r13d
0x140006c76  mov     eax, [rdi]
0x140006c78  mov     rcx, r15
0x140006c7b  shl     eax, cl
0x140006c7d  mov     edx, r10d
0x140006c80  and     edx, r9d
0x140006c83  mov     rcx, r11
0x140006c86  or      edx, eax
0x140006c88  mov     r9d, r13d
0x140006c8b  mov     [r8], edx
0x140006c8e  add     r8, 4
0x140006c92  mov     eax, [rdi]
0x140006c94  add     rdi, 4
0x140006c98  shr     eax, cl
0x140006c9a  and     r9d, [r8]
0x140006c9d  or      r9d, eax
0x140006ca0  mov     [r8], r9d
0x140006ca3  cmp     rdi, rbp
0x140006ca6  jnz     short loc_140006C76
0x140006ca8  test    r14, r14
0x140006cab  jz      loc_140006D97
0x140006cb1  mov     eax, [rdi]
0x140006cb3  mov     rcx, r15
0x140006cb6  and     eax, r12d
0x140006cb9  shl     eax, cl
0x140006cbb  cmp     r14, r11
0x140006cbe  jb      short loc_140006CE1
0x140006cc0  and     r10d, [r8]
0x140006cc3  or      r10d, eax
0x140006cc6  mov     [r8], r10d
0x140006cc9  cmp     r14, r11
0x140006ccc  jz      loc_140006D97
0x140006cd2  mov     edx, [rdi]
0x140006cd4  mov     rcx, r11
0x140006cd7  and     edx, r12d
0x140006cda  shr     edx, cl
0x140006cdc  jmp     loc_140006D65
0x140006ce1  or      r10d, ebx
0x140006ce4  and     r10d, [r8]
0x140006ce7  or      r10d, eax
0x140006cea  mov     [r8], r10d
0x140006ced  jmp     loc_140006D97
0x140006cf2  mov     r10, [rsp+88h+var_68]
0x140006cf7  sub     rdx, r11
0x140006cfa  mov     r11, [rsp+88h+var_50]
0x140006cff  mov     rcx, rdx
0x140006d02  shl     r9d, cl
0x140006d05  sub     r15, rdx
0x140006d08  or      r9d, ebp
0x140006d0b  mov     rcx, r15
0x140006d0e  mov     [r8], r9d
0x140006d11  mov     r9d, [r11]
0x140006d14  shr     r9d, cl
0x140006d17  add     r8, 4
0x140006d1b  jmp     short loc_140006D3B
0x140006d1d  mov     eax, [rdi]
0x140006d1f  mov     rcx, rdx
  ... truncated ...
```
