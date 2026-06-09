# Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,8,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180099540`
- end: `0x180099bae`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$07$01$00$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$01$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1646`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180099c30`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x180067110`
- `0x1800963a0`
- `0x180099540`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,8,2,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int64 _R9)
{
  __int64 v12; // rsi
  unsigned __int8 *v13; // rcx
  unsigned __int8 *v14; // rax
  unsigned __int8 *v15; // rdx
  int v16; // r14d
  unsigned __int8 *v17; // rbx
  int v18; // eax
  __int64 v20; // r12
  int v22; // r11d
  int v23; // edi
  int v24; // r15d
  int v26; // ecx
  unsigned __int8 *v27; // r13
  int v28; // r10d
  __int64 v29; // r8
  int v30; // eax
  int v32; // r10d
  int v33; // r9d
  int v34; // eax
  __int64 v35; // rcx
  int v36; // r14d
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r9
  __int64 v41; // rcx
  __int64 v42; // r12
  __int64 v43; // rbx
  __int64 v44; // rdi
  int v52; // eax
  __int64 v55; // r11
  __int64 v97; // rdx
  __int64 v129; // rdi
  __int64 v130; // rbx
  unsigned __int8 *v131; // r13
  __int64 v132; // r14
  __int64 v140; // rax
  int v153; // [rsp+58h] [rbp+0h] BYREF
  char v154; // [rsp+9A0h] [rbp+948h] BYREF

  _RBP = (unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL;
  __asm { vmovups xmm0, xmmword ptr [r9] }
  *(_QWORD *)(_RBP + 24) = a3;
  *(_QWORD *)(_RBP + 16) = a1;
  v12 = a1;
  __asm { vmovups xmmword ptr [rbp+980h+var_950], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 608,
    2,
    1,
    a3,
    (_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 48),
    (_DWORD *)(a1 + 8));
  v13 = a2[1];
  v14 = a2[2];
  v15 = a2[3];
  v16 = 0;
  if ( *a2 <= v13 )
    v13 = *a2;
  if ( v13 <= v14 )
    v14 = v13;
  if ( v14 <= v15 )
    v15 = v14;
  v17 = &v15[*(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x268)];
  *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = v17;
  *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = v17 + 2;
  *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v17 + 4;
  *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = v17 + 6;
  LOBYTE(v18) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)(_RBP + 624),
                  v15,
                  (unsigned __int8 **)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 32),
                  (unsigned __int8 **)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 48));
  if ( (_BYTE)v18 )
  {
    v20 = 0;
    *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 2;
    *(_DWORD *)_RBP = 0;
    if ( *(int *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x260) > 0 )
    {
      __asm { vmovss  xmm14, cs:__real@447fc000 }
      v22 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x874);
      v23 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x290);
      v24 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x264);
      __asm { vxorps  xmm15, xmm15, xmm15 }
      do
      {
        *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x290) = ++v23;
        if ( v23 == 1 )
        {
          v26 = *(_DWORD *)(v12 + 40);
          v27 = &v17[v20];
          v28 = *(_DWORD *)(v12 + 28);
          v29 = *(int *)(v12 + 52);
          if ( *(int *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x294) <= 0 )
            v16 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x294);
          v30 = *(_DWORD *)(v12 + 44);
          __asm { vmovups ymm0, [rbp+980h+var_938] }
          if ( v28 < v30 )
            v28 = *(_DWORD *)(v12 + 44);
          v32 = v28 - v30;
          v33 = v29 - 1;
          v34 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x298);
          __asm { vmovups [rbp+980h+var_918], ymm0 }
          if ( v34 < v26 )
            v34 = v26;
          v35 = v29 * ((v34 - v26) % *(_DWORD *)(v12 + 48));
          if ( v32 <= v33 )
            v33 = v32;
          v36 = -v16;
          v37 = v33 + v35;
          v38 = *(_QWORD *)(v12 + 56);
          v39 = v20 + *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78);
          *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v39;
          _RSI = (_WORD *)(v38 + 2 * v37);
          v41 = v20 + *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70);
          v42 = *(int *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88C);
          *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v41;
          if ( v42 < 1 )
          {
            v43 = v41;
            do
            {
              if ( v36 >= v24 )
                break;
              v44 = 8 * v36;
              __asm { vzeroupper }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v43 + v44);
              __asm { vmovaps xmm7, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v44 + *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20));
              __asm { vmovaps xmm6, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v27[v44]);
              __asm
              {
                vaddss  xmm1, xmm0, xmm7
                vdivss  xmm0, xmm14, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                vaddss  xmm2, xmm1, xmm6
                vmulss  xmm1, xmm2, xmm0
                vminss  xmm2, xmm14, xmm1
                vmaxss  xmm0, xmm15, xmm2
                vcvttss2si eax, xmm0
              }
              *_RSI++ = _EAX;
              v52 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40 + 4 * v42++);
              v36 += v52;
            }
            while ( v42 < 1 );
            v22 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x874);
            v23 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x290);
            v24 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x264);
            v17 = *(unsigned __int8 **)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48);
            v39 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
          }
          v20 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
          if ( v36 < v24 - 31 )
          {
            _R10 = v27 - v17 - v20;
            _R8 = &v17[8 * v36 + 144 + v20];
            v55 = ((unsigned int)(v24 - 31 - v36 - 1) >> 5) + 1;
            v36 += 32 * v55;
            do
            {
              __asm
              {
                vmovups xmm0, xmmword ptr [r8+r10-90h]
                vinsertf128 ymm7, ymm0, xmmword ptr [r8+r10-10h], 1
                vmovups xmm1, xmmword ptr [r8-80h]
                vinsertf128 ymm10, ymm1, xmmword ptr [r8], 1
                vmovups xmm0, xmmword ptr [r8-70h]
                vinsertf128 ymm12, ymm0, xmmword ptr [r8+10h], 1
                vmovups xmm1, xmmword ptr [r8-60h]
                vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
                vmovups xmm0, xmmword ptr [r8-50h]
                vinsertf128 ymm2, ymm0, xmmword ptr [r8+r10+30h], 1
                vmovups xmm1, xmmword ptr [r8-40h]
                vinsertf128 ymm3, ymm1, xmmword ptr [r8+40h], 1
                vmovups xmm0, xmmword ptr [r8-30h]
                vinsertf128 ymm4, ymm0, xmmword ptr [r8+50h], 1
                vmovups xmm1, xmmword ptr [r8-20h]
                vinsertf128 ymm5, ymm1, xmmword ptr [r8+60h], 1
                vpunpckhwd ymm8, ymm7, ymm2
                vpunpckhwd ymm1, ymm12, ymm4
                vpunpcklwd ymm6, ymm7, ymm2
                vpunpcklwd ymm9, ymm10, ymm3
                vpunpcklwd ymm0, ymm12, ymm4
                vpunpcklwd ymm7, ymm6, ymm0
                vpunpckhwd ymm6, ymm6, ymm0
                vpunpckhwd ymm11, ymm10, ymm3
                vpunpcklwd ymm10, ymm8, ymm1
                vpunpckhwd ymm8, ymm8, ymm1
                vpunpcklwd ymm2, ymm13, ymm5
                vpunpcklwd ymm1, ymm9, ymm2
                vpunpcklwd ymm0, ymm7, ymm1
                vpunpckhwd ymm1, ymm7, ymm1
                vmovdqu [rbp+980h+var_8C0], ymm1
                vmovdqu [rbp+980h+var_8E0], ymm0
                vpunpckhwd ymm2, ymm9, ymm2
                vpunpckhwd ymm4, ymm13, ymm5
                vpunpckhwd ymm1, ymm6, ymm2
                vpunpcklwd ymm0, ymm6, ymm2
                vpunpcklwd ymm3, ymm11, ymm4
                vmovdqu [rbp+980h+var_880], ymm1
                vmovdqu [rbp+980h+var_8A0], ymm0
                vpunpckhwd ymm1, ymm10, ymm3
                vpunpcklwd ymm0, ymm10, ymm3
                vpunpckhwd ymm5, ymm11, ymm4
                vmovdqu [rbp+980h+var_840], ymm1
                vmovdqu [rbp+980h+var_860], ymm0
                vpunpckhwd ymm1, ymm8, ymm5
                vpunpcklwd ymm0, ymm8, ymm5
                vmovdqu [rbp+980h+var_800], ymm1
                vmovdqu [rbp+980h+var_820], ymm0
              }
              _RAX = _RBP + 480;
              v97 = 2;
              _RCX = _RBP + 224;
              do
              {
                _RAX += 96LL;
                __asm
                {
                  vmovdqu ymm0, ymmword ptr [rcx-40h]
                  vmovdqu ymm1, ymmword ptr [rcx-20h]
                }
                _RCX += 128LL;
                __asm
                {
                  vmovdqu ymmword ptr [rax-0A0h], ymm0
                  vmovdqu ymm0, ymmword ptr [rcx-80h]
                  vmovdqu ymmword ptr [rax-60h], ymm0
                  vmovdqu ymmword ptr [rax-80h], ymm1
                }
                --v97;
              }
              while ( v97 );
              __asm
              {
                vmovdqu ymm4, cs:__ymm@7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff
                vpcmpeqw ymm0, ymm4, [rbp+980h+var_7E0]
                vpandn  ymm2, ymm0, [rbp+980h+var_7E0]
                vextracti128 xmm0, ymm2, 1
                vcvtph2ps ymm7, xmm0
                vpcmpeqw ymm0, ymm4, [rbp+980h+var_7C0]
                vpandn  ymm3, ymm0, [rbp+980h+var_7C0]
                vextracti128 xmm0, ymm3, 1
                vcvtph2ps ymm6, xmm0
                vpcmpeqw ymm0, ymm4, [rbp+980h+var_7A0]
                vpandn  ymm5, ymm0, [rbp+980h+var_7A0]
                vcvtph2ps ymm0, xmm3
                vcvtph2ps ymm2, xmm2
                vaddps  ymm1, ymm2, ymm0
                vcvtph2ps ymm0, xmm5
                vaddps  ymm1, ymm1, ymm0
                vmulps  ymm2, ymm1, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
                vminps  ymm3, ymm2, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
                vxorps  xmm9, xmm9, xmm9
                vmaxps  ymm0, ymm3, ymm9
                vcvttps2dq ymm4, ymm0
                vextracti128 xmm1, ymm5, 1
                vcvtph2ps ymm2, xmm1
                vaddps  ymm0, ymm7, ymm6
                vaddps  ymm2, ymm2, ymm0
                vmulps  ymm1, ymm2, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
                vminps  ymm3, ymm1, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
                vmaxps  ymm0, ymm3, ymm9
                vcvttps2dq ymm2, ymm0
                vpackusdw ymm1, ymm4, ymm2
                vpermq  ymm3, ymm1, 0D8h
                vmovdqu ymmword ptr [rsi], ymm3
              }
              _RSI += 16;
              _R8 += 256;
              --v55;
            }
            while ( v55 );
            v22 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x874);
            v23 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x290);
            v24 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x264);
          }
          if ( v36 < v24 )
          {
            v129 = v39 + 8 * v36;
            v130 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) - v39;
            v131 = &v27[-v39];
            v132 = ((unsigned int)(v24 - v36 - 1) >> 1) + 1;
            do
            {
              __asm { vzeroupper }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v130 + v129);
              __asm { vmovaps xmm7, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v129);
              __asm { vmovaps xmm6, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v131[v129]);
              __asm
              {
                vaddss  xmm1, xmm0, xmm7
                vdivss  xmm0, xmm14, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                vaddss  xmm2, xmm1, xmm6
                vmulss  xmm1, xmm2, xmm0
                vminss  xmm2, xmm14, xmm1
                vmaxss  xmm0, xmm15, xmm2
                vcvttss2si eax, xmm0
              }
              v129 += 16;
              *_RSI++ = _EAX;
              --v132;
            }
            while ( v132 );
            v22 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x874);
            v23 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x290);
            v24 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x264);
            v17 = *(unsigned __int8 **)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48);
          }
          v12 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
          v16 = 0;
          v140 = v22++;
          v23 -= *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x29C + 4 * v140);
          if ( v22 >= *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x87C) )
            v22 = 0;
          ++*(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x298);
          *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x874) = v22;
        }
        v20 += **(int **)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
        v18 = *(_DWORD *)_RBP + 1;
        *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = v20;
        *(_DWORD *)_RBP = v18;
      }
      while ( v18 < *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x260) );
    }
  }
  __asm { vzeroupper }
  _R11 = &v154;
  __asm
  {
    vmovaps xmm6, xmmword ptr [r11-18h]
    vmovaps xmm7, xmmword ptr [r11-28h]
    vmovaps xmm8, xmmword ptr [r11-38h]
    vmovaps xmm9, xmmword ptr [r11-48h]
    vmovaps xmm10, xmmword ptr [r11-58h]
    vmovaps xmm11, xmmword ptr [r11-68h]
    vmovaps xmm12, xmmword ptr [r11-78h]
    vmovaps xmm13, xmmword ptr [r11-88h]
    vmovaps xmm14, xmmword ptr [r11-98h]
    vmovaps xmm15, xmmword ptr [r11-0A8h]
  }
  return v18;
}

```

## disassembly

```asm
0x180099540  mov     rax, rsp
0x180099543  push    rbp
0x180099544  push    rbx
0x180099545  push    rsi
0x180099546  push    rdi
0x180099547  push    r12
0x180099549  push    r13
0x18009954b  push    r14
0x18009954d  push    r15
0x18009954f  sub     rsp, 998h
0x180099556  vmovaps xmmword ptr [rax-58h], xmm6
0x18009955b  vmovaps xmmword ptr [rax-68h], xmm7
0x180099560  vmovaps xmmword ptr [rax-78h], xmm8
0x180099565  vmovaps xmmword ptr [rax-88h], xmm9
0x18009956d  vmovaps xmmword ptr [rax-98h], xmm10
0x180099575  vmovaps xmmword ptr [rax-0A8h], xmm11
0x18009957d  vmovaps xmmword ptr [rax-0B8h], xmm12
0x180099585  vmovaps xmmword ptr [rax-0C8h], xmm13
0x18009958d  vmovaps xmmword ptr [rax-0D8h], xmm14
0x180099595  vmovaps xmmword ptr [rax-0E8h], xmm15
0x18009959d  lea     rbp, [rsp+9D0h+var_980]
0x1800995a2  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800995a6  mov     rax, cs:__security_cookie
0x1800995ad  xor     rax, rsp
0x1800995b0  mov     [rbp+980h+var_F0], rax
0x1800995b7  vmovups xmm0, xmmword ptr [r9]
0x1800995bc  lea     rax, [rcx+8]
0x1800995c0  mov     [rbp+980h+var_968], r8
0x1800995c4  mov     [rsp+9D0h+var_9A8], rax
0x1800995c9  mov     rbx, rdx
0x1800995cc  mov     edx, 2
0x1800995d1  mov     [rbp+980h+var_970], rcx
0x1800995d5  mov     rsi, rcx
0x1800995d8  lea     rax, [rbp+980h+var_950]
0x1800995dc  mov     r9, r8
0x1800995df  mov     [rsp+9D0h+var_9B0], rax
0x1800995e4  lea     rcx, [rbp+980h+var_720]
0x1800995eb  lea     r8d, [rdx-1]
0x1800995ef  vmovups xmmword ptr [rbp+980h+var_950], xmm0
0x1800995f4  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x1800995f9  mov     rcx, [rbx+8]
0x1800995fd  lea     r9, [rbp+980h+var_950]; unsigned __int8 **
0x180099601  mov     rax, [rbx+10h]
0x180099605  lea     r8, [rbp+980h+var_960]; unsigned __int8 **
0x180099609  mov     rdx, [rbx+18h]
0x18009960d  xor     r14d, r14d
0x180099610  cmp     [rbx], rcx
0x180099613  cmovbe  rcx, [rbx]
0x180099617  mov     rbx, [rbp+980h+var_718]
0x18009961e  cmp     rcx, rax
0x180099621  cmovbe  rax, rcx
0x180099625  lea     rcx, [rbp+980h+var_710]; this
0x18009962c  cmp     rax, rdx
0x18009962f  cmovbe  rdx, rax; unsigned __int8 *
0x180099633  add     rbx, rdx
0x180099636  mov     qword ptr [rbp+980h+var_938], rbx
0x18009963a  lea     rax, [rbx+2]
0x18009963e  mov     qword ptr [rbp+980h+var_938+8], rax
0x180099642  lea     rax, [rbx+4]
0x180099646  mov     qword ptr [rbp+980h+var_938+10h], rax
0x18009964a  lea     rax, [rbx+6]
0x18009964e  mov     qword ptr [rbp+980h+var_938+18h], rax
0x180099652  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180099657  test    al, al
0x180099659  jz      loc_180099B3F
0x18009965f  mov     r12d, r14d
0x180099662  mov     [rbp+980h+var_978], r14
0x180099666  mov     [rbp+980h+var_940], 2
0x18009966d  mov     [rbp+980h+var_980], r14d
0x180099671  cmp     [rbp+980h+var_720], r14d
0x180099678  jle     loc_180099B3F
0x18009967e  vmovss  xmm14, cs:__real@447fc000
0x180099686  mov     r11d, [rbp+980h+var_10C]
0x18009968d  mov     edi, [rbp+980h+var_6F0]
0x180099693  mov     r15d, [rbp+980h+var_71C]
0x18009969a  vxorps  xmm15, xmm15, xmm15
0x18009969f  nop
0x1800996a0  inc     edi
0x1800996a2  mov     [rbp+980h+var_6F0], edi
0x1800996a8  cmp     edi, 1
0x1800996ab  jnz     loc_180099B1D
0x1800996b1  mov     ecx, [rsi+28h]
0x1800996b4  lea     r13, [rbx+r12]
0x1800996b8  mov     eax, [rbp+980h+var_6EC]
0x1800996be  test    eax, eax
0x1800996c0  mov     r10d, [rsi+1Ch]
0x1800996c4  movsxd  r8, dword ptr [rsi+34h]
0x1800996c8  cmovle  r14d, eax
0x1800996cc  mov     eax, [rsi+2Ch]
0x1800996cf  cmp     r10d, eax
0x1800996d2  vmovups ymm0, [rbp+980h+var_938]
0x1800996d7  cmovl   r10d, eax
0x1800996db  sub     r10d, eax
0x1800996de  lea     r9d, [r8-1]
0x1800996e2  mov     eax, [rbp+980h+var_6E8]
0x1800996e8  cmp     eax, ecx
0x1800996ea  vmovups [rbp+980h+var_918], ymm0
0x1800996ef  cmovl   eax, ecx
0x1800996f2  sub     eax, ecx
0x1800996f4  cdq
0x1800996f5  idiv    dword ptr [rsi+30h]
0x1800996f8  movsxd  rcx, edx
0x1800996fb  imul    rcx, r8
0x1800996ff  cmp     r10d, r9d
0x180099702  cmovle  r9d, r10d
0x180099706  neg     r14d
0x180099709  movsxd  rax, r9d
0x18009970c  mov     r9, qword ptr [rbp+980h+var_918+10h]
0x180099710  add     rcx, rax
0x180099713  mov     rax, [rsi+38h]
0x180099717  add     r9, r12
0x18009971a  mov     [rbp+980h+var_960], r9
0x18009971e  lea     rsi, [rax+rcx*2]
0x180099722  mov     rcx, qword ptr [rbp+980h+var_918+8]
0x180099726  add     rcx, r12
0x180099729  movsxd  r12, [rbp+980h+var_F4]
0x180099730  mov     [rbp+980h+var_950], rcx
0x180099734  cmp     r12, 1
0x180099738  jge     loc_1800997CE
0x18009973e  mov     rbx, rcx
0x180099741  cmp     r14d, r15d
0x180099744  jge     short loc_1800997B2
0x180099746  lea     eax, ds:0[r14*8]
0x18009974e  movsxd  rdi, eax
0x180099751  lea     rcx, [rbx+rdi]
0x180099755  vzeroupper
0x180099758  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009975d  mov     rcx, [rbp+980h+var_960]
0x180099761  add     rcx, rdi
0x180099764  vmovaps xmm7, xmm0
0x180099768  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009976d  lea     rcx, [rdi+r13]
0x180099771  vmovaps xmm6, xmm0
0x180099775  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009977a  vaddss  xmm1, xmm0, xmm7
0x18009977e  vdivss  xmm0, xmm14, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180099786  vaddss  xmm2, xmm1, xmm6
0x18009978a  vmulss  xmm1, xmm2, xmm0
0x18009978e  vminss  xmm2, xmm14, xmm1
0x180099792  vmaxss  xmm0, xmm15, xmm2
0x180099796  vcvttss2si eax, xmm0
0x18009979a  mov     [rsi], ax
0x18009979d  add     rsi, 2
0x1800997a1  mov     eax, [rbp+r12*4+980h+var_940]
0x1800997a6  inc     r12
0x1800997a9  add     r14d, eax
0x1800997ac  cmp     r12, 1
0x1800997b0  jl      short loc_180099741
0x1800997b2  mov     r11d, [rbp+980h+var_10C]
0x1800997b9  mov     edi, [rbp+980h+var_6F0]
0x1800997bf  mov     r15d, [rbp+980h+var_71C]
0x1800997c6  mov     rbx, qword ptr [rbp+980h+var_938]
0x1800997ca  mov     r9, [rbp+980h+var_960]
0x1800997ce  mov     r12, [rbp+980h+var_978]
0x1800997d2  lea     ecx, [r15-1Fh]
0x1800997d6  cmp     r14d, ecx
0x1800997d9  jge     loc_180099A49
0x1800997df  sub     ecx, r14d
0x1800997e2  movsxd  r8, r14d
0x1800997e5  add     r8, 12h
0x1800997e9  mov     r10, r13
0x1800997ec  sub     r10, rbx
0x1800997ef  sub     r10, r12
0x1800997f2  lea     eax, [rcx-1]
0x1800997f5  shr     eax, 5
0x1800997f8  lea     r8, [rbx+r8*8]
0x1800997fc  inc     eax
0x1800997fe  add     r8, r12
0x180099801  mov     r11d, eax
0x180099804  shl     eax, 5
0x180099807  add     r14d, eax
0x18009980a  nop     word ptr [rax+rax+00h]
0x180099810  vmovups xmm0, xmmword ptr [r8+r10-90h]
0x18009981a  vinsertf128 ymm7, ymm0, xmmword ptr [r8+r10-10h], 1
0x180099822  vmovups xmm1, xmmword ptr [r8-80h]
0x180099828  vinsertf128 ymm10, ymm1, xmmword ptr [r8], 1
0x18009982e  vmovups xmm0, xmmword ptr [r8-70h]
0x180099834  vinsertf128 ymm12, ymm0, xmmword ptr [r8+10h], 1
0x18009983b  vmovups xmm1, xmmword ptr [r8-60h]
0x180099841  vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
0x180099848  vmovups xmm0, xmmword ptr [r8-50h]
0x18009984e  vinsertf128 ymm2, ymm0, xmmword ptr [r8+r10+30h], 1
0x180099856  vmovups xmm1, xmmword ptr [r8-40h]
0x18009985c  vinsertf128 ymm3, ymm1, xmmword ptr [r8+40h], 1
0x180099863  vmovups xmm0, xmmword ptr [r8-30h]
0x180099869  vinsertf128 ymm4, ymm0, xmmword ptr [r8+50h], 1
0x180099870  vmovups xmm1, xmmword ptr [r8-20h]
0x180099876  vinsertf128 ymm5, ymm1, xmmword ptr [r8+60h], 1
0x18009987d  vpunpckhwd ymm8, ymm7, ymm2
0x180099881  vpunpckhwd ymm1, ymm12, ymm4
0x180099885  vpunpcklwd ymm6, ymm7, ymm2
0x180099889  vpunpcklwd ymm9, ymm10, ymm3
0x18009988d  vpunpcklwd ymm0, ymm12, ymm4
0x180099891  vpunpcklwd ymm7, ymm6, ymm0
0x180099895  vpunpckhwd ymm6, ymm6, ymm0
0x180099899  vpunpckhwd ymm11, ymm10, ymm3
0x18009989d  vpunpcklwd ymm10, ymm8, ymm1
0x1800998a1  vpunpckhwd ymm8, ymm8, ymm1
0x1800998a5  vpunpcklwd ymm2, ymm13, ymm5
0x1800998a9  vpunpcklwd ymm1, ymm9, ymm2
0x1800998ad  vpunpcklwd ymm0, ymm7, ymm1
0x1800998b1  vpunpckhwd ymm1, ymm7, ymm1
0x1800998b5  vmovdqu [rbp+980h+var_8C0], ymm1
0x1800998bd  vmovdqu [rbp+980h+var_8E0], ymm0
0x1800998c5  vpunpckhwd ymm2, ymm9, ymm2
0x1800998c9  vpunpckhwd ymm4, ymm13, ymm5
0x1800998cd  vpunpckhwd ymm1, ymm6, ymm2
0x1800998d1  vpunpcklwd ymm0, ymm6, ymm2
0x1800998d5  vpunpcklwd ymm3, ymm11, ymm4
0x1800998d9  vmovdqu [rbp+980h+var_880], ymm1
0x1800998e1  vmovdqu [rbp+980h+var_8A0], ymm0
0x1800998e9  vpunpckhwd ymm1, ymm10, ymm3
0x1800998ed  vpunpcklwd ymm0, ymm10, ymm3
0x1800998f1  vpunpckhwd ymm5, ymm11, ymm4
0x1800998f5  vmovdqu [rbp+980h+var_840], ymm1
0x1800998fd  vmovdqu [rbp+980h+var_860], ymm0
0x180099905  vpunpckhwd ymm1, ymm8, ymm5
0x180099909  vpunpcklwd ymm0, ymm8, ymm5
0x18009990d  vmovdqu [rbp+980h+var_800], ymm1
0x180099915  vmovdqu [rbp+980h+var_820], ymm0
0x18009991d  lea     rax, [rbp+980h+var_7A0]
0x180099924  mov     edx, 2
0x180099929  lea     rcx, [rbp+980h+var_8A0]
0x180099930  lea     rax, [rax+60h]
0x180099934  vmovdqu ymm0, ymmword ptr [rcx-40h]
0x180099939  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x18009993e  lea     rcx, [rcx+80h]
0x180099945  vmovdqu ymmword ptr [rax-0A0h], ymm0
0x18009994d  vmovdqu ymm0, ymmword ptr [rcx-80h]
0x180099952  vmovdqu ymmword ptr [rax-60h], ymm0
0x180099957  vmovdqu ymmword ptr [rax-80h], ymm1
0x18009995c  sub     rdx, 1
0x180099960  jnz     short loc_180099930
0x180099962  vmovdqu ymm4, cs:__ymm@7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff
0x18009996a  vpcmpeqw ymm0, ymm4, [rbp+980h+var_7E0]
0x180099972  vpandn  ymm2, ymm0, [rbp+980h+var_7E0]
0x18009997a  vextracti128 xmm0, ymm2, 1
0x180099980  vcvtph2ps ymm7, xmm0
0x180099985  vpcmpeqw ymm0, ymm4, [rbp+980h+var_7C0]
0x18009998d  vpandn  ymm3, ymm0, [rbp+980h+var_7C0]
0x180099995  vextracti128 xmm0, ymm3, 1
0x18009999b  vcvtph2ps ymm6, xmm0
0x1800999a0  vpcmpeqw ymm0, ymm4, [rbp+980h+var_7A0]
0x1800999a8  vpandn  ymm5, ymm0, [rbp+980h+var_7A0]
0x1800999b0  vcvtph2ps ymm0, xmm3
0x1800999b5  vcvtph2ps ymm2, xmm2
0x1800999ba  vaddps  ymm1, ymm2, ymm0
0x1800999be  vcvtph2ps ymm0, xmm5
0x1800999c3  vaddps  ymm1, ymm1, ymm0
0x1800999c7  vmulps  ymm2, ymm1, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
0x1800999cf  vminps  ymm3, ymm2, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
0x1800999d7  vxorps  xmm9, xmm9, xmm9
0x1800999dc  vmaxps  ymm0, ymm3, ymm9
0x1800999e1  vcvttps2dq ymm4, ymm0
0x1800999e5  vextracti128 xmm1, ymm5, 1
0x1800999eb  vcvtph2ps ymm2, xmm1
0x1800999f0  vaddps  ymm0, ymm7, ymm6
0x1800999f4  vaddps  ymm2, ymm2, ymm0
0x1800999f8  vmulps  ymm1, ymm2, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
0x180099a00  vminps  ymm3, ymm1, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
0x180099a08  vmaxps  ymm0, ymm3, ymm9
0x180099a0d  vcvttps2dq ymm2, ymm0
0x180099a11  vpackusdw ymm1, ymm4, ymm2
0x180099a16  vpermq  ymm3, ymm1, 0D8h
0x180099a1c  vmovdqu ymmword ptr [rsi], ymm3
0x180099a20  add     rsi, 20h ; ' '
0x180099a24  add     r8, 100h
0x180099a2b  sub     r11, 1
0x180099a2f  jnz     loc_180099810
0x180099a35  mov     r11d, [rbp+980h+var_10C]
0x180099a3c  mov     edi, [rbp+980h+var_6F0]
0x180099a42  mov     r15d, [rbp+980h+var_71C]
0x180099a49  cmp     r14d, r15d
0x180099a4c  jge     loc_180099AEE
0x180099a52  mov     rbx, [rbp+980h+var_950]
0x180099a56  lea     eax, ds:0[r14*8]
0x180099a5e  sub     r15d, r14d
0x180099a61  movsxd  rdi, eax
0x180099a64  add     rdi, r9
0x180099a67  sub     rbx, r9
0x180099a6a  sub     r13, r9
0x180099a6d  lea     r14d, [r15-1]
0x180099a71  shr     r14d, 1
0x180099a74  inc     r14d
0x180099a77  nop     word ptr [rax+rax+00000000h]
0x180099a80  lea     rcx, [rbx+rdi]
0x180099a84  vzeroupper
0x180099a87  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180099a8c  mov     rcx, rdi
0x180099a8f  vmovaps xmm7, xmm0
0x180099a93  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180099a98  lea     rcx, [rdi+r13]
0x180099a9c  vmovaps xmm6, xmm0
0x180099aa0  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180099aa5  vaddss  xmm1, xmm0, xmm7
0x180099aa9  vdivss  xmm0, xmm14, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180099ab1  vaddss  xmm2, xmm1, xmm6
0x180099ab5  vmulss  xmm1, xmm2, xmm0
0x180099ab9  vminss  xmm2, xmm14, xmm1
0x180099abd  vmaxss  xmm0, xmm15, xmm2
  ... truncated ...
```
