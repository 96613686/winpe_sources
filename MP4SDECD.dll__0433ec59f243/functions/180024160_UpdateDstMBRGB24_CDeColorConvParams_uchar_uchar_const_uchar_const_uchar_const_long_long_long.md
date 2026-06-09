# UpdateDstMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180024160`
- end: `0x180024e83`
- name: `?UpdateDstMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `3363`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800431f0`

## callees

- `0x180024160`

## pseudocode

```c
void __fastcall UpdateDstMBRGB24(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v8; // r14
  const unsigned __int8 *v9; // rbx
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
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // r13d
  int v23; // r15d
  __int64 v24; // r12
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // esi
  int v28; // r14d
  int v29; // ebp
  __int64 v30; // rdx
  __int64 v31; // rax
  int v32; // r11d
  int v33; // edi
  int v34; // ebx
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // r10d
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // r12
  __int64 v41; // r12
  __int64 v42; // r12
  __int64 v43; // r12
  __int64 v44; // r12
  __int64 v45; // r12
  __int64 v46; // r12
  __int64 v47; // r12
  __int64 v48; // r15
  unsigned __int8 *v49; // r12
  __int64 v50; // rcx
  const unsigned __int8 *v51; // rsi
  __int64 v52; // rax
  bool v53; // zf
  int v54; // [rsp+0h] [rbp-78h]
  int v55; // [rsp+4h] [rbp-74h]
  int v56; // [rsp+8h] [rbp-70h]
  int v57; // [rsp+Ch] [rbp-6Ch]
  int v58; // [rsp+10h] [rbp-68h]
  int v59; // [rsp+14h] [rbp-64h]
  int v60; // [rsp+18h] [rbp-60h]
  int v61; // [rsp+1Ch] [rbp-5Ch]
  int v62; // [rsp+20h] [rbp-58h]
  int v63; // [rsp+24h] [rbp-54h]
  int v64; // [rsp+28h] [rbp-50h]
  int v65; // [rsp+2Ch] [rbp-4Ch]
  int v66; // [rsp+30h] [rbp-48h]
  int v67; // [rsp+34h] [rbp-44h]
  unsigned __int8 *v68; // [rsp+88h] [rbp+10h]
  const unsigned __int8 *v69; // [rsp+90h] [rbp+18h]
  const unsigned __int8 *v70; // [rsp+98h] [rbp+20h]

  v70 = a4;
  v69 = a3;
  v68 = a2;
  v8 = g_rgiClapTabDec;
  v9 = a4;
  v66 = 8;
  v10 = a3;
  v11 = a2;
  do
  {
    v12 = *v9;
    v13 = *a5;
    v56 = g_iUtoB[v12];
    v55 = g_iVtoG[v13] + g_iUtoG[v12];
    v54 = g_iVtoR[v13];
    LODWORD(v12) = g_iYscale[*v10];
    v11[2] = *(_BYTE *)(v54 + (int)v12 + v8);
    v11[1] = *(_BYTE *)((int)v12 - v55 + v8);
    *v11 = *(_BYTE *)((int)v12 + v56 + v8);
    LODWORD(v12) = g_iYscale[v10[1]];
    v11[5] = *(_BYTE *)(v54 + (int)v12 + v8);
    v11[4] = *(_BYTE *)((int)v12 - v55 + v8);
    v11[3] = *(_BYTE *)((int)v12 + v56 + v8);
    v14 = v9[1];
    v15 = a5[1];
    v57 = g_iVtoR[v15];
    v58 = g_iVtoG[v15] + g_iUtoG[v14];
    v59 = g_iUtoB[v14];
    LODWORD(v14) = g_iYscale[v10[2]];
    v11[8] = *(_BYTE *)((int)v14 + v57 + v8);
    v11[7] = *(_BYTE *)((int)v14 - v58 + v8);
    v11[6] = *(_BYTE *)((int)v14 + v59 + v8);
    LODWORD(v14) = g_iYscale[v10[3]];
    v11[11] = *(_BYTE *)((int)v14 + v57 + v8);
    v11[10] = *(_BYTE *)((int)v14 - v58 + v8);
    v11[9] = *(_BYTE *)((int)v14 + v59 + v8);
    v16 = a5[2];
    v17 = v9[2];
    v60 = g_iVtoR[v16];
    v61 = g_iVtoG[v16] + g_iUtoG[v17];
    v62 = g_iUtoB[v17];
    LODWORD(v17) = g_iYscale[v10[4]];
    v11[14] = *(_BYTE *)((int)v17 + v60 + v8);
    v11[13] = *(_BYTE *)((int)v17 - v61 + v8);
    v11[12] = *(_BYTE *)((int)v17 + v62 + v8);
    LODWORD(v17) = g_iYscale[v10[5]];
    v11[17] = *(_BYTE *)((int)v17 + v60 + v8);
    v11[16] = *(_BYTE *)((int)v17 - v61 + v8);
    v11[15] = *(_BYTE *)((int)v17 + v62 + v8);
    v18 = v9[3];
    v19 = a5[3];
    v63 = g_iVtoR[v19];
    v64 = g_iVtoG[v19] + g_iUtoG[v18];
    v65 = g_iUtoB[v18];
    LODWORD(v18) = g_iYscale[v10[6]];
    v11[20] = *(_BYTE *)((int)v18 + v63 + v8);
    v11[19] = *(_BYTE *)((int)v18 - v64 + v8);
    v11[18] = *(_BYTE *)((int)v18 + v65 + v8);
    LODWORD(v18) = g_iYscale[v10[7]];
    v11[23] = *(_BYTE *)((int)v18 + v63 + v8);
    v11[22] = *(_BYTE *)((int)v18 - v64 + v8);
    v11[21] = *(_BYTE *)((int)v18 + v65 + v8);
    v20 = a5[4];
    v21 = v9[4];
    v22 = g_iVtoR[v20];
    v23 = g_iVtoG[v20] + g_iUtoG[v21];
    v67 = g_iUtoB[v21];
    LODWORD(v21) = g_iYscale[v10[8]];
    v11[26] = *(_BYTE *)((int)v21 + v22 + v8);
    v11[25] = *(_BYTE *)((int)v21 - v23 + v8);
    v11[24] = *(_BYTE *)((int)v21 + v67 + v8);
    LODWORD(v21) = g_iYscale[v10[9]];
    v11[29] = *(_BYTE *)((int)v21 + v22 + v8);
    v24 = g_rgiClapTabDec;
    v11[28] = *(_BYTE *)((int)v21 - v23 + v8);
    v11[27] = *(_BYTE *)((int)v21 + v67 + v8);
    v25 = v9[5];
    v26 = a5[5];
    v27 = g_iVtoG[v26] + g_iUtoG[v25];
    v28 = g_iVtoR[v26];
    v29 = g_iUtoB[v25];
    LODWORD(v25) = g_iYscale[v10[10]];
    v11[32] = *(_BYTE *)((int)v25 + v28 + v24);
    v11[31] = *(_BYTE *)((int)v25 - v27 + v24);
    v11[30] = *(_BYTE *)((int)v25 + v29 + v24);
    LODWORD(v25) = g_iYscale[v10[11]];
    v11[35] = *(_BYTE *)((int)v25 + v28 + v24);
    v11[34] = *(_BYTE *)((int)v25 - v27 + v24);
    v11[33] = *(_BYTE *)((int)v25 + v29 + v24);
    v30 = v9[6];
    v31 = a5[6];
    v32 = g_iVtoG[v31] + g_iUtoG[v30];
    v33 = g_iVtoR[v31];
    v34 = g_iUtoB[v30];
    LODWORD(v30) = g_iYscale[v69[12]];
    v68[38] = *(_BYTE *)((int)v30 + v33 + v24);
    v68[37] = *(_BYTE *)((int)v30 - v32 + v24);
    v68[36] = *(_BYTE *)((int)v30 + v34 + v24);
    LODWORD(v30) = g_iYscale[v69[13]];
    v68[41] = *(_BYTE *)((int)v30 + v33 + v24);
    v68[40] = *(_BYTE *)((int)v30 - v32 + v24);
    v68[39] = *(_BYTE *)((int)v30 + v34 + v24);
    v35 = a5[7];
    v36 = v70[7];
    v37 = g_iVtoR[v35];
    v38 = g_iVtoG[v35] + g_iUtoG[v36];
    v39 = g_iUtoB[v36];
    LODWORD(v36) = g_iYscale[v69[14]];
    v68[44] = *(_BYTE *)((int)v36 + v37 + v24);
    v68[43] = *(_BYTE *)((int)v36 - v38 + v24);
    v68[42] = *(_BYTE *)((int)v36 + v39 + v24);
    LODWORD(v36) = g_iYscale[v69[15]];
    v68[47] = *(_BYTE *)((int)v36 + v37 + v24);
    v68[46] = *(_BYTE *)((int)v36 - v38 + v24);
    v68[45] = *(_BYTE *)((int)v36 + v39 + v24);
    v70 += a7;
    a5 += a7;
    LODWORD(v36) = g_iYscale[v69[a6]];
    v68[a8 + 2] = *(_BYTE *)((int)v36 + v54 + v24);
    v68[a8 + 1] = *(_BYTE *)((int)v36 - v55 + g_rgiClapTabDec);
    v40 = g_rgiClapTabDec;
    v68[a8] = *(_BYTE *)((int)v36 + v56 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 1]];
    v68[a8 + 5] = *(_BYTE *)((int)v36 + v54 + v40);
    v68[a8 + 4] = *(_BYTE *)((int)v36 - v55 + g_rgiClapTabDec);
    v41 = g_rgiClapTabDec;
    v68[a8 + 3] = *(_BYTE *)((int)v36 + v56 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 2]];
    v68[a8 + 8] = *(_BYTE *)((int)v36 + v57 + v41);
    v68[a8 + 7] = *(_BYTE *)((int)v36 - v58 + g_rgiClapTabDec);
    v42 = g_rgiClapTabDec;
    v68[a8 + 6] = *(_BYTE *)((int)v36 + v59 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 3]];
    v68[a8 + 11] = *(_BYTE *)((int)v36 + v57 + v42);
    v68[a8 + 10] = *(_BYTE *)((int)v36 - v58 + g_rgiClapTabDec);
    v43 = g_rgiClapTabDec;
    v68[a8 + 9] = *(_BYTE *)((int)v36 + v59 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 4]];
    v68[a8 + 14] = *(_BYTE *)((int)v36 + v60 + v43);
    v68[a8 + 13] = *(_BYTE *)((int)v36 - v61 + g_rgiClapTabDec);
    v44 = g_rgiClapTabDec;
    v68[a8 + 12] = *(_BYTE *)((int)v36 + v62 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 5]];
    v68[a8 + 17] = *(_BYTE *)((int)v36 + v60 + v44);
    v68[a8 + 16] = *(_BYTE *)((int)v36 - v61 + g_rgiClapTabDec);
    v45 = g_rgiClapTabDec;
    v68[a8 + 15] = *(_BYTE *)((int)v36 + v62 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 6]];
    v68[a8 + 20] = *(_BYTE *)((int)v36 + v63 + v45);
    v68[a8 + 19] = *(_BYTE *)((int)v36 - v64 + g_rgiClapTabDec);
    v46 = g_rgiClapTabDec;
    v68[a8 + 18] = *(_BYTE *)((int)v36 + v65 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 7]];
    v68[a8 + 23] = *(_BYTE *)((int)v36 + v63 + v46);
    v68[a8 + 22] = *(_BYTE *)((int)v36 - v64 + g_rgiClapTabDec);
    v47 = g_rgiClapTabDec;
    v68[a8 + 21] = *(_BYTE *)((int)v36 + v65 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 8]];
    v68[a8 + 26] = *(_BYTE *)((int)v36 + v22 + v47);
    v68[a8 + 25] = *(_BYTE *)((int)v36 - v23 + g_rgiClapTabDec);
    v68[a8 + 24] = *(_BYTE *)((int)v36 + v67 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 9]];
    v68[a8 + 29] = *(_BYTE *)((int)v36 + v22 + g_rgiClapTabDec);
    LODWORD(v35) = v36 - v23;
    v48 = g_rgiClapTabDec;
    v68[a8 + 28] = *(_BYTE *)((int)v35 + g_rgiClapTabDec);
    v49 = v68;
    v68[a8 + 27] = *(_BYTE *)((int)v36 + v67 + v48);
    LODWORD(v36) = g_iYscale[v69[a6 + 10]];
    v50 = g_rgiClapTabDec;
    v68[a8 + 32] = *(_BYTE *)((int)v36 + v28 + g_rgiClapTabDec);
    v68[a8 + 31] = *(_BYTE *)((int)v36 - v27 + v50);
    v68[a8 + 30] = *(_BYTE *)((int)v36 + v29 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 11]];
    LODWORD(v35) = v36 + v28;
    v8 = g_rgiClapTabDec;
    v68[a8 + 35] = *(_BYTE *)((int)v35 + g_rgiClapTabDec);
    LODWORD(v35) = v36 - v27;
    v51 = v69;
    v68[a8 + 34] = *(_BYTE *)((int)v35 + v8);
    v68[a8 + 33] = *(_BYTE *)((int)v36 + v29 + v8);
    LODWORD(v36) = g_iYscale[v69[a6 + 12]];
    v68[a8 + 38] = *(_BYTE *)((int)v36 + v33 + v8);
    v68[a8 + 37] = *(_BYTE *)((int)v36 - v32 + v8);
    v68[a8 + 36] = *(_BYTE *)((int)v36 + v34 + v8);
    LODWORD(v36) = g_iYscale[v69[a6 + 13]];
    v68[a8 + 41] = *(_BYTE *)((int)v36 + v33 + v8);
    v11 = &v68[2 * a8];
    v68 = v11;
    v52 = (int)v36 - v32;
    v10 = &v69[2 * a6];
    v69 = v10;
    LOBYTE(v50) = *(_BYTE *)(v52 + v8);
    LODWORD(v52) = v36 + v34;
    v9 = v70;
    v49[a8 + 40] = v50;
    v49[a8 + 39] = *(_BYTE *)((int)v52 + v8);
    LODWORD(v36) = g_iYscale[v51[a6 + 14]];
    v49[a8 + 44] = *(_BYTE *)((int)v36 + v37 + v8);
    v49[a8 + 43] = *(_BYTE *)((int)v36 - v38 + v8);
    v49[a8 + 42] = *(_BYTE *)((int)v36 + v39 + v8);
    LODWORD(v36) = g_iYscale[v51[a6 + 15]];
    v49[a8 + 47] = *(_BYTE *)((int)v36 + v37 + v8);
    v53 = v66-- == 1;
    v49[a8 + 46] = *(_BYTE *)((int)v36 - v38 + v8);
    v49[a8 + 45] = *(_BYTE *)((int)v36 + v39 + v8);
  }
  while ( !v53 );
}

```

## disassembly

```asm
0x180024160  mov     rax, rsp
0x180024163  mov     [rax+8], rbx
0x180024167  mov     [rax+20h], r9
0x18002416b  mov     [rax+18h], r8
0x18002416f  mov     [rax+10h], rdx
0x180024173  push    rbp
0x180024174  push    rsi
0x180024175  push    rdi
0x180024176  push    r12
0x180024178  push    r13
0x18002417a  push    r14
0x18002417c  push    r15
0x18002417e  sub     rsp, 40h
0x180024182  mov     r14, cs:g_rgiClapTabDec
0x180024189  lea     rbp, __ImageBase
0x180024190  mov     rbx, r9
0x180024193  mov     [rsp+78h+var_48], 8
0x18002419b  mov     r11, r8
0x18002419e  mov     rdi, rdx
0x1800241a1  movzx   edx, byte ptr [rbx]
0x1800241a4  mov     rsi, [rsp+78h+arg_20]
0x1800241ac  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x1800241b4  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x1800241bc  movzx   eax, byte ptr [rsi]
0x1800241bf  mov     [rsp+78h+var_70], r9d
0x1800241c4  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x1800241cc  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x1800241d4  movzx   eax, byte ptr [r11]
0x1800241d8  mov     [rsp+78h+var_74], r8d
0x1800241dd  mov     [rsp+78h+var_78], r10d
0x1800241e1  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x1800241e8  lea     eax, [r10+rdx]
0x1800241ec  movsxd  rcx, eax
0x1800241ef  mov     al, [rcx+r14]
0x1800241f3  mov     [rdi+2], al
0x1800241f6  mov     eax, edx
0x1800241f8  sub     eax, r8d
0x1800241fb  cdqe
0x1800241fd  mov     cl, [rax+r14]
0x180024201  lea     eax, [rdx+r9]
0x180024205  mov     [rdi+1], cl
0x180024208  movsxd  rcx, eax
0x18002420b  mov     al, [rcx+r14]
0x18002420f  mov     [rdi], al
0x180024211  movzx   eax, byte ptr [r11+1]
0x180024216  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18002421d  lea     eax, [r10+rdx]
0x180024221  movsxd  rcx, eax
0x180024224  mov     al, [rcx+r14]
0x180024228  mov     [rdi+5], al
0x18002422b  mov     eax, edx
0x18002422d  sub     eax, r8d
0x180024230  cdqe
0x180024232  mov     cl, [rax+r14]
0x180024236  lea     eax, [rdx+r9]
0x18002423a  mov     [rdi+4], cl
0x18002423d  movsxd  rcx, eax
0x180024240  mov     al, [rcx+r14]
0x180024244  mov     [rdi+3], al
0x180024247  movzx   edx, byte ptr [rbx+1]
0x18002424b  movzx   eax, byte ptr [rsi+1]
0x18002424f  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x180024257  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x18002425f  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x180024267  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x18002426f  movzx   eax, byte ptr [r11+2]
0x180024274  mov     [rsp+78h+var_6C], r10d
0x180024279  mov     [rsp+78h+var_68], r8d
0x18002427e  mov     [rsp+78h+var_64], r9d
0x180024283  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18002428a  lea     eax, [rdx+r10]
0x18002428e  movsxd  rcx, eax
0x180024291  mov     al, [rcx+r14]
0x180024295  mov     [rdi+8], al
0x180024298  mov     eax, edx
0x18002429a  sub     eax, r8d
0x18002429d  cdqe
0x18002429f  mov     cl, [rax+r14]
0x1800242a3  lea     eax, [rdx+r9]
0x1800242a7  mov     [rdi+7], cl
0x1800242aa  movsxd  rcx, eax
0x1800242ad  mov     al, [rcx+r14]
0x1800242b1  mov     [rdi+6], al
0x1800242b4  movzx   eax, byte ptr [r11+3]
0x1800242b9  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x1800242c0  lea     eax, [rdx+r10]
0x1800242c4  movsxd  rcx, eax
0x1800242c7  mov     al, [rcx+r14]
0x1800242cb  mov     [rdi+0Bh], al
0x1800242ce  mov     eax, edx
0x1800242d0  sub     eax, r8d
0x1800242d3  cdqe
0x1800242d5  mov     cl, [rax+r14]
0x1800242d9  lea     eax, [rdx+r9]
0x1800242dd  mov     [rdi+0Ah], cl
0x1800242e0  movsxd  rcx, eax
0x1800242e3  mov     al, [rcx+r14]
0x1800242e7  mov     [rdi+9], al
0x1800242ea  movzx   eax, byte ptr [rsi+2]
0x1800242ee  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x1800242f6  movzx   edx, byte ptr [rbx+2]
0x1800242fa  mov     [rsp+78h+var_60], r10d
0x1800242ff  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x180024307  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x18002430f  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x180024317  movzx   eax, byte ptr [r11+4]
0x18002431c  mov     [rsp+78h+var_5C], r8d
0x180024321  mov     [rsp+78h+var_58], r9d
0x180024326  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18002432d  lea     eax, [rdx+r10]
0x180024331  movsxd  rcx, eax
0x180024334  mov     al, [rcx+r14]
0x180024338  mov     [rdi+0Eh], al
0x18002433b  mov     eax, edx
0x18002433d  sub     eax, r8d
0x180024340  cdqe
0x180024342  mov     cl, [rax+r14]
0x180024346  lea     eax, [rdx+r9]
0x18002434a  mov     [rdi+0Dh], cl
0x18002434d  movsxd  rcx, eax
0x180024350  mov     al, [rcx+r14]
0x180024354  mov     [rdi+0Ch], al
0x180024357  movzx   eax, byte ptr [r11+5]
0x18002435c  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180024363  lea     eax, [rdx+r10]
0x180024367  movsxd  rcx, eax
0x18002436a  mov     al, [rcx+r14]
0x18002436e  mov     [rdi+11h], al
0x180024371  mov     eax, edx
0x180024373  sub     eax, r8d
0x180024376  cdqe
0x180024378  mov     cl, [rax+r14]
0x18002437c  lea     eax, [rdx+r9]
0x180024380  mov     [rdi+10h], cl
0x180024383  movsxd  rcx, eax
0x180024386  mov     al, [rcx+r14]
0x18002438a  mov     [rdi+0Fh], al
0x18002438d  movzx   edx, byte ptr [rbx+3]
0x180024391  movzx   eax, byte ptr [rsi+3]
0x180024395  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x18002439d  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x1800243a5  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x1800243ad  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x1800243b5  movzx   eax, byte ptr [r11+6]
0x1800243ba  mov     [rsp+78h+var_54], r10d
0x1800243bf  mov     [rsp+78h+var_50], r8d
0x1800243c4  mov     [rsp+78h+var_4C], r9d
0x1800243c9  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x1800243d0  lea     eax, [rdx+r10]
0x1800243d4  movsxd  rcx, eax
0x1800243d7  mov     al, [rcx+r14]
0x1800243db  mov     [rdi+14h], al
0x1800243de  mov     eax, edx
0x1800243e0  sub     eax, r8d
0x1800243e3  cdqe
0x1800243e5  mov     cl, [rax+r14]
0x1800243e9  lea     eax, [rdx+r9]
0x1800243ed  mov     [rdi+13h], cl
0x1800243f0  movsxd  rcx, eax
0x1800243f3  mov     al, [rcx+r14]
0x1800243f7  mov     [rdi+12h], al
0x1800243fa  movzx   eax, byte ptr [r11+7]
0x1800243ff  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180024406  lea     eax, [rdx+r10]
0x18002440a  movsxd  rcx, eax
0x18002440d  mov     al, [rcx+r14]
0x180024411  mov     [rdi+17h], al
0x180024414  mov     eax, edx
0x180024416  sub     eax, r8d
0x180024419  cdqe
0x18002441b  mov     cl, [rax+r14]
0x18002441f  lea     eax, [rdx+r9]
0x180024423  mov     [rdi+16h], cl
0x180024426  movsxd  rcx, eax
0x180024429  mov     al, [rcx+r14]
0x18002442d  mov     [rdi+15h], al
0x180024430  movzx   eax, byte ptr [rsi+4]
0x180024434  movzx   edx, byte ptr [rbx+4]
0x180024438  mov     r13d, ss:rva g_iVtoR[rbp+rax*4]
0x180024440  mov     r15d, ss:rva g_iUtoG[rbp+rdx*4]
0x180024448  add     r15d, ss:rva g_iVtoG[rbp+rax*4]
0x180024450  mov     r12d, ss:rva g_iUtoB[rbp+rdx*4]
0x180024458  lea     r8, __ImageBase
0x18002445f  movzx   eax, byte ptr [r11+8]
0x180024464  mov     r10, [rsp+78h+arg_20]
0x18002446c  mov     r9, [rsp+78h+arg_10]
0x180024474  mov     [rsp+78h+var_44], r12d
0x180024479  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180024480  lea     eax, [rdx+r13]
0x180024484  movsxd  rcx, eax
0x180024487  mov     al, [rcx+r14]
0x18002448b  mov     [rdi+1Ah], al
0x18002448e  mov     eax, edx
0x180024490  sub     eax, r15d
0x180024493  cdqe
0x180024495  mov     cl, [rax+r14]
0x180024499  lea     eax, [rdx+r12]
0x18002449d  mov     [rdi+19h], cl
0x1800244a0  movsxd  rcx, eax
0x1800244a3  mov     al, [rcx+r14]
0x1800244a7  mov     [rdi+18h], al
0x1800244aa  movzx   eax, byte ptr [r11+9]
0x1800244af  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x1800244b6  lea     eax, [rdx+r13]
0x1800244ba  movsxd  rcx, eax
0x1800244bd  mov     al, [rcx+r14]
0x1800244c1  mov     [rdi+1Dh], al
0x1800244c4  mov     eax, edx
0x1800244c6  sub     eax, r15d
0x1800244c9  cdqe
0x1800244cb  mov     cl, [rax+r14]
0x1800244cf  lea     eax, [rdx+r12]
0x1800244d3  mov     r12, cs:g_rgiClapTabDec
0x1800244da  mov     [rdi+1Ch], cl
0x1800244dd  movsxd  rcx, eax
0x1800244e0  mov     al, [rcx+r14]
0x1800244e4  mov     [rdi+1Bh], al
0x1800244e7  movzx   edx, byte ptr [rbx+5]
0x1800244eb  movzx   eax, byte ptr [rsi+5]
0x1800244ef  mov     esi, ss:rva g_iUtoG[rbp+rdx*4]
0x1800244f6  add     esi, ss:rva g_iVtoG[rbp+rax*4]
0x1800244fd  mov     r14d, ss:rva g_iVtoR[rbp+rax*4]
0x180024505  mov     ebp, ss:rva g_iUtoB[rbp+rdx*4]
0x18002450c  movzx   eax, byte ptr [r11+0Ah]
0x180024511  mov     edx, rva g_iYscale[r8+rax*4]
0x180024519  lea     eax, [rdx+r14]
0x18002451d  movsxd  rcx, eax
0x180024520  mov     al, [rcx+r12]
0x180024524  mov     [rdi+20h], al
0x180024527  mov     eax, edx
0x180024529  sub     eax, esi
0x18002452b  cdqe
0x18002452d  mov     cl, [rax+r12]
0x180024531  lea     eax, [rdx+rbp]
0x180024534  mov     [rdi+1Fh], cl
0x180024537  movsxd  rcx, eax
0x18002453a  mov     al, [rcx+r12]
0x18002453e  mov     [rdi+1Eh], al
0x180024541  movzx   eax, byte ptr [r11+0Bh]
0x180024546  mov     edx, rva g_iYscale[r8+rax*4]
0x18002454e  lea     eax, [rdx+r14]
0x180024552  movsxd  rcx, eax
0x180024555  mov     al, [rcx+r12]
0x180024559  mov     [rdi+23h], al
0x18002455c  mov     eax, edx
0x18002455e  sub     eax, esi
0x180024560  cdqe
0x180024562  mov     cl, [rax+r12]
0x180024566  lea     eax, [rdx+rbp]
0x180024569  mov     [rdi+22h], cl
0x18002456c  movsxd  rcx, eax
0x18002456f  mov     al, [rcx+r12]
0x180024573  mov     [rdi+21h], al
0x180024576  movzx   edx, byte ptr [rbx+6]
0x18002457a  movzx   eax, byte ptr [r10+6]
0x18002457f  mov     r11d, rva g_iUtoG[r8+rdx*4]
0x180024587  add     r11d, rva g_iVtoG[r8+rax*4]
0x18002458f  mov     edi, rva g_iVtoR[r8+rax*4]
0x180024597  movzx   eax, byte ptr [r9+0Ch]
0x18002459c  mov     ebx, rva g_iUtoB[r8+rdx*4]
0x1800245a4  mov     edx, rva g_iYscale[r8+rax*4]
0x1800245ac  lea     eax, [rdx+rdi]
0x1800245af  movsxd  rcx, eax
0x1800245b2  mov     r8, [rsp+78h+arg_8]
0x1800245ba  mov     al, [rcx+r12]
0x1800245be  mov     [r8+26h], al
0x1800245c2  mov     eax, edx
0x1800245c4  sub     eax, r11d
0x1800245c7  cdqe
0x1800245c9  mov     cl, [rax+r12]
0x1800245cd  lea     eax, [rdx+rbx]
0x1800245d0  mov     [r8+25h], cl
0x1800245d4  movsxd  rcx, eax
0x1800245d7  mov     al, [rcx+r12]
0x1800245db  mov     [r8+24h], al
0x1800245df  movzx   eax, byte ptr [r9+0Dh]
0x1800245e4  lea     r9, __ImageBase
0x1800245eb  mov     edx, rva g_iYscale[r9+rax*4]
0x1800245f3  lea     eax, [rdx+rdi]
0x1800245f6  movsxd  rcx, eax
0x1800245f9  mov     al, [rcx+r12]
0x1800245fd  mov     [r8+29h], al
0x180024601  mov     eax, edx
0x180024603  sub     eax, r11d
0x180024606  cdqe
0x180024608  mov     cl, [rax+r12]
0x18002460c  lea     eax, [rdx+rbx]
0x18002460f  mov     [r8+28h], cl
0x180024613  movsxd  rcx, eax
0x180024616  mov     al, [rcx+r12]
0x18002461a  mov     rcx, [rsp+78h+arg_18]
0x180024622  mov     [r8+27h], al
0x180024626  movzx   eax, byte ptr [r10+7]
0x18002462b  movzx   edx, byte ptr [rcx+7]
0x18002462f  mov     r10d, rva g_iVtoR[r9+rax*4]
0x180024637  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18002463f  add     r8d, rva g_iVtoG[r9+rax*4]
0x180024647  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18002464f  lea     rdx, __ImageBase
0x180024656  mov     rax, [rsp+78h+arg_10]
  ... truncated ...
```
