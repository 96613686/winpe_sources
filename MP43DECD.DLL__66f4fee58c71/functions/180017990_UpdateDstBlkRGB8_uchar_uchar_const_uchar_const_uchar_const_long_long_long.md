# UpdateDstBlkRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180017990`
- end: `0x18001823f`
- name: `?UpdateDstBlkRGB8@@YAXPEAEPEBE11JJJ@Z`
- size: `2223`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180017990`

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
0x180017990  mov     rax, rsp
0x180017993  mov     [rax+20h], r9
0x180017997  mov     [rax+18h], r8
0x18001799b  mov     [rax+10h], rdx
0x18001799f  mov     [rax+8], rcx
0x1800179a3  push    rbx
0x1800179a4  push    rbp
0x1800179a5  push    rsi
0x1800179a6  push    rdi
0x1800179a7  push    r12
0x1800179a9  push    r13
0x1800179ab  push    r14
0x1800179ad  push    r15
0x1800179af  sub     rsp, 18h
0x1800179b3  mov     r12, r9
0x1800179b6  lea     r13, __ImageBase
0x1800179bd  mov     r9, rdx
0x1800179c0  xor     edx, edx
0x1800179c2  mov     [rsp+58h+var_4C], edx
0x1800179c6  mov     eax, edx
0x1800179c8  movzx   edx, byte ptr [r8]
0x1800179cc  neg     eax
0x1800179ce  add     eax, eax
0x1800179d0  and     eax, 3
0x1800179d3  mov     ebx, rva ?g_iUtoG@@3PAJA[r13+rdx*4]; long near * g_iUtoG ...
0x1800179db  mov     edi, rva ?g_iUtoB@@3PAJA[r13+rdx*4]; long near * g_iUtoB ...
0x1800179e3  movzx   edx, byte ptr [r8+1]
0x1800179e8  lea     r10d, [rax+rax*2]
0x1800179ec  movzx   eax, byte ptr [r12]
0x1800179f1  shl     r10d, 0Ah
0x1800179f5  mov     r15d, rva ?g_iUtoB@@3PAJA[r13+rdx*4]; long near * g_iUtoB ...
0x1800179fd  add     ebx, rva ?g_iVtoG@@3PAJA[r13+rax*4]; long near * g_iVtoG ...
0x180017a05  mov     r14d, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017a0d  movzx   eax, byte ptr [r12+1]
0x180017a13  mov     ecx, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017a1b  mov     eax, rva ?g_iVtoG@@3PAJA[r13+rax*4]; long near * g_iVtoG ...
0x180017a23  add     eax, rva ?g_iUtoG@@3PAJA[r13+rdx*4]; long near * g_iUtoG ...
0x180017a2b  movzx   edx, byte ptr [r8+2]
0x180017a30  mov     [rsp+58h+var_58], eax
0x180017a33  movzx   eax, byte ptr [r12+2]
0x180017a39  mov     [rsp+58h+var_54], ecx
0x180017a3d  mov     ebp, rva ?g_iUtoG@@3PAJA[r13+rdx*4]; long near * g_iUtoG ...
0x180017a45  mov     r11d, rva ?g_iUtoB@@3PAJA[r13+rdx*4]; long near * g_iUtoB ...
0x180017a4d  add     ebp, rva ?g_iVtoG@@3PAJA[r13+rax*4]; long near * g_iVtoG ...
0x180017a55  mov     esi, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017a5d  movzx   edx, byte ptr [r8+3]
0x180017a62  lea     r8, __ImageBase
0x180017a69  movzx   eax, byte ptr [r12+3]
0x180017a6f  mov     r12d, rva ?g_iUtoG@@3PAJA[r8+rdx*4]; long near * g_iUtoG ...
0x180017a77  add     r12d, rva ?g_iVtoG@@3PAJA[r8+rax*4]; long near * g_iVtoG ...
0x180017a7f  mov     r13d, rva ?g_iVtoR@@3PAJA[r13+rax*4]; long near * g_iVtoR ...
0x180017a87  mov     eax, rva ?g_iUtoB@@3PAJA[r8+rdx*4]; long near * g_iUtoB ...
0x180017a8f  mov     [rsp+58h+var_50], eax
0x180017a93  movzx   eax, byte ptr [r9]
0x180017a97  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017a9e  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017aa6  mov     eax, r8d
0x180017aa9  sub     eax, ebx
0x180017aab  cdqe
0x180017aad  movzx   edx, byte ptr [rax+r9]
0x180017ab2  lea     eax, [rdi+r8]
0x180017ab6  movsxd  rcx, eax
0x180017ab9  add     edx, r10d
0x180017abc  lea     rax, __ImageBase
0x180017ac3  mov     dl, [rdx+rax+39C10h]
0x180017aca  movzx   ecx, byte ptr [rcx+r9]
0x180017acf  add     ecx, r10d
0x180017ad2  add     dl, [rcx+rax+39D10h]
0x180017ad9  lea     eax, [r14+r8]
0x180017add  movsxd  rcx, eax
0x180017ae0  lea     r8, __ImageBase
0x180017ae7  movzx   eax, byte ptr [rcx+r9]
0x180017aec  mov     rcx, [rsp+58h+arg_0]
0x180017af1  add     eax, r10d
0x180017af4  add     dl, [rax+r8+39B10h]
0x180017afc  mov     rax, [rsp+58h+arg_8]
0x180017b01  mov     [rcx], dl
0x180017b03  movzx   eax, byte ptr [rax+4]
0x180017b07  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017b0f  mov     eax, r8d
0x180017b12  sub     eax, ebp
0x180017b14  cdqe
0x180017b16  movzx   edx, byte ptr [rax+r9]
0x180017b1b  lea     eax, [r11+r8]
0x180017b1f  movsxd  rcx, eax
0x180017b22  add     edx, r10d
0x180017b25  lea     rax, __ImageBase
0x180017b2c  mov     dl, [rdx+rax+39C10h]
0x180017b33  movzx   ecx, byte ptr [rcx+r9]
0x180017b38  add     ecx, r10d
0x180017b3b  add     dl, [rcx+rax+39D10h]
0x180017b42  lea     eax, [rsi+r8]
0x180017b46  movsxd  rcx, eax
0x180017b49  lea     r8, __ImageBase
0x180017b50  movzx   eax, byte ptr [rcx+r9]
0x180017b55  add     eax, r10d
0x180017b58  add     dl, [rax+r8+39B10h]
0x180017b60  mov     rax, [rsp+58h+arg_0]
0x180017b65  mov     [rax+4], dl
0x180017b68  mov     rax, [rsp+58h+arg_8]
0x180017b6d  movzx   eax, byte ptr [rax+1]
0x180017b71  add     r10d, 300h
0x180017b78  mov     r8d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017b80  mov     eax, r8d
0x180017b83  sub     eax, ebx
0x180017b85  cdqe
0x180017b87  movzx   edx, byte ptr [rax+r9]
0x180017b8c  lea     eax, [rdi+r8]
0x180017b90  movsxd  rcx, eax
0x180017b93  add     edx, r10d
0x180017b96  lea     rax, __ImageBase
0x180017b9d  mov     dl, [rdx+rax+39C10h]
0x180017ba4  movzx   ecx, byte ptr [rcx+r9]
0x180017ba9  add     ecx, r10d
0x180017bac  add     dl, [rcx+rax+39D10h]
0x180017bb3  lea     eax, [r14+r8]
0x180017bb7  movsxd  rcx, eax
0x180017bba  lea     r8, __ImageBase
0x180017bc1  movzx   eax, byte ptr [rcx+r9]
0x180017bc6  add     eax, r10d
0x180017bc9  add     dl, [rax+r8+39B10h]
0x180017bd1  mov     rax, [rsp+58h+arg_0]
0x180017bd6  mov     [rax+1], dl
0x180017bd9  mov     rax, [rsp+58h+arg_8]
0x180017bde  movzx   eax, byte ptr [rax+5]
0x180017be2  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017bea  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017bf1  lea     eax, [r11+r9]
0x180017bf5  movsxd  rcx, eax
0x180017bf8  lea     eax, [rsi+r9]
0x180017bfc  sub     r9d, ebp
0x180017bff  movzx   edx, byte ptr [rcx+r8]
0x180017c04  movsxd  rcx, eax
0x180017c07  add     edx, r10d
0x180017c0a  lea     rax, __ImageBase
0x180017c11  movzx   ecx, byte ptr [rcx+r8]
0x180017c16  mov     r8b, [rdx+rax+39D10h]
0x180017c1e  add     ecx, r10d
0x180017c21  lea     rdx, __ImageBase
0x180017c28  movsxd  rax, r9d
0x180017c2b  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017c32  add     r8b, [rcx+rdx+39B10h]
0x180017c3a  movzx   ecx, byte ptr [rax+r9]
0x180017c3f  mov     rax, [rsp+58h+arg_0]
0x180017c44  add     ecx, r10d
0x180017c47  add     r10d, 300h
0x180017c4e  add     r8b, [rcx+rdx+39C10h]
0x180017c56  mov     [rax+5], r8b
0x180017c5a  mov     rax, [rsp+58h+arg_8]
0x180017c5f  movzx   eax, byte ptr [rax+2]
0x180017c63  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017c6b  mov     eax, r8d
0x180017c6e  sub     eax, [rsp+58h+var_58]
0x180017c71  cdqe
0x180017c73  movzx   edx, byte ptr [rax+r9]
0x180017c78  lea     eax, [r15+r8]
0x180017c7c  movsxd  rcx, eax
0x180017c7f  add     edx, r10d
0x180017c82  lea     rax, __ImageBase
0x180017c89  mov     dl, [rdx+rax+39C10h]
0x180017c90  movzx   ecx, byte ptr [rcx+r9]
0x180017c95  add     ecx, r10d
0x180017c98  add     dl, [rcx+rax+39D10h]
0x180017c9f  mov     eax, [rsp+58h+var_54]
0x180017ca3  add     eax, r8d
0x180017ca6  lea     r8, __ImageBase
0x180017cad  movsxd  rcx, eax
0x180017cb0  movzx   eax, byte ptr [rcx+r9]
0x180017cb5  add     eax, r10d
0x180017cb8  add     dl, [rax+r8+39B10h]
0x180017cc0  mov     rax, [rsp+58h+arg_0]
0x180017cc5  mov     [rax+2], dl
0x180017cc8  mov     rax, [rsp+58h+arg_8]
0x180017ccd  movzx   eax, byte ptr [rax+6]
0x180017cd1  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017cd9  mov     eax, [rsp+58h+var_50]
0x180017cdd  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017ce4  add     eax, r9d
0x180017ce7  movsxd  rcx, eax
0x180017cea  movzx   edx, byte ptr [rcx+r8]
0x180017cef  add     edx, r10d
0x180017cf2  lea     eax, [r9+r13]
0x180017cf6  sub     r9d, r12d
0x180017cf9  movsxd  rcx, eax
0x180017cfc  lea     rax, __ImageBase
0x180017d03  movzx   ecx, byte ptr [rcx+r8]
0x180017d08  mov     r8b, [rdx+rax+39D10h]
0x180017d10  add     ecx, r10d
0x180017d13  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017d1a  add     r8b, [rcx+rax+39B10h]
0x180017d22  lea     rcx, __ImageBase
0x180017d29  movsxd  rax, r9d
0x180017d2c  movzx   eax, byte ptr [rax+rdx]
0x180017d30  add     eax, r10d
0x180017d33  add     r10d, 300h
0x180017d3a  add     r8b, [rax+rcx+39C10h]
0x180017d42  mov     rax, [rsp+58h+arg_0]
0x180017d47  mov     [rax+6], r8b
0x180017d4b  mov     rax, [rsp+58h+arg_8]
0x180017d50  movzx   eax, byte ptr [rax+3]
0x180017d54  mov     r9d, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017d5c  lea     eax, [r15+r9]
0x180017d60  movsxd  rcx, eax
0x180017d63  mov     eax, [rsp+58h+var_54]
0x180017d67  add     eax, r9d
0x180017d6a  sub     r9d, [rsp+58h+var_58]
0x180017d6e  movzx   edx, byte ptr [rcx+rdx]
0x180017d72  movsxd  rcx, eax
0x180017d75  add     edx, r10d
0x180017d78  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017d7f  movzx   ecx, byte ptr [rcx+rax]
0x180017d83  lea     rax, __ImageBase
0x180017d8a  mov     r8b, [rdx+rax+39D10h]
0x180017d92  add     ecx, r10d
0x180017d95  lea     rdx, __ImageBase
0x180017d9c  movsxd  rax, r9d
0x180017d9f  mov     r9, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017da6  add     r8b, [rcx+rdx+39B10h]
0x180017dae  movzx   ecx, byte ptr [rax+r9]
0x180017db3  mov     rax, [rsp+58h+arg_0]
0x180017db8  add     ecx, r10d
0x180017dbb  add     r8b, [rcx+rdx+39C10h]
0x180017dc3  mov     [rax+3], r8b
0x180017dc7  mov     rax, [rsp+58h+arg_8]
0x180017dcc  movzx   eax, byte ptr [rax+7]
0x180017dd0  mov     r8d, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017dd8  lea     eax, [r8+r13]
0x180017ddc  movsxd  rcx, eax
0x180017ddf  mov     eax, r8d
0x180017de2  sub     eax, r12d
0x180017de5  cdqe
0x180017de7  movzx   edx, byte ptr [rcx+r9]
0x180017dec  lea     rcx, __ImageBase
0x180017df3  add     edx, r10d
0x180017df6  movzx   eax, byte ptr [rax+r9]
0x180017dfb  add     eax, r10d
0x180017dfe  mov     dl, [rdx+rcx+39B10h]
0x180017e05  add     dl, [rax+rcx+39C10h]
0x180017e0c  mov     eax, [rsp+58h+var_50]
0x180017e10  add     eax, r8d
0x180017e13  lea     r8, __ImageBase
0x180017e1a  movsxd  rcx, eax
0x180017e1d  movzx   eax, byte ptr [rcx+r9]
0x180017e22  mov     ecx, 1
0x180017e27  add     eax, r10d
0x180017e2a  add     dl, [rax+r8+39D10h]
0x180017e32  mov     rax, [rsp+58h+arg_0]
0x180017e37  mov     [rax+7], dl
0x180017e3a  movsxd  rax, [rsp+58h+arg_28]
0x180017e42  add     [rsp+58h+arg_10], rax
0x180017e47  add     [rsp+58h+arg_18], rax
0x180017e4c  mov     eax, [rsp+58h+var_4C]
0x180017e50  add     eax, eax
0x180017e52  sub     ecx, eax
0x180017e54  movsxd  rax, [rsp+58h+arg_20]
0x180017e5c  and     ecx, 3
0x180017e5f  lea     r10d, [rcx+rcx*2]
0x180017e63  mov     rcx, [rsp+58h+arg_8]
0x180017e68  shl     r10d, 0Ah
0x180017e6c  movzx   eax, byte ptr [rax+rcx]
0x180017e70  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017e78  lea     eax, [rdi+r9]
0x180017e7c  mov     r8, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017e83  movsxd  rcx, eax
0x180017e86  lea     eax, [r14+r9]
0x180017e8a  sub     r9d, ebx
0x180017e8d  movzx   edx, byte ptr [rcx+r8]
0x180017e92  movsxd  rcx, eax
0x180017e95  add     edx, r10d
0x180017e98  lea     rax, __ImageBase
0x180017e9f  movzx   ecx, byte ptr [rcx+r8]
0x180017ea4  mov     r8b, [rdx+rax+39D10h]
0x180017eac  add     ecx, r10d
0x180017eaf  mov     rdx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017eb6  add     r8b, [rcx+rax+39B10h]
0x180017ebe  lea     rcx, __ImageBase
0x180017ec5  movsxd  rax, r9d
0x180017ec8  movzx   eax, byte ptr [rax+rdx]
0x180017ecc  add     eax, r10d
0x180017ecf  add     r8b, [rax+rcx+39C10h]
0x180017ed7  movsxd  rax, [rsp+58h+arg_30]
0x180017edf  mov     rcx, [rsp+58h+arg_0]
0x180017ee4  mov     [rax+rcx], r8b
0x180017ee8  lea     r8, __ImageBase
0x180017eef  mov     rcx, [rsp+58h+arg_8]
0x180017ef4  movsxd  rax, [rsp+58h+arg_20]
0x180017efc  movzx   eax, byte ptr [rax+rcx+4]
0x180017f01  mov     r9d, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017f09  lea     eax, [r11+r9]
0x180017f0d  movsxd  rcx, eax
0x180017f10  lea     eax, [rsi+r9]
0x180017f14  sub     r9d, ebp
0x180017f17  movzx   edx, byte ptr [rcx+rdx]
0x180017f1b  movsxd  rcx, eax
0x180017f1e  add     edx, r10d
0x180017f21  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017f28  mov     r8b, [rdx+r8+39D10h]
0x180017f30  lea     rdx, __ImageBase
0x180017f37  movzx   eax, byte ptr [rcx+rax]
0x180017f3b  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
  ... truncated ...
```
