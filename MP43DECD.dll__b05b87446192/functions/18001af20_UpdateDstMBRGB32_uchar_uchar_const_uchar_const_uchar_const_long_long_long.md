# UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001af20`
- end: `0x18001bc46`
- name: `?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z`
- size: `3366`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001d7f0`

## callees

- `0x18001af20`

## pseudocode

```c
void __fastcall UpdateDstMBRGB32(
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
    v11[6] = v7[v55 + (int)v12];
    v11[5] = v7[(int)v12 - v56];
    v11[4] = v7[(int)v12 + v57];
    v14 = v9[1];
    v15 = v8[1];
    v58 = *((_DWORD *)&g_iVtoR + v15);
    v59 = *((_DWORD *)&g_iVtoG + v15) + *((_DWORD *)&g_iUtoG + v14);
    v60 = *((_DWORD *)&g_iUtoB + v14);
    LODWORD(v14) = *((_DWORD *)&g_iYscale + v10[2]);
    v11[10] = v7[(int)v14 + v58];
    v11[9] = v7[(int)v14 - v59];
    v11[8] = v7[(int)v14 + v60];
    LODWORD(v14) = *((_DWORD *)&g_iYscale + v10[3]);
    v11[14] = v7[(int)v14 + v58];
    v11[13] = v7[(int)v14 - v59];
    v11[12] = v7[(int)v14 + v60];
    v16 = v8[2];
    v61 = *((_DWORD *)&g_iVtoR + v16);
    v17 = v9[2];
    v62 = *((_DWORD *)&g_iVtoG + v16) + *((_DWORD *)&g_iUtoG + v17);
    v63 = *((_DWORD *)&g_iUtoB + v17);
    LODWORD(v17) = *((_DWORD *)&g_iYscale + v10[4]);
    v11[18] = v7[(int)v17 + v61];
    v11[17] = v7[(int)v17 - v62];
    v11[16] = v7[(int)v17 + v63];
    LODWORD(v17) = *((_DWORD *)&g_iYscale + v10[5]);
    v11[22] = v7[(int)v17 + v61];
    v11[21] = v7[(int)v17 - v62];
    v11[20] = v7[(int)v17 + v63];
    v18 = v9[3];
    v19 = v8[3];
    v64 = *((_DWORD *)&g_iVtoR + v19);
    v65 = *((_DWORD *)&g_iVtoG + v19) + *((_DWORD *)&g_iUtoG + v18);
    v66 = *((_DWORD *)&g_iUtoB + v18);
    LODWORD(v18) = *((_DWORD *)&g_iYscale + v10[6]);
    v11[26] = v7[(int)v18 + v64];
    v11[25] = v7[(int)v18 - v65];
    v11[24] = v7[(int)v18 + v66];
    LODWORD(v18) = *((_DWORD *)&g_iYscale + v10[7]);
    v11[30] = v7[(int)v18 + v64];
    v11[29] = v7[(int)v18 - v65];
    v11[28] = v7[(int)v18 + v66];
    v20 = v9[4];
    v21 = v8[4];
    v22 = *((_DWORD *)&g_iVtoG + v21) + *((_DWORD *)&g_iUtoG + v20);
    v23 = *((_DWORD *)&g_iVtoR + v21);
    v68 = *((_DWORD *)&g_iUtoB + v20);
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v10[8]);
    v11[34] = v7[(int)v20 + v23];
    v11[33] = v7[(int)v20 - v22];
    v11[32] = v7[(int)v20 + v68];
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v10[9]);
    v11[38] = v7[(int)v20 + v23];
    v24 = g_rgiClapTabDec;
    v11[37] = v7[(int)v20 - v22];
    v11[36] = v7[(int)v20 + v68];
    v25 = v9[5];
    v26 = v8[5];
    v27 = *((_DWORD *)&g_iVtoG + v26) + *((_DWORD *)&g_iUtoG + v25);
    v28 = *((_DWORD *)&g_iVtoR + v26);
    v29 = *((_DWORD *)&g_iUtoB + v25);
    LODWORD(v25) = *((_DWORD *)&g_iYscale + v10[10]);
    v11[42] = v24[(int)v25 + v28];
    v11[41] = v24[(int)v25 - v27];
    v11[40] = v24[(int)v25 + v29];
    LODWORD(v25) = *((_DWORD *)&g_iYscale + v10[11]);
    v11[46] = v24[(int)v25 + v28];
    v11[45] = v24[(int)v25 - v27];
    v11[44] = v24[(int)v25 + v29];
    v30 = v8[6];
    v31 = v71[6];
    v32 = *((_DWORD *)&g_iVtoR + v30);
    v33 = *((_DWORD *)&g_iVtoG + v30) + *((_DWORD *)&g_iUtoG + v31);
    v34 = *((_DWORD *)&g_iUtoB + v31);
    LODWORD(v31) = *((_DWORD *)&g_iYscale + v70[12]);
    v69[50] = v24[(int)v31 + v32];
    v69[49] = v24[(int)v31 - v33];
    v69[48] = v24[(int)v31 + v34];
    LODWORD(v31) = *((_DWORD *)&g_iYscale + v70[13]);
    v69[54] = v24[(int)v31 + v32];
    v69[53] = v24[(int)v31 - v33];
    v69[52] = v24[(int)v31 + v34];
    v35 = v71[7];
    v36 = v72[7];
    v37 = *((_DWORD *)&g_iVtoG + v36) + *((_DWORD *)&g_iUtoG + v35);
    v38 = *((_DWORD *)&g_iVtoR + v36);
    v39 = *((_DWORD *)&g_iUtoB + v35);
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[14]);
    v69[58] = v24[(int)v35 + v38];
    v69[57] = v24[(int)v35 - v37];
    v69[56] = v24[(int)v35 + v39];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[15]);
    v69[62] = v24[(int)v35 + v38];
    v69[61] = v24[(int)v35 - v37];
    v69[60] = v24[(int)v35 + v39];
    v71 += a6;
    v72 += a6;
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5]);
    v69[a7 + 2] = v24[(int)v35 + v55];
    v69[a7 + 1] = g_rgiClapTabDec[(int)v35 - v56];
    v40 = g_rgiClapTabDec;
    v69[a7] = g_rgiClapTabDec[(int)v35 + v57];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 1]);
    v69[a7 + 6] = v40[(int)v35 + v55];
    v69[a7 + 5] = g_rgiClapTabDec[(int)v35 - v56];
    v41 = g_rgiClapTabDec;
    v69[a7 + 4] = g_rgiClapTabDec[(int)v35 + v57];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 2]);
    v69[a7 + 10] = v41[(int)v35 + v58];
    v69[a7 + 9] = g_rgiClapTabDec[(int)v35 - v59];
    v42 = g_rgiClapTabDec;
    v69[a7 + 8] = g_rgiClapTabDec[(int)v35 + v60];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 3]);
    v69[a7 + 14] = v42[(int)v35 + v58];
    v69[a7 + 13] = g_rgiClapTabDec[(int)v35 - v59];
    v43 = g_rgiClapTabDec;
    v69[a7 + 12] = g_rgiClapTabDec[(int)v35 + v60];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 4]);
    v69[a7 + 18] = v43[(int)v35 + v61];
    v69[a7 + 17] = g_rgiClapTabDec[(int)v35 - v62];
    v44 = g_rgiClapTabDec;
    v69[a7 + 16] = g_rgiClapTabDec[(int)v35 + v63];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 5]);
    v69[a7 + 22] = v44[(int)v35 + v61];
    v69[a7 + 21] = g_rgiClapTabDec[(int)v35 - v62];
    v45 = g_rgiClapTabDec;
    v69[a7 + 20] = g_rgiClapTabDec[(int)v35 + v63];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 6]);
    v69[a7 + 26] = v45[(int)v35 + v64];
    v69[a7 + 25] = g_rgiClapTabDec[(int)v35 - v65];
    v46 = g_rgiClapTabDec;
    v69[a7 + 24] = g_rgiClapTabDec[(int)v35 + v66];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 7]);
    v69[a7 + 30] = v46[(int)v35 + v64];
    v69[a7 + 29] = g_rgiClapTabDec[(int)v35 - v65];
    v47 = g_rgiClapTabDec;
    v69[a7 + 28] = g_rgiClapTabDec[(int)v35 + v66];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 8]);
    v69[a7 + 34] = v47[(int)v35 + v23];
    v69[a7 + 33] = g_rgiClapTabDec[(int)v35 - v22];
    v69[a7 + 32] = g_rgiClapTabDec[(int)v35 + v68];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 9]);
    v69[a7 + 38] = g_rgiClapTabDec[(int)v35 + v23];
    LODWORD(v36) = v35 - v22;
    v48 = g_rgiClapTabDec;
    v69[a7 + 37] = g_rgiClapTabDec[(int)v36];
    v49 = v69;
    v69[a7 + 36] = v48[(int)v35 + v68];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 10]);
    v50 = g_rgiClapTabDec;
    v69[a7 + 42] = g_rgiClapTabDec[(int)v35 + v28];
    v69[a7 + 41] = v50[(int)v35 - v27];
    v69[a7 + 40] = g_rgiClapTabDec[(int)v35 + v29];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 11]);
    LODWORD(v36) = v35 + v28;
    v7 = g_rgiClapTabDec;
    v69[a7 + 46] = g_rgiClapTabDec[(int)v36];
    LODWORD(v36) = v35 - v27;
    v51 = v70;
    v69[a7 + 45] = v7[(int)v36];
    v69[a7 + 44] = v7[(int)v35 + v29];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 12]);
    v69[a7 + 50] = v7[(int)v35 + v32];
    v69[a7 + 49] = v7[(int)v35 - v33];
    v69[a7 + 48] = v7[(int)v35 + v34];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v70[a5 + 13]);
    v69[a7 + 54] = v7[(int)v35 + v32];
    v11 = &v69[2 * a7];
    v69 = v11;
    v52 = (int)v35 - v33;
    v10 = &v70[2 * a5];
    v70 = v10;
    LOBYTE(v50) = v7[v52];
    LODWORD(v52) = v35 + v34;
    v8 = v72;
    v49[a7 + 53] = (unsigned __int8)v50;
    v49[a7 + 52] = v7[(int)v52];
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v51[a5 + 14]);
    v49[a7 + 58] = v7[(int)v35 + v38];
    v49[a7 + 57] = v7[(int)v35 - v37];
    v49[a7 + 56] = v7[(int)v35 + v39];
    v53 = v51[a5 + 15];
    v9 = v71;
    LODWORD(v35) = *((_DWORD *)&g_iYscale + v53);
    v49[a7 + 62] = v7[(int)v35 + v38];
    v54 = v67-- == 1;
    v49[a7 + 61] = v7[(int)v35 - v37];
    v49[a7 + 60] = v7[(int)v35 + v39];
  }
  while ( !v54 );
}

```

## disassembly

```asm
0x18001af20  mov     rax, rsp
0x18001af23  mov     [rax+20h], r9
0x18001af27  mov     [rax+18h], r8
0x18001af2b  mov     [rax+10h], rdx
0x18001af2f  mov     [rax+8], rcx
0x18001af33  push    rbx
0x18001af34  push    rbp
0x18001af35  push    rsi
0x18001af36  push    rdi
0x18001af37  push    r12
0x18001af39  push    r13
0x18001af3b  push    r14
0x18001af3d  push    r15
0x18001af3f  sub     rsp, 48h
0x18001af43  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001af4a  lea     rbp, __ImageBase
0x18001af51  mov     rbx, r9
0x18001af54  mov     [rsp+88h+var_58], 8
0x18001af5c  mov     rsi, r8
0x18001af5f  mov     r11, rdx
0x18001af62  mov     rdi, rcx
0x18001af65  movzx   edx, byte ptr [rsi]
0x18001af68  movzx   eax, byte ptr [rbx]
0x18001af6b  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001af73  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001af7b  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001af83  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001af8b  movzx   eax, byte ptr [r11]
0x18001af8f  mov     [rsp+88h+var_84], r8d
0x18001af94  mov     [rsp+88h+var_88], r10d
0x18001af98  mov     [rsp+88h+var_80], r9d
0x18001af9d  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001afa4  lea     eax, [r10+rdx]
0x18001afa8  movsxd  rcx, eax
0x18001afab  mov     al, [rcx+r14]
0x18001afaf  mov     [rdi+2], al
0x18001afb2  mov     eax, edx
0x18001afb4  sub     eax, r8d
0x18001afb7  cdqe
0x18001afb9  mov     cl, [rax+r14]
0x18001afbd  lea     eax, [rdx+r9]
0x18001afc1  mov     [rdi+1], cl
0x18001afc4  movsxd  rcx, eax
0x18001afc7  mov     al, [rcx+r14]
0x18001afcb  mov     [rdi], al
0x18001afcd  movzx   eax, byte ptr [r11+1]
0x18001afd2  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001afd9  lea     eax, [r10+rdx]
0x18001afdd  movsxd  rcx, eax
0x18001afe0  mov     al, [rcx+r14]
0x18001afe4  mov     [rdi+6], al
0x18001afe7  mov     eax, edx
0x18001afe9  sub     eax, r8d
0x18001afec  cdqe
0x18001afee  mov     cl, [rax+r14]
0x18001aff2  lea     eax, [rdx+r9]
0x18001aff6  mov     [rdi+5], cl
0x18001aff9  movsxd  rcx, eax
0x18001affc  mov     al, [rcx+r14]
0x18001b000  mov     [rdi+4], al
0x18001b003  movzx   edx, byte ptr [rsi+1]
0x18001b007  movzx   eax, byte ptr [rbx+1]
0x18001b00b  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001b013  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001b01b  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001b023  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001b02b  movzx   eax, byte ptr [r11+2]
0x18001b030  mov     [rsp+88h+var_7C], r10d
0x18001b035  mov     [rsp+88h+var_78], r8d
0x18001b03a  mov     [rsp+88h+var_74], r9d
0x18001b03f  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b046  lea     eax, [rdx+r10]
0x18001b04a  movsxd  rcx, eax
0x18001b04d  mov     al, [rcx+r14]
0x18001b051  mov     [rdi+0Ah], al
0x18001b054  mov     eax, edx
0x18001b056  sub     eax, r8d
0x18001b059  cdqe
0x18001b05b  mov     cl, [rax+r14]
0x18001b05f  lea     eax, [rdx+r9]
0x18001b063  mov     [rdi+9], cl
0x18001b066  movsxd  rcx, eax
0x18001b069  mov     al, [rcx+r14]
0x18001b06d  mov     [rdi+8], al
0x18001b070  movzx   eax, byte ptr [r11+3]
0x18001b075  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b07c  lea     eax, [rdx+r10]
0x18001b080  movsxd  rcx, eax
0x18001b083  mov     al, [rcx+r14]
0x18001b087  mov     [rdi+0Eh], al
0x18001b08a  mov     eax, edx
0x18001b08c  sub     eax, r8d
0x18001b08f  cdqe
0x18001b091  mov     cl, [rax+r14]
0x18001b095  lea     eax, [rdx+r9]
0x18001b099  mov     [rdi+0Dh], cl
0x18001b09c  movsxd  rcx, eax
0x18001b09f  mov     al, [rcx+r14]
0x18001b0a3  mov     [rdi+0Ch], al
0x18001b0a6  movzx   eax, byte ptr [rbx+2]
0x18001b0aa  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001b0b2  mov     [rsp+88h+var_70], r10d
0x18001b0b7  movzx   edx, byte ptr [rsi+2]
0x18001b0bb  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001b0c3  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001b0cb  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001b0d3  movzx   eax, byte ptr [r11+4]
0x18001b0d8  mov     [rsp+88h+var_6C], r8d
0x18001b0dd  mov     [rsp+88h+var_68], r9d
0x18001b0e2  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b0e9  lea     eax, [rdx+r10]
0x18001b0ed  movsxd  rcx, eax
0x18001b0f0  mov     al, [rcx+r14]
0x18001b0f4  mov     [rdi+12h], al
0x18001b0f7  mov     eax, edx
0x18001b0f9  sub     eax, r8d
0x18001b0fc  cdqe
0x18001b0fe  mov     cl, [rax+r14]
0x18001b102  lea     eax, [rdx+r9]
0x18001b106  mov     [rdi+11h], cl
0x18001b109  movsxd  rcx, eax
0x18001b10c  mov     al, [rcx+r14]
0x18001b110  mov     [rdi+10h], al
0x18001b113  movzx   eax, byte ptr [r11+5]
0x18001b118  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b11f  lea     eax, [rdx+r10]
0x18001b123  movsxd  rcx, eax
0x18001b126  mov     al, [rcx+r14]
0x18001b12a  mov     [rdi+16h], al
0x18001b12d  mov     eax, edx
0x18001b12f  sub     eax, r8d
0x18001b132  cdqe
0x18001b134  mov     cl, [rax+r14]
0x18001b138  lea     eax, [rdx+r9]
0x18001b13c  mov     [rdi+15h], cl
0x18001b13f  movsxd  rcx, eax
0x18001b142  mov     al, [rcx+r14]
0x18001b146  mov     [rdi+14h], al
0x18001b149  movzx   edx, byte ptr [rsi+3]
0x18001b14d  movzx   eax, byte ptr [rbx+3]
0x18001b151  mov     r9d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001b159  mov     r10d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001b161  mov     r8d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001b169  add     r8d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001b171  movzx   eax, byte ptr [r11+6]
0x18001b176  mov     [rsp+88h+var_64], r10d
0x18001b17b  mov     [rsp+88h+var_60], r8d
0x18001b180  mov     [rsp+88h+var_5C], r9d
0x18001b185  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b18c  lea     eax, [rdx+r10]
0x18001b190  movsxd  rcx, eax
0x18001b193  mov     al, [rcx+r14]
0x18001b197  mov     [rdi+1Ah], al
0x18001b19a  mov     eax, edx
0x18001b19c  sub     eax, r8d
0x18001b19f  cdqe
0x18001b1a1  mov     cl, [rax+r14]
0x18001b1a5  lea     eax, [rdx+r9]
0x18001b1a9  mov     [rdi+19h], cl
0x18001b1ac  movsxd  rcx, eax
0x18001b1af  mov     al, [rcx+r14]
0x18001b1b3  mov     [rdi+18h], al
0x18001b1b6  movzx   eax, byte ptr [r11+7]
0x18001b1bb  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b1c2  lea     eax, [rdx+r10]
0x18001b1c6  movsxd  rcx, eax
0x18001b1c9  mov     al, [rcx+r14]
0x18001b1cd  mov     [rdi+1Eh], al
0x18001b1d0  mov     eax, edx
0x18001b1d2  sub     eax, r8d
0x18001b1d5  cdqe
0x18001b1d7  mov     cl, [rax+r14]
0x18001b1db  lea     eax, [rdx+r9]
0x18001b1df  mov     [rdi+1Dh], cl
0x18001b1e2  movsxd  rcx, eax
0x18001b1e5  mov     al, [rcx+r14]
0x18001b1e9  mov     [rdi+1Ch], al
0x18001b1ec  movzx   edx, byte ptr [rsi+4]
0x18001b1f0  movzx   eax, byte ptr [rbx+4]
0x18001b1f4  mov     r15d, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001b1fc  add     r15d, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001b204  mov     r13d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001b20c  mov     r12d, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001b214  movzx   eax, byte ptr [r11+8]
0x18001b219  lea     r10, __ImageBase
0x18001b220  mov     r9, [rsp+88h+arg_8]
0x18001b228  mov     [rsp+88h+var_54], r12d
0x18001b22d  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b234  lea     eax, [rdx+r13]
0x18001b238  movsxd  rcx, eax
0x18001b23b  mov     al, [rcx+r14]
0x18001b23f  mov     [rdi+22h], al
0x18001b242  mov     eax, edx
0x18001b244  sub     eax, r15d
0x18001b247  cdqe
0x18001b249  mov     cl, [rax+r14]
0x18001b24d  lea     eax, [rdx+r12]
0x18001b251  mov     [rdi+21h], cl
0x18001b254  movsxd  rcx, eax
0x18001b257  mov     al, [rcx+r14]
0x18001b25b  mov     [rdi+20h], al
0x18001b25e  movzx   eax, byte ptr [r11+9]
0x18001b263  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001b26a  lea     eax, [rdx+r13]
0x18001b26e  movsxd  rcx, eax
0x18001b271  mov     al, [rcx+r14]
0x18001b275  mov     [rdi+26h], al
0x18001b278  mov     eax, edx
0x18001b27a  sub     eax, r15d
0x18001b27d  cdqe
0x18001b27f  mov     cl, [rax+r14]
0x18001b283  lea     eax, [rdx+r12]
0x18001b287  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001b28e  mov     [rdi+25h], cl
0x18001b291  movsxd  rcx, eax
0x18001b294  mov     al, [rcx+r14]
0x18001b298  mov     [rdi+24h], al
0x18001b29b  movzx   edx, byte ptr [rsi+5]
0x18001b29f  movzx   eax, byte ptr [rbx+5]
0x18001b2a3  mov     esi, ss:rva ?g_iUtoG@@3PAJA[rbp+rdx*4]; long near * g_iUtoG ...
0x18001b2aa  add     esi, ss:rva ?g_iVtoG@@3PAJA[rbp+rax*4]; long near * g_iVtoG ...
0x18001b2b1  mov     r14d, ss:rva ?g_iVtoR@@3PAJA[rbp+rax*4]; long near * g_iVtoR ...
0x18001b2b9  mov     ebp, ss:rva ?g_iUtoB@@3PAJA[rbp+rdx*4]; long near * g_iUtoB ...
0x18001b2c0  movzx   eax, byte ptr [r11+0Ah]
0x18001b2c5  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001b2cd  lea     eax, [rdx+r14]
0x18001b2d1  movsxd  rcx, eax
0x18001b2d4  mov     al, [rcx+r12]
0x18001b2d8  mov     [rdi+2Ah], al
0x18001b2db  mov     eax, edx
0x18001b2dd  sub     eax, esi
0x18001b2df  cdqe
0x18001b2e1  mov     cl, [rax+r12]
0x18001b2e5  lea     eax, [rdx+rbp]
0x18001b2e8  mov     [rdi+29h], cl
0x18001b2eb  movsxd  rcx, eax
0x18001b2ee  mov     al, [rcx+r12]
0x18001b2f2  mov     [rdi+28h], al
0x18001b2f5  movzx   eax, byte ptr [r11+0Bh]
0x18001b2fa  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001b302  lea     eax, [rdx+r14]
0x18001b306  movsxd  rcx, eax
0x18001b309  mov     al, [rcx+r12]
0x18001b30d  mov     [rdi+2Eh], al
0x18001b310  mov     eax, edx
0x18001b312  sub     eax, esi
0x18001b314  cdqe
0x18001b316  mov     cl, [rax+r12]
0x18001b31a  lea     eax, [rdx+rbp]
0x18001b31d  mov     [rdi+2Dh], cl
0x18001b320  movsxd  rcx, eax
0x18001b323  mov     al, [rcx+r12]
0x18001b327  mov     rcx, [rsp+88h+arg_10]
0x18001b32f  mov     [rdi+2Ch], al
0x18001b332  movzx   eax, byte ptr [rbx+6]
0x18001b336  movzx   edx, byte ptr [rcx+6]
0x18001b33a  mov     edi, rva ?g_iVtoR@@3PAJA[r10+rax*4]; long near * g_iVtoR ...
0x18001b342  mov     r11d, rva ?g_iUtoG@@3PAJA[r10+rdx*4]; long near * g_iUtoG ...
0x18001b34a  add     r11d, rva ?g_iVtoG@@3PAJA[r10+rax*4]; long near * g_iVtoG ...
0x18001b352  movzx   eax, byte ptr [r9+0Ch]
0x18001b357  mov     ebx, rva ?g_iUtoB@@3PAJA[r10+rdx*4]; long near * g_iUtoB ...
0x18001b35f  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001b367  lea     eax, [rdx+rdi]
0x18001b36a  movsxd  rcx, eax
0x18001b36d  mov     al, [rcx+r12]
0x18001b371  mov     r8, [rsp+88h+arg_0]
0x18001b379  mov     [r8+32h], al
0x18001b37d  mov     eax, edx
0x18001b37f  sub     eax, r11d
0x18001b382  cdqe
0x18001b384  mov     cl, [rax+r12]
0x18001b388  lea     eax, [rdx+rbx]
0x18001b38b  mov     [r8+31h], cl
0x18001b38f  movsxd  rcx, eax
0x18001b392  mov     al, [rcx+r12]
0x18001b396  mov     [r8+30h], al
0x18001b39a  movzx   eax, byte ptr [r9+0Dh]
0x18001b39f  lea     r9, __ImageBase
0x18001b3a6  mov     edx, rva ?g_iYscale@@3PAJA[r10+rax*4]; long near * g_iYscale ...
0x18001b3ae  lea     eax, [rdx+rdi]
0x18001b3b1  movsxd  rcx, eax
0x18001b3b4  mov     al, [rcx+r12]
0x18001b3b8  mov     [r8+36h], al
0x18001b3bc  mov     eax, edx
0x18001b3be  sub     eax, r11d
0x18001b3c1  cdqe
0x18001b3c3  mov     cl, [rax+r12]
0x18001b3c7  lea     eax, [rdx+rbx]
0x18001b3ca  mov     [r8+35h], cl
0x18001b3ce  movsxd  rcx, eax
0x18001b3d1  mov     al, [rcx+r12]
0x18001b3d5  mov     rcx, [rsp+88h+arg_10]
0x18001b3dd  mov     [r8+34h], al
0x18001b3e1  mov     rax, [rsp+88h+arg_18]
0x18001b3e9  movzx   edx, byte ptr [rcx+7]
0x18001b3ed  movzx   eax, byte ptr [rax+7]
0x18001b3f1  mov     r8d, rva ?g_iUtoG@@3PAJA[r9+rdx*4]; long near * g_iUtoG ...
0x18001b3f9  add     r8d, rva ?g_iVtoG@@3PAJA[r9+rax*4]; long near * g_iVtoG ...
0x18001b401  mov     r10d, rva ?g_iVtoR@@3PAJA[r10+rax*4]; long near * g_iVtoR ...
0x18001b409  mov     r9d, rva ?g_iUtoB@@3PAJA[r9+rdx*4]; long near * g_iUtoB ...
  ... truncated ...
```
