# UpdateDstBlkRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003da30`
- end: `0x18003e000`
- name: `?UpdateDstBlkRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `1488`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003da30`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB32(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v8; // rdi
  unsigned __int8 *v9; // r10
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // r15d
  int v13; // r13d
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // r14d
  int v17; // ebp
  int v18; // esi
  __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // edi
  int v22; // r11d
  int v23; // ebx
  __int64 v24; // r12
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // r10d
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // r15
  unsigned __int8 *v31; // r12
  __int64 v32; // rcx
  __int64 v33; // r14
  __int64 v34; // rcx
  bool v35; // zf
  int v36; // [rsp+0h] [rbp-48h]
  int v37; // [rsp+4h] [rbp-44h]
  unsigned __int8 *v38; // [rsp+58h] [rbp+10h]
  const unsigned __int8 *v39; // [rsp+60h] [rbp+18h]
  const unsigned __int8 *v40; // [rsp+68h] [rbp+20h]

  v40 = a4;
  v39 = a3;
  v38 = a2;
  v8 = g_rgiClapTabDec;
  v9 = a2;
  v36 = 4;
  do
  {
    v10 = *a4;
    v11 = *a5;
    v37 = g_iUtoB[v10];
    v12 = g_iVtoG[v11] + g_iUtoG[v10];
    v13 = g_iVtoR[v11];
    LODWORD(v10) = g_iYscale[*a3];
    v9[2] = *(_BYTE *)((int)v10 + v13 + v8);
    v9[1] = *(_BYTE *)((int)v10 - v12 + v8);
    *v9 = *(_BYTE *)((int)v10 + v37 + v8);
    LODWORD(v10) = g_iYscale[a3[1]];
    v9[6] = *(_BYTE *)((int)v10 + v13 + v8);
    v9[5] = *(_BYTE *)((int)v10 - v12 + v8);
    v9[4] = *(_BYTE *)((int)v10 + v37 + v8);
    v14 = a5[1];
    v15 = a4[1];
    v16 = g_iVtoR[v14];
    v17 = g_iUtoB[v15];
    v18 = g_iVtoG[v14] + g_iUtoG[v15];
    LODWORD(v15) = g_iYscale[a3[2]];
    v9[10] = *(_BYTE *)((int)v15 + v16 + v8);
    v9[9] = *(_BYTE *)((int)v15 - v18 + v8);
    v9[8] = *(_BYTE *)((int)v15 + v17 + v8);
    LODWORD(v15) = g_iYscale[a3[3]];
    v9[14] = *(_BYTE *)((int)v15 + v16 + v8);
    v9[13] = *(_BYTE *)((int)v15 - v18 + v8);
    v9[12] = *(_BYTE *)((int)v15 + v17 + v8);
    v19 = a5[2];
    v20 = a4[2];
    v21 = g_iVtoR[v19];
    v22 = g_iVtoG[v19] + g_iUtoG[v20];
    v23 = g_iUtoB[v20];
    v24 = g_rgiClapTabDec;
    LODWORD(v20) = g_iYscale[a3[4]];
    v9[18] = *(_BYTE *)((int)v20 + v21 + g_rgiClapTabDec);
    v9[17] = *(_BYTE *)((int)v20 - v22 + v24);
    v9[16] = *(_BYTE *)((int)v20 + v23 + v24);
    LODWORD(v20) = g_iYscale[a3[5]];
    v9[22] = *(_BYTE *)((int)v20 + v21 + v24);
    v9[21] = *(_BYTE *)((int)v20 - v22 + v24);
    v9[20] = *(_BYTE *)((int)v20 + v23 + v24);
    v25 = a4[3];
    v26 = a5[3];
    v27 = g_iVtoR[v26];
    v28 = g_iUtoG[v25] + g_iVtoG[v26];
    v29 = g_iUtoB[v25];
    LODWORD(v25) = g_iYscale[v39[6]];
    v38[26] = *(_BYTE *)((int)v25 + v27 + v24);
    v38[25] = *(_BYTE *)((int)v25 - v28 + v24);
    v38[24] = *(_BYTE *)((int)v25 + v29 + v24);
    LODWORD(v25) = g_iYscale[v39[7]];
    v38[30] = *(_BYTE *)((int)v25 + v27 + v24);
    v38[29] = *(_BYTE *)((int)v25 - v28 + v24);
    v38[28] = *(_BYTE *)((int)v25 + v29 + v24);
    v40 += a7;
    a5 += a7;
    LODWORD(v25) = g_iYscale[v39[a6]];
    v38[a8 + 2] = *(_BYTE *)((int)v25 + v13 + v24);
    v38[a8 + 1] = *(_BYTE *)((int)v25 - v12 + g_rgiClapTabDec);
    v38[a8] = *(_BYTE *)((int)v25 + v37 + g_rgiClapTabDec);
    LODWORD(v25) = g_iYscale[v39[a6 + 1]];
    v38[a8 + 6] = *(_BYTE *)((int)v25 + v13 + g_rgiClapTabDec);
    LODWORD(v26) = v25 - v12;
    v30 = g_rgiClapTabDec;
    v38[a8 + 5] = *(_BYTE *)((int)v26 + g_rgiClapTabDec);
    v31 = v38;
    v38[a8 + 4] = *(_BYTE *)((int)v25 + v37 + v30);
    LODWORD(v25) = g_iYscale[v39[a6 + 2]];
    v32 = g_rgiClapTabDec;
    v38[a8 + 10] = *(_BYTE *)((int)v25 + v16 + g_rgiClapTabDec);
    v38[a8 + 9] = *(_BYTE *)((int)v25 - v18 + v32);
    v38[a8 + 8] = *(_BYTE *)((int)v25 + v17 + g_rgiClapTabDec);
    LODWORD(v25) = g_iYscale[v39[a6 + 3]];
    LODWORD(v26) = v25 + v16;
    v33 = g_rgiClapTabDec;
    v38[a8 + 14] = *(_BYTE *)((int)v26 + g_rgiClapTabDec);
    v38[a8 + 13] = *(_BYTE *)((int)v25 - v18 + v33);
    v38[a8 + 12] = *(_BYTE *)((int)v25 + v17 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 4]];
    v38[a8 + 18] = *(_BYTE *)((int)v25 + v21 + v33);
    v38[a8 + 17] = *(_BYTE *)((int)v25 - v22 + v33);
    v38[a8 + 16] = *(_BYTE *)((int)v25 + v23 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 5]];
    LODWORD(v26) = v25 + v21;
    v8 = v33;
    v38[a8 + 22] = *(_BYTE *)((int)v26 + v33);
    v38[a8 + 21] = *(_BYTE *)((int)v25 - v22 + v33);
    v38[a8 + 20] = *(_BYTE *)((int)v25 + v23 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 6]];
    v38[a8 + 26] = *(_BYTE *)((int)v25 + v27 + v33);
    v38[a8 + 25] = *(_BYTE *)((int)v25 - v28 + v33);
    v38[a8 + 24] = *(_BYTE *)((int)v25 + v29 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 7]];
    v34 = (int)v25 + v27;
    v9 = &v38[2 * a8];
    v38 = v9;
    v31[a8 + 30] = *(_BYTE *)(v34 + v33);
    LODWORD(v26) = v25 - v28;
    v35 = v36-- == 1;
    a3 = &v39[2 * a6];
    v39 = a3;
    v31[a8 + 29] = *(_BYTE *)((int)v26 + v33);
    v31[a8 + 28] = *(_BYTE *)((int)v25 + v29 + v33);
    a4 = v40;
  }
  while ( !v35 );
}

```

## disassembly

```asm
0x18003da30  mov     rax, rsp
0x18003da33  mov     [rax+8], rbx
0x18003da37  mov     [rax+20h], r9
0x18003da3b  mov     [rax+18h], r8
0x18003da3f  mov     [rax+10h], rdx
0x18003da43  push    rbp
0x18003da44  push    rsi
0x18003da45  push    rdi
0x18003da46  push    r12
0x18003da48  push    r13
0x18003da4a  push    r14
0x18003da4c  push    r15
0x18003da4e  sub     rsp, 10h
0x18003da52  mov     rdi, cs:g_rgiClapTabDec
0x18003da59  lea     rbx, __ImageBase
0x18003da60  mov     r10, rdx
0x18003da63  mov     [rsp+48h+var_48], 4
0x18003da6a  movzx   edx, byte ptr [r9]
0x18003da6e  mov     r11, [rsp+48h+arg_20]
0x18003da73  mov     r12d, rva g_iUtoB[rbx+rdx*4]
0x18003da7b  mov     r15d, rva g_iUtoG[rbx+rdx*4]
0x18003da83  movzx   eax, byte ptr [r11]
0x18003da87  mov     [rsp+48h+var_44], r12d
0x18003da8c  add     r15d, rva g_iVtoG[rbx+rax*4]
0x18003da94  mov     r13d, rva g_iVtoR[rbx+rax*4]
0x18003da9c  movzx   eax, byte ptr [r8]
0x18003daa0  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003daa7  lea     eax, [rdx+r13]
0x18003daab  movsxd  rcx, eax
0x18003daae  mov     al, [rcx+rdi]
0x18003dab1  mov     [r10+2], al
0x18003dab5  mov     eax, edx
0x18003dab7  sub     eax, r15d
0x18003daba  cdqe
0x18003dabc  mov     cl, [rax+rdi]
0x18003dabf  lea     eax, [rdx+r12]
0x18003dac3  mov     [r10+1], cl
0x18003dac7  movsxd  rcx, eax
0x18003daca  mov     al, [rcx+rdi]
0x18003dacd  mov     [r10], al
0x18003dad0  movzx   eax, byte ptr [r8+1]
0x18003dad5  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003dadc  lea     eax, [rdx+r13]
0x18003dae0  movsxd  rcx, eax
0x18003dae3  mov     al, [rcx+rdi]
0x18003dae6  mov     [r10+6], al
0x18003daea  mov     eax, edx
0x18003daec  sub     eax, r15d
0x18003daef  cdqe
0x18003daf1  mov     cl, [rax+rdi]
0x18003daf4  lea     eax, [rdx+r12]
0x18003daf8  mov     [r10+5], cl
0x18003dafc  movsxd  rcx, eax
0x18003daff  mov     al, [rcx+rdi]
0x18003db02  mov     [r10+4], al
0x18003db06  movzx   eax, byte ptr [r11+1]
0x18003db0b  movzx   edx, byte ptr [r9+1]
0x18003db10  mov     r14d, rva g_iVtoR[rbx+rax*4]
0x18003db18  mov     ebp, rva g_iUtoB[rbx+rdx*4]
0x18003db1f  mov     esi, rva g_iUtoG[rbx+rdx*4]
0x18003db26  add     esi, rva g_iVtoG[rbx+rax*4]
0x18003db2d  movzx   eax, byte ptr [r8+2]
0x18003db32  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003db39  lea     eax, [rdx+r14]
0x18003db3d  movsxd  rcx, eax
0x18003db40  mov     al, [rcx+rdi]
0x18003db43  mov     [r10+0Ah], al
0x18003db47  mov     eax, edx
0x18003db49  sub     eax, esi
0x18003db4b  cdqe
0x18003db4d  mov     cl, [rax+rdi]
0x18003db50  lea     eax, [rdx+rbp]
0x18003db53  mov     [r10+9], cl
0x18003db57  movsxd  rcx, eax
0x18003db5a  mov     al, [rcx+rdi]
0x18003db5d  mov     [r10+8], al
0x18003db61  movzx   eax, byte ptr [r8+3]
0x18003db66  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003db6d  lea     eax, [rdx+r14]
0x18003db71  movsxd  rcx, eax
0x18003db74  mov     al, [rcx+rdi]
0x18003db77  mov     [r10+0Eh], al
0x18003db7b  mov     eax, edx
0x18003db7d  sub     eax, esi
0x18003db7f  cdqe
0x18003db81  mov     cl, [rax+rdi]
0x18003db84  lea     eax, [rdx+rbp]
0x18003db87  mov     [r10+0Dh], cl
0x18003db8b  movsxd  rcx, eax
0x18003db8e  mov     al, [rcx+rdi]
0x18003db91  mov     [r10+0Ch], al
0x18003db95  movzx   eax, byte ptr [r11+2]
0x18003db9a  movzx   edx, byte ptr [r9+2]
0x18003db9f  mov     edi, rva g_iVtoR[rbx+rax*4]
0x18003dba6  mov     r11d, rva g_iUtoG[rbx+rdx*4]
0x18003dbae  add     r11d, rva g_iVtoG[rbx+rax*4]
0x18003dbb6  mov     ebx, rva g_iUtoB[rbx+rdx*4]
0x18003dbbd  movzx   eax, byte ptr [r8+4]
0x18003dbc2  mov     r12, cs:g_rgiClapTabDec
0x18003dbc9  lea     rdx, __ImageBase
0x18003dbd0  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003dbd7  lea     eax, [rdx+rdi]
0x18003dbda  movsxd  rcx, eax
0x18003dbdd  mov     al, [rcx+r12]
0x18003dbe1  mov     [r10+12h], al
0x18003dbe5  mov     eax, edx
0x18003dbe7  sub     eax, r11d
0x18003dbea  cdqe
0x18003dbec  mov     cl, [rax+r12]
0x18003dbf0  lea     eax, [rdx+rbx]
0x18003dbf3  mov     [r10+11h], cl
0x18003dbf7  movsxd  rcx, eax
0x18003dbfa  mov     al, [rcx+r12]
0x18003dbfe  mov     [r10+10h], al
0x18003dc02  movzx   eax, byte ptr [r8+5]
0x18003dc07  lea     r8, __ImageBase
0x18003dc0e  mov     edx, rva g_iYscale[r8+rax*4]
0x18003dc16  lea     eax, [rdx+rdi]
0x18003dc19  movsxd  rcx, eax
0x18003dc1c  mov     al, [rcx+r12]
0x18003dc20  mov     [r10+16h], al
0x18003dc24  mov     eax, edx
0x18003dc26  sub     eax, r11d
0x18003dc29  cdqe
0x18003dc2b  mov     cl, [rax+r12]
0x18003dc2f  lea     eax, [rdx+rbx]
0x18003dc32  mov     [r10+15h], cl
0x18003dc36  movsxd  rcx, eax
0x18003dc39  mov     al, [rcx+r12]
0x18003dc3d  mov     [r10+14h], al
0x18003dc41  movzx   edx, byte ptr [r9+3]
0x18003dc46  mov     rax, [rsp+48h+arg_20]
0x18003dc4b  mov     ecx, rva g_iUtoG[r8+rdx*4]
0x18003dc53  movzx   eax, byte ptr [rax+3]
0x18003dc57  mov     r10d, rva g_iVtoR[r8+rax*4]
0x18003dc5f  mov     r8d, rva g_iVtoG[r8+rax*4]
0x18003dc67  mov     rax, [rsp+48h+arg_10]
0x18003dc6c  add     r8d, ecx
0x18003dc6f  lea     rcx, __ImageBase
0x18003dc76  mov     r9d, rva g_iUtoB[rcx+rdx*4]
0x18003dc7e  movzx   eax, byte ptr [rax+6]
0x18003dc82  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003dc89  lea     eax, [rdx+r10]
0x18003dc8d  movsxd  rcx, eax
0x18003dc90  mov     al, [rcx+r12]
0x18003dc94  mov     rcx, [rsp+48h+arg_8]
0x18003dc99  mov     [rcx+1Ah], al
0x18003dc9c  mov     eax, edx
0x18003dc9e  sub     eax, r8d
0x18003dca1  cdqe
0x18003dca3  mov     cl, [rax+r12]
0x18003dca7  mov     rax, [rsp+48h+arg_8]
0x18003dcac  mov     [rax+19h], cl
0x18003dcaf  lea     eax, [rdx+r9]
0x18003dcb3  movsxd  rcx, eax
0x18003dcb6  lea     rdx, __ImageBase
0x18003dcbd  mov     al, [rcx+r12]
0x18003dcc1  mov     rcx, [rsp+48h+arg_8]
0x18003dcc6  mov     [rcx+18h], al
0x18003dcc9  mov     rax, [rsp+48h+arg_10]
0x18003dcce  movzx   eax, byte ptr [rax+7]
0x18003dcd2  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003dcd9  lea     eax, [rdx+r10]
0x18003dcdd  movsxd  rcx, eax
0x18003dce0  mov     al, [rcx+r12]
0x18003dce4  mov     rcx, [rsp+48h+arg_8]
0x18003dce9  mov     [rcx+1Eh], al
0x18003dcec  mov     eax, edx
0x18003dcee  sub     eax, r8d
0x18003dcf1  cdqe
0x18003dcf3  mov     cl, [rax+r12]
0x18003dcf7  mov     rax, [rsp+48h+arg_8]
0x18003dcfc  mov     [rax+1Dh], cl
0x18003dcff  lea     eax, [rdx+r9]
0x18003dd03  movsxd  rcx, eax
0x18003dd06  mov     al, [rcx+r12]
0x18003dd0a  mov     rcx, [rsp+48h+arg_8]
0x18003dd0f  mov     [rcx+1Ch], al
0x18003dd12  movsxd  rax, [rsp+48h+arg_30]
0x18003dd1a  add     [rsp+48h+arg_18], rax
0x18003dd1f  add     [rsp+48h+arg_20], rax
0x18003dd24  mov     rcx, [rsp+48h+arg_10]
0x18003dd29  movsxd  rax, [rsp+48h+arg_28]
0x18003dd2e  movzx   eax, byte ptr [rax+rcx]
0x18003dd32  lea     rcx, __ImageBase
0x18003dd39  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003dd40  lea     eax, [rdx+r13]
0x18003dd44  movsxd  rcx, eax
0x18003dd47  mov     al, [rcx+r12]
0x18003dd4b  mov     r12, [rsp+48h+arg_8]
0x18003dd50  movsxd  rcx, [rsp+48h+arg_38]
0x18003dd58  mov     [rcx+r12+2], al
0x18003dd5d  mov     eax, edx
0x18003dd5f  mov     rcx, cs:g_rgiClapTabDec
0x18003dd66  sub     eax, r15d
0x18003dd69  cdqe
0x18003dd6b  mov     cl, [rax+rcx]
0x18003dd6e  movsxd  rax, [rsp+48h+arg_38]
0x18003dd76  mov     [rax+r12+1], cl
0x18003dd7b  mov     r12d, [rsp+48h+var_44]
0x18003dd80  lea     eax, [rdx+r12]
0x18003dd84  mov     rdx, [rsp+48h+arg_8]
0x18003dd89  movsxd  rcx, eax
0x18003dd8c  mov     rax, cs:g_rgiClapTabDec
0x18003dd93  mov     al, [rcx+rax]
0x18003dd96  movsxd  rcx, [rsp+48h+arg_38]
0x18003dd9e  mov     [rcx+rdx], al
0x18003dda1  mov     rcx, [rsp+48h+arg_10]
0x18003dda6  movsxd  rax, [rsp+48h+arg_28]
0x18003ddab  movzx   eax, byte ptr [rax+rcx+1]
0x18003ddb0  lea     rcx, __ImageBase
0x18003ddb7  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003ddbe  lea     eax, [rdx+r13]
0x18003ddc2  movsxd  r13, [rsp+48h+arg_38]
0x18003ddca  movsxd  rcx, eax
0x18003ddcd  mov     rax, cs:g_rgiClapTabDec
0x18003ddd4  mov     al, [rcx+rax]
0x18003ddd7  mov     rcx, [rsp+48h+arg_8]
0x18003dddc  mov     [rcx+r13+6], al
0x18003dde1  mov     eax, edx
0x18003dde3  sub     eax, r15d
0x18003dde6  mov     r15, cs:g_rgiClapTabDec
0x18003dded  cdqe
0x18003ddef  mov     cl, [rax+r15]
0x18003ddf3  mov     rax, [rsp+48h+arg_8]
0x18003ddf8  mov     [rax+r13+5], cl
0x18003ddfd  lea     eax, [rdx+r12]
0x18003de01  mov     r12, [rsp+48h+arg_8]
0x18003de06  movsxd  rcx, eax
0x18003de09  mov     al, [rcx+r15]
0x18003de0d  lea     rcx, __ImageBase
0x18003de14  movsxd  r15, [rsp+48h+arg_28]
0x18003de19  mov     [r12+r13+4], al
0x18003de1e  mov     rax, [rsp+48h+arg_10]
0x18003de23  movzx   eax, byte ptr [r15+rax+2]
0x18003de29  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003de30  lea     eax, [rdx+r14]
0x18003de34  movsxd  rcx, eax
0x18003de37  mov     rax, cs:g_rgiClapTabDec
0x18003de3e  mov     al, [rcx+rax]
0x18003de41  mov     rcx, cs:g_rgiClapTabDec
0x18003de48  mov     [r12+r13+0Ah], al
0x18003de4d  mov     eax, edx
0x18003de4f  sub     eax, esi
0x18003de51  cdqe
0x18003de53  mov     cl, [rax+rcx]
0x18003de56  lea     eax, [rdx+rbp]
0x18003de59  mov     [r12+r13+9], cl
0x18003de5e  movsxd  rcx, eax
0x18003de61  mov     rax, cs:g_rgiClapTabDec
0x18003de68  mov     al, [rcx+rax]
0x18003de6b  lea     rcx, __ImageBase
0x18003de72  mov     [r12+r13+8], al
0x18003de77  mov     rax, [rsp+48h+arg_10]
0x18003de7c  movzx   eax, byte ptr [r15+rax+3]
0x18003de82  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003de89  lea     eax, [rdx+r14]
0x18003de8d  mov     r14, cs:g_rgiClapTabDec
0x18003de94  movsxd  rcx, eax
0x18003de97  mov     al, [rcx+r14]
0x18003de9b  mov     [r12+r13+0Eh], al
0x18003dea0  mov     eax, edx
0x18003dea2  sub     eax, esi
0x18003dea4  mov     rsi, [rsp+48h+arg_10]
0x18003dea9  cdqe
0x18003deab  mov     cl, [rax+r14]
0x18003deaf  lea     eax, [rdx+rbp]
0x18003deb2  mov     [r12+r13+0Dh], cl
0x18003deb7  lea     rbp, __ImageBase
0x18003debe  movsxd  rcx, eax
0x18003dec1  mov     al, [rcx+r14]
0x18003dec5  mov     [r12+r13+0Ch], al
0x18003deca  movzx   eax, byte ptr [r15+rsi+4]
0x18003ded0  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18003ded7  lea     eax, [rdx+rdi]
0x18003deda  movsxd  rcx, eax
0x18003dedd  mov     al, [rcx+r14]
0x18003dee1  mov     [r12+r13+12h], al
0x18003dee6  mov     eax, edx
0x18003dee8  sub     eax, r11d
0x18003deeb  cdqe
0x18003deed  mov     cl, [rax+r14]
0x18003def1  lea     eax, [rdx+rbx]
0x18003def4  mov     [r12+r13+11h], cl
0x18003def9  movsxd  rcx, eax
0x18003defc  mov     al, [rcx+r14]
0x18003df00  mov     [r12+r13+10h], al
0x18003df05  movzx   eax, byte ptr [r15+rsi+5]
0x18003df0b  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18003df12  lea     eax, [rdx+rdi]
0x18003df15  mov     rdi, r14
0x18003df18  movsxd  rcx, eax
0x18003df1b  mov     al, [rcx+r14]
0x18003df1f  mov     [r12+r13+16h], al
0x18003df24  mov     eax, edx
0x18003df26  sub     eax, r11d
0x18003df29  cdqe
0x18003df2b  mov     cl, [rax+r14]
0x18003df2f  lea     eax, [rdx+rbx]
0x18003df32  mov     [r12+r13+15h], cl
  ... truncated ...
```
