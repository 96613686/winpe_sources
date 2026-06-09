# Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)

- ea: `0x18008a170`
- end: `0x18008a666`
- name: `??$PutBooleanUnit@VSmoothArticle@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1270`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800889c0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x18008a170`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,3>(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5)
{
  signed int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r10
  __int64 v15; // r11
  __int64 v16; // rbp
  __int64 v17; // r14
  __int64 v18; // r15
  __int64 v19; // r12
  __int64 v20; // rax
  __int64 v21; // r13
  _WORD *v22; // rdi
  char *v23; // rbx
  _WORD *v24; // rcx
  char *v25; // rdx
  char *v26; // rsi
  __int16 v27; // ax
  __int16 v28; // dx
  unsigned __int16 v29; // dx
  int v30; // ebx
  _QWORD *v32; // rdi
  int v33; // r8d
  int v34; // esi
  __int64 v45; // r10
  __int64 v46; // rdx
  __int64 v47; // rax
  int v48; // ecx
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // rbp
  __int64 v52; // r14
  __int64 v53; // r15
  __int64 v54; // r12
  __int64 v55; // r13
  __int64 v56; // rcx
  __int64 v57; // rsi
  __int64 v58; // r8
  char *v59; // r10
  __int64 v60; // r11
  __int64 v61; // r9
  __int16 v62; // dx
  __int16 v63; // cx
  int v64; // eax
  int v77; // [rsp+20h] [rbp-E8h]
  int v78; // [rsp+24h] [rbp-E4h]
  __int64 v79; // [rsp+28h] [rbp-E0h]
  int v80; // [rsp+30h] [rbp-D8h]
  _WORD *v81; // [rsp+38h] [rbp-D0h]
  char *v82; // [rsp+40h] [rbp-C8h]
  char *v83; // [rsp+48h] [rbp-C0h]
  _WORD *v84; // [rsp+50h] [rbp-B8h]
  char *v85; // [rsp+58h] [rbp-B0h]
  _WORD *v86; // [rsp+60h] [rbp-A8h]
  char *v87; // [rsp+68h] [rbp-A0h]
  _WORD *v88; // [rsp+70h] [rbp-98h]
  _BYTE v92[8]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE *v93; // [rsp+A0h] [rbp-68h]
  __int128 v94; // [rsp+A8h] [rbp-60h] BYREF

  v77 = a1;
  __asm { vpxor   xmm0, xmm0, xmm0 }
  _RDX = v92;
  __asm { vmovups xmmword ptr [r11-70h], xmm0 }
  Binary::Policy::CompleteOperation::TargetDigitalRegion(a2, v92);
  if ( a1 > 1 )
  {
    v11 = a1 & 0x80000001;
    v77 = v11;
    if ( v11 < 0 )
    {
      v11 = (((_BYTE)v11 - 1) | 0xFFFFFFFE) + 1;
      v77 = v11;
    }
    if ( v11 < 0 )
      v77 = v11 + 2;
  }
  v12 = a4[6];
  v13 = 8;
  v14 = a4[7] - v12;
  v15 = a4[5] - v12;
  v16 = a4[4] - v12;
  v17 = a4[3] - v12;
  v18 = a4[2] - v12;
  v19 = a4[1] - v12;
  v20 = (__int64)a5 << 6;
  v21 = *a4 - v12;
  v81 = (__int16 *)((char *)&word_1800DE70E + v20);
  v22 = (__int16 *)((char *)&word_1800DE70E + v20);
  v82 = &byte_1800DE70C[v20];
  v23 = &byte_1800DE70C[v20];
  v88 = (__int16 *)((char *)&word_1800DE70A + v20);
  v87 = &byte_1800DE708[v20];
  v86 = (__int16 *)((char *)&word_1800DE706 + v20);
  v85 = &byte_1800DE704[v20];
  v24 = (__int16 *)((char *)&word_1800DE702 + v20);
  v25 = &Binary::Policy::SmoothArticle::OddOperation[v20];
  v84 = (__int16 *)((char *)&word_1800DE702 + v20);
  v83 = &Binary::Policy::SmoothArticle::OddOperation[v20];
  v26 = (char *)&v94 - v12;
  do
  {
    v27 = *(_WORD *)v25;
    v28 = *(_WORD *)(v12 + v21);
    v12 += 2;
    v29 = *(_WORD *)v23 * *(_WORD *)(v12 - 2)
        + *v22 * *(_WORD *)(v14 + v12 - 2)
        + *v88 * *(_WORD *)(v15 + v12 - 2)
        + *(_WORD *)v87 * *(_WORD *)(v12 + v16 - 2)
        + *v86 * *(_WORD *)(v17 + v12 - 2)
        + *(_WORD *)v85 * *(_WORD *)(v18 + v12 - 2)
        + *v24 * *(_WORD *)(v19 + v12 - 2)
        + v27 * v28;
    v24 = v84;
    *(_WORD *)&v26[v12 - 2] = v29 >> 6;
    v25 = v83;
    --v13;
  }
  while ( v13 );
  v30 = v77;
  _RDX = 0x180000000uLL;
  v32 = a4;
  v33 = 1;
  v34 = 0;
  _RAX = (__int64)v77 << 6;
  v80 = 1;
  __asm
  {
    vmovdqu xmm0, xmmword ptr [rax+rdx+0DE700h]
    vpmullw xmm2, xmm0, [rsp+108h+var_60]
  }
  __asm
  {
    vpsrldq xmm1, xmm2, 8
    vpaddw  xmm3, xmm2, xmm1
    vpsrldq xmm0, xmm3, 4
    vpaddw  xmm1, xmm3, xmm0
    vpsrldq xmm0, xmm1, 2
    vpaddw  xmm1, xmm1, xmm0
    vmovd   ecx, xmm1
  }
  *v93 = BYTE1(_ECX);
  if ( *(int *)(a3 + 12) > 1 )
  {
    v45 = 1;
    v79 = 1;
    do
    {
      v46 = Binary::Policy::SmoothArticle::GlobalCase[v30];
      v47 = 0;
      v34 += v46;
      v48 = 8 - v46;
      v78 = v34;
      v49 = 8 - (int)v46;
      if ( 8 - (int)v46 > 0 )
      {
        do
        {
          *((_WORD *)&v94 + v47) = *((_WORD *)&v94 + v46 + v47);
          ++v47;
        }
        while ( v47 < v48 );
        v33 = v80;
      }
      if ( v48 < 8LL )
      {
        v50 = v32[6];
        v51 = v32[5] - v50;
        v52 = v32[4] - v50;
        v53 = v32[3] - v50;
        v54 = v32[2] - v50;
        v55 = v32[1] - v50;
        v56 = v34;
        v57 = v32[7] - v50;
        v58 = v50 + 2 * (v49 + v56);
        v59 = (char *)&v94 - v50 + -2 * v56;
        v60 = 8 - v49;
        v61 = *v32 - v50;
        do
        {
          v62 = *(_WORD *)(v58 + v61);
          v63 = *(_WORD *)(v58 + v55);
          v58 += 2;
          *(_WORD *)&v59[v58 - 2] = (unsigned __int16)(*(_WORD *)(v58 - 2) * *(_WORD *)v82
                                                     + *v81 * *(_WORD *)(v58 + v57 - 2)
                                                     + *v88 * *(_WORD *)(v58 + v51 - 2)
                                                     + *(_WORD *)v87 * *(_WORD *)(v58 + v52 - 2)
                                                     + *v86 * *(_WORD *)(v58 + v53 - 2)
                                                     + *(_WORD *)v85 * *(_WORD *)(v58 + v54 - 2)
                                                     + *v84 * v63
                                                     + *(_WORD *)v83 * v62) >> 6;
          --v60;
        }
        while ( v60 );
        v30 = v77;
        v32 = a4;
        v34 = v78;
        v33 = v80;
        v45 = v79;
      }
      v64 = v30 + 1;
      v30 = 0;
      _RCX = 0x180000000uLL;
      if ( v64 < 2 )
        v30 = v64;
      ++v33;
      _RAX = (__int64)v30 << 6;
      v77 = v30;
      v80 = v33;
      __asm
      {
        vmovdqu xmm0, xmmword ptr [rax+rcx+0DE700h]
        vpmullw xmm2, xmm0, [rsp+108h+var_60]
      }
      __asm
      {
        vpsrldq xmm1, xmm2, 8
        vpaddw  xmm3, xmm2, xmm1
        vpsrldq xmm0, xmm3, 4
        vpaddw  xmm1, xmm3, xmm0
        vpsrldq xmm0, xmm1, 2
        vpaddw  xmm1, xmm1, xmm0
        vmovd   edx, xmm1
      }
      v93[v45] = BYTE1(_EDX);
      v79 = ++v45;
    }
    while ( v33 < *(_DWORD *)(a3 + 12) );
  }
  return Binary::Policy::CompleteOperation::MoveVirtualAddition(a2, v92);
}

```

## disassembly

```asm
0x18008a170  mov     r11, rsp
0x18008a173  mov     [r11+8], rbx
0x18008a177  push    rbp
0x18008a178  push    rsi
0x18008a179  push    rdi
0x18008a17a  push    r12
0x18008a17c  push    r13
0x18008a17e  push    r14
0x18008a180  push    r15
0x18008a182  sub     rsp, 0D0h
0x18008a189  mov     rax, cs:__security_cookie
0x18008a190  xor     rax, rsp
0x18008a193  mov     [rsp+108h+var_48], rax
0x18008a19b  mov     rdi, r9
0x18008a19e  mov     [rsp+108h+var_90], r9
0x18008a1a3  mov     r9, rdx
0x18008a1a6  mov     [rsp+108h+var_78], rdx
0x18008a1ae  mov     ebx, ecx
0x18008a1b0  mov     [rsp+108h+var_E8], ecx
0x18008a1b4  vpxor   xmm0, xmm0, xmm0
0x18008a1b8  xor     esi, esi
0x18008a1ba  mov     [rsp+108h+var_88], r8
0x18008a1c2  mov     rcx, r9
0x18008a1c5  mov     [rsp+108h+var_E4], esi
0x18008a1c9  lea     rdx, [r11-70h]
0x18008a1cd  vmovups xmmword ptr [r11-70h], xmm0
0x18008a1d3  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18008a1d8  cmp     ebx, 1
0x18008a1db  jbe     short loc_18008A1FF
0x18008a1dd  and     ebx, 80000001h
0x18008a1e3  mov     [rsp+108h+var_E8], ebx
0x18008a1e7  jge     short loc_18008A1F4
0x18008a1e9  dec     ebx
0x18008a1eb  or      ebx, 0FFFFFFFEh
0x18008a1ee  inc     ebx
0x18008a1f0  mov     [rsp+108h+var_E8], ebx
0x18008a1f4  test    ebx, ebx
0x18008a1f6  jns     short loc_18008A1FF
0x18008a1f8  add     ebx, 2
0x18008a1fb  mov     [rsp+108h+var_E8], ebx
0x18008a1ff  mov     r8, [rdi+30h]
0x18008a203  lea     rdx, cs:180000000h
0x18008a20a  movsxd  rax, [rsp+108h+arg_20]
0x18008a212  lea     rcx, rva word_1800DE70E[rdx]
0x18008a219  mov     r10, [rdi+38h]
0x18008a21d  mov     r9d, 8
0x18008a223  mov     r11, [rdi+28h]
0x18008a227  sub     r10, r8
0x18008a22a  mov     rbp, [rdi+20h]
0x18008a22e  sub     r11, r8
0x18008a231  mov     r14, [rdi+18h]
0x18008a235  sub     rbp, r8
0x18008a238  mov     r15, [rdi+10h]
0x18008a23c  sub     r14, r8
0x18008a23f  mov     r12, [rdi+8]
0x18008a243  sub     r15, r8
0x18008a246  mov     r13, [rdi]
0x18008a249  sub     r12, r8
0x18008a24c  shl     rax, 6
0x18008a250  sub     r13, r8
0x18008a253  add     rcx, rax
0x18008a256  mov     [rsp+108h+var_D0], rcx
0x18008a25b  lea     rcx, rva byte_1800DE70C[rdx]
0x18008a262  mov     rdi, [rsp+108h+var_D0]
0x18008a267  add     rcx, rax
0x18008a26a  mov     [rsp+108h+var_C8], rcx
0x18008a26f  lea     rcx, rva word_1800DE70A[rdx]
0x18008a276  mov     rbx, [rsp+108h+var_C8]
0x18008a27b  add     rcx, rax
0x18008a27e  mov     [rsp+108h+var_98], rcx
0x18008a283  lea     rcx, rva byte_1800DE708[rdx]
0x18008a28a  add     rcx, rax
0x18008a28d  mov     [rsp+108h+var_A0], rcx
0x18008a292  lea     rcx, rva word_1800DE706[rdx]
0x18008a299  add     rcx, rax
0x18008a29c  mov     [rsp+108h+var_A8], rcx
0x18008a2a1  lea     rcx, rva byte_1800DE704[rdx]
0x18008a2a8  add     rcx, rax
0x18008a2ab  mov     [rsp+108h+var_B0], rcx
0x18008a2b0  lea     rcx, rva word_1800DE702[rdx]
0x18008a2b7  add     rcx, rax
0x18008a2ba  lea     rdx, rva ?OddOperation@SmoothArticle@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$01$00$0A@$0IA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,2,1,0,128> const Binary::Policy::SmoothArticle::OddOperation ...
0x18008a2c1  add     rdx, rax
0x18008a2c4  mov     [rsp+108h+var_B8], rcx
0x18008a2c9  lea     rax, [rsp+108h+var_60]
0x18008a2d1  mov     [rsp+108h+var_C0], rdx
0x18008a2d6  sub     rax, r8
0x18008a2d9  mov     rsi, rax
0x18008a2dc  nop     dword ptr [rax+00h]
0x18008a2e0  movzx   eax, word ptr [rdx]
0x18008a2e3  movzx   edx, word ptr [r8+r13]
0x18008a2e8  lea     r8, [r8+2]
0x18008a2ec  imul    edx, eax
0x18008a2ef  movzx   eax, word ptr [rcx]
0x18008a2f2  movzx   ecx, word ptr [r12+r8-2]
0x18008a2f8  imul    ecx, eax
0x18008a2fb  mov     rax, [rsp+108h+var_B0]
0x18008a300  movzx   eax, word ptr [rax]
0x18008a303  add     dx, cx
0x18008a306  movzx   ecx, word ptr [r15+r8-2]
0x18008a30c  imul    ecx, eax
0x18008a30f  mov     rax, [rsp+108h+var_A8]
0x18008a314  movzx   eax, word ptr [rax]
0x18008a317  add     dx, cx
0x18008a31a  movzx   ecx, word ptr [r14+r8-2]
0x18008a320  imul    ecx, eax
0x18008a323  mov     rax, [rsp+108h+var_A0]
0x18008a328  movzx   eax, word ptr [rax]
0x18008a32b  add     dx, cx
0x18008a32e  movzx   ecx, word ptr [r8+rbp-2]
0x18008a334  imul    ecx, eax
0x18008a337  mov     rax, [rsp+108h+var_98]
0x18008a33c  movzx   eax, word ptr [rax]
0x18008a33f  add     dx, cx
0x18008a342  movzx   ecx, word ptr [r11+r8-2]
0x18008a348  imul    ecx, eax
0x18008a34b  movzx   eax, word ptr [rdi]
0x18008a34e  add     dx, cx
0x18008a351  movzx   ecx, word ptr [r10+r8-2]
0x18008a357  imul    ecx, eax
0x18008a35a  movzx   eax, word ptr [rbx]
0x18008a35d  add     dx, cx
0x18008a360  movzx   ecx, word ptr [r8-2]
0x18008a365  imul    ecx, eax
0x18008a368  add     dx, cx
0x18008a36b  mov     rcx, [rsp+108h+var_B8]
0x18008a370  shr     dx, 6
0x18008a374  mov     [rsi+r8-2], dx
0x18008a37a  mov     rdx, [rsp+108h+var_C0]
0x18008a37f  sub     r9, 1
0x18008a383  jnz     loc_18008A2E0
0x18008a389  movsxd  rbx, [rsp+108h+var_E8]
0x18008a38e  lea     rdx, cs:180000000h
0x18008a395  mov     rdi, [rsp+108h+var_90]
0x18008a39a  mov     r8d, 1
0x18008a3a0  mov     esi, [rsp+108h+var_E4]
0x18008a3a4  mov     rax, rbx
0x18008a3a7  shl     rax, 6
0x18008a3ab  mov     [rsp+108h+var_D8], r8
0x18008a3b0  vmovdqu xmm0, xmmword ptr [rax+rdx+0DE700h]
0x18008a3b9  vpmullw xmm2, xmm0, [rsp+108h+var_60]
0x18008a3c2  mov     rax, [rsp+108h+var_68]
0x18008a3ca  vpsrldq xmm1, xmm2, 8
0x18008a3cf  vpaddw  xmm3, xmm2, xmm1
0x18008a3d3  vpsrldq xmm0, xmm3, 4
0x18008a3d8  vpaddw  xmm1, xmm3, xmm0
0x18008a3dc  vpsrldq xmm0, xmm1, 2
0x18008a3e1  vpaddw  xmm1, xmm1, xmm0
0x18008a3e5  vmovd   ecx, xmm1
0x18008a3e9  shr     cx, 8
0x18008a3ed  mov     [rax], cl
0x18008a3ef  mov     rax, [rsp+108h+var_88]
0x18008a3f7  cmp     [rax+0Ch], r8d
0x18008a3fb  jle     loc_18008A626
0x18008a401  mov     r10d, r8d
0x18008a404  mov     [rsp+108h+var_E0], r8
0x18008a409  nop     dword ptr [rax+00000000h]
0x18008a410  movsxd  rax, ebx
0x18008a413  mov     ecx, 8
0x18008a418  movsxd  rdx, ds:rva ?GlobalCase@SmoothArticle@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B[rdx+rax*4]; Data::StripedCategory<int,2> const Binary::Policy::SmoothArticle::GlobalCase ...
0x18008a420  xor     eax, eax
0x18008a422  add     esi, edx
0x18008a424  sub     ecx, edx
0x18008a426  mov     [rsp+108h+var_E4], esi
0x18008a42a  movsxd  r9, ecx
0x18008a42d  test    ecx, ecx
0x18008a42f  jle     short loc_18008A461
0x18008a431  lea     r8, [rdx+rdx]
0x18008a435  nop     word ptr [rax+rax+00000000h]
0x18008a440  lea     rcx, [r8+rax*2]
0x18008a444  movzx   edx, word ptr [rsp+rcx+108h+var_60]
0x18008a44c  mov     word ptr [rsp+rax*2+108h+var_60], dx
0x18008a454  inc     rax
0x18008a457  cmp     rax, r9
0x18008a45a  jl      short loc_18008A440
0x18008a45c  mov     r8, [rsp+108h+var_D8]
0x18008a461  cmp     r9, 8
0x18008a465  jge     loc_18008A59F
0x18008a46b  mov     rdx, [rdi+30h]
0x18008a46f  lea     r10, [rsp+108h+var_60]
0x18008a477  mov     rbp, [rdi+28h]
0x18008a47b  mov     r11d, 8
0x18008a481  mov     r14, [rdi+20h]
0x18008a485  sub     rbp, rdx
0x18008a488  mov     r15, [rdi+18h]
0x18008a48c  sub     r14, rdx
0x18008a48f  mov     r12, [rdi+10h]
0x18008a493  sub     r15, rdx
0x18008a496  mov     r13, [rdi+8]
0x18008a49a  sub     r12, rdx
0x18008a49d  mov     rbx, [rsp+108h+var_C8]
0x18008a4a2  sub     r13, rdx
0x18008a4a5  movsxd  rcx, esi
0x18008a4a8  mov     rsi, [rdi+38h]
0x18008a4ac  sub     rsi, rdx
0x18008a4af  lea     rax, [r9+rcx]
0x18008a4b3  lea     r8, [rdx+rax*2]
0x18008a4b7  mov     rax, [rdi]
0x18008a4ba  mov     rdi, [rsp+108h+var_D0]
0x18008a4bf  sub     rax, rdx
0x18008a4c2  mov     [rsp+108h+var_80], rax
0x18008a4ca  lea     rax, [rcx+rcx]
0x18008a4ce  sub     r10, rax
0x18008a4d1  sub     r10, rdx
0x18008a4d4  sub     r11, r9
0x18008a4d7  mov     r9, [rsp+108h+var_80]
0x18008a4df  nop
0x18008a4e0  mov     rax, [rsp+108h+var_C0]
0x18008a4e5  movzx   edx, word ptr [r8+r9]
0x18008a4ea  movzx   ecx, word ptr [r8+r13]
0x18008a4ef  lea     r8, [r8+2]
0x18008a4f3  movzx   eax, word ptr [rax]
0x18008a4f6  imul    edx, eax
0x18008a4f9  mov     rax, [rsp+108h+var_B8]
0x18008a4fe  movzx   eax, word ptr [rax]
0x18008a501  imul    ecx, eax
0x18008a504  mov     rax, [rsp+108h+var_B0]
0x18008a509  movzx   eax, word ptr [rax]
0x18008a50c  add     dx, cx
0x18008a50f  movzx   ecx, word ptr [r8+r12-2]
0x18008a515  imul    ecx, eax
0x18008a518  mov     rax, [rsp+108h+var_A8]
0x18008a51d  movzx   eax, word ptr [rax]
0x18008a520  add     dx, cx
0x18008a523  movzx   ecx, word ptr [r8+r15-2]
0x18008a529  imul    ecx, eax
0x18008a52c  mov     rax, [rsp+108h+var_A0]
0x18008a531  movzx   eax, word ptr [rax]
0x18008a534  add     dx, cx
0x18008a537  movzx   ecx, word ptr [r8+r14-2]
0x18008a53d  imul    ecx, eax
0x18008a540  mov     rax, [rsp+108h+var_98]
0x18008a545  movzx   eax, word ptr [rax]
0x18008a548  add     dx, cx
0x18008a54b  movzx   ecx, word ptr [r8+rbp-2]
0x18008a551  imul    ecx, eax
0x18008a554  movzx   eax, word ptr [rdi]
0x18008a557  add     dx, cx
0x18008a55a  movzx   ecx, word ptr [r8+rsi-2]
0x18008a560  imul    ecx, eax
0x18008a563  movzx   eax, word ptr [r8-2]
0x18008a568  add     dx, cx
0x18008a56b  movzx   ecx, word ptr [rbx]
0x18008a56e  imul    ecx, eax
0x18008a571  add     dx, cx
0x18008a574  shr     dx, 6
0x18008a578  mov     [r8+r10-2], dx
0x18008a57e  sub     r11, 1
0x18008a582  jnz     loc_18008A4E0
0x18008a588  mov     ebx, [rsp+108h+var_E8]
0x18008a58c  mov     rdi, [rsp+108h+var_90]
0x18008a591  mov     esi, [rsp+108h+var_E4]
0x18008a595  mov     r8, [rsp+108h+var_D8]
0x18008a59a  mov     r10, [rsp+108h+var_E0]
0x18008a59f  lea     eax, [rbx+1]
0x18008a5a2  xor     ebx, ebx
0x18008a5a4  cmp     eax, 2
0x18008a5a7  lea     rcx, cs:180000000h
0x18008a5ae  cmovl   ebx, eax
0x18008a5b1  inc     r8d
0x18008a5b4  movsxd  rax, ebx
0x18008a5b7  shl     rax, 6
0x18008a5bb  mov     [rsp+108h+var_E8], ebx
0x18008a5bf  mov     [rsp+108h+var_D8], r8
0x18008a5c4  vmovdqu xmm0, xmmword ptr [rax+rcx+0DE700h]
0x18008a5cd  vpmullw xmm2, xmm0, [rsp+108h+var_60]
0x18008a5d6  mov     rax, [rsp+108h+var_68]
0x18008a5de  vpsrldq xmm1, xmm2, 8
0x18008a5e3  vpaddw  xmm3, xmm2, xmm1
0x18008a5e7  vpsrldq xmm0, xmm3, 4
0x18008a5ec  vpaddw  xmm1, xmm3, xmm0
0x18008a5f0  vpsrldq xmm0, xmm1, 2
0x18008a5f5  vpaddw  xmm1, xmm1, xmm0
0x18008a5f9  vmovd   edx, xmm1
0x18008a5fd  shr     dx, 8
0x18008a601  mov     [r10+rax], dl
0x18008a605  inc     r10
0x18008a608  mov     rax, [rsp+108h+var_88]
0x18008a610  lea     rdx, cs:180000000h
0x18008a617  mov     [rsp+108h+var_E0], r10
0x18008a61c  cmp     r8d, [rax+0Ch]
0x18008a620  jl      loc_18008A410
0x18008a626  mov     rcx, [rsp+108h+var_78]
0x18008a62e  lea     rdx, [rsp+108h+var_70]
0x18008a636  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008a63b  mov     rcx, [rsp+108h+var_48]
0x18008a643  xor     rcx, rsp; StackCookie
0x18008a646  call    __security_check_cookie
0x18008a64b  mov     rbx, [rsp+108h+arg_0]
0x18008a653  add     rsp, 0D0h
0x18008a65a  pop     r15
0x18008a65c  pop     r14
0x18008a65e  pop     r13
0x18008a660  pop     r12
0x18008a662  pop     rdi
0x18008a663  pop     rsi
0x18008a664  pop     rbp
0x18008a665  retn
```
