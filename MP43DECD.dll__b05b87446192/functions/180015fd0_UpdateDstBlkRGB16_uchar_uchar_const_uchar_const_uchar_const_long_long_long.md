# UpdateDstBlkRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180015fd0`
- end: `0x180016daa`
- name: `?UpdateDstBlkRGB16@@YAXPEAEPEBE11JJJ@Z`
- size: `3546`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180015fd0`

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
0x180015fd0  mov     rax, rsp
0x180015fd3  mov     [rax+20h], r9
0x180015fd7  mov     [rax+18h], r8
0x180015fdb  mov     [rax+10h], rdx
0x180015fdf  mov     [rax+8], rcx
0x180015fe3  push    rbx
0x180015fe4  push    rbp
0x180015fe5  push    rsi
0x180015fe6  push    rdi
0x180015fe7  push    r12
0x180015fe9  push    r13
0x180015feb  push    r14
0x180015fed  push    r15
0x180015fef  sub     rsp, 28h
0x180015ff3  movsxd  rax, [rsp+68h+arg_20]
0x180015ffb  mov     r13, rcx
0x180015ffe  movsxd  rcx, [rsp+68h+arg_30]
0x180016006  add     rax, rax
0x180016009  cmp     cs:?g_redscale@@3JA, 7; long g_redscale
0x180016010  mov     r12, r9
0x180016013  mov     [rsp+68h+var_58], rax
0x180016018  mov     r15, rdx
0x18001601b  mov     [rsp+68h+var_68], 4
0x180016022  lea     rax, [rcx+rcx]
0x180016026  mov     [rsp+68h+var_50], rax
0x18001602b  jnz     loc_1800166F8
0x180016031  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016038  lea     rsi, __ImageBase
0x18001603f  mov     edi, 1F001Fh
0x180016044  movzx   edx, byte ptr [r8]
0x180016048  movzx   eax, byte ptr [r12]
0x18001604d  mov     ebx, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x180016054  mov     r11d, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x18001605c  mov     r12d, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x180016064  add     r12d, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x18001606c  movzx   eax, byte ptr [r15+1]
0x180016071  mov     [rsp+68h+var_60], ebx
0x180016075  mov     [rsp+68h+var_64], r11d
0x18001607a  mov     r8d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x180016082  movzx   eax, byte ptr [r15]
0x180016086  mov     r9d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x18001608e  mov     eax, r9d
0x180016091  sub     eax, r12d
0x180016094  cdqe
0x180016096  movzx   edx, byte ptr [rax+r14]
0x18001609b  mov     eax, r8d
0x18001609e  sub     eax, r12d
0x1800160a1  cdqe
0x1800160a3  movzx   ecx, byte ptr [rax+r14]
0x1800160a8  lea     eax, [r9+r11]
0x1800160ac  shl     ecx, 12h
0x1800160af  lea     r10d, [rcx+rdx*4]
0x1800160b3  movsxd  rcx, eax
0x1800160b6  lea     eax, [r8+r11]
0x1800160ba  and     r10d, 3E003E0h
0x1800160c1  movzx   edx, byte ptr [rcx+r14]
0x1800160c6  movsxd  rcx, eax
0x1800160c9  shl     edx, 7
0x1800160cc  movzx   eax, byte ptr [rcx+r14]
0x1800160d1  shl     eax, 17h
0x1800160d4  add     edx, eax
0x1800160d6  lea     eax, [r8+rbx]
0x1800160da  movsxd  rcx, eax
0x1800160dd  and     edx, 7C007C00h
0x1800160e3  or      r10d, edx
0x1800160e6  lea     eax, [r9+rbx]
0x1800160ea  mov     rbx, [rsp+68h+arg_18]
0x1800160f2  movzx   edx, byte ptr [rcx+r14]
0x1800160f7  movsxd  rcx, eax
0x1800160fa  shl     edx, 10h
0x1800160fd  movzx   eax, byte ptr [rcx+r14]
0x180016102  mov     rcx, [rsp+68h+arg_10]
0x18001610a  add     edx, eax
0x18001610c  shr     edx, 3
0x18001610f  and     edx, edi
0x180016111  or      r10d, edx
0x180016114  mov     [r13+0], r10d
0x180016118  movzx   edx, byte ptr [rcx+1]
0x18001611c  movzx   eax, byte ptr [rbx+1]
0x180016120  mov     ebp, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x180016127  add     ebp, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x18001612e  mov     r13d, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x180016136  mov     r11d, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x18001613e  movzx   eax, byte ptr [r15+3]
0x180016143  mov     [rsp+68h+var_5C], r11d
0x180016148  mov     r8d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x180016150  movzx   eax, byte ptr [r15+2]
0x180016155  mov     r9d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x18001615d  mov     eax, r9d
0x180016160  sub     eax, ebp
0x180016162  cdqe
0x180016164  movzx   edx, byte ptr [rax+r14]
0x180016169  mov     eax, r8d
0x18001616c  sub     eax, ebp
0x18001616e  cdqe
0x180016170  movzx   ecx, byte ptr [rax+r14]
0x180016175  lea     eax, [r9+r13]
0x180016179  shl     ecx, 12h
0x18001617c  lea     r10d, [rcx+rdx*4]
0x180016180  movsxd  rcx, eax
0x180016183  lea     eax, [r8+r13]
0x180016187  and     r10d, 3E003E0h
0x18001618e  movzx   edx, byte ptr [rcx+r14]
0x180016193  shl     edx, 7
0x180016196  movsxd  rcx, eax
0x180016199  movzx   eax, byte ptr [rcx+r14]
0x18001619e  shl     eax, 17h
0x1800161a1  add     edx, eax
0x1800161a3  and     edx, 7C007C00h
0x1800161a9  or      r10d, edx
0x1800161ac  lea     eax, [r8+r11]
0x1800161b0  movsxd  rcx, eax
0x1800161b3  lea     eax, [r9+r11]
0x1800161b7  mov     r11, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800161be  movzx   edx, byte ptr [rcx+r14]
0x1800161c3  movsxd  rcx, eax
0x1800161c6  shl     edx, 10h
0x1800161c9  movzx   eax, byte ptr [rcx+r14]
0x1800161ce  add     edx, eax
0x1800161d0  mov     rcx, [rsp+68h+arg_10]
0x1800161d8  mov     rax, [rsp+68h+arg_0]
0x1800161dd  shr     edx, 3
0x1800161e0  and     edx, edi
0x1800161e2  or      r10d, edx
0x1800161e5  mov     [rax+4], r10d
0x1800161e9  movzx   edx, byte ptr [rcx+2]
0x1800161ed  movzx   eax, byte ptr [rbx+2]
0x1800161f1  mov     rcx, [rsp+68h+arg_8]
0x1800161f6  mov     r15d, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x1800161fe  mov     r14d, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x180016206  mov     ebx, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x18001620d  add     ebx, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x180016214  movzx   eax, byte ptr [rcx+5]
0x180016218  mov     r8d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x180016220  movzx   eax, byte ptr [rcx+4]
0x180016224  mov     r9d, rva ?g_iYscale@@3PAJA[rsi+rax*4]; long near * g_iYscale ...
0x18001622c  mov     eax, r9d
0x18001622f  sub     eax, ebx
0x180016231  cdqe
0x180016233  movzx   edx, byte ptr [rax+r11]
0x180016238  mov     eax, r8d
0x18001623b  sub     eax, ebx
0x18001623d  cdqe
0x18001623f  movzx   ecx, byte ptr [rax+r11]
0x180016244  lea     eax, [r9+r14]
0x180016248  shl     ecx, 12h
0x18001624b  lea     r10d, [rcx+rdx*4]
0x18001624f  movsxd  rcx, eax
0x180016252  lea     eax, [r8+r14]
0x180016256  and     r10d, 3E003E0h
0x18001625d  movzx   edx, byte ptr [rcx+r11]
0x180016262  movsxd  rcx, eax
0x180016265  shl     edx, 7
0x180016268  movzx   eax, byte ptr [rcx+r11]
0x18001626d  shl     eax, 17h
0x180016270  add     edx, eax
0x180016272  lea     eax, [r8+r15]
0x180016276  movsxd  rcx, eax
0x180016279  and     edx, 7C007C00h
0x18001627f  or      r10d, edx
0x180016282  lea     eax, [r9+r15]
0x180016286  lea     r9, __ImageBase
0x18001628d  movzx   edx, byte ptr [rcx+r11]
0x180016292  movsxd  rcx, eax
0x180016295  shl     edx, 10h
0x180016298  movzx   eax, byte ptr [rcx+r11]
0x18001629d  mov     rcx, [rsp+68h+arg_10]
0x1800162a5  add     edx, eax
0x1800162a7  mov     rax, [rsp+68h+arg_0]
0x1800162ac  shr     edx, 3
0x1800162af  and     edx, edi
0x1800162b1  mov     rdi, [rsp+68h+arg_18]
0x1800162b9  or      r10d, edx
0x1800162bc  mov     [rax+8], r10d
0x1800162c0  movzx   edx, byte ptr [rcx+3]
0x1800162c4  movzx   eax, byte ptr [rdi+3]
0x1800162c8  mov     rcx, [rsp+68h+arg_8]
0x1800162cd  mov     r11d, rva ?g_iUtoG@@3PAJA[rsi+rdx*4]; long near * g_iUtoG ...
0x1800162d5  add     r11d, rva ?g_iVtoG@@3PAJA[rsi+rax*4]; long near * g_iVtoG ...
0x1800162dd  mov     edi, rva ?g_iVtoR@@3PAJA[rsi+rax*4]; long near * g_iVtoR ...
0x1800162e4  movzx   eax, byte ptr [rcx+7]
0x1800162e8  mov     esi, rva ?g_iUtoB@@3PAJA[rsi+rdx*4]; long near * g_iUtoB ...
0x1800162ef  mov     r8d, rva ?g_iYscale@@3PAJA[r9+rax*4]; long near * g_iYscale ...
0x1800162f7  movzx   eax, byte ptr [rcx+6]
0x1800162fb  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016302  mov     r9d, rva ?g_iYscale@@3PAJA[r9+rax*4]; long near * g_iYscale ...
0x18001630a  mov     eax, r9d
0x18001630d  sub     eax, r11d
0x180016310  cdqe
0x180016312  movzx   edx, byte ptr [rax+rcx]
0x180016316  mov     eax, r8d
0x180016319  sub     eax, r11d
0x18001631c  cdqe
0x18001631e  movzx   ecx, byte ptr [rax+rcx]
0x180016322  lea     eax, [r8+rdi]
0x180016326  shl     ecx, 12h
0x180016329  lea     r10d, [rcx+rdx*4]
0x18001632d  movsxd  rcx, eax
0x180016330  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016337  and     r10d, 3E003E0h
0x18001633e  movzx   edx, byte ptr [rcx+rax]
0x180016342  lea     eax, [r9+rdi]
0x180016346  movsxd  rcx, eax
0x180016349  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016350  shl     edx, 17h
0x180016353  movzx   eax, byte ptr [rcx+rax]
0x180016357  shl     eax, 7
0x18001635a  add     edx, eax
0x18001635c  lea     eax, [r8+rsi]
0x180016360  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016367  and     edx, 7C007C00h
0x18001636d  movsxd  rcx, eax
0x180016370  or      r10d, edx
0x180016373  lea     eax, [r9+rsi]
0x180016377  mov     r9, [rsp+68h+arg_8]
0x18001637c  movzx   edx, byte ptr [rcx+r8]
0x180016381  movsxd  rcx, eax
0x180016384  shl     edx, 10h
0x180016387  movzx   eax, byte ptr [rcx+r8]
0x18001638c  lea     rcx, __ImageBase
0x180016393  add     edx, eax
0x180016395  mov     rax, [rsp+68h+arg_0]
0x18001639a  shr     edx, 3
0x18001639d  and     edx, 1F001Fh
0x1800163a3  or      r10d, edx
0x1800163a6  movsxd  rdx, [rsp+68h+arg_20]
0x1800163ae  mov     [rax+0Ch], r10d
0x1800163b2  movsxd  rax, [rsp+68h+arg_28]
0x1800163ba  add     [rsp+68h+arg_10], rax
0x1800163c2  add     [rsp+68h+arg_18], rax
0x1800163ca  movzx   eax, byte ptr [rdx+r9+1]
0x1800163d0  mov     r8d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800163d8  movzx   eax, byte ptr [rdx+r9]
0x1800163dd  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800163e5  mov     eax, r9d
0x1800163e8  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800163ef  sub     eax, r12d
0x1800163f2  cdqe
0x1800163f4  movzx   edx, byte ptr [rax+rcx]
0x1800163f8  mov     eax, r8d
0x1800163fb  sub     eax, r12d
0x1800163fe  mov     r12d, [rsp+68h+var_64]
0x180016403  cdqe
0x180016405  movzx   ecx, byte ptr [rax+rcx]
0x180016409  lea     eax, [r9+r12]
0x18001640d  shl     ecx, 12h
0x180016410  lea     r10d, [rcx+rdx*4]
0x180016414  movsxd  rcx, eax
0x180016417  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001641e  and     r10d, 3E003E0h
0x180016425  movzx   edx, byte ptr [rcx+rax]
0x180016429  lea     eax, [r8+r12]
0x18001642d  mov     r12d, [rsp+68h+var_60]
0x180016432  movsxd  rcx, eax
0x180016435  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001643c  shl     edx, 7
0x18001643f  movzx   eax, byte ptr [rcx+rax]
0x180016443  shl     eax, 17h
0x180016446  add     edx, eax
0x180016448  lea     eax, [r8+r12]
0x18001644c  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016453  and     edx, 7C007C00h
0x180016459  or      r10d, edx
0x18001645c  movsxd  rcx, eax
0x18001645f  lea     eax, [r9+r12]
0x180016463  movzx   edx, byte ptr [rcx+r8]
0x180016468  shl     edx, 10h
0x18001646b  movsxd  rcx, eax
0x18001646e  movzx   eax, byte ptr [rcx+r8]
0x180016473  add     edx, eax
0x180016475  shr     edx, 3
0x180016478  and     edx, 1F001Fh
0x18001647e  movsxd  rax, [rsp+68h+arg_30]
0x180016486  lea     r12, __ImageBase
0x18001648d  mov     rcx, [rsp+68h+arg_0]
0x180016492  or      r10d, edx
0x180016495  mov     rdx, [rsp+68h+arg_8]
0x18001649a  mov     [rax+rcx], r10d
0x18001649e  movsxd  rcx, [rsp+68h+arg_20]
0x1800164a6  movzx   eax, byte ptr [rcx+rdx+3]
0x1800164ab  mov     r8d, rva ?g_iYscale@@3PAJA[r12+rax*4]; long near * g_iYscale ...
0x1800164b3  movzx   eax, byte ptr [rcx+rdx+2]
0x1800164b8  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800164bf  mov     r9d, rva ?g_iYscale@@3PAJA[r12+rax*4]; long near * g_iYscale ...
0x1800164c7  mov     eax, r9d
0x1800164ca  sub     eax, ebp
0x1800164cc  cdqe
0x1800164ce  movzx   edx, byte ptr [rax+rcx]
0x1800164d2  mov     eax, r8d
0x1800164d5  sub     eax, ebp
0x1800164d7  mov     rbp, rcx
0x1800164da  cdqe
0x1800164dc  movzx   ecx, byte ptr [rax+rcx]
0x1800164e0  lea     eax, [r9+r13]
0x1800164e4  shl     ecx, 12h
0x1800164e7  lea     r10d, [rcx+rdx*4]
0x1800164eb  movsxd  rcx, eax
0x1800164ee  lea     eax, [r8+r13]
0x1800164f2  and     r10d, 3E003E0h
0x1800164f9  mov     r13d, 1F001Fh
  ... truncated ...
```
