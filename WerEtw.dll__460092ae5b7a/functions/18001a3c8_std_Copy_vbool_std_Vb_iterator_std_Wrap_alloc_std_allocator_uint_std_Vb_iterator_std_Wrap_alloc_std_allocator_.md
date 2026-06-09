# std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>>(std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<uint>>>)

- ea: `0x18001a3c8`
- end: `0x18001a820`
- name: `??$_Copy_vbool@V?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@V12@@std@@YA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@0@V10@00@Z`
- size: `1112`
- prototype: `_OWORD *__fastcall(_OWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fdb0`

## callees

- `0x1800027bd`
- `0x18001a3c8`

## pseudocode

```c
_OWORD *__fastcall std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>(
        _OWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  unsigned __int64 *v5; // r13
  unsigned int *v6; // r9
  unsigned __int64 *v7; // r11
  unsigned int *v9; // rcx
  unsigned __int64 v10; // r10
  __int64 *v11; // rdx
  unsigned __int64 v12; // rsi
  int *v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rdi
  unsigned __int64 v20; // rdx
  int v21; // r9d
  unsigned int v22; // r12d
  unsigned int v23; // r15d
  int v24; // ebx
  int *v25; // rax
  int v26; // r9d
  unsigned __int64 v27; // rcx
  char v28; // cl
  unsigned int v29; // eax
  unsigned int v30; // r10d
  unsigned int v31; // eax
  int v32; // eax
  unsigned __int64 v33; // r11
  char v34; // r11
  unsigned int v35; // eax
  unsigned int v36; // r9d
  unsigned int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // r15
  _BYTE *v42; // r12
  _BYTE *v43; // rdi
  _BYTE *v44; // r9
  char v45; // dl
  __int64 v46; // rsi
  unsigned int v47; // r9d
  unsigned int *v48; // rdi
  int v49; // r12d
  unsigned __int64 v50; // r11
  char v51; // bp
  int v52; // r9d
  unsigned int v53; // r10d
  unsigned int v54; // eax
  int v55; // eax
  unsigned int v56; // edx
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // rbp
  unsigned int v59; // r9d
  int v60; // ebx
  unsigned int *v62; // [rsp+20h] [rbp-48h]
  __int64 v63; // [rsp+28h] [rbp-40h]
  int *v64; // [rsp+28h] [rbp-40h]
  unsigned int *v65; // [rsp+78h] [rbp+10h]
  unsigned __int64 v66; // [rsp+80h] [rbp+18h]

  v5 = a3 + 1;
  v6 = (unsigned int *)*a3;
  v7 = a2 + 1;
  v65 = (unsigned int *)*a3;
  v9 = (unsigned int *)*a2;
  v62 = (unsigned int *)*a2;
  if ( *a2 == *a3 && *v7 == *v5 )
  {
    *a1 = *(_OWORD *)a4;
    return a1;
  }
  v10 = *v7;
  v11 = (__int64 *)a1 + 1;
  v12 = *v5;
  v13 = *(int **)a4;
  v14 = 32 * (v6 - v9) - *v7;
  v66 = *v7;
  *a1 = *(_OWORD *)a4;
  v15 = v14 + v12;
  if ( (__int64)(v14 + v12) >= 0 || (v16 = *v11, *v11 >= (unsigned __int64)-(__int64)v15) )
  {
    *v11 += v15;
    v17 = *v11;
    v18 = 4 * ((unsigned __int64)*v11 >> 5);
  }
  else
  {
    LOBYTE(v17) = v16 + v15;
    *v11 = v16 + v15;
    v18 = -4LL - 4 * (~(v16 + v15) >> 5);
  }
  *(_QWORD *)a1 += v18;
  v19 = v17 & 0x1F;
  v63 = *(_QWORD *)a1;
  *v11 = v19;
  v20 = *(_QWORD *)(a4 + 8);
  v21 = -1 << v10;
  if ( v20 )
    v22 = 0xFFFFFFFF >> (32 - v20);
  else
    v22 = 0;
  if ( v12 )
    v23 = 0xFFFFFFFF >> (32 - v12);
  else
    v23 = 0;
  v24 = -1 << v19;
  v25 = (int *)((-(__int64)(v19 == 0) & 0xFFFFFFFFFFFFFFFCuLL) + v63);
  v64 = v25;
  if ( v62 == v65 )
  {
    v26 = v23 & v21;
    v27 = *v7;
    if ( v20 >= v66 )
      v28 = v20 - v27;
    else
      v28 = v27 - v20;
    v29 = *v62 & v26;
    v30 = v29 >> v28;
    v31 = v29 << v28;
    if ( v20 >= v66 )
      v30 = v31;
    if ( v13 != v64 )
    {
      *v13 = v30 | v22 & *v13;
      v13[1] = v13[1] & v24 | ((*v62 & v26) >> (v12 - v19));
      return a1;
    }
    v32 = v30 | *v13 & (v22 | (v19 != 0 ? v24 : 0));
LABEL_55:
    *v13 = v32;
    return a1;
  }
  v33 = *v7;
  if ( v13 == v25 )
  {
    if ( v20 >= v66 )
      v34 = v20 - v33;
    else
      v34 = v33 - v20;
    v35 = *v62 & v21;
    v36 = v35 >> v34;
    v37 = v35 << v34;
    if ( v20 >= v66 )
      v36 = v37;
    if ( v12 )
      v38 = *v13 & (v22 | (v19 != 0 ? v24 : 0)) | ((v23 & *v65) << (v19 - v12));
    else
      v38 = *v13 & (v22 | (v19 != 0 ? v24 : 0));
    v32 = v36 | v38;
    goto LABEL_55;
  }
  v39 = v33 & 7;
  v40 = v20 & 7;
  if ( v39 == v40 )
  {
    v41 = v12 & 7;
    v42 = (char *)v65 + ((v12 - v41) >> 3);
    v43 = (char *)v13 + ((v20 - v40) >> 3);
    v44 = (char *)v62 + ((v33 - v39) >> 3);
    if ( (v33 & 7) != 0 )
    {
      v45 = *v44++ & (-1 << v39) | *v43 & (255 >> (8 - v39));
      *v43++ = v45;
    }
    v46 = v42 - v44;
    memmove_0(v43, v44, v42 - v44);
    if ( v41 )
      v43[v46] = v43[v46] & (-1 << v41) | *v42 & (255 >> (8 - v41));
    return a1;
  }
  v47 = *v62 & v21;
  v48 = v62 + 1;
  v49 = *v13 & v22;
  if ( v20 >= v66 )
  {
    v57 = v20 - v33;
    v58 = 32 - v57;
    *v13 = v49 | (v47 << v57);
    v59 = *v62 >> (32 - v57);
    ++v13;
    while ( v48 != v65 )
    {
      *v13++ = v59 | (*v48 << v57);
      v59 = *v48++ >> v58;
    }
    if ( v12 < v58 )
    {
      v60 = *v13 & v24;
      if ( !*v5 )
      {
        *v13 = v60 | v59;
        return a1;
      }
      v32 = v60 | v59 | ((v23 & *v48) << v57);
      goto LABEL_55;
    }
    *v13 = v59 | (*v48 << v57);
    if ( *v5 == v58 )
      return a1;
    v56 = ~v24 & (*v48 >> v58);
LABEL_52:
    v13[1] = v24 & v13[1] | v56;
    return a1;
  }
  v50 = v33 - v20;
  v51 = 32 - v50;
  v52 = v49 | (v47 >> v50);
  v53 = 0xFFFFFFFF >> v50;
  for ( *v13 = v52; v48 != v65; *v13 = v52 )
  {
    *v13++ = (*v48 << v51) | v52 & v53;
    v54 = *v48++;
    v52 = (v54 >> v50) | ~v53 & *v13;
  }
  if ( v12 )
  {
    v55 = (v23 & *v48) << v51;
    if ( v12 < v50 )
    {
      *v13 = v55 | *v13 & (v24 | v53);
      return a1;
    }
    *v13 = v55 | *v13 & v53;
    if ( v12 != v50 )
    {
      v56 = (v23 & *v48) >> v50;
      goto LABEL_52;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001a3c8  mov     [rsp+arg_0], rbx
0x18001a3cd  push    rbp
0x18001a3ce  push    rsi
0x18001a3cf  push    rdi
0x18001a3d0  push    r12
0x18001a3d2  push    r13
0x18001a3d4  push    r14
0x18001a3d6  push    r15
0x18001a3d8  sub     rsp, 30h
0x18001a3dc  mov     rbx, r9
0x18001a3df  lea     r13, [r8+8]
0x18001a3e3  mov     r9, [r8]
0x18001a3e6  lea     r11, [rdx+8]
0x18001a3ea  mov     r14, rcx
0x18001a3ed  mov     [rsp+68h+arg_8], r9
0x18001a3f2  mov     rcx, [rdx]
0x18001a3f5  mov     [rsp+68h+var_48], rcx
0x18001a3fa  cmp     rcx, r9
0x18001a3fd  jnz     short loc_18001A415
0x18001a3ff  mov     rax, [r13+0]
0x18001a403  cmp     [r11], rax
0x18001a406  jnz     short loc_18001A415
0x18001a408  movaps  xmm0, xmmword ptr [rbx]
0x18001a40b  movdqu  xmmword ptr [r14], xmm0
0x18001a410  jmp     loc_18001A808
0x18001a415  mov     r10, [r11]
0x18001a418  lea     rdx, [r14+8]
0x18001a41c  mov     rsi, [r13+0]
0x18001a420  mov     rax, r9
0x18001a423  movaps  xmm0, xmmword ptr [rbx]
0x18001a426  sub     rax, rcx
0x18001a429  mov     r8, [rbx]
0x18001a42c  sar     rax, 2
0x18001a430  shl     rax, 5
0x18001a434  sub     rax, r10
0x18001a437  mov     [rsp+68h+arg_10], r10
0x18001a43f  movdqu  xmmword ptr [r14], xmm0
0x18001a444  lea     rcx, [rax+rsi]
0x18001a448  test    rcx, rcx
0x18001a44b  jns     short loc_18001A47C
0x18001a44d  mov     r9, [rdx]
0x18001a450  mov     rax, rcx
0x18001a453  neg     rax
0x18001a456  cmp     r9, rax
0x18001a459  jnb     short loc_18001A47C
0x18001a45b  lea     rdi, [r9+rcx]
0x18001a45f  mov     rax, 0FFFFFFFFFFFFFFFCh
0x18001a466  mov     rcx, rdi
0x18001a469  mov     [rdx], rdi
0x18001a46c  not     rcx
0x18001a46f  shr     rcx, 5
0x18001a473  shl     rcx, 2
0x18001a477  sub     rax, rcx
0x18001a47a  jmp     short loc_18001A48D
0x18001a47c  add     [rdx], rcx
0x18001a47f  mov     rdi, [rdx]
0x18001a482  mov     rax, rdi
0x18001a485  shr     rax, 5
0x18001a489  shl     rax, 2
0x18001a48d  add     [r14], rax
0x18001a490  mov     rcx, r10
0x18001a493  mov     rax, [r14]
0x18001a496  or      r10d, 0FFFFFFFFh
0x18001a49a  and     edi, 1Fh
0x18001a49d  mov     [rsp+68h+var_40], rax
0x18001a4a2  mov     r9d, r10d
0x18001a4a5  mov     [rdx], rdi
0x18001a4a8  mov     rdx, [rbx+8]
0x18001a4ac  mov     ebp, 20h ; ' '
0x18001a4b1  shl     r9d, cl
0x18001a4b4  test    rdx, rdx
0x18001a4b7  jnz     short loc_18001A4BE
0x18001a4b9  xor     r12d, r12d
0x18001a4bc  jmp     short loc_18001A4C8
0x18001a4be  mov     ecx, ebp
0x18001a4c0  mov     r12d, r10d
0x18001a4c3  sub     cl, dl
0x18001a4c5  shr     r12d, cl
0x18001a4c8  test    rsi, rsi
0x18001a4cb  jnz     short loc_18001A4D2
0x18001a4cd  xor     r15d, r15d
0x18001a4d0  jmp     short loc_18001A4DD
0x18001a4d2  mov     ecx, ebp
0x18001a4d4  mov     r15d, r10d
0x18001a4d7  sub     cl, sil
0x18001a4da  shr     r15d, cl
0x18001a4dd  mov     rcx, rdi
0x18001a4e0  mov     ebx, r10d
0x18001a4e3  shl     ebx, cl
0x18001a4e5  mov     rax, rdi
0x18001a4e8  neg     rax
0x18001a4eb  mov     rax, [rsp+68h+var_40]
0x18001a4f0  sbb     rcx, rcx
0x18001a4f3  not     rcx
0x18001a4f6  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18001a4fa  add     rax, rcx
0x18001a4fd  mov     rcx, [rsp+68h+var_48]
0x18001a502  mov     [rsp+68h+var_40], rax
0x18001a507  cmp     rcx, [rsp+68h+arg_8]
0x18001a50c  jnz     short loc_18001A58D
0x18001a50e  mov     rbp, [rsp+68h+arg_10]
0x18001a516  and     r9d, r15d
0x18001a519  mov     rcx, [r11]
0x18001a51c  cmp     rdx, rbp
0x18001a51f  jnb     short loc_18001A526
0x18001a521  sub     rcx, rdx
0x18001a524  jmp     short loc_18001A52F
0x18001a526  mov     rax, rdx
0x18001a529  sub     rax, rcx
0x18001a52c  mov     rcx, rax
0x18001a52f  mov     r11, [rsp+68h+var_48]
0x18001a534  mov     r10d, r9d
0x18001a537  and     r10d, [r11]
0x18001a53a  mov     eax, r10d
0x18001a53d  shr     r10d, cl
0x18001a540  shl     eax, cl
0x18001a542  cmp     rdx, rbp
0x18001a545  cmovnb  r10d, eax
0x18001a549  cmp     r8, [rsp+68h+var_40]
0x18001a54e  jnz     short loc_18001A565
0x18001a550  neg     rdi
0x18001a553  sbb     eax, eax
0x18001a555  and     eax, ebx
0x18001a557  or      eax, r12d
0x18001a55a  and     eax, [r8]
0x18001a55d  or      eax, r10d
0x18001a560  jmp     loc_18001A7FD
0x18001a565  mov     eax, [r8]
0x18001a568  mov     cl, sil
0x18001a56b  and     eax, r12d
0x18001a56e  sub     cl, dil
0x18001a571  or      eax, r10d
0x18001a574  mov     [r8], eax
0x18001a577  and     r9d, [r11]
0x18001a57a  and     ebx, [r8+4]
0x18001a57e  shr     r9d, cl
0x18001a581  or      r9d, ebx
0x18001a584  mov     [r8+4], r9d
0x18001a588  jmp     loc_18001A808
0x18001a58d  mov     r11, [r11]
0x18001a590  cmp     r8, rax
0x18001a593  jnz     short loc_18001A5FA
0x18001a595  mov     r10, [rsp+68h+arg_10]
0x18001a59d  cmp     rdx, r10
0x18001a5a0  jnb     short loc_18001A5A7
0x18001a5a2  sub     r11, rdx
0x18001a5a5  jmp     short loc_18001A5B0
0x18001a5a7  mov     rax, rdx
0x18001a5aa  sub     rax, r11
0x18001a5ad  mov     r11, rax
0x18001a5b0  and     r9d, [rcx]
0x18001a5b3  mov     rcx, r11
0x18001a5b6  mov     eax, r9d
0x18001a5b9  shr     r9d, cl
0x18001a5bc  shl     eax, cl
0x18001a5be  cmp     rdx, r10
0x18001a5c1  cmovnb  r9d, eax
0x18001a5c5  mov     rax, rdi
0x18001a5c8  neg     rax
0x18001a5cb  sbb     edx, edx
0x18001a5cd  and     edx, ebx
0x18001a5cf  or      edx, r12d
0x18001a5d2  and     edx, [r8]
0x18001a5d5  test    rsi, rsi
0x18001a5d8  jz      short loc_18001A5F0
0x18001a5da  mov     rax, [rsp+68h+arg_8]
0x18001a5df  mov     cl, dil
0x18001a5e2  sub     cl, sil
0x18001a5e5  mov     eax, [rax]
0x18001a5e7  and     eax, r15d
0x18001a5ea  shl     eax, cl
0x18001a5ec  or      eax, edx
0x18001a5ee  jmp     short loc_18001A5F2
0x18001a5f0  mov     eax, edx
0x18001a5f2  or      eax, r9d
0x18001a5f5  jmp     loc_18001A7FD
0x18001a5fa  mov     rax, r11
0x18001a5fd  mov     rdi, rdx
0x18001a600  and     eax, 7
0x18001a603  and     edi, 7
0x18001a606  cmp     rax, rdi
0x18001a609  jnz     loc_18001A6AA
0x18001a60f  mov     r12, [rsp+68h+arg_8]
0x18001a614  mov     r15, rsi
0x18001a617  sub     rdx, rdi
0x18001a61a  and     r15d, 7
0x18001a61e  sub     rsi, r15
0x18001a621  shr     rdx, 3
0x18001a625  sub     r11, rax
0x18001a628  shr     rsi, 3
0x18001a62c  shr     r11, 3
0x18001a630  add     r12, rsi
0x18001a633  or      ebp, 0FFFFFFFFh
0x18001a636  mov     ebx, 0FFh
0x18001a63b  lea     rdi, [rdx+r8]
0x18001a63f  mov     r13d, 8
0x18001a645  lea     r9, [r11+rcx]
0x18001a649  test    rax, rax
0x18001a64c  jz      short loc_18001A66C
0x18001a64e  mov     ecx, r13d
0x18001a651  mov     edx, ebx
0x18001a653  sub     cl, al
0x18001a655  sar     edx, cl
0x18001a657  mov     ecx, eax
0x18001a659  and     dl, [rdi]
0x18001a65b  mov     eax, ebp
0x18001a65d  shl     al, cl
0x18001a65f  and     al, [r9]
0x18001a662  or      dl, al
0x18001a664  inc     r9
0x18001a667  mov     [rdi], dl
0x18001a669  inc     rdi
0x18001a66c  mov     rsi, r12
0x18001a66f  mov     rdx, r9; Src
0x18001a672  sub     rsi, r9
0x18001a675  mov     rcx, rdi; void *
0x18001a678  mov     r8, rsi; Size
0x18001a67b  call    memmove_0
0x18001a680  test    r15, r15
0x18001a683  jz      loc_18001A808
0x18001a689  mov     ecx, r13d
0x18001a68c  sub     cl, r15b
0x18001a68f  sar     ebx, cl
0x18001a691  mov     rcx, r15
0x18001a694  and     bl, [r12]
0x18001a698  shl     bpl, cl
0x18001a69b  and     bpl, [rdi+rsi]
0x18001a69f  or      bl, bpl
0x18001a6a2  mov     [rdi+rsi], bl
0x18001a6a5  jmp     loc_18001A808
0x18001a6aa  and     r9d, [rcx]
0x18001a6ad  lea     rdi, [rcx+4]
0x18001a6b1  and     r12d, [r8]
0x18001a6b4  cmp     rdx, [rsp+68h+arg_10]
0x18001a6bc  jnb     loc_18001A763
0x18001a6c2  sub     r11, rdx
0x18001a6c5  mov     rcx, r11
0x18001a6c8  sub     rbp, r11
0x18001a6cb  shr     r9d, cl
0x18001a6ce  or      r9d, r12d
0x18001a6d1  shr     r10d, cl
0x18001a6d4  mov     r12, [rsp+68h+arg_8]
0x18001a6d9  mov     [r8], r9d
0x18001a6dc  cmp     rdi, r12
0x18001a6df  jz      short loc_18001A719
0x18001a6e1  mov     r13d, r10d
0x18001a6e4  not     r13d
0x18001a6e7  mov     eax, [rdi]
0x18001a6e9  mov     rcx, rbp
0x18001a6ec  shl     eax, cl
0x18001a6ee  mov     edx, r10d
0x18001a6f1  and     edx, r9d
0x18001a6f4  mov     rcx, r11
0x18001a6f7  or      edx, eax
0x18001a6f9  mov     [r8], edx
0x18001a6fc  add     r8, 4
0x18001a700  mov     eax, [rdi]
0x18001a702  add     rdi, 4
0x18001a706  shr     eax, cl
0x18001a708  mov     r9d, [r8]
0x18001a70b  and     r9d, r13d
0x18001a70e  or      r9d, eax
0x18001a711  mov     [r8], r9d
0x18001a714  cmp     rdi, r12
0x18001a717  jnz     short loc_18001A6E7
0x18001a719  test    rsi, rsi
0x18001a71c  jz      loc_18001A808
0x18001a722  mov     eax, [rdi]
0x18001a724  mov     rcx, rbp
0x18001a727  and     eax, r15d
0x18001a72a  shl     eax, cl
0x18001a72c  cmp     rsi, r11
0x18001a72f  jb      short loc_18001A752
0x18001a731  and     r10d, [r8]
0x18001a734  or      r10d, eax
0x18001a737  mov     [r8], r10d
0x18001a73a  cmp     rsi, r11
0x18001a73d  jz      loc_18001A808
0x18001a743  mov     edx, [rdi]
0x18001a745  mov     rcx, r11
0x18001a748  and     edx, r15d
0x18001a74b  shr     edx, cl
0x18001a74d  jmp     loc_18001A7D6
0x18001a752  or      r10d, ebx
0x18001a755  and     r10d, [r8]
0x18001a758  or      r10d, eax
0x18001a75b  mov     [r8], r10d
0x18001a75e  jmp     loc_18001A808
0x18001a763  mov     r10, [rsp+68h+arg_8]
0x18001a768  sub     rdx, r11
0x18001a76b  mov     r11, [rsp+68h+var_48]
0x18001a770  mov     rcx, rdx
0x18001a773  shl     r9d, cl
0x18001a776  sub     rbp, rdx
0x18001a779  or      r9d, r12d
0x18001a77c  mov     rcx, rbp
0x18001a77f  mov     [r8], r9d
0x18001a782  mov     r9d, [r11]
0x18001a785  shr     r9d, cl
0x18001a788  add     r8, 4
  ... truncated ...
```
