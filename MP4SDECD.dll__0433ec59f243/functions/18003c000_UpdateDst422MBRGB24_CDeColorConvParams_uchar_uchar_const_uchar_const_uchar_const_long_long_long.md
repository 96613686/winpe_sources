# UpdateDst422MBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003c000`
- end: `0x18003c599`
- name: `?UpdateDst422MBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `1433`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003c5a0`

## callees

- `0x18003c000`

## pseudocode

```c
void __fastcall UpdateDst422MBRGB24(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v8; // rbx
  int v13; // r15d
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r10d
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // r10d
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // r10d
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r10d
  int v33; // r9d
  __int64 v34; // rdx
  __int64 v35; // rax
  int v36; // r8d
  int v37; // r10d
  int v38; // r9d
  __int64 v39; // rdx
  __int64 v40; // rax
  int v41; // r8d
  int v42; // r10d
  int v43; // r9d
  __int64 v44; // rdx
  __int64 v45; // rax
  int v46; // r8d
  int v47; // r10d
  int v48; // r9d
  __int64 v49; // rdx
  __int64 v50; // rax
  int v51; // r8d
  int v52; // r10d
  int v53; // r9d
  __int64 v54; // rax

  v8 = g_rgiClapTabDec;
  v13 = 16;
  do
  {
    v14 = *a4;
    v15 = *a5;
    v16 = g_iVtoG[v15] + g_iUtoG[v14];
    v17 = g_iVtoR[v15];
    v18 = g_iUtoB[v14];
    LODWORD(v14) = g_iYscale[*a3];
    a2[2] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[1] = *(_BYTE *)((int)v14 - v16 + v8);
    *a2 = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[1]];
    a2[5] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[4] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[3] = *(_BYTE *)((int)v14 + v18 + v8);
    v19 = a4[1];
    v20 = a5[1];
    v21 = g_iVtoR[v20];
    v22 = g_iVtoG[v20] + g_iUtoG[v19];
    v23 = g_iUtoB[v19];
    LODWORD(v19) = g_iYscale[a3[2]];
    a2[8] = *(_BYTE *)((int)v19 + v21 + v8);
    a2[7] = *(_BYTE *)((int)v19 - v22 + v8);
    a2[6] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[3]];
    a2[11] = *(_BYTE *)((int)v19 + v21 + v8);
    a2[10] = *(_BYTE *)((int)v19 - v22 + v8);
    a2[9] = *(_BYTE *)((int)v19 + v23 + v8);
    v24 = a5[2];
    v25 = a4[2];
    v26 = g_iVtoR[v24];
    v27 = g_iVtoG[v24] + g_iUtoG[v25];
    v28 = g_iUtoB[v25];
    LODWORD(v25) = g_iYscale[a3[4]];
    a2[14] = *(_BYTE *)((int)v25 + v26 + v8);
    a2[13] = *(_BYTE *)((int)v25 - v27 + v8);
    a2[12] = *(_BYTE *)((int)v25 + v28 + v8);
    LODWORD(v25) = g_iYscale[a3[5]];
    a2[17] = *(_BYTE *)((int)v25 + v26 + v8);
    a2[16] = *(_BYTE *)((int)v25 - v27 + v8);
    a2[15] = *(_BYTE *)((int)v25 + v28 + v8);
    v29 = a4[3];
    v30 = a5[3];
    v31 = g_iVtoG[v30] + g_iUtoG[v29];
    v32 = g_iVtoR[v30];
    v33 = g_iUtoB[v29];
    LODWORD(v29) = g_iYscale[a3[6]];
    a2[20] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[19] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[18] = *(_BYTE *)(v33 + (int)v29 + v8);
    LODWORD(v29) = g_iYscale[a3[7]];
    a2[23] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[22] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[21] = *(_BYTE *)(v33 + (int)v29 + v8);
    v34 = a4[4];
    v35 = a5[4];
    v36 = g_iVtoG[v35] + g_iUtoG[v34];
    v37 = g_iVtoR[v35];
    v38 = g_iUtoB[v34];
    LODWORD(v34) = g_iYscale[a3[8]];
    a2[26] = *(_BYTE *)(v37 + (int)v34 + v8);
    a2[25] = *(_BYTE *)((int)v34 - v36 + v8);
    a2[24] = *(_BYTE *)(v38 + (int)v34 + v8);
    LODWORD(v34) = g_iYscale[a3[9]];
    a2[29] = *(_BYTE *)(v37 + (int)v34 + v8);
    a2[28] = *(_BYTE *)((int)v34 - v36 + v8);
    a2[27] = *(_BYTE *)(v38 + (int)v34 + v8);
    v39 = a4[5];
    v40 = a5[5];
    v41 = g_iVtoG[v40] + g_iUtoG[v39];
    v42 = g_iVtoR[v40];
    v43 = g_iUtoB[v39];
    LODWORD(v39) = g_iYscale[a3[10]];
    a2[32] = *(_BYTE *)(v42 + (int)v39 + v8);
    a2[31] = *(_BYTE *)((int)v39 - v41 + v8);
    a2[30] = *(_BYTE *)(v43 + (int)v39 + v8);
    LODWORD(v39) = g_iYscale[a3[11]];
    a2[35] = *(_BYTE *)(v42 + (int)v39 + v8);
    a2[34] = *(_BYTE *)((int)v39 - v41 + v8);
    a2[33] = *(_BYTE *)(v43 + (int)v39 + v8);
    v44 = a4[6];
    v45 = a5[6];
    v46 = g_iVtoG[v45] + g_iUtoG[v44];
    v47 = g_iVtoR[v45];
    v48 = g_iUtoB[v44];
    LODWORD(v44) = g_iYscale[a3[12]];
    a2[38] = *(_BYTE *)(v47 + (int)v44 + v8);
    a2[37] = *(_BYTE *)((int)v44 - v46 + v8);
    a2[36] = *(_BYTE *)(v48 + (int)v44 + v8);
    LODWORD(v44) = g_iYscale[a3[13]];
    a2[41] = *(_BYTE *)(v47 + (int)v44 + v8);
    a2[40] = *(_BYTE *)((int)v44 - v46 + v8);
    a2[39] = *(_BYTE *)(v48 + (int)v44 + v8);
    v49 = a4[7];
    a4 += a7;
    v50 = a5[7];
    a5 += a7;
    v51 = g_iVtoG[v50] + g_iUtoG[v49];
    v52 = g_iVtoR[v50];
    v53 = g_iUtoB[v49];
    LODWORD(v49) = g_iYscale[a3[14]];
    a2[44] = *(_BYTE *)(v52 + (int)v49 + v8);
    a2[43] = *(_BYTE *)((int)v49 - v51 + v8);
    a2[42] = *(_BYTE *)(v53 + (int)v49 + v8);
    v54 = a3[15];
    a3 += a6;
    LODWORD(v49) = g_iYscale[v54];
    a2[47] = *(_BYTE *)(v52 + (int)v49 + v8);
    a2[46] = *(_BYTE *)((int)v49 - v51 + v8);
    a2[45] = *(_BYTE *)(v53 + (int)v49 + v8);
    a2 += a8;
    --v13;
  }
  while ( v13 );
}

```

## disassembly

```asm
0x18003c000  push    rbx
0x18003c002  push    rbp
0x18003c003  push    rsi
0x18003c004  push    rdi
0x18003c005  push    r12
0x18003c007  push    r13
0x18003c009  push    r14
0x18003c00b  push    r15
0x18003c00d  mov     rbx, cs:g_rgiClapTabDec
0x18003c014  mov     rsi, r9
0x18003c017  movsxd  r12, [rsp+40h+arg_28]
0x18003c01c  lea     r9, __ImageBase
0x18003c023  movsxd  r14, [rsp+40h+arg_30]
0x18003c028  mov     rdi, r8
0x18003c02b  movsxd  r13, [rsp+40h+arg_38]
0x18003c033  mov     r11, rdx
0x18003c036  mov     rbp, [rsp+40h+arg_20]
0x18003c03b  mov     r15d, 10h
0x18003c041  movzx   edx, byte ptr [rsi]
0x18003c044  movzx   eax, byte ptr [rbp+0]
0x18003c048  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c050  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c058  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c060  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c068  lea     rdx, __ImageBase
0x18003c06f  movzx   eax, byte ptr [rdi]
0x18003c072  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003c079  lea     eax, [rdx+r10]
0x18003c07d  movsxd  rcx, eax
0x18003c080  mov     al, [rcx+rbx]
0x18003c083  mov     [r11+2], al
0x18003c087  mov     eax, edx
0x18003c089  sub     eax, r8d
0x18003c08c  cdqe
0x18003c08e  mov     cl, [rax+rbx]
0x18003c091  lea     eax, [rdx+r9]
0x18003c095  mov     [r11+1], cl
0x18003c099  movsxd  rcx, eax
0x18003c09c  mov     al, [rcx+rbx]
0x18003c09f  lea     rcx, __ImageBase
0x18003c0a6  mov     [r11], al
0x18003c0a9  movzx   eax, byte ptr [rdi+1]
0x18003c0ad  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c0b4  lea     eax, [rdx+r10]
0x18003c0b8  movsxd  rcx, eax
0x18003c0bb  mov     al, [rcx+rbx]
0x18003c0be  mov     [r11+5], al
0x18003c0c2  mov     eax, edx
0x18003c0c4  sub     eax, r8d
0x18003c0c7  cdqe
0x18003c0c9  mov     cl, [rax+rbx]
0x18003c0cc  lea     eax, [rdx+r9]
0x18003c0d0  mov     [r11+4], cl
0x18003c0d4  lea     r9, __ImageBase
0x18003c0db  movsxd  rcx, eax
0x18003c0de  mov     al, [rcx+rbx]
0x18003c0e1  lea     rcx, __ImageBase
0x18003c0e8  mov     [r11+3], al
0x18003c0ec  movzx   edx, byte ptr [rsi+1]
0x18003c0f0  movzx   eax, byte ptr [rbp+1]
0x18003c0f4  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c0fc  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c104  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c10c  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c114  movzx   eax, byte ptr [rdi+2]
0x18003c118  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c11f  lea     eax, [rdx+r10]
0x18003c123  movsxd  rcx, eax
0x18003c126  mov     al, [rcx+rbx]
0x18003c129  mov     [r11+8], al
0x18003c12d  mov     eax, edx
0x18003c12f  sub     eax, r8d
0x18003c132  cdqe
0x18003c134  mov     cl, [rax+rbx]
0x18003c137  lea     eax, [rdx+r9]
0x18003c13b  mov     [r11+7], cl
0x18003c13f  movsxd  rcx, eax
0x18003c142  mov     al, [rcx+rbx]
0x18003c145  lea     rcx, __ImageBase
0x18003c14c  mov     [r11+6], al
0x18003c150  movzx   eax, byte ptr [rdi+3]
0x18003c154  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c15b  lea     eax, [rdx+r10]
0x18003c15f  movsxd  rcx, eax
0x18003c162  mov     al, [rcx+rbx]
0x18003c165  mov     [r11+0Bh], al
0x18003c169  mov     eax, edx
0x18003c16b  sub     eax, r8d
0x18003c16e  cdqe
0x18003c170  mov     cl, [rax+rbx]
0x18003c173  lea     eax, [rdx+r9]
0x18003c177  mov     [r11+0Ah], cl
0x18003c17b  lea     r9, __ImageBase
0x18003c182  movsxd  rcx, eax
0x18003c185  mov     al, [rcx+rbx]
0x18003c188  mov     [r11+9], al
0x18003c18c  movzx   eax, byte ptr [rbp+2]
0x18003c190  movzx   edx, byte ptr [rsi+2]
0x18003c194  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c19c  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c1a4  lea     rcx, __ImageBase
0x18003c1ab  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c1b3  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c1bb  movzx   eax, byte ptr [rdi+4]
0x18003c1bf  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c1c6  lea     eax, [rdx+r10]
0x18003c1ca  movsxd  rcx, eax
0x18003c1cd  mov     al, [rcx+rbx]
0x18003c1d0  mov     [r11+0Eh], al
0x18003c1d4  mov     eax, edx
0x18003c1d6  sub     eax, r8d
0x18003c1d9  cdqe
0x18003c1db  mov     cl, [rax+rbx]
0x18003c1de  lea     eax, [rdx+r9]
0x18003c1e2  mov     [r11+0Dh], cl
0x18003c1e6  movsxd  rcx, eax
0x18003c1e9  mov     al, [rcx+rbx]
0x18003c1ec  lea     rcx, __ImageBase
0x18003c1f3  mov     [r11+0Ch], al
0x18003c1f7  movzx   eax, byte ptr [rdi+5]
0x18003c1fb  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c202  lea     eax, [rdx+r10]
0x18003c206  movsxd  rcx, eax
0x18003c209  mov     al, [rcx+rbx]
0x18003c20c  mov     [r11+11h], al
0x18003c210  mov     eax, edx
0x18003c212  sub     eax, r8d
0x18003c215  cdqe
0x18003c217  mov     cl, [rax+rbx]
0x18003c21a  lea     eax, [rdx+r9]
0x18003c21e  mov     [r11+10h], cl
0x18003c222  lea     r9, __ImageBase
0x18003c229  movsxd  rcx, eax
0x18003c22c  mov     al, [rcx+rbx]
0x18003c22f  lea     rcx, __ImageBase
0x18003c236  mov     [r11+0Fh], al
0x18003c23a  movzx   edx, byte ptr [rsi+3]
0x18003c23e  movzx   eax, byte ptr [rbp+3]
0x18003c242  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c24a  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c252  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c25a  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c262  movzx   eax, byte ptr [rdi+6]
0x18003c266  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c26d  lea     eax, [r10+rdx]
0x18003c271  movsxd  rcx, eax
0x18003c274  mov     al, [rcx+rbx]
0x18003c277  mov     [r11+14h], al
0x18003c27b  mov     eax, edx
0x18003c27d  sub     eax, r8d
0x18003c280  cdqe
0x18003c282  mov     cl, [rax+rbx]
0x18003c285  lea     eax, [r9+rdx]
0x18003c289  mov     [r11+13h], cl
0x18003c28d  movsxd  rcx, eax
0x18003c290  mov     al, [rcx+rbx]
0x18003c293  lea     rcx, __ImageBase
0x18003c29a  mov     [r11+12h], al
0x18003c29e  movzx   eax, byte ptr [rdi+7]
0x18003c2a2  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c2a9  lea     eax, [r10+rdx]
0x18003c2ad  movsxd  rcx, eax
0x18003c2b0  mov     al, [rcx+rbx]
0x18003c2b3  mov     [r11+17h], al
0x18003c2b7  mov     eax, edx
0x18003c2b9  sub     eax, r8d
0x18003c2bc  cdqe
0x18003c2be  mov     cl, [rax+rbx]
0x18003c2c1  lea     eax, [r9+rdx]
0x18003c2c5  mov     [r11+16h], cl
0x18003c2c9  lea     r9, __ImageBase
0x18003c2d0  movsxd  rcx, eax
0x18003c2d3  mov     al, [rcx+rbx]
0x18003c2d6  mov     [r11+15h], al
0x18003c2da  movzx   edx, byte ptr [rsi+4]
0x18003c2de  movzx   eax, byte ptr [rbp+4]
0x18003c2e2  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c2ea  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c2f2  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c2fa  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c302  movzx   eax, byte ptr [rdi+8]
0x18003c306  lea     rcx, __ImageBase
0x18003c30d  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c314  lea     eax, [r10+rdx]
0x18003c318  movsxd  rcx, eax
0x18003c31b  mov     al, [rcx+rbx]
0x18003c31e  mov     [r11+1Ah], al
0x18003c322  mov     eax, edx
0x18003c324  sub     eax, r8d
0x18003c327  cdqe
0x18003c329  mov     cl, [rax+rbx]
0x18003c32c  lea     eax, [r9+rdx]
0x18003c330  mov     [r11+19h], cl
0x18003c334  movsxd  rcx, eax
0x18003c337  mov     al, [rcx+rbx]
0x18003c33a  lea     rcx, __ImageBase
0x18003c341  mov     [r11+18h], al
0x18003c345  movzx   eax, byte ptr [rdi+9]
0x18003c349  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c350  lea     eax, [r10+rdx]
0x18003c354  movsxd  rcx, eax
0x18003c357  mov     al, [rcx+rbx]
0x18003c35a  mov     [r11+1Dh], al
0x18003c35e  mov     eax, edx
0x18003c360  sub     eax, r8d
0x18003c363  cdqe
0x18003c365  mov     cl, [rax+rbx]
0x18003c368  lea     eax, [r9+rdx]
0x18003c36c  mov     [r11+1Ch], cl
0x18003c370  lea     r9, __ImageBase
0x18003c377  movsxd  rcx, eax
0x18003c37a  mov     al, [rcx+rbx]
0x18003c37d  lea     rcx, __ImageBase
0x18003c384  mov     [r11+1Bh], al
0x18003c388  movzx   edx, byte ptr [rsi+5]
0x18003c38c  movzx   eax, byte ptr [rbp+5]
0x18003c390  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c398  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c3a0  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c3a8  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c3b0  movzx   eax, byte ptr [rdi+0Ah]
0x18003c3b4  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c3bb  lea     eax, [r10+rdx]
0x18003c3bf  movsxd  rcx, eax
0x18003c3c2  mov     al, [rcx+rbx]
0x18003c3c5  mov     [r11+20h], al
0x18003c3c9  mov     eax, edx
0x18003c3cb  sub     eax, r8d
0x18003c3ce  cdqe
0x18003c3d0  mov     cl, [rax+rbx]
0x18003c3d3  lea     eax, [r9+rdx]
0x18003c3d7  mov     [r11+1Fh], cl
0x18003c3db  movsxd  rcx, eax
0x18003c3de  mov     al, [rcx+rbx]
0x18003c3e1  lea     rcx, __ImageBase
0x18003c3e8  mov     [r11+1Eh], al
0x18003c3ec  movzx   eax, byte ptr [rdi+0Bh]
0x18003c3f0  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c3f7  lea     eax, [r10+rdx]
0x18003c3fb  movsxd  rcx, eax
0x18003c3fe  mov     al, [rcx+rbx]
0x18003c401  mov     [r11+23h], al
0x18003c405  mov     eax, edx
0x18003c407  sub     eax, r8d
0x18003c40a  cdqe
0x18003c40c  mov     cl, [rax+rbx]
0x18003c40f  lea     eax, [r9+rdx]
0x18003c413  mov     [r11+22h], cl
0x18003c417  lea     r9, __ImageBase
0x18003c41e  movsxd  rcx, eax
0x18003c421  mov     al, [rcx+rbx]
0x18003c424  lea     rcx, __ImageBase
0x18003c42b  mov     [r11+21h], al
0x18003c42f  movzx   edx, byte ptr [rsi+6]
0x18003c433  movzx   eax, byte ptr [rbp+6]
0x18003c437  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c43f  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c447  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c44f  movzx   eax, byte ptr [rdi+0Ch]
0x18003c453  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003c45b  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c462  lea     eax, [r10+rdx]
0x18003c466  movsxd  rcx, eax
0x18003c469  mov     al, [rcx+rbx]
0x18003c46c  mov     [r11+26h], al
0x18003c470  mov     eax, edx
0x18003c472  sub     eax, r8d
0x18003c475  cdqe
0x18003c477  mov     cl, [rax+rbx]
0x18003c47a  lea     eax, [r9+rdx]
0x18003c47e  mov     [r11+25h], cl
0x18003c482  movsxd  rcx, eax
0x18003c485  mov     al, [rcx+rbx]
0x18003c488  lea     rcx, __ImageBase
0x18003c48f  mov     [r11+24h], al
0x18003c493  movzx   eax, byte ptr [rdi+0Dh]
0x18003c497  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003c49e  lea     eax, [r10+rdx]
0x18003c4a2  movsxd  rcx, eax
0x18003c4a5  mov     al, [rcx+rbx]
0x18003c4a8  mov     [r11+29h], al
0x18003c4ac  mov     eax, edx
0x18003c4ae  sub     eax, r8d
0x18003c4b1  cdqe
0x18003c4b3  mov     cl, [rax+rbx]
0x18003c4b6  lea     eax, [r9+rdx]
0x18003c4ba  mov     [r11+28h], cl
0x18003c4be  lea     r9, __ImageBase
0x18003c4c5  movsxd  rcx, eax
0x18003c4c8  mov     al, [rcx+rbx]
0x18003c4cb  lea     rcx, __ImageBase
0x18003c4d2  mov     [r11+27h], al
0x18003c4d6  movzx   edx, byte ptr [rsi+7]
0x18003c4da  add     rsi, r14
0x18003c4dd  movzx   eax, byte ptr [rbp+7]
0x18003c4e1  add     rbp, r14
0x18003c4e4  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003c4ec  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003c4f4  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003c4fc  mov     r9d, rva g_iUtoB[r9+rdx*4]
  ... truncated ...
```
