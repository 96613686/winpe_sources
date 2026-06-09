# Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)

- ea: `0x180089c70`
- end: `0x18008a166`
- name: `??$PutBooleanUnit@VSlowSource@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z`
- size: `1270`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800886a0`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180089c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,3>(
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
  if ( a1 > 3 )
  {
    v11 = a1 & 0x80000003;
    v77 = v11;
    if ( v11 < 0 )
    {
      v11 = (((_BYTE)v11 - 1) | 0xFFFFFFFC) + 1;
      v77 = v11;
    }
    if ( v11 < 0 )
      v77 = v11 + 4;
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
  v81 = (__int16 *)((char *)&word_1800DE48E + v20);
  v22 = (__int16 *)((char *)&word_1800DE48E + v20);
  v82 = &byte_1800DE48C[v20];
  v23 = &byte_1800DE48C[v20];
  v88 = (__int16 *)((char *)&word_1800DE48A + v20);
  v87 = &byte_1800DE488[v20];
  v86 = (__int16 *)((char *)&word_1800DE486 + v20);
  v85 = &byte_1800DE484[v20];
  v24 = (__int16 *)((char *)&word_1800DE482 + v20);
  v25 = &Binary::Policy::SlowSource::OddOperation[v20];
  v84 = (__int16 *)((char *)&word_1800DE482 + v20);
  v83 = &Binary::Policy::SlowSource::OddOperation[v20];
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
    vmovdqu xmm0, xmmword ptr [rax+rdx+0DE480h]
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
      v46 = Binary::Policy::SlowSource::GlobalCase[v30];
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
      if ( v64 < 4 )
        v30 = v64;
      ++v33;
      _RAX = (__int64)v30 << 6;
      v77 = v30;
      v80 = v33;
      __asm
      {
        vmovdqu xmm0, xmmword ptr [rax+rcx+0DE480h]
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
0x180089c70  mov     r11, rsp
0x180089c73  mov     [r11+8], rbx
0x180089c77  push    rbp
0x180089c78  push    rsi
0x180089c79  push    rdi
0x180089c7a  push    r12
0x180089c7c  push    r13
0x180089c7e  push    r14
0x180089c80  push    r15
0x180089c82  sub     rsp, 0D0h
0x180089c89  mov     rax, cs:__security_cookie
0x180089c90  xor     rax, rsp
0x180089c93  mov     [rsp+108h+var_48], rax
0x180089c9b  mov     rdi, r9
0x180089c9e  mov     [rsp+108h+var_90], r9
0x180089ca3  mov     r9, rdx
0x180089ca6  mov     [rsp+108h+var_78], rdx
0x180089cae  mov     ebx, ecx
0x180089cb0  mov     [rsp+108h+var_E8], ecx
0x180089cb4  vpxor   xmm0, xmm0, xmm0
0x180089cb8  xor     esi, esi
0x180089cba  mov     [rsp+108h+var_88], r8
0x180089cc2  mov     rcx, r9
0x180089cc5  mov     [rsp+108h+var_E4], esi
0x180089cc9  lea     rdx, [r11-70h]
0x180089ccd  vmovups xmmword ptr [r11-70h], xmm0
0x180089cd3  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x180089cd8  cmp     ebx, 3
0x180089cdb  jbe     short loc_180089CFF
0x180089cdd  and     ebx, 80000003h
0x180089ce3  mov     [rsp+108h+var_E8], ebx
0x180089ce7  jge     short loc_180089CF4
0x180089ce9  dec     ebx
0x180089ceb  or      ebx, 0FFFFFFFCh
0x180089cee  inc     ebx
0x180089cf0  mov     [rsp+108h+var_E8], ebx
0x180089cf4  test    ebx, ebx
0x180089cf6  jns     short loc_180089CFF
0x180089cf8  add     ebx, 4
0x180089cfb  mov     [rsp+108h+var_E8], ebx
0x180089cff  mov     r8, [rdi+30h]
0x180089d03  lea     rdx, cs:180000000h
0x180089d0a  movsxd  rax, [rsp+108h+arg_20]
0x180089d12  lea     rcx, rva word_1800DE48E[rdx]
0x180089d19  mov     r10, [rdi+38h]
0x180089d1d  mov     r9d, 8
0x180089d23  mov     r11, [rdi+28h]
0x180089d27  sub     r10, r8
0x180089d2a  mov     rbp, [rdi+20h]
0x180089d2e  sub     r11, r8
0x180089d31  mov     r14, [rdi+18h]
0x180089d35  sub     rbp, r8
0x180089d38  mov     r15, [rdi+10h]
0x180089d3c  sub     r14, r8
0x180089d3f  mov     r12, [rdi+8]
0x180089d43  sub     r15, r8
0x180089d46  mov     r13, [rdi]
0x180089d49  sub     r12, r8
0x180089d4c  shl     rax, 6
0x180089d50  sub     r13, r8
0x180089d53  add     rcx, rax
0x180089d56  mov     [rsp+108h+var_D0], rcx
0x180089d5b  lea     rcx, rva byte_1800DE48C[rdx]
0x180089d62  mov     rdi, [rsp+108h+var_D0]
0x180089d67  add     rcx, rax
0x180089d6a  mov     [rsp+108h+var_C8], rcx
0x180089d6f  lea     rcx, rva word_1800DE48A[rdx]
0x180089d76  mov     rbx, [rsp+108h+var_C8]
0x180089d7b  add     rcx, rax
0x180089d7e  mov     [rsp+108h+var_98], rcx
0x180089d83  lea     rcx, rva byte_1800DE488[rdx]
0x180089d8a  add     rcx, rax
0x180089d8d  mov     [rsp+108h+var_A0], rcx
0x180089d92  lea     rcx, rva word_1800DE486[rdx]
0x180089d99  add     rcx, rax
0x180089d9c  mov     [rsp+108h+var_A8], rcx
0x180089da1  lea     rcx, rva byte_1800DE484[rdx]
0x180089da8  add     rcx, rax
0x180089dab  mov     [rsp+108h+var_B0], rcx
0x180089db0  lea     rcx, rva word_1800DE482[rdx]
0x180089db7  add     rcx, rax
0x180089dba  lea     rdx, rva ?OddOperation@SlowSource@Policy@Binary@@2V?$OneContext@V?$OneContext@G$07$00$0A@$0BA@@Data@@$03$00$0A@$0BAA@@Data@@B[rdx]; Data::OneContext<Data::OneContext<ushort,8,1,0,16>,4,1,0,256> const Binary::Policy::SlowSource::OddOperation ...
0x180089dc1  add     rdx, rax
0x180089dc4  mov     [rsp+108h+var_B8], rcx
0x180089dc9  lea     rax, [rsp+108h+var_60]
0x180089dd1  mov     [rsp+108h+var_C0], rdx
0x180089dd6  sub     rax, r8
0x180089dd9  mov     rsi, rax
0x180089ddc  nop     dword ptr [rax+00h]
0x180089de0  movzx   eax, word ptr [rdx]
0x180089de3  movzx   edx, word ptr [r8+r13]
0x180089de8  lea     r8, [r8+2]
0x180089dec  imul    edx, eax
0x180089def  movzx   eax, word ptr [rcx]
0x180089df2  movzx   ecx, word ptr [r12+r8-2]
0x180089df8  imul    ecx, eax
0x180089dfb  mov     rax, [rsp+108h+var_B0]
0x180089e00  movzx   eax, word ptr [rax]
0x180089e03  add     dx, cx
0x180089e06  movzx   ecx, word ptr [r15+r8-2]
0x180089e0c  imul    ecx, eax
0x180089e0f  mov     rax, [rsp+108h+var_A8]
0x180089e14  movzx   eax, word ptr [rax]
0x180089e17  add     dx, cx
0x180089e1a  movzx   ecx, word ptr [r14+r8-2]
0x180089e20  imul    ecx, eax
0x180089e23  mov     rax, [rsp+108h+var_A0]
0x180089e28  movzx   eax, word ptr [rax]
0x180089e2b  add     dx, cx
0x180089e2e  movzx   ecx, word ptr [r8+rbp-2]
0x180089e34  imul    ecx, eax
0x180089e37  mov     rax, [rsp+108h+var_98]
0x180089e3c  movzx   eax, word ptr [rax]
0x180089e3f  add     dx, cx
0x180089e42  movzx   ecx, word ptr [r11+r8-2]
0x180089e48  imul    ecx, eax
0x180089e4b  movzx   eax, word ptr [rdi]
0x180089e4e  add     dx, cx
0x180089e51  movzx   ecx, word ptr [r10+r8-2]
0x180089e57  imul    ecx, eax
0x180089e5a  movzx   eax, word ptr [rbx]
0x180089e5d  add     dx, cx
0x180089e60  movzx   ecx, word ptr [r8-2]
0x180089e65  imul    ecx, eax
0x180089e68  add     dx, cx
0x180089e6b  mov     rcx, [rsp+108h+var_B8]
0x180089e70  shr     dx, 6
0x180089e74  mov     [rsi+r8-2], dx
0x180089e7a  mov     rdx, [rsp+108h+var_C0]
0x180089e7f  sub     r9, 1
0x180089e83  jnz     loc_180089DE0
0x180089e89  movsxd  rbx, [rsp+108h+var_E8]
0x180089e8e  lea     rdx, cs:180000000h
0x180089e95  mov     rdi, [rsp+108h+var_90]
0x180089e9a  mov     r8d, 1
0x180089ea0  mov     esi, [rsp+108h+var_E4]
0x180089ea4  mov     rax, rbx
0x180089ea7  shl     rax, 6
0x180089eab  mov     [rsp+108h+var_D8], r8
0x180089eb0  vmovdqu xmm0, xmmword ptr [rax+rdx+0DE480h]
0x180089eb9  vpmullw xmm2, xmm0, [rsp+108h+var_60]
0x180089ec2  mov     rax, [rsp+108h+var_68]
0x180089eca  vpsrldq xmm1, xmm2, 8
0x180089ecf  vpaddw  xmm3, xmm2, xmm1
0x180089ed3  vpsrldq xmm0, xmm3, 4
0x180089ed8  vpaddw  xmm1, xmm3, xmm0
0x180089edc  vpsrldq xmm0, xmm1, 2
0x180089ee1  vpaddw  xmm1, xmm1, xmm0
0x180089ee5  vmovd   ecx, xmm1
0x180089ee9  shr     cx, 8
0x180089eed  mov     [rax], cl
0x180089eef  mov     rax, [rsp+108h+var_88]
0x180089ef7  cmp     [rax+0Ch], r8d
0x180089efb  jle     loc_18008A126
0x180089f01  mov     r10d, r8d
0x180089f04  mov     [rsp+108h+var_E0], r8
0x180089f09  nop     dword ptr [rax+00000000h]
0x180089f10  movsxd  rax, ebx
0x180089f13  mov     ecx, 8
0x180089f18  movsxd  rdx, ds:rva ?GlobalCase@SlowSource@Policy@Binary@@2V?$StripedCategory@H$03@Data@@B[rdx+rax*4]; Data::StripedCategory<int,4> const Binary::Policy::SlowSource::GlobalCase ...
0x180089f20  xor     eax, eax
0x180089f22  add     esi, edx
0x180089f24  sub     ecx, edx
0x180089f26  mov     [rsp+108h+var_E4], esi
0x180089f2a  movsxd  r9, ecx
0x180089f2d  test    ecx, ecx
0x180089f2f  jle     short loc_180089F61
0x180089f31  lea     r8, [rdx+rdx]
0x180089f35  nop     word ptr [rax+rax+00000000h]
0x180089f40  lea     rcx, [r8+rax*2]
0x180089f44  movzx   edx, word ptr [rsp+rcx+108h+var_60]
0x180089f4c  mov     word ptr [rsp+rax*2+108h+var_60], dx
0x180089f54  inc     rax
0x180089f57  cmp     rax, r9
0x180089f5a  jl      short loc_180089F40
0x180089f5c  mov     r8, [rsp+108h+var_D8]
0x180089f61  cmp     r9, 8
0x180089f65  jge     loc_18008A09F
0x180089f6b  mov     rdx, [rdi+30h]
0x180089f6f  lea     r10, [rsp+108h+var_60]
0x180089f77  mov     rbp, [rdi+28h]
0x180089f7b  mov     r11d, 8
0x180089f81  mov     r14, [rdi+20h]
0x180089f85  sub     rbp, rdx
0x180089f88  mov     r15, [rdi+18h]
0x180089f8c  sub     r14, rdx
0x180089f8f  mov     r12, [rdi+10h]
0x180089f93  sub     r15, rdx
0x180089f96  mov     r13, [rdi+8]
0x180089f9a  sub     r12, rdx
0x180089f9d  mov     rbx, [rsp+108h+var_C8]
0x180089fa2  sub     r13, rdx
0x180089fa5  movsxd  rcx, esi
0x180089fa8  mov     rsi, [rdi+38h]
0x180089fac  sub     rsi, rdx
0x180089faf  lea     rax, [r9+rcx]
0x180089fb3  lea     r8, [rdx+rax*2]
0x180089fb7  mov     rax, [rdi]
0x180089fba  mov     rdi, [rsp+108h+var_D0]
0x180089fbf  sub     rax, rdx
0x180089fc2  mov     [rsp+108h+var_80], rax
0x180089fca  lea     rax, [rcx+rcx]
0x180089fce  sub     r10, rax
0x180089fd1  sub     r10, rdx
0x180089fd4  sub     r11, r9
0x180089fd7  mov     r9, [rsp+108h+var_80]
0x180089fdf  nop
0x180089fe0  mov     rax, [rsp+108h+var_C0]
0x180089fe5  movzx   edx, word ptr [r8+r9]
0x180089fea  movzx   ecx, word ptr [r8+r13]
0x180089fef  lea     r8, [r8+2]
0x180089ff3  movzx   eax, word ptr [rax]
0x180089ff6  imul    edx, eax
0x180089ff9  mov     rax, [rsp+108h+var_B8]
0x180089ffe  movzx   eax, word ptr [rax]
0x18008a001  imul    ecx, eax
0x18008a004  mov     rax, [rsp+108h+var_B0]
0x18008a009  movzx   eax, word ptr [rax]
0x18008a00c  add     dx, cx
0x18008a00f  movzx   ecx, word ptr [r8+r12-2]
0x18008a015  imul    ecx, eax
0x18008a018  mov     rax, [rsp+108h+var_A8]
0x18008a01d  movzx   eax, word ptr [rax]
0x18008a020  add     dx, cx
0x18008a023  movzx   ecx, word ptr [r8+r15-2]
0x18008a029  imul    ecx, eax
0x18008a02c  mov     rax, [rsp+108h+var_A0]
0x18008a031  movzx   eax, word ptr [rax]
0x18008a034  add     dx, cx
0x18008a037  movzx   ecx, word ptr [r8+r14-2]
0x18008a03d  imul    ecx, eax
0x18008a040  mov     rax, [rsp+108h+var_98]
0x18008a045  movzx   eax, word ptr [rax]
0x18008a048  add     dx, cx
0x18008a04b  movzx   ecx, word ptr [r8+rbp-2]
0x18008a051  imul    ecx, eax
0x18008a054  movzx   eax, word ptr [rdi]
0x18008a057  add     dx, cx
0x18008a05a  movzx   ecx, word ptr [r8+rsi-2]
0x18008a060  imul    ecx, eax
0x18008a063  movzx   eax, word ptr [r8-2]
0x18008a068  add     dx, cx
0x18008a06b  movzx   ecx, word ptr [rbx]
0x18008a06e  imul    ecx, eax
0x18008a071  add     dx, cx
0x18008a074  shr     dx, 6
0x18008a078  mov     [r8+r10-2], dx
0x18008a07e  sub     r11, 1
0x18008a082  jnz     loc_180089FE0
0x18008a088  mov     ebx, [rsp+108h+var_E8]
0x18008a08c  mov     rdi, [rsp+108h+var_90]
0x18008a091  mov     esi, [rsp+108h+var_E4]
0x18008a095  mov     r8, [rsp+108h+var_D8]
0x18008a09a  mov     r10, [rsp+108h+var_E0]
0x18008a09f  lea     eax, [rbx+1]
0x18008a0a2  xor     ebx, ebx
0x18008a0a4  cmp     eax, 4
0x18008a0a7  lea     rcx, cs:180000000h
0x18008a0ae  cmovl   ebx, eax
0x18008a0b1  inc     r8d
0x18008a0b4  movsxd  rax, ebx
0x18008a0b7  shl     rax, 6
0x18008a0bb  mov     [rsp+108h+var_E8], ebx
0x18008a0bf  mov     [rsp+108h+var_D8], r8
0x18008a0c4  vmovdqu xmm0, xmmword ptr [rax+rcx+0DE480h]
0x18008a0cd  vpmullw xmm2, xmm0, [rsp+108h+var_60]
0x18008a0d6  mov     rax, [rsp+108h+var_68]
0x18008a0de  vpsrldq xmm1, xmm2, 8
0x18008a0e3  vpaddw  xmm3, xmm2, xmm1
0x18008a0e7  vpsrldq xmm0, xmm3, 4
0x18008a0ec  vpaddw  xmm1, xmm3, xmm0
0x18008a0f0  vpsrldq xmm0, xmm1, 2
0x18008a0f5  vpaddw  xmm1, xmm1, xmm0
0x18008a0f9  vmovd   edx, xmm1
0x18008a0fd  shr     dx, 8
0x18008a101  mov     [r10+rax], dl
0x18008a105  inc     r10
0x18008a108  mov     rax, [rsp+108h+var_88]
0x18008a110  lea     rdx, cs:180000000h
0x18008a117  mov     [rsp+108h+var_E0], r10
0x18008a11c  cmp     r8d, [rax+0Ch]
0x18008a120  jl      loc_180089F10
0x18008a126  mov     rcx, [rsp+108h+var_78]
0x18008a12e  lea     rdx, [rsp+108h+var_70]
0x18008a136  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008a13b  mov     rcx, [rsp+108h+var_48]
0x18008a143  xor     rcx, rsp; StackCookie
0x18008a146  call    __security_check_cookie
0x18008a14b  mov     rbx, [rsp+108h+arg_0]
0x18008a153  add     rsp, 0D0h
0x18008a15a  pop     r15
0x18008a15c  pop     r14
0x18008a15e  pop     r13
0x18008a160  pop     r12
0x18008a162  pop     rdi
0x18008a163  pop     rsi
0x18008a164  pop     rbp
0x18008a165  retn
```
