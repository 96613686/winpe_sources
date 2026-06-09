# UpdateDstBlkRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180016e70`
- end: `0x18001744c`
- name: `?UpdateDstBlkRGB24@@YAXPEAEPEBE11JJJ@Z`
- size: `1500`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180016e70`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB24(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  unsigned __int8 *v7; // rdi
  const unsigned __int8 *v8; // r11
  const unsigned __int8 *v9; // r8
  unsigned __int8 *v10; // r10
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r13d
  int v14; // r15d
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // ebp
  int v18; // r14d
  int v19; // esi
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // r11d
  int v23; // edi
  int v24; // ebx
  unsigned __int8 *v25; // r12
  __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // r10d
  int v29; // r8d
  int v30; // r9d
  unsigned __int8 *v31; // r15
  unsigned __int8 *v32; // r12
  unsigned __int8 *v33; // rcx
  unsigned __int8 *v34; // r14
  __int64 v35; // rcx
  bool v36; // zf
  int v37; // [rsp+0h] [rbp-58h]
  int v38; // [rsp+4h] [rbp-54h]
  unsigned __int8 *v39; // [rsp+60h] [rbp+8h]
  const unsigned __int8 *v40; // [rsp+68h] [rbp+10h]
  const unsigned __int8 *v41; // [rsp+70h] [rbp+18h]
  const unsigned __int8 *v42; // [rsp+78h] [rbp+20h]

  v42 = a4;
  v41 = a3;
  v40 = a2;
  v39 = a1;
  v7 = g_rgiClapTabDec;
  v8 = a3;
  v37 = 4;
  v9 = a2;
  v10 = a1;
  do
  {
    v11 = *v8;
    v12 = *a4;
    v13 = *((_DWORD *)&g_iVtoR + v12);
    v14 = *((_DWORD *)&g_iVtoG + v12) + *((_DWORD *)&g_iUtoG + v11);
    v38 = *((_DWORD *)&g_iUtoB + v11);
    LODWORD(v11) = *((_DWORD *)&g_iYscale + *v9);
    v10[2] = v7[(int)v11 + v13];
    v10[1] = v7[(int)v11 - v14];
    *v10 = v7[(int)v11 + v38];
    LODWORD(v11) = *((_DWORD *)&g_iYscale + v9[1]);
    v10[5] = v7[(int)v11 + v13];
    v10[4] = v7[(int)v11 - v14];
    v10[3] = v7[(int)v11 + v38];
    v15 = v8[1];
    v16 = a4[1];
    v17 = *((_DWORD *)&g_iUtoB + v15);
    v18 = *((_DWORD *)&g_iVtoR + v16);
    v19 = *((_DWORD *)&g_iVtoG + v16) + *((_DWORD *)&g_iUtoG + v15);
    LODWORD(v15) = *((_DWORD *)&g_iYscale + v9[2]);
    v10[8] = v7[(int)v15 + v18];
    v10[7] = v7[(int)v15 - v19];
    v10[6] = v7[(int)v15 + v17];
    LODWORD(v15) = *((_DWORD *)&g_iYscale + v9[3]);
    v10[11] = v7[(int)v15 + v18];
    v10[10] = v7[(int)v15 - v19];
    v10[9] = v7[(int)v15 + v17];
    v20 = v8[2];
    v21 = a4[2];
    v22 = *((_DWORD *)&g_iVtoG + v21) + *((_DWORD *)&g_iUtoG + v20);
    v23 = *((_DWORD *)&g_iVtoR + v21);
    v24 = *((_DWORD *)&g_iUtoB + v20);
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v9[4]);
    v25 = g_rgiClapTabDec;
    v10[14] = g_rgiClapTabDec[(int)v20 + v23];
    v10[13] = v25[(int)v20 - v22];
    v10[12] = v25[(int)v20 + v24];
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v9[5]);
    v10[17] = v25[(int)v20 + v23];
    v10[16] = v25[(int)v20 - v22];
    v10[15] = v25[(int)v20 + v24];
    v26 = a4[3];
    v27 = v41[3];
    v28 = *((_DWORD *)&g_iVtoR + v26);
    v29 = *((_DWORD *)&g_iUtoG + v27) + *((_DWORD *)&g_iVtoG + v26);
    v30 = *((_DWORD *)&g_iUtoB + v27);
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[6]);
    v39[20] = v25[(int)v27 + v28];
    v39[19] = v25[(int)v27 - v29];
    v39[18] = v25[(int)v27 + v30];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[7]);
    v39[23] = v25[(int)v27 + v28];
    v39[22] = v25[(int)v27 - v29];
    v39[21] = v25[(int)v27 + v30];
    v41 += a6;
    v42 += a6;
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5]);
    v39[a7 + 2] = v25[(int)v27 + v13];
    v39[a7 + 1] = g_rgiClapTabDec[(int)v27 - v14];
    v39[a7] = g_rgiClapTabDec[(int)v27 + v38];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 1]);
    v39[a7 + 5] = g_rgiClapTabDec[(int)v27 + v13];
    LODWORD(v26) = v27 - v14;
    v31 = g_rgiClapTabDec;
    v39[a7 + 4] = g_rgiClapTabDec[(int)v26];
    v32 = v39;
    v39[a7 + 3] = v31[(int)v27 + v38];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 2]);
    v33 = g_rgiClapTabDec;
    v39[a7 + 8] = g_rgiClapTabDec[(int)v27 + v18];
    v39[a7 + 7] = v33[(int)v27 - v19];
    v39[a7 + 6] = g_rgiClapTabDec[(int)v27 + v17];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 3]);
    LODWORD(v26) = v27 + v18;
    v34 = g_rgiClapTabDec;
    v39[a7 + 11] = g_rgiClapTabDec[(int)v26];
    v39[a7 + 10] = v34[(int)v27 - v19];
    v39[a7 + 9] = v34[(int)v27 + v17];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 4]);
    v39[a7 + 14] = v34[(int)v27 + v23];
    v39[a7 + 13] = v34[(int)v27 - v22];
    v39[a7 + 12] = v34[(int)v27 + v24];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 5]);
    LODWORD(v26) = v27 + v23;
    v7 = v34;
    v39[a7 + 17] = v34[(int)v26];
    v39[a7 + 16] = v34[(int)v27 - v22];
    v39[a7 + 15] = v34[(int)v27 + v24];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 6]);
    v39[a7 + 20] = v34[(int)v27 + v28];
    v39[a7 + 19] = v34[(int)v27 - v29];
    v39[a7 + 18] = v34[(int)v27 + v30];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 7]);
    v35 = (int)v27 + v28;
    v10 = &v39[2 * a7];
    v39 = v10;
    v32[a7 + 23] = v34[v35];
    LODWORD(v26) = v27 - v29;
    v36 = v37-- == 1;
    v9 = &v40[2 * a5];
    v40 = v9;
    LOBYTE(v35) = v34[(int)v26];
    LODWORD(v26) = v27 + v30;
    a4 = v42;
    v32[a7 + 22] = v35;
    v32[a7 + 21] = v34[(int)v26];
    v8 = v41;
  }
  while ( !v36 );
}

```

## disassembly

```asm
0x180016e70  mov     rax, rsp
0x180016e73  mov     [rax+20h], r9
0x180016e77  mov     [rax+18h], r8
0x180016e7b  mov     [rax+10h], rdx
0x180016e7f  mov     [rax+8], rcx
0x180016e83  push    rbx
0x180016e84  push    rbp
0x180016e85  push    rsi
0x180016e86  push    rdi
0x180016e87  push    r12
0x180016e89  push    r13
0x180016e8b  push    r14
0x180016e8d  push    r15
0x180016e8f  sub     rsp, 18h
0x180016e93  mov     rdi, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016e9a  lea     rbx, __ImageBase
0x180016ea1  mov     r11, r8
0x180016ea4  mov     [rsp+58h+var_58], 4
0x180016eab  mov     r8, rdx
0x180016eae  mov     r10, rcx
0x180016eb1  movzx   edx, byte ptr [r11]
0x180016eb5  movzx   eax, byte ptr [r9]
0x180016eb9  mov     r12d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180016ec1  mov     r13d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180016ec9  mov     r15d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180016ed1  add     r15d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180016ed9  movzx   eax, byte ptr [r8]
0x180016edd  mov     [rsp+58h+var_54], r12d
0x180016ee2  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016ee9  lea     eax, [rdx+r13]
0x180016eed  movsxd  rcx, eax
0x180016ef0  mov     al, [rcx+rdi]
0x180016ef3  mov     [r10+2], al
0x180016ef7  mov     eax, edx
0x180016ef9  sub     eax, r15d
0x180016efc  cdqe
0x180016efe  mov     cl, [rax+rdi]
0x180016f01  lea     eax, [rdx+r12]
0x180016f05  mov     [r10+1], cl
0x180016f09  movsxd  rcx, eax
0x180016f0c  mov     al, [rcx+rdi]
0x180016f0f  mov     [r10], al
0x180016f12  movzx   eax, byte ptr [r8+1]
0x180016f17  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016f1e  lea     eax, [rdx+r13]
0x180016f22  movsxd  rcx, eax
0x180016f25  mov     al, [rcx+rdi]
0x180016f28  mov     [r10+5], al
0x180016f2c  mov     eax, edx
0x180016f2e  sub     eax, r15d
0x180016f31  cdqe
0x180016f33  mov     cl, [rax+rdi]
0x180016f36  lea     eax, [rdx+r12]
0x180016f3a  mov     [r10+4], cl
0x180016f3e  movsxd  rcx, eax
0x180016f41  mov     al, [rcx+rdi]
0x180016f44  mov     [r10+3], al
0x180016f48  movzx   edx, byte ptr [r11+1]
0x180016f4d  movzx   eax, byte ptr [r9+1]
0x180016f52  mov     ebp, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180016f59  mov     r14d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180016f61  mov     esi, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180016f68  add     esi, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180016f6f  movzx   eax, byte ptr [r8+2]
0x180016f74  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016f7b  lea     eax, [rdx+r14]
0x180016f7f  movsxd  rcx, eax
0x180016f82  mov     al, [rcx+rdi]
0x180016f85  mov     [r10+8], al
0x180016f89  mov     eax, edx
0x180016f8b  sub     eax, esi
0x180016f8d  cdqe
0x180016f8f  mov     cl, [rax+rdi]
0x180016f92  lea     eax, [rdx+rbp]
0x180016f95  mov     [r10+7], cl
0x180016f99  movsxd  rcx, eax
0x180016f9c  mov     al, [rcx+rdi]
0x180016f9f  mov     [r10+6], al
0x180016fa3  movzx   eax, byte ptr [r8+3]
0x180016fa8  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016faf  lea     eax, [rdx+r14]
0x180016fb3  movsxd  rcx, eax
0x180016fb6  mov     al, [rcx+rdi]
0x180016fb9  mov     [r10+0Bh], al
0x180016fbd  mov     eax, edx
0x180016fbf  sub     eax, esi
0x180016fc1  cdqe
0x180016fc3  mov     cl, [rax+rdi]
0x180016fc6  lea     eax, [rdx+rbp]
0x180016fc9  mov     [r10+0Ah], cl
0x180016fcd  movsxd  rcx, eax
0x180016fd0  mov     al, [rcx+rdi]
0x180016fd3  mov     [r10+9], al
0x180016fd7  movzx   edx, byte ptr [r11+2]
0x180016fdc  movzx   eax, byte ptr [r9+2]
0x180016fe1  mov     r11d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180016fe9  add     r11d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180016ff1  mov     edi, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180016ff8  mov     ebx, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180016fff  lea     rdx, __ImageBase
0x180017006  movzx   eax, byte ptr [r8+4]
0x18001700b  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017012  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017019  lea     eax, [rdx+rdi]
0x18001701c  movsxd  rcx, eax
0x18001701f  mov     al, [rcx+r12]
0x180017023  mov     [r10+0Eh], al
0x180017027  mov     eax, edx
0x180017029  sub     eax, r11d
0x18001702c  cdqe
0x18001702e  mov     cl, [rax+r12]
0x180017032  lea     eax, [rdx+rbx]
0x180017035  mov     [r10+0Dh], cl
0x180017039  movsxd  rcx, eax
0x18001703c  mov     al, [rcx+r12]
0x180017040  mov     [r10+0Ch], al
0x180017044  movzx   eax, byte ptr [r8+5]
0x180017049  lea     r8, __ImageBase
0x180017050  mov     edx, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017058  lea     eax, [rdx+rdi]
0x18001705b  movsxd  rcx, eax
0x18001705e  mov     al, [rcx+r12]
0x180017062  mov     [r10+11h], al
0x180017066  mov     eax, edx
0x180017068  sub     eax, r11d
0x18001706b  cdqe
0x18001706d  mov     cl, [rax+r12]
0x180017071  lea     eax, [rdx+rbx]
0x180017074  mov     [r10+10h], cl
0x180017078  movsxd  rcx, eax
0x18001707b  mov     al, [rcx+r12]
0x18001707f  mov     rcx, [rsp+58h+arg_10]
0x180017084  mov     [r10+0Fh], al
0x180017088  movzx   eax, byte ptr [r9+3]
0x18001708d  movzx   edx, byte ptr [rcx+3]
0x180017091  mov     r10d, rva ?g_iVtoR@@3PAJA[r8+rax*4]; long near * g_iVtoR ...
0x180017099  mov     ecx, rva ?g_iUtoG@@3PAJA[r8+rdx*4]; long near * g_iUtoG ...
0x1800170a1  mov     r8d, rva ?g_iVtoG@@3PAJA[r8+rax*4]; long near * g_iVtoG ...
0x1800170a9  mov     rax, [rsp+58h+arg_8]
0x1800170ae  add     r8d, ecx
0x1800170b1  lea     rcx, __ImageBase
0x1800170b8  mov     r9d, rva ?g_iUtoB@@3PAJA[rcx+rdx*4]; long near * g_iUtoB ...
0x1800170c0  movzx   eax, byte ptr [rax+6]
0x1800170c4  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800170cb  lea     eax, [rdx+r10]
0x1800170cf  movsxd  rcx, eax
0x1800170d2  mov     al, [rcx+r12]
0x1800170d6  mov     rcx, [rsp+58h+arg_0]
0x1800170db  mov     [rcx+14h], al
0x1800170de  mov     eax, edx
0x1800170e0  sub     eax, r8d
0x1800170e3  cdqe
0x1800170e5  mov     cl, [rax+r12]
0x1800170e9  mov     rax, [rsp+58h+arg_0]
0x1800170ee  mov     [rax+13h], cl
0x1800170f1  lea     eax, [rdx+r9]
0x1800170f5  movsxd  rcx, eax
0x1800170f8  lea     rdx, __ImageBase
0x1800170ff  mov     al, [rcx+r12]
0x180017103  mov     rcx, [rsp+58h+arg_0]
0x180017108  mov     [rcx+12h], al
0x18001710b  mov     rax, [rsp+58h+arg_8]
0x180017110  movzx   eax, byte ptr [rax+7]
0x180017114  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001711b  lea     eax, [rdx+r10]
0x18001711f  movsxd  rcx, eax
0x180017122  mov     al, [rcx+r12]
0x180017126  mov     rcx, [rsp+58h+arg_0]
0x18001712b  mov     [rcx+17h], al
0x18001712e  mov     eax, edx
0x180017130  sub     eax, r8d
0x180017133  cdqe
0x180017135  mov     cl, [rax+r12]
0x180017139  mov     rax, [rsp+58h+arg_0]
0x18001713e  mov     [rax+16h], cl
0x180017141  lea     eax, [rdx+r9]
0x180017145  movsxd  rcx, eax
0x180017148  mov     al, [rcx+r12]
0x18001714c  mov     rcx, [rsp+58h+arg_0]
0x180017151  mov     [rcx+15h], al
0x180017154  movsxd  rax, [rsp+58h+arg_28]
0x18001715c  add     [rsp+58h+arg_10], rax
0x180017161  add     [rsp+58h+arg_18], rax
0x180017166  mov     rcx, [rsp+58h+arg_8]
0x18001716b  movsxd  rax, [rsp+58h+arg_20]
0x180017173  movzx   eax, byte ptr [rax+rcx]
0x180017177  lea     rcx, __ImageBase
0x18001717e  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017185  lea     eax, [rdx+r13]
0x180017189  movsxd  rcx, eax
0x18001718c  mov     al, [rcx+r12]
0x180017190  mov     r12, [rsp+58h+arg_0]
0x180017195  movsxd  rcx, [rsp+58h+arg_30]
0x18001719d  mov     [rcx+r12+2], al
0x1800171a2  mov     eax, edx
0x1800171a4  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800171ab  sub     eax, r15d
0x1800171ae  cdqe
0x1800171b0  mov     cl, [rax+rcx]
0x1800171b3  movsxd  rax, [rsp+58h+arg_30]
0x1800171bb  mov     [rax+r12+1], cl
0x1800171c0  mov     r12d, [rsp+58h+var_54]
0x1800171c5  lea     eax, [rdx+r12]
0x1800171c9  mov     rdx, [rsp+58h+arg_0]
0x1800171ce  movsxd  rcx, eax
0x1800171d1  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800171d8  mov     al, [rcx+rax]
0x1800171db  movsxd  rcx, [rsp+58h+arg_30]
0x1800171e3  mov     [rcx+rdx], al
0x1800171e6  mov     rcx, [rsp+58h+arg_8]
0x1800171eb  movsxd  rax, [rsp+58h+arg_20]
0x1800171f3  movzx   eax, byte ptr [rax+rcx+1]
0x1800171f8  lea     rcx, __ImageBase
0x1800171ff  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017206  lea     eax, [rdx+r13]
0x18001720a  movsxd  r13, [rsp+58h+arg_30]
0x180017212  movsxd  rcx, eax
0x180017215  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001721c  mov     al, [rcx+rax]
0x18001721f  mov     rcx, [rsp+58h+arg_0]
0x180017224  mov     [rcx+r13+5], al
0x180017229  mov     eax, edx
0x18001722b  sub     eax, r15d
0x18001722e  mov     r15, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017235  cdqe
0x180017237  mov     cl, [rax+r15]
0x18001723b  mov     rax, [rsp+58h+arg_0]
0x180017240  mov     [rax+r13+4], cl
0x180017245  lea     eax, [rdx+r12]
0x180017249  mov     r12, [rsp+58h+arg_0]
0x18001724e  movsxd  rcx, eax
0x180017251  mov     al, [rcx+r15]
0x180017255  lea     rcx, __ImageBase
0x18001725c  movsxd  r15, [rsp+58h+arg_20]
0x180017264  mov     [r12+r13+3], al
0x180017269  mov     rax, [rsp+58h+arg_8]
0x18001726e  movzx   eax, byte ptr [r15+rax+2]
0x180017274  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001727b  lea     eax, [rdx+r14]
0x18001727f  movsxd  rcx, eax
0x180017282  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017289  mov     al, [rcx+rax]
0x18001728c  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017293  mov     [r12+r13+8], al
0x180017298  mov     eax, edx
0x18001729a  sub     eax, esi
0x18001729c  cdqe
0x18001729e  mov     cl, [rax+rcx]
0x1800172a1  lea     eax, [rdx+rbp]
0x1800172a4  mov     [r12+r13+7], cl
0x1800172a9  movsxd  rcx, eax
0x1800172ac  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800172b3  mov     al, [rcx+rax]
0x1800172b6  lea     rcx, __ImageBase
0x1800172bd  mov     [r12+r13+6], al
0x1800172c2  mov     rax, [rsp+58h+arg_8]
0x1800172c7  movzx   eax, byte ptr [r15+rax+3]
0x1800172cd  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800172d4  lea     eax, [rdx+r14]
0x1800172d8  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800172df  movsxd  rcx, eax
0x1800172e2  mov     al, [rcx+r14]
0x1800172e6  mov     [r12+r13+0Bh], al
0x1800172eb  mov     eax, edx
0x1800172ed  sub     eax, esi
0x1800172ef  mov     rsi, [rsp+58h+arg_8]
0x1800172f4  cdqe
0x1800172f6  mov     cl, [rax+r14]
0x1800172fa  lea     eax, [rdx+rbp]
0x1800172fd  mov     [r12+r13+0Ah], cl
0x180017302  lea     rbp, __ImageBase
0x180017309  movsxd  rcx, eax
0x18001730c  mov     al, [rcx+r14]
0x180017310  mov     [r12+r13+9], al
0x180017315  movzx   eax, byte ptr [r15+rsi+4]
0x18001731b  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x180017322  lea     eax, [rdx+rdi]
0x180017325  movsxd  rcx, eax
0x180017328  mov     al, [rcx+r14]
0x18001732c  mov     [r12+r13+0Eh], al
0x180017331  mov     eax, edx
0x180017333  sub     eax, r11d
0x180017336  cdqe
0x180017338  mov     cl, [rax+r14]
0x18001733c  lea     eax, [rdx+rbx]
0x18001733f  mov     [r12+r13+0Dh], cl
0x180017344  movsxd  rcx, eax
0x180017347  mov     al, [rcx+r14]
0x18001734b  mov     [r12+r13+0Ch], al
0x180017350  movzx   eax, byte ptr [r15+rsi+5]
0x180017356  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001735d  lea     eax, [rdx+rdi]
0x180017360  mov     rdi, r14
0x180017363  movsxd  rcx, eax
0x180017366  mov     al, [rcx+r14]
0x18001736a  mov     [r12+r13+11h], al
0x18001736f  mov     eax, edx
0x180017371  sub     eax, r11d
0x180017374  cdqe
0x180017376  mov     cl, [rax+r14]
  ... truncated ...
```
