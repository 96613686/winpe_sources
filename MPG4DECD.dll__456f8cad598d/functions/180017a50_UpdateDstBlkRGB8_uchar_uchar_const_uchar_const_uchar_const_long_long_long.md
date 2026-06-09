# UpdateDstBlkRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180017a50`
- end: `0x1800182ff`
- name: `?UpdateDstBlkRGB8@@YAXPEAEPEBE11JJJ@Z`
- size: `2223`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180017a50`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB8(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  const unsigned __int8 *v7; // r12
  const unsigned __int8 *v8; // r9
  char v9; // al
  __int64 v10; // rdx
  int v11; // ebx
  int v12; // edi
  __int64 v13; // rdx
  int v14; // r10d
  __int64 v15; // rax
  int v16; // r15d
  int v17; // ebx
  int v18; // r14d
  __int64 v19; // rax
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // r11d
  int v24; // ebp
  int v25; // esi
  __int64 v26; // rdx
  __int64 v27; // rax
  int v28; // r12d
  int v29; // r13d
  __int64 v30; // rax
  unsigned __int8 *v31; // r9
  int v32; // r8d
  int v33; // r8d
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int8 *v36; // r9
  __int64 v37; // rcx
  int v38; // r8d
  unsigned __int8 *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  unsigned __int8 *v43; // r9
  int v44; // r8d
  int v45; // r10d
  unsigned __int8 *v46; // rdx
  __int64 v47; // rcx
  int v48; // r8d
  unsigned __int8 *v49; // rbx
  __int64 v50; // rcx
  int v51; // r8d
  __int64 v52; // rcx
  __int64 v53; // rax
  int v54; // r8d
  int v55; // [rsp+0h] [rbp-58h]
  int v56; // [rsp+4h] [rbp-54h]
  int v57; // [rsp+8h] [rbp-50h]
  int v58; // [rsp+Ch] [rbp-4Ch]
  const unsigned __int8 *v60; // [rsp+68h] [rbp+10h]
  const unsigned __int8 *v61; // [rsp+70h] [rbp+18h]
  const unsigned __int8 *v62; // [rsp+78h] [rbp+20h]

  v62 = a4;
  v61 = a3;
  v60 = a2;
  v7 = a4;
  v8 = a2;
  LOBYTE(a2) = 0;
  v58 = 0;
  do
  {
    v9 = (char)a2;
    v10 = *a3;
    v11 = *((_DWORD *)&g_iUtoG + v10);
    v12 = *((_DWORD *)&g_iUtoB + v10);
    v13 = a3[1];
    v14 = 3 * ((-2 * v9) & 3);
    v15 = *v7;
    v14 <<= 10;
    v16 = *((_DWORD *)&g_iUtoB + v13);
    v17 = *((_DWORD *)&g_iVtoG + v15) + v11;
    v18 = *((_DWORD *)&g_iVtoR + v15);
    v19 = v7[1];
    v20 = *((_DWORD *)&g_iVtoR + v19);
    LODWORD(v19) = *((_DWORD *)&g_iUtoG + v13) + *((_DWORD *)&g_iVtoG + v19);
    v21 = a3[2];
    v55 = v19;
    v22 = v7[2];
    v56 = v20;
    v23 = *((_DWORD *)&g_iUtoB + v21);
    v24 = *((_DWORD *)&g_iVtoG + v22) + *((_DWORD *)&g_iUtoG + v21);
    v25 = *((_DWORD *)&g_iVtoR + v22);
    v26 = a3[3];
    v27 = v7[3];
    v28 = *((_DWORD *)&g_iVtoG + v27) + *((_DWORD *)&g_iUtoG + v26);
    v29 = *((_DWORD *)&g_iVtoR + v27);
    v57 = *((_DWORD *)&g_iUtoB + v26);
    v30 = *v8;
    v31 = g_rgiClapTabDec;
    *a1 = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v18 + *((_DWORD *)&g_iYscale + v30)])
        + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v12 + *((_DWORD *)&g_iYscale + v30)] + 512)
        + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[*((_DWORD *)&g_iYscale + v30) - v17] + 256);
    v32 = *((_DWORD *)&g_iYscale + v60[4]);
    a1[4] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v31[v25 + v32])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v31[v23 + v32] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v31[v32 - v24] + 256);
    v14 += 768;
    v33 = *((_DWORD *)&g_iYscale + v60[1]);
    a1[1] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v31[v18 + v33])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v31[v12 + v33] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v31[v33 - v17] + 256);
    LODWORD(v31) = *((_DWORD *)&g_iYscale + v60[5]);
    LOBYTE(v33) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v23 + (int)v31] + 512);
    v34 = v14 + (unsigned int)g_rgiClapTabDec[v25 + (int)v31];
    v35 = (int)v31 - v24;
    v36 = g_rgiClapTabDec;
    LOBYTE(v33) = *((_BYTE *)&g_rgDitherMap + v34) + v33;
    v37 = v14 + (unsigned int)g_rgiClapTabDec[v35];
    v14 += 768;
    a1[5] = *((_BYTE *)&g_rgDitherMap + v37 + 256) + v33;
    v38 = *((_DWORD *)&g_iYscale + v60[2]);
    a1[2] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v36[v38 + v56])
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v36[v16 + v38] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v36[v38 - v55] + 256);
    LODWORD(v36) = *((_DWORD *)&g_iYscale + v60[6]);
    v39 = g_rgiClapTabDec;
    LOBYTE(v38) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v36 + v29])
                + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[(int)v36 + v57] + 512);
    v40 = v14 + (unsigned int)g_rgiClapTabDec[(int)v36 - v28];
    v14 += 768;
    a1[6] = *((_BYTE *)&g_rgDitherMap + v40 + 256) + v38;
    LODWORD(v36) = *((_DWORD *)&g_iYscale + v60[3]);
    LOBYTE(v38) = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v39[v16 + (int)v36] + 512);
    v41 = v14 + (unsigned int)g_rgiClapTabDec[(int)v36 + v56];
    v42 = (int)v36 - v55;
    v43 = g_rgiClapTabDec;
    a1[3] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)g_rgiClapTabDec[v42] + 256)
          + *((_BYTE *)&g_rgDitherMap + v41)
          + v38;
    v44 = *((_DWORD *)&g_iYscale + v60[7]);
    a1[7] = *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v43[v44 + v57] + 512)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v43[v44 - v28] + 256)
          + *((_BYTE *)&g_rgDitherMap + v14 + (unsigned int)v43[v44 + v29]);
    v61 += a6;
    v62 += a6;
    v45 = 3072 * ((1 - 2 * (_BYTE)v58) & 3);
    LODWORD(v43) = *((_DWORD *)&g_iYscale + v60[a5]);
    v46 = g_rgiClapTabDec;
    a1[a7] = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[(int)v43 - v17] + 256)
           + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[v18 + (int)v43])
           + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[v12 + (int)v43] + 512);
    LODWORD(v43) = *((_DWORD *)&g_iYscale + v60[a5 + 4]);
    LOBYTE(v44) = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[v25 + (int)v43])
                + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v46[v23 + (int)v43] + 512);
    v47 = v45 + (unsigned int)g_rgiClapTabDec[(int)v43 - v24];
    v45 += 768;
    a1[a7 + 4] = *((_BYTE *)&g_rgDitherMap + v47 + 256) + v44;
    v48 = *((_DWORD *)&g_iYscale + v60[a5 + 1]);
    LODWORD(v42) = v48 - v17;
    v49 = g_rgiClapTabDec;
    a1[a7 + 1] = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[v18 + v48])
               + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[v12 + v48] + 512)
               + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)g_rgiClapTabDec[(int)v42] + 256);
    LODWORD(v43) = *((_DWORD *)&g_iYscale + v60[a5 + 5]);
    LOBYTE(v48) = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v25 + (int)v43])
                + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v23 + (int)v43] + 512);
    v50 = v45 + (unsigned int)v49[(int)v43 - v24];
    v45 += 768;
    a1[a7 + 5] = *((_BYTE *)&g_rgDitherMap + v50 + 256) + v48;
    v51 = *((_DWORD *)&g_iYscale + v60[a5 + 2]);
    a1[a7 + 2] = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v56 + v51])
               + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v16 + v51] + 512)
               + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v51 - v55] + 256);
    LODWORD(v43) = *((_DWORD *)&g_iYscale + v60[a5 + 6]);
    LOBYTE(v51) = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[(int)v43 + v29])
                + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v57 + (int)v43] + 512);
    v52 = v45 + (unsigned int)v49[(int)v43 - v28];
    v45 += 768;
    a1[a7 + 6] = *((_BYTE *)&g_rgDitherMap + v52 + 256) + v51;
    LODWORD(v43) = *((_DWORD *)&g_iYscale + v60[a5 + 3]);
    a1[a7 + 3] = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[(int)v43 - v55] + 256)
               + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v56 + (int)v43])
               + *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[v16 + (int)v43] + 512);
    v53 = v60[a5 + 7];
    v8 = &v60[2 * a5];
    v60 = v8;
    v54 = *((_DWORD *)&g_iYscale + v53);
    LODWORD(v53) = v54 - v28;
    v7 = v62;
    a2 = (const unsigned __int8 *)(v45 + (unsigned int)v49[v54 + v29]);
    LODWORD(v52) = v49[(int)v53];
    LODWORD(v53) = v57 + v54;
    a3 = v61;
    a1[a7 + 7] = *((_BYTE *)&g_rgDitherMap + v45 + (unsigned int)v49[(int)v53] + 512)
               + *((_BYTE *)&g_rgDitherMap + (unsigned int)(v45 + v52) + 256)
               + *((_BYTE *)&g_rgDitherMap + (_QWORD)a2);
    LODWORD(a2) = v58 + 1;
    a1 += 2 * a7;
    v58 = (int)a2;
  }
  while ( (unsigned int)a2 < 4 );
}

```

## disassembly

```asm
0x180017a50  mov     rax, rsp
0x180017a53  mov     [rax+20h], r9
0x180017a57  mov     [rax+18h], r8
0x180017a5b  mov     [rax+10h], rdx
0x180017a5f  mov     [rax+8], rcx
0x180017a63  push    rbx
0x180017a64  push    rbp
0x180017a65  push    rsi
0x180017a66  push    rdi
0x180017a67  push    r12
0x180017a69  push    r13
0x180017a6b  push    r14
0x180017a6d  push    r15
0x180017a6f  sub     rsp, 18h
0x180017a73  mov     r12, r9
0x180017a76  lea     r13, __ImageBase
0x180017a7d  mov     r9, rdx
0x180017a80  xor     edx, edx
0x180017a82  mov     [rsp+58h+var_4C], edx
0x180017a86  mov     eax, edx
0x180017a88  movzx   edx, byte ptr [r8]
0x180017a8c  neg     eax
0x180017a8e  add     eax, eax
0x180017a90  and     eax, 3
0x180017a93  mov     ebx, rva ?g_iUtoG@@3PAJA[r13+rdx*4]; long near * g_iUtoG ...
0x180017a9b  mov     edi, rva ?g_iUtoB@@3PAJA[r13+rdx*4]; long near * g_iUtoB ...
0x180017aa3  movzx   edx, byte ptr [r8+1]
0x180017aa8  lea     r10d, [rax+rax*2]
0x180017aac  movzx   eax, byte ptr [r12]
0x180017ab1  shl     r10d, 0Ah
0x180017ab5  mov     r15d, rva ?g_iUtoB@@3PAJA[r13+rdx*4]; long near * g_iUtoB ...
0x180017abd  add     ebx, rva ?g_iVtoG@@3PAJA[r13+rax*4]; long near * g_iVtoG ...
0x180017ac5  mov     r14d, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017acd  movzx   eax, byte ptr [r12+1]
0x180017ad3  mov     ecx, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017adb  mov     eax, rva ?g_iVtoG@@3PAJA[r13+rax*4]; long near * g_iVtoG ...
0x180017ae3  add     eax, rva ?g_iUtoG@@3PAJA[r13+rdx*4]; long near * g_iUtoG ...
0x180017aeb  movzx   edx, byte ptr [r8+2]
0x180017af0  mov     [rsp+58h+var_58], eax
0x180017af3  movzx   eax, byte ptr [r12+2]
0x180017af9  mov     [rsp+58h+var_54], ecx
0x180017afd  mov     ebp, rva ?g_iUtoG@@3PAJA[r13+rdx*4]; long near * g_iUtoG ...
0x180017b05  mov     r11d, rva ?g_iUtoB@@3PAJA[r13+rdx*4]; long near * g_iUtoB ...
0x180017b0d  add     ebp, rva ?g_iVtoG@@3PAJA[r13+rax*4]; long near * g_iVtoG ...
0x180017b15  mov     esi, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017b1d  movzx   edx, byte ptr [r8+3]
0x180017b22  lea     r8, __ImageBase
0x180017b29  movzx   eax, byte ptr [r12+3]
0x180017b2f  mov     r12d, rva ?g_iUtoG@@3PAJA[r8+rdx*4]; long near * g_iUtoG ...
0x180017b37  add     r12d, rva ?g_iVtoG@@3PAJA[r8+rax*4]; long near * g_iVtoG ...
0x180017b3f  mov     r13d, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017b47  mov     eax, rva ?g_iUtoB@@3PAJA[r8+rdx*4]; long near * g_iUtoB ...
0x180017b4f  mov     [rsp+58h+var_50], eax
0x180017b53  movzx   eax, byte ptr [r9]
0x180017b57  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017b5e  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017b66  mov     eax, r8d
0x180017b69  sub     eax, ebx
0x180017b6b  cdqe
0x180017b6d  movzx   edx, byte ptr [rax+r9]
0x180017b72  lea     eax, [rdi+r8]
0x180017b76  movsxd  rcx, eax
0x180017b79  add     edx, r10d
0x180017b7c  lea     rax, __ImageBase
0x180017b83  mov     dl, [rdx+rax+39C50h]
0x180017b8a  movzx   ecx, byte ptr [rcx+r9]
0x180017b8f  add     ecx, r10d
0x180017b92  add     dl, [rcx+rax+39D50h]
0x180017b99  lea     eax, [r14+r8]
0x180017b9d  movsxd  rcx, eax
0x180017ba0  lea     r8, __ImageBase
0x180017ba7  movzx   eax, byte ptr [rcx+r9]
0x180017bac  mov     rcx, [rsp+58h+arg_0]
0x180017bb1  add     eax, r10d
0x180017bb4  add     dl, [rax+r8+39B50h]
0x180017bbc  mov     rax, [rsp+58h+arg_8]
0x180017bc1  mov     [rcx], dl
0x180017bc3  movzx   eax, byte ptr [rax+4]
0x180017bc7  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017bcf  mov     eax, r8d
0x180017bd2  sub     eax, ebp
0x180017bd4  cdqe
0x180017bd6  movzx   edx, byte ptr [rax+r9]
0x180017bdb  lea     eax, [r11+r8]
0x180017bdf  movsxd  rcx, eax
0x180017be2  add     edx, r10d
0x180017be5  lea     rax, __ImageBase
0x180017bec  mov     dl, [rdx+rax+39C50h]
0x180017bf3  movzx   ecx, byte ptr [rcx+r9]
0x180017bf8  add     ecx, r10d
0x180017bfb  add     dl, [rcx+rax+39D50h]
0x180017c02  lea     eax, [rsi+r8]
0x180017c06  movsxd  rcx, eax
0x180017c09  lea     r8, __ImageBase
0x180017c10  movzx   eax, byte ptr [rcx+r9]
0x180017c15  add     eax, r10d
0x180017c18  add     dl, [rax+r8+39B50h]
0x180017c20  mov     rax, [rsp+58h+arg_0]
0x180017c25  mov     [rax+4], dl
0x180017c28  mov     rax, [rsp+58h+arg_8]
0x180017c2d  movzx   eax, byte ptr [rax+1]
0x180017c31  add     r10d, 300h
0x180017c38  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017c40  mov     eax, r8d
0x180017c43  sub     eax, ebx
0x180017c45  cdqe
0x180017c47  movzx   edx, byte ptr [rax+r9]
0x180017c4c  lea     eax, [rdi+r8]
0x180017c50  movsxd  rcx, eax
0x180017c53  add     edx, r10d
0x180017c56  lea     rax, __ImageBase
0x180017c5d  mov     dl, [rdx+rax+39C50h]
0x180017c64  movzx   ecx, byte ptr [rcx+r9]
0x180017c69  add     ecx, r10d
0x180017c6c  add     dl, [rcx+rax+39D50h]
0x180017c73  lea     eax, [r14+r8]
0x180017c77  movsxd  rcx, eax
0x180017c7a  lea     r8, __ImageBase
0x180017c81  movzx   eax, byte ptr [rcx+r9]
0x180017c86  add     eax, r10d
0x180017c89  add     dl, [rax+r8+39B50h]
0x180017c91  mov     rax, [rsp+58h+arg_0]
0x180017c96  mov     [rax+1], dl
0x180017c99  mov     rax, [rsp+58h+arg_8]
0x180017c9e  movzx   eax, byte ptr [rax+5]
0x180017ca2  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017caa  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017cb1  lea     eax, [r11+r9]
0x180017cb5  movsxd  rcx, eax
0x180017cb8  lea     eax, [rsi+r9]
0x180017cbc  sub     r9d, ebp
0x180017cbf  movzx   edx, byte ptr [rcx+r8]
0x180017cc4  movsxd  rcx, eax
0x180017cc7  add     edx, r10d
0x180017cca  lea     rax, __ImageBase
0x180017cd1  movzx   ecx, byte ptr [rcx+r8]
0x180017cd6  mov     r8b, [rdx+rax+39D50h]
0x180017cde  add     ecx, r10d
0x180017ce1  lea     rdx, __ImageBase
0x180017ce8  movsxd  rax, r9d
0x180017ceb  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017cf2  add     r8b, [rcx+rdx+39B50h]
0x180017cfa  movzx   ecx, byte ptr [rax+r9]
0x180017cff  mov     rax, [rsp+58h+arg_0]
0x180017d04  add     ecx, r10d
0x180017d07  add     r10d, 300h
0x180017d0e  add     r8b, [rcx+rdx+39C50h]
0x180017d16  mov     [rax+5], r8b
0x180017d1a  mov     rax, [rsp+58h+arg_8]
0x180017d1f  movzx   eax, byte ptr [rax+2]
0x180017d23  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017d2b  mov     eax, r8d
0x180017d2e  sub     eax, [rsp+58h+var_58]
0x180017d31  cdqe
0x180017d33  movzx   edx, byte ptr [rax+r9]
0x180017d38  lea     eax, [r15+r8]
0x180017d3c  movsxd  rcx, eax
0x180017d3f  add     edx, r10d
0x180017d42  lea     rax, __ImageBase
0x180017d49  mov     dl, [rdx+rax+39C50h]
0x180017d50  movzx   ecx, byte ptr [rcx+r9]
0x180017d55  add     ecx, r10d
0x180017d58  add     dl, [rcx+rax+39D50h]
0x180017d5f  mov     eax, [rsp+58h+var_54]
0x180017d63  add     eax, r8d
0x180017d66  lea     r8, __ImageBase
0x180017d6d  movsxd  rcx, eax
0x180017d70  movzx   eax, byte ptr [rcx+r9]
0x180017d75  add     eax, r10d
0x180017d78  add     dl, [rax+r8+39B50h]
0x180017d80  mov     rax, [rsp+58h+arg_0]
0x180017d85  mov     [rax+2], dl
0x180017d88  mov     rax, [rsp+58h+arg_8]
0x180017d8d  movzx   eax, byte ptr [rax+6]
0x180017d91  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017d99  mov     eax, [rsp+58h+var_50]
0x180017d9d  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017da4  add     eax, r9d
0x180017da7  movsxd  rcx, eax
0x180017daa  movzx   edx, byte ptr [rcx+r8]
0x180017daf  add     edx, r10d
0x180017db2  lea     eax, [r9+r13]
0x180017db6  sub     r9d, r12d
0x180017db9  movsxd  rcx, eax
0x180017dbc  lea     rax, __ImageBase
0x180017dc3  movzx   ecx, byte ptr [rcx+r8]
0x180017dc8  mov     r8b, [rdx+rax+39D50h]
0x180017dd0  add     ecx, r10d
0x180017dd3  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017dda  add     r8b, [rcx+rax+39B50h]
0x180017de2  lea     rcx, __ImageBase
0x180017de9  movsxd  rax, r9d
0x180017dec  movzx   eax, byte ptr [rax+rdx]
0x180017df0  add     eax, r10d
0x180017df3  add     r10d, 300h
0x180017dfa  add     r8b, [rax+rcx+39C50h]
0x180017e02  mov     rax, [rsp+58h+arg_0]
0x180017e07  mov     [rax+6], r8b
0x180017e0b  mov     rax, [rsp+58h+arg_8]
0x180017e10  movzx   eax, byte ptr [rax+3]
0x180017e14  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017e1c  lea     eax, [r15+r9]
0x180017e20  movsxd  rcx, eax
0x180017e23  mov     eax, [rsp+58h+var_54]
0x180017e27  add     eax, r9d
0x180017e2a  sub     r9d, [rsp+58h+var_58]
0x180017e2e  movzx   edx, byte ptr [rcx+rdx]
0x180017e32  movsxd  rcx, eax
0x180017e35  add     edx, r10d
0x180017e38  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017e3f  movzx   ecx, byte ptr [rcx+rax]
0x180017e43  lea     rax, __ImageBase
0x180017e4a  mov     r8b, [rdx+rax+39D50h]
0x180017e52  add     ecx, r10d
0x180017e55  lea     rdx, __ImageBase
0x180017e5c  movsxd  rax, r9d
0x180017e5f  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017e66  add     r8b, [rcx+rdx+39B50h]
0x180017e6e  movzx   ecx, byte ptr [rax+r9]
0x180017e73  mov     rax, [rsp+58h+arg_0]
0x180017e78  add     ecx, r10d
0x180017e7b  add     r8b, [rcx+rdx+39C50h]
0x180017e83  mov     [rax+3], r8b
0x180017e87  mov     rax, [rsp+58h+arg_8]
0x180017e8c  movzx   eax, byte ptr [rax+7]
0x180017e90  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017e98  lea     eax, [r8+r13]
0x180017e9c  movsxd  rcx, eax
0x180017e9f  mov     eax, r8d
0x180017ea2  sub     eax, r12d
0x180017ea5  cdqe
0x180017ea7  movzx   edx, byte ptr [rcx+r9]
0x180017eac  lea     rcx, __ImageBase
0x180017eb3  add     edx, r10d
0x180017eb6  movzx   eax, byte ptr [rax+r9]
0x180017ebb  add     eax, r10d
0x180017ebe  mov     dl, [rdx+rcx+39B50h]
0x180017ec5  add     dl, [rax+rcx+39C50h]
0x180017ecc  mov     eax, [rsp+58h+var_50]
0x180017ed0  add     eax, r8d
0x180017ed3  lea     r8, __ImageBase
0x180017eda  movsxd  rcx, eax
0x180017edd  movzx   eax, byte ptr [rcx+r9]
0x180017ee2  mov     ecx, 1
0x180017ee7  add     eax, r10d
0x180017eea  add     dl, [rax+r8+39D50h]
0x180017ef2  mov     rax, [rsp+58h+arg_0]
0x180017ef7  mov     [rax+7], dl
0x180017efa  movsxd  rax, [rsp+58h+arg_28]
0x180017f02  add     [rsp+58h+arg_10], rax
0x180017f07  add     [rsp+58h+arg_18], rax
0x180017f0c  mov     eax, [rsp+58h+var_4C]
0x180017f10  add     eax, eax
0x180017f12  sub     ecx, eax
0x180017f14  movsxd  rax, [rsp+58h+arg_20]
0x180017f1c  and     ecx, 3
0x180017f1f  lea     r10d, [rcx+rcx*2]
0x180017f23  mov     rcx, [rsp+58h+arg_8]
0x180017f28  shl     r10d, 0Ah
0x180017f2c  movzx   eax, byte ptr [rax+rcx]
0x180017f30  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017f38  lea     eax, [rdi+r9]
0x180017f3c  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017f43  movsxd  rcx, eax
0x180017f46  lea     eax, [r14+r9]
0x180017f4a  sub     r9d, ebx
0x180017f4d  movzx   edx, byte ptr [rcx+r8]
0x180017f52  movsxd  rcx, eax
0x180017f55  add     edx, r10d
0x180017f58  lea     rax, __ImageBase
0x180017f5f  movzx   ecx, byte ptr [rcx+r8]
0x180017f64  mov     r8b, [rdx+rax+39D50h]
0x180017f6c  add     ecx, r10d
0x180017f6f  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017f76  add     r8b, [rcx+rax+39B50h]
0x180017f7e  lea     rcx, __ImageBase
0x180017f85  movsxd  rax, r9d
0x180017f88  movzx   eax, byte ptr [rax+rdx]
0x180017f8c  add     eax, r10d
0x180017f8f  add     r8b, [rax+rcx+39C50h]
0x180017f97  movsxd  rax, [rsp+58h+arg_30]
0x180017f9f  mov     rcx, [rsp+58h+arg_0]
0x180017fa4  mov     [rax+rcx], r8b
0x180017fa8  lea     r8, __ImageBase
0x180017faf  mov     rcx, [rsp+58h+arg_8]
0x180017fb4  movsxd  rax, [rsp+58h+arg_20]
0x180017fbc  movzx   eax, byte ptr [rax+rcx+4]
0x180017fc1  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017fc9  lea     eax, [r11+r9]
0x180017fcd  movsxd  rcx, eax
0x180017fd0  lea     eax, [rsi+r9]
0x180017fd4  sub     r9d, ebp
0x180017fd7  movzx   edx, byte ptr [rcx+rdx]
0x180017fdb  movsxd  rcx, eax
0x180017fde  add     edx, r10d
0x180017fe1  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017fe8  mov     r8b, [rdx+r8+39D50h]
0x180017ff0  lea     rdx, __ImageBase
0x180017ff7  movzx   eax, byte ptr [rcx+rax]
0x180017ffb  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
  ... truncated ...
```
