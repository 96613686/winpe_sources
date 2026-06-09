# UpdateDstMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x1800408b0`
- end: `0x1800415d3`
- name: `?UpdateDstMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `3363`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800432c0`

## callees

- `0x1800408b0`

## pseudocode

```c
void __fastcall UpdateDstMBRGB32(
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
    v11[6] = *(_BYTE *)(v54 + (int)v12 + v8);
    v11[5] = *(_BYTE *)((int)v12 - v55 + v8);
    v11[4] = *(_BYTE *)((int)v12 + v56 + v8);
    v14 = v9[1];
    v15 = a5[1];
    v57 = g_iVtoR[v15];
    v58 = g_iVtoG[v15] + g_iUtoG[v14];
    v59 = g_iUtoB[v14];
    LODWORD(v14) = g_iYscale[v10[2]];
    v11[10] = *(_BYTE *)((int)v14 + v57 + v8);
    v11[9] = *(_BYTE *)((int)v14 - v58 + v8);
    v11[8] = *(_BYTE *)((int)v14 + v59 + v8);
    LODWORD(v14) = g_iYscale[v10[3]];
    v11[14] = *(_BYTE *)((int)v14 + v57 + v8);
    v11[13] = *(_BYTE *)((int)v14 - v58 + v8);
    v11[12] = *(_BYTE *)((int)v14 + v59 + v8);
    v16 = a5[2];
    v17 = v9[2];
    v60 = g_iVtoR[v16];
    v61 = g_iVtoG[v16] + g_iUtoG[v17];
    v62 = g_iUtoB[v17];
    LODWORD(v17) = g_iYscale[v10[4]];
    v11[18] = *(_BYTE *)((int)v17 + v60 + v8);
    v11[17] = *(_BYTE *)((int)v17 - v61 + v8);
    v11[16] = *(_BYTE *)((int)v17 + v62 + v8);
    LODWORD(v17) = g_iYscale[v10[5]];
    v11[22] = *(_BYTE *)((int)v17 + v60 + v8);
    v11[21] = *(_BYTE *)((int)v17 - v61 + v8);
    v11[20] = *(_BYTE *)((int)v17 + v62 + v8);
    v18 = v9[3];
    v19 = a5[3];
    v63 = g_iVtoR[v19];
    v64 = g_iVtoG[v19] + g_iUtoG[v18];
    v65 = g_iUtoB[v18];
    LODWORD(v18) = g_iYscale[v10[6]];
    v11[26] = *(_BYTE *)((int)v18 + v63 + v8);
    v11[25] = *(_BYTE *)((int)v18 - v64 + v8);
    v11[24] = *(_BYTE *)((int)v18 + v65 + v8);
    LODWORD(v18) = g_iYscale[v10[7]];
    v11[30] = *(_BYTE *)((int)v18 + v63 + v8);
    v11[29] = *(_BYTE *)((int)v18 - v64 + v8);
    v11[28] = *(_BYTE *)((int)v18 + v65 + v8);
    v20 = a5[4];
    v21 = v9[4];
    v22 = g_iVtoR[v20];
    v23 = g_iVtoG[v20] + g_iUtoG[v21];
    v67 = g_iUtoB[v21];
    LODWORD(v21) = g_iYscale[v10[8]];
    v11[34] = *(_BYTE *)((int)v21 + v22 + v8);
    v11[33] = *(_BYTE *)((int)v21 - v23 + v8);
    v11[32] = *(_BYTE *)((int)v21 + v67 + v8);
    LODWORD(v21) = g_iYscale[v10[9]];
    v11[38] = *(_BYTE *)((int)v21 + v22 + v8);
    v24 = g_rgiClapTabDec;
    v11[37] = *(_BYTE *)((int)v21 - v23 + v8);
    v11[36] = *(_BYTE *)((int)v21 + v67 + v8);
    v25 = v9[5];
    v26 = a5[5];
    v27 = g_iVtoG[v26] + g_iUtoG[v25];
    v28 = g_iVtoR[v26];
    v29 = g_iUtoB[v25];
    LODWORD(v25) = g_iYscale[v10[10]];
    v11[42] = *(_BYTE *)((int)v25 + v28 + v24);
    v11[41] = *(_BYTE *)((int)v25 - v27 + v24);
    v11[40] = *(_BYTE *)((int)v25 + v29 + v24);
    LODWORD(v25) = g_iYscale[v10[11]];
    v11[46] = *(_BYTE *)((int)v25 + v28 + v24);
    v11[45] = *(_BYTE *)((int)v25 - v27 + v24);
    v11[44] = *(_BYTE *)((int)v25 + v29 + v24);
    v30 = v9[6];
    v31 = a5[6];
    v32 = g_iVtoG[v31] + g_iUtoG[v30];
    v33 = g_iVtoR[v31];
    v34 = g_iUtoB[v30];
    LODWORD(v30) = g_iYscale[v69[12]];
    v68[50] = *(_BYTE *)((int)v30 + v33 + v24);
    v68[49] = *(_BYTE *)((int)v30 - v32 + v24);
    v68[48] = *(_BYTE *)((int)v30 + v34 + v24);
    LODWORD(v30) = g_iYscale[v69[13]];
    v68[54] = *(_BYTE *)((int)v30 + v33 + v24);
    v68[53] = *(_BYTE *)((int)v30 - v32 + v24);
    v68[52] = *(_BYTE *)((int)v30 + v34 + v24);
    v35 = a5[7];
    v36 = v70[7];
    v37 = g_iVtoR[v35];
    v38 = g_iVtoG[v35] + g_iUtoG[v36];
    v39 = g_iUtoB[v36];
    LODWORD(v36) = g_iYscale[v69[14]];
    v68[58] = *(_BYTE *)((int)v36 + v37 + v24);
    v68[57] = *(_BYTE *)((int)v36 - v38 + v24);
    v68[56] = *(_BYTE *)((int)v36 + v39 + v24);
    LODWORD(v36) = g_iYscale[v69[15]];
    v68[62] = *(_BYTE *)((int)v36 + v37 + v24);
    v68[61] = *(_BYTE *)((int)v36 - v38 + v24);
    v68[60] = *(_BYTE *)((int)v36 + v39 + v24);
    v70 += a7;
    a5 += a7;
    LODWORD(v36) = g_iYscale[v69[a6]];
    v68[a8 + 2] = *(_BYTE *)((int)v36 + v54 + v24);
    v68[a8 + 1] = *(_BYTE *)((int)v36 - v55 + g_rgiClapTabDec);
    v40 = g_rgiClapTabDec;
    v68[a8] = *(_BYTE *)((int)v36 + v56 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 1]];
    v68[a8 + 6] = *(_BYTE *)((int)v36 + v54 + v40);
    v68[a8 + 5] = *(_BYTE *)((int)v36 - v55 + g_rgiClapTabDec);
    v41 = g_rgiClapTabDec;
    v68[a8 + 4] = *(_BYTE *)((int)v36 + v56 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 2]];
    v68[a8 + 10] = *(_BYTE *)((int)v36 + v57 + v41);
    v68[a8 + 9] = *(_BYTE *)((int)v36 - v58 + g_rgiClapTabDec);
    v42 = g_rgiClapTabDec;
    v68[a8 + 8] = *(_BYTE *)((int)v36 + v59 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 3]];
    v68[a8 + 14] = *(_BYTE *)((int)v36 + v57 + v42);
    v68[a8 + 13] = *(_BYTE *)((int)v36 - v58 + g_rgiClapTabDec);
    v43 = g_rgiClapTabDec;
    v68[a8 + 12] = *(_BYTE *)((int)v36 + v59 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 4]];
    v68[a8 + 18] = *(_BYTE *)((int)v36 + v60 + v43);
    v68[a8 + 17] = *(_BYTE *)((int)v36 - v61 + g_rgiClapTabDec);
    v44 = g_rgiClapTabDec;
    v68[a8 + 16] = *(_BYTE *)((int)v36 + v62 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 5]];
    v68[a8 + 22] = *(_BYTE *)((int)v36 + v60 + v44);
    v68[a8 + 21] = *(_BYTE *)((int)v36 - v61 + g_rgiClapTabDec);
    v45 = g_rgiClapTabDec;
    v68[a8 + 20] = *(_BYTE *)((int)v36 + v62 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 6]];
    v68[a8 + 26] = *(_BYTE *)((int)v36 + v63 + v45);
    v68[a8 + 25] = *(_BYTE *)((int)v36 - v64 + g_rgiClapTabDec);
    v46 = g_rgiClapTabDec;
    v68[a8 + 24] = *(_BYTE *)((int)v36 + v65 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 7]];
    v68[a8 + 30] = *(_BYTE *)((int)v36 + v63 + v46);
    v68[a8 + 29] = *(_BYTE *)((int)v36 - v64 + g_rgiClapTabDec);
    v47 = g_rgiClapTabDec;
    v68[a8 + 28] = *(_BYTE *)((int)v36 + v65 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 8]];
    v68[a8 + 34] = *(_BYTE *)((int)v36 + v22 + v47);
    v68[a8 + 33] = *(_BYTE *)((int)v36 - v23 + g_rgiClapTabDec);
    v68[a8 + 32] = *(_BYTE *)((int)v36 + v67 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 9]];
    v68[a8 + 38] = *(_BYTE *)((int)v36 + v22 + g_rgiClapTabDec);
    LODWORD(v35) = v36 - v23;
    v48 = g_rgiClapTabDec;
    v68[a8 + 37] = *(_BYTE *)((int)v35 + g_rgiClapTabDec);
    v49 = v68;
    v68[a8 + 36] = *(_BYTE *)((int)v36 + v67 + v48);
    LODWORD(v36) = g_iYscale[v69[a6 + 10]];
    v50 = g_rgiClapTabDec;
    v68[a8 + 42] = *(_BYTE *)((int)v36 + v28 + g_rgiClapTabDec);
    v68[a8 + 41] = *(_BYTE *)((int)v36 - v27 + v50);
    v68[a8 + 40] = *(_BYTE *)((int)v36 + v29 + g_rgiClapTabDec);
    LODWORD(v36) = g_iYscale[v69[a6 + 11]];
    LODWORD(v35) = v36 + v28;
    v8 = g_rgiClapTabDec;
    v68[a8 + 46] = *(_BYTE *)((int)v35 + g_rgiClapTabDec);
    LODWORD(v35) = v36 - v27;
    v51 = v69;
    v68[a8 + 45] = *(_BYTE *)((int)v35 + v8);
    v68[a8 + 44] = *(_BYTE *)((int)v36 + v29 + v8);
    LODWORD(v36) = g_iYscale[v69[a6 + 12]];
    v68[a8 + 50] = *(_BYTE *)((int)v36 + v33 + v8);
    v68[a8 + 49] = *(_BYTE *)((int)v36 - v32 + v8);
    v68[a8 + 48] = *(_BYTE *)((int)v36 + v34 + v8);
    LODWORD(v36) = g_iYscale[v69[a6 + 13]];
    v68[a8 + 54] = *(_BYTE *)((int)v36 + v33 + v8);
    v11 = &v68[2 * a8];
    v68 = v11;
    v52 = (int)v36 - v32;
    v10 = &v69[2 * a6];
    v69 = v10;
    LOBYTE(v50) = *(_BYTE *)(v52 + v8);
    LODWORD(v52) = v36 + v34;
    v9 = v70;
    v49[a8 + 53] = v50;
    v49[a8 + 52] = *(_BYTE *)((int)v52 + v8);
    LODWORD(v36) = g_iYscale[v51[a6 + 14]];
    v49[a8 + 58] = *(_BYTE *)((int)v36 + v37 + v8);
    v49[a8 + 57] = *(_BYTE *)((int)v36 - v38 + v8);
    v49[a8 + 56] = *(_BYTE *)((int)v36 + v39 + v8);
    LODWORD(v36) = g_iYscale[v51[a6 + 15]];
    v49[a8 + 62] = *(_BYTE *)((int)v36 + v37 + v8);
    v53 = v66-- == 1;
    v49[a8 + 61] = *(_BYTE *)((int)v36 - v38 + v8);
    v49[a8 + 60] = *(_BYTE *)((int)v36 + v39 + v8);
  }
  while ( !v53 );
}

```

## disassembly

```asm
0x1800408b0  mov     rax, rsp
0x1800408b3  mov     [rax+8], rbx
0x1800408b7  mov     [rax+20h], r9
0x1800408bb  mov     [rax+18h], r8
0x1800408bf  mov     [rax+10h], rdx
0x1800408c3  push    rbp
0x1800408c4  push    rsi
0x1800408c5  push    rdi
0x1800408c6  push    r12
0x1800408c8  push    r13
0x1800408ca  push    r14
0x1800408cc  push    r15
0x1800408ce  sub     rsp, 40h
0x1800408d2  mov     r14, cs:g_rgiClapTabDec
0x1800408d9  lea     rbp, __ImageBase
0x1800408e0  mov     rbx, r9
0x1800408e3  mov     [rsp+78h+var_48], 8
0x1800408eb  mov     r11, r8
0x1800408ee  mov     rdi, rdx
0x1800408f1  movzx   edx, byte ptr [rbx]
0x1800408f4  mov     rsi, [rsp+78h+arg_20]
0x1800408fc  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x180040904  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x18004090c  movzx   eax, byte ptr [rsi]
0x18004090f  mov     [rsp+78h+var_70], r9d
0x180040914  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x18004091c  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x180040924  movzx   eax, byte ptr [r11]
0x180040928  mov     [rsp+78h+var_74], r8d
0x18004092d  mov     [rsp+78h+var_78], r10d
0x180040931  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040938  lea     eax, [r10+rdx]
0x18004093c  movsxd  rcx, eax
0x18004093f  mov     al, [rcx+r14]
0x180040943  mov     [rdi+2], al
0x180040946  mov     eax, edx
0x180040948  sub     eax, r8d
0x18004094b  cdqe
0x18004094d  mov     cl, [rax+r14]
0x180040951  lea     eax, [rdx+r9]
0x180040955  mov     [rdi+1], cl
0x180040958  movsxd  rcx, eax
0x18004095b  mov     al, [rcx+r14]
0x18004095f  mov     [rdi], al
0x180040961  movzx   eax, byte ptr [r11+1]
0x180040966  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18004096d  lea     eax, [r10+rdx]
0x180040971  movsxd  rcx, eax
0x180040974  mov     al, [rcx+r14]
0x180040978  mov     [rdi+6], al
0x18004097b  mov     eax, edx
0x18004097d  sub     eax, r8d
0x180040980  cdqe
0x180040982  mov     cl, [rax+r14]
0x180040986  lea     eax, [rdx+r9]
0x18004098a  mov     [rdi+5], cl
0x18004098d  movsxd  rcx, eax
0x180040990  mov     al, [rcx+r14]
0x180040994  mov     [rdi+4], al
0x180040997  movzx   edx, byte ptr [rbx+1]
0x18004099b  movzx   eax, byte ptr [rsi+1]
0x18004099f  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x1800409a7  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x1800409af  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x1800409b7  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x1800409bf  movzx   eax, byte ptr [r11+2]
0x1800409c4  mov     [rsp+78h+var_6C], r10d
0x1800409c9  mov     [rsp+78h+var_68], r8d
0x1800409ce  mov     [rsp+78h+var_64], r9d
0x1800409d3  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x1800409da  lea     eax, [rdx+r10]
0x1800409de  movsxd  rcx, eax
0x1800409e1  mov     al, [rcx+r14]
0x1800409e5  mov     [rdi+0Ah], al
0x1800409e8  mov     eax, edx
0x1800409ea  sub     eax, r8d
0x1800409ed  cdqe
0x1800409ef  mov     cl, [rax+r14]
0x1800409f3  lea     eax, [rdx+r9]
0x1800409f7  mov     [rdi+9], cl
0x1800409fa  movsxd  rcx, eax
0x1800409fd  mov     al, [rcx+r14]
0x180040a01  mov     [rdi+8], al
0x180040a04  movzx   eax, byte ptr [r11+3]
0x180040a09  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040a10  lea     eax, [rdx+r10]
0x180040a14  movsxd  rcx, eax
0x180040a17  mov     al, [rcx+r14]
0x180040a1b  mov     [rdi+0Eh], al
0x180040a1e  mov     eax, edx
0x180040a20  sub     eax, r8d
0x180040a23  cdqe
0x180040a25  mov     cl, [rax+r14]
0x180040a29  lea     eax, [rdx+r9]
0x180040a2d  mov     [rdi+0Dh], cl
0x180040a30  movsxd  rcx, eax
0x180040a33  mov     al, [rcx+r14]
0x180040a37  mov     [rdi+0Ch], al
0x180040a3a  movzx   eax, byte ptr [rsi+2]
0x180040a3e  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x180040a46  movzx   edx, byte ptr [rbx+2]
0x180040a4a  mov     [rsp+78h+var_60], r10d
0x180040a4f  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x180040a57  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x180040a5f  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x180040a67  movzx   eax, byte ptr [r11+4]
0x180040a6c  mov     [rsp+78h+var_5C], r8d
0x180040a71  mov     [rsp+78h+var_58], r9d
0x180040a76  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040a7d  lea     eax, [rdx+r10]
0x180040a81  movsxd  rcx, eax
0x180040a84  mov     al, [rcx+r14]
0x180040a88  mov     [rdi+12h], al
0x180040a8b  mov     eax, edx
0x180040a8d  sub     eax, r8d
0x180040a90  cdqe
0x180040a92  mov     cl, [rax+r14]
0x180040a96  lea     eax, [rdx+r9]
0x180040a9a  mov     [rdi+11h], cl
0x180040a9d  movsxd  rcx, eax
0x180040aa0  mov     al, [rcx+r14]
0x180040aa4  mov     [rdi+10h], al
0x180040aa7  movzx   eax, byte ptr [r11+5]
0x180040aac  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040ab3  lea     eax, [rdx+r10]
0x180040ab7  movsxd  rcx, eax
0x180040aba  mov     al, [rcx+r14]
0x180040abe  mov     [rdi+16h], al
0x180040ac1  mov     eax, edx
0x180040ac3  sub     eax, r8d
0x180040ac6  cdqe
0x180040ac8  mov     cl, [rax+r14]
0x180040acc  lea     eax, [rdx+r9]
0x180040ad0  mov     [rdi+15h], cl
0x180040ad3  movsxd  rcx, eax
0x180040ad6  mov     al, [rcx+r14]
0x180040ada  mov     [rdi+14h], al
0x180040add  movzx   edx, byte ptr [rbx+3]
0x180040ae1  movzx   eax, byte ptr [rsi+3]
0x180040ae5  mov     r9d, ss:rva g_iUtoB[rbp+rdx*4]
0x180040aed  mov     r10d, ss:rva g_iVtoR[rbp+rax*4]
0x180040af5  mov     r8d, ss:rva g_iUtoG[rbp+rdx*4]
0x180040afd  add     r8d, ss:rva g_iVtoG[rbp+rax*4]
0x180040b05  movzx   eax, byte ptr [r11+6]
0x180040b0a  mov     [rsp+78h+var_54], r10d
0x180040b0f  mov     [rsp+78h+var_50], r8d
0x180040b14  mov     [rsp+78h+var_4C], r9d
0x180040b19  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040b20  lea     eax, [rdx+r10]
0x180040b24  movsxd  rcx, eax
0x180040b27  mov     al, [rcx+r14]
0x180040b2b  mov     [rdi+1Ah], al
0x180040b2e  mov     eax, edx
0x180040b30  sub     eax, r8d
0x180040b33  cdqe
0x180040b35  mov     cl, [rax+r14]
0x180040b39  lea     eax, [rdx+r9]
0x180040b3d  mov     [rdi+19h], cl
0x180040b40  movsxd  rcx, eax
0x180040b43  mov     al, [rcx+r14]
0x180040b47  mov     [rdi+18h], al
0x180040b4a  movzx   eax, byte ptr [r11+7]
0x180040b4f  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040b56  lea     eax, [rdx+r10]
0x180040b5a  movsxd  rcx, eax
0x180040b5d  mov     al, [rcx+r14]
0x180040b61  mov     [rdi+1Eh], al
0x180040b64  mov     eax, edx
0x180040b66  sub     eax, r8d
0x180040b69  cdqe
0x180040b6b  mov     cl, [rax+r14]
0x180040b6f  lea     eax, [rdx+r9]
0x180040b73  mov     [rdi+1Dh], cl
0x180040b76  movsxd  rcx, eax
0x180040b79  mov     al, [rcx+r14]
0x180040b7d  mov     [rdi+1Ch], al
0x180040b80  movzx   eax, byte ptr [rsi+4]
0x180040b84  movzx   edx, byte ptr [rbx+4]
0x180040b88  mov     r13d, ss:rva g_iVtoR[rbp+rax*4]
0x180040b90  mov     r15d, ss:rva g_iUtoG[rbp+rdx*4]
0x180040b98  add     r15d, ss:rva g_iVtoG[rbp+rax*4]
0x180040ba0  mov     r12d, ss:rva g_iUtoB[rbp+rdx*4]
0x180040ba8  lea     r8, __ImageBase
0x180040baf  movzx   eax, byte ptr [r11+8]
0x180040bb4  mov     r10, [rsp+78h+arg_20]
0x180040bbc  mov     r9, [rsp+78h+arg_10]
0x180040bc4  mov     [rsp+78h+var_44], r12d
0x180040bc9  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040bd0  lea     eax, [rdx+r13]
0x180040bd4  movsxd  rcx, eax
0x180040bd7  mov     al, [rcx+r14]
0x180040bdb  mov     [rdi+22h], al
0x180040bde  mov     eax, edx
0x180040be0  sub     eax, r15d
0x180040be3  cdqe
0x180040be5  mov     cl, [rax+r14]
0x180040be9  lea     eax, [rdx+r12]
0x180040bed  mov     [rdi+21h], cl
0x180040bf0  movsxd  rcx, eax
0x180040bf3  mov     al, [rcx+r14]
0x180040bf7  mov     [rdi+20h], al
0x180040bfa  movzx   eax, byte ptr [r11+9]
0x180040bff  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x180040c06  lea     eax, [rdx+r13]
0x180040c0a  movsxd  rcx, eax
0x180040c0d  mov     al, [rcx+r14]
0x180040c11  mov     [rdi+26h], al
0x180040c14  mov     eax, edx
0x180040c16  sub     eax, r15d
0x180040c19  cdqe
0x180040c1b  mov     cl, [rax+r14]
0x180040c1f  lea     eax, [rdx+r12]
0x180040c23  mov     r12, cs:g_rgiClapTabDec
0x180040c2a  mov     [rdi+25h], cl
0x180040c2d  movsxd  rcx, eax
0x180040c30  mov     al, [rcx+r14]
0x180040c34  mov     [rdi+24h], al
0x180040c37  movzx   edx, byte ptr [rbx+5]
0x180040c3b  movzx   eax, byte ptr [rsi+5]
0x180040c3f  mov     esi, ss:rva g_iUtoG[rbp+rdx*4]
0x180040c46  add     esi, ss:rva g_iVtoG[rbp+rax*4]
0x180040c4d  mov     r14d, ss:rva g_iVtoR[rbp+rax*4]
0x180040c55  mov     ebp, ss:rva g_iUtoB[rbp+rdx*4]
0x180040c5c  movzx   eax, byte ptr [r11+0Ah]
0x180040c61  mov     edx, rva g_iYscale[r8+rax*4]
0x180040c69  lea     eax, [rdx+r14]
0x180040c6d  movsxd  rcx, eax
0x180040c70  mov     al, [rcx+r12]
0x180040c74  mov     [rdi+2Ah], al
0x180040c77  mov     eax, edx
0x180040c79  sub     eax, esi
0x180040c7b  cdqe
0x180040c7d  mov     cl, [rax+r12]
0x180040c81  lea     eax, [rdx+rbp]
0x180040c84  mov     [rdi+29h], cl
0x180040c87  movsxd  rcx, eax
0x180040c8a  mov     al, [rcx+r12]
0x180040c8e  mov     [rdi+28h], al
0x180040c91  movzx   eax, byte ptr [r11+0Bh]
0x180040c96  mov     edx, rva g_iYscale[r8+rax*4]
0x180040c9e  lea     eax, [rdx+r14]
0x180040ca2  movsxd  rcx, eax
0x180040ca5  mov     al, [rcx+r12]
0x180040ca9  mov     [rdi+2Eh], al
0x180040cac  mov     eax, edx
0x180040cae  sub     eax, esi
0x180040cb0  cdqe
0x180040cb2  mov     cl, [rax+r12]
0x180040cb6  lea     eax, [rdx+rbp]
0x180040cb9  mov     [rdi+2Dh], cl
0x180040cbc  movsxd  rcx, eax
0x180040cbf  mov     al, [rcx+r12]
0x180040cc3  mov     [rdi+2Ch], al
0x180040cc6  movzx   edx, byte ptr [rbx+6]
0x180040cca  movzx   eax, byte ptr [r10+6]
0x180040ccf  mov     r11d, rva g_iUtoG[r8+rdx*4]
0x180040cd7  add     r11d, rva g_iVtoG[r8+rax*4]
0x180040cdf  mov     edi, rva g_iVtoR[r8+rax*4]
0x180040ce7  movzx   eax, byte ptr [r9+0Ch]
0x180040cec  mov     ebx, rva g_iUtoB[r8+rdx*4]
0x180040cf4  mov     edx, rva g_iYscale[r8+rax*4]
0x180040cfc  lea     eax, [rdx+rdi]
0x180040cff  movsxd  rcx, eax
0x180040d02  mov     r8, [rsp+78h+arg_8]
0x180040d0a  mov     al, [rcx+r12]
0x180040d0e  mov     [r8+32h], al
0x180040d12  mov     eax, edx
0x180040d14  sub     eax, r11d
0x180040d17  cdqe
0x180040d19  mov     cl, [rax+r12]
0x180040d1d  lea     eax, [rdx+rbx]
0x180040d20  mov     [r8+31h], cl
0x180040d24  movsxd  rcx, eax
0x180040d27  mov     al, [rcx+r12]
0x180040d2b  mov     [r8+30h], al
0x180040d2f  movzx   eax, byte ptr [r9+0Dh]
0x180040d34  lea     r9, __ImageBase
0x180040d3b  mov     edx, rva g_iYscale[r9+rax*4]
0x180040d43  lea     eax, [rdx+rdi]
0x180040d46  movsxd  rcx, eax
0x180040d49  mov     al, [rcx+r12]
0x180040d4d  mov     [r8+36h], al
0x180040d51  mov     eax, edx
0x180040d53  sub     eax, r11d
0x180040d56  cdqe
0x180040d58  mov     cl, [rax+r12]
0x180040d5c  lea     eax, [rdx+rbx]
0x180040d5f  mov     [r8+35h], cl
0x180040d63  movsxd  rcx, eax
0x180040d66  mov     al, [rcx+r12]
0x180040d6a  mov     rcx, [rsp+78h+arg_18]
0x180040d72  mov     [r8+34h], al
0x180040d76  movzx   eax, byte ptr [r10+7]
0x180040d7b  movzx   edx, byte ptr [rcx+7]
0x180040d7f  mov     r10d, rva g_iVtoR[r9+rax*4]
0x180040d87  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x180040d8f  add     r8d, rva g_iVtoG[r9+rax*4]
0x180040d97  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x180040d9f  lea     rdx, __ImageBase
0x180040da6  mov     rax, [rsp+78h+arg_10]
  ... truncated ...
```
