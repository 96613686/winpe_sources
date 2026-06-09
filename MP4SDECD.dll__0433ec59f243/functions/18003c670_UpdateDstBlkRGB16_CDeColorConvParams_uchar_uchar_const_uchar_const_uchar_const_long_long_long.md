# UpdateDstBlkRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003c670`
- end: `0x18003d440`
- name: `?UpdateDstBlkRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `3536`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003c670`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB16(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  unsigned __int8 *v8; // r13
  const unsigned __int8 *v9; // r12
  const unsigned __int8 *v10; // rbp
  __int64 v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // r12d
  int v19; // ebp
  int v20; // r13d
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rax
  __int64 v24; // rdx
  int v25; // r14d
  int v26; // r15d
  int v27; // ebx
  int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // edi
  int v33; // r11d
  int v34; // esi
  int v35; // r8d
  int v36; // r9d
  int v37; // r8d
  __int64 v38; // rax
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rcx
  __int64 v42; // r13
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rcx
  int v46; // r8d
  int v47; // r9d
  int v48; // r10d
  bool v49; // zf
  const unsigned __int8 *v50; // r15
  __int64 v51; // rbp
  __int64 v52; // rdx
  __int64 v53; // rax
  int v54; // r8d
  int v55; // r9d
  __int64 v56; // rdx
  __int64 v57; // rax
  int v58; // r12d
  int v59; // r15d
  int v60; // r13d
  int v61; // r8d
  int v62; // r9d
  __int64 v63; // rax
  __int64 v64; // rdx
  int v65; // esi
  int v66; // ebp
  int v67; // r14d
  int v68; // r8d
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdx
  int v72; // r11d
  int v73; // ebx
  int v74; // edi
  int v75; // r8d
  int v76; // r9d
  int v77; // r8d
  __int64 v78; // rax
  int v79; // r8d
  int v80; // r9d
  __int64 v81; // r12
  int v82; // r8d
  int v83; // r9d
  int v84; // r8d
  __int64 v85; // rax
  int v86; // r9d
  unsigned __int32 v87; // r10d
  int v88; // [rsp+0h] [rbp-68h]
  int v89; // [rsp+0h] [rbp-68h]
  int v90; // [rsp+4h] [rbp-64h]
  int v91; // [rsp+4h] [rbp-64h]
  int v92; // [rsp+8h] [rbp-60h]
  int v93; // [rsp+8h] [rbp-60h]
  const unsigned __int8 *v94; // [rsp+10h] [rbp-58h]
  const unsigned __int8 *v95; // [rsp+10h] [rbp-58h]
  __int64 v96; // [rsp+18h] [rbp-50h]
  int v97; // [rsp+70h] [rbp+8h]
  unsigned __int8 *v98; // [rsp+78h] [rbp+10h]
  const unsigned __int8 *v99; // [rsp+80h] [rbp+18h]
  const unsigned __int8 *v100; // [rsp+88h] [rbp+20h]

  v100 = a4;
  v99 = a3;
  v98 = a2;
  v8 = a2;
  v9 = a3;
  v97 = 4;
  v96 = 2LL * a8;
  if ( *((_DWORD *)a1 + 26) == 7 )
  {
    v10 = a5;
    v11 = g_rgiClapTabDec;
    v94 = a5;
    do
    {
      v12 = *a4;
      v13 = *v10;
      v92 = g_iVtoG[v13] + g_iUtoG[v12];
      v90 = g_iVtoR[v13];
      v88 = g_iUtoB[v12];
      v14 = g_iYscale[v9[1]];
      v15 = g_iYscale[*v9];
      *(_DWORD *)v8 = ((unsigned int)(*(unsigned __int8 *)(v15 + v88 + v11)
                                    + (*(unsigned __int8 *)(v14 + v88 + v11) << 16)) >> 3)
                    & 0x1F001F
                    | ((*(unsigned __int8 *)(v14 - v92 + v11) << 18) + 4 * *(unsigned __int8 *)(v15 - v92 + v11))
                    & 0x3E003E0
                    | ((*(unsigned __int8 *)(v14 + v90 + v11) << 23) + (*(unsigned __int8 *)(v15 + v90 + v11) << 7))
                    & 0x7C007C00;
      v16 = v10[1];
      v17 = v100[1];
      v18 = g_iVtoR[v16];
      v19 = g_iVtoG[v16] + g_iUtoG[v17];
      v20 = g_iUtoB[v17];
      v21 = g_iYscale[v99[3]];
      v22 = g_iYscale[v99[2]];
      *((_DWORD *)v98 + 1) = ((unsigned int)(*(unsigned __int8 *)(v22 + v20 + v11)
                                           + (*(unsigned __int8 *)(v21 + v20 + v11) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v21 + v18 + v11) << 23)
                            + (*(unsigned __int8 *)(v22 + v18 + v11) << 7))
                           & 0x7C007C00
                           | ((*(unsigned __int8 *)(v21 - v19 + v11) << 18) + 4 * *(unsigned __int8 *)(v22 - v19 + v11))
                           & 0x3E003E0;
      v23 = v94[2];
      v24 = v100[2];
      v25 = g_iVtoR[v23];
      v26 = g_iUtoB[v24];
      v27 = g_iVtoG[v23] + g_iUtoG[v24];
      v28 = g_iYscale[v99[5]];
      v29 = v99[4];
      *((_DWORD *)v98 + 2) = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v29] + v26 + g_rgiClapTabDec)
                                           + (*(unsigned __int8 *)(v28 + v26 + g_rgiClapTabDec) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v28 + v25 + g_rgiClapTabDec) << 23)
                            + (*(unsigned __int8 *)(g_iYscale[v29] + v25 + g_rgiClapTabDec) << 7))
                           & 0x7C007C00
                           | ((*(unsigned __int8 *)(v28 - v27 + g_rgiClapTabDec) << 18)
                            + 4 * *(unsigned __int8 *)(g_iYscale[v29] - v27 + g_rgiClapTabDec))
                           & 0x3E003E0;
      v30 = v94[3];
      v31 = v100[3];
      v32 = g_iVtoR[v30];
      v33 = g_iVtoG[v30] + g_iUtoG[v31];
      v34 = g_iUtoB[v31];
      v35 = g_iYscale[v99[7]];
      v36 = g_iYscale[v99[6]];
      *((_DWORD *)v98 + 3) = ((unsigned int)(*(unsigned __int8 *)(v36 + v34 + g_rgiClapTabDec)
                                           + (*(unsigned __int8 *)(v35 + v34 + g_rgiClapTabDec) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v35 + v32 + g_rgiClapTabDec) << 23)
                            + (*(unsigned __int8 *)(v36 + v32 + g_rgiClapTabDec) << 7))
                           & 0x7C007C00
                           | ((*(unsigned __int8 *)(v35 - v33 + g_rgiClapTabDec) << 18)
                            + 4 * *(unsigned __int8 *)(v36 - v33 + g_rgiClapTabDec))
                           & 0x3E003E0;
      v100 += a7;
      v94 += a7;
      v37 = g_iYscale[v99[a6 + 1]];
      v38 = v99[a6];
      *(_DWORD *)&v98[a8] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v38] + v88 + g_rgiClapTabDec)
                                          + (*(unsigned __int8 *)(v37 + v88 + g_rgiClapTabDec) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v37 - v92 + g_rgiClapTabDec) << 18)
                           + 4 * *(unsigned __int8 *)(g_iYscale[v38] - v92 + g_rgiClapTabDec))
                          & 0x3E003E0
                          | ((*(unsigned __int8 *)(v37 + v90 + g_rgiClapTabDec) << 23)
                           + (*(unsigned __int8 *)(g_iYscale[v38] + v90 + g_rgiClapTabDec) << 7))
                          & 0x7C007C00;
      v39 = g_iYscale[v99[a6 + 3]];
      v40 = g_iYscale[v99[a6 + 2]];
      v41 = v39 + v20;
      LODWORD(v38) = v40 + v20;
      v42 = g_rgiClapTabDec;
      *(_DWORD *)&v98[a8 + 4] = ((unsigned int)(*(unsigned __int8 *)((int)v38 + g_rgiClapTabDec)
                                              + (*(unsigned __int8 *)(v41 + g_rgiClapTabDec) << 16)) >> 3)
                              & 0x1F001F
                              | ((*(unsigned __int8 *)(v39 + v18 + g_rgiClapTabDec) << 23)
                               + (*(unsigned __int8 *)(v40 + v18 + g_rgiClapTabDec) << 7))
                              & 0x7C007C00
                              | ((*(unsigned __int8 *)(v39 - v19 + g_rgiClapTabDec) << 18)
                               + 4 * *(unsigned __int8 *)(v40 - v19 + g_rgiClapTabDec))
                              & 0x3E003E0;
      v43 = g_iYscale[v99[a6 + 5]];
      v44 = g_iYscale[v99[a6 + 4]];
      LODWORD(v31) = *(unsigned __int8 *)(v43 + v26 + v42);
      v45 = v44 + v26;
      v11 = v42;
      *(_DWORD *)&v98[a8 + 8] = (((unsigned int)*(unsigned __int8 *)(v45 + v42) + ((_DWORD)v31 << 16)) >> 3) & 0x1F001F
                              | ((*(unsigned __int8 *)(v43 + v25 + v42) << 23)
                               + (*(unsigned __int8 *)(v44 + v25 + v42) << 7))
                              & 0x7C007C00
                              | ((*(unsigned __int8 *)(v43 - v27 + v42) << 18)
                               + 4 * *(unsigned __int8 *)(v44 - v27 + v42))
                              & 0x3E003E0;
      v46 = g_iYscale[v99[a6 + 7]];
      v47 = g_iYscale[v99[a6 + 6]];
      v9 = &v99[2 * a6];
      v10 = v94;
      v99 = v9;
      v48 = ((*(unsigned __int8 *)(v46 + v32 + v11) << 23) + (*(unsigned __int8 *)(v47 + v32 + v11) << 7)) & 0x7C007C00
          | ((*(unsigned __int8 *)(v46 - v33 + v11) << 18) + 4 * *(unsigned __int8 *)(v47 - v33 + v11)) & 0x3E003E0;
      LODWORD(v38) = v47 + v34;
      a4 = v100;
      v49 = v97-- == 1;
      *(_DWORD *)&v98[a8 + 12] = ((unsigned int)(*(unsigned __int8 *)((int)v38 + v42)
                                               + (*(unsigned __int8 *)(v46 + v34 + v42) << 16)) >> 3)
                               & 0x1F001F
                               | v48;
      v8 = &v98[2 * a8];
      v98 = v8;
    }
    while ( !v49 );
  }
  else
  {
    v50 = a5;
    v51 = g_rgiClapTabDec;
    v95 = a5;
    do
    {
      v52 = *a4;
      v53 = *v50;
      v91 = g_iVtoG[v53] + g_iUtoG[v52];
      v89 = g_iUtoB[v52];
      v93 = g_iVtoR[v53];
      v54 = g_iYscale[v9[1]];
      v55 = g_iYscale[*v9];
      *(_DWORD *)v8 = ((unsigned int)(*(unsigned __int8 *)(v55 + v89 + v51)
                                    + (*(unsigned __int8 *)(v54 + v89 + v51) << 16)) >> 3)
                    & 0x1F001F
                    | ((*(unsigned __int8 *)(v54 - v91 + v51) << 19) + 8 * *(unsigned __int8 *)(v55 - v91 + v51))
                    & 0x7E007E0
                    | ((*(unsigned __int8 *)(v55 + v93 + v51) << 8)
                     + _byteswap_ulong(*(unsigned __int8 *)(v54 + v93 + v51)))
                    & 0xF800F800;
      v56 = v100[1];
      v57 = v50[1];
      v58 = g_iVtoG[v57] + g_iUtoG[v56];
      v59 = g_iVtoR[v57];
      v60 = g_iUtoB[v56];
      v61 = g_iYscale[v99[3]];
      v62 = g_iYscale[v99[2]];
      *((_DWORD *)v98 + 1) = ((unsigned int)(*(unsigned __int8 *)(v62 + v60 + v51)
                                           + (*(unsigned __int8 *)(v61 + v60 + v51) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v61 - v58 + v51) << 19) + 8 * *(unsigned __int8 *)(v62 - v58 + v51))
                           & 0x7E007E0
                           | ((*(unsigned __int8 *)(v62 + v59 + v51) << 8)
                            + _byteswap_ulong(*(unsigned __int8 *)(v61 + v59 + v51)))
                           & 0xF800F800;
      v63 = v95[2];
      v64 = v100[2];
      v65 = g_iVtoR[v63];
      v66 = g_iVtoG[v63] + g_iUtoG[v64];
      v67 = g_iUtoB[v64];
      v68 = g_iYscale[v99[5]];
      v69 = v99[4];
      *((_DWORD *)v98 + 2) = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v69] + v67 + g_rgiClapTabDec)
                                           + (*(unsigned __int8 *)(v68 + v67 + g_rgiClapTabDec) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v68 - v66 + g_rgiClapTabDec) << 19)
                            + 8 * *(unsigned __int8 *)(g_iYscale[v69] - v66 + g_rgiClapTabDec))
                           & 0x7E007E0
                           | ((*(unsigned __int8 *)(g_iYscale[v69] + v65 + g_rgiClapTabDec) << 8)
                            + _byteswap_ulong(*(unsigned __int8 *)(v68 + v65 + g_rgiClapTabDec)))
                           & 0xF800F800;
      v70 = v95[3];
      v71 = v100[3];
      v72 = g_iVtoR[v70];
      v73 = g_iVtoG[v70] + g_iUtoG[v71];
      v74 = g_iUtoB[v71];
      v75 = g_iYscale[v99[7]];
      v76 = g_iYscale[v99[6]];
      *((_DWORD *)v98 + 3) = ((unsigned int)(*(unsigned __int8 *)(v76 + v74 + g_rgiClapTabDec)
                                           + (*(unsigned __int8 *)(v75 + v74 + g_rgiClapTabDec) << 16)) >> 3)
                           & 0x1F001F
                           | ((*(unsigned __int8 *)(v75 - v73 + g_rgiClapTabDec) << 19)
                            + 8 * *(unsigned __int8 *)(v76 - v73 + g_rgiClapTabDec))
                           & 0x7E007E0
                           | ((*(unsigned __int8 *)(v76 + v72 + g_rgiClapTabDec) << 8)
                            + _byteswap_ulong(*(unsigned __int8 *)(v75 + v72 + g_rgiClapTabDec)))
                           & 0xF800F800;
      v100 += a7;
      v95 += a7;
      v77 = g_iYscale[v99[a6 + 1]];
      v78 = v99[a6];
      *(_DWORD *)&v98[a8] = ((unsigned int)(*(unsigned __int8 *)(g_iYscale[v78] + v89 + g_rgiClapTabDec)
                                          + (*(unsigned __int8 *)(v77 + v89 + g_rgiClapTabDec) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v77 - v91 + g_rgiClapTabDec) << 19)
                           + 8 * *(unsigned __int8 *)(g_iYscale[v78] - v91 + g_rgiClapTabDec))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(g_iYscale[v78] + v93 + g_rgiClapTabDec) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v77 + v93 + g_rgiClapTabDec)))
                          & 0xF800F800;
      v79 = g_iYscale[v99[a6 + 3]];
      v80 = g_iYscale[v99[a6 + 2]];
      LODWORD(v71) = *(unsigned __int8 *)(v80 - v58 + g_rgiClapTabDec);
      LODWORD(v78) = v79 - v58;
      v81 = g_rgiClapTabDec;
      *(_DWORD *)&v98[a8 + 4] = ((unsigned int)(*(unsigned __int8 *)(v80 + v60 + g_rgiClapTabDec)
                                              + (*(unsigned __int8 *)(v79 + v60 + g_rgiClapTabDec) << 16)) >> 3)
                              & 0x1F001F
                              | ((*(unsigned __int8 *)((int)v78 + g_rgiClapTabDec) << 19) + 8 * v71) & 0x7E007E0
                              | ((*(unsigned __int8 *)(v80 + v59 + g_rgiClapTabDec) << 8)
                               + _byteswap_ulong(*(unsigned __int8 *)(v79 + v59 + g_rgiClapTabDec)))
                              & 0xF800F800;
      v82 = g_iYscale[v99[a6 + 5]];
      v83 = g_iYscale[v99[a6 + 4]];
      LODWORD(v71) = *(unsigned __int8 *)(v83 - v66 + v81);
      LODWORD(v78) = v82 - v66;
      v51 = v81;
      *(_DWORD *)&v98[a8 + 8] = ((unsigned int)(*(unsigned __int8 *)(v83 + v67 + v81)
                                              + (*(unsigned __int8 *)(v82 + v67 + v81) << 16)) >> 3)
                              & 0x1F001F
                              | ((*(unsigned __int8 *)((int)v78 + v81) << 19) + 8 * v71) & 0x7E007E0
                              | ((*(unsigned __int8 *)(v83 + v65 + v81) << 8)
                               + _byteswap_ulong(*(unsigned __int8 *)(v82 + v65 + v81)))
                              & 0xF800F800;
      v84 = g_iYscale[v99[a6 + 7]];
      v85 = v99[a6 + 6];
      v9 = &v99[2 * a6];
      v50 = v95;
      v99 = v9;
      v86 = g_iYscale[v85];
      v87 = ((*(unsigned __int8 *)(v84 - v73 + v51) << 19) + 8 * *(unsigned __int8 *)(v86 - v73 + v51)) & 0x7E007E0
          | ((*(unsigned __int8 *)(v86 + v72 + v51) << 8) + _byteswap_ulong(*(unsigned __int8 *)(v84 + v72 + v51)))
          & 0xF800F800;
      LODWORD(v85) = v86 + v74;
      a4 = v100;
      *(_DWORD *)&v98[a8 + 12] = ((unsigned int)(*(unsigned __int8 *)((int)v85 + v51)
                                               + (*(unsigned __int8 *)(v84 + v74 + v51) << 16)) >> 3)
                               & 0x1F001F
                               | v87;
      v8 = &v98[v96];
      v49 = v97-- == 1;
      v98 += v96;
    }
    while ( !v49 );
  }
}

```

## disassembly

```asm
0x18003c670  mov     [rsp+arg_18], r9
0x18003c675  mov     [rsp+arg_10], r8
0x18003c67a  mov     [rsp+arg_8], rdx
0x18003c67f  push    rbx
0x18003c680  push    rbp
0x18003c681  push    rsi
0x18003c682  push    rdi
0x18003c683  push    r12
0x18003c685  push    r13
0x18003c687  push    r14
0x18003c689  push    r15
0x18003c68b  sub     rsp, 28h
0x18003c68f  cmp     dword ptr [rcx+68h], 7
0x18003c693  mov     r13, rdx
0x18003c696  movsxd  rdx, [rsp+68h+arg_38]
0x18003c69e  mov     r12, r8
0x18003c6a1  mov     [rsp+68h+arg_0], 4
0x18003c6a9  lea     rax, [rdx+rdx]
0x18003c6ad  mov     [rsp+68h+var_50], rax
0x18003c6b2  jnz     loc_18003CD83
0x18003c6b8  mov     rbp, [rsp+68h+arg_20]
0x18003c6c0  lea     rsi, __ImageBase
0x18003c6c7  mov     r15, cs:g_rgiClapTabDec
0x18003c6ce  mov     r14d, 1F001Fh
0x18003c6d4  mov     [rsp+68h+var_58], rbp
0x18003c6d9  movzx   edx, byte ptr [r9]
0x18003c6dd  movzx   eax, byte ptr [rbp+0]
0x18003c6e1  mov     ebx, rva g_iUtoG[rsi+rdx*4]
0x18003c6e8  add     ebx, rva g_iVtoG[rsi+rax*4]
0x18003c6ef  mov     r11d, rva g_iVtoR[rsi+rax*4]
0x18003c6f7  mov     edi, rva g_iUtoB[rsi+rdx*4]
0x18003c6fe  movzx   eax, byte ptr [r12+1]
0x18003c704  mov     [rsp+68h+var_60], ebx
0x18003c708  mov     [rsp+68h+var_64], r11d
0x18003c70d  mov     [rsp+68h+var_68], edi
0x18003c710  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003c718  movzx   eax, byte ptr [r12]
0x18003c71d  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003c725  lea     eax, [r9+r11]
0x18003c729  movsxd  rcx, eax
0x18003c72c  lea     eax, [r8+r11]
0x18003c730  mov     r11, [rsp+68h+arg_10]
0x18003c738  movzx   r10d, byte ptr [rcx+r15]
0x18003c73d  movsxd  rcx, eax
0x18003c740  shl     r10d, 7
0x18003c744  movzx   eax, byte ptr [rcx+r15]
0x18003c749  shl     eax, 17h
0x18003c74c  add     r10d, eax
0x18003c74f  mov     eax, r9d
0x18003c752  sub     eax, ebx
0x18003c754  and     r10d, 7C007C00h
0x18003c75b  cdqe
0x18003c75d  movzx   edx, byte ptr [rax+r15]
0x18003c762  mov     eax, r8d
0x18003c765  sub     eax, ebx
0x18003c767  mov     rbx, [rsp+68h+arg_18]
0x18003c76f  cdqe
0x18003c771  movzx   ecx, byte ptr [rax+r15]
0x18003c776  shl     ecx, 12h
0x18003c779  lea     eax, [rcx+rdx*4]
0x18003c77c  and     eax, 3E003E0h
0x18003c781  or      r10d, eax
0x18003c784  lea     eax, [r8+rdi]
0x18003c788  movsxd  rcx, eax
0x18003c78b  lea     eax, [r9+rdi]
0x18003c78f  movzx   edx, byte ptr [rcx+r15]
0x18003c794  movsxd  rcx, eax
0x18003c797  shl     edx, 10h
0x18003c79a  movzx   eax, byte ptr [rcx+r15]
0x18003c79f  add     edx, eax
0x18003c7a1  shr     edx, 3
0x18003c7a4  and     edx, r14d
0x18003c7a7  or      r10d, edx
0x18003c7aa  mov     [r13+0], r10d
0x18003c7ae  movzx   eax, byte ptr [rbp+1]
0x18003c7b2  movzx   edx, byte ptr [rbx+1]
0x18003c7b6  mov     r12d, rva g_iVtoR[rsi+rax*4]
0x18003c7be  mov     ebp, rva g_iUtoG[rsi+rdx*4]
0x18003c7c5  add     ebp, rva g_iVtoG[rsi+rax*4]
0x18003c7cc  mov     r13d, rva g_iUtoB[rsi+rdx*4]
0x18003c7d4  movzx   eax, byte ptr [r11+3]
0x18003c7d9  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003c7e1  movzx   eax, byte ptr [r11+2]
0x18003c7e6  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003c7ee  mov     eax, r9d
0x18003c7f1  sub     eax, ebp
0x18003c7f3  cdqe
0x18003c7f5  movzx   edx, byte ptr [rax+r15]
0x18003c7fa  mov     eax, r8d
0x18003c7fd  sub     eax, ebp
0x18003c7ff  cdqe
0x18003c801  movzx   ecx, byte ptr [rax+r15]
0x18003c806  lea     eax, [r9+r12]
0x18003c80a  shl     ecx, 12h
0x18003c80d  lea     r10d, [rcx+rdx*4]
0x18003c811  movsxd  rcx, eax
0x18003c814  lea     eax, [r8+r12]
0x18003c818  and     r10d, 3E003E0h
0x18003c81f  movzx   edx, byte ptr [rcx+r15]
0x18003c824  shl     edx, 7
0x18003c827  movsxd  rcx, eax
0x18003c82a  movzx   eax, byte ptr [rcx+r15]
0x18003c82f  shl     eax, 17h
0x18003c832  add     edx, eax
0x18003c834  and     edx, 7C007C00h
0x18003c83a  or      r10d, edx
0x18003c83d  mov     rdi, [rsp+68h+arg_8]
0x18003c842  lea     eax, [r8+r13]
0x18003c846  movsxd  rcx, eax
0x18003c849  lea     eax, [r9+r13]
0x18003c84d  movzx   edx, byte ptr [rcx+r15]
0x18003c852  movsxd  rcx, eax
0x18003c855  shl     edx, 10h
0x18003c858  movzx   eax, byte ptr [rcx+r15]
0x18003c85d  add     edx, eax
0x18003c85f  mov     rax, [rsp+68h+var_58]
0x18003c864  shr     edx, 3
0x18003c867  and     edx, r14d
0x18003c86a  or      r10d, edx
0x18003c86d  mov     [rdi+4], r10d
0x18003c871  movzx   eax, byte ptr [rax+2]
0x18003c875  movzx   edx, byte ptr [rbx+2]
0x18003c879  mov     r14d, rva g_iVtoR[rsi+rax*4]
0x18003c881  mov     r15d, rva g_iUtoB[rsi+rdx*4]
0x18003c889  mov     ebx, rva g_iUtoG[rsi+rdx*4]
0x18003c890  add     ebx, rva g_iVtoG[rsi+rax*4]
0x18003c897  movzx   eax, byte ptr [r11+5]
0x18003c89c  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003c8a4  movzx   eax, byte ptr [r11+4]
0x18003c8a9  mov     r11, cs:g_rgiClapTabDec
0x18003c8b0  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003c8b8  mov     eax, r9d
0x18003c8bb  sub     eax, ebx
0x18003c8bd  cdqe
0x18003c8bf  movzx   edx, byte ptr [rax+r11]
0x18003c8c4  mov     eax, r8d
0x18003c8c7  sub     eax, ebx
0x18003c8c9  cdqe
0x18003c8cb  movzx   ecx, byte ptr [rax+r11]
0x18003c8d0  lea     eax, [r9+r14]
0x18003c8d4  shl     ecx, 12h
0x18003c8d7  lea     r10d, [rcx+rdx*4]
0x18003c8db  movsxd  rcx, eax
0x18003c8de  lea     eax, [r8+r14]
0x18003c8e2  and     r10d, 3E003E0h
0x18003c8e9  movzx   edx, byte ptr [rcx+r11]
0x18003c8ee  movsxd  rcx, eax
0x18003c8f1  shl     edx, 7
0x18003c8f4  movzx   eax, byte ptr [rcx+r11]
0x18003c8f9  shl     eax, 17h
0x18003c8fc  add     edx, eax
0x18003c8fe  lea     eax, [r8+r15]
0x18003c902  movsxd  rcx, eax
0x18003c905  and     edx, 7C007C00h
0x18003c90b  or      r10d, edx
0x18003c90e  lea     eax, [r9+r15]
0x18003c912  lea     r9, __ImageBase
0x18003c919  movzx   edx, byte ptr [rcx+r11]
0x18003c91e  movsxd  rcx, eax
0x18003c921  shl     edx, 10h
0x18003c924  movzx   eax, byte ptr [rcx+r11]
0x18003c929  mov     rcx, [rsp+68h+arg_18]
0x18003c931  add     edx, eax
0x18003c933  mov     rax, [rsp+68h+var_58]
0x18003c938  shr     edx, 3
0x18003c93b  and     edx, 1F001Fh
0x18003c941  or      r10d, edx
0x18003c944  mov     [rdi+8], r10d
0x18003c948  movzx   eax, byte ptr [rax+3]
0x18003c94c  movzx   edx, byte ptr [rcx+3]
0x18003c950  mov     rcx, [rsp+68h+arg_10]
0x18003c958  mov     edi, rva g_iVtoR[rsi+rax*4]
0x18003c95f  mov     r11d, rva g_iUtoG[rsi+rdx*4]
0x18003c967  add     r11d, rva g_iVtoG[rsi+rax*4]
0x18003c96f  movzx   eax, byte ptr [rcx+7]
0x18003c973  mov     esi, rva g_iUtoB[rsi+rdx*4]
0x18003c97a  mov     r8d, rva g_iYscale[r9+rax*4]
0x18003c982  movzx   eax, byte ptr [rcx+6]
0x18003c986  mov     rcx, cs:g_rgiClapTabDec
0x18003c98d  mov     r9d, rva g_iYscale[r9+rax*4]
0x18003c995  mov     eax, r9d
0x18003c998  sub     eax, r11d
0x18003c99b  cdqe
0x18003c99d  movzx   edx, byte ptr [rax+rcx]
0x18003c9a1  mov     eax, r8d
0x18003c9a4  sub     eax, r11d
0x18003c9a7  cdqe
0x18003c9a9  movzx   ecx, byte ptr [rax+rcx]
0x18003c9ad  lea     eax, [r9+rdi]
0x18003c9b1  shl     ecx, 12h
0x18003c9b4  lea     r10d, [rcx+rdx*4]
0x18003c9b8  movsxd  rcx, eax
0x18003c9bb  mov     rax, cs:g_rgiClapTabDec
0x18003c9c2  and     r10d, 3E003E0h
0x18003c9c9  movzx   edx, byte ptr [rcx+rax]
0x18003c9cd  lea     eax, [r8+rdi]
0x18003c9d1  movsxd  rcx, eax
0x18003c9d4  mov     rax, cs:g_rgiClapTabDec
0x18003c9db  shl     edx, 7
0x18003c9de  movzx   eax, byte ptr [rcx+rax]
0x18003c9e2  shl     eax, 17h
0x18003c9e5  add     edx, eax
0x18003c9e7  lea     eax, [r8+rsi]
0x18003c9eb  mov     r8, cs:g_rgiClapTabDec
0x18003c9f2  and     edx, 7C007C00h
0x18003c9f8  movsxd  rcx, eax
0x18003c9fb  or      r10d, edx
0x18003c9fe  lea     eax, [r9+rsi]
0x18003ca02  mov     r9, [rsp+68h+arg_10]
0x18003ca0a  movzx   edx, byte ptr [rcx+r8]
0x18003ca0f  movsxd  rcx, eax
0x18003ca12  shl     edx, 10h
0x18003ca15  movzx   eax, byte ptr [rcx+r8]
0x18003ca1a  lea     rcx, __ImageBase
0x18003ca21  add     edx, eax
0x18003ca23  mov     rax, [rsp+68h+arg_8]
0x18003ca28  shr     edx, 3
0x18003ca2b  and     edx, 1F001Fh
0x18003ca31  or      r10d, edx
0x18003ca34  movsxd  rdx, [rsp+68h+arg_28]
0x18003ca3c  mov     [rax+0Ch], r10d
0x18003ca40  movsxd  rax, [rsp+68h+arg_30]
0x18003ca48  add     [rsp+68h+arg_18], rax
0x18003ca50  add     [rsp+68h+var_58], rax
0x18003ca55  movzx   eax, byte ptr [rdx+r9+1]
0x18003ca5b  mov     r8d, rva g_iYscale[rcx+rax*4]
0x18003ca63  movzx   eax, byte ptr [rdx+r9]
0x18003ca68  mov     edx, [rsp+68h+var_64]
0x18003ca6c  mov     r9d, rva g_iYscale[rcx+rax*4]
0x18003ca74  lea     eax, [r9+rdx]
0x18003ca78  movsxd  rcx, eax
0x18003ca7b  mov     rax, cs:g_rgiClapTabDec
0x18003ca82  movzx   r10d, byte ptr [rcx+rax]
0x18003ca87  lea     eax, [r8+rdx]
0x18003ca8b  mov     rdx, cs:g_rgiClapTabDec
0x18003ca92  movsxd  rcx, eax
0x18003ca95  shl     r10d, 7
0x18003ca99  movzx   eax, byte ptr [rcx+rdx]
0x18003ca9d  mov     rcx, cs:g_rgiClapTabDec
0x18003caa4  shl     eax, 17h
0x18003caa7  add     r10d, eax
0x18003caaa  mov     eax, r9d
0x18003caad  sub     eax, [rsp+68h+var_60]
0x18003cab1  and     r10d, 7C007C00h
0x18003cab8  cdqe
0x18003caba  movzx   edx, byte ptr [rax+rdx]
0x18003cabe  mov     eax, r8d
0x18003cac1  sub     eax, [rsp+68h+var_60]
0x18003cac5  cdqe
0x18003cac7  movzx   ecx, byte ptr [rax+rcx]
0x18003cacb  shl     ecx, 12h
0x18003cace  lea     eax, [rcx+rdx*4]
0x18003cad1  and     eax, 3E003E0h
0x18003cad6  or      r10d, eax
0x18003cad9  mov     eax, [rsp+68h+var_68]
0x18003cadc  add     eax, r8d
0x18003cadf  mov     r8, cs:g_rgiClapTabDec
0x18003cae6  movsxd  rcx, eax
0x18003cae9  mov     eax, [rsp+68h+var_68]
0x18003caec  add     eax, r9d
0x18003caef  movzx   edx, byte ptr [rcx+r8]
0x18003caf4  shl     edx, 10h
0x18003caf7  movsxd  rcx, eax
0x18003cafa  movzx   eax, byte ptr [rcx+r8]
0x18003caff  add     edx, eax
0x18003cb01  shr     edx, 3
0x18003cb04  and     edx, 1F001Fh
0x18003cb0a  or      r10d, edx
0x18003cb0d  movsxd  rdx, [rsp+68h+arg_28]
0x18003cb15  mov     r9, [rsp+68h+arg_10]
0x18003cb1d  movsxd  rax, [rsp+68h+arg_38]
0x18003cb25  mov     rcx, [rsp+68h+arg_8]
0x18003cb2a  mov     [rax+rcx], r10d
0x18003cb2e  lea     rcx, __ImageBase
0x18003cb35  movzx   eax, byte ptr [rdx+r9+3]
0x18003cb3b  mov     r8d, rva g_iYscale[rcx+rax*4]
0x18003cb43  movzx   eax, byte ptr [rdx+r9+2]
0x18003cb49  mov     r9d, rva g_iYscale[rcx+rax*4]
0x18003cb51  mov     eax, r9d
0x18003cb54  mov     rcx, cs:g_rgiClapTabDec
0x18003cb5b  sub     eax, ebp
0x18003cb5d  cdqe
0x18003cb5f  movzx   edx, byte ptr [rax+rcx]
0x18003cb63  mov     eax, r8d
0x18003cb66  sub     eax, ebp
0x18003cb68  mov     rbp, rcx
0x18003cb6b  cdqe
0x18003cb6d  movzx   ecx, byte ptr [rax+rcx]
0x18003cb71  lea     eax, [r9+r12]
0x18003cb75  shl     ecx, 12h
0x18003cb78  lea     r10d, [rcx+rdx*4]
0x18003cb7c  movsxd  rcx, eax
0x18003cb7f  lea     eax, [r8+r12]
0x18003cb83  and     r10d, 3E003E0h
0x18003cb8a  lea     r12, __ImageBase
0x18003cb91  movzx   edx, byte ptr [rcx+rbp]
0x18003cb95  movsxd  rcx, eax
0x18003cb98  shl     edx, 7
0x18003cb9b  movzx   eax, byte ptr [rcx+rbp]
0x18003cb9f  shl     eax, 17h
  ... truncated ...
```
