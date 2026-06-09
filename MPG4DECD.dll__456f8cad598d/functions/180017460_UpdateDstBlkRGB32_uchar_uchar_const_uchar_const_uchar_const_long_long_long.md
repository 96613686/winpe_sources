# UpdateDstBlkRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180017460`
- end: `0x180017a3c`
- name: `?UpdateDstBlkRGB32@@YAXPEAEPEBE11JJJ@Z`
- size: `1500`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180017460`

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
0x180017460  mov     rax, rsp
0x180017463  mov     [rax+20h], r9
0x180017467  mov     [rax+18h], r8
0x18001746b  mov     [rax+10h], rdx
0x18001746f  mov     [rax+8], rcx
0x180017473  push    rbx
0x180017474  push    rbp
0x180017475  push    rsi
0x180017476  push    rdi
0x180017477  push    r12
0x180017479  push    r13
0x18001747b  push    r14
0x18001747d  push    r15
0x18001747f  sub     rsp, 18h
0x180017483  mov     rdi, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001748a  lea     rbx, __ImageBase
0x180017491  mov     r11, r8
0x180017494  mov     [rsp+58h+var_58], 4
0x18001749b  mov     r8, rdx
0x18001749e  mov     r10, rcx
0x1800174a1  movzx   edx, byte ptr [r11]
0x1800174a5  movzx   eax, byte ptr [r9]
0x1800174a9  mov     r12d, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x1800174b1  mov     r13d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x1800174b9  mov     r15d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x1800174c1  add     r15d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x1800174c9  movzx   eax, byte ptr [r8]
0x1800174cd  mov     [rsp+58h+var_54], r12d
0x1800174d2  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x1800174d9  lea     eax, [rdx+r13]
0x1800174dd  movsxd  rcx, eax
0x1800174e0  mov     al, [rcx+rdi]
0x1800174e3  mov     [r10+2], al
0x1800174e7  mov     eax, edx
0x1800174e9  sub     eax, r15d
0x1800174ec  cdqe
0x1800174ee  mov     cl, [rax+rdi]
0x1800174f1  lea     eax, [rdx+r12]
0x1800174f5  mov     [r10+1], cl
0x1800174f9  movsxd  rcx, eax
0x1800174fc  mov     al, [rcx+rdi]
0x1800174ff  mov     [r10], al
0x180017502  movzx   eax, byte ptr [r8+1]
0x180017507  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x18001750e  lea     eax, [rdx+r13]
0x180017512  movsxd  rcx, eax
0x180017515  mov     al, [rcx+rdi]
0x180017518  mov     [r10+6], al
0x18001751c  mov     eax, edx
0x18001751e  sub     eax, r15d
0x180017521  cdqe
0x180017523  mov     cl, [rax+rdi]
0x180017526  lea     eax, [rdx+r12]
0x18001752a  mov     [r10+5], cl
0x18001752e  movsxd  rcx, eax
0x180017531  mov     al, [rcx+rdi]
0x180017534  mov     [r10+4], al
0x180017538  movzx   edx, byte ptr [r11+1]
0x18001753d  movzx   eax, byte ptr [r9+1]
0x180017542  mov     ebp, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x180017549  mov     r14d, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x180017551  mov     esi, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x180017558  add     esi, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x18001755f  movzx   eax, byte ptr [r8+2]
0x180017564  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x18001756b  lea     eax, [rdx+r14]
0x18001756f  movsxd  rcx, eax
0x180017572  mov     al, [rcx+rdi]
0x180017575  mov     [r10+0Ah], al
0x180017579  mov     eax, edx
0x18001757b  sub     eax, esi
0x18001757d  cdqe
0x18001757f  mov     cl, [rax+rdi]
0x180017582  lea     eax, [rdx+rbp]
0x180017585  mov     [r10+9], cl
0x180017589  movsxd  rcx, eax
0x18001758c  mov     al, [rcx+rdi]
0x18001758f  mov     [r10+8], al
0x180017593  movzx   eax, byte ptr [r8+3]
0x180017598  mov     edx, rva ?g_iYscale@@3PAJA[rbx+rax*4]; long near * g_iYscale ...
0x18001759f  lea     eax, [rdx+r14]
0x1800175a3  movsxd  rcx, eax
0x1800175a6  mov     al, [rcx+rdi]
0x1800175a9  mov     [r10+0Eh], al
0x1800175ad  mov     eax, edx
0x1800175af  sub     eax, esi
0x1800175b1  cdqe
0x1800175b3  mov     cl, [rax+rdi]
0x1800175b6  lea     eax, [rdx+rbp]
0x1800175b9  mov     [r10+0Dh], cl
0x1800175bd  movsxd  rcx, eax
0x1800175c0  mov     al, [rcx+rdi]
0x1800175c3  mov     [r10+0Ch], al
0x1800175c7  movzx   edx, byte ptr [r11+2]
0x1800175cc  movzx   eax, byte ptr [r9+2]
0x1800175d1  mov     r11d, rva ?g_iUtoG@@3PAJA[rbx+rdx*4]; long near * g_iUtoG ...
0x1800175d9  add     r11d, rva ?g_iVtoG@@3PAJA[rbx+rax*4]; long near * g_iVtoG ...
0x1800175e1  mov     edi, rva ?g_iVtoR@@3PAJA[rbx+rax*4]; long near * g_iVtoR ...
0x1800175e8  mov     ebx, rva ?g_iUtoB@@3PAJA[rbx+rdx*4]; long near * g_iUtoB ...
0x1800175ef  lea     rdx, __ImageBase
0x1800175f6  movzx   eax, byte ptr [r8+4]
0x1800175fb  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x180017602  mov     r12, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017609  lea     eax, [rdx+rdi]
0x18001760c  movsxd  rcx, eax
0x18001760f  mov     al, [rcx+r12]
0x180017613  mov     [r10+12h], al
0x180017617  mov     eax, edx
0x180017619  sub     eax, r11d
0x18001761c  cdqe
0x18001761e  mov     cl, [rax+r12]
0x180017622  lea     eax, [rdx+rbx]
0x180017625  mov     [r10+11h], cl
0x180017629  movsxd  rcx, eax
0x18001762c  mov     al, [rcx+r12]
0x180017630  mov     [r10+10h], al
0x180017634  movzx   eax, byte ptr [r8+5]
0x180017639  lea     r8, __ImageBase
0x180017640  mov     edx, rva ?g_iYscale@@3PAJA[r8+rax*4]; long near * g_iYscale ...
0x180017648  lea     eax, [rdx+rdi]
0x18001764b  movsxd  rcx, eax
0x18001764e  mov     al, [rcx+r12]
0x180017652  mov     [r10+16h], al
0x180017656  mov     eax, edx
0x180017658  sub     eax, r11d
0x18001765b  cdqe
0x18001765d  mov     cl, [rax+r12]
0x180017661  lea     eax, [rdx+rbx]
0x180017664  mov     [r10+15h], cl
0x180017668  movsxd  rcx, eax
0x18001766b  mov     al, [rcx+r12]
0x18001766f  mov     rcx, [rsp+58h+arg_10]
0x180017674  mov     [r10+14h], al
0x180017678  movzx   eax, byte ptr [r9+3]
0x18001767d  movzx   edx, byte ptr [rcx+3]
0x180017681  mov     r10d, rva ?g_iVtoR@@3PAJA[r8+rax*4]; long near * g_iVtoR ...
0x180017689  mov     ecx, rva ?g_iUtoG@@3PAJA[r8+rdx*4]; long near * g_iUtoG ...
0x180017691  mov     r8d, rva ?g_iVtoG@@3PAJA[r8+rax*4]; long near * g_iVtoG ...
0x180017699  mov     rax, [rsp+58h+arg_8]
0x18001769e  add     r8d, ecx
0x1800176a1  lea     rcx, __ImageBase
0x1800176a8  mov     r9d, rva ?g_iUtoB@@3PAJA[rcx+rdx*4]; long near * g_iUtoB ...
0x1800176b0  movzx   eax, byte ptr [rax+6]
0x1800176b4  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800176bb  lea     eax, [rdx+r10]
0x1800176bf  movsxd  rcx, eax
0x1800176c2  mov     al, [rcx+r12]
0x1800176c6  mov     rcx, [rsp+58h+arg_0]
0x1800176cb  mov     [rcx+1Ah], al
0x1800176ce  mov     eax, edx
0x1800176d0  sub     eax, r8d
0x1800176d3  cdqe
0x1800176d5  mov     cl, [rax+r12]
0x1800176d9  mov     rax, [rsp+58h+arg_0]
0x1800176de  mov     [rax+19h], cl
0x1800176e1  lea     eax, [rdx+r9]
0x1800176e5  movsxd  rcx, eax
0x1800176e8  lea     rdx, __ImageBase
0x1800176ef  mov     al, [rcx+r12]
0x1800176f3  mov     rcx, [rsp+58h+arg_0]
0x1800176f8  mov     [rcx+18h], al
0x1800176fb  mov     rax, [rsp+58h+arg_8]
0x180017700  movzx   eax, byte ptr [rax+7]
0x180017704  mov     edx, rva ?g_iYscale@@3PAJA[rdx+rax*4]; long near * g_iYscale ...
0x18001770b  lea     eax, [rdx+r10]
0x18001770f  movsxd  rcx, eax
0x180017712  mov     al, [rcx+r12]
0x180017716  mov     rcx, [rsp+58h+arg_0]
0x18001771b  mov     [rcx+1Eh], al
0x18001771e  mov     eax, edx
0x180017720  sub     eax, r8d
0x180017723  cdqe
0x180017725  mov     cl, [rax+r12]
0x180017729  mov     rax, [rsp+58h+arg_0]
0x18001772e  mov     [rax+1Dh], cl
0x180017731  lea     eax, [rdx+r9]
0x180017735  movsxd  rcx, eax
0x180017738  mov     al, [rcx+r12]
0x18001773c  mov     rcx, [rsp+58h+arg_0]
0x180017741  mov     [rcx+1Ch], al
0x180017744  movsxd  rax, [rsp+58h+arg_28]
0x18001774c  add     [rsp+58h+arg_10], rax
0x180017751  add     [rsp+58h+arg_18], rax
0x180017756  mov     rcx, [rsp+58h+arg_8]
0x18001775b  movsxd  rax, [rsp+58h+arg_20]
0x180017763  movzx   eax, byte ptr [rax+rcx]
0x180017767  lea     rcx, __ImageBase
0x18001776e  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x180017775  lea     eax, [rdx+r13]
0x180017779  movsxd  rcx, eax
0x18001777c  mov     al, [rcx+r12]
0x180017780  mov     r12, [rsp+58h+arg_0]
0x180017785  movsxd  rcx, [rsp+58h+arg_30]
0x18001778d  mov     [rcx+r12+2], al
0x180017792  mov     eax, edx
0x180017794  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001779b  sub     eax, r15d
0x18001779e  cdqe
0x1800177a0  mov     cl, [rax+rcx]
0x1800177a3  movsxd  rax, [rsp+58h+arg_30]
0x1800177ab  mov     [rax+r12+1], cl
0x1800177b0  mov     r12d, [rsp+58h+var_54]
0x1800177b5  lea     eax, [rdx+r12]
0x1800177b9  mov     rdx, [rsp+58h+arg_0]
0x1800177be  movsxd  rcx, eax
0x1800177c1  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800177c8  mov     al, [rcx+rax]
0x1800177cb  movsxd  rcx, [rsp+58h+arg_30]
0x1800177d3  mov     [rcx+rdx], al
0x1800177d6  mov     rcx, [rsp+58h+arg_8]
0x1800177db  movsxd  rax, [rsp+58h+arg_20]
0x1800177e3  movzx   eax, byte ptr [rax+rcx+1]
0x1800177e8  lea     rcx, __ImageBase
0x1800177ef  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800177f6  lea     eax, [rdx+r13]
0x1800177fa  movsxd  r13, [rsp+58h+arg_30]
0x180017802  movsxd  rcx, eax
0x180017805  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x18001780c  mov     al, [rcx+rax]
0x18001780f  mov     rcx, [rsp+58h+arg_0]
0x180017814  mov     [rcx+r13+6], al
0x180017819  mov     eax, edx
0x18001781b  sub     eax, r15d
0x18001781e  mov     r15, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017825  cdqe
0x180017827  mov     cl, [rax+r15]
0x18001782b  mov     rax, [rsp+58h+arg_0]
0x180017830  mov     [rax+r13+5], cl
0x180017835  lea     eax, [rdx+r12]
0x180017839  mov     r12, [rsp+58h+arg_0]
0x18001783e  movsxd  rcx, eax
0x180017841  mov     al, [rcx+r15]
0x180017845  lea     rcx, __ImageBase
0x18001784c  movsxd  r15, [rsp+58h+arg_20]
0x180017854  mov     [r12+r13+4], al
0x180017859  mov     rax, [rsp+58h+arg_8]
0x18001785e  movzx   eax, byte ptr [r15+rax+2]
0x180017864  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x18001786b  lea     eax, [rdx+r14]
0x18001786f  movsxd  rcx, eax
0x180017872  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017879  mov     al, [rcx+rax]
0x18001787c  mov     rcx, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x180017883  mov     [r12+r13+0Ah], al
0x180017888  mov     eax, edx
0x18001788a  sub     eax, esi
0x18001788c  cdqe
0x18001788e  mov     cl, [rax+rcx]
0x180017891  lea     eax, [rdx+rbp]
0x180017894  mov     [r12+r13+9], cl
0x180017899  movsxd  rcx, eax
0x18001789c  mov     rax, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800178a3  mov     al, [rcx+rax]
0x1800178a6  lea     rcx, __ImageBase
0x1800178ad  mov     [r12+r13+8], al
0x1800178b2  mov     rax, [rsp+58h+arg_8]
0x1800178b7  movzx   eax, byte ptr [r15+rax+3]
0x1800178bd  mov     edx, rva ?g_iYscale@@3PAJA[rcx+rax*4]; long near * g_iYscale ...
0x1800178c4  lea     eax, [rdx+r14]
0x1800178c8  mov     r14, cs:?g_rgiClapTabDec@@3PEAEEA; uchar * g_rgiClapTabDec
0x1800178cf  movsxd  rcx, eax
0x1800178d2  mov     al, [rcx+r14]
0x1800178d6  mov     [r12+r13+0Eh], al
0x1800178db  mov     eax, edx
0x1800178dd  sub     eax, esi
0x1800178df  mov     rsi, [rsp+58h+arg_8]
0x1800178e4  cdqe
0x1800178e6  mov     cl, [rax+r14]
0x1800178ea  lea     eax, [rdx+rbp]
0x1800178ed  mov     [r12+r13+0Dh], cl
0x1800178f2  lea     rbp, __ImageBase
0x1800178f9  movsxd  rcx, eax
0x1800178fc  mov     al, [rcx+r14]
0x180017900  mov     [r12+r13+0Ch], al
0x180017905  movzx   eax, byte ptr [r15+rsi+4]
0x18001790b  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x180017912  lea     eax, [rdx+rdi]
0x180017915  movsxd  rcx, eax
0x180017918  mov     al, [rcx+r14]
0x18001791c  mov     [r12+r13+12h], al
0x180017921  mov     eax, edx
0x180017923  sub     eax, r11d
0x180017926  cdqe
0x180017928  mov     cl, [rax+r14]
0x18001792c  lea     eax, [rdx+rbx]
0x18001792f  mov     [r12+r13+11h], cl
0x180017934  movsxd  rcx, eax
0x180017937  mov     al, [rcx+r14]
0x18001793b  mov     [r12+r13+10h], al
0x180017940  movzx   eax, byte ptr [r15+rsi+5]
0x180017946  mov     edx, ss:rva ?g_iYscale@@3PAJA[rbp+rax*4]; long near * g_iYscale ...
0x18001794d  lea     eax, [rdx+rdi]
0x180017950  mov     rdi, r14
0x180017953  movsxd  rcx, eax
0x180017956  mov     al, [rcx+r14]
0x18001795a  mov     [r12+r13+16h], al
0x18001795f  mov     eax, edx
0x180017961  sub     eax, r11d
0x180017964  cdqe
0x180017966  mov     cl, [rax+r14]
  ... truncated ...
```
