# UpdateDst411MBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003b3d0`
- end: `0x18003b8fd`
- name: `?UpdateDst411MBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `1325`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003bc90`

## callees

- `0x18003b3d0`

## pseudocode

```c
void __fastcall UpdateDst411MBRGB32(
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
  int v21; // r8d
  int v22; // r10d
  int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // r8d
  int v27; // r10d
  int v28; // r9d
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r10d
  int v33; // r9d
  __int64 v34; // rax

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
    a2[3] = 0;
    a2[2] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[1] = *(_BYTE *)((int)v14 - v16 + v8);
    *a2 = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[1]];
    a2[7] = 0;
    a2[6] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[5] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[4] = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[2]];
    a2[11] = 0;
    a2[10] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[9] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[8] = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[3]];
    a2[15] = 0;
    a2[14] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[13] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[12] = *(_BYTE *)((int)v14 + v18 + v8);
    v19 = a4[1];
    v20 = a5[1];
    v21 = g_iVtoG[v20] + g_iUtoG[v19];
    v22 = g_iVtoR[v20];
    v23 = g_iUtoB[v19];
    LODWORD(v19) = g_iYscale[a3[4]];
    a2[19] = 0;
    a2[18] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[17] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[16] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[5]];
    a2[23] = 0;
    a2[22] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[21] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[20] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[6]];
    a2[27] = 0;
    a2[26] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[25] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[24] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[7]];
    a2[31] = 0;
    a2[30] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[29] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[28] = *(_BYTE *)((int)v19 + v23 + v8);
    v24 = a4[2];
    v25 = a5[2];
    v26 = g_iVtoG[v25] + g_iUtoG[v24];
    v27 = g_iVtoR[v25];
    v28 = g_iUtoB[v24];
    LODWORD(v24) = g_iYscale[a3[8]];
    a2[35] = 0;
    a2[34] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[33] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[32] = *(_BYTE *)((int)v24 + v28 + v8);
    LODWORD(v24) = g_iYscale[a3[9]];
    a2[39] = 0;
    a2[38] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[37] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[36] = *(_BYTE *)((int)v24 + v28 + v8);
    LODWORD(v24) = g_iYscale[a3[10]];
    a2[43] = 0;
    a2[42] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[41] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[40] = *(_BYTE *)((int)v24 + v28 + v8);
    LODWORD(v24) = g_iYscale[a3[11]];
    a2[47] = 0;
    a2[46] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[45] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[44] = *(_BYTE *)((int)v24 + v28 + v8);
    v29 = a4[3];
    v30 = a5[3];
    v31 = g_iVtoG[v30] + g_iUtoG[v29];
    v32 = g_iVtoR[v30];
    v33 = g_iUtoB[v29];
    LODWORD(v29) = g_iYscale[a3[12]];
    a2[51] = 0;
    a2[50] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[49] = *(_BYTE *)((int)v29 - v31 + v8);
    a4 += a7;
    a5 += a7;
    a2[48] = *(_BYTE *)(v33 + (int)v29 + v8);
    LODWORD(v29) = g_iYscale[a3[13]];
    a2[55] = 0;
    a2[54] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[53] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[52] = *(_BYTE *)(v33 + (int)v29 + v8);
    LODWORD(v29) = g_iYscale[a3[14]];
    a2[59] = 0;
    a2[58] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[57] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[56] = *(_BYTE *)(v33 + (int)v29 + v8);
    v34 = a3[15];
    a3 += a6;
    LODWORD(v29) = g_iYscale[v34];
    a2[63] = 0;
    a2[62] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[61] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[60] = *(_BYTE *)(v33 + (int)v29 + v8);
    a2 += a8;
    --v13;
  }
  while ( v13 );
}

```

## disassembly

```asm
0x18003b3d0  push    rbx
0x18003b3d2  push    rbp
0x18003b3d3  push    rsi
0x18003b3d4  push    rdi
0x18003b3d5  push    r12
0x18003b3d7  push    r13
0x18003b3d9  push    r14
0x18003b3db  push    r15
0x18003b3dd  mov     rbx, cs:g_rgiClapTabDec
0x18003b3e4  mov     rsi, r9
0x18003b3e7  movsxd  r12, [rsp+40h+arg_28]
0x18003b3ec  lea     r9, __ImageBase
0x18003b3f3  movsxd  r14, [rsp+40h+arg_30]
0x18003b3f8  mov     rdi, r8
0x18003b3fb  movsxd  r13, [rsp+40h+arg_38]
0x18003b403  mov     r11, rdx
0x18003b406  mov     rbp, [rsp+40h+arg_20]
0x18003b40b  mov     r15d, 10h
0x18003b411  movzx   edx, byte ptr [rsi]
0x18003b414  movzx   eax, byte ptr [rbp+0]
0x18003b418  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b420  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b428  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b430  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b438  lea     rdx, __ImageBase
0x18003b43f  movzx   eax, byte ptr [rdi]
0x18003b442  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003b449  mov     byte ptr [r11+3], 0
0x18003b44e  lea     eax, [rdx+r10]
0x18003b452  movsxd  rcx, eax
0x18003b455  mov     al, [rcx+rbx]
0x18003b458  mov     [r11+2], al
0x18003b45c  mov     eax, edx
0x18003b45e  sub     eax, r8d
0x18003b461  cdqe
0x18003b463  mov     cl, [rax+rbx]
0x18003b466  lea     eax, [rdx+r9]
0x18003b46a  mov     [r11+1], cl
0x18003b46e  movsxd  rcx, eax
0x18003b471  mov     al, [rcx+rbx]
0x18003b474  lea     rcx, __ImageBase
0x18003b47b  mov     [r11], al
0x18003b47e  movzx   eax, byte ptr [rdi+1]
0x18003b482  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b489  mov     byte ptr [r11+7], 0
0x18003b48e  lea     eax, [rdx+r10]
0x18003b492  movsxd  rcx, eax
0x18003b495  mov     al, [rcx+rbx]
0x18003b498  mov     [r11+6], al
0x18003b49c  mov     eax, edx
0x18003b49e  sub     eax, r8d
0x18003b4a1  cdqe
0x18003b4a3  mov     cl, [rax+rbx]
0x18003b4a6  lea     eax, [rdx+r9]
0x18003b4aa  mov     [r11+5], cl
0x18003b4ae  movsxd  rcx, eax
0x18003b4b1  mov     al, [rcx+rbx]
0x18003b4b4  lea     rcx, __ImageBase
0x18003b4bb  mov     [r11+4], al
0x18003b4bf  movzx   eax, byte ptr [rdi+2]
0x18003b4c3  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b4ca  mov     byte ptr [r11+0Bh], 0
0x18003b4cf  lea     eax, [rdx+r10]
0x18003b4d3  movsxd  rcx, eax
0x18003b4d6  mov     al, [rcx+rbx]
0x18003b4d9  mov     [r11+0Ah], al
0x18003b4dd  mov     eax, edx
0x18003b4df  sub     eax, r8d
0x18003b4e2  cdqe
0x18003b4e4  mov     cl, [rax+rbx]
0x18003b4e7  lea     eax, [rdx+r9]
0x18003b4eb  mov     [r11+9], cl
0x18003b4ef  movsxd  rcx, eax
0x18003b4f2  mov     al, [rcx+rbx]
0x18003b4f5  lea     rcx, __ImageBase
0x18003b4fc  mov     [r11+8], al
0x18003b500  movzx   eax, byte ptr [rdi+3]
0x18003b504  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b50b  mov     byte ptr [r11+0Fh], 0
0x18003b510  lea     eax, [rdx+r10]
0x18003b514  movsxd  rcx, eax
0x18003b517  mov     al, [rcx+rbx]
0x18003b51a  mov     [r11+0Eh], al
0x18003b51e  mov     eax, edx
0x18003b520  sub     eax, r8d
0x18003b523  cdqe
0x18003b525  mov     cl, [rax+rbx]
0x18003b528  lea     eax, [rdx+r9]
0x18003b52c  mov     [r11+0Dh], cl
0x18003b530  lea     r9, __ImageBase
0x18003b537  movsxd  rcx, eax
0x18003b53a  mov     al, [rcx+rbx]
0x18003b53d  mov     [r11+0Ch], al
0x18003b541  movzx   edx, byte ptr [rsi+1]
0x18003b545  movzx   eax, byte ptr [rbp+1]
0x18003b549  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b551  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b559  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b561  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b569  movzx   eax, byte ptr [rdi+4]
0x18003b56d  lea     rcx, __ImageBase
0x18003b574  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b57b  mov     byte ptr [r11+13h], 0
0x18003b580  lea     eax, [rdx+r10]
0x18003b584  movsxd  rcx, eax
0x18003b587  mov     al, [rcx+rbx]
0x18003b58a  mov     [r11+12h], al
0x18003b58e  mov     eax, edx
0x18003b590  sub     eax, r8d
0x18003b593  cdqe
0x18003b595  mov     cl, [rax+rbx]
0x18003b598  lea     eax, [rdx+r9]
0x18003b59c  mov     [r11+11h], cl
0x18003b5a0  movsxd  rcx, eax
0x18003b5a3  mov     al, [rcx+rbx]
0x18003b5a6  lea     rcx, __ImageBase
0x18003b5ad  mov     [r11+10h], al
0x18003b5b1  movzx   eax, byte ptr [rdi+5]
0x18003b5b5  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b5bc  mov     byte ptr [r11+17h], 0
0x18003b5c1  lea     eax, [rdx+r10]
0x18003b5c5  movsxd  rcx, eax
0x18003b5c8  mov     al, [rcx+rbx]
0x18003b5cb  mov     [r11+16h], al
0x18003b5cf  mov     eax, edx
0x18003b5d1  sub     eax, r8d
0x18003b5d4  cdqe
0x18003b5d6  mov     cl, [rax+rbx]
0x18003b5d9  lea     eax, [rdx+r9]
0x18003b5dd  mov     [r11+15h], cl
0x18003b5e1  movsxd  rcx, eax
0x18003b5e4  mov     al, [rcx+rbx]
0x18003b5e7  lea     rcx, __ImageBase
0x18003b5ee  mov     [r11+14h], al
0x18003b5f2  movzx   eax, byte ptr [rdi+6]
0x18003b5f6  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b5fd  mov     byte ptr [r11+1Bh], 0
0x18003b602  lea     eax, [rdx+r10]
0x18003b606  movsxd  rcx, eax
0x18003b609  mov     al, [rcx+rbx]
0x18003b60c  mov     [r11+1Ah], al
0x18003b610  mov     eax, edx
0x18003b612  sub     eax, r8d
0x18003b615  cdqe
0x18003b617  mov     cl, [rax+rbx]
0x18003b61a  lea     eax, [rdx+r9]
0x18003b61e  mov     [r11+19h], cl
0x18003b622  movsxd  rcx, eax
0x18003b625  mov     al, [rcx+rbx]
0x18003b628  lea     rcx, __ImageBase
0x18003b62f  mov     [r11+18h], al
0x18003b633  movzx   eax, byte ptr [rdi+7]
0x18003b637  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b63e  mov     byte ptr [r11+1Fh], 0
0x18003b643  lea     eax, [rdx+r10]
0x18003b647  movsxd  rcx, eax
0x18003b64a  mov     al, [rcx+rbx]
0x18003b64d  mov     [r11+1Eh], al
0x18003b651  mov     eax, edx
0x18003b653  sub     eax, r8d
0x18003b656  cdqe
0x18003b658  mov     cl, [rax+rbx]
0x18003b65b  lea     eax, [rdx+r9]
0x18003b65f  mov     [r11+1Dh], cl
0x18003b663  lea     r9, __ImageBase
0x18003b66a  movsxd  rcx, eax
0x18003b66d  mov     al, [rcx+rbx]
0x18003b670  lea     rcx, __ImageBase
0x18003b677  mov     [r11+1Ch], al
0x18003b67b  movzx   edx, byte ptr [rsi+2]
0x18003b67f  movzx   eax, byte ptr [rbp+2]
0x18003b683  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b68b  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b693  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b69b  movzx   eax, byte ptr [rdi+8]
0x18003b69f  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b6a7  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b6ae  mov     byte ptr [r11+23h], 0
0x18003b6b3  lea     eax, [rdx+r10]
0x18003b6b7  movsxd  rcx, eax
0x18003b6ba  mov     al, [rcx+rbx]
0x18003b6bd  mov     [r11+22h], al
0x18003b6c1  mov     eax, edx
0x18003b6c3  sub     eax, r8d
0x18003b6c6  cdqe
0x18003b6c8  mov     cl, [rax+rbx]
0x18003b6cb  lea     eax, [rdx+r9]
0x18003b6cf  mov     [r11+21h], cl
0x18003b6d3  movsxd  rcx, eax
0x18003b6d6  mov     al, [rcx+rbx]
0x18003b6d9  lea     rcx, __ImageBase
0x18003b6e0  mov     [r11+20h], al
0x18003b6e4  movzx   eax, byte ptr [rdi+9]
0x18003b6e8  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b6ef  mov     byte ptr [r11+27h], 0
0x18003b6f4  lea     eax, [rdx+r10]
0x18003b6f8  movsxd  rcx, eax
0x18003b6fb  mov     al, [rcx+rbx]
0x18003b6fe  mov     [r11+26h], al
0x18003b702  mov     eax, edx
0x18003b704  sub     eax, r8d
0x18003b707  cdqe
0x18003b709  mov     cl, [rax+rbx]
0x18003b70c  lea     eax, [rdx+r9]
0x18003b710  mov     [r11+25h], cl
0x18003b714  movsxd  rcx, eax
0x18003b717  mov     al, [rcx+rbx]
0x18003b71a  lea     rcx, __ImageBase
0x18003b721  mov     [r11+24h], al
0x18003b725  movzx   eax, byte ptr [rdi+0Ah]
0x18003b729  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b730  mov     byte ptr [r11+2Bh], 0
0x18003b735  lea     eax, [rdx+r10]
0x18003b739  movsxd  rcx, eax
0x18003b73c  mov     al, [rcx+rbx]
0x18003b73f  mov     [r11+2Ah], al
0x18003b743  mov     eax, edx
0x18003b745  sub     eax, r8d
0x18003b748  cdqe
0x18003b74a  mov     cl, [rax+rbx]
0x18003b74d  lea     eax, [rdx+r9]
0x18003b751  mov     [r11+29h], cl
0x18003b755  movsxd  rcx, eax
0x18003b758  mov     al, [rcx+rbx]
0x18003b75b  lea     rcx, __ImageBase
0x18003b762  mov     [r11+28h], al
0x18003b766  movzx   eax, byte ptr [rdi+0Bh]
0x18003b76a  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b771  mov     byte ptr [r11+2Fh], 0
0x18003b776  lea     eax, [rdx+r10]
0x18003b77a  movsxd  rcx, eax
0x18003b77d  mov     al, [rcx+rbx]
0x18003b780  mov     [r11+2Eh], al
0x18003b784  mov     eax, edx
0x18003b786  sub     eax, r8d
0x18003b789  cdqe
0x18003b78b  mov     cl, [rax+rbx]
0x18003b78e  lea     eax, [rdx+r9]
0x18003b792  mov     [r11+2Dh], cl
0x18003b796  lea     r9, __ImageBase
0x18003b79d  movsxd  rcx, eax
0x18003b7a0  mov     al, [rcx+rbx]
0x18003b7a3  lea     rcx, __ImageBase
0x18003b7aa  mov     [r11+2Ch], al
0x18003b7ae  movzx   edx, byte ptr [rsi+3]
0x18003b7b2  movzx   eax, byte ptr [rbp+3]
0x18003b7b6  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b7be  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b7c6  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b7ce  movzx   eax, byte ptr [rdi+0Ch]
0x18003b7d2  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b7da  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b7e1  mov     byte ptr [r11+33h], 0
0x18003b7e6  lea     eax, [r10+rdx]
0x18003b7ea  movsxd  rcx, eax
0x18003b7ed  mov     al, [rcx+rbx]
0x18003b7f0  mov     [r11+32h], al
0x18003b7f4  mov     eax, edx
0x18003b7f6  sub     eax, r8d
0x18003b7f9  cdqe
0x18003b7fb  mov     cl, [rax+rbx]
0x18003b7fe  mov     [r11+31h], cl
0x18003b802  lea     eax, [r9+rdx]
0x18003b806  movsxd  rcx, eax
0x18003b809  add     rsi, r14
0x18003b80c  add     rbp, r14
0x18003b80f  mov     al, [rcx+rbx]
0x18003b812  lea     rcx, __ImageBase
0x18003b819  mov     [r11+30h], al
0x18003b81d  movzx   eax, byte ptr [rdi+0Dh]
0x18003b821  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b828  mov     byte ptr [r11+37h], 0
0x18003b82d  lea     eax, [r10+rdx]
0x18003b831  movsxd  rcx, eax
0x18003b834  mov     al, [rcx+rbx]
0x18003b837  mov     [r11+36h], al
0x18003b83b  mov     eax, edx
0x18003b83d  sub     eax, r8d
0x18003b840  cdqe
0x18003b842  mov     cl, [rax+rbx]
0x18003b845  lea     eax, [r9+rdx]
0x18003b849  mov     [r11+35h], cl
0x18003b84d  movsxd  rcx, eax
0x18003b850  mov     al, [rcx+rbx]
0x18003b853  lea     rcx, __ImageBase
0x18003b85a  mov     [r11+34h], al
0x18003b85e  movzx   eax, byte ptr [rdi+0Eh]
0x18003b862  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b869  mov     byte ptr [r11+3Bh], 0
0x18003b86e  lea     eax, [r10+rdx]
0x18003b872  movsxd  rcx, eax
0x18003b875  mov     al, [rcx+rbx]
0x18003b878  mov     [r11+3Ah], al
0x18003b87c  mov     eax, edx
0x18003b87e  sub     eax, r8d
0x18003b881  cdqe
0x18003b883  mov     cl, [rax+rbx]
0x18003b886  lea     eax, [r9+rdx]
0x18003b88a  mov     [r11+39h], cl
0x18003b88e  movsxd  rcx, eax
  ... truncated ...
```
