# UpdateDstBlkRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003d450`
- end: `0x18003da20`
- name: `?UpdateDstBlkRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `1488`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003d450`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB24(
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
    v9[5] = *(_BYTE *)((int)v10 + v13 + v8);
    v9[4] = *(_BYTE *)((int)v10 - v12 + v8);
    v9[3] = *(_BYTE *)((int)v10 + v37 + v8);
    v14 = a5[1];
    v15 = a4[1];
    v16 = g_iVtoR[v14];
    v17 = g_iUtoB[v15];
    v18 = g_iVtoG[v14] + g_iUtoG[v15];
    LODWORD(v15) = g_iYscale[a3[2]];
    v9[8] = *(_BYTE *)((int)v15 + v16 + v8);
    v9[7] = *(_BYTE *)((int)v15 - v18 + v8);
    v9[6] = *(_BYTE *)((int)v15 + v17 + v8);
    LODWORD(v15) = g_iYscale[a3[3]];
    v9[11] = *(_BYTE *)((int)v15 + v16 + v8);
    v9[10] = *(_BYTE *)((int)v15 - v18 + v8);
    v9[9] = *(_BYTE *)((int)v15 + v17 + v8);
    v19 = a5[2];
    v20 = a4[2];
    v21 = g_iVtoR[v19];
    v22 = g_iVtoG[v19] + g_iUtoG[v20];
    v23 = g_iUtoB[v20];
    v24 = g_rgiClapTabDec;
    LODWORD(v20) = g_iYscale[a3[4]];
    v9[14] = *(_BYTE *)((int)v20 + v21 + g_rgiClapTabDec);
    v9[13] = *(_BYTE *)((int)v20 - v22 + v24);
    v9[12] = *(_BYTE *)((int)v20 + v23 + v24);
    LODWORD(v20) = g_iYscale[a3[5]];
    v9[17] = *(_BYTE *)((int)v20 + v21 + v24);
    v9[16] = *(_BYTE *)((int)v20 - v22 + v24);
    v9[15] = *(_BYTE *)((int)v20 + v23 + v24);
    v25 = a4[3];
    v26 = a5[3];
    v27 = g_iVtoR[v26];
    v28 = g_iUtoG[v25] + g_iVtoG[v26];
    v29 = g_iUtoB[v25];
    LODWORD(v25) = g_iYscale[v39[6]];
    v38[20] = *(_BYTE *)((int)v25 + v27 + v24);
    v38[19] = *(_BYTE *)((int)v25 - v28 + v24);
    v38[18] = *(_BYTE *)((int)v25 + v29 + v24);
    LODWORD(v25) = g_iYscale[v39[7]];
    v38[23] = *(_BYTE *)((int)v25 + v27 + v24);
    v38[22] = *(_BYTE *)((int)v25 - v28 + v24);
    v38[21] = *(_BYTE *)((int)v25 + v29 + v24);
    v40 += a7;
    a5 += a7;
    LODWORD(v25) = g_iYscale[v39[a6]];
    v38[a8 + 2] = *(_BYTE *)((int)v25 + v13 + v24);
    v38[a8 + 1] = *(_BYTE *)((int)v25 - v12 + g_rgiClapTabDec);
    v38[a8] = *(_BYTE *)((int)v25 + v37 + g_rgiClapTabDec);
    LODWORD(v25) = g_iYscale[v39[a6 + 1]];
    v38[a8 + 5] = *(_BYTE *)((int)v25 + v13 + g_rgiClapTabDec);
    LODWORD(v26) = v25 - v12;
    v30 = g_rgiClapTabDec;
    v38[a8 + 4] = *(_BYTE *)((int)v26 + g_rgiClapTabDec);
    v31 = v38;
    v38[a8 + 3] = *(_BYTE *)((int)v25 + v37 + v30);
    LODWORD(v25) = g_iYscale[v39[a6 + 2]];
    v32 = g_rgiClapTabDec;
    v38[a8 + 8] = *(_BYTE *)((int)v25 + v16 + g_rgiClapTabDec);
    v38[a8 + 7] = *(_BYTE *)((int)v25 - v18 + v32);
    v38[a8 + 6] = *(_BYTE *)((int)v25 + v17 + g_rgiClapTabDec);
    LODWORD(v25) = g_iYscale[v39[a6 + 3]];
    LODWORD(v26) = v25 + v16;
    v33 = g_rgiClapTabDec;
    v38[a8 + 11] = *(_BYTE *)((int)v26 + g_rgiClapTabDec);
    v38[a8 + 10] = *(_BYTE *)((int)v25 - v18 + v33);
    v38[a8 + 9] = *(_BYTE *)((int)v25 + v17 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 4]];
    v38[a8 + 14] = *(_BYTE *)((int)v25 + v21 + v33);
    v38[a8 + 13] = *(_BYTE *)((int)v25 - v22 + v33);
    v38[a8 + 12] = *(_BYTE *)((int)v25 + v23 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 5]];
    LODWORD(v26) = v25 + v21;
    v8 = v33;
    v38[a8 + 17] = *(_BYTE *)((int)v26 + v33);
    v38[a8 + 16] = *(_BYTE *)((int)v25 - v22 + v33);
    v38[a8 + 15] = *(_BYTE *)((int)v25 + v23 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 6]];
    v38[a8 + 20] = *(_BYTE *)((int)v25 + v27 + v33);
    v38[a8 + 19] = *(_BYTE *)((int)v25 - v28 + v33);
    v38[a8 + 18] = *(_BYTE *)((int)v25 + v29 + v33);
    LODWORD(v25) = g_iYscale[v39[a6 + 7]];
    v34 = (int)v25 + v27;
    v9 = &v38[2 * a8];
    v38 = v9;
    v31[a8 + 23] = *(_BYTE *)(v34 + v33);
    LODWORD(v26) = v25 - v28;
    v35 = v36-- == 1;
    a3 = &v39[2 * a6];
    v39 = a3;
    v31[a8 + 22] = *(_BYTE *)((int)v26 + v33);
    v31[a8 + 21] = *(_BYTE *)((int)v25 + v29 + v33);
    a4 = v40;
  }
  while ( !v35 );
}

```

## disassembly

```asm
0x18003d450  mov     rax, rsp
0x18003d453  mov     [rax+8], rbx
0x18003d457  mov     [rax+20h], r9
0x18003d45b  mov     [rax+18h], r8
0x18003d45f  mov     [rax+10h], rdx
0x18003d463  push    rbp
0x18003d464  push    rsi
0x18003d465  push    rdi
0x18003d466  push    r12
0x18003d468  push    r13
0x18003d46a  push    r14
0x18003d46c  push    r15
0x18003d46e  sub     rsp, 10h
0x18003d472  mov     rdi, cs:g_rgiClapTabDec
0x18003d479  lea     rbx, __ImageBase
0x18003d480  mov     r10, rdx
0x18003d483  mov     [rsp+48h+var_48], 4
0x18003d48a  movzx   edx, byte ptr [r9]
0x18003d48e  mov     r11, [rsp+48h+arg_20]
0x18003d493  mov     r12d, rva g_iUtoB[rbx+rdx*4]
0x18003d49b  mov     r15d, rva g_iUtoG[rbx+rdx*4]
0x18003d4a3  movzx   eax, byte ptr [r11]
0x18003d4a7  mov     [rsp+48h+var_44], r12d
0x18003d4ac  add     r15d, rva g_iVtoG[rbx+rax*4]
0x18003d4b4  mov     r13d, rva g_iVtoR[rbx+rax*4]
0x18003d4bc  movzx   eax, byte ptr [r8]
0x18003d4c0  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003d4c7  lea     eax, [rdx+r13]
0x18003d4cb  movsxd  rcx, eax
0x18003d4ce  mov     al, [rcx+rdi]
0x18003d4d1  mov     [r10+2], al
0x18003d4d5  mov     eax, edx
0x18003d4d7  sub     eax, r15d
0x18003d4da  cdqe
0x18003d4dc  mov     cl, [rax+rdi]
0x18003d4df  lea     eax, [rdx+r12]
0x18003d4e3  mov     [r10+1], cl
0x18003d4e7  movsxd  rcx, eax
0x18003d4ea  mov     al, [rcx+rdi]
0x18003d4ed  mov     [r10], al
0x18003d4f0  movzx   eax, byte ptr [r8+1]
0x18003d4f5  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003d4fc  lea     eax, [rdx+r13]
0x18003d500  movsxd  rcx, eax
0x18003d503  mov     al, [rcx+rdi]
0x18003d506  mov     [r10+5], al
0x18003d50a  mov     eax, edx
0x18003d50c  sub     eax, r15d
0x18003d50f  cdqe
0x18003d511  mov     cl, [rax+rdi]
0x18003d514  lea     eax, [rdx+r12]
0x18003d518  mov     [r10+4], cl
0x18003d51c  movsxd  rcx, eax
0x18003d51f  mov     al, [rcx+rdi]
0x18003d522  mov     [r10+3], al
0x18003d526  movzx   eax, byte ptr [r11+1]
0x18003d52b  movzx   edx, byte ptr [r9+1]
0x18003d530  mov     r14d, rva g_iVtoR[rbx+rax*4]
0x18003d538  mov     ebp, rva g_iUtoB[rbx+rdx*4]
0x18003d53f  mov     esi, rva g_iUtoG[rbx+rdx*4]
0x18003d546  add     esi, rva g_iVtoG[rbx+rax*4]
0x18003d54d  movzx   eax, byte ptr [r8+2]
0x18003d552  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003d559  lea     eax, [rdx+r14]
0x18003d55d  movsxd  rcx, eax
0x18003d560  mov     al, [rcx+rdi]
0x18003d563  mov     [r10+8], al
0x18003d567  mov     eax, edx
0x18003d569  sub     eax, esi
0x18003d56b  cdqe
0x18003d56d  mov     cl, [rax+rdi]
0x18003d570  lea     eax, [rdx+rbp]
0x18003d573  mov     [r10+7], cl
0x18003d577  movsxd  rcx, eax
0x18003d57a  mov     al, [rcx+rdi]
0x18003d57d  mov     [r10+6], al
0x18003d581  movzx   eax, byte ptr [r8+3]
0x18003d586  mov     edx, rva g_iYscale[rbx+rax*4]
0x18003d58d  lea     eax, [rdx+r14]
0x18003d591  movsxd  rcx, eax
0x18003d594  mov     al, [rcx+rdi]
0x18003d597  mov     [r10+0Bh], al
0x18003d59b  mov     eax, edx
0x18003d59d  sub     eax, esi
0x18003d59f  cdqe
0x18003d5a1  mov     cl, [rax+rdi]
0x18003d5a4  lea     eax, [rdx+rbp]
0x18003d5a7  mov     [r10+0Ah], cl
0x18003d5ab  movsxd  rcx, eax
0x18003d5ae  mov     al, [rcx+rdi]
0x18003d5b1  mov     [r10+9], al
0x18003d5b5  movzx   eax, byte ptr [r11+2]
0x18003d5ba  movzx   edx, byte ptr [r9+2]
0x18003d5bf  mov     edi, rva g_iVtoR[rbx+rax*4]
0x18003d5c6  mov     r11d, rva g_iUtoG[rbx+rdx*4]
0x18003d5ce  add     r11d, rva g_iVtoG[rbx+rax*4]
0x18003d5d6  mov     ebx, rva g_iUtoB[rbx+rdx*4]
0x18003d5dd  movzx   eax, byte ptr [r8+4]
0x18003d5e2  mov     r12, cs:g_rgiClapTabDec
0x18003d5e9  lea     rdx, __ImageBase
0x18003d5f0  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003d5f7  lea     eax, [rdx+rdi]
0x18003d5fa  movsxd  rcx, eax
0x18003d5fd  mov     al, [rcx+r12]
0x18003d601  mov     [r10+0Eh], al
0x18003d605  mov     eax, edx
0x18003d607  sub     eax, r11d
0x18003d60a  cdqe
0x18003d60c  mov     cl, [rax+r12]
0x18003d610  lea     eax, [rdx+rbx]
0x18003d613  mov     [r10+0Dh], cl
0x18003d617  movsxd  rcx, eax
0x18003d61a  mov     al, [rcx+r12]
0x18003d61e  mov     [r10+0Ch], al
0x18003d622  movzx   eax, byte ptr [r8+5]
0x18003d627  lea     r8, __ImageBase
0x18003d62e  mov     edx, rva g_iYscale[r8+rax*4]
0x18003d636  lea     eax, [rdx+rdi]
0x18003d639  movsxd  rcx, eax
0x18003d63c  mov     al, [rcx+r12]
0x18003d640  mov     [r10+11h], al
0x18003d644  mov     eax, edx
0x18003d646  sub     eax, r11d
0x18003d649  cdqe
0x18003d64b  mov     cl, [rax+r12]
0x18003d64f  lea     eax, [rdx+rbx]
0x18003d652  mov     [r10+10h], cl
0x18003d656  movsxd  rcx, eax
0x18003d659  mov     al, [rcx+r12]
0x18003d65d  mov     [r10+0Fh], al
0x18003d661  movzx   edx, byte ptr [r9+3]
0x18003d666  mov     rax, [rsp+48h+arg_20]
0x18003d66b  mov     ecx, rva g_iUtoG[r8+rdx*4]
0x18003d673  movzx   eax, byte ptr [rax+3]
0x18003d677  mov     r10d, rva g_iVtoR[r8+rax*4]
0x18003d67f  mov     r8d, rva g_iVtoG[r8+rax*4]
0x18003d687  mov     rax, [rsp+48h+arg_10]
0x18003d68c  add     r8d, ecx
0x18003d68f  lea     rcx, __ImageBase
0x18003d696  mov     r9d, rva g_iUtoB[rcx+rdx*4]
0x18003d69e  movzx   eax, byte ptr [rax+6]
0x18003d6a2  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003d6a9  lea     eax, [rdx+r10]
0x18003d6ad  movsxd  rcx, eax
0x18003d6b0  mov     al, [rcx+r12]
0x18003d6b4  mov     rcx, [rsp+48h+arg_8]
0x18003d6b9  mov     [rcx+14h], al
0x18003d6bc  mov     eax, edx
0x18003d6be  sub     eax, r8d
0x18003d6c1  cdqe
0x18003d6c3  mov     cl, [rax+r12]
0x18003d6c7  mov     rax, [rsp+48h+arg_8]
0x18003d6cc  mov     [rax+13h], cl
0x18003d6cf  lea     eax, [rdx+r9]
0x18003d6d3  movsxd  rcx, eax
0x18003d6d6  lea     rdx, __ImageBase
0x18003d6dd  mov     al, [rcx+r12]
0x18003d6e1  mov     rcx, [rsp+48h+arg_8]
0x18003d6e6  mov     [rcx+12h], al
0x18003d6e9  mov     rax, [rsp+48h+arg_10]
0x18003d6ee  movzx   eax, byte ptr [rax+7]
0x18003d6f2  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003d6f9  lea     eax, [rdx+r10]
0x18003d6fd  movsxd  rcx, eax
0x18003d700  mov     al, [rcx+r12]
0x18003d704  mov     rcx, [rsp+48h+arg_8]
0x18003d709  mov     [rcx+17h], al
0x18003d70c  mov     eax, edx
0x18003d70e  sub     eax, r8d
0x18003d711  cdqe
0x18003d713  mov     cl, [rax+r12]
0x18003d717  mov     rax, [rsp+48h+arg_8]
0x18003d71c  mov     [rax+16h], cl
0x18003d71f  lea     eax, [rdx+r9]
0x18003d723  movsxd  rcx, eax
0x18003d726  mov     al, [rcx+r12]
0x18003d72a  mov     rcx, [rsp+48h+arg_8]
0x18003d72f  mov     [rcx+15h], al
0x18003d732  movsxd  rax, [rsp+48h+arg_30]
0x18003d73a  add     [rsp+48h+arg_18], rax
0x18003d73f  add     [rsp+48h+arg_20], rax
0x18003d744  mov     rcx, [rsp+48h+arg_10]
0x18003d749  movsxd  rax, [rsp+48h+arg_28]
0x18003d74e  movzx   eax, byte ptr [rax+rcx]
0x18003d752  lea     rcx, __ImageBase
0x18003d759  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003d760  lea     eax, [rdx+r13]
0x18003d764  movsxd  rcx, eax
0x18003d767  mov     al, [rcx+r12]
0x18003d76b  mov     r12, [rsp+48h+arg_8]
0x18003d770  movsxd  rcx, [rsp+48h+arg_38]
0x18003d778  mov     [rcx+r12+2], al
0x18003d77d  mov     eax, edx
0x18003d77f  mov     rcx, cs:g_rgiClapTabDec
0x18003d786  sub     eax, r15d
0x18003d789  cdqe
0x18003d78b  mov     cl, [rax+rcx]
0x18003d78e  movsxd  rax, [rsp+48h+arg_38]
0x18003d796  mov     [rax+r12+1], cl
0x18003d79b  mov     r12d, [rsp+48h+var_44]
0x18003d7a0  lea     eax, [rdx+r12]
0x18003d7a4  mov     rdx, [rsp+48h+arg_8]
0x18003d7a9  movsxd  rcx, eax
0x18003d7ac  mov     rax, cs:g_rgiClapTabDec
0x18003d7b3  mov     al, [rcx+rax]
0x18003d7b6  movsxd  rcx, [rsp+48h+arg_38]
0x18003d7be  mov     [rcx+rdx], al
0x18003d7c1  mov     rcx, [rsp+48h+arg_10]
0x18003d7c6  movsxd  rax, [rsp+48h+arg_28]
0x18003d7cb  movzx   eax, byte ptr [rax+rcx+1]
0x18003d7d0  lea     rcx, __ImageBase
0x18003d7d7  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003d7de  lea     eax, [rdx+r13]
0x18003d7e2  movsxd  r13, [rsp+48h+arg_38]
0x18003d7ea  movsxd  rcx, eax
0x18003d7ed  mov     rax, cs:g_rgiClapTabDec
0x18003d7f4  mov     al, [rcx+rax]
0x18003d7f7  mov     rcx, [rsp+48h+arg_8]
0x18003d7fc  mov     [rcx+r13+5], al
0x18003d801  mov     eax, edx
0x18003d803  sub     eax, r15d
0x18003d806  mov     r15, cs:g_rgiClapTabDec
0x18003d80d  cdqe
0x18003d80f  mov     cl, [rax+r15]
0x18003d813  mov     rax, [rsp+48h+arg_8]
0x18003d818  mov     [rax+r13+4], cl
0x18003d81d  lea     eax, [rdx+r12]
0x18003d821  mov     r12, [rsp+48h+arg_8]
0x18003d826  movsxd  rcx, eax
0x18003d829  mov     al, [rcx+r15]
0x18003d82d  lea     rcx, __ImageBase
0x18003d834  movsxd  r15, [rsp+48h+arg_28]
0x18003d839  mov     [r12+r13+3], al
0x18003d83e  mov     rax, [rsp+48h+arg_10]
0x18003d843  movzx   eax, byte ptr [r15+rax+2]
0x18003d849  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003d850  lea     eax, [rdx+r14]
0x18003d854  movsxd  rcx, eax
0x18003d857  mov     rax, cs:g_rgiClapTabDec
0x18003d85e  mov     al, [rcx+rax]
0x18003d861  mov     rcx, cs:g_rgiClapTabDec
0x18003d868  mov     [r12+r13+8], al
0x18003d86d  mov     eax, edx
0x18003d86f  sub     eax, esi
0x18003d871  cdqe
0x18003d873  mov     cl, [rax+rcx]
0x18003d876  lea     eax, [rdx+rbp]
0x18003d879  mov     [r12+r13+7], cl
0x18003d87e  movsxd  rcx, eax
0x18003d881  mov     rax, cs:g_rgiClapTabDec
0x18003d888  mov     al, [rcx+rax]
0x18003d88b  lea     rcx, __ImageBase
0x18003d892  mov     [r12+r13+6], al
0x18003d897  mov     rax, [rsp+48h+arg_10]
0x18003d89c  movzx   eax, byte ptr [r15+rax+3]
0x18003d8a2  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003d8a9  lea     eax, [rdx+r14]
0x18003d8ad  mov     r14, cs:g_rgiClapTabDec
0x18003d8b4  movsxd  rcx, eax
0x18003d8b7  mov     al, [rcx+r14]
0x18003d8bb  mov     [r12+r13+0Bh], al
0x18003d8c0  mov     eax, edx
0x18003d8c2  sub     eax, esi
0x18003d8c4  mov     rsi, [rsp+48h+arg_10]
0x18003d8c9  cdqe
0x18003d8cb  mov     cl, [rax+r14]
0x18003d8cf  lea     eax, [rdx+rbp]
0x18003d8d2  mov     [r12+r13+0Ah], cl
0x18003d8d7  lea     rbp, __ImageBase
0x18003d8de  movsxd  rcx, eax
0x18003d8e1  mov     al, [rcx+r14]
0x18003d8e5  mov     [r12+r13+9], al
0x18003d8ea  movzx   eax, byte ptr [r15+rsi+4]
0x18003d8f0  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18003d8f7  lea     eax, [rdx+rdi]
0x18003d8fa  movsxd  rcx, eax
0x18003d8fd  mov     al, [rcx+r14]
0x18003d901  mov     [r12+r13+0Eh], al
0x18003d906  mov     eax, edx
0x18003d908  sub     eax, r11d
0x18003d90b  cdqe
0x18003d90d  mov     cl, [rax+r14]
0x18003d911  lea     eax, [rdx+rbx]
0x18003d914  mov     [r12+r13+0Dh], cl
0x18003d919  movsxd  rcx, eax
0x18003d91c  mov     al, [rcx+r14]
0x18003d920  mov     [r12+r13+0Ch], al
0x18003d925  movzx   eax, byte ptr [r15+rsi+5]
0x18003d92b  mov     edx, ss:rva g_iYscale[rbp+rax*4]
0x18003d932  lea     eax, [rdx+rdi]
0x18003d935  mov     rdi, r14
0x18003d938  movsxd  rcx, eax
0x18003d93b  mov     al, [rcx+r14]
0x18003d93f  mov     [r12+r13+11h], al
0x18003d944  mov     eax, edx
0x18003d946  sub     eax, r11d
0x18003d949  cdqe
0x18003d94b  mov     cl, [rax+r14]
0x18003d94f  lea     eax, [rdx+rbx]
0x18003d952  mov     [r12+r13+10h], cl
  ... truncated ...
```
