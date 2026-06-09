# UpdateDstBlkRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180016090`
- end: `0x180016e6a`
- name: `?UpdateDstBlkRGB16@@YAXPEAEPEBE11JJJ@Z`
- size: `3546`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180016090`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB16(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  unsigned __int8 *v7; // r13
  const unsigned __int8 *v8; // r12
  const unsigned __int8 *v9; // r15
  unsigned __int8 *v10; // r14
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r11d
  int v14; // r12d
  __int64 v15; // rax
  int v16; // r9d
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // ebp
  int v20; // r13d
  __int64 v21; // rax
  int v22; // r9d
  unsigned __int8 *v23; // r11
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // r15d
  int v27; // r14d
  int v28; // ebx
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rdx
  __int64 v32; // rax
  int v33; // edi
  int v34; // esi
  int v35; // r8d
  int v36; // r9d
  int v37; // r8d
  int v38; // r9d
  int v39; // r8d
  int v40; // r9d
  int v41; // r8d
  int v42; // r9d
  int v43; // r8d
  __int64 v44; // rax
  int v45; // r9d
  int v46; // r10d
  bool v47; // zf
  unsigned __int8 *v48; // rbp
  __int64 v49; // rdx
  __int64 v50; // rax
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rdx
  __int64 v54; // rax
  int v55; // r12d
  int v56; // r15d
  int v57; // r13d
  int v58; // r8d
  int v59; // r9d
  __int64 v60; // rdx
  __int64 v61; // rax
  int v62; // ebp
  int v63; // esi
  int v64; // r14d
  int v65; // r8d
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rax
  int v69; // ebx
  int v70; // r11d
  int v71; // edi
  int v72; // r8d
  int v73; // r9d
  int v74; // r8d
  __int64 v75; // rax
  int v76; // r8d
  int v77; // r9d
  unsigned __int8 *v78; // r12
  int v79; // r8d
  int v80; // r9d
  int v81; // r8d
  __int64 v82; // rax
  int v83; // r9d
  unsigned __int32 v84; // r10d
  int v85; // [rsp+0h] [rbp-68h]
  int v86; // [rsp+4h] [rbp-64h]
  int v87; // [rsp+4h] [rbp-64h]
  int v88; // [rsp+8h] [rbp-60h]
  int v89; // [rsp+8h] [rbp-60h]
  int v90; // [rsp+Ch] [rbp-5Ch]
  int v91; // [rsp+Ch] [rbp-5Ch]
  __int64 v92; // [rsp+10h] [rbp-58h]
  __int64 v93; // [rsp+18h] [rbp-50h]
  unsigned __int8 *v94; // [rsp+70h] [rbp+8h]
  const unsigned __int8 *v95; // [rsp+78h] [rbp+10h]
  const unsigned __int8 *v96; // [rsp+80h] [rbp+18h]
  const unsigned __int8 *v97; // [rsp+88h] [rbp+20h]

  v97 = a4;
  v96 = a3;
  v95 = a2;
  v94 = a1;
  v7 = a1;
  v8 = a4;
  v92 = 2LL * a5;
  v9 = a2;
  v85 = 4;
  v93 = 2LL * a7;
  if ( g_redscale == 7 )
  {
    v10 = g_rgiClapTabDec;
    do
    {
      v11 = *a3;
      v12 = *v8;
      v13 = *((_DWORD *)&g_iVtoR + v12);
      v14 = *((_DWORD *)&g_iVtoG + v12) + *((_DWORD *)&g_iUtoG + v11);
      v15 = v9[1];
      v88 = *((_DWORD *)&g_iUtoB + v11);
      v86 = v13;
      v16 = *((_DWORD *)&g_iYscale + *v9);
      *(_DWORD *)v7 = ((unsigned int)(v10[v16 + v88] + (v10[*((_DWORD *)&g_iYscale + v15) + v88] << 16)) >> 3)
                    & 0x1F001F
                    | ((v10[*((_DWORD *)&g_iYscale + v15) + v13] << 23) + (v10[v16 + v13] << 7)) & 0x7C007C00
                    | ((v10[*((_DWORD *)&g_iYscale + v15) - v14] << 18) + 4 * v10[v16 - v14]) & 0x3E003E0;
      v17 = v96[1];
      v18 = v97[1];
      v19 = *((_DWORD *)&g_iVtoG + v18) + *((_DWORD *)&g_iUtoG + v17);
      v20 = *((_DWORD *)&g_iVtoR + v18);
      v21 = v9[3];
      v90 = *((_DWORD *)&g_iUtoB + v17);
      v22 = *((_DWORD *)&g_iYscale + v9[2]);
      v23 = g_rgiClapTabDec;
      *((_DWORD *)v94 + 1) = ((unsigned int)(v10[v22 + v90] + (v10[*((_DWORD *)&g_iYscale + v21) + v90] << 16)) >> 3)
                           & 0x1F001F
                           | ((v10[*((_DWORD *)&g_iYscale + v21) + v20] << 23) + (v10[v22 + v20] << 7)) & 0x7C007C00
                           | ((v10[*((_DWORD *)&g_iYscale + v21) - v19] << 18) + 4 * v10[v22 - v19]) & 0x3E003E0;
      v24 = v96[2];
      v25 = v97[2];
      v26 = *((_DWORD *)&g_iUtoB + v24);
      v27 = *((_DWORD *)&g_iVtoR + v25);
      v28 = *((_DWORD *)&g_iVtoG + v25) + *((_DWORD *)&g_iUtoG + v24);
      v29 = *((_DWORD *)&g_iYscale + v95[5]);
      v30 = *((_DWORD *)&g_iYscale + v95[4]);
      *((_DWORD *)v94 + 2) = ((unsigned int)(v23[v30 + v26] + (v23[v29 + v26] << 16)) >> 3) & 0x1F001F
                           | ((v23[v29 + v27] << 23) + (v23[v30 + v27] << 7)) & 0x7C007C00
                           | ((v23[v29 - v28] << 18) + 4 * v23[v30 - v28]) & 0x3E003E0;
      v31 = v96[3];
      v32 = v97[3];
      LODWORD(v23) = *((_DWORD *)&g_iVtoG + v32) + *((_DWORD *)&g_iUtoG + v31);
      v33 = *((_DWORD *)&g_iVtoR + v32);
      v34 = *((_DWORD *)&g_iUtoB + v31);
      v35 = *((_DWORD *)&g_iYscale + v95[7]);
      v36 = *((_DWORD *)&g_iYscale + v95[6]);
      *((_DWORD *)v94 + 3) = ((unsigned int)(g_rgiClapTabDec[v36 + v34] + (g_rgiClapTabDec[v35 + v34] << 16)) >> 3)
                           & 0x1F001F
                           | ((g_rgiClapTabDec[v36 + v33] << 7) + (g_rgiClapTabDec[v35 + v33] << 23)) & 0x7C007C00
                           | ((g_rgiClapTabDec[v35 - (int)v23] << 18) + 4 * g_rgiClapTabDec[v36 - (int)v23]) & 0x3E003E0;
      v96 += a6;
      v97 += a6;
      v37 = *((_DWORD *)&g_iYscale + v95[a5 + 1]);
      v38 = *((_DWORD *)&g_iYscale + v95[a5]);
      *(_DWORD *)&v94[a7] = ((unsigned int)(g_rgiClapTabDec[v38 + v88] + (g_rgiClapTabDec[v37 + v88] << 16)) >> 3)
                          & 0x1F001F
                          | ((g_rgiClapTabDec[v37 + v86] << 23) + (g_rgiClapTabDec[v38 + v86] << 7)) & 0x7C007C00
                          | ((g_rgiClapTabDec[v37 - v14] << 18) + 4 * g_rgiClapTabDec[v38 - v14]) & 0x3E003E0;
      v39 = *((_DWORD *)&g_iYscale + v95[a5 + 3]);
      v40 = *((_DWORD *)&g_iYscale + v95[a5 + 2]);
      *(_DWORD *)&v94[a7 + 4] = ((unsigned int)(g_rgiClapTabDec[v40 + v90] + (g_rgiClapTabDec[v39 + v90] << 16)) >> 3)
                              & 0x1F001F
                              | ((g_rgiClapTabDec[v39 + v20] << 23) + (g_rgiClapTabDec[v40 + v20] << 7)) & 0x7C007C00
                              | ((g_rgiClapTabDec[v39 - v19] << 18) + 4 * g_rgiClapTabDec[v40 - v19]) & 0x3E003E0;
      v41 = *((_DWORD *)&g_iYscale + v95[a5 + 5]);
      v42 = *((_DWORD *)&g_iYscale + v95[a5 + 4]);
      LODWORD(v31) = g_rgiClapTabDec[v42 + v27];
      LODWORD(v32) = v41 + v27;
      v10 = g_rgiClapTabDec;
      *(_DWORD *)&v94[a7 + 8] = ((unsigned int)(g_rgiClapTabDec[v42 + v26] + (g_rgiClapTabDec[v41 + v26] << 16)) >> 3)
                              & 0x1F001F
                              | ((g_rgiClapTabDec[(int)v32] << 23) + ((_DWORD)v31 << 7)) & 0x7C007C00
                              | ((g_rgiClapTabDec[v41 - v28] << 18) + 4 * g_rgiClapTabDec[v42 - v28]) & 0x3E003E0;
      v43 = *((_DWORD *)&g_iYscale + v95[a5 + 7]);
      v44 = v95[a5 + 6];
      v9 = &v95[2 * a5];
      v95 = v9;
      v45 = *((_DWORD *)&g_iYscale + v44);
      v8 = v97;
      v46 = ((v10[v43 - (int)v23] << 18) + 4 * v10[v45 - (int)v23]) & 0x3E003E0;
      LODWORD(v31) = (v10[v45 + v33] << 7) + (v10[v43 + v33] << 23);
      LODWORD(v44) = v43 + v34;
      a3 = v96;
      v47 = v85-- == 1;
      *(_DWORD *)&v94[a7 + 12] = ((unsigned int)(v10[v45 + v34] + (v10[(int)v44] << 16)) >> 3) & 0x1F001F
                               | v31 & 0x7C007C00
                               | v46;
      v7 = &v94[2 * a7];
      v94 = v7;
    }
    while ( !v47 );
  }
  else
  {
    v48 = g_rgiClapTabDec;
    do
    {
      v49 = *a3;
      v50 = *v8;
      v89 = *((_DWORD *)&g_iVtoG + v50) + *((_DWORD *)&g_iUtoG + v49);
      v91 = *((_DWORD *)&g_iVtoR + v50);
      v87 = *((_DWORD *)&g_iUtoB + v49);
      v51 = *((_DWORD *)&g_iYscale + v9[1]);
      v52 = *((_DWORD *)&g_iYscale + *v9);
      *(_DWORD *)v7 = ((unsigned int)(v48[v52 + v87] + (v48[v51 + v87] << 16)) >> 3) & 0x1F001F
                    | ((v48[v51 - v89] << 19) + 8 * v48[v52 - v89]) & 0x7E007E0
                    | ((v48[v52 + v91] << 8) + _byteswap_ulong(v48[v51 + v91])) & 0xF800F800;
      v53 = v96[1];
      v54 = v8[1];
      v55 = *((_DWORD *)&g_iVtoG + v54) + *((_DWORD *)&g_iUtoG + v53);
      v56 = *((_DWORD *)&g_iVtoR + v54);
      v57 = *((_DWORD *)&g_iUtoB + v53);
      v58 = *((_DWORD *)&g_iYscale + v95[3]);
      v59 = *((_DWORD *)&g_iYscale + v95[2]);
      *((_DWORD *)v94 + 1) = ((unsigned int)(v48[v59 + v57] + (v48[v58 + v57] << 16)) >> 3) & 0x1F001F
                           | ((v48[v58 - v55] << 19) + 8 * v48[v59 - v55]) & 0x7E007E0
                           | ((v48[v59 + v56] << 8) + _byteswap_ulong(v48[v58 + v56])) & 0xF800F800;
      v60 = v96[2];
      v61 = v97[2];
      v62 = *((_DWORD *)&g_iVtoG + v61) + *((_DWORD *)&g_iUtoG + v60);
      v63 = *((_DWORD *)&g_iVtoR + v61);
      v64 = *((_DWORD *)&g_iUtoB + v60);
      v65 = *((_DWORD *)&g_iYscale + v95[5]);
      v66 = v95[4];
      *((_DWORD *)v94 + 2) = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v66) + v64]
                                           + (g_rgiClapTabDec[v65 + v64] << 16)) >> 3)
                           & 0x1F001F
                           | ((g_rgiClapTabDec[v65 - v62] << 19)
                            + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v66) - v62])
                           & 0x7E007E0
                           | ((g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v66) + v63] << 8)
                            + _byteswap_ulong(g_rgiClapTabDec[v65 + v63]))
                           & 0xF800F800;
      v67 = v96[3];
      v68 = v97[3];
      v69 = *((_DWORD *)&g_iVtoG + v68) + *((_DWORD *)&g_iUtoG + v67);
      v70 = *((_DWORD *)&g_iVtoR + v68);
      v71 = *((_DWORD *)&g_iUtoB + v67);
      v72 = *((_DWORD *)&g_iYscale + v95[7]);
      v73 = *((_DWORD *)&g_iYscale + v95[6]);
      *((_DWORD *)v94 + 3) = ((unsigned int)(g_rgiClapTabDec[v73 + v71] + (g_rgiClapTabDec[v72 + v71] << 16)) >> 3)
                           & 0x1F001F
                           | ((g_rgiClapTabDec[v72 - v69] << 19) + 8 * g_rgiClapTabDec[v73 - v69]) & 0x7E007E0
                           | ((g_rgiClapTabDec[v73 + v70] << 8) + _byteswap_ulong(g_rgiClapTabDec[v72 + v70]))
                           & 0xF800F800;
      v96 += a6;
      v97 += a6;
      v74 = *((_DWORD *)&g_iYscale + v95[a5 + 1]);
      v75 = v95[a5];
      *(_DWORD *)&v94[a7] = ((unsigned int)(g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v75) + v87]
                                          + (g_rgiClapTabDec[v74 + v87] << 16)) >> 3)
                          & 0x1F001F
                          | ((g_rgiClapTabDec[v74 - v89] << 19)
                           + 8 * g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v75) - v89])
                          & 0x7E007E0
                          | ((g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v75) + v91] << 8)
                           + _byteswap_ulong(g_rgiClapTabDec[v74 + v91]))
                          & 0xF800F800;
      v76 = *((_DWORD *)&g_iYscale + v95[a5 + 3]);
      v77 = *((_DWORD *)&g_iYscale + v95[a5 + 2]);
      LODWORD(v67) = g_rgiClapTabDec[v77 - v55];
      LODWORD(v75) = v76 - v55;
      v78 = g_rgiClapTabDec;
      *(_DWORD *)&v94[a7 + 4] = ((unsigned int)(g_rgiClapTabDec[v77 + v57] + (g_rgiClapTabDec[v76 + v57] << 16)) >> 3)
                              & 0x1F001F
                              | ((g_rgiClapTabDec[(int)v75] << 19) + 8 * v67) & 0x7E007E0
                              | ((g_rgiClapTabDec[v77 + v56] << 8) + _byteswap_ulong(g_rgiClapTabDec[v76 + v56]))
                              & 0xF800F800;
      v79 = *((_DWORD *)&g_iYscale + v95[a5 + 5]);
      v80 = *((_DWORD *)&g_iYscale + v95[a5 + 4]);
      LODWORD(v67) = v78[v80 - v62];
      LODWORD(v75) = v79 - v62;
      v48 = v78;
      *(_DWORD *)&v94[a7 + 8] = ((unsigned int)(v78[v80 + v64] + (v78[v79 + v64] << 16)) >> 3) & 0x1F001F
                              | ((v78[(int)v75] << 19) + 8 * v67) & 0x7E007E0
                              | ((v78[v80 + v63] << 8) + _byteswap_ulong(v78[v79 + v63])) & 0xF800F800;
      v81 = *((_DWORD *)&g_iYscale + v95[a5 + 7]);
      v82 = v95[a5 + 6];
      v9 = &v95[v92];
      v95 += v92;
      v83 = *((_DWORD *)&g_iYscale + v82);
      v84 = ((v48[v81 - v69] << 19) + 8 * v48[v83 - v69]) & 0x7E007E0
          | ((v48[v83 + v70] << 8) + _byteswap_ulong(v48[v81 + v70])) & 0xF800F800;
      LODWORD(v82) = v81 + v71;
      a3 = v96;
      *(_DWORD *)&v94[a7 + 12] = ((unsigned int)(v78[v83 + v71] + (v78[(int)v82] << 16)) >> 3) & 0x1F001F | v84;
      v7 = &v94[v93];
      v47 = v85-- == 1;
      v8 = v97;
      v94 += v93;
    }
    while ( !v47 );
  }
}

```

## disassembly

```asm
0x180016090  mov     rax, rsp
0x180016093  mov     [rax+20h], r9
0x180016097  mov     [rax+18h], r8
0x18001609b  mov     [rax+10h], rdx
0x18001609f  mov     [rax+8], rcx
0x1800160a3  push    rbx
0x1800160a4  push    rbp
0x1800160a5  push    rsi
0x1800160a6  push    rdi
0x1800160a7  push    r12
0x1800160a9  push    r13
0x1800160ab  push    r14
0x1800160ad  push    r15
0x1800160af  sub     rsp, 28h
0x1800160b3  movsxd  rax, [rsp+68h+arg_20]
0x1800160bb  mov     r13, rcx
0x1800160be  movsxd  rcx, [rsp+68h+arg_30]
0x1800160c6  add     rax, rax
0x1800160c9  cmp     cs:?g_redscale@@3JA, 7; long g_redscale
0x1800160d0  mov     r12, r9
0x1800160d3  mov     [rsp+68h+var_58], rax
0x1800160d8  mov     r15, rdx
0x1800160db  mov     [rsp+68h+var_68], 4
0x1800160e2  lea     rax, [rcx+rcx]
0x1800160e6  mov     [rsp+68h+var_50], rax
0x1800160eb  jnz     loc_1800167B8
0x1800160f1  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800160f8  lea     rsi, __ImageBase
0x1800160ff  mov     edi, 1F001Fh
0x180016104  movzx   edx, byte ptr [r8]
0x180016108  movzx   eax, byte ptr [r12]
0x18001610d  mov     ebx, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x180016114  mov     r11d, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x18001611c  mov     r12d, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x180016124  add     r12d, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x18001612c  movzx   eax, byte ptr [r15+1]
0x180016131  mov     [rsp+68h+var_60], ebx
0x180016135  mov     [rsp+68h+var_64], r11d
0x18001613a  mov     r8d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x180016142  movzx   eax, byte ptr [r15]
0x180016146  mov     r9d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x18001614e  mov     eax, r9d
0x180016151  sub     eax, r12d
0x180016154  cdqe
0x180016156  movzx   edx, byte ptr [rax+r14]
0x18001615b  mov     eax, r8d
0x18001615e  sub     eax, r12d
0x180016161  cdqe
0x180016163  movzx   ecx, byte ptr [rax+r14]
0x180016168  lea     eax, [r9+r11]
0x18001616c  shl     ecx, 12h
0x18001616f  lea     r10d, [rcx+rdx*4]
0x180016173  movsxd  rcx, eax
0x180016176  lea     eax, [r8+r11]
0x18001617a  and     r10d, 3E003E0h
0x180016181  movzx   edx, byte ptr [rcx+r14]
0x180016186  movsxd  rcx, eax
0x180016189  shl     edx, 7
0x18001618c  movzx   eax, byte ptr [rcx+r14]
0x180016191  shl     eax, 17h
0x180016194  add     edx, eax
0x180016196  lea     eax, [r8+rbx]
0x18001619a  movsxd  rcx, eax
0x18001619d  and     edx, 7C007C00h
0x1800161a3  or      r10d, edx
0x1800161a6  lea     eax, [r9+rbx]
0x1800161aa  mov     rbx, [rsp+68h+arg_18]
0x1800161b2  movzx   edx, byte ptr [rcx+r14]
0x1800161b7  movsxd  rcx, eax
0x1800161ba  shl     edx, 10h
0x1800161bd  movzx   eax, byte ptr [rcx+r14]
0x1800161c2  mov     rcx, [rsp+68h+arg_10]
0x1800161ca  add     edx, eax
0x1800161cc  shr     edx, 3
0x1800161cf  and     edx, edi
0x1800161d1  or      r10d, edx
0x1800161d4  mov     [r13+0], r10d
0x1800161d8  movzx   edx, byte ptr [rcx+1]
0x1800161dc  movzx   eax, byte ptr [rbx+1]
0x1800161e0  mov     ebp, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x1800161e7  add     ebp, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x1800161ee  mov     r13d, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x1800161f6  mov     r11d, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x1800161fe  movzx   eax, byte ptr [r15+3]
0x180016203  mov     [rsp+68h+var_5C], r11d
0x180016208  mov     r8d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x180016210  movzx   eax, byte ptr [r15+2]
0x180016215  mov     r9d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x18001621d  mov     eax, r9d
0x180016220  sub     eax, ebp
0x180016222  cdqe
0x180016224  movzx   edx, byte ptr [rax+r14]
0x180016229  mov     eax, r8d
0x18001622c  sub     eax, ebp
0x18001622e  cdqe
0x180016230  movzx   ecx, byte ptr [rax+r14]
0x180016235  lea     eax, [r9+r13]
0x180016239  shl     ecx, 12h
0x18001623c  lea     r10d, [rcx+rdx*4]
0x180016240  movsxd  rcx, eax
0x180016243  lea     eax, [r8+r13]
0x180016247  and     r10d, 3E003E0h
0x18001624e  movzx   edx, byte ptr [rcx+r14]
0x180016253  shl     edx, 7
0x180016256  movsxd  rcx, eax
0x180016259  movzx   eax, byte ptr [rcx+r14]
0x18001625e  shl     eax, 17h
0x180016261  add     edx, eax
0x180016263  and     edx, 7C007C00h
0x180016269  or      r10d, edx
0x18001626c  lea     eax, [r8+r11]
0x180016270  movsxd  rcx, eax
0x180016273  lea     eax, [r9+r11]
0x180016277  mov     r11, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001627e  movzx   edx, byte ptr [rcx+r14]
0x180016283  movsxd  rcx, eax
0x180016286  shl     edx, 10h
0x180016289  movzx   eax, byte ptr [rcx+r14]
0x18001628e  add     edx, eax
0x180016290  mov     rcx, [rsp+68h+arg_10]
0x180016298  mov     rax, [rsp+68h+arg_0]
0x18001629d  shr     edx, 3
0x1800162a0  and     edx, edi
0x1800162a2  or      r10d, edx
0x1800162a5  mov     [rax+4], r10d
0x1800162a9  movzx   edx, byte ptr [rcx+2]
0x1800162ad  movzx   eax, byte ptr [rbx+2]
0x1800162b1  mov     rcx, [rsp+68h+arg_8]
0x1800162b6  mov     r15d, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x1800162be  mov     r14d, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x1800162c6  mov     ebx, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x1800162cd  add     ebx, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x1800162d4  movzx   eax, byte ptr [rcx+5]
0x1800162d8  mov     r8d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x1800162e0  movzx   eax, byte ptr [rcx+4]
0x1800162e4  mov     r9d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x1800162ec  mov     eax, r9d
0x1800162ef  sub     eax, ebx
0x1800162f1  cdqe
0x1800162f3  movzx   edx, byte ptr [rax+r11]
0x1800162f8  mov     eax, r8d
0x1800162fb  sub     eax, ebx
0x1800162fd  cdqe
0x1800162ff  movzx   ecx, byte ptr [rax+r11]
0x180016304  lea     eax, [r9+r14]
0x180016308  shl     ecx, 12h
0x18001630b  lea     r10d, [rcx+rdx*4]
0x18001630f  movsxd  rcx, eax
0x180016312  lea     eax, [r8+r14]
0x180016316  and     r10d, 3E003E0h
0x18001631d  movzx   edx, byte ptr [rcx+r11]
0x180016322  movsxd  rcx, eax
0x180016325  shl     edx, 7
0x180016328  movzx   eax, byte ptr [rcx+r11]
0x18001632d  shl     eax, 17h
0x180016330  add     edx, eax
0x180016332  lea     eax, [r8+r15]
0x180016336  movsxd  rcx, eax
0x180016339  and     edx, 7C007C00h
0x18001633f  or      r10d, edx
0x180016342  lea     eax, [r9+r15]
0x180016346  lea     r9, __ImageBase
0x18001634d  movzx   edx, byte ptr [rcx+r11]
0x180016352  movsxd  rcx, eax
0x180016355  shl     edx, 10h
0x180016358  movzx   eax, byte ptr [rcx+r11]
0x18001635d  mov     rcx, [rsp+68h+arg_10]
0x180016365  add     edx, eax
0x180016367  mov     rax, [rsp+68h+arg_0]
0x18001636c  shr     edx, 3
0x18001636f  and     edx, edi
0x180016371  mov     rdi, [rsp+68h+arg_18]
0x180016379  or      r10d, edx
0x18001637c  mov     [rax+8], r10d
0x180016380  movzx   edx, byte ptr [rcx+3]
0x180016384  movzx   eax, byte ptr [rdi+3]
0x180016388  mov     rcx, [rsp+68h+arg_8]
0x18001638d  mov     r11d, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x180016395  add     r11d, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x18001639d  mov     edi, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x1800163a4  movzx   eax, byte ptr [rcx+7]
0x1800163a8  mov     esi, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x1800163af  mov     r8d, rva ?g_iYscale@@3PAJA[r9+rax*4]; long near * g_iYscale ...
0x1800163b7  movzx   eax, byte ptr [rcx+6]
0x1800163bb  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800163c2  mov     r9d, rva ?g_iYscale@@3PAJA[r9+rax*4]; long near * g_iYscale ...
0x1800163ca  mov     eax, r9d
0x1800163cd  sub     eax, r11d
0x1800163d0  cdqe
0x1800163d2  movzx   edx, byte ptr [rax+rcx]
0x1800163d6  mov     eax, r8d
0x1800163d9  sub     eax, r11d
0x1800163dc  cdqe
0x1800163de  movzx   ecx, byte ptr [rax+rcx]
0x1800163e2  lea     eax, [r8+rdi]
0x1800163e6  shl     ecx, 12h
0x1800163e9  lea     r10d, [rcx+rdx*4]
0x1800163ed  movsxd  rcx, eax
0x1800163f0  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800163f7  and     r10d, 3E003E0h
0x1800163fe  movzx   edx, byte ptr [rcx+rax]
0x180016402  lea     eax, [r9+rdi]
0x180016406  movsxd  rcx, eax
0x180016409  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016410  shl     edx, 17h
0x180016413  movzx   eax, byte ptr [rcx+rax]
0x180016417  shl     eax, 7
0x18001641a  add     edx, eax
0x18001641c  lea     eax, [r8+rsi]
0x180016420  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016427  and     edx, 7C007C00h
0x18001642d  movsxd  rcx, eax
0x180016430  or      r10d, edx
0x180016433  lea     eax, [r9+rsi]
0x180016437  mov     r9, [rsp+68h+arg_8]
0x18001643c  movzx   edx, byte ptr [rcx+r8]
0x180016441  movsxd  rcx, eax
0x180016444  shl     edx, 10h
0x180016447  movzx   eax, byte ptr [rcx+r8]
0x18001644c  lea     rcx, __ImageBase
0x180016453  add     edx, eax
0x180016455  mov     rax, [rsp+68h+arg_0]
0x18001645a  shr     edx, 3
0x18001645d  and     edx, 1F001Fh
0x180016463  or      r10d, edx
0x180016466  movsxd  rdx, [rsp+68h+arg_20]
0x18001646e  mov     [rax+0Ch], r10d
0x180016472  movsxd  rax, [rsp+68h+arg_28]
0x18001647a  add     [rsp+68h+arg_10], rax
0x180016482  add     [rsp+68h+arg_18], rax
0x18001648a  movzx   eax, byte ptr [rdx+r9+1]
0x180016490  mov     r8d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180016498  movzx   eax, byte ptr [rdx+r9]
0x18001649d  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800164a5  mov     eax, r9d
0x1800164a8  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800164af  sub     eax, r12d
0x1800164b2  cdqe
0x1800164b4  movzx   edx, byte ptr [rax+rcx]
0x1800164b8  mov     eax, r8d
0x1800164bb  sub     eax, r12d
0x1800164be  mov     r12d, [rsp+68h+var_64]
0x1800164c3  cdqe
0x1800164c5  movzx   ecx, byte ptr [rax+rcx]
0x1800164c9  lea     eax, [r9+r12]
0x1800164cd  shl     ecx, 12h
0x1800164d0  lea     r10d, [rcx+rdx*4]
0x1800164d4  movsxd  rcx, eax
0x1800164d7  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800164de  and     r10d, 3E003E0h
0x1800164e5  movzx   edx, byte ptr [rcx+rax]
0x1800164e9  lea     eax, [r8+r12]
0x1800164ed  mov     r12d, [rsp+68h+var_60]
0x1800164f2  movsxd  rcx, eax
0x1800164f5  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800164fc  shl     edx, 7
0x1800164ff  movzx   eax, byte ptr [rcx+rax]
0x180016503  shl     eax, 17h
0x180016506  add     edx, eax
0x180016508  lea     eax, [r8+r12]
0x18001650c  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016513  and     edx, 7C007C00h
0x180016519  or      r10d, edx
0x18001651c  movsxd  rcx, eax
0x18001651f  lea     eax, [r9+r12]
0x180016523  movzx   edx, byte ptr [rcx+r8]
0x180016528  shl     edx, 10h
0x18001652b  movsxd  rcx, eax
0x18001652e  movzx   eax, byte ptr [rcx+r8]
0x180016533  add     edx, eax
0x180016535  shr     edx, 3
0x180016538  and     edx, 1F001Fh
0x18001653e  movsxd  rax, [rsp+68h+arg_30]
0x180016546  lea     r12, __ImageBase
0x18001654d  mov     rcx, [rsp+68h+arg_0]
0x180016552  or      r10d, edx
0x180016555  mov     rdx, [rsp+68h+arg_8]
0x18001655a  mov     [rax+rcx], r10d
0x18001655e  movsxd  rcx, [rsp+68h+arg_20]
0x180016566  movzx   eax, byte ptr [rcx+rdx+3]
0x18001656b  mov     r8d, rva ?g_iYscale@@3PAJA[r12+rax*4]; long near * g_iYscale ...
0x180016573  movzx   eax, byte ptr [rcx+rdx+2]
0x180016578  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001657f  mov     r9d, rva ?g_iYscale@@3PAJA[r12+rax*4]; long near * g_iYscale ...
0x180016587  mov     eax, r9d
0x18001658a  sub     eax, ebp
0x18001658c  cdqe
0x18001658e  movzx   edx, byte ptr [rax+rcx]
0x180016592  mov     eax, r8d
0x180016595  sub     eax, ebp
0x180016597  mov     rbp, rcx
0x18001659a  cdqe
0x18001659c  movzx   ecx, byte ptr [rax+rcx]
0x1800165a0  lea     eax, [r9+r13]
0x1800165a4  shl     ecx, 12h
0x1800165a7  lea     r10d, [rcx+rdx*4]
0x1800165ab  movsxd  rcx, eax
0x1800165ae  lea     eax, [r8+r13]
0x1800165b2  and     r10d, 3E003E0h
0x1800165b9  mov     r13d, 1F001Fh
  ... truncated ...
```
