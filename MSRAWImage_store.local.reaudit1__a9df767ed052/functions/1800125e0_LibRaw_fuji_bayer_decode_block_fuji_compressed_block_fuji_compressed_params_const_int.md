# LibRaw::fuji_bayer_decode_block(fuji_compressed_block *,fuji_compressed_params const *,int)

- ea: `0x1800125e0`
- end: `0x180013003`
- name: `?fuji_bayer_decode_block@LibRaw@@IEAAXPEAUfuji_compressed_block@@PEBUfuji_compressed_params@@H@Z`
- size: `2595`
- prototype: `void __fastcall(LibRaw *__hidden this, struct fuji_compressed_block *, const struct fuji_compressed_params *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013a50`

## callees

- `0x1800090f0`
- `0x1800125e0`
- `0x180013440`
- `0x180013770`
- `0x180013e50`

## pseudocode

```c
void __fastcall LibRaw::fuji_bayer_decode_block(
        LibRaw *this,
        struct fuji_compressed_block *a2,
        const struct fuji_compressed_params *a3)
{
  __int64 v3; // r14
  _DWORD *v4; // r13
  char *v5; // rax
  int v6; // edi
  int v7; // r12d
  int v8; // ecx
  int v9; // ebp
  int v10; // r15d
  __int64 v12; // r8
  int v13; // ecx
  _DWORD *v14; // r13
  char *v15; // rax
  int v16; // r12d
  _DWORD *v17; // r13
  int v18; // r12d
  int v19; // ecx
  char *v20; // rax
  int v21; // ecx
  int v22; // r12d
  _DWORD *v23; // r13
  char *v24; // rax
  _DWORD *v25; // r13
  int v26; // r12d
  int v27; // ecx
  char *v28; // rax
  int v29; // r11d
  _DWORD *v30; // r12
  _QWORD *v31; // r13
  int v32; // ebp
  int v33; // eax
  int v34; // ebp
  int v35; // ebp
  int v36; // eax
  int v37; // ebp
  int v38; // eax
  int v39; // ebp
  int v40; // eax
  int v41; // ebp
  int v42; // ebp
  int v43; // eax
  int v44; // ebp
  int v45; // eax
  int v46; // ebp
  int v47; // eax
  int v48; // ebp
  int v49; // ebp
  int v50; // eax
  int v51; // ebp
  int v52; // eax
  int v53; // [rsp+30h] [rbp-58h]
  int v54; // [rsp+34h] [rbp-54h]
  int v55; // [rsp+34h] [rbp-54h]
  int v56; // [rsp+38h] [rbp-50h]
  int v57; // [rsp+38h] [rbp-50h]
  int v58; // [rsp+38h] [rbp-50h]
  char *v59; // [rsp+40h] [rbp-48h]
  char *v60; // [rsp+40h] [rbp-48h]
  char *v61; // [rsp+40h] [rbp-48h]
  char *v62; // [rsp+40h] [rbp-48h]
  char *v63; // [rsp+40h] [rbp-48h]
  int v65; // [rsp+98h] [rbp+10h]
  int v66; // [rsp+98h] [rbp+10h]
  int v67; // [rsp+98h] [rbp+10h]
  int v68; // [rsp+98h] [rbp+10h]
  int v69; // [rsp+98h] [rbp+10h]
  int v70; // [rsp+98h] [rbp+10h]
  int v71; // [rsp+A0h] [rbp+18h]

  v3 = *((unsigned __int16 *)a3 + 74);
  v4 = (_DWORD *)((char *)a2 + 2760);
  v5 = (char *)a2 + 2800;
  v6 = 1;
  v71 = 0;
  v7 = 0;
  v53 = 1;
  v8 = 1;
  v54 = 0;
  v56 = 1;
  v9 = 0;
  v10 = (int)a3;
LABEL_2:
  v65 = v8;
  while ( 1 )
  {
    v59 = v5;
    if ( v7 >= (int)v3 )
      break;
    v32 = fuji_decode_sample_even((_DWORD)a2, v10, *v4 + 2, v7, (__int64)a2 + 48) + v9;
    v33 = fuji_decode_sample_even((_DWORD)a2, v10, *(_DWORD *)v59 + 2, v7, (__int64)a2 + 48);
    v8 = v65;
    v9 = v33 + v32;
    v7 += 2;
LABEL_26:
    if ( v7 > 8 )
    {
      v34 = fuji_decode_sample_odd((_DWORD)a2, v10, (unsigned int)*(_QWORD *)v4 + 2, v8, (__int64)a2 + 1392) + v9;
      v9 = fuji_decode_sample_odd((_DWORD)a2, v10, *(_DWORD *)v59 + 2, v65, (__int64)a2 + 1392) + v34;
      v5 = v59;
      v8 = v65 + 2;
      goto LABEL_2;
    }
    v4 = (_DWORD *)((char *)a2 + 2760);
    v5 = (char *)a2 + 2800;
  }
  if ( v8 < (int)v3 )
    goto LABEL_26;
  _mm_lfence();
  v12 = 2 * v3 + 2;
  **((_WORD **)a2 + 345) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2LL);
  *(_WORD *)(v12 + *((_QWORD *)a2 + 345)) = *(_WORD *)(2 * v3 + *((_QWORD *)a2 + 344));
  **((_WORD **)a2 + 346) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2LL);
  *(_WORD *)(v12 + *((_QWORD *)a2 + 346)) = *(_WORD *)(2 * v3 + *((_QWORD *)a2 + 345));
  **((_WORD **)a2 + 347) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2LL);
  *(_WORD *)(v12 + *((_QWORD *)a2 + 347)) = *(_WORD *)(2 * v3 + *((_QWORD *)a2 + 346));
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  v13 = 1;
  v14 = (_DWORD *)((char *)a2 + 2808);
  v66 = 1;
  v15 = (char *)a2 + 2864;
  v16 = 0;
  while ( 1 )
  {
    v60 = v15;
    if ( v16 < (int)v3 )
    {
      v35 = fuji_decode_sample_even((_DWORD)a2, v10, *v14 + 2, v16, (__int64)a2 + 496) + v9;
      v16 += 2;
      v36 = fuji_decode_sample_even((_DWORD)a2, v10, *(_DWORD *)v60 + 2, v54, (__int64)a2 + 496);
      v13 = v66;
      v9 = v36 + v35;
      v54 += 2;
      goto LABEL_30;
    }
    if ( v13 >= (int)v3 )
      break;
LABEL_30:
    if ( v16 <= 8 )
    {
      v13 = v66;
      v14 = (_DWORD *)((char *)a2 + 2808);
      v15 = (char *)a2 + 2864;
    }
    else
    {
      v66 += 2;
      v37 = fuji_decode_sample_odd((_DWORD)a2, v10, (unsigned int)*(_QWORD *)v14 + 2, v13, (__int64)a2 + 1840) + v9;
      v38 = fuji_decode_sample_odd((_DWORD)a2, v10, *(_DWORD *)v60 + 2, v56, (__int64)a2 + 1840);
      v13 = v66;
      v9 = v38 + v37;
      v15 = v60;
      v56 += 2;
    }
  }
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  _mm_lfence();
  v17 = (_DWORD *)((char *)a2 + 2768);
  v18 = 0;
  **((_WORD **)a2 + 358) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2 * v3);
  **((_WORD **)a2 + 359) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3);
  **((_WORD **)a2 + 360) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 360) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3);
  v19 = 1;
  v20 = (char *)a2 + 2816;
LABEL_9:
  v67 = v19;
  while ( 1 )
  {
    v61 = v20;
    if ( v18 >= (int)v3 )
      break;
    v39 = fuji_decode_sample_even((_DWORD)a2, v10, *v17 + 2, v18, (__int64)a2 + 944) + v9;
    v40 = fuji_decode_sample_even((_DWORD)a2, v10, *(_DWORD *)v61 + 2, v18, (__int64)a2 + 944);
    v19 = v67;
    v9 = v40 + v39;
    v18 += 2;
LABEL_34:
    if ( v18 > 8 )
    {
      v41 = fuji_decode_sample_odd((_DWORD)a2, v10, (unsigned int)*(_QWORD *)v17 + 2, v19, (__int64)a2 + 2288) + v9;
      v9 = fuji_decode_sample_odd((_DWORD)a2, v10, *(_DWORD *)v61 + 2, v67, (__int64)a2 + 2288) + v41;
      v20 = v61;
      v19 = v67 + 2;
      goto LABEL_9;
    }
    v17 = (_DWORD *)((char *)a2 + 2768);
    v20 = (char *)a2 + 2816;
  }
  if ( v19 < (int)v3 )
    goto LABEL_34;
  **((_WORD **)a2 + 345) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2 * v3);
  **((_WORD **)a2 + 346) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3);
  **((_WORD **)a2 + 347) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 347) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3);
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  v55 = 1;
  v21 = 1;
  v57 = 0;
  v22 = 0;
  v68 = 1;
  v23 = (_DWORD *)((char *)a2 + 2824);
  v24 = (char *)a2 + 2872;
  while ( 1 )
  {
    v62 = v24;
    if ( v22 < (int)v3 )
    {
      v42 = fuji_decode_sample_even((_DWORD)a2, v10, *v23 + 2, v22, (__int64)a2 + 48) + v9;
      v22 += 2;
      v43 = fuji_decode_sample_even((_DWORD)a2, v10, *(_DWORD *)v62 + 2, v57, (__int64)a2 + 48);
      v21 = v68;
      v9 = v43 + v42;
      v57 += 2;
      goto LABEL_38;
    }
    if ( v21 >= (int)v3 )
      break;
LABEL_38:
    if ( v22 <= 8 )
    {
      v21 = v68;
      v23 = (_DWORD *)((char *)a2 + 2824);
      v24 = (char *)a2 + 2872;
    }
    else
    {
      v68 += 2;
      v44 = fuji_decode_sample_odd((_DWORD)a2, v10, (unsigned int)*(_QWORD *)v23 + 2, v21, (__int64)a2 + 1392) + v9;
      v45 = fuji_decode_sample_odd((_DWORD)a2, v10, *(_DWORD *)v62 + 2, v55, (__int64)a2 + 1392);
      v21 = v68;
      v9 = v45 + v44;
      v24 = v62;
      v55 += 2;
    }
  }
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  _mm_lfence();
  v25 = (_DWORD *)((char *)a2 + 2776);
  v26 = 0;
  **((_WORD **)a2 + 358) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2 * v3);
  **((_WORD **)a2 + 359) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3);
  **((_WORD **)a2 + 360) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 360) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3);
  v27 = 1;
  v28 = (char *)a2 + 2832;
LABEL_16:
  v69 = v27;
  while ( 1 )
  {
    v63 = v28;
    if ( v26 >= (int)v3 )
      break;
    v46 = fuji_decode_sample_even((_DWORD)a2, v10, *v25 + 2, v26, (__int64)a2 + 496) + v9;
    v47 = fuji_decode_sample_even((_DWORD)a2, v10, *(_DWORD *)v63 + 2, v26, (__int64)a2 + 496);
    v27 = v69;
    v9 = v47 + v46;
    v26 += 2;
LABEL_42:
    if ( v26 > 8 )
    {
      v48 = fuji_decode_sample_odd((_DWORD)a2, v10, (unsigned int)*(_QWORD *)v25 + 2, v27, (__int64)a2 + 1840) + v9;
      v9 = fuji_decode_sample_odd((_DWORD)a2, v10, *(_DWORD *)v63 + 2, v69, (__int64)a2 + 1840) + v48;
      v28 = v63;
      v27 = v69 + 2;
      goto LABEL_16;
    }
    v25 = (_DWORD *)((char *)a2 + 2776);
    v28 = (char *)a2 + 2832;
  }
  if ( v27 < (int)v3 )
    goto LABEL_42;
  **((_WORD **)a2 + 345) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 344) + 2 * v3);
  **((_WORD **)a2 + 346) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 345) + 2 * v3);
  **((_WORD **)a2 + 347) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 347) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 346) + 2 * v3);
  fuji_extend_green((char *)a2 + 2744, v3);
  v29 = 0;
  v58 = 1;
  v70 = 0;
  v30 = (_DWORD *)((char *)a2 + 2840);
  v31 = (_QWORD *)((char *)a2 + 2880);
  while ( 1 )
  {
    if ( v29 < (int)v3 )
    {
      v71 += 2;
      v49 = fuji_decode_sample_even((_DWORD)a2, v10, *v30 + 2, v29, (__int64)a2 + 944) + v9;
      v50 = fuji_decode_sample_even((_DWORD)a2, v10, (unsigned int)*v31 + 2, v70, (__int64)a2 + 944);
      v29 = v71;
      v9 = v50 + v49;
      v6 = v53;
      v70 += 2;
      goto LABEL_46;
    }
    if ( v6 >= (int)v3 )
      break;
LABEL_46:
    if ( v29 <= 8 )
    {
      v6 = v53;
      v30 = (_DWORD *)((char *)a2 + 2840);
      v31 = (_QWORD *)((char *)a2 + 2880);
    }
    else
    {
      v53 += 2;
      v51 = fuji_decode_sample_odd((_DWORD)a2, v10, *v30 + 2, v6, (__int64)a2 + 2288) + v9;
      v52 = fuji_decode_sample_odd((_DWORD)a2, v10, (unsigned int)*v31 + 2, v58, (__int64)a2 + 2288);
      v29 = v71;
      v9 = v52 + v51;
      v6 = v53;
      v58 += 2;
    }
  }
  fuji_extend_green((char *)a2 + 2744, (unsigned int)v3);
  _mm_lfence();
  **((_WORD **)a2 + 358) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 357) + 2 * v3);
  **((_WORD **)a2 + 359) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 358) + 2 * v3);
  **((_WORD **)a2 + 360) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2LL);
  *(_WORD *)(*((_QWORD *)a2 + 360) + 2 * v3 + 2) = *(_WORD *)(*((_QWORD *)a2 + 359) + 2 * v3);
  if ( v9 )
    LibRaw::derror(this);
}

```

## disassembly

```asm
0x1800125e0  mov     [rsp+arg_18], rbx
0x1800125e5  mov     [rsp+arg_0], rcx
0x1800125ea  push    rbp
0x1800125eb  push    rsi
0x1800125ec  push    rdi
0x1800125ed  push    r12
0x1800125ef  push    r13
0x1800125f1  push    r14
0x1800125f3  push    r15
0x1800125f5  sub     rsp, 50h
0x1800125f9  movzx   r14d, word ptr [r8+94h]
0x180012601  lea     r13, [rdx+0AC8h]
0x180012608  xor     r11d, r11d
0x18001260b  lea     rax, [rdx+0AF0h]
0x180012612  mov     edi, 1
0x180012617  mov     [rsp+88h+arg_10], r11d
0x18001261f  mov     r12d, r11d
0x180012622  mov     [rsp+88h+var_58], edi
0x180012626  mov     ecx, edi
0x180012628  mov     [rsp+88h+var_54], r11d
0x18001262d  mov     [rsp+88h+var_50], edi
0x180012631  mov     ebp, r11d
0x180012634  mov     r15, r8
0x180012637  mov     rbx, rdx
0x18001263a  mov     [rsp+88h+arg_8], ecx
0x180012641  mov     [rsp+88h+var_48], rax
0x180012646  cmp     r12d, r14d
0x180012649  jl      loc_180012B07
0x18001264f  cmp     ecx, r14d
0x180012652  jl      loc_180012B54
0x180012658  lea     r11, [rbx+0AB8h]
0x18001265f  lfence
0x180012662  mov     rax, [r11+8]
0x180012666  lea     rdx, [r14+r14]
0x18001266a  mov     rcx, [r11+10h]
0x18001266e  lea     r8, ds:2[r14*2]
0x180012676  movzx   eax, word ptr [rax+2]
0x18001267a  mov     [rcx], ax
0x18001267d  mov     rax, [r11+8]
0x180012681  mov     rcx, [r11+10h]
0x180012685  movzx   eax, word ptr [rdx+rax]
0x180012689  mov     [r8+rcx], ax
0x18001268e  mov     rax, [r11+10h]
0x180012692  mov     rcx, [r11+18h]
0x180012696  movzx   eax, word ptr [rax+2]
0x18001269a  mov     [rcx], ax
0x18001269d  mov     rax, [r11+10h]
0x1800126a1  mov     rcx, [r11+18h]
0x1800126a5  movzx   eax, word ptr [rdx+rax]
0x1800126a9  mov     [r8+rcx], ax
0x1800126ae  mov     rax, [r11+18h]
0x1800126b2  mov     rcx, [r11+20h]
0x1800126b6  movzx   eax, word ptr [rax+2]
0x1800126ba  mov     [rcx], ax
0x1800126bd  mov     rax, [r11+18h]
0x1800126c1  mov     rcx, [r11+20h]
0x1800126c5  movzx   eax, word ptr [rdx+rax]
0x1800126c9  mov     edx, r14d
0x1800126cc  mov     [r8+rcx], ax
0x1800126d1  mov     rcx, r11
0x1800126d4  call    fuji_extend_green
0x1800126d9  mov     ecx, edi
0x1800126db  lea     r13, [rbx+0AF8h]
0x1800126e2  mov     [rsp+88h+arg_8], ecx
0x1800126e9  lea     rax, [rbx+0B30h]
0x1800126f0  xor     r12d, r12d
0x1800126f3  mov     [rsp+88h+var_48], rax
0x1800126f8  cmp     r12d, r14d
0x1800126fb  jl      loc_180012BCB
0x180012701  cmp     ecx, r14d
0x180012704  jl      loc_180012C26
0x18001270a  mov     edx, r14d
0x18001270d  lea     rcx, [rbx+0AB8h]
0x180012714  call    fuji_extend_green
0x180012719  lfence
0x18001271c  mov     rax, [rbx+0B28h]
0x180012723  lea     r13, [rbx+0AD0h]
0x18001272a  mov     rcx, [rbx+0B30h]
0x180012731  xor     r12d, r12d
0x180012734  movzx   eax, word ptr [rax+2]
0x180012738  mov     [rcx], ax
0x18001273b  mov     rax, [rbx+0B28h]
0x180012742  mov     rcx, [rbx+0B30h]
0x180012749  movzx   eax, word ptr [rax+r14*2]
0x18001274e  mov     [rcx+r14*2+2], ax
0x180012754  mov     rax, [rbx+0B30h]
0x18001275b  mov     rcx, [rbx+0B38h]
0x180012762  movzx   eax, word ptr [rax+2]
0x180012766  mov     [rcx], ax
0x180012769  mov     rax, [rbx+0B30h]
0x180012770  mov     rcx, [rbx+0B38h]
0x180012777  movzx   eax, word ptr [rax+r14*2]
0x18001277c  mov     [rcx+r14*2+2], ax
0x180012782  mov     rax, [rbx+0B38h]
0x180012789  mov     rcx, [rbx+0B40h]
0x180012790  movzx   eax, word ptr [rax+2]
0x180012794  mov     [rcx], ax
0x180012797  mov     rax, [rbx+0B38h]
0x18001279e  mov     rcx, [rbx+0B40h]
0x1800127a5  movzx   eax, word ptr [rax+r14*2]
0x1800127aa  mov     [rcx+r14*2+2], ax
0x1800127b0  mov     ecx, edi
0x1800127b2  lea     rax, [rbx+0B00h]
0x1800127b9  mov     [rsp+88h+arg_8], ecx
0x1800127c0  mov     [rsp+88h+var_48], rax
0x1800127c5  cmp     r12d, r14d
0x1800127c8  jl      loc_180012CAF
0x1800127ce  cmp     ecx, r14d
0x1800127d1  jl      loc_180012CFF
0x1800127d7  mov     rax, [rbx+0AC0h]
0x1800127de  mov     edx, r14d
0x1800127e1  mov     rcx, [rbx+0AC8h]
0x1800127e8  movzx   eax, word ptr [rax+2]
0x1800127ec  mov     [rcx], ax
0x1800127ef  mov     rax, [rbx+0AC0h]
0x1800127f6  mov     rcx, [rbx+0AC8h]
0x1800127fd  movzx   eax, word ptr [rax+r14*2]
0x180012802  mov     [rcx+r14*2+2], ax
0x180012808  mov     rax, [rbx+0AC8h]
0x18001280f  mov     rcx, [rbx+0AD0h]
0x180012816  movzx   eax, word ptr [rax+2]
0x18001281a  mov     [rcx], ax
0x18001281d  mov     rax, [rbx+0AC8h]
0x180012824  mov     rcx, [rbx+0AD0h]
0x18001282b  movzx   eax, word ptr [rax+r14*2]
0x180012830  mov     [rcx+r14*2+2], ax
0x180012836  mov     rax, [rbx+0AD0h]
0x18001283d  mov     rcx, [rbx+0AD8h]
0x180012844  movzx   eax, word ptr [rax+2]
0x180012848  mov     [rcx], ax
0x18001284b  mov     rax, [rbx+0AD0h]
0x180012852  mov     rcx, [rbx+0AD8h]
0x180012859  movzx   eax, word ptr [rax+r14*2]
0x18001285e  mov     [rcx+r14*2+2], ax
0x180012864  lea     rcx, [rbx+0AB8h]
0x18001286b  call    fuji_extend_green
0x180012870  xor     r11d, r11d
0x180012873  mov     [rsp+88h+var_54], edi
0x180012877  mov     ecx, edi
0x180012879  mov     [rsp+88h+var_50], r11d
0x18001287e  mov     r12d, r11d
0x180012881  mov     [rsp+88h+arg_8], ecx
0x180012888  lea     r13, [rbx+0B08h]
0x18001288f  lea     rax, [rbx+0B38h]
0x180012896  mov     [rsp+88h+var_48], rax
0x18001289b  cmp     r12d, r14d
0x18001289e  jl      loc_180012D76
0x1800128a4  cmp     ecx, r14d
0x1800128a7  jl      loc_180012DCE
0x1800128ad  lea     rcx, [rbx+0AB8h]
0x1800128b4  mov     edx, r14d
0x1800128b7  call    fuji_extend_green
0x1800128bc  lfence
0x1800128bf  mov     rax, [rbx+0B28h]
0x1800128c6  lea     r13, [rbx+0AD8h]
0x1800128cd  mov     rcx, [rbx+0B30h]
0x1800128d4  xor     r12d, r12d
0x1800128d7  movzx   eax, word ptr [rax+2]
0x1800128db  mov     [rcx], ax
0x1800128de  mov     rax, [rbx+0B28h]
0x1800128e5  mov     rcx, [rbx+0B30h]
0x1800128ec  movzx   eax, word ptr [rax+r14*2]
0x1800128f1  mov     [rcx+r14*2+2], ax
0x1800128f7  mov     rax, [rbx+0B30h]
0x1800128fe  mov     rcx, [rbx+0B38h]
0x180012905  movzx   eax, word ptr [rax+2]
0x180012909  mov     [rcx], ax
0x18001290c  mov     rax, [rbx+0B30h]
0x180012913  mov     rcx, [rbx+0B38h]
0x18001291a  movzx   eax, word ptr [rax+r14*2]
0x18001291f  mov     [rcx+r14*2+2], ax
0x180012925  mov     rax, [rbx+0B38h]
0x18001292c  mov     rcx, [rbx+0B40h]
0x180012933  movzx   eax, word ptr [rax+2]
0x180012937  mov     [rcx], ax
0x18001293a  mov     rax, [rbx+0B38h]
0x180012941  mov     rcx, [rbx+0B40h]
0x180012948  movzx   eax, word ptr [rax+r14*2]
0x18001294d  mov     [rcx+r14*2+2], ax
0x180012953  mov     ecx, edi
0x180012955  lea     rax, [rbx+0B10h]
0x18001295c  mov     [rsp+88h+arg_8], ecx
0x180012963  mov     [rsp+88h+var_48], rax
0x180012968  cmp     r12d, r14d
0x18001296b  jl      loc_180012E57
0x180012971  cmp     ecx, r14d
0x180012974  jl      loc_180012EA7
0x18001297a  mov     rax, [rbx+0AC0h]
0x180012981  mov     rdx, r14
0x180012984  mov     rcx, [rbx+0AC8h]
0x18001298b  movzx   eax, word ptr [rax+2]
0x18001298f  mov     [rcx], ax
0x180012992  mov     rax, [rbx+0AC0h]
0x180012999  mov     rcx, [rbx+0AC8h]
0x1800129a0  movzx   eax, word ptr [rax+r14*2]
0x1800129a5  mov     [rcx+r14*2+2], ax
0x1800129ab  mov     rax, [rbx+0AC8h]
0x1800129b2  mov     rcx, [rbx+0AD0h]
0x1800129b9  movzx   eax, word ptr [rax+2]
0x1800129bd  mov     [rcx], ax
0x1800129c0  mov     rax, [rbx+0AC8h]
0x1800129c7  mov     rcx, [rbx+0AD0h]
0x1800129ce  movzx   eax, word ptr [rax+r14*2]
0x1800129d3  mov     [rcx+r14*2+2], ax
0x1800129d9  mov     rax, [rbx+0AD0h]
0x1800129e0  mov     rcx, [rbx+0AD8h]
0x1800129e7  movzx   eax, word ptr [rax+2]
0x1800129eb  mov     [rcx], ax
0x1800129ee  mov     rax, [rbx+0AD0h]
0x1800129f5  mov     rcx, [rbx+0AD8h]
0x1800129fc  movzx   eax, word ptr [rax+r14*2]
0x180012a01  mov     [rcx+r14*2+2], ax
0x180012a07  lea     rcx, [rbx+0AB8h]
0x180012a0e  call    fuji_extend_green
0x180012a13  xor     r11d, r11d
0x180012a16  mov     [rsp+88h+var_50], edi
0x180012a1a  mov     [rsp+88h+arg_8], r11d
0x180012a22  lea     r12, [rbx+0B18h]
0x180012a29  lea     r13, [rbx+0B40h]
0x180012a30  cmp     r11d, r14d
0x180012a33  jl      loc_180012F1E
0x180012a39  cmp     edi, r14d
0x180012a3c  jl      loc_180012F84
0x180012a42  lea     rcx, [rbx+0AB8h]
0x180012a49  mov     edx, r14d
0x180012a4c  call    fuji_extend_green
0x180012a51  lfence
0x180012a54  mov     rax, [rbx+0B28h]
0x180012a5b  mov     rcx, [rbx+0B30h]
0x180012a62  movzx   eax, word ptr [rax+2]
0x180012a66  mov     [rcx], ax
0x180012a69  mov     rax, [rbx+0B28h]
0x180012a70  mov     rcx, [rbx+0B30h]
0x180012a77  movzx   eax, word ptr [rax+r14*2]
0x180012a7c  mov     [rcx+r14*2+2], ax
0x180012a82  mov     rax, [rbx+0B30h]
0x180012a89  mov     rcx, [rbx+0B38h]
0x180012a90  movzx   eax, word ptr [rax+2]
0x180012a94  mov     [rcx], ax
0x180012a97  mov     rax, [rbx+0B30h]
0x180012a9e  mov     rcx, [rbx+0B38h]
0x180012aa5  movzx   eax, word ptr [rax+r14*2]
0x180012aaa  mov     [rcx+r14*2+2], ax
0x180012ab0  mov     rax, [rbx+0B38h]
0x180012ab7  mov     rcx, [rbx+0B40h]
0x180012abe  movzx   eax, word ptr [rax+2]
0x180012ac2  mov     [rcx], ax
0x180012ac5  mov     rax, [rbx+0B38h]
0x180012acc  mov     rcx, [rbx+0B40h]
0x180012ad3  movzx   eax, word ptr [rax+r14*2]
0x180012ad8  mov     [rcx+r14*2+2], ax
0x180012ade  test    ebp, ebp
0x180012ae0  jz      short loc_180012AEF
0x180012ae2  mov     rcx, [rsp+88h+arg_0]; this
0x180012aea  call    ?derror@LibRaw@@IEAAXXZ; LibRaw::derror(void)
0x180012aef  mov     rbx, [rsp+88h+arg_18]
0x180012af7  add     rsp, 50h
0x180012afb  pop     r15
0x180012afd  pop     r14
0x180012aff  pop     r13
0x180012b01  pop     r12
0x180012b03  pop     rdi
0x180012b04  pop     rsi
0x180012b05  pop     rbp
0x180012b06  retn
0x180012b07  mov     r8, [r13+0]
0x180012b0b  lea     rsi, [rbx+30h]
0x180012b0f  add     r8, 2
0x180012b13  mov     [rsp+88h+var_68], rsi
0x180012b18  mov     r9d, r12d
0x180012b1b  mov     rdx, r15
0x180012b1e  mov     rcx, rbx
0x180012b21  call    fuji_decode_sample_even
0x180012b26  mov     r8, [rsp+88h+var_48]
0x180012b2b  mov     r9d, r12d
0x180012b2e  mov     rdx, r15
0x180012b31  mov     [rsp+88h+var_68], rsi
0x180012b36  mov     rcx, rbx
0x180012b39  add     ebp, eax
0x180012b3b  mov     r8, [r8]
0x180012b3e  add     r8, 2
0x180012b42  call    fuji_decode_sample_even
0x180012b47  mov     ecx, [rsp+88h+arg_8]
0x180012b4e  add     ebp, eax
0x180012b50  add     r12d, 2
0x180012b54  cmp     r12d, 8
0x180012b58  jle     short loc_180012BB8
0x180012b5a  mov     r8, [r13+0]
0x180012b5e  lea     rsi, [rbx+570h]
0x180012b65  mov     r9d, ecx
0x180012b68  mov     [rsp+88h+var_68], rsi
0x180012b6d  add     r8, 2
0x180012b71  mov     rdx, r15
0x180012b74  mov     rcx, rbx
0x180012b77  call    fuji_decode_sample_odd
0x180012b7c  mov     r9d, [rsp+88h+arg_8]
0x180012b84  add     ebp, eax
0x180012b86  mov     rax, [rsp+88h+var_48]
0x180012b8b  mov     rdx, r15
0x180012b8e  mov     rcx, rbx
  ... truncated ...
```
