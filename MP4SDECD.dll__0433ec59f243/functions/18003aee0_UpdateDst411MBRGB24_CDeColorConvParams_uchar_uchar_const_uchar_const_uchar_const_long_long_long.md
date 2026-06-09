# UpdateDst411MBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003aee0`
- end: `0x18003b3bd`
- name: `?UpdateDst411MBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `1245`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003bbc0`

## callees

- `0x18003aee0`

## pseudocode

```c
void __fastcall UpdateDst411MBRGB24(
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
    a2[2] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[1] = *(_BYTE *)((int)v14 - v16 + v8);
    *a2 = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[1]];
    a2[5] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[4] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[3] = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[2]];
    a2[8] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[7] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[6] = *(_BYTE *)((int)v14 + v18 + v8);
    LODWORD(v14) = g_iYscale[a3[3]];
    a2[11] = *(_BYTE *)((int)v14 + v17 + v8);
    a2[10] = *(_BYTE *)((int)v14 - v16 + v8);
    a2[9] = *(_BYTE *)((int)v14 + v18 + v8);
    v19 = a4[1];
    v20 = a5[1];
    v21 = g_iVtoG[v20] + g_iUtoG[v19];
    v22 = g_iVtoR[v20];
    v23 = g_iUtoB[v19];
    LODWORD(v19) = g_iYscale[a3[4]];
    a2[14] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[13] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[12] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[5]];
    a2[17] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[16] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[15] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[6]];
    a2[20] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[19] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[18] = *(_BYTE *)((int)v19 + v23 + v8);
    LODWORD(v19) = g_iYscale[a3[7]];
    a2[23] = *(_BYTE *)((int)v19 + v22 + v8);
    a2[22] = *(_BYTE *)((int)v19 - v21 + v8);
    a2[21] = *(_BYTE *)((int)v19 + v23 + v8);
    v24 = a4[2];
    v25 = a5[2];
    v26 = g_iVtoG[v25] + g_iUtoG[v24];
    v27 = g_iVtoR[v25];
    v28 = g_iUtoB[v24];
    LODWORD(v24) = g_iYscale[a3[8]];
    a2[26] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[25] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[24] = *(_BYTE *)((int)v24 + v28 + v8);
    LODWORD(v24) = g_iYscale[a3[9]];
    a2[29] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[28] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[27] = *(_BYTE *)((int)v24 + v28 + v8);
    LODWORD(v24) = g_iYscale[a3[10]];
    a2[32] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[31] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[30] = *(_BYTE *)((int)v24 + v28 + v8);
    LODWORD(v24) = g_iYscale[a3[11]];
    a2[35] = *(_BYTE *)((int)v24 + v27 + v8);
    a2[34] = *(_BYTE *)((int)v24 - v26 + v8);
    a2[33] = *(_BYTE *)((int)v24 + v28 + v8);
    v29 = a4[3];
    v30 = a5[3];
    v31 = g_iVtoG[v30] + g_iUtoG[v29];
    v32 = g_iVtoR[v30];
    v33 = g_iUtoB[v29];
    LODWORD(v29) = g_iYscale[a3[12]];
    a2[38] = *(_BYTE *)((int)v29 + v32 + v8);
    a2[37] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[36] = *(_BYTE *)((int)v29 + v33 + v8);
    LODWORD(v29) = g_iYscale[a3[13]];
    a2[41] = *(_BYTE *)((int)v29 + v32 + v8);
    a4 += a7;
    a5 += a7;
    a2[40] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[39] = *(_BYTE *)((int)v29 + v33 + v8);
    LODWORD(v29) = g_iYscale[a3[14]];
    a2[44] = *(_BYTE *)((int)v29 + v32 + v8);
    a2[43] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[42] = *(_BYTE *)((int)v29 + v33 + v8);
    v34 = a3[15];
    a3 += a6;
    LODWORD(v29) = g_iYscale[v34];
    a2[47] = *(_BYTE *)(v32 + (int)v29 + v8);
    a2[46] = *(_BYTE *)((int)v29 - v31 + v8);
    a2[45] = *(_BYTE *)(v33 + (int)v29 + v8);
    a2 += a8;
    --v13;
  }
  while ( v13 );
}

```

## disassembly

```asm
0x18003aee0  push    rbx
0x18003aee2  push    rbp
0x18003aee3  push    rsi
0x18003aee4  push    rdi
0x18003aee5  push    r12
0x18003aee7  push    r13
0x18003aee9  push    r14
0x18003aeeb  push    r15
0x18003aeed  mov     rbx, cs:g_rgiClapTabDec
0x18003aef4  mov     rsi, r9
0x18003aef7  movsxd  r12, [rsp+40h+arg_28]
0x18003aefc  lea     r9, __ImageBase
0x18003af03  movsxd  r14, [rsp+40h+arg_30]
0x18003af08  mov     rdi, r8
0x18003af0b  movsxd  r13, [rsp+40h+arg_38]
0x18003af13  mov     r11, rdx
0x18003af16  mov     rbp, [rsp+40h+arg_20]
0x18003af1b  mov     r15d, 10h
0x18003af21  movzx   edx, byte ptr [rsi]
0x18003af24  movzx   eax, byte ptr [rbp+0]
0x18003af28  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003af30  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003af38  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003af40  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003af48  lea     rdx, __ImageBase
0x18003af4f  movzx   eax, byte ptr [rdi]
0x18003af52  mov     edx, rva g_iYscale[rdx+rax*4]
0x18003af59  lea     eax, [rdx+r10]
0x18003af5d  movsxd  rcx, eax
0x18003af60  mov     al, [rcx+rbx]
0x18003af63  mov     [r11+2], al
0x18003af67  mov     eax, edx
0x18003af69  sub     eax, r8d
0x18003af6c  cdqe
0x18003af6e  mov     cl, [rax+rbx]
0x18003af71  lea     eax, [rdx+r9]
0x18003af75  mov     [r11+1], cl
0x18003af79  movsxd  rcx, eax
0x18003af7c  mov     al, [rcx+rbx]
0x18003af7f  lea     rcx, __ImageBase
0x18003af86  mov     [r11], al
0x18003af89  movzx   eax, byte ptr [rdi+1]
0x18003af8d  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003af94  lea     eax, [rdx+r10]
0x18003af98  movsxd  rcx, eax
0x18003af9b  mov     al, [rcx+rbx]
0x18003af9e  mov     [r11+5], al
0x18003afa2  mov     eax, edx
0x18003afa4  sub     eax, r8d
0x18003afa7  cdqe
0x18003afa9  mov     cl, [rax+rbx]
0x18003afac  lea     eax, [rdx+r9]
0x18003afb0  mov     [r11+4], cl
0x18003afb4  movsxd  rcx, eax
0x18003afb7  mov     al, [rcx+rbx]
0x18003afba  lea     rcx, __ImageBase
0x18003afc1  mov     [r11+3], al
0x18003afc5  movzx   eax, byte ptr [rdi+2]
0x18003afc9  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003afd0  lea     eax, [rdx+r10]
0x18003afd4  movsxd  rcx, eax
0x18003afd7  mov     al, [rcx+rbx]
0x18003afda  mov     [r11+8], al
0x18003afde  mov     eax, edx
0x18003afe0  sub     eax, r8d
0x18003afe3  cdqe
0x18003afe5  mov     cl, [rax+rbx]
0x18003afe8  lea     eax, [rdx+r9]
0x18003afec  mov     [r11+7], cl
0x18003aff0  movsxd  rcx, eax
0x18003aff3  mov     al, [rcx+rbx]
0x18003aff6  lea     rcx, __ImageBase
0x18003affd  mov     [r11+6], al
0x18003b001  movzx   eax, byte ptr [rdi+3]
0x18003b005  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b00c  lea     eax, [rdx+r10]
0x18003b010  movsxd  rcx, eax
0x18003b013  mov     al, [rcx+rbx]
0x18003b016  mov     [r11+0Bh], al
0x18003b01a  mov     eax, edx
0x18003b01c  sub     eax, r8d
0x18003b01f  cdqe
0x18003b021  mov     cl, [rax+rbx]
0x18003b024  lea     eax, [rdx+r9]
0x18003b028  mov     [r11+0Ah], cl
0x18003b02c  lea     r9, __ImageBase
0x18003b033  movsxd  rcx, eax
0x18003b036  mov     al, [rcx+rbx]
0x18003b039  lea     rcx, __ImageBase
0x18003b040  mov     [r11+9], al
0x18003b044  movzx   edx, byte ptr [rsi+1]
0x18003b048  movzx   eax, byte ptr [rbp+1]
0x18003b04c  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b054  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b05c  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b064  movzx   eax, byte ptr [rdi+4]
0x18003b068  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b070  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b077  lea     eax, [rdx+r10]
0x18003b07b  movsxd  rcx, eax
0x18003b07e  mov     al, [rcx+rbx]
0x18003b081  mov     [r11+0Eh], al
0x18003b085  mov     eax, edx
0x18003b087  sub     eax, r8d
0x18003b08a  cdqe
0x18003b08c  mov     cl, [rax+rbx]
0x18003b08f  lea     eax, [rdx+r9]
0x18003b093  mov     [r11+0Dh], cl
0x18003b097  movsxd  rcx, eax
0x18003b09a  mov     al, [rcx+rbx]
0x18003b09d  lea     rcx, __ImageBase
0x18003b0a4  mov     [r11+0Ch], al
0x18003b0a8  movzx   eax, byte ptr [rdi+5]
0x18003b0ac  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b0b3  lea     eax, [rdx+r10]
0x18003b0b7  movsxd  rcx, eax
0x18003b0ba  mov     al, [rcx+rbx]
0x18003b0bd  mov     [r11+11h], al
0x18003b0c1  mov     eax, edx
0x18003b0c3  sub     eax, r8d
0x18003b0c6  cdqe
0x18003b0c8  mov     cl, [rax+rbx]
0x18003b0cb  lea     eax, [rdx+r9]
0x18003b0cf  mov     [r11+10h], cl
0x18003b0d3  movsxd  rcx, eax
0x18003b0d6  mov     al, [rcx+rbx]
0x18003b0d9  lea     rcx, __ImageBase
0x18003b0e0  mov     [r11+0Fh], al
0x18003b0e4  movzx   eax, byte ptr [rdi+6]
0x18003b0e8  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b0ef  lea     eax, [rdx+r10]
0x18003b0f3  movsxd  rcx, eax
0x18003b0f6  mov     al, [rcx+rbx]
0x18003b0f9  mov     [r11+14h], al
0x18003b0fd  mov     eax, edx
0x18003b0ff  sub     eax, r8d
0x18003b102  cdqe
0x18003b104  mov     cl, [rax+rbx]
0x18003b107  lea     eax, [rdx+r9]
0x18003b10b  mov     [r11+13h], cl
0x18003b10f  movsxd  rcx, eax
0x18003b112  mov     al, [rcx+rbx]
0x18003b115  lea     rcx, __ImageBase
0x18003b11c  mov     [r11+12h], al
0x18003b120  movzx   eax, byte ptr [rdi+7]
0x18003b124  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b12b  lea     eax, [rdx+r10]
0x18003b12f  movsxd  rcx, eax
0x18003b132  mov     al, [rcx+rbx]
0x18003b135  mov     [r11+17h], al
0x18003b139  mov     eax, edx
0x18003b13b  sub     eax, r8d
0x18003b13e  cdqe
0x18003b140  mov     cl, [rax+rbx]
0x18003b143  lea     eax, [rdx+r9]
0x18003b147  mov     [r11+16h], cl
0x18003b14b  lea     r9, __ImageBase
0x18003b152  movsxd  rcx, eax
0x18003b155  mov     al, [rcx+rbx]
0x18003b158  lea     rcx, __ImageBase
0x18003b15f  mov     [r11+15h], al
0x18003b163  movzx   edx, byte ptr [rsi+2]
0x18003b167  movzx   eax, byte ptr [rbp+2]
0x18003b16b  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b173  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b17b  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b183  movzx   eax, byte ptr [rdi+8]
0x18003b187  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b18f  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b196  lea     eax, [rdx+r10]
0x18003b19a  movsxd  rcx, eax
0x18003b19d  mov     al, [rcx+rbx]
0x18003b1a0  mov     [r11+1Ah], al
0x18003b1a4  mov     eax, edx
0x18003b1a6  sub     eax, r8d
0x18003b1a9  cdqe
0x18003b1ab  mov     cl, [rax+rbx]
0x18003b1ae  lea     eax, [rdx+r9]
0x18003b1b2  mov     [r11+19h], cl
0x18003b1b6  movsxd  rcx, eax
0x18003b1b9  mov     al, [rcx+rbx]
0x18003b1bc  lea     rcx, __ImageBase
0x18003b1c3  mov     [r11+18h], al
0x18003b1c7  movzx   eax, byte ptr [rdi+9]
0x18003b1cb  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b1d2  lea     eax, [rdx+r10]
0x18003b1d6  movsxd  rcx, eax
0x18003b1d9  mov     al, [rcx+rbx]
0x18003b1dc  mov     [r11+1Dh], al
0x18003b1e0  mov     eax, edx
0x18003b1e2  sub     eax, r8d
0x18003b1e5  cdqe
0x18003b1e7  mov     cl, [rax+rbx]
0x18003b1ea  lea     eax, [rdx+r9]
0x18003b1ee  mov     [r11+1Ch], cl
0x18003b1f2  movsxd  rcx, eax
0x18003b1f5  mov     al, [rcx+rbx]
0x18003b1f8  lea     rcx, __ImageBase
0x18003b1ff  mov     [r11+1Bh], al
0x18003b203  movzx   eax, byte ptr [rdi+0Ah]
0x18003b207  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b20e  lea     eax, [rdx+r10]
0x18003b212  movsxd  rcx, eax
0x18003b215  mov     al, [rcx+rbx]
0x18003b218  mov     [r11+20h], al
0x18003b21c  mov     eax, edx
0x18003b21e  sub     eax, r8d
0x18003b221  cdqe
0x18003b223  mov     cl, [rax+rbx]
0x18003b226  lea     eax, [rdx+r9]
0x18003b22a  mov     [r11+1Fh], cl
0x18003b22e  movsxd  rcx, eax
0x18003b231  mov     al, [rcx+rbx]
0x18003b234  lea     rcx, __ImageBase
0x18003b23b  mov     [r11+1Eh], al
0x18003b23f  movzx   eax, byte ptr [rdi+0Bh]
0x18003b243  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b24a  lea     eax, [rdx+r10]
0x18003b24e  movsxd  rcx, eax
0x18003b251  mov     al, [rcx+rbx]
0x18003b254  mov     [r11+23h], al
0x18003b258  mov     eax, edx
0x18003b25a  sub     eax, r8d
0x18003b25d  cdqe
0x18003b25f  mov     cl, [rax+rbx]
0x18003b262  lea     eax, [rdx+r9]
0x18003b266  mov     [r11+22h], cl
0x18003b26a  lea     r9, __ImageBase
0x18003b271  movsxd  rcx, eax
0x18003b274  mov     al, [rcx+rbx]
0x18003b277  lea     rcx, __ImageBase
0x18003b27e  mov     [r11+21h], al
0x18003b282  movzx   edx, byte ptr [rsi+3]
0x18003b286  movzx   eax, byte ptr [rbp+3]
0x18003b28a  mov     r8d, rva g_iUtoG[r9+rdx*4]
0x18003b292  add     r8d, rva g_iVtoG[r9+rax*4]
0x18003b29a  mov     r10d, rva g_iVtoR[r9+rax*4]
0x18003b2a2  movzx   eax, byte ptr [rdi+0Ch]
0x18003b2a6  mov     r9d, rva g_iUtoB[r9+rdx*4]
0x18003b2ae  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b2b5  lea     eax, [rdx+r10]
0x18003b2b9  movsxd  rcx, eax
0x18003b2bc  mov     al, [rcx+rbx]
0x18003b2bf  mov     [r11+26h], al
0x18003b2c3  mov     eax, edx
0x18003b2c5  sub     eax, r8d
0x18003b2c8  cdqe
0x18003b2ca  mov     cl, [rax+rbx]
0x18003b2cd  lea     eax, [rdx+r9]
0x18003b2d1  mov     [r11+25h], cl
0x18003b2d5  movsxd  rcx, eax
0x18003b2d8  mov     al, [rcx+rbx]
0x18003b2db  lea     rcx, __ImageBase
0x18003b2e2  mov     [r11+24h], al
0x18003b2e6  movzx   eax, byte ptr [rdi+0Dh]
0x18003b2ea  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b2f1  lea     eax, [rdx+r10]
0x18003b2f5  movsxd  rcx, eax
0x18003b2f8  mov     al, [rcx+rbx]
0x18003b2fb  mov     [r11+29h], al
0x18003b2ff  mov     eax, edx
0x18003b301  sub     eax, r8d
0x18003b304  add     rsi, r14
0x18003b307  cdqe
0x18003b309  add     rbp, r14
0x18003b30c  mov     cl, [rax+rbx]
0x18003b30f  lea     eax, [rdx+r9]
0x18003b313  mov     [r11+28h], cl
0x18003b317  movsxd  rcx, eax
0x18003b31a  mov     al, [rcx+rbx]
0x18003b31d  lea     rcx, __ImageBase
0x18003b324  mov     [r11+27h], al
0x18003b328  movzx   eax, byte ptr [rdi+0Eh]
0x18003b32c  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b333  lea     eax, [rdx+r10]
0x18003b337  movsxd  rcx, eax
0x18003b33a  mov     al, [rcx+rbx]
0x18003b33d  mov     [r11+2Ch], al
0x18003b341  mov     eax, edx
0x18003b343  sub     eax, r8d
0x18003b346  cdqe
0x18003b348  mov     cl, [rax+rbx]
0x18003b34b  lea     eax, [rdx+r9]
0x18003b34f  mov     [r11+2Bh], cl
0x18003b353  movsxd  rcx, eax
0x18003b356  mov     al, [rcx+rbx]
0x18003b359  lea     rcx, __ImageBase
0x18003b360  mov     [r11+2Ah], al
0x18003b364  movzx   eax, byte ptr [rdi+0Fh]
0x18003b368  add     rdi, r12
0x18003b36b  mov     edx, rva g_iYscale[rcx+rax*4]
0x18003b372  lea     eax, [r10+rdx]
0x18003b376  movsxd  rcx, eax
0x18003b379  mov     al, [rcx+rbx]
0x18003b37c  mov     [r11+2Fh], al
0x18003b380  mov     eax, edx
0x18003b382  sub     eax, r8d
0x18003b385  cdqe
0x18003b387  mov     cl, [rax+rbx]
0x18003b38a  lea     eax, [r9+rdx]
  ... truncated ...
```
