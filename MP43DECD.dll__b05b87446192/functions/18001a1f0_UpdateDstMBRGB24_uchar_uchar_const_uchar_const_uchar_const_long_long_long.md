# UpdateDstMBRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001a1f0`
- end: `0x18001af16`
- name: `?UpdateDstMBRGB24@@YAXPEAEPEBE11JJJ@Z`
- size: `3366`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d710`

## callees

- `0x18001a1f0`

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
0x18001a1f0  mov     rax, rsp
0x18001a1f3  mov     [rax+20h], r9
0x18001a1f7  mov     [rax+18h], r8
0x18001a1fb  mov     [rax+10h], rdx
0x18001a1ff  mov     [rax+8], rcx
0x18001a203  push    rbx
0x18001a204  push    rbp
0x18001a205  push    rsi
0x18001a206  push    rdi
0x18001a207  push    r12
0x18001a209  push    r13
0x18001a20b  push    r14
0x18001a20d  push    r15
0x18001a20f  sub     rsp, 48h
0x18001a213  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001a21a  lea     rbp, __ImageBase
0x18001a221  mov     rbx, r9
0x18001a224  mov     [rsp+88h+var_58], 8
0x18001a22c  mov     rsi, r8
0x18001a22f  mov     r11, rdx
0x18001a232  mov     rdi, rcx
0x18001a235  movzx   edx, byte ptr [rsi]
0x18001a238  movzx   eax, byte ptr [rbx]
0x18001a23b  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a243  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a24b  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a253  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a25b  movzx   eax, byte ptr [r11]
0x18001a25f  mov     [rsp+88h+var_84], r8d
0x18001a264  mov     [rsp+88h+var_88], r10d
0x18001a268  mov     [rsp+88h+var_80], r9d
0x18001a26d  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a274  lea     eax, [r10+rdx]
0x18001a278  movsxd  rcx, eax
0x18001a27b  mov     al, [rcx+r14]
0x18001a27f  mov     [rdi+2], al
0x18001a282  mov     eax, edx
0x18001a284  sub     eax, r8d
0x18001a287  cdqe
0x18001a289  mov     cl, [rax+r14]
0x18001a28d  lea     eax, [rdx+r9]
0x18001a291  mov     [rdi+1], cl
0x18001a294  movsxd  rcx, eax
0x18001a297  mov     al, [rcx+r14]
0x18001a29b  mov     [rdi], al
0x18001a29d  movzx   eax, byte ptr [r11+1]
0x18001a2a2  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a2a9  lea     eax, [r10+rdx]
0x18001a2ad  movsxd  rcx, eax
0x18001a2b0  mov     al, [rcx+r14]
0x18001a2b4  mov     [rdi+5], al
0x18001a2b7  mov     eax, edx
0x18001a2b9  sub     eax, r8d
0x18001a2bc  cdqe
0x18001a2be  mov     cl, [rax+r14]
0x18001a2c2  lea     eax, [rdx+r9]
0x18001a2c6  mov     [rdi+4], cl
0x18001a2c9  movsxd  rcx, eax
0x18001a2cc  mov     al, [rcx+r14]
0x18001a2d0  mov     [rdi+3], al
0x18001a2d3  movzx   edx, byte ptr [rsi+1]
0x18001a2d7  movzx   eax, byte ptr [rbx+1]
0x18001a2db  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a2e3  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a2eb  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a2f3  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a2fb  movzx   eax, byte ptr [r11+2]
0x18001a300  mov     [rsp+88h+var_7C], r10d
0x18001a305  mov     [rsp+88h+var_78], r8d
0x18001a30a  mov     [rsp+88h+var_74], r9d
0x18001a30f  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a316  lea     eax, [rdx+r10]
0x18001a31a  movsxd  rcx, eax
0x18001a31d  mov     al, [rcx+r14]
0x18001a321  mov     [rdi+8], al
0x18001a324  mov     eax, edx
0x18001a326  sub     eax, r8d
0x18001a329  cdqe
0x18001a32b  mov     cl, [rax+r14]
0x18001a32f  lea     eax, [rdx+r9]
0x18001a333  mov     [rdi+7], cl
0x18001a336  movsxd  rcx, eax
0x18001a339  mov     al, [rcx+r14]
0x18001a33d  mov     [rdi+6], al
0x18001a340  movzx   eax, byte ptr [r11+3]
0x18001a345  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a34c  lea     eax, [rdx+r10]
0x18001a350  movsxd  rcx, eax
0x18001a353  mov     al, [rcx+r14]
0x18001a357  mov     [rdi+0Bh], al
0x18001a35a  mov     eax, edx
0x18001a35c  sub     eax, r8d
0x18001a35f  cdqe
0x18001a361  mov     cl, [rax+r14]
0x18001a365  lea     eax, [rdx+r9]
0x18001a369  mov     [rdi+0Ah], cl
0x18001a36c  movsxd  rcx, eax
0x18001a36f  mov     al, [rcx+r14]
0x18001a373  mov     [rdi+9], al
0x18001a376  movzx   eax, byte ptr [rbx+2]
0x18001a37a  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a382  mov     [rsp+88h+var_70], r10d
0x18001a387  movzx   edx, byte ptr [rsi+2]
0x18001a38b  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a393  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a39b  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a3a3  movzx   eax, byte ptr [r11+4]
0x18001a3a8  mov     [rsp+88h+var_6C], r8d
0x18001a3ad  mov     [rsp+88h+var_68], r9d
0x18001a3b2  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a3b9  lea     eax, [rdx+r10]
0x18001a3bd  movsxd  rcx, eax
0x18001a3c0  mov     al, [rcx+r14]
0x18001a3c4  mov     [rdi+0Eh], al
0x18001a3c7  mov     eax, edx
0x18001a3c9  sub     eax, r8d
0x18001a3cc  cdqe
0x18001a3ce  mov     cl, [rax+r14]
0x18001a3d2  lea     eax, [rdx+r9]
0x18001a3d6  mov     [rdi+0Dh], cl
0x18001a3d9  movsxd  rcx, eax
0x18001a3dc  mov     al, [rcx+r14]
0x18001a3e0  mov     [rdi+0Ch], al
0x18001a3e3  movzx   eax, byte ptr [r11+5]
0x18001a3e8  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a3ef  lea     eax, [rdx+r10]
0x18001a3f3  movsxd  rcx, eax
0x18001a3f6  mov     al, [rcx+r14]
0x18001a3fa  mov     [rdi+11h], al
0x18001a3fd  mov     eax, edx
0x18001a3ff  sub     eax, r8d
0x18001a402  cdqe
0x18001a404  mov     cl, [rax+r14]
0x18001a408  lea     eax, [rdx+r9]
0x18001a40c  mov     [rdi+10h], cl
0x18001a40f  movsxd  rcx, eax
0x18001a412  mov     al, [rcx+r14]
0x18001a416  mov     [rdi+0Fh], al
0x18001a419  movzx   edx, byte ptr [rsi+3]
0x18001a41d  movzx   eax, byte ptr [rbx+3]
0x18001a421  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a429  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a431  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a439  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a441  movzx   eax, byte ptr [r11+6]
0x18001a446  mov     [rsp+88h+var_64], r10d
0x18001a44b  mov     [rsp+88h+var_60], r8d
0x18001a450  mov     [rsp+88h+var_5C], r9d
0x18001a455  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a45c  lea     eax, [rdx+r10]
0x18001a460  movsxd  rcx, eax
0x18001a463  mov     al, [rcx+r14]
0x18001a467  mov     [rdi+14h], al
0x18001a46a  mov     eax, edx
0x18001a46c  sub     eax, r8d
0x18001a46f  cdqe
0x18001a471  mov     cl, [rax+r14]
0x18001a475  lea     eax, [rdx+r9]
0x18001a479  mov     [rdi+13h], cl
0x18001a47c  movsxd  rcx, eax
0x18001a47f  mov     al, [rcx+r14]
0x18001a483  mov     [rdi+12h], al
0x18001a486  movzx   eax, byte ptr [r11+7]
0x18001a48b  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a492  lea     eax, [rdx+r10]
0x18001a496  movsxd  rcx, eax
0x18001a499  mov     al, [rcx+r14]
0x18001a49d  mov     [rdi+17h], al
0x18001a4a0  mov     eax, edx
0x18001a4a2  sub     eax, r8d
0x18001a4a5  cdqe
0x18001a4a7  mov     cl, [rax+r14]
0x18001a4ab  lea     eax, [rdx+r9]
0x18001a4af  mov     [rdi+16h], cl
0x18001a4b2  movsxd  rcx, eax
0x18001a4b5  mov     al, [rcx+r14]
0x18001a4b9  mov     [rdi+15h], al
0x18001a4bc  movzx   edx, byte ptr [rsi+4]
0x18001a4c0  movzx   eax, byte ptr [rbx+4]
0x18001a4c4  mov     r15d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a4cc  add     r15d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a4d4  mov     r13d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a4dc  mov     r12d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a4e4  movzx   eax, byte ptr [r11+8]
0x18001a4e9  lea     r10, __ImageBase
0x18001a4f0  mov     r9, [rsp+88h+arg_8]
0x18001a4f8  mov     [rsp+88h+var_54], r12d
0x18001a4fd  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a504  lea     eax, [rdx+r13]
0x18001a508  movsxd  rcx, eax
0x18001a50b  mov     al, [rcx+r14]
0x18001a50f  mov     [rdi+1Ah], al
0x18001a512  mov     eax, edx
0x18001a514  sub     eax, r15d
0x18001a517  cdqe
0x18001a519  mov     cl, [rax+r14]
0x18001a51d  lea     eax, [rdx+r12]
0x18001a521  mov     [rdi+19h], cl
0x18001a524  movsxd  rcx, eax
0x18001a527  mov     al, [rcx+r14]
0x18001a52b  mov     [rdi+18h], al
0x18001a52e  movzx   eax, byte ptr [r11+9]
0x18001a533  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001a53a  lea     eax, [rdx+r13]
0x18001a53e  movsxd  rcx, eax
0x18001a541  mov     al, [rcx+r14]
0x18001a545  mov     [rdi+1Dh], al
0x18001a548  mov     eax, edx
0x18001a54a  sub     eax, r15d
0x18001a54d  cdqe
0x18001a54f  mov     cl, [rax+r14]
0x18001a553  lea     eax, [rdx+r12]
0x18001a557  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001a55e  mov     [rdi+1Ch], cl
0x18001a561  movsxd  rcx, eax
0x18001a564  mov     al, [rcx+r14]
0x18001a568  mov     [rdi+1Bh], al
0x18001a56b  movzx   edx, byte ptr [rsi+5]
0x18001a56f  movzx   eax, byte ptr [rbx+5]
0x18001a573  mov     esi, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001a57a  add     esi, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001a581  mov     r14d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001a589  mov     ebp, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001a590  movzx   eax, byte ptr [r11+0Ah]
0x18001a595  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a59d  lea     eax, [rdx+r14]
0x18001a5a1  movsxd  rcx, eax
0x18001a5a4  mov     al, [rcx+r12]
0x18001a5a8  mov     [rdi+20h], al
0x18001a5ab  mov     eax, edx
0x18001a5ad  sub     eax, esi
0x18001a5af  cdqe
0x18001a5b1  mov     cl, [rax+r12]
0x18001a5b5  lea     eax, [rdx+rbp]
0x18001a5b8  mov     [rdi+1Fh], cl
0x18001a5bb  movsxd  rcx, eax
0x18001a5be  mov     al, [rcx+r12]
0x18001a5c2  mov     [rdi+1Eh], al
0x18001a5c5  movzx   eax, byte ptr [r11+0Bh]
0x18001a5ca  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a5d2  lea     eax, [rdx+r14]
0x18001a5d6  movsxd  rcx, eax
0x18001a5d9  mov     al, [rcx+r12]
0x18001a5dd  mov     [rdi+23h], al
0x18001a5e0  mov     eax, edx
0x18001a5e2  sub     eax, esi
0x18001a5e4  cdqe
0x18001a5e6  mov     cl, [rax+r12]
0x18001a5ea  lea     eax, [rdx+rbp]
0x18001a5ed  mov     [rdi+22h], cl
0x18001a5f0  movsxd  rcx, eax
0x18001a5f3  mov     al, [rcx+r12]
0x18001a5f7  mov     rcx, [rsp+88h+arg_10]
0x18001a5ff  mov     [rdi+21h], al
0x18001a602  movzx   eax, byte ptr [rbx+6]
0x18001a606  movzx   edx, byte ptr [rcx+6]
0x18001a60a  mov     edi, rva ?g_iVtoR@@3PAJA[r10+rax*4]; long near * g_iVtoR ...
0x18001a612  mov     r11d, rva ?g_iUtoG@@3PAJA[r10+rdx*4]; long near * g_iUtoG ...
0x18001a61a  add     r11d, rva ?g_iVtoG@@3PAJA[r10+rax*4]; long near * g_iVtoG ...
0x18001a622  movzx   eax, byte ptr [r9+0Ch]
0x18001a627  mov     ebx, rva ?g_iUtoB@@3PAJA[r10+rdx*4]; long near * g_iUtoB ...
0x18001a62f  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a637  lea     eax, [rdx+rdi]
0x18001a63a  movsxd  rcx, eax
0x18001a63d  mov     al, [rcx+r12]
0x18001a641  mov     r8, [rsp+88h+arg_0]
0x18001a649  mov     [r8+26h], al
0x18001a64d  mov     eax, edx
0x18001a64f  sub     eax, r11d
0x18001a652  cdqe
0x18001a654  mov     cl, [rax+r12]
0x18001a658  lea     eax, [rdx+rbx]
0x18001a65b  mov     [r8+25h], cl
0x18001a65f  movsxd  rcx, eax
0x18001a662  mov     al, [rcx+r12]
0x18001a666  mov     [r8+24h], al
0x18001a66a  movzx   eax, byte ptr [r9+0Dh]
0x18001a66f  lea     r9, __ImageBase
0x18001a676  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001a67e  lea     eax, [rdx+rdi]
0x18001a681  movsxd  rcx, eax
0x18001a684  mov     al, [rcx+r12]
0x18001a688  mov     [r8+29h], al
0x18001a68c  mov     eax, edx
0x18001a68e  sub     eax, r11d
0x18001a691  cdqe
0x18001a693  mov     cl, [rax+r12]
0x18001a697  lea     eax, [rdx+rbx]
0x18001a69a  mov     [r8+28h], cl
0x18001a69e  movsxd  rcx, eax
0x18001a6a1  mov     al, [rcx+r12]
0x18001a6a5  mov     rcx, [rsp+88h+arg_10]
0x18001a6ad  mov     [r8+27h], al
0x18001a6b1  mov     rax, [rsp+88h+arg_18]
0x18001a6b9  movzx   edx, byte ptr [rcx+7]
0x18001a6bd  movzx   eax, byte ptr [rax+7]
0x18001a6c1  mov     r8d, rva ?g_iUtoG@@3PAJA[r9+rdx*4]; long near * g_iUtoG ...
0x18001a6c9  add     r8d, rva ?g_iVtoG@@3PAJA[r9+rax*4]; long near * g_iVtoG ...
0x18001a6d1  mov     r10d, rva ?g_iVtoR@@3PAJA[r10+rax*4]; long near * g_iVtoR ...
0x18001a6d9  mov     r9d, rva ?g_iUtoB@@3PAJA[r9+rdx*4]; long near * g_iUtoB ...
  ... truncated ...
```
