# LibRaw::xtrans_decode_block(fuji_compressed_block *,fuji_compressed_params const *,int)

- ea: `0x180014da0`
- end: `0x180015832`
- name: `?xtrans_decode_block@LibRaw@@IEAAXPEAUfuji_compressed_block@@PEBUfuji_compressed_params@@H@Z`
- size: `2706`
- prototype: `void __fastcall(LibRaw *this, struct fuji_compressed_block *, const struct fuji_compressed_params *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013a50`

## callees

- `0x1800090f0`
- `0x180013290`
- `0x180013440`
- `0x180013770`
- `0x180013e50`
- `0x180014da0`

## pseudocode

```c
void __fastcall LibRaw::xtrans_decode_block(
        LibRaw *this,
        struct fuji_compressed_block *a2,
        const struct fuji_compressed_params *a3)
{
  __int64 v3; // r14
  _QWORD *v4; // r13
  _DWORD *v5; // rdi
  int v6; // r12d
  int v7; // eax
  int v8; // ebp
  int v9; // r15d
  __int64 v11; // r8
  int v12; // r12d
  _DWORD *v13; // r13
  int v14; // eax
  _QWORD *v15; // rdi
  unsigned int v16; // esi
  _QWORD *v17; // rdi
  unsigned int v18; // r13d
  int v19; // r12d
  int v20; // ecx
  _QWORD *v21; // rax
  _DWORD *v22; // rax
  int v23; // ecx
  __int64 *v24; // rdi
  int v25; // r13d
  unsigned int v26; // r12d
  _DWORD *v27; // rsi
  int v28; // r12d
  unsigned int v29; // r13d
  int v30; // ecx
  _QWORD *v31; // rax
  int v32; // r11d
  _QWORD *v33; // r13
  int v34; // eax
  _QWORD *v35; // rdi
  unsigned int v36; // r12d
  int v37; // ebp
  int v38; // ebp
  __int64 v39; // rdx
  int v40; // ebp
  int v41; // eax
  __int64 v42; // rcx
  int v43; // ebp
  __int64 v44; // rcx
  char *v45; // rdi
  int v46; // eax
  int v47; // ebp
  __int64 v48; // rdx
  int v49; // ebp
  int v50; // [rsp+30h] [rbp-68h]
  unsigned int v51; // [rsp+38h] [rbp-60h]
  int v52; // [rsp+40h] [rbp-58h]
  int v53; // [rsp+40h] [rbp-58h]
  _QWORD *v54; // [rsp+48h] [rbp-50h]
  _DWORD *v55; // [rsp+48h] [rbp-50h]
  _QWORD *v56; // [rsp+48h] [rbp-50h]
  int v58; // [rsp+A8h] [rbp+10h]
  int v59; // [rsp+A8h] [rbp+10h]
  int v60; // [rsp+A8h] [rbp+10h]
  int v61; // [rsp+A8h] [rbp+10h]
  int v62; // [rsp+A8h] [rbp+10h]
  int v63; // [rsp+A8h] [rbp+10h]
  int v64; // [rsp+B0h] [rbp+18h]

  v3 = *((unsigned __int16 *)a3 + 74);
  v4 = (_QWORD *)((char *)a2 + 2760);
  v5 = (_DWORD *)((char *)a2 + 2800);
  v64 = 0;
  v6 = 0;
  v50 = 1;
  v7 = 1;
  v51 = 0;
  v52 = 1;
  v8 = 0;
  v9 = (int)a3;
LABEL_2:
  v58 = v7;
  while ( v6 < (int)v3 )
  {
    fuji_decode_interpolation_even((unsigned int)v3, *v4 + 2LL, (unsigned int)v6);
    v8 += fuji_decode_sample_even((_DWORD)a2, v9, *v5 + 2, v6, (__int64)a2 + 48);
    v7 = v58;
    v6 += 2;
LABEL_26:
    if ( v6 > 8 )
    {
      v37 = fuji_decode_sample_odd((_DWORD)a2, v9, *(_DWORD *)v4 + 2, v7, (__int64)a2 + 1392) + v8;
      v8 = fuji_decode_sample_odd((_DWORD)a2, v9, *v5 + 2, v58, (__int64)a2 + 1392) + v37;
      v7 = v58 + 2;
      goto LABEL_2;
    }
    v4 = (_QWORD *)((char *)a2 + 2760);
    v5 = (_DWORD *)((char *)a2 + 2800);
  }
  if ( v7 < (int)v3 )
    goto LABEL_26;
  _mm_lfence();
  v11 = 2 * v3 + 2;
  **((_WORD **)a2 + 345) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2LL);
  *(_WORD *)(v11 + *((_QWORD *)a2 + 345)) = *(_WORD *)(2 * v3 + *((_QWORD *)a2 + 344));
  **((_WORD **)a2 + 346) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2LL);
  *(_WORD *)(v11 + *((_QWORD *)a2 + 346)) = *(_WORD *)(2 * v3 + *((_QWORD *)a2 + 345));
  **((_WORD **)a2 + 347) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2LL);
  *(_WORD *)(v11 + *((_QWORD *)a2 + 347)) = *(_WORD *)(2 * v3 + *((_QWORD *)a2 + 346));
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  v12 = 0;
  v13 = (_DWORD *)((char *)a2 + 2808);
  v14 = 1;
  v15 = (_QWORD *)((char *)a2 + 2864);
  v59 = 1;
  v16 = 0;
  while ( 1 )
  {
    if ( v12 < (int)v3 )
    {
      v8 += fuji_decode_sample_even((_DWORD)a2, v9, *v13 + 2, v12, (__int64)a2 + 496);
      v12 += 2;
      fuji_decode_interpolation_even((unsigned int)v3, *v15 + 2LL, v16);
      v14 = v59;
      v16 += 2;
      v51 = v16;
      goto LABEL_30;
    }
    if ( v14 >= (int)v3 )
      break;
LABEL_30:
    if ( v12 <= 8 )
    {
      v14 = v59;
      v13 = (_DWORD *)((char *)a2 + 2808);
      v15 = (_QWORD *)((char *)a2 + 2864);
    }
    else
    {
      v59 += 2;
      v38 = fuji_decode_sample_odd((_DWORD)a2, v9, *v13 + 2, v14, (__int64)a2 + 1840) + v8;
      v8 = fuji_decode_sample_odd((_DWORD)a2, v9, *(_DWORD *)v15 + 2, v52, (__int64)a2 + 1840) + v38;
      v14 = v59;
      v52 += 2;
      v16 = v51;
    }
  }
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  _mm_lfence();
  v17 = (_QWORD *)((char *)a2 + 2816);
  v18 = 0;
  v19 = 0;
  **((_WORD **)a2 + 358) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2 * v3);
  **((_WORD **)a2 + 359) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3);
  **((_WORD **)a2 + 360) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 360) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3);
  v20 = 1;
  v21 = (_QWORD *)((char *)a2 + 2768);
LABEL_9:
  v60 = v20;
  while ( 1 )
  {
    v54 = v21;
    if ( v19 >= (int)v3 )
      break;
    v39 = *v21 + 2LL;
    if ( (v18 & 3) != 0 )
      v8 += fuji_decode_sample_even((_DWORD)a2, v9, v39, v18, (__int64)a2 + 944);
    else
      fuji_decode_interpolation_even((unsigned int)v3, v39, v18);
    v18 += 2;
    fuji_decode_interpolation_even((unsigned int)v3, *v17 + 2LL, (unsigned int)v19);
    v21 = v54;
    v19 += 2;
    v20 = v60;
LABEL_37:
    if ( v19 > 8 )
    {
      v40 = fuji_decode_sample_odd((_DWORD)a2, v9, (unsigned int)*v21 + 2, v20, (__int64)a2 + 2288) + v8;
      v8 = fuji_decode_sample_odd((_DWORD)a2, v9, *(_DWORD *)v17 + 2, v60, (__int64)a2 + 2288) + v40;
      v21 = v54;
      v20 = v60 + 2;
      goto LABEL_9;
    }
    v21 = (_QWORD *)((char *)a2 + 2768);
    v17 = (_QWORD *)((char *)a2 + 2816);
  }
  if ( v20 < (int)v3 )
    goto LABEL_37;
  **((_WORD **)a2 + 345) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2 * v3);
  **((_WORD **)a2 + 346) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3);
  **((_WORD **)a2 + 347) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 347) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3);
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  v22 = (_DWORD *)((char *)a2 + 2824);
  v53 = 1;
  v23 = 1;
  v24 = (__int64 *)((char *)a2 + 2872);
  v61 = 1;
  v25 = 0;
  v26 = 0;
  while ( 1 )
  {
    v55 = v22;
    if ( v25 >= (int)v3 )
      break;
    v41 = fuji_decode_sample_even((_DWORD)a2, v9, *v22 + 2, v25, (__int64)a2 + 48);
    v42 = *v24;
    v8 += v41;
    v25 += 2;
    if ( (v26 & 3) == 2 )
      fuji_decode_interpolation_even((unsigned int)v3, v42 + 2, v26);
    else
      v8 += fuji_decode_sample_even((_DWORD)a2, v9, (int)v42 + 2, v26, (__int64)a2 + 48);
    v22 = v55;
    v26 += 2;
    v23 = v61;
LABEL_44:
    if ( v25 <= 8 )
    {
      v23 = v61;
      v22 = (_DWORD *)((char *)a2 + 2824);
      v24 = (__int64 *)((char *)a2 + 2872);
    }
    else
    {
      v61 += 2;
      v43 = fuji_decode_sample_odd((_DWORD)a2, v9, (unsigned int)*(_QWORD *)v22 + 2, v23, (__int64)a2 + 1392) + v8;
      v8 = fuji_decode_sample_odd((_DWORD)a2, v9, *(_DWORD *)v24 + 2, v53, (__int64)a2 + 1392) + v43;
      v22 = v55;
      v23 = v61;
      v53 += 2;
    }
  }
  if ( v23 < (int)v3 )
    goto LABEL_44;
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  _mm_lfence();
  v27 = (_DWORD *)((char *)a2 + 2832);
  v28 = 0;
  v29 = 0;
  **((_WORD **)a2 + 358) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2 * v3);
  **((_WORD **)a2 + 359) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3);
  **((_WORD **)a2 + 360) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 360) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3);
  v30 = 1;
  v31 = (_QWORD *)((char *)a2 + 2776);
LABEL_16:
  v62 = v30;
  while ( 1 )
  {
    v56 = v31;
    if ( v28 >= (int)v3 )
      break;
    v44 = *v31;
    if ( (v29 & 3) == 2 )
    {
      fuji_decode_interpolation_even((unsigned int)v3, v44 + 2, v29);
      v45 = (char *)a2 + 496;
    }
    else
    {
      v45 = (char *)a2 + 496;
      v8 += fuji_decode_sample_even((_DWORD)a2, v9, (int)v44 + 2, v29, (__int64)a2 + 496);
    }
    v29 += 2;
    v46 = fuji_decode_sample_even((_DWORD)a2, v9, *v27 + 2, v28, (__int64)v45);
    v30 = v62;
    v8 += v46;
    v31 = v56;
    v28 += 2;
LABEL_51:
    if ( v28 > 8 )
    {
      v47 = fuji_decode_sample_odd((_DWORD)a2, v9, (unsigned int)*v31 + 2, v30, (__int64)a2 + 1840) + v8;
      v8 = fuji_decode_sample_odd((_DWORD)a2, v9, *v27 + 2, v62, (__int64)a2 + 1840) + v47;
      v31 = v56;
      v30 = v62 + 2;
      goto LABEL_16;
    }
    v31 = (_QWORD *)((char *)a2 + 2776);
    v27 = (_DWORD *)((char *)a2 + 2832);
  }
  if ( v30 < (int)v3 )
    goto LABEL_51;
  **((_WORD **)a2 + 345) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2 * v3);
  **((_WORD **)a2 + 346) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3);
  **((_WORD **)a2 + 347) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 347) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3);
  fuji_extend_green((char *)a2 + 2744, v3);
  v32 = 0;
  v33 = (_QWORD *)((char *)a2 + 2840);
  v34 = 1;
  v35 = (_QWORD *)((char *)a2 + 2880);
  v36 = 0;
  v63 = 1;
  while ( v32 < (int)v3 )
  {
    fuji_decode_interpolation_even((unsigned int)v3, *v33 + 2LL, (unsigned int)v32);
    v64 += 2;
    v48 = *v35 + 2LL;
    if ( (v36 & 3) != 0 )
      v8 += fuji_decode_sample_even((_DWORD)a2, v9, v48, v36, (__int64)a2 + 944);
    else
      fuji_decode_interpolation_even((unsigned int)v3, v48, v36);
    v32 = v64;
    v36 += 2;
    v34 = v50;
LABEL_58:
    if ( v32 <= 8 )
    {
      v34 = v50;
      v33 = (_QWORD *)((char *)a2 + 2840);
      v35 = (_QWORD *)((char *)a2 + 2880);
    }
    else
    {
      v50 += 2;
      v49 = fuji_decode_sample_odd((_DWORD)a2, v9, *(_DWORD *)v33 + 2, v34, (__int64)a2 + 2288) + v8;
      v8 = fuji_decode_sample_odd((_DWORD)a2, v9, *(_DWORD *)v35 + 2, v63, (__int64)a2 + 2288) + v49;
      v32 = v64;
      v34 = v50;
      v63 += 2;
    }
  }
  if ( v34 < (int)v3 )
    goto LABEL_58;
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  _mm_lfence();
  **((_WORD **)a2 + 358) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2 * v3);
  **((_WORD **)a2 + 359) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3);
  **((_WORD **)a2 + 360) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 360) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3);
  if ( v8 )
    LibRaw::derror(this);
}

```

## disassembly

```asm
0x180014da0  mov     [rsp+arg_18], rbx
0x180014da5  mov     [rsp+arg_0], rcx
0x180014daa  push    rbp
0x180014dab  push    rsi
0x180014dac  push    rdi
0x180014dad  push    r12
0x180014daf  push    r13
0x180014db1  push    r14
0x180014db3  push    r15
0x180014db5  sub     rsp, 60h
0x180014db9  movzx   r14d, word ptr [r8+94h]
0x180014dc1  lea     r13, [rdx+0AC8h]
0x180014dc8  xor     r11d, r11d
0x180014dcb  lea     rdi, [rdx+0AF0h]
0x180014dd2  mov     esi, 1
0x180014dd7  mov     [rsp+98h+arg_10], r11d
0x180014ddf  mov     r12d, r11d
0x180014de2  mov     [rsp+98h+var_68], esi
0x180014de6  mov     eax, esi
0x180014de8  mov     dword ptr [rsp+98h+var_60], r11d
0x180014ded  mov     dword ptr [rsp+98h+var_58], esi
0x180014df1  mov     ebp, r11d
0x180014df4  mov     r15, r8
0x180014df7  mov     rbx, rdx
0x180014dfa  mov     [rsp+98h+arg_8], eax
0x180014e01  mov     [rsp+98h+var_50], rdi
0x180014e06  cmp     r12d, r14d
0x180014e09  jl      loc_1800152F6
0x180014e0f  cmp     eax, r14d
0x180014e12  jl      loc_180015334
0x180014e18  lea     r11, [rbx+0AB8h]
0x180014e1f  lfence
0x180014e22  mov     rax, [r11+8]
0x180014e26  lea     rdx, [r14+r14]
0x180014e2a  mov     rcx, [r11+10h]
0x180014e2e  lea     r8, ds:2[r14*2]
0x180014e36  movzx   eax, word ptr [rax+2]
0x180014e3a  mov     [rcx], ax
0x180014e3d  mov     rax, [r11+8]
0x180014e41  mov     rcx, [r11+10h]
0x180014e45  movzx   eax, word ptr [rdx+rax]
0x180014e49  mov     [r8+rcx], ax
0x180014e4e  mov     rax, [r11+10h]
0x180014e52  mov     rcx, [r11+18h]
0x180014e56  movzx   eax, word ptr [rax+2]
0x180014e5a  mov     [rcx], ax
0x180014e5d  mov     rax, [r11+10h]
0x180014e61  mov     rcx, [r11+18h]
0x180014e65  movzx   eax, word ptr [rdx+rax]
0x180014e69  mov     [r8+rcx], ax
0x180014e6e  mov     rax, [r11+18h]
0x180014e72  mov     rcx, [r11+20h]
0x180014e76  movzx   eax, word ptr [rax+2]
0x180014e7a  mov     [rcx], ax
0x180014e7d  mov     rax, [r11+18h]
0x180014e81  mov     rcx, [r11+20h]
0x180014e85  movzx   eax, word ptr [rdx+rax]
0x180014e89  mov     edx, r14d
0x180014e8c  mov     [r8+rcx], ax
0x180014e91  mov     rcx, r11
0x180014e94  call    fuji_extend_green
0x180014e99  xor     r12d, r12d
0x180014e9c  lea     r13, [rbx+0AF8h]
0x180014ea3  mov     eax, 1
0x180014ea8  lea     rdi, [rbx+0B30h]
0x180014eaf  mov     [rsp+98h+arg_8], eax
0x180014eb6  mov     esi, r12d
0x180014eb9  mov     [rsp+98h+var_50], rdi
0x180014ebe  cmp     r12d, r14d
0x180014ec1  jl      loc_1800153AB
0x180014ec7  cmp     eax, r14d
0x180014eca  jl      loc_1800153F3
0x180014ed0  mov     edx, r14d
0x180014ed3  lea     rcx, [rbx+0AB8h]
0x180014eda  call    fuji_extend_green
0x180014edf  lfence
0x180014ee2  mov     rax, [rbx+0B28h]
0x180014ee9  lea     rdi, [rbx+0B00h]
0x180014ef0  mov     rcx, [rbx+0B30h]
0x180014ef7  xor     r11d, r11d
0x180014efa  mov     r13d, r11d
0x180014efd  mov     r12d, r11d
0x180014f00  movzx   eax, word ptr [rax+2]
0x180014f04  mov     [rcx], ax
0x180014f07  mov     rax, [rbx+0B28h]
0x180014f0e  mov     rcx, [rbx+0B30h]
0x180014f15  movzx   eax, word ptr [rax+r14*2]
0x180014f1a  mov     [rcx+r14*2+2], ax
0x180014f20  mov     rax, [rbx+0B30h]
0x180014f27  mov     rcx, [rbx+0B38h]
0x180014f2e  movzx   eax, word ptr [rax+2]
0x180014f32  mov     [rcx], ax
0x180014f35  mov     rax, [rbx+0B30h]
0x180014f3c  mov     rcx, [rbx+0B38h]
0x180014f43  movzx   eax, word ptr [rax+r14*2]
0x180014f48  mov     [rcx+r14*2+2], ax
0x180014f4e  mov     rax, [rbx+0B38h]
0x180014f55  mov     rcx, [rbx+0B40h]
0x180014f5c  movzx   eax, word ptr [rax+2]
0x180014f60  mov     [rcx], ax
0x180014f63  mov     rax, [rbx+0B38h]
0x180014f6a  mov     rcx, [rbx+0B40h]
0x180014f71  movzx   eax, word ptr [rax+r14*2]
0x180014f76  mov     [rcx+r14*2+2], ax
0x180014f7c  mov     ecx, 1
0x180014f81  lea     rax, [rbx+0AD0h]
0x180014f88  mov     [rsp+98h+arg_8], ecx
0x180014f8f  mov     [rsp+98h+var_50], rax
0x180014f94  mov     [rsp+98h+var_58], rdi
0x180014f99  cmp     r12d, r14d
0x180014f9c  jl      loc_180015480
0x180014fa2  cmp     ecx, r14d
0x180014fa5  jl      loc_1800154DF
0x180014fab  mov     rax, [rbx+0AC0h]
0x180014fb2  mov     edx, r14d
0x180014fb5  mov     rcx, [rbx+0AC8h]
0x180014fbc  movzx   eax, word ptr [rax+2]
0x180014fc0  mov     [rcx], ax
0x180014fc3  mov     rax, [rbx+0AC0h]
0x180014fca  mov     rcx, [rbx+0AC8h]
0x180014fd1  movzx   eax, word ptr [rax+r14*2]
0x180014fd6  mov     [rcx+r14*2+2], ax
0x180014fdc  mov     rax, [rbx+0AC8h]
0x180014fe3  mov     rcx, [rbx+0AD0h]
0x180014fea  movzx   eax, word ptr [rax+2]
0x180014fee  mov     [rcx], ax
0x180014ff1  mov     rax, [rbx+0AC8h]
0x180014ff8  mov     rcx, [rbx+0AD0h]
0x180014fff  movzx   eax, word ptr [rax+r14*2]
0x180015004  mov     [rcx+r14*2+2], ax
0x18001500a  mov     rax, [rbx+0AD0h]
0x180015011  mov     rcx, [rbx+0AD8h]
0x180015018  movzx   eax, word ptr [rax+2]
0x18001501c  mov     [rcx], ax
0x18001501f  mov     rax, [rbx+0AD0h]
0x180015026  mov     rcx, [rbx+0AD8h]
0x18001502d  movzx   eax, word ptr [rax+r14*2]
0x180015032  mov     [rcx+r14*2+2], ax
0x180015038  lea     rcx, [rbx+0AB8h]
0x18001503f  call    fuji_extend_green
0x180015044  mov     esi, 1
0x180015049  lea     rax, [rbx+0B08h]
0x180015050  xor     r11d, r11d
0x180015053  mov     dword ptr [rsp+98h+var_58], esi
0x180015057  mov     ecx, esi
0x180015059  lea     rdi, [rbx+0B38h]
0x180015060  mov     [rsp+98h+arg_8], ecx
0x180015067  mov     r13d, r11d
0x18001506a  mov     r12d, r11d
0x18001506d  mov     [rsp+98h+var_60], rdi
0x180015072  mov     [rsp+98h+var_50], rax
0x180015077  cmp     r13d, r14d
0x18001507a  jl      loc_18001555A
0x180015080  cmp     ecx, r14d
0x180015083  jl      loc_1800155C4
0x180015089  lea     rcx, [rbx+0AB8h]
0x180015090  mov     edx, r14d
0x180015093  call    fuji_extend_green
0x180015098  lfence
0x18001509b  mov     rax, [rbx+0B28h]
0x1800150a2  lea     rsi, [rbx+0B10h]
0x1800150a9  mov     rcx, [rbx+0B30h]
0x1800150b0  xor     r12d, r12d
0x1800150b3  mov     r13d, r12d
0x1800150b6  movzx   eax, word ptr [rax+2]
0x1800150ba  mov     [rcx], ax
0x1800150bd  mov     rax, [rbx+0B28h]
0x1800150c4  mov     rcx, [rbx+0B30h]
0x1800150cb  movzx   eax, word ptr [rax+r14*2]
0x1800150d0  mov     [rcx+r14*2+2], ax
0x1800150d6  mov     rax, [rbx+0B30h]
0x1800150dd  mov     rcx, [rbx+0B38h]
0x1800150e4  movzx   eax, word ptr [rax+2]
0x1800150e8  mov     [rcx], ax
0x1800150eb  mov     rax, [rbx+0B30h]
0x1800150f2  mov     rcx, [rbx+0B38h]
0x1800150f9  movzx   eax, word ptr [rax+r14*2]
0x1800150fe  mov     [rcx+r14*2+2], ax
0x180015104  mov     rax, [rbx+0B38h]
0x18001510b  mov     rcx, [rbx+0B40h]
0x180015112  movzx   eax, word ptr [rax+2]
0x180015116  mov     [rcx], ax
0x180015119  mov     rax, [rbx+0B38h]
0x180015120  mov     rcx, [rbx+0B40h]
0x180015127  movzx   eax, word ptr [rax+r14*2]
0x18001512c  mov     [rcx+r14*2+2], ax
0x180015132  mov     ecx, 1
0x180015137  lea     rax, [rbx+0AD8h]
0x18001513e  mov     [rsp+98h+arg_8], ecx
0x180015145  mov     [rsp+98h+var_50], rax
0x18001514a  mov     [rsp+98h+var_58], rsi
0x18001514f  cmp     r12d, r14d
0x180015152  jl      loc_180015651
0x180015158  cmp     ecx, r14d
0x18001515b  jl      loc_1800156C5
0x180015161  mov     rax, [rbx+0AC0h]
0x180015168  mov     rdx, r14
0x18001516b  mov     rcx, [rbx+0AC8h]
0x180015172  movzx   eax, word ptr [rax+2]
0x180015176  mov     [rcx], ax
0x180015179  mov     rax, [rbx+0AC0h]
0x180015180  mov     rcx, [rbx+0AC8h]
0x180015187  movzx   eax, word ptr [rax+r14*2]
0x18001518c  mov     [rcx+r14*2+2], ax
0x180015192  mov     rax, [rbx+0AC8h]
0x180015199  mov     rcx, [rbx+0AD0h]
0x1800151a0  movzx   eax, word ptr [rax+2]
0x1800151a4  mov     [rcx], ax
0x1800151a7  mov     rax, [rbx+0AC8h]
0x1800151ae  mov     rcx, [rbx+0AD0h]
0x1800151b5  movzx   eax, word ptr [rax+r14*2]
0x1800151ba  mov     [rcx+r14*2+2], ax
0x1800151c0  mov     rax, [rbx+0AD0h]
0x1800151c7  mov     rcx, [rbx+0AD8h]
0x1800151ce  movzx   eax, word ptr [rax+2]
0x1800151d2  mov     [rcx], ax
0x1800151d5  mov     rax, [rbx+0AD0h]
0x1800151dc  mov     rcx, [rbx+0AD8h]
0x1800151e3  movzx   eax, word ptr [rax+r14*2]
0x1800151e8  mov     [rcx+r14*2+2], ax
0x1800151ee  lea     rcx, [rbx+0AB8h]
0x1800151f5  call    fuji_extend_green
0x1800151fa  xor     r11d, r11d
0x1800151fd  lea     r13, [rbx+0B18h]
0x180015204  mov     eax, 1
0x180015209  lea     rdi, [rbx+0B40h]
0x180015210  mov     r12d, r11d
0x180015213  mov     [rsp+98h+arg_8], eax
0x18001521a  mov     [rsp+98h+var_50], rdi
0x18001521f  cmp     r11d, r14d
0x180015222  jl      loc_180015740
0x180015228  cmp     eax, r14d
0x18001522b  jl      loc_1800157A4
0x180015231  lea     rcx, [rbx+0AB8h]
0x180015238  mov     edx, r14d
0x18001523b  call    fuji_extend_green
0x180015240  lfence
0x180015243  mov     rax, [rbx+0B28h]
0x18001524a  mov     rcx, [rbx+0B30h]
0x180015251  movzx   eax, word ptr [rax+2]
0x180015255  mov     [rcx], ax
0x180015258  mov     rax, [rbx+0B28h]
0x18001525f  mov     rcx, [rbx+0B30h]
0x180015266  movzx   eax, word ptr [rax+r14*2]
0x18001526b  mov     [rcx+r14*2+2], ax
0x180015271  mov     rax, [rbx+0B30h]
0x180015278  mov     rcx, [rbx+0B38h]
0x18001527f  movzx   eax, word ptr [rax+2]
0x180015283  mov     [rcx], ax
0x180015286  mov     rax, [rbx+0B30h]
0x18001528d  mov     rcx, [rbx+0B38h]
0x180015294  movzx   eax, word ptr [rax+r14*2]
0x180015299  mov     [rcx+r14*2+2], ax
0x18001529f  mov     rax, [rbx+0B38h]
0x1800152a6  mov     rcx, [rbx+0B40h]
0x1800152ad  movzx   eax, word ptr [rax+2]
0x1800152b1  mov     [rcx], ax
0x1800152b4  mov     rax, [rbx+0B38h]
0x1800152bb  mov     rcx, [rbx+0B40h]
0x1800152c2  movzx   eax, word ptr [rax+r14*2]
0x1800152c7  mov     [rcx+r14*2+2], ax
0x1800152cd  test    ebp, ebp
0x1800152cf  jz      short loc_1800152DE
0x1800152d1  mov     rcx, [rsp+98h+arg_0]; this
0x1800152d9  call    ?derror@LibRaw@@IEAAXXZ; LibRaw::derror(void)
0x1800152de  mov     rbx, [rsp+98h+arg_18]
0x1800152e6  add     rsp, 60h
0x1800152ea  pop     r15
0x1800152ec  pop     r14
0x1800152ee  pop     r13
0x1800152f0  pop     r12
0x1800152f2  pop     rdi
0x1800152f3  pop     rsi
0x1800152f4  pop     rbp
0x1800152f5  retn
0x1800152f6  mov     rdx, [r13+0]
0x1800152fa  mov     r8d, r12d
0x1800152fd  add     rdx, 2
0x180015301  mov     ecx, r14d
0x180015304  call    fuji_decode_interpolation_even
0x180015309  mov     r8, [rdi]
0x18001530c  lea     rax, [rbx+30h]
0x180015310  add     r8, 2
0x180015314  mov     [rsp+98h+var_78], rax
0x180015319  mov     r9d, r12d
0x18001531c  mov     rdx, r15
0x18001531f  mov     rcx, rbx
0x180015322  call    fuji_decode_sample_even
0x180015327  add     ebp, eax
0x180015329  mov     eax, [rsp+98h+arg_8]
0x180015330  add     r12d, 2
0x180015334  cmp     r12d, 8
0x180015338  jle     short loc_180015398
0x18001533a  mov     r8, [r13+0]
0x18001533e  lea     rsi, [rbx+570h]
0x180015345  add     r8, 2
0x180015349  mov     [rsp+98h+var_78], rsi
0x18001534e  mov     r9d, eax
0x180015351  mov     rdx, r15
0x180015354  mov     rcx, rbx
  ... truncated ...
```
