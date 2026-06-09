# UpdateDstBlkRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180016db0`
- end: `0x18001738c`
- name: `?UpdateDstBlkRGB24@@YAXPEAEPEBE11JJJ@Z`
- size: `1500`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180016db0`

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
0x180016db0  mov     rax, rsp
0x180016db3  mov     [rax+20h], r9
0x180016db7  mov     [rax+18h], r8
0x180016dbb  mov     [rax+10h], rdx
0x180016dbf  mov     [rax+8], rcx
0x180016dc3  push    rbx
0x180016dc4  push    rbp
0x180016dc5  push    rsi
0x180016dc6  push    rdi
0x180016dc7  push    r12
0x180016dc9  push    r13
0x180016dcb  push    r14
0x180016dcd  push    r15
0x180016dcf  sub     rsp, 18h
0x180016dd3  mov     rdi, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016dda  lea     rbx, __ImageBase
0x180016de1  mov     r11, r8
0x180016de4  mov     [rsp+58h+var_58], 4
0x180016deb  mov     r8, rdx
0x180016dee  mov     r10, rcx
0x180016df1  movzx   edx, byte ptr [r11]
0x180016df5  movzx   eax, byte ptr [r9]
0x180016df9  mov     r12d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180016e01  mov     r13d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180016e09  mov     r15d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180016e11  add     r15d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180016e19  movzx   eax, byte ptr [r8]
0x180016e1d  mov     [rsp+58h+var_54], r12d
0x180016e22  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016e29  lea     eax, [rdx+r13]
0x180016e2d  movsxd  rcx, eax
0x180016e30  mov     al, [rcx+rdi]
0x180016e33  mov     [r10+2], al
0x180016e37  mov     eax, edx
0x180016e39  sub     eax, r15d
0x180016e3c  cdqe
0x180016e3e  mov     cl, [rax+rdi]
0x180016e41  lea     eax, [rdx+r12]
0x180016e45  mov     [r10+1], cl
0x180016e49  movsxd  rcx, eax
0x180016e4c  mov     al, [rcx+rdi]
0x180016e4f  mov     [r10], al
0x180016e52  movzx   eax, byte ptr [r8+1]
0x180016e57  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016e5e  lea     eax, [rdx+r13]
0x180016e62  movsxd  rcx, eax
0x180016e65  mov     al, [rcx+rdi]
0x180016e68  mov     [r10+5], al
0x180016e6c  mov     eax, edx
0x180016e6e  sub     eax, r15d
0x180016e71  cdqe
0x180016e73  mov     cl, [rax+rdi]
0x180016e76  lea     eax, [rdx+r12]
0x180016e7a  mov     [r10+4], cl
0x180016e7e  movsxd  rcx, eax
0x180016e81  mov     al, [rcx+rdi]
0x180016e84  mov     [r10+3], al
0x180016e88  movzx   edx, byte ptr [r11+1]
0x180016e8d  movzx   eax, byte ptr [r9+1]
0x180016e92  mov     ebp, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180016e99  mov     r14d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180016ea1  mov     esi, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180016ea8  add     esi, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180016eaf  movzx   eax, byte ptr [r8+2]
0x180016eb4  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016ebb  lea     eax, [rdx+r14]
0x180016ebf  movsxd  rcx, eax
0x180016ec2  mov     al, [rcx+rdi]
0x180016ec5  mov     [r10+8], al
0x180016ec9  mov     eax, edx
0x180016ecb  sub     eax, esi
0x180016ecd  cdqe
0x180016ecf  mov     cl, [rax+rdi]
0x180016ed2  lea     eax, [rdx+rbp]
0x180016ed5  mov     [r10+7], cl
0x180016ed9  movsxd  rcx, eax
0x180016edc  mov     al, [rcx+rdi]
0x180016edf  mov     [r10+6], al
0x180016ee3  movzx   eax, byte ptr [r8+3]
0x180016ee8  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180016eef  lea     eax, [rdx+r14]
0x180016ef3  movsxd  rcx, eax
0x180016ef6  mov     al, [rcx+rdi]
0x180016ef9  mov     [r10+0Bh], al
0x180016efd  mov     eax, edx
0x180016eff  sub     eax, esi
0x180016f01  cdqe
0x180016f03  mov     cl, [rax+rdi]
0x180016f06  lea     eax, [rdx+rbp]
0x180016f09  mov     [r10+0Ah], cl
0x180016f0d  movsxd  rcx, eax
0x180016f10  mov     al, [rcx+rdi]
0x180016f13  mov     [r10+9], al
0x180016f17  movzx   edx, byte ptr [r11+2]
0x180016f1c  movzx   eax, byte ptr [r9+2]
0x180016f21  mov     r11d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180016f29  add     r11d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180016f31  mov     edi, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180016f38  mov     ebx, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180016f3f  lea     rdx, __ImageBase
0x180016f46  movzx   eax, byte ptr [r8+4]
0x180016f4b  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180016f52  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180016f59  lea     eax, [rdx+rdi]
0x180016f5c  movsxd  rcx, eax
0x180016f5f  mov     al, [rcx+r12]
0x180016f63  mov     [r10+0Eh], al
0x180016f67  mov     eax, edx
0x180016f69  sub     eax, r11d
0x180016f6c  cdqe
0x180016f6e  mov     cl, [rax+r12]
0x180016f72  lea     eax, [rdx+rbx]
0x180016f75  mov     [r10+0Dh], cl
0x180016f79  movsxd  rcx, eax
0x180016f7c  mov     al, [rcx+r12]
0x180016f80  mov     [r10+0Ch], al
0x180016f84  movzx   eax, byte ptr [r8+5]
0x180016f89  lea     r8, __ImageBase
0x180016f90  mov     edx, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180016f98  lea     eax, [rdx+rdi]
0x180016f9b  movsxd  rcx, eax
0x180016f9e  mov     al, [rcx+r12]
0x180016fa2  mov     [r10+11h], al
0x180016fa6  mov     eax, edx
0x180016fa8  sub     eax, r11d
0x180016fab  cdqe
0x180016fad  mov     cl, [rax+r12]
0x180016fb1  lea     eax, [rdx+rbx]
0x180016fb4  mov     [r10+10h], cl
0x180016fb8  movsxd  rcx, eax
0x180016fbb  mov     al, [rcx+r12]
0x180016fbf  mov     rcx, [rsp+58h+arg_10]
0x180016fc4  mov     [r10+0Fh], al
0x180016fc8  movzx   eax, byte ptr [r9+3]
0x180016fcd  movzx   edx, byte ptr [rcx+3]
0x180016fd1  mov     r10d, rva ?g_iVtoR@@3PAJA[r8+rax*4]; long near * g_iVtoR ...
0x180016fd9  mov     ecx, rva ?g_iUtoG@@3PAJA[r8+rdx*4]; long near * g_iUtoG ...
0x180016fe1  mov     r8d, rva ?g_iVtoG@@3PAJA[r8+rax*4]; long near * g_iVtoG ...
0x180016fe9  mov     rax, [rsp+58h+arg_8]
0x180016fee  add     r8d, ecx
0x180016ff1  lea     rcx, __ImageBase
0x180016ff8  mov     r9d, rva ?g_iUtoB@@3PAJA[rcx+rdx*4]; long near * g_iUtoB ...
0x180017000  movzx   eax, byte ptr [rax+6]
0x180017004  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001700b  lea     eax, [rdx+r10]
0x18001700f  movsxd  rcx, eax
0x180017012  mov     al, [rcx+r12]
0x180017016  mov     rcx, [rsp+58h+arg_0]
0x18001701b  mov     [rcx+14h], al
0x18001701e  mov     eax, edx
0x180017020  sub     eax, r8d
0x180017023  cdqe
0x180017025  mov     cl, [rax+r12]
0x180017029  mov     rax, [rsp+58h+arg_0]
0x18001702e  mov     [rax+13h], cl
0x180017031  lea     eax, [rdx+r9]
0x180017035  movsxd  rcx, eax
0x180017038  lea     rdx, __ImageBase
0x18001703f  mov     al, [rcx+r12]
0x180017043  mov     rcx, [rsp+58h+arg_0]
0x180017048  mov     [rcx+12h], al
0x18001704b  mov     rax, [rsp+58h+arg_8]
0x180017050  movzx   eax, byte ptr [rax+7]
0x180017054  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001705b  lea     eax, [rdx+r10]
0x18001705f  movsxd  rcx, eax
0x180017062  mov     al, [rcx+r12]
0x180017066  mov     rcx, [rsp+58h+arg_0]
0x18001706b  mov     [rcx+17h], al
0x18001706e  mov     eax, edx
0x180017070  sub     eax, r8d
0x180017073  cdqe
0x180017075  mov     cl, [rax+r12]
0x180017079  mov     rax, [rsp+58h+arg_0]
0x18001707e  mov     [rax+16h], cl
0x180017081  lea     eax, [rdx+r9]
0x180017085  movsxd  rcx, eax
0x180017088  mov     al, [rcx+r12]
0x18001708c  mov     rcx, [rsp+58h+arg_0]
0x180017091  mov     [rcx+15h], al
0x180017094  movsxd  rax, [rsp+58h+arg_28]
0x18001709c  add     [rsp+58h+arg_10], rax
0x1800170a1  add     [rsp+58h+arg_18], rax
0x1800170a6  mov     rcx, [rsp+58h+arg_8]
0x1800170ab  movsxd  rax, [rsp+58h+arg_20]
0x1800170b3  movzx   eax, byte ptr [rax+rcx]
0x1800170b7  lea     rcx, __ImageBase
0x1800170be  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800170c5  lea     eax, [rdx+r13]
0x1800170c9  movsxd  rcx, eax
0x1800170cc  mov     al, [rcx+r12]
0x1800170d0  mov     r12, [rsp+58h+arg_0]
0x1800170d5  movsxd  rcx, [rsp+58h+arg_30]
0x1800170dd  mov     [rcx+r12+2], al
0x1800170e2  mov     eax, edx
0x1800170e4  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800170eb  sub     eax, r15d
0x1800170ee  cdqe
0x1800170f0  mov     cl, [rax+rcx]
0x1800170f3  movsxd  rax, [rsp+58h+arg_30]
0x1800170fb  mov     [rax+r12+1], cl
0x180017100  mov     r12d, [rsp+58h+var_54]
0x180017105  lea     eax, [rdx+r12]
0x180017109  mov     rdx, [rsp+58h+arg_0]
0x18001710e  movsxd  rcx, eax
0x180017111  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017118  mov     al, [rcx+rax]
0x18001711b  movsxd  rcx, [rsp+58h+arg_30]
0x180017123  mov     [rcx+rdx], al
0x180017126  mov     rcx, [rsp+58h+arg_8]
0x18001712b  movsxd  rax, [rsp+58h+arg_20]
0x180017133  movzx   eax, byte ptr [rax+rcx+1]
0x180017138  lea     rcx, __ImageBase
0x18001713f  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017146  lea     eax, [rdx+r13]
0x18001714a  movsxd  r13, [rsp+58h+arg_30]
0x180017152  movsxd  rcx, eax
0x180017155  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001715c  mov     al, [rcx+rax]
0x18001715f  mov     rcx, [rsp+58h+arg_0]
0x180017164  mov     [rcx+r13+5], al
0x180017169  mov     eax, edx
0x18001716b  sub     eax, r15d
0x18001716e  mov     r15, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017175  cdqe
0x180017177  mov     cl, [rax+r15]
0x18001717b  mov     rax, [rsp+58h+arg_0]
0x180017180  mov     [rax+r13+4], cl
0x180017185  lea     eax, [rdx+r12]
0x180017189  mov     r12, [rsp+58h+arg_0]
0x18001718e  movsxd  rcx, eax
0x180017191  mov     al, [rcx+r15]
0x180017195  lea     rcx, __ImageBase
0x18001719c  movsxd  r15, [rsp+58h+arg_20]
0x1800171a4  mov     [r12+r13+3], al
0x1800171a9  mov     rax, [rsp+58h+arg_8]
0x1800171ae  movzx   eax, byte ptr [r15+rax+2]
0x1800171b4  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800171bb  lea     eax, [rdx+r14]
0x1800171bf  movsxd  rcx, eax
0x1800171c2  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800171c9  mov     al, [rcx+rax]
0x1800171cc  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800171d3  mov     [r12+r13+8], al
0x1800171d8  mov     eax, edx
0x1800171da  sub     eax, esi
0x1800171dc  cdqe
0x1800171de  mov     cl, [rax+rcx]
0x1800171e1  lea     eax, [rdx+rbp]
0x1800171e4  mov     [r12+r13+7], cl
0x1800171e9  movsxd  rcx, eax
0x1800171ec  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800171f3  mov     al, [rcx+rax]
0x1800171f6  lea     rcx, __ImageBase
0x1800171fd  mov     [r12+r13+6], al
0x180017202  mov     rax, [rsp+58h+arg_8]
0x180017207  movzx   eax, byte ptr [r15+rax+3]
0x18001720d  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017214  lea     eax, [rdx+r14]
0x180017218  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001721f  movsxd  rcx, eax
0x180017222  mov     al, [rcx+r14]
0x180017226  mov     [r12+r13+0Bh], al
0x18001722b  mov     eax, edx
0x18001722d  sub     eax, esi
0x18001722f  mov     rsi, [rsp+58h+arg_8]
0x180017234  cdqe
0x180017236  mov     cl, [rax+r14]
0x18001723a  lea     eax, [rdx+rbp]
0x18001723d  mov     [r12+r13+0Ah], cl
0x180017242  lea     rbp, __ImageBase
0x180017249  movsxd  rcx, eax
0x18001724c  mov     al, [rcx+r14]
0x180017250  mov     [r12+r13+9], al
0x180017255  movzx   eax, byte ptr [r15+rsi+4]
0x18001725b  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x180017262  lea     eax, [rdx+rdi]
0x180017265  movsxd  rcx, eax
0x180017268  mov     al, [rcx+r14]
0x18001726c  mov     [r12+r13+0Eh], al
0x180017271  mov     eax, edx
0x180017273  sub     eax, r11d
0x180017276  cdqe
0x180017278  mov     cl, [rax+r14]
0x18001727c  lea     eax, [rdx+rbx]
0x18001727f  mov     [r12+r13+0Dh], cl
0x180017284  movsxd  rcx, eax
0x180017287  mov     al, [rcx+r14]
0x18001728b  mov     [r12+r13+0Ch], al
0x180017290  movzx   eax, byte ptr [r15+rsi+5]
0x180017296  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001729d  lea     eax, [rdx+rdi]
0x1800172a0  mov     rdi, r14
0x1800172a3  movsxd  rcx, eax
0x1800172a6  mov     al, [rcx+r14]
0x1800172aa  mov     [r12+r13+11h], al
0x1800172af  mov     eax, edx
0x1800172b1  sub     eax, r11d
0x1800172b4  cdqe
0x1800172b6  mov     cl, [rax+r14]
  ... truncated ...
```
