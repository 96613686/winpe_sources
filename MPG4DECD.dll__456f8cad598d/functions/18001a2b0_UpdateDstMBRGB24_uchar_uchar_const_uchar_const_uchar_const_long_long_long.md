# UpdateDstMBRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001a2b0`
- end: `0x18001afd6`
- name: `?UpdateDstMBRGB24@@YAXPEAEPEBE11JJJ@Z`
- size: `3366`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d7d0`

## callees

- `0x18001a2b0`

## pseudocode

```c
void __fastcall UpdateDstMBRGB24(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  unsigned __int8 *v7; // r14
  const unsigned __int8 *v8; // rbx
  const unsigned __int8 *v9; // rsi
  const unsigned __int8 *v10; // r11
  unsigned __int8 *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // r15d
  int v23; // r13d
  unsigned __int8 *v24; // r12
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // esi
  int v28; // r14d
  int v29; // ebp
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // edi
  int v33; // r11d
  int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rax
  int v37; // r8d
  int v38; // r10d
  int v39; // r9d
  unsigned __int8 *v40; // r12
  unsigned __int8 *v41; // r12
  unsigned __int8 *v42; // r12
  unsigned __int8 *v43; // r12
  unsigned __int8 *v44; // r12
  unsigned __int8 *v45; // r12
  unsigned __int8 *v46; // r12
  unsigned __int8 *v47; // r12
  unsigned __int8 *v48; // r15
  unsigned __int8 *v49; // r12
  unsigned __int8 *v50; // rcx
  const unsigned __int8 *v51; // rsi
  __int64 v52; // rax
  __int64 v53; // rax
  bool v54; // zf
  int v55; // [rsp+0h] [rbp-88h]
  int v56; // [rsp+4h] [rbp-84h]
  int v57; // [rsp+8h] [rbp-80h]
  int v58; // [rsp+Ch] [rbp-7Ch]
  int v59; // [rsp+10h] [rbp-78h]
  int v60; // [rsp+14h] [rbp-74h]
  int v61; // [rsp+18h] [rbp-70h]
  int v62; // [rsp+1Ch] [rbp-6Ch]
  int v63; // [rsp+20h] [rbp-68h]
  int v64; // [rsp+24h] [rbp-64h]
  int v65; // [rsp+28h] [rbp-60h]
  int v66; // [rsp+2Ch] [rbp-5Ch]
  int v67; // [rsp+30h] [rbp-58h]
  int v68; // [rsp+34h] [rbp-54h]
  unsigned __int8 *v69; // [rsp+90h] [rbp+8h]
  const unsigned __int8 *v70; // [rsp+98h] [rbp+10h]
  const unsigned __int8 *v71; // [rsp+A0h] [rbp+18h]
  const unsigned __int8 *v72; // [rsp+A8h] [rbp+20h]

  v72 = a4;
  v71 = a3;
  v70 = a2;
  v69 = a1;
  v7 = g_rgiClapTabDec;
  v8 = a4;
  v67 = 8;
  v9 = a3;
  v10 = a2;
  v11 = a1;
  do
  {
    v12 = *v9;
    v13 = *v8;
    v56 = *((_DWORD *)&g_iVtoG + v13) + *((_DWORD *)&g_iUtoG + v12);
    v55 = *((_DWORD *)&g_iVtoR + v13);
    v57 = *((_DWORD *)&g_iUtoB + v12);
    LODWORD(v12) = *((_DWORD *)&g_iYscale + *v10);
    v11[2] = v7[v55 + (int)v12];
    v11[1] = v7[(int)v12 - v56];
    *v11 = v7[(int)v12 + v57];
    LODWORD(v12) = *((_DWORD *)&g_iYscale + v10[1]);
    v11[5] = v7[v55 + (int)v12];
    v11[4] = v7[(int)v12 - v56];
    v11[3] = v7[(int)v12 + v57];
    v14 = v9[1];
    v15 = v8[1];
    v58 = *((_DWORD *)&g_iVtoR + v15);
    v59 = *((_DWORD *)&g_iVtoG + v15) + *((_DWORD *)&g_iUtoG + v14);
    v60 = *((_DWORD *)&g_iUtoB + v14);
    LODWORD(v14) = *((_DWORD *)&g_iYscale + v10[2]);
    v11[8] = v7[(int)v14 + v58];
    v11[7] = v7[(int)v14 - v59];
    v11[6] = v7[(int)v14 + v60];
    LODWORD(v14) = *((_DWORD *)&g_iYscale + v10[3]);
    v11[11] = v7[(int)v14 + v58];
    v11[10] = v7[(int)v14 - v59];
    v11[9] = v7[(int)v14 + v60];
    v16 = v8[2];
    v61 = *((_DWORD *)&g_iVtoR + v16);
    v17 = v9[2];
    v62 = *((_DWORD *)&g_iVtoG + v16) + *((_DWORD *)&g_iUtoG + v17);
    v63 = *((_DWORD *)&g_iUtoB + v17);
    LODWORD(v17) = *((_DWORD *)&g_iYscale + v10[4]);
    v11[14] = v7[(int)v17 + v61];
    v11[13] = v7[(int)v17 - v62];
    v11[12] = v7[(int)v17 + v63];
    LODWORD(v17) = *((_DWORD *)&g_iYscale + v10[5]);
    v11[17] = v7[(int)v17 + v61];
    v11[16] = v7[(int)v17 - v62];
    v11[15] = v7[(int)v17 + v63];
    v18 = v9[3];
    v19 = v8[3];
    v64 = *((_DWORD *)&g_iVtoR + v19);
    v65 = *((_DWORD *)&g_iVtoG + v19) + *((_DWORD *)&g_iUtoG + v18);
    v66 = *((_DWORD *)&g_iUtoB + v18);
    LODWORD(v18) = *((_DWORD *)&g_iYscale + v10[6]);
    v11[20] = v7[(int)v18 + v64];
    v11[19] = v7[(int)v18 - v65];
    v11[18] = v7[(int)v18 + v66];
    LODWORD(v18) = *((_DWORD *)&g_iYscale + v10[7]);
    v11[23] = v7[(int)v18 + v64];
    v11[22] = v7[(int)v18 - v65];
    v11[21] = v7[(int)v18 + v66];
    v20 = v9[4];
    v21 = v8[4];
    v22 = *((_DWORD *)&g_iVtoG + v21) + *((_DWORD *)&g_iUtoG + v20);
    v23 = *((_DWORD *)&g_iVtoR + v21);
    v68 = *((_DWORD *)&g_iUtoB + v20);
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v10[8]);
    v11[26] = v7[(int)v20 + v23];
    v11[25] = v7[(int)v20 - v22];
    v11[24] = v7[(int)v20 + v68];
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v10[9]);
    v11[29] = v7[(int)v20 + v23];
    v24 = g_rgiClapTabDec;
    v11[28] = v7[(int)v20 - v22];
    v11[27] = v7[(int)v20 + v68];
    v25 = v9[5];
    v26 = v8[5];
    v27 = *((_DWORD *)&g_iVtoG + v26) + *((_DWORD *)&g_iUtoG + v25);
    v28 = *((_DWORD *)&g_iVtoR + v26);
    v29 = *((_DWORD *)&g_iUtoB + v25);
    LODWORD(v25) = *((_DWORD *)&g_iYscale + v10[10]);
    v11[32] = v24[(int)v25 + v28];
    v11[31] = v24[(int)v25 - v27];
    v11[30] = v24[(int)v25 + v29];
    LODWORD(v25) = *((_DWORD *)&g_iYscale + v10[11]);
    v11[35] = v24[(int)v25 + v28];
    v11[34] = v24[(int)v25 - v27];
    v11[33] = v24[(int)v25 + v29];
    v30 = v8[6];
    v31 = v71[6];
    v32 = *((_DWORD *)&g_iVtoR + v30);
    v33 = *((_DWORD *)&g_iVtoG + v30) + *((_DWORD *)&g_iUtoG + v31);
    v34 = *((_DWORD *)&g_iUtoB + v31);
    LODWORD(v31) = *((_DWORD *)&g_iYscale + v70[12]);
    v69[38] = v24[(int)v31 + v32];
    v69[37] = v24[(int)v31 - v33];
    v69[36] = v24[(int)v31 + v34];
    LODWORD(v31) = *((_DWORD *)&g_iYscale + v70[13]);
    v69[41] = v24[(int)v31 + v32];
    v69[40] = v24[(int)v31 - v33];
    v69[39] = v24[(int)v31 + v34];
    v35 = v71[7];
    v36 = v72[7];
    v37 = *((_DWORD *)&g_iVtoG + v36) + *((_DWORD *)&g_iUtoG + v35);
    v38 = *((_DWORD *)&g_iVtoR + v36);
    v39 = *((_DWORD *)&g_iUtoB + v35);
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[14]);
    v69[44] = v24[(int)v35 + v38];
    v69[43] = v24[(int)v35 - v37];
    v69[42] = v24[(int)v35 + v39];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[15]);
    v69[47] = v24[(int)v35 + v38];
    v69[46] = v24[(int)v35 - v37];
    v69[45] = v24[(int)v35 + v39];
    v71 += a6;
    v72 += a6;
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5]);
    v69[a7 + 2] = v24[(int)v35 + v55];
    v69[a7 + 1] = g_rgiClapTabDec[(int)v35 - v56];
    v40 = g_rgiClapTabDec;
    v69[a7] = g_rgiClapTabDec[(int)v35 + v57];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 1]);
    v69[a7 + 5] = v40[(int)v35 + v55];
    v69[a7 + 4] = g_rgiClapTabDec[(int)v35 - v56];
    v41 = g_rgiClapTabDec;
    v69[a7 + 3] = g_rgiClapTabDec[(int)v35 + v57];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 2]);
    v69[a7 + 8] = v41[(int)v35 + v58];
    v69[a7 + 7] = g_rgiClapTabDec[(int)v35 - v59];
    v42 = g_rgiClapTabDec;
    v69[a7 + 6] = g_rgiClapTabDec[(int)v35 + v60];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 3]);
    v69[a7 + 11] = v42[(int)v35 + v58];
    v69[a7 + 10] = g_rgiClapTabDec[(int)v35 - v59];
    v43 = g_rgiClapTabDec;
    v69[a7 + 9] = g_rgiClapTabDec[(int)v35 + v60];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 4]);
    v69[a7 + 14] = v43[(int)v35 + v61];
    v69[a7 + 13] = g_rgiClapTabDec[(int)v35 - v62];
    v44 = g_rgiClapTabDec;
    v69[a7 + 12] = g_rgiClapTabDec[(int)v35 + v63];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 5]);
    v69[a7 + 17] = v44[(int)v35 + v61];
    v69[a7 + 16] = g_rgiClapTabDec[(int)v35 - v62];
    v45 = g_rgiClapTabDec;
    v69[a7 + 15] = g_rgiClapTabDec[(int)v35 + v63];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 6]);
    v69[a7 + 20] = v45[(int)v35 + v64];
    v69[a7 + 19] = g_rgiClapTabDec[(int)v35 - v65];
    v46 = g_rgiClapTabDec;
    v69[a7 + 18] = g_rgiClapTabDec[(int)v35 + v66];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 7]);
    v69[a7 + 23] = v46[(int)v35 + v64];
    v69[a7 + 22] = g_rgiClapTabDec[(int)v35 - v65];
    v47 = g_rgiClapTabDec;
    v69[a7 + 21] = g_rgiClapTabDec[(int)v35 + v66];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 8]);
    v69[a7 + 26] = v47[(int)v35 + v23];
    v69[a7 + 25] = g_rgiClapTabDec[(int)v35 - v22];
    v69[a7 + 24] = g_rgiClapTabDec[(int)v35 + v68];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 9]);
    v69[a7 + 29] = g_rgiClapTabDec[(int)v35 + v23];
    LODWORD(v36) = v35 - v22;
    v48 = g_rgiClapTabDec;
    v69[a7 + 28] = g_rgiClapTabDec[(int)v36];
    v49 = v69;
    v69[a7 + 27] = v48[(int)v35 + v68];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 10]);
    v50 = g_rgiClapTabDec;
    v69[a7 + 32] = g_rgiClapTabDec[(int)v35 + v28];
    v69[a7 + 31] = v50[(int)v35 - v27];
    v69[a7 + 30] = g_rgiClapTabDec[(int)v35 + v29];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 11]);
    LODWORD(v36) = v35 + v28;
    v7 = g_rgiClapTabDec;
    v69[a7 + 35] = g_rgiClapTabDec[(int)v36];
    LODWORD(v36) = v35 - v27;
    v51 = v70;
    v69[a7 + 34] = v7[(int)v36];
    v69[a7 + 33] = v7[(int)v35 + v29];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 12]);
    v69[a7 + 38] = v7[(int)v35 + v32];
    v69[a7 + 37] = v7[(int)v35 - v33];
    v69[a7 + 36] = v7[(int)v35 + v34];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 13]);
    v69[a7 + 41] = v7[(int)v35 + v32];
    v11 = &v69[2 * a7];
    v69 = v11;
    v52 = (int)v35 - v33;
    v10 = &v70[2 * a5];
    v70 = v10;
    LOBYTE(v50) = v7[v52];
    LODWORD(v52) = v35 + v34;
    v8 = v72;
    v49[a7 + 40] = (unsigned __int8)v50;
    v49[a7 + 39] = v7[(int)v52];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v51[a5 + 14]);
    v49[a7 + 44] = v7[(int)v35 + v38];
    v49[a7 + 43] = v7[(int)v35 - v37];
    v49[a7 + 42] = v7[(int)v35 + v39];
    v53 = v51[a5 + 15];
    v9 = v71;
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v53);
    v49[a7 + 47] = v7[(int)v35 + v38];
    v54 = v67-- == 1;
    v49[a7 + 46] = v7[(int)v35 - v37];
    v49[a7 + 45] = v7[(int)v35 + v39];
  }
  while ( !v54 );
}

```

## disassembly

```asm
0x18001a2b0  mov     rax, rsp
0x18001a2b3  mov     [rax+20h], r9
0x18001a2b7  mov     [rax+18h], r8
0x18001a2bb  mov     [rax+10h], rdx
0x18001a2bf  mov     [rax+8], rcx
0x18001a2c3  push    rbx
0x18001a2c4  push    rbp
0x18001a2c5  push    rsi
0x18001a2c6  push    rdi
0x18001a2c7  push    r12
0x18001a2c9  push    r13
0x18001a2cb  push    r14
0x18001a2cd  push    r15
0x18001a2cf  sub     rsp, 48h
0x18001a2d3  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001a2da  lea     rbp, __ImageBase
0x18001a2e1  mov     rbx, r9
0x18001a2e4  mov     [rsp+88h+var_58], 8
0x18001a2ec  mov     rsi, r8
0x18001a2ef  mov     r11, rdx
0x18001a2f2  mov     rdi, rcx
0x18001a2f5  movzx   edx, byte ptr [rsi]
0x18001a2f8  movzx   eax, byte ptr [rbx]
0x18001a2fb  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a303  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a30b  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a313  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a31b  movzx   eax, byte ptr [r11]
0x18001a31f  mov     [rsp+88h+var_84], r8d
0x18001a324  mov     [rsp+88h+var_88], r10d
0x18001a328  mov     [rsp+88h+var_80], r9d
0x18001a32d  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a334  lea     eax, [r10+rdx]
0x18001a338  movsxd  rcx, eax
0x18001a33b  mov     al, [rcx+r14]
0x18001a33f  mov     [rdi+2], al
0x18001a342  mov     eax, edx
0x18001a344  sub     eax, r8d
0x18001a347  cdqe
0x18001a349  mov     cl, [rax+r14]
0x18001a34d  lea     eax, [rdx+r9]
0x18001a351  mov     [rdi+1], cl
0x18001a354  movsxd  rcx, eax
0x18001a357  mov     al, [rcx+r14]
0x18001a35b  mov     [rdi], al
0x18001a35d  movzx   eax, byte ptr [r11+1]
0x18001a362  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a369  lea     eax, [r10+rdx]
0x18001a36d  movsxd  rcx, eax
0x18001a370  mov     al, [rcx+r14]
0x18001a374  mov     [rdi+5], al
0x18001a377  mov     eax, edx
0x18001a379  sub     eax, r8d
0x18001a37c  cdqe
0x18001a37e  mov     cl, [rax+r14]
0x18001a382  lea     eax, [rdx+r9]
0x18001a386  mov     [rdi+4], cl
0x18001a389  movsxd  rcx, eax
0x18001a38c  mov     al, [rcx+r14]
0x18001a390  mov     [rdi+3], al
0x18001a393  movzx   edx, byte ptr [rsi+1]
0x18001a397  movzx   eax, byte ptr [rbx+1]
0x18001a39b  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a3a3  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a3ab  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a3b3  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a3bb  movzx   eax, byte ptr [r11+2]
0x18001a3c0  mov     [rsp+88h+var_7C], r10d
0x18001a3c5  mov     [rsp+88h+var_78], r8d
0x18001a3ca  mov     [rsp+88h+var_74], r9d
0x18001a3cf  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a3d6  lea     eax, [rdx+r10]
0x18001a3da  movsxd  rcx, eax
0x18001a3dd  mov     al, [rcx+r14]
0x18001a3e1  mov     [rdi+8], al
0x18001a3e4  mov     eax, edx
0x18001a3e6  sub     eax, r8d
0x18001a3e9  cdqe
0x18001a3eb  mov     cl, [rax+r14]
0x18001a3ef  lea     eax, [rdx+r9]
0x18001a3f3  mov     [rdi+7], cl
0x18001a3f6  movsxd  rcx, eax
0x18001a3f9  mov     al, [rcx+r14]
0x18001a3fd  mov     [rdi+6], al
0x18001a400  movzx   eax, byte ptr [r11+3]
0x18001a405  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a40c  lea     eax, [rdx+r10]
0x18001a410  movsxd  rcx, eax
0x18001a413  mov     al, [rcx+r14]
0x18001a417  mov     [rdi+0Bh], al
0x18001a41a  mov     eax, edx
0x18001a41c  sub     eax, r8d
0x18001a41f  cdqe
0x18001a421  mov     cl, [rax+r14]
0x18001a425  lea     eax, [rdx+r9]
0x18001a429  mov     [rdi+0Ah], cl
0x18001a42c  movsxd  rcx, eax
0x18001a42f  mov     al, [rcx+r14]
0x18001a433  mov     [rdi+9], al
0x18001a436  movzx   eax, byte ptr [rbx+2]
0x18001a43a  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a442  mov     [rsp+88h+var_70], r10d
0x18001a447  movzx   edx, byte ptr [rsi+2]
0x18001a44b  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a453  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a45b  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a463  movzx   eax, byte ptr [r11+4]
0x18001a468  mov     [rsp+88h+var_6C], r8d
0x18001a46d  mov     [rsp+88h+var_68], r9d
0x18001a472  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a479  lea     eax, [rdx+r10]
0x18001a47d  movsxd  rcx, eax
0x18001a480  mov     al, [rcx+r14]
0x18001a484  mov     [rdi+0Eh], al
0x18001a487  mov     eax, edx
0x18001a489  sub     eax, r8d
0x18001a48c  cdqe
0x18001a48e  mov     cl, [rax+r14]
0x18001a492  lea     eax, [rdx+r9]
0x18001a496  mov     [rdi+0Dh], cl
0x18001a499  movsxd  rcx, eax
0x18001a49c  mov     al, [rcx+r14]
0x18001a4a0  mov     [rdi+0Ch], al
0x18001a4a3  movzx   eax, byte ptr [r11+5]
0x18001a4a8  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a4af  lea     eax, [rdx+r10]
0x18001a4b3  movsxd  rcx, eax
0x18001a4b6  mov     al, [rcx+r14]
0x18001a4ba  mov     [rdi+11h], al
0x18001a4bd  mov     eax, edx
0x18001a4bf  sub     eax, r8d
0x18001a4c2  cdqe
0x18001a4c4  mov     cl, [rax+r14]
0x18001a4c8  lea     eax, [rdx+r9]
0x18001a4cc  mov     [rdi+10h], cl
0x18001a4cf  movsxd  rcx, eax
0x18001a4d2  mov     al, [rcx+r14]
0x18001a4d6  mov     [rdi+0Fh], al
0x18001a4d9  movzx   edx, byte ptr [rsi+3]
0x18001a4dd  movzx   eax, byte ptr [rbx+3]
0x18001a4e1  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a4e9  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a4f1  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a4f9  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a501  movzx   eax, byte ptr [r11+6]
0x18001a506  mov     [rsp+88h+var_64], r10d
0x18001a50b  mov     [rsp+88h+var_60], r8d
0x18001a510  mov     [rsp+88h+var_5C], r9d
0x18001a515  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a51c  lea     eax, [rdx+r10]
0x18001a520  movsxd  rcx, eax
0x18001a523  mov     al, [rcx+r14]
0x18001a527  mov     [rdi+14h], al
0x18001a52a  mov     eax, edx
0x18001a52c  sub     eax, r8d
0x18001a52f  cdqe
0x18001a531  mov     cl, [rax+r14]
0x18001a535  lea     eax, [rdx+r9]
0x18001a539  mov     [rdi+13h], cl
0x18001a53c  movsxd  rcx, eax
0x18001a53f  mov     al, [rcx+r14]
0x18001a543  mov     [rdi+12h], al
0x18001a546  movzx   eax, byte ptr [r11+7]
0x18001a54b  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a552  lea     eax, [rdx+r10]
0x18001a556  movsxd  rcx, eax
0x18001a559  mov     al, [rcx+r14]
0x18001a55d  mov     [rdi+17h], al
0x18001a560  mov     eax, edx
0x18001a562  sub     eax, r8d
0x18001a565  cdqe
0x18001a567  mov     cl, [rax+r14]
0x18001a56b  lea     eax, [rdx+r9]
0x18001a56f  mov     [rdi+16h], cl
0x18001a572  movsxd  rcx, eax
0x18001a575  mov     al, [rcx+r14]
0x18001a579  mov     [rdi+15h], al
0x18001a57c  movzx   edx, byte ptr [rsi+4]
0x18001a580  movzx   eax, byte ptr [rbx+4]
0x18001a584  mov     r15d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a58c  add     r15d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a594  mov     r13d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a59c  mov     r12d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a5a4  movzx   eax, byte ptr [r11+8]
0x18001a5a9  lea     r10, __ImageBase
0x18001a5b0  mov     r9, [rsp+88h+arg_8]
0x18001a5b8  mov     [rsp+88h+var_54], r12d
0x18001a5bd  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a5c4  lea     eax, [rdx+r13]
0x18001a5c8  movsxd  rcx, eax
0x18001a5cb  mov     al, [rcx+r14]
0x18001a5cf  mov     [rdi+1Ah], al
0x18001a5d2  mov     eax, edx
0x18001a5d4  sub     eax, r15d
0x18001a5d7  cdqe
0x18001a5d9  mov     cl, [rax+r14]
0x18001a5dd  lea     eax, [rdx+r12]
0x18001a5e1  mov     [rdi+19h], cl
0x18001a5e4  movsxd  rcx, eax
0x18001a5e7  mov     al, [rcx+r14]
0x18001a5eb  mov     [rdi+18h], al
0x18001a5ee  movzx   eax, byte ptr [r11+9]
0x18001a5f3  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a5fa  lea     eax, [rdx+r13]
0x18001a5fe  movsxd  rcx, eax
0x18001a601  mov     al, [rcx+r14]
0x18001a605  mov     [rdi+1Dh], al
0x18001a608  mov     eax, edx
0x18001a60a  sub     eax, r15d
0x18001a60d  cdqe
0x18001a60f  mov     cl, [rax+r14]
0x18001a613  lea     eax, [rdx+r12]
0x18001a617  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001a61e  mov     [rdi+1Ch], cl
0x18001a621  movsxd  rcx, eax
0x18001a624  mov     al, [rcx+r14]
0x18001a628  mov     [rdi+1Bh], al
0x18001a62b  movzx   edx, byte ptr [rsi+5]
0x18001a62f  movzx   eax, byte ptr [rbx+5]
0x18001a633  mov     esi, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a63a  add     esi, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a641  mov     r14d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a649  mov     ebp, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a650  movzx   eax, byte ptr [r11+0Ah]
0x18001a655  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a65d  lea     eax, [rdx+r14]
0x18001a661  movsxd  rcx, eax
0x18001a664  mov     al, [rcx+r12]
0x18001a668  mov     [rdi+20h], al
0x18001a66b  mov     eax, edx
0x18001a66d  sub     eax, esi
0x18001a66f  cdqe
0x18001a671  mov     cl, [rax+r12]
0x18001a675  lea     eax, [rdx+rbp]
0x18001a678  mov     [rdi+1Fh], cl
0x18001a67b  movsxd  rcx, eax
0x18001a67e  mov     al, [rcx+r12]
0x18001a682  mov     [rdi+1Eh], al
0x18001a685  movzx   eax, byte ptr [r11+0Bh]
0x18001a68a  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a692  lea     eax, [rdx+r14]
0x18001a696  movsxd  rcx, eax
0x18001a699  mov     al, [rcx+r12]
0x18001a69d  mov     [rdi+23h], al
0x18001a6a0  mov     eax, edx
0x18001a6a2  sub     eax, esi
0x18001a6a4  cdqe
0x18001a6a6  mov     cl, [rax+r12]
0x18001a6aa  lea     eax, [rdx+rbp]
0x18001a6ad  mov     [rdi+22h], cl
0x18001a6b0  movsxd  rcx, eax
0x18001a6b3  mov     al, [rcx+r12]
0x18001a6b7  mov     rcx, [rsp+88h+arg_10]
0x18001a6bf  mov     [rdi+21h], al
0x18001a6c2  movzx   eax, byte ptr [rbx+6]
0x18001a6c6  movzx   edx, byte ptr [rcx+6]
0x18001a6ca  mov     edi, rva ?g_iVtoR@@3PAJA[r10+rax*4]; long near * g_iVtoR ...
0x18001a6d2  mov     r11d, rva ?g_iUtoG@@3PAJA[r10+rdx*4]; long near * g_iUtoG ...
0x18001a6da  add     r11d, rva ?g_iVtoG@@3PAJA[r10+rax*4]; long near * g_iVtoG ...
0x18001a6e2  movzx   eax, byte ptr [r9+0Ch]
0x18001a6e7  mov     ebx, rva ?g_iUtoB@@3PAJA[r10+rdx*4]; long near * g_iUtoB ...
0x18001a6ef  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a6f7  lea     eax, [rdx+rdi]
0x18001a6fa  movsxd  rcx, eax
0x18001a6fd  mov     al, [rcx+r12]
0x18001a701  mov     r8, [rsp+88h+arg_0]
0x18001a709  mov     [r8+26h], al
0x18001a70d  mov     eax, edx
0x18001a70f  sub     eax, r11d
0x18001a712  cdqe
0x18001a714  mov     cl, [rax+r12]
0x18001a718  lea     eax, [rdx+rbx]
0x18001a71b  mov     [r8+25h], cl
0x18001a71f  movsxd  rcx, eax
0x18001a722  mov     al, [rcx+r12]
0x18001a726  mov     [r8+24h], al
0x18001a72a  movzx   eax, byte ptr [r9+0Dh]
0x18001a72f  lea     r9, __ImageBase
0x18001a736  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a73e  lea     eax, [rdx+rdi]
0x18001a741  movsxd  rcx, eax
0x18001a744  mov     al, [rcx+r12]
0x18001a748  mov     [r8+29h], al
0x18001a74c  mov     eax, edx
0x18001a74e  sub     eax, r11d
0x18001a751  cdqe
0x18001a753  mov     cl, [rax+r12]
0x18001a757  lea     eax, [rdx+rbx]
0x18001a75a  mov     [r8+28h], cl
0x18001a75e  movsxd  rcx, eax
0x18001a761  mov     al, [rcx+r12]
0x18001a765  mov     rcx, [rsp+88h+arg_10]
0x18001a76d  mov     [r8+27h], al
0x18001a771  mov     rax, [rsp+88h+arg_18]
0x18001a779  movzx   edx, byte ptr [rcx+7]
0x18001a77d  movzx   eax, byte ptr [rax+7]
0x18001a781  mov     r8d, rva ?g_iUtoG@@3PAJA[r9+rdx*4]; long near * g_iUtoG ...
0x18001a789  add     r8d, rva ?g_iVtoG@@3PAJA[r9+rax*4]; long near * g_iVtoG ...
0x18001a791  mov     r10d, rva ?g_iVtoR@@3PAJA[r10+rax*4]; long near * g_iVtoR ...
0x18001a799  mov     r9d, rva ?g_iUtoB@@3PAJA[r9+rdx*4]; long near * g_iUtoB ...
  ... truncated ...
```
