# UpdateDst411MBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003a350`
- end: `0x18003aed4`
- name: `?UpdateDst411MBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `2948`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003baf0`

## callees

- `0x18003a350`

## pseudocode

```c
void __fastcall UpdateDst411MBRGB16(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  const unsigned __int8 *v8; // rax
  __int64 v10; // r14
  int v12; // r15d
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // ebx
  int v16; // edi
  int v17; // r11d
  int v18; // r8d
  int v19; // r9d
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // edi
  int v25; // ebx
  int v26; // r11d
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rax
  __int64 v32; // rdx
  int v33; // ebx
  int v34; // edi
  int v35; // r11d
  int v36; // r8d
  int v37; // r9d
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rax
  __int64 v41; // rdx
  int v42; // ebx
  int v43; // edi
  int v44; // r11d
  int v45; // r8d
  int v46; // r9d
  int v47; // r8d
  int v48; // r9d
  int v49; // r10d
  __int64 v50; // rax
  __int64 v51; // rdx
  int v52; // r11d
  int v53; // edi
  int v54; // ebx
  int v55; // r8d
  int v56; // r9d
  int v57; // r8d
  int v58; // r9d
  __int64 v59; // rdx
  __int64 v60; // rax
  int v61; // edi
  int v62; // r11d
  int v63; // ebx
  int v64; // r8d
  int v65; // r9d
  int v66; // r8d
  int v67; // r9d
  __int64 v68; // rax
  __int64 v69; // rdx
  int v70; // r11d
  int v71; // edi
  int v72; // ebx
  int v73; // r8d
  int v74; // r9d
  int v75; // r8d
  int v76; // r9d
  __int64 v77; // rax
  __int64 v78; // rdx
  int v79; // r11d
  int v80; // edi
  int v81; // ebx
  int v82; // r8d
  int v83; // r9d
  int v84; // r8d
  int v85; // r9d
  unsigned __int32 v86; // r10d
  const unsigned __int8 *v87; // [rsp+38h] [rbp+8h]
  const unsigned __int8 *v88; // [rsp+50h] [rbp+20h]

  v88 = a4;
  v8 = a5;
  v10 = g_rgiClapTabDec;
  v87 = a5;
  v12 = 16;
  if ( *((_DWORD *)a1 + 26) == 7 )
  {
    do
    {
      v13 = *v8;
      v14 = *a4;
      v15 = g_iVtoR[v13];
      v16 = g_iUtoB[v14];
      v17 = g_iVtoG[v13] + g_iUtoG[v14];
      v18 = g_iYscale[a3[1]];
      v19 = g_iYscale[*a3];
      *(_DWORD *)a2 = ((unsigned int)(*(unsigned __int8 *)(v19 + v16 + v10)
                                    + (*(unsigned __int8 *)(v18 + v16 + v10) << 16)) >> 3)
                    & 0x1F001F
                    | ((*(unsigned __int8 *)(v18 + v15 + v10) << 23) + (*(unsigned __int8 *)(v19 + v15 + v10) << 7))
                    & 0x7C007C00
                    | ((*(unsigned __int8 *)(v18 - v17 + v10) << 18) + 4 * *(unsigned __int8 *)(v19 - v17 + v10))
                    & 0x3E003E0;
      v20 = g_iYscale[a3[3]];
      v21 = g_iYscale[a3[2]];
      *((_DWORD *)a2 + 1) = ((unsigned int)(*(unsigned __int8 *)(v21 + v16 + v10)
                                          + (*(unsigned __int8 *)(v20 + v16 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v20 + v15 + v10) << 23) + (*(unsigned __int8 *)(v21 + v15 + v10) << 7))
                          & 0x7C007C00
                          | ((*(unsigned __int8 *)(v20 - v17 + v10) << 18) + 4 * *(unsigned __int8 *)(v21 - v17 + v10))
                          & 0x3E003E0;
      v22 = v88[1];
      v23 = v87[1];
      v24 = g_iUtoB[v22];
      v25 = g_iVtoR[v23];
      v26 = g_iVtoG[v23] + g_iUtoG[v22];
      v27 = g_iYscale[a3[5]];
      v28 = g_iYscale[a3[4]];
      *((_DWORD *)a2 + 2) = ((unsigned int)(*(unsigned __int8 *)(v28 + v24 + v10)
                                          + (*(unsigned __int8 *)(v27 + v24 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v27 + v25 + v10) << 23) + (*(unsigned __int8 *)(v28 + v25 + v10) << 7))
                          & 0x7C007C00
                          | ((*(unsigned __int8 *)(v27 - v26 + v10) << 18) + 4 * *(unsigned __int8 *)(v28 - v26 + v10))
                          & 0x3E003E0;
      v29 = g_iYscale[a3[7]];
      v30 = g_iYscale[a3[6]];
      *((_DWORD *)a2 + 3) = ((unsigned int)(*(unsigned __int8 *)(v30 + v24 + v10)
                                          + (*(unsigned __int8 *)(v29 + v24 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v29 + v25 + v10) << 23) + (*(unsigned __int8 *)(v30 + v25 + v10) << 7))
                          & 0x7C007C00
                          | ((*(unsigned __int8 *)(v29 - v26 + v10) << 18) + 4 * *(unsigned __int8 *)(v30 - v26 + v10))
                          & 0x3E003E0;
      v31 = v87[2];
      v32 = v88[2];
      v33 = g_iVtoR[v31];
      v34 = g_iUtoB[v32];
      v35 = g_iVtoG[v31] + g_iUtoG[v32];
      v36 = g_iYscale[a3[9]];
      v37 = g_iYscale[a3[8]];
      *((_DWORD *)a2 + 4) = ((unsigned int)(*(unsigned __int8 *)(v37 + v34 + v10)
                                          + (*(unsigned __int8 *)(v36 + v34 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v37 + v33 + v10) << 7) + (*(unsigned __int8 *)(v36 + v33 + v10) << 23))
                          & 0x7C007C00
                          | ((*(unsigned __int8 *)(v36 - v35 + v10) << 18) + 4 * *(unsigned __int8 *)(v37 - v35 + v10))
                          & 0x3E003E0;
      v38 = g_iYscale[a3[11]];
      v39 = g_iYscale[a3[10]];
      *((_DWORD *)a2 + 5) = ((unsigned int)(*(unsigned __int8 *)(v39 + v34 + v10)
                                          + (*(unsigned __int8 *)(v38 + v34 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v38 + v33 + v10) << 23) + (*(unsigned __int8 *)(v39 + v33 + v10) << 7))
                          & 0x7C007C00
                          | ((*(unsigned __int8 *)(v38 - v35 + v10) << 18) + 4 * *(unsigned __int8 *)(v39 - v35 + v10))
                          & 0x3E003E0;
      v40 = v87[3];
      v41 = v88[3];
      v42 = g_iVtoR[v40];
      v43 = g_iUtoB[v41];
      v44 = g_iVtoG[v40] + g_iUtoG[v41];
      v45 = g_iYscale[a3[13]];
      v46 = g_iYscale[a3[12]];
      *((_DWORD *)a2 + 6) = ((unsigned int)(*(unsigned __int8 *)(v43 + v46 + v10)
                                          + (*(unsigned __int8 *)(v43 + v45 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v45 - v44 + v10) << 18) + 4 * *(unsigned __int8 *)(v46 - v44 + v10))
                          & 0x3E003E0
                          | ((*(unsigned __int8 *)(v42 + v45 + v10) << 23) + (*(unsigned __int8 *)(v42 + v46 + v10) << 7))
                          & 0x7C007C00;
      v47 = g_iYscale[a3[15]];
      v48 = g_iYscale[a3[14]];
      v49 = ((*(unsigned __int8 *)(v42 + v47 + v10) << 23) + (*(unsigned __int8 *)(v42 + v48 + v10) << 7)) & 0x7C007C00
          | ((*(unsigned __int8 *)(v47 - v44 + v10) << 18) + 4 * *(unsigned __int8 *)(v48 - v44 + v10)) & 0x3E003E0;
      LODWORD(v40) = v43 + v48;
      a4 = &v88[a7];
      a3 += a6;
      LODWORD(v41) = ((unsigned int)(*(unsigned __int8 *)((int)v40 + v10) + (*(unsigned __int8 *)(v43 + v47 + v10) << 16)) >> 3)
                   & 0x1F001F;
      v8 = &v87[a7];
      v88 = a4;
      *((_DWORD *)a2 + 7) = v41 | v49;
      a2 += a8;
      v87 = v8;
      --v12;
    }
    while ( v12 );
  }
  else
  {
    do
    {
      v50 = *v8;
      v51 = *a4;
      v52 = g_iVtoR[v50];
      v53 = g_iUtoB[v51];
      v54 = g_iVtoG[v50] + g_iUtoG[v51];
      v55 = g_iYscale[a3[1]];
      v56 = g_iYscale[*a3];
      *(_DWORD *)a2 = ((unsigned int)(*(unsigned __int8 *)(v56 + v53 + v10)
                                    + (*(unsigned __int8 *)(v55 + v53 + v10) << 16)) >> 3)
                    & 0x1F001F
                    | ((*(unsigned __int8 *)(v55 - v54 + v10) << 19) + 8 * *(unsigned __int8 *)(v56 - v54 + v10))
                    & 0x7E007E0
                    | ((*(unsigned __int8 *)(v56 + v52 + v10) << 8)
                     + _byteswap_ulong(*(unsigned __int8 *)(v55 + v52 + v10)))
                    & 0xF800F800;
      v57 = g_iYscale[a3[3]];
      v58 = g_iYscale[a3[2]];
      *((_DWORD *)a2 + 1) = ((unsigned int)(*(unsigned __int8 *)(v58 + v53 + v10)
                                          + (*(unsigned __int8 *)(v57 + v53 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v57 - v54 + v10) << 19) + 8 * *(unsigned __int8 *)(v58 - v54 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v58 + v52 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v57 + v52 + v10)))
                          & 0xF800F800;
      v59 = v88[1];
      v60 = v87[1];
      v61 = g_iUtoB[v59];
      v62 = g_iVtoR[v60];
      v63 = g_iVtoG[v60] + g_iUtoG[v59];
      v64 = g_iYscale[a3[5]];
      v65 = g_iYscale[a3[4]];
      *((_DWORD *)a2 + 2) = ((unsigned int)(*(unsigned __int8 *)(v65 + v61 + v10)
                                          + (*(unsigned __int8 *)(v64 + v61 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v64 - v63 + v10) << 19) + 8 * *(unsigned __int8 *)(v65 - v63 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v65 + v62 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v64 + v62 + v10)))
                          & 0xF800F800;
      v66 = g_iYscale[a3[7]];
      v67 = g_iYscale[a3[6]];
      *((_DWORD *)a2 + 3) = ((unsigned int)(*(unsigned __int8 *)(v67 + v61 + v10)
                                          + (*(unsigned __int8 *)(v66 + v61 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v66 - v63 + v10) << 19) + 8 * *(unsigned __int8 *)(v67 - v63 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v67 + v62 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v66 + v62 + v10)))
                          & 0xF800F800;
      v68 = v87[2];
      v69 = v88[2];
      v70 = g_iVtoR[v68];
      v71 = g_iUtoB[v69];
      v72 = g_iVtoG[v68] + g_iUtoG[v69];
      v73 = g_iYscale[a3[9]];
      v74 = g_iYscale[a3[8]];
      *((_DWORD *)a2 + 4) = ((unsigned int)(*(unsigned __int8 *)(v74 + v71 + v10)
                                          + (*(unsigned __int8 *)(v73 + v71 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v73 - v72 + v10) << 19) + 8 * *(unsigned __int8 *)(v74 - v72 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v74 + v70 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v73 + v70 + v10)))
                          & 0xF800F800;
      v75 = g_iYscale[a3[11]];
      v76 = g_iYscale[a3[10]];
      *((_DWORD *)a2 + 5) = ((unsigned int)(*(unsigned __int8 *)(v76 + v71 + v10)
                                          + (*(unsigned __int8 *)(v75 + v71 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v75 - v72 + v10) << 19) + 8 * *(unsigned __int8 *)(v76 - v72 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v76 + v70 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v75 + v70 + v10)))
                          & 0xF800F800;
      v77 = v87[3];
      v78 = v88[3];
      v79 = g_iVtoR[v77];
      v80 = g_iUtoB[v78];
      v81 = g_iVtoG[v77] + g_iUtoG[v78];
      v82 = g_iYscale[a3[13]];
      v83 = g_iYscale[a3[12]];
      *((_DWORD *)a2 + 6) = ((unsigned int)(*(unsigned __int8 *)(v80 + v83 + v10)
                                          + (*(unsigned __int8 *)(v80 + v82 + v10) << 16)) >> 3)
                          & 0x1F001F
                          | ((*(unsigned __int8 *)(v82 - v81 + v10) << 19) + 8 * *(unsigned __int8 *)(v83 - v81 + v10))
                          & 0x7E007E0
                          | ((*(unsigned __int8 *)(v79 + v83 + v10) << 8)
                           + _byteswap_ulong(*(unsigned __int8 *)(v79 + v82 + v10)))
                          & 0xF800F800;
      v84 = g_iYscale[a3[15]];
      v85 = g_iYscale[a3[14]];
      v86 = ((*(unsigned __int8 *)(v84 - v81 + v10) << 19) + 8 * *(unsigned __int8 *)(v85 - v81 + v10)) & 0x7E007E0
          | ((*(unsigned __int8 *)(v79 + v85 + v10) << 8) + _byteswap_ulong(*(unsigned __int8 *)(v79 + v84 + v10)))
          & 0xF800F800;
      LODWORD(v77) = v80 + v85;
      a4 = &v88[a7];
      a3 += a6;
      LODWORD(v78) = ((unsigned int)(*(unsigned __int8 *)((int)v77 + v10) + (*(unsigned __int8 *)(v80 + v84 + v10) << 16)) >> 3)
                   & 0x1F001F;
      v8 = &v87[a7];
      v88 = a4;
      *((_DWORD *)a2 + 7) = v78 | v86;
      a2 += a8;
      v87 = v8;
      --v12;
    }
    while ( v12 );
  }
}

```

## disassembly

```asm
0x18003a350  mov     [rsp+arg_8], rbx
0x18003a355  mov     [rsp+arg_10], rbp
0x18003a35a  mov     [rsp+arg_18], r9
0x18003a35f  push    rsi
0x18003a360  push    rdi
0x18003a361  push    r12
0x18003a363  push    r13
0x18003a365  push    r14
0x18003a367  push    r15
0x18003a369  cmp     dword ptr [rcx+68h], 7
0x18003a36d  lea     rsi, __ImageBase
0x18003a374  mov     rax, [rsp+30h+arg_20]
0x18003a379  mov     r12, r8
0x18003a37c  mov     r14, cs:g_rgiClapTabDec
0x18003a383  mov     r13, rdx
0x18003a386  mov     [rsp+30h+arg_0], rax
0x18003a38b  mov     r15d, 10h
0x18003a391  mov     ebp, 1F001Fh
0x18003a396  jnz     loc_18003A93E
0x18003a39c  movzx   eax, byte ptr [rax]
0x18003a39f  movzx   edx, byte ptr [r9]
0x18003a3a3  mov     ebx, rva g_iVtoR[rsi+rax*4]
0x18003a3aa  mov     edi, rva g_iUtoB[rsi+rdx*4]
0x18003a3b1  mov     r11d, rva g_iUtoG[rsi+rdx*4]
0x18003a3b9  add     r11d, rva g_iVtoG[rsi+rax*4]
0x18003a3c1  movzx   eax, byte ptr [r12+1]
0x18003a3c7  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a3cf  movzx   eax, byte ptr [r12]
0x18003a3d4  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a3dc  mov     eax, r9d
0x18003a3df  sub     eax, r11d
0x18003a3e2  cdqe
0x18003a3e4  movzx   edx, byte ptr [rax+r14]
0x18003a3e9  mov     eax, r8d
0x18003a3ec  sub     eax, r11d
0x18003a3ef  cdqe
0x18003a3f1  movzx   ecx, byte ptr [rax+r14]
0x18003a3f6  lea     eax, [r9+rbx]
0x18003a3fa  shl     ecx, 12h
0x18003a3fd  lea     r10d, [rcx+rdx*4]
0x18003a401  movsxd  rcx, eax
0x18003a404  and     r10d, 3E003E0h
0x18003a40b  lea     eax, [r8+rbx]
0x18003a40f  movzx   edx, byte ptr [rcx+r14]
0x18003a414  movsxd  rcx, eax
0x18003a417  shl     edx, 7
0x18003a41a  movzx   eax, byte ptr [rcx+r14]
0x18003a41f  shl     eax, 17h
0x18003a422  add     edx, eax
0x18003a424  lea     eax, [r8+rdi]
0x18003a428  movsxd  rcx, eax
0x18003a42b  and     edx, 7C007C00h
0x18003a431  or      r10d, edx
0x18003a434  lea     eax, [r9+rdi]
0x18003a438  movzx   edx, byte ptr [rcx+r14]
0x18003a43d  movsxd  rcx, eax
0x18003a440  shl     edx, 10h
0x18003a443  movzx   eax, byte ptr [rcx+r14]
0x18003a448  add     edx, eax
0x18003a44a  shr     edx, 3
0x18003a44d  and     edx, ebp
0x18003a44f  or      r10d, edx
0x18003a452  mov     [r13+0], r10d
0x18003a456  movzx   eax, byte ptr [r12+3]
0x18003a45c  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a464  movzx   eax, byte ptr [r12+2]
0x18003a46a  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a472  mov     eax, r9d
0x18003a475  sub     eax, r11d
0x18003a478  cdqe
0x18003a47a  movzx   edx, byte ptr [rax+r14]
0x18003a47f  mov     eax, r8d
0x18003a482  sub     eax, r11d
0x18003a485  cdqe
0x18003a487  movzx   ecx, byte ptr [rax+r14]
0x18003a48c  lea     eax, [r9+rbx]
0x18003a490  shl     ecx, 12h
0x18003a493  lea     r10d, [rcx+rdx*4]
0x18003a497  movsxd  rcx, eax
0x18003a49a  lea     eax, [r8+rbx]
0x18003a49e  and     r10d, 3E003E0h
0x18003a4a5  movzx   edx, byte ptr [rcx+r14]
0x18003a4aa  shl     edx, 7
0x18003a4ad  movsxd  rcx, eax
0x18003a4b0  movzx   eax, byte ptr [rcx+r14]
0x18003a4b5  shl     eax, 17h
0x18003a4b8  add     edx, eax
0x18003a4ba  lea     eax, [r8+rdi]
0x18003a4be  and     edx, 7C007C00h
0x18003a4c4  movsxd  rcx, eax
0x18003a4c7  or      r10d, edx
0x18003a4ca  lea     eax, [r9+rdi]
0x18003a4ce  movzx   edx, byte ptr [rcx+r14]
0x18003a4d3  shl     edx, 10h
0x18003a4d6  movsxd  rcx, eax
0x18003a4d9  movzx   eax, byte ptr [rcx+r14]
0x18003a4de  add     edx, eax
0x18003a4e0  shr     edx, 3
0x18003a4e3  and     edx, ebp
0x18003a4e5  or      r10d, edx
0x18003a4e8  mov     rcx, [rsp+30h+arg_18]
0x18003a4ed  mov     rax, [rsp+30h+arg_0]
0x18003a4f2  mov     [r13+4], r10d
0x18003a4f6  movzx   edx, byte ptr [rcx+1]
0x18003a4fa  movzx   eax, byte ptr [rax+1]
0x18003a4fe  mov     edi, rva g_iUtoB[rsi+rdx*4]
0x18003a505  mov     ebx, rva g_iVtoR[rsi+rax*4]
0x18003a50c  mov     r11d, rva g_iUtoG[rsi+rdx*4]
0x18003a514  add     r11d, rva g_iVtoG[rsi+rax*4]
0x18003a51c  movzx   eax, byte ptr [r12+5]
0x18003a522  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a52a  movzx   eax, byte ptr [r12+4]
0x18003a530  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a538  mov     eax, r9d
0x18003a53b  sub     eax, r11d
0x18003a53e  cdqe
0x18003a540  movzx   edx, byte ptr [rax+r14]
0x18003a545  mov     eax, r8d
0x18003a548  sub     eax, r11d
0x18003a54b  cdqe
0x18003a54d  movzx   ecx, byte ptr [rax+r14]
0x18003a552  lea     eax, [r9+rbx]
0x18003a556  shl     ecx, 12h
0x18003a559  lea     r10d, [rcx+rdx*4]
0x18003a55d  movsxd  rcx, eax
0x18003a560  and     r10d, 3E003E0h
0x18003a567  lea     eax, [r8+rbx]
0x18003a56b  movzx   edx, byte ptr [rcx+r14]
0x18003a570  movsxd  rcx, eax
0x18003a573  shl     edx, 7
0x18003a576  movzx   eax, byte ptr [rcx+r14]
0x18003a57b  shl     eax, 17h
0x18003a57e  add     edx, eax
0x18003a580  lea     eax, [r8+rdi]
0x18003a584  movsxd  rcx, eax
0x18003a587  and     edx, 7C007C00h
0x18003a58d  or      r10d, edx
0x18003a590  lea     eax, [r9+rdi]
0x18003a594  movzx   edx, byte ptr [rcx+r14]
0x18003a599  movsxd  rcx, eax
0x18003a59c  shl     edx, 10h
0x18003a59f  movzx   eax, byte ptr [rcx+r14]
0x18003a5a4  add     edx, eax
0x18003a5a6  shr     edx, 3
0x18003a5a9  and     edx, ebp
0x18003a5ab  or      r10d, edx
0x18003a5ae  mov     [r13+8], r10d
0x18003a5b2  movzx   eax, byte ptr [r12+7]
0x18003a5b8  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a5c0  movzx   eax, byte ptr [r12+6]
0x18003a5c6  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a5ce  mov     eax, r9d
0x18003a5d1  sub     eax, r11d
0x18003a5d4  cdqe
0x18003a5d6  movzx   edx, byte ptr [rax+r14]
0x18003a5db  mov     eax, r8d
0x18003a5de  sub     eax, r11d
0x18003a5e1  cdqe
0x18003a5e3  movzx   ecx, byte ptr [rax+r14]
0x18003a5e8  lea     eax, [r9+rbx]
0x18003a5ec  shl     ecx, 12h
0x18003a5ef  lea     r10d, [rcx+rdx*4]
0x18003a5f3  movsxd  rcx, eax
0x18003a5f6  lea     eax, [r8+rbx]
0x18003a5fa  and     r10d, 3E003E0h
0x18003a601  movzx   edx, byte ptr [rcx+r14]
0x18003a606  movsxd  rcx, eax
0x18003a609  shl     edx, 7
0x18003a60c  movzx   eax, byte ptr [rcx+r14]
0x18003a611  shl     eax, 17h
0x18003a614  add     edx, eax
0x18003a616  lea     eax, [r8+rdi]
0x18003a61a  movsxd  rcx, eax
0x18003a61d  and     edx, 7C007C00h
0x18003a623  or      r10d, edx
0x18003a626  lea     eax, [r9+rdi]
0x18003a62a  movzx   edx, byte ptr [rcx+r14]
0x18003a62f  movsxd  rcx, eax
0x18003a632  shl     edx, 10h
0x18003a635  movzx   eax, byte ptr [rcx+r14]
0x18003a63a  add     edx, eax
0x18003a63c  mov     rcx, [rsp+30h+arg_18]
0x18003a641  mov     rax, [rsp+30h+arg_0]
0x18003a646  shr     edx, 3
0x18003a649  and     edx, ebp
0x18003a64b  or      r10d, edx
0x18003a64e  mov     [r13+0Ch], r10d
0x18003a652  movzx   eax, byte ptr [rax+2]
0x18003a656  movzx   edx, byte ptr [rcx+2]
0x18003a65a  mov     ebx, rva g_iVtoR[rsi+rax*4]
0x18003a661  mov     edi, rva g_iUtoB[rsi+rdx*4]
0x18003a668  mov     r11d, rva g_iUtoG[rsi+rdx*4]
0x18003a670  add     r11d, rva g_iVtoG[rsi+rax*4]
0x18003a678  movzx   eax, byte ptr [r12+9]
0x18003a67e  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a686  movzx   eax, byte ptr [r12+8]
0x18003a68c  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a694  mov     eax, r9d
0x18003a697  sub     eax, r11d
0x18003a69a  cdqe
0x18003a69c  movzx   edx, byte ptr [rax+r14]
0x18003a6a1  mov     eax, r8d
0x18003a6a4  sub     eax, r11d
0x18003a6a7  cdqe
0x18003a6a9  movzx   ecx, byte ptr [rax+r14]
0x18003a6ae  lea     eax, [r8+rbx]
0x18003a6b2  shl     ecx, 12h
0x18003a6b5  lea     r10d, [rcx+rdx*4]
0x18003a6b9  movsxd  rcx, eax
0x18003a6bc  and     r10d, 3E003E0h
0x18003a6c3  lea     eax, [r9+rbx]
0x18003a6c7  movzx   edx, byte ptr [rcx+r14]
0x18003a6cc  movsxd  rcx, eax
0x18003a6cf  shl     edx, 17h
0x18003a6d2  movzx   eax, byte ptr [rcx+r14]
0x18003a6d7  shl     eax, 7
0x18003a6da  add     edx, eax
0x18003a6dc  lea     eax, [r8+rdi]
0x18003a6e0  movsxd  rcx, eax
0x18003a6e3  and     edx, 7C007C00h
0x18003a6e9  or      r10d, edx
0x18003a6ec  lea     eax, [r9+rdi]
0x18003a6f0  movzx   edx, byte ptr [rcx+r14]
0x18003a6f5  movsxd  rcx, eax
0x18003a6f8  shl     edx, 10h
0x18003a6fb  movzx   eax, byte ptr [rcx+r14]
0x18003a700  add     edx, eax
0x18003a702  shr     edx, 3
0x18003a705  and     edx, ebp
0x18003a707  or      r10d, edx
0x18003a70a  mov     [r13+10h], r10d
0x18003a70e  movzx   eax, byte ptr [r12+0Bh]
0x18003a714  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a71c  movzx   eax, byte ptr [r12+0Ah]
0x18003a722  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a72a  mov     eax, r9d
0x18003a72d  sub     eax, r11d
0x18003a730  cdqe
0x18003a732  movzx   edx, byte ptr [rax+r14]
0x18003a737  mov     eax, r8d
0x18003a73a  sub     eax, r11d
0x18003a73d  cdqe
0x18003a73f  movzx   ecx, byte ptr [rax+r14]
0x18003a744  lea     eax, [r9+rbx]
0x18003a748  shl     ecx, 12h
0x18003a74b  lea     r10d, [rcx+rdx*4]
0x18003a74f  movsxd  rcx, eax
0x18003a752  lea     eax, [r8+rbx]
0x18003a756  and     r10d, 3E003E0h
0x18003a75d  movzx   edx, byte ptr [rcx+r14]
0x18003a762  movsxd  rcx, eax
0x18003a765  shl     edx, 7
0x18003a768  movzx   eax, byte ptr [rcx+r14]
0x18003a76d  shl     eax, 17h
0x18003a770  add     edx, eax
0x18003a772  lea     eax, [r8+rdi]
0x18003a776  and     edx, 7C007C00h
0x18003a77c  movsxd  rcx, eax
0x18003a77f  or      r10d, edx
0x18003a782  lea     eax, [r9+rdi]
0x18003a786  movzx   edx, byte ptr [rcx+r14]
0x18003a78b  shl     edx, 10h
0x18003a78e  movsxd  rcx, eax
0x18003a791  movzx   eax, byte ptr [rcx+r14]
0x18003a796  add     edx, eax
0x18003a798  mov     rcx, [rsp+30h+arg_18]
0x18003a79d  mov     rax, [rsp+30h+arg_0]
0x18003a7a2  shr     edx, 3
0x18003a7a5  and     edx, ebp
0x18003a7a7  or      r10d, edx
0x18003a7aa  mov     [r13+14h], r10d
0x18003a7ae  movzx   eax, byte ptr [rax+3]
0x18003a7b2  movzx   edx, byte ptr [rcx+3]
0x18003a7b6  mov     ebx, rva g_iVtoR[rsi+rax*4]
0x18003a7bd  mov     edi, rva g_iUtoB[rsi+rdx*4]
0x18003a7c4  mov     r11d, rva g_iUtoG[rsi+rdx*4]
0x18003a7cc  add     r11d, rva g_iVtoG[rsi+rax*4]
0x18003a7d4  movzx   eax, byte ptr [r12+0Dh]
0x18003a7da  mov     r8d, rva g_iYscale[rsi+rax*4]
0x18003a7e2  movzx   eax, byte ptr [r12+0Ch]
0x18003a7e8  mov     r9d, rva g_iYscale[rsi+rax*4]
0x18003a7f0  lea     eax, [rbx+r9]
0x18003a7f4  movsxd  rcx, eax
0x18003a7f7  lea     eax, [rbx+r8]
0x18003a7fb  movzx   r10d, byte ptr [rcx+r14]
0x18003a800  movsxd  rcx, eax
0x18003a803  shl     r10d, 7
0x18003a807  movzx   eax, byte ptr [rcx+r14]
0x18003a80c  shl     eax, 17h
0x18003a80f  add     r10d, eax
0x18003a812  mov     eax, r9d
0x18003a815  sub     eax, r11d
0x18003a818  and     r10d, 7C007C00h
0x18003a81f  cdqe
0x18003a821  movzx   edx, byte ptr [rax+r14]
0x18003a826  mov     eax, r8d
0x18003a829  sub     eax, r11d
0x18003a82c  cdqe
0x18003a82e  movzx   ecx, byte ptr [rax+r14]
0x18003a833  shl     ecx, 12h
  ... truncated ...
```
