# UpdateDstBlkRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x1800173a0`
- end: `0x18001797c`
- name: `?UpdateDstBlkRGB32@@YAXPEAEPEBE11JJJ@Z`
- size: `1500`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800173a0`

## pseudocode

```c
void __fastcall UpdateDstBlkRGB32(
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
    v10[6] = v7[(int)v11 + v13];
    v10[5] = v7[(int)v11 - v14];
    v10[4] = v7[(int)v11 + v38];
    v15 = v8[1];
    v16 = a4[1];
    v17 = *((_DWORD *)&g_iUtoB + v15);
    v18 = *((_DWORD *)&g_iVtoR + v16);
    v19 = *((_DWORD *)&g_iVtoG + v16) + *((_DWORD *)&g_iUtoG + v15);
    LODWORD(v15) = *((_DWORD *)&g_iYscale + v9[2]);
    v10[10] = v7[(int)v15 + v18];
    v10[9] = v7[(int)v15 - v19];
    v10[8] = v7[(int)v15 + v17];
    LODWORD(v15) = *((_DWORD *)&g_iYscale + v9[3]);
    v10[14] = v7[(int)v15 + v18];
    v10[13] = v7[(int)v15 - v19];
    v10[12] = v7[(int)v15 + v17];
    v20 = v8[2];
    v21 = a4[2];
    v22 = *((_DWORD *)&g_iVtoG + v21) + *((_DWORD *)&g_iUtoG + v20);
    v23 = *((_DWORD *)&g_iVtoR + v21);
    v24 = *((_DWORD *)&g_iUtoB + v20);
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v9[4]);
    v25 = g_rgiClapTabDec;
    v10[18] = g_rgiClapTabDec[(int)v20 + v23];
    v10[17] = v25[(int)v20 - v22];
    v10[16] = v25[(int)v20 + v24];
    LODWORD(v20) = *((_DWORD *)&g_iYscale + v9[5]);
    v10[22] = v25[(int)v20 + v23];
    v10[21] = v25[(int)v20 - v22];
    v10[20] = v25[(int)v20 + v24];
    v26 = a4[3];
    v27 = v41[3];
    v28 = *((_DWORD *)&g_iVtoR + v26);
    v29 = *((_DWORD *)&g_iUtoG + v27) + *((_DWORD *)&g_iVtoG + v26);
    v30 = *((_DWORD *)&g_iUtoB + v27);
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[6]);
    v39[26] = v25[(int)v27 + v28];
    v39[25] = v25[(int)v27 - v29];
    v39[24] = v25[(int)v27 + v30];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[7]);
    v39[30] = v25[(int)v27 + v28];
    v39[29] = v25[(int)v27 - v29];
    v39[28] = v25[(int)v27 + v30];
    v41 += a6;
    v42 += a6;
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5]);
    v39[a7 + 2] = v25[(int)v27 + v13];
    v39[a7 + 1] = g_rgiClapTabDec[(int)v27 - v14];
    v39[a7] = g_rgiClapTabDec[(int)v27 + v38];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 1]);
    v39[a7 + 6] = g_rgiClapTabDec[(int)v27 + v13];
    LODWORD(v26) = v27 - v14;
    v31 = g_rgiClapTabDec;
    v39[a7 + 5] = g_rgiClapTabDec[(int)v26];
    v32 = v39;
    v39[a7 + 4] = v31[(int)v27 + v38];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 2]);
    v33 = g_rgiClapTabDec;
    v39[a7 + 10] = g_rgiClapTabDec[(int)v27 + v18];
    v39[a7 + 9] = v33[(int)v27 - v19];
    v39[a7 + 8] = g_rgiClapTabDec[(int)v27 + v17];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 3]);
    LODWORD(v26) = v27 + v18;
    v34 = g_rgiClapTabDec;
    v39[a7 + 14] = g_rgiClapTabDec[(int)v26];
    v39[a7 + 13] = v34[(int)v27 - v19];
    v39[a7 + 12] = v34[(int)v27 + v17];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 4]);
    v39[a7 + 18] = v34[(int)v27 + v23];
    v39[a7 + 17] = v34[(int)v27 - v22];
    v39[a7 + 16] = v34[(int)v27 + v24];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 5]);
    LODWORD(v26) = v27 + v23;
    v7 = v34;
    v39[a7 + 22] = v34[(int)v26];
    v39[a7 + 21] = v34[(int)v27 - v22];
    v39[a7 + 20] = v34[(int)v27 + v24];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 6]);
    v39[a7 + 26] = v34[(int)v27 + v28];
    v39[a7 + 25] = v34[(int)v27 - v29];
    v39[a7 + 24] = v34[(int)v27 + v30];
    LODWORD(v27) = *((_DWORD *)&g_iYscale + v40[a5 + 7]);
    v35 = (int)v27 + v28;
    v10 = &v39[2 * a7];
    v39 = v10;
    v32[a7 + 30] = v34[v35];
    LODWORD(v26) = v27 - v29;
    v36 = v37-- == 1;
    v9 = &v40[2 * a5];
    v40 = v9;
    LOBYTE(v35) = v34[(int)v26];
    LODWORD(v26) = v27 + v30;
    a4 = v42;
    v32[a7 + 29] = v35;
    v32[a7 + 28] = v34[(int)v26];
    v8 = v41;
  }
  while ( !v36 );
}

```

## disassembly

```asm
0x1800173a0  mov     rax, rsp
0x1800173a3  mov     [rax+20h], r9
0x1800173a7  mov     [rax+18h], r8
0x1800173ab  mov     [rax+10h], rdx
0x1800173af  mov     [rax+8], rcx
0x1800173b3  push    rbx
0x1800173b4  push    rbp
0x1800173b5  push    rsi
0x1800173b6  push    rdi
0x1800173b7  push    r12
0x1800173b9  push    r13
0x1800173bb  push    r14
0x1800173bd  push    r15
0x1800173bf  sub     rsp, 18h
0x1800173c3  mov     rdi, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800173ca  lea     rbx, __ImageBase
0x1800173d1  mov     r11, r8
0x1800173d4  mov     [rsp+58h+var_58], 4
0x1800173db  mov     r8, rdx
0x1800173de  mov     r10, rcx
0x1800173e1  movzx   edx, byte ptr [r11]
0x1800173e5  movzx   eax, byte ptr [r9]
0x1800173e9  mov     r12d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x1800173f1  mov     r13d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x1800173f9  mov     r15d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180017401  add     r15d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180017409  movzx   eax, byte ptr [r8]
0x18001740d  mov     [rsp+58h+var_54], r12d
0x180017412  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x180017419  lea     eax, [rdx+r13]
0x18001741d  movsxd  rcx, eax
0x180017420  mov     al, [rcx+rdi]
0x180017423  mov     [r10+2], al
0x180017427  mov     eax, edx
0x180017429  sub     eax, r15d
0x18001742c  cdqe
0x18001742e  mov     cl, [rax+rdi]
0x180017431  lea     eax, [rdx+r12]
0x180017435  mov     [r10+1], cl
0x180017439  movsxd  rcx, eax
0x18001743c  mov     al, [rcx+rdi]
0x18001743f  mov     [r10], al
0x180017442  movzx   eax, byte ptr [r8+1]
0x180017447  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x18001744e  lea     eax, [rdx+r13]
0x180017452  movsxd  rcx, eax
0x180017455  mov     al, [rcx+rdi]
0x180017458  mov     [r10+6], al
0x18001745c  mov     eax, edx
0x18001745e  sub     eax, r15d
0x180017461  cdqe
0x180017463  mov     cl, [rax+rdi]
0x180017466  lea     eax, [rdx+r12]
0x18001746a  mov     [r10+5], cl
0x18001746e  movsxd  rcx, eax
0x180017471  mov     al, [rcx+rdi]
0x180017474  mov     [r10+4], al
0x180017478  movzx   edx, byte ptr [r11+1]
0x18001747d  movzx   eax, byte ptr [r9+1]
0x180017482  mov     ebp, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180017489  mov     r14d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180017491  mov     esi, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180017498  add     esi, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001749f  movzx   eax, byte ptr [r8+2]
0x1800174a4  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x1800174ab  lea     eax, [rdx+r14]
0x1800174af  movsxd  rcx, eax
0x1800174b2  mov     al, [rcx+rdi]
0x1800174b5  mov     [r10+0Ah], al
0x1800174b9  mov     eax, edx
0x1800174bb  sub     eax, esi
0x1800174bd  cdqe
0x1800174bf  mov     cl, [rax+rdi]
0x1800174c2  lea     eax, [rdx+rbp]
0x1800174c5  mov     [r10+9], cl
0x1800174c9  movsxd  rcx, eax
0x1800174cc  mov     al, [rcx+rdi]
0x1800174cf  mov     [r10+8], al
0x1800174d3  movzx   eax, byte ptr [r8+3]
0x1800174d8  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x1800174df  lea     eax, [rdx+r14]
0x1800174e3  movsxd  rcx, eax
0x1800174e6  mov     al, [rcx+rdi]
0x1800174e9  mov     [r10+0Eh], al
0x1800174ed  mov     eax, edx
0x1800174ef  sub     eax, esi
0x1800174f1  cdqe
0x1800174f3  mov     cl, [rax+rdi]
0x1800174f6  lea     eax, [rdx+rbp]
0x1800174f9  mov     [r10+0Dh], cl
0x1800174fd  movsxd  rcx, eax
0x180017500  mov     al, [rcx+rdi]
0x180017503  mov     [r10+0Ch], al
0x180017507  movzx   edx, byte ptr [r11+2]
0x18001750c  movzx   eax, byte ptr [r9+2]
0x180017511  mov     r11d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180017519  add     r11d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x180017521  mov     edi, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180017528  mov     ebx, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x18001752f  lea     rdx, __ImageBase
0x180017536  movzx   eax, byte ptr [r8+4]
0x18001753b  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017542  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017549  lea     eax, [rdx+rdi]
0x18001754c  movsxd  rcx, eax
0x18001754f  mov     al, [rcx+r12]
0x180017553  mov     [r10+12h], al
0x180017557  mov     eax, edx
0x180017559  sub     eax, r11d
0x18001755c  cdqe
0x18001755e  mov     cl, [rax+r12]
0x180017562  lea     eax, [rdx+rbx]
0x180017565  mov     [r10+11h], cl
0x180017569  movsxd  rcx, eax
0x18001756c  mov     al, [rcx+r12]
0x180017570  mov     [r10+10h], al
0x180017574  movzx   eax, byte ptr [r8+5]
0x180017579  lea     r8, __ImageBase
0x180017580  mov     edx, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017588  lea     eax, [rdx+rdi]
0x18001758b  movsxd  rcx, eax
0x18001758e  mov     al, [rcx+r12]
0x180017592  mov     [r10+16h], al
0x180017596  mov     eax, edx
0x180017598  sub     eax, r11d
0x18001759b  cdqe
0x18001759d  mov     cl, [rax+r12]
0x1800175a1  lea     eax, [rdx+rbx]
0x1800175a4  mov     [r10+15h], cl
0x1800175a8  movsxd  rcx, eax
0x1800175ab  mov     al, [rcx+r12]
0x1800175af  mov     rcx, [rsp+58h+arg_10]
0x1800175b4  mov     [r10+14h], al
0x1800175b8  movzx   eax, byte ptr [r9+3]
0x1800175bd  movzx   edx, byte ptr [rcx+3]
0x1800175c1  mov     r10d, rva ?g_iVtoR@@3PAJA[r8+rax*4]; long near * g_iVtoR ...
0x1800175c9  mov     ecx, rva ?g_iUtoG@@3PAJA[r8+rdx*4]; long near * g_iUtoG ...
0x1800175d1  mov     r8d, rva ?g_iVtoG@@3PAJA[r8+rax*4]; long near * g_iVtoG ...
0x1800175d9  mov     rax, [rsp+58h+arg_8]
0x1800175de  add     r8d, ecx
0x1800175e1  lea     rcx, __ImageBase
0x1800175e8  mov     r9d, rva ?g_iUtoB@@3PAJA[rcx+rdx*4]; long near * g_iUtoB ...
0x1800175f0  movzx   eax, byte ptr [rax+6]
0x1800175f4  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800175fb  lea     eax, [rdx+r10]
0x1800175ff  movsxd  rcx, eax
0x180017602  mov     al, [rcx+r12]
0x180017606  mov     rcx, [rsp+58h+arg_0]
0x18001760b  mov     [rcx+1Ah], al
0x18001760e  mov     eax, edx
0x180017610  sub     eax, r8d
0x180017613  cdqe
0x180017615  mov     cl, [rax+r12]
0x180017619  mov     rax, [rsp+58h+arg_0]
0x18001761e  mov     [rax+19h], cl
0x180017621  lea     eax, [rdx+r9]
0x180017625  movsxd  rcx, eax
0x180017628  lea     rdx, __ImageBase
0x18001762f  mov     al, [rcx+r12]
0x180017633  mov     rcx, [rsp+58h+arg_0]
0x180017638  mov     [rcx+18h], al
0x18001763b  mov     rax, [rsp+58h+arg_8]
0x180017640  movzx   eax, byte ptr [rax+7]
0x180017644  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001764b  lea     eax, [rdx+r10]
0x18001764f  movsxd  rcx, eax
0x180017652  mov     al, [rcx+r12]
0x180017656  mov     rcx, [rsp+58h+arg_0]
0x18001765b  mov     [rcx+1Eh], al
0x18001765e  mov     eax, edx
0x180017660  sub     eax, r8d
0x180017663  cdqe
0x180017665  mov     cl, [rax+r12]
0x180017669  mov     rax, [rsp+58h+arg_0]
0x18001766e  mov     [rax+1Dh], cl
0x180017671  lea     eax, [rdx+r9]
0x180017675  movsxd  rcx, eax
0x180017678  mov     al, [rcx+r12]
0x18001767c  mov     rcx, [rsp+58h+arg_0]
0x180017681  mov     [rcx+1Ch], al
0x180017684  movsxd  rax, [rsp+58h+arg_28]
0x18001768c  add     [rsp+58h+arg_10], rax
0x180017691  add     [rsp+58h+arg_18], rax
0x180017696  mov     rcx, [rsp+58h+arg_8]
0x18001769b  movsxd  rax, [rsp+58h+arg_20]
0x1800176a3  movzx   eax, byte ptr [rax+rcx]
0x1800176a7  lea     rcx, __ImageBase
0x1800176ae  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800176b5  lea     eax, [rdx+r13]
0x1800176b9  movsxd  rcx, eax
0x1800176bc  mov     al, [rcx+r12]
0x1800176c0  mov     r12, [rsp+58h+arg_0]
0x1800176c5  movsxd  rcx, [rsp+58h+arg_30]
0x1800176cd  mov     [rcx+r12+2], al
0x1800176d2  mov     eax, edx
0x1800176d4  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800176db  sub     eax, r15d
0x1800176de  cdqe
0x1800176e0  mov     cl, [rax+rcx]
0x1800176e3  movsxd  rax, [rsp+58h+arg_30]
0x1800176eb  mov     [rax+r12+1], cl
0x1800176f0  mov     r12d, [rsp+58h+var_54]
0x1800176f5  lea     eax, [rdx+r12]
0x1800176f9  mov     rdx, [rsp+58h+arg_0]
0x1800176fe  movsxd  rcx, eax
0x180017701  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017708  mov     al, [rcx+rax]
0x18001770b  movsxd  rcx, [rsp+58h+arg_30]
0x180017713  mov     [rcx+rdx], al
0x180017716  mov     rcx, [rsp+58h+arg_8]
0x18001771b  movsxd  rax, [rsp+58h+arg_20]
0x180017723  movzx   eax, byte ptr [rax+rcx+1]
0x180017728  lea     rcx, __ImageBase
0x18001772f  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017736  lea     eax, [rdx+r13]
0x18001773a  movsxd  r13, [rsp+58h+arg_30]
0x180017742  movsxd  rcx, eax
0x180017745  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001774c  mov     al, [rcx+rax]
0x18001774f  mov     rcx, [rsp+58h+arg_0]
0x180017754  mov     [rcx+r13+6], al
0x180017759  mov     eax, edx
0x18001775b  sub     eax, r15d
0x18001775e  mov     r15, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017765  cdqe
0x180017767  mov     cl, [rax+r15]
0x18001776b  mov     rax, [rsp+58h+arg_0]
0x180017770  mov     [rax+r13+5], cl
0x180017775  lea     eax, [rdx+r12]
0x180017779  mov     r12, [rsp+58h+arg_0]
0x18001777e  movsxd  rcx, eax
0x180017781  mov     al, [rcx+r15]
0x180017785  lea     rcx, __ImageBase
0x18001778c  movsxd  r15, [rsp+58h+arg_20]
0x180017794  mov     [r12+r13+4], al
0x180017799  mov     rax, [rsp+58h+arg_8]
0x18001779e  movzx   eax, byte ptr [r15+rax+2]
0x1800177a4  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800177ab  lea     eax, [rdx+r14]
0x1800177af  movsxd  rcx, eax
0x1800177b2  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800177b9  mov     al, [rcx+rax]
0x1800177bc  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800177c3  mov     [r12+r13+0Ah], al
0x1800177c8  mov     eax, edx
0x1800177ca  sub     eax, esi
0x1800177cc  cdqe
0x1800177ce  mov     cl, [rax+rcx]
0x1800177d1  lea     eax, [rdx+rbp]
0x1800177d4  mov     [r12+r13+9], cl
0x1800177d9  movsxd  rcx, eax
0x1800177dc  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800177e3  mov     al, [rcx+rax]
0x1800177e6  lea     rcx, __ImageBase
0x1800177ed  mov     [r12+r13+8], al
0x1800177f2  mov     rax, [rsp+58h+arg_8]
0x1800177f7  movzx   eax, byte ptr [r15+rax+3]
0x1800177fd  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017804  lea     eax, [rdx+r14]
0x180017808  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001780f  movsxd  rcx, eax
0x180017812  mov     al, [rcx+r14]
0x180017816  mov     [r12+r13+0Eh], al
0x18001781b  mov     eax, edx
0x18001781d  sub     eax, esi
0x18001781f  mov     rsi, [rsp+58h+arg_8]
0x180017824  cdqe
0x180017826  mov     cl, [rax+r14]
0x18001782a  lea     eax, [rdx+rbp]
0x18001782d  mov     [r12+r13+0Dh], cl
0x180017832  lea     rbp, __ImageBase
0x180017839  movsxd  rcx, eax
0x18001783c  mov     al, [rcx+r14]
0x180017840  mov     [r12+r13+0Ch], al
0x180017845  movzx   eax, byte ptr [r15+rsi+4]
0x18001784b  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x180017852  lea     eax, [rdx+rdi]
0x180017855  movsxd  rcx, eax
0x180017858  mov     al, [rcx+r14]
0x18001785c  mov     [r12+r13+12h], al
0x180017861  mov     eax, edx
0x180017863  sub     eax, r11d
0x180017866  cdqe
0x180017868  mov     cl, [rax+r14]
0x18001786c  lea     eax, [rdx+rbx]
0x18001786f  mov     [r12+r13+11h], cl
0x180017874  movsxd  rcx, eax
0x180017877  mov     al, [rcx+r14]
0x18001787b  mov     [r12+r13+10h], al
0x180017880  movzx   eax, byte ptr [r15+rsi+5]
0x180017886  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001788d  lea     eax, [rdx+rdi]
0x180017890  mov     rdi, r14
0x180017893  movsxd  rcx, eax
0x180017896  mov     al, [rcx+r14]
0x18001789a  mov     [r12+r13+16h], al
0x18001789f  mov     eax, edx
0x1800178a1  sub     eax, r11d
0x1800178a4  cdqe
0x1800178a6  mov     cl, [rax+r14]
  ... truncated ...
```
