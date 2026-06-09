# Binary::IntegratedSelection::DerivativeServer<8,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,8,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180098460`
- end: `0x180098c22`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$07$00$00$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$00$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1986`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180099c20`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x180067110`
- `0x1800963a0`
- `0x180098460`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,8,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int64 _R9)
{
  __int64 v10; // rsi
  unsigned __int8 *v11; // rcx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rdx
  int v14; // r14d
  unsigned __int8 *v15; // rbx
  int v16; // eax
  __int64 v17; // r15
  int v19; // r11d
  int v20; // edi
  int v21; // r13d
  int v22; // ecx
  unsigned __int8 *v23; // r12
  int v24; // r10d
  __int64 v25; // r8
  int v26; // eax
  int v28; // r10d
  int v29; // r9d
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // r10
  int v33; // r14d
  __int64 v35; // rcx
  __int64 v36; // r15
  __int64 v37; // rbx
  __int64 v38; // rdi
  int v46; // eax
  __int64 v50; // r9
  __int64 v99; // rdx
  unsigned __int64 v104; // rcx
  __int64 v105; // rdx
  __int64 v149; // rdx
  __int64 v155; // rbx
  __int64 v156; // rdi
  unsigned __int8 *v157; // r12
  __int64 v158; // r14
  __int64 v166; // rax
  int v179; // [rsp+58h] [rbp+0h] BYREF
  char v180; // [rsp+BD0h] [rbp+B78h] BYREF

  _RBP = (unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL;
  __asm { vmovups xmm0, xmmword ptr [r9] }
  *(_QWORD *)(_RBP + 24) = a3;
  *(_QWORD *)(_RBP + 16) = a1;
  v10 = a1;
  __asm { vmovups xmmword ptr [rbp+0BB0h+var_B80], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 960,
    1,
    1,
    a3,
    (_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 48),
    (_DWORD *)(a1 + 8));
  v11 = a2[1];
  v12 = a2[2];
  v13 = a2[3];
  v14 = 0;
  if ( *a2 <= v11 )
    v11 = *a2;
  if ( v11 <= v12 )
    v12 = v11;
  if ( v12 <= v13 )
    v13 = v12;
  v15 = &v13[*(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C8)];
  *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = v15;
  *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = v15 + 2;
  *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v15 + 4;
  *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = v15 + 6;
  LOBYTE(v16) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)(_RBP + 976),
                  v13,
                  (unsigned __int8 **)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 32),
                  (unsigned __int8 **)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 48));
  if ( (_BYTE)v16 )
  {
    v17 = 0;
    *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 1;
    *(_DWORD *)_RBP = 0;
    if ( *(int *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C0) > 0 )
    {
      __asm { vmovss  xmm15, cs:__real@447fc000 }
      v19 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9D4);
      v20 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F0);
      v21 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C4);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F0) = ++v20;
        if ( v20 == 1 )
        {
          v22 = *(_DWORD *)(v10 + 40);
          v23 = &v15[v17];
          v24 = *(_DWORD *)(v10 + 28);
          v25 = *(int *)(v10 + 52);
          if ( *(int *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F4) <= 0 )
            v14 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F4);
          v26 = *(_DWORD *)(v10 + 44);
          __asm { vmovups ymm0, [rbp+0BB0h+var_B68] }
          if ( v24 < v26 )
            v24 = *(_DWORD *)(v10 + 44);
          v28 = v24 - v26;
          v29 = v25 - 1;
          v30 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F8);
          __asm { vmovups [rbp+0BB0h+var_B30], ymm0 }
          if ( v30 < v22 )
            v30 = v22;
          v31 = v25 * ((v30 - v22) % *(_DWORD *)(v10 + 48));
          if ( v28 <= v29 )
            v29 = v28;
          v32 = v17 + *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90);
          *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v32;
          v33 = -v14;
          _RSI = (_WORD *)(*(_QWORD *)(v10 + 56) + 2 * (v29 + v31));
          v35 = v17 + *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          v36 = *(int *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9EC);
          *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v35;
          if ( v36 < 1 )
          {
            v37 = v35;
            do
            {
              if ( v33 >= v21 )
                break;
              v38 = 8 * v33;
              __asm { vzeroupper }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v37 + v38);
              __asm { vmovaps xmm7, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v38 + *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20));
              __asm { vmovaps xmm6, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v23[v38]);
              __asm
              {
                vaddss  xmm1, xmm0, xmm7
                vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                vaddss  xmm2, xmm1, xmm6
                vmulss  xmm1, xmm2, xmm0
                vminss  xmm2, xmm15, xmm1
                vxorps  xmm0, xmm0, xmm0
                vmaxss  xmm0, xmm0, xmm2
                vcvttss2si eax, xmm0
              }
              *_RSI++ = _EAX;
              v46 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40 + 4 * v36++);
              v33 += v46;
            }
            while ( v36 < 1 );
            v19 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9D4);
            v20 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F0);
            v21 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C4);
            v15 = *(unsigned __int8 **)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48);
            v32 = *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
          }
          v17 = *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
          if ( v33 < v21 - 31 )
          {
            __asm { vmovdqu ymm14, cs:__ymm@7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff }
            _R11 = v23 - v15 - v17;
            _R8 = &v15[8 * v33 + 80 + v17];
            v50 = ((unsigned int)(v21 - 31 - v33 - 1) >> 5) + 1;
            v33 += 32 * v50;
            do
            {
              __asm
              {
                vmovups xmm0, xmmword ptr [r8+r11-50h]
                vinsertf128 ymm7, ymm0, xmmword ptr [r8-10h], 1
                vmovups xmm1, xmmword ptr [r8-40h]
                vinsertf128 ymm9, ymm1, xmmword ptr [r8], 1
                vmovups xmm0, xmmword ptr [r8-30h]
                vinsertf128 ymm11, ymm0, xmmword ptr [r8+10h], 1
                vmovups xmm1, xmmword ptr [r8-20h]
                vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
                vmovups xmm0, xmmword ptr [r8+30h]
                vinsertf128 ymm2, ymm0, xmmword ptr [r8+70h], 1
                vmovups xmm1, xmmword ptr [r8+40h]
                vinsertf128 ymm3, ymm1, xmmword ptr [r8+80h], 1
                vmovups xmm0, xmmword ptr [r8+50h]
                vinsertf128 ymm4, ymm0, xmmword ptr [r8+90h], 1
                vmovups xmm1, xmmword ptr [r8+60h]
                vinsertf128 ymm5, ymm1, xmmword ptr [r8+0A0h], 1
                vpunpckhwd ymm8, ymm7, ymm2
                vpunpcklwd ymm0, ymm11, ymm4
                vpunpcklwd ymm6, ymm7, ymm2
                vpunpcklwd ymm7, ymm6, ymm0
                vpunpcklwd ymm10, ymm9, ymm3
                vpunpckhwd ymm1, ymm11, ymm4
                vpunpcklwd ymm11, ymm8, ymm1
                vpunpcklwd ymm2, ymm13, ymm5
                vpunpckhwd ymm12, ymm9, ymm3
                vpunpckhwd ymm9, ymm6, ymm0
                vpunpckhwd ymm4, ymm13, ymm5
                vpunpckhwd ymm13, ymm8, ymm1
                vpunpckhwd ymm1, ymm10, ymm2
                vpunpcklwd ymm8, ymm9, ymm1
                vpunpckhwd ymm9, ymm9, ymm1
                vpunpcklwd ymm0, ymm10, ymm2
                vpunpcklwd ymm6, ymm7, ymm0
                vpunpckhwd ymm7, ymm7, ymm0
                vpunpcklwd ymm3, ymm12, ymm4
                vpunpcklwd ymm1, ymm11, ymm3
                vpunpcklwd ymm0, ymm6, ymm1
                vpunpckhwd ymm1, ymm6, ymm1
                vpunpckhwd ymm2, ymm11, ymm3
                vmovdqu [rbp+0BB0h+var_9F0], ymm1
                vmovdqu [rbp+0BB0h+var_A70], ymm0
                vpunpckhwd ymm5, ymm12, ymm4
                vpunpckhwd ymm1, ymm7, ymm2
                vpunpcklwd ymm0, ymm7, ymm2
                vpunpcklwd ymm4, ymm13, ymm5
                vmovdqu [rbp+0BB0h+var_9D0], ymm1
                vmovdqu [rbp+0BB0h+var_A50], ymm0
                vpunpckhwd ymm1, ymm8, ymm4
                vpunpcklwd ymm0, ymm8, ymm4
                vpunpckhwd ymm3, ymm13, ymm5
                vmovdqu [rbp+0BB0h+var_9B0], ymm1
                vmovdqu [rbp+0BB0h+var_A30], ymm0
                vpunpckhwd ymm1, ymm9, ymm3
                vpunpcklwd ymm0, ymm9, ymm3
                vmovdqu [rbp+0BB0h+var_990], ymm1
                vmovdqu [rbp+0BB0h+var_A10], ymm0
              }
              _RAX = _RBP + 2624;
              v99 = 2;
              _RCX = _RBP + 384;
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
                --v99;
              }
              while ( v99 );
              v104 = _RBP + 2624;
              v105 = 2;
              _RAX = _RBP + 608;
              do
              {
                _RAX += 192LL;
                __asm
                {
                  vpcmpeqw ymm0, ymm14, ymmword ptr [rcx-40h]
                  vpandn  ymm2, ymm0, ymmword ptr [rcx-40h]
                }
                v104 += 96LL;
                __asm
                {
                  vcvtph2ps ymm0, xmm2
                  vmovups ymmword ptr [rax-0E0h], ymm0
                  vpcmpeqw ymm0, ymm14, ymmword ptr [rcx-80h]
                  vextracti128 xmm1, ymm2, 1
                  vcvtph2ps ymm2, xmm1
                  vpandn  ymm1, ymm0, ymmword ptr [rcx-80h]
                  vcvtph2ps ymm0, xmm1
                  vmovups ymmword ptr [rax-0C0h], ymm0
                  vpcmpeqw ymm0, ymm14, ymmword ptr [rcx-60h]
                  vextracti128 xmm1, ymm1, 1
                  vmovups ymmword ptr [rax-80h], ymm2
                  vcvtph2ps ymm2, xmm1
                  vpandn  ymm1, ymm0, ymmword ptr [rcx-60h]
                  vcvtph2ps ymm0, xmm1
                  vmovups ymmword ptr [rax-60h], ymm2
                  vextracti128 xmm1, ymm1, 1
                  vcvtph2ps ymm2, xmm1
                  vmovups ymmword ptr [rax-40h], ymm2
                  vmovups ymmword ptr [rax-0A0h], ymm0
                }
                --v105;
              }
              while ( v105 );
              __asm
              {
                vmovups ymm6, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
                vmovups ymm8, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
                vmovups ymm0, [rbp+0BB0h+var_970]
                vaddps  ymm1, ymm0, [rbp+0BB0h+var_950]
                vaddps  ymm2, ymm1, [rbp+0BB0h+var_930]
                vmovups ymm0, [rbp+0BB0h+var_910]
                vaddps  ymm1, ymm0, [rbp+0BB0h+var_8F0]
                vaddps  ymm5, ymm1, [rbp+0BB0h+var_8D0]
                vmovups ymm0, [rbp+0BB0h+var_8B0]
                vaddps  ymm1, ymm0, [rbp+0BB0h+var_890]
                vaddps  ymm4, ymm1, [rbp+0BB0h+var_870]
                vmovups ymm0, [rbp+0BB0h+var_850]
                vaddps  ymm1, ymm0, [rbp+0BB0h+var_830]
                vaddps  ymm3, ymm1, [rbp+0BB0h+var_810]
                vmulps  ymm0, ymm6, ymm2
                vminps  ymm1, ymm0, ymm8
                vxorps  xmm7, xmm7, xmm7
                vmaxps  ymm2, ymm1, ymm7
                vmovups [rbp+0BB0h+var_AF0], ymm2
                vmulps  ymm0, ymm6, ymm5
                vminps  ymm1, ymm0, ymm8
                vmaxps  ymm2, ymm1, ymm7
                vmulps  ymm0, ymm6, ymm4
                vminps  ymm1, ymm0, ymm8
                vmovups [rbp+0BB0h+var_AD0], ymm2
                vmaxps  ymm2, ymm1, ymm7
                vmulps  ymm0, ymm6, ymm3
                vminps  ymm1, ymm0, ymm8
                vmovups [rbp+0BB0h+var_AB0], ymm2
                vmaxps  ymm2, ymm1, ymm7
                vmovups [rbp+0BB0h+var_A90], ymm2
              }
              _RCX = _RBP + 128;
              v149 = 2;
              _RAX = _RBP + 192;
              do
              {
                _RCX += 32LL;
                __asm
                {
                  vcvttps2dq ymm1, ymmword ptr [rax+20h]
                  vcvttps2dq ymm0, ymmword ptr [rax]
                }
                _RAX += 64LL;
                __asm
                {
                  vpackusdw ymm1, ymm0, ymm1
                  vpermq  ymm2, ymm1, 0D8h
                  vmovdqu ymmword ptr [rcx-20h], ymm2
                }
                --v149;
              }
              while ( v149 );
              __asm
              {
                vmovdqu ymm0, [rbp+0BB0h+var_B30]
                vmovdqu ymm1, [rbp+0BB0h+var_B10]
                vmovdqu ymmword ptr [rsi], ymm0
                vmovdqu ymmword ptr [rsi+20h], ymm1
              }
              _RSI += 32;
              _R8 += 256;
              --v50;
            }
            while ( v50 );
            v19 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9D4);
            v20 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F0);
            v21 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C4);
          }
          if ( v33 < v21 )
          {
            v155 = *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) - v32;
            v156 = v32 + 8 * v33;
            v157 = &v23[-v32];
            v158 = (unsigned int)(v21 - v33);
            do
            {
              __asm { vzeroupper }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v155 + v156);
              __asm { vmovaps xmm7, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v156);
              __asm { vmovaps xmm6, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v157[v156]);
              __asm
              {
                vaddss  xmm1, xmm0, xmm7
                vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                vaddss  xmm2, xmm1, xmm6
                vmulss  xmm1, xmm2, xmm0
                vminss  xmm2, xmm15, xmm1
                vxorps  xmm0, xmm0, xmm0
                vmaxss  xmm0, xmm0, xmm2
                vcvttss2si eax, xmm0
              }
              v156 += 8;
              *_RSI++ = _EAX;
              --v158;
            }
            while ( v158 );
            v19 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9D4);
            v20 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F0);
            v21 = *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C4);
            v15 = *(unsigned __int8 **)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48);
          }
          v10 = *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
          v14 = 0;
          v166 = v19++;
          v20 -= *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3FC + 4 * v166);
          if ( v19 >= *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9DC) )
            v19 = 0;
          ++*(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3F8);
          *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x9D4) = v19;
        }
        v17 += **(int **)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
        v16 = *(_DWORD *)_RBP + 1;
        *(_QWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = v17;
        *(_DWORD *)_RBP = v16;
      }
      while ( v16 < *(_DWORD *)(((unsigned __int64)&v179 & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C0) );
    }
  }
  __asm { vzeroupper }
  _R11 = &v180;
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
  return v16;
}

```

## disassembly

```asm
0x180098460  mov     rax, rsp
0x180098463  push    rbp
0x180098464  push    rbx
0x180098465  push    rsi
0x180098466  push    rdi
0x180098467  push    r12
0x180098469  push    r13
0x18009846b  push    r14
0x18009846d  push    r15
0x18009846f  sub     rsp, 0BC8h
0x180098476  vmovaps xmmword ptr [rax-58h], xmm6
0x18009847b  vmovaps xmmword ptr [rax-68h], xmm7
0x180098480  vmovaps xmmword ptr [rax-78h], xmm8
0x180098485  vmovaps xmmword ptr [rax-88h], xmm9
0x18009848d  vmovaps xmmword ptr [rax-98h], xmm10
0x180098495  vmovaps xmmword ptr [rax-0A8h], xmm11
0x18009849d  vmovaps xmmword ptr [rax-0B8h], xmm12
0x1800984a5  vmovaps xmmword ptr [rax-0C8h], xmm13
0x1800984ad  vmovaps xmmword ptr [rax-0D8h], xmm14
0x1800984b5  vmovaps xmmword ptr [rax-0E8h], xmm15
0x1800984bd  lea     rbp, [rsp+0C00h+var_BB0]
0x1800984c2  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800984c6  mov     rax, cs:__security_cookie
0x1800984cd  xor     rax, rsp
0x1800984d0  mov     [rbp+0BB0h+var_F0], rax
0x1800984d7  vmovups xmm0, xmmword ptr [r9]
0x1800984dc  lea     rax, [rcx+8]
0x1800984e0  mov     [rbp+0BB0h+var_B98], r8
0x1800984e4  mov     [rsp+0C00h+var_BD8], rax
0x1800984e9  mov     rbx, rdx
0x1800984ec  mov     edx, 1
0x1800984f1  mov     [rbp+0BB0h+var_BA0], rcx
0x1800984f5  lea     rax, [rbp+0BB0h+var_B80]
0x1800984f9  mov     rsi, rcx
0x1800984fc  mov     r9, r8
0x1800984ff  mov     [rsp+0C00h+var_BE0], rax
0x180098504  mov     r8d, edx
0x180098507  lea     rcx, [rbp+0BB0h+var_7F0]
0x18009850e  vmovups xmmword ptr [rbp+0BB0h+var_B80], xmm0
0x180098513  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180098518  mov     rcx, [rbx+8]
0x18009851c  lea     r9, [rbp+0BB0h+var_B80]; unsigned __int8 **
0x180098520  mov     rax, [rbx+10h]
0x180098524  lea     r8, [rbp+0BB0h+var_B90]; unsigned __int8 **
0x180098528  mov     rdx, [rbx+18h]
0x18009852c  xor     r14d, r14d
0x18009852f  cmp     [rbx], rcx
0x180098532  cmovbe  rcx, [rbx]
0x180098536  mov     rbx, [rbp+0BB0h+var_7E8]
0x18009853d  cmp     rcx, rax
0x180098540  cmovbe  rax, rcx
0x180098544  lea     rcx, [rbp+0BB0h+var_7E0]; this
0x18009854b  cmp     rax, rdx
0x18009854e  cmovbe  rdx, rax; unsigned __int8 *
0x180098552  add     rbx, rdx
0x180098555  mov     qword ptr [rbp+0BB0h+var_B68], rbx
0x180098559  lea     rax, [rbx+2]
0x18009855d  mov     qword ptr [rbp+0BB0h+var_B68+8], rax
0x180098561  lea     rax, [rbx+4]
0x180098565  mov     qword ptr [rbp+0BB0h+var_B68+10h], rax
0x180098569  lea     rax, [rbx+6]
0x18009856d  mov     qword ptr [rbp+0BB0h+var_B68+18h], rax
0x180098571  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180098576  test    al, al
0x180098578  jz      loc_180098BB3
0x18009857e  mov     r15d, r14d
0x180098581  mov     [rbp+0BB0h+var_BA8], r14
0x180098585  mov     [rbp+0BB0h+var_B70], 1
0x18009858c  mov     [rbp+0BB0h+var_BB0], r14d
0x180098590  cmp     [rbp+0BB0h+var_7F0], r14d
0x180098597  jle     loc_180098BB3
0x18009859d  vmovss  xmm15, cs:__real@447fc000
0x1800985a5  mov     r11d, [rbp+0BB0h+var_1DC]
0x1800985ac  mov     edi, [rbp+0BB0h+var_7C0]
0x1800985b2  mov     r13d, [rbp+0BB0h+var_7EC]
0x1800985b9  nop     dword ptr [rax+00000000h]
0x1800985c0  inc     edi
0x1800985c2  mov     [rbp+0BB0h+var_7C0], edi
0x1800985c8  cmp     edi, 1
0x1800985cb  jnz     loc_180098B91
0x1800985d1  mov     ecx, [rsi+28h]
0x1800985d4  lea     r12, [rbx+r15]
0x1800985d8  mov     eax, [rbp+0BB0h+var_7BC]
0x1800985de  test    eax, eax
0x1800985e0  mov     r10d, [rsi+1Ch]
0x1800985e4  movsxd  r8, dword ptr [rsi+34h]
0x1800985e8  cmovle  r14d, eax
0x1800985ec  mov     eax, [rsi+2Ch]
0x1800985ef  cmp     r10d, eax
0x1800985f2  vmovups ymm0, [rbp+0BB0h+var_B68]
0x1800985f7  cmovl   r10d, eax
0x1800985fb  sub     r10d, eax
0x1800985fe  lea     r9d, [r8-1]
0x180098602  mov     eax, [rbp+0BB0h+var_7B8]
0x180098608  cmp     eax, ecx
0x18009860a  vmovups [rbp+0BB0h+var_B30], ymm0
0x180098612  cmovl   eax, ecx
0x180098615  sub     eax, ecx
0x180098617  cdq
0x180098618  idiv    dword ptr [rsi+30h]
0x18009861b  movsxd  rcx, edx
0x18009861e  imul    rcx, r8
0x180098622  cmp     r10d, r9d
0x180098625  cmovle  r9d, r10d
0x180098629  mov     r10, qword ptr [rbp+0BB0h+var_B30+10h]
0x180098630  add     r10, r15
0x180098633  movsxd  rax, r9d
0x180098636  add     rcx, rax
0x180098639  mov     [rbp+0BB0h+var_B90], r10
0x18009863d  mov     rax, [rsi+38h]
0x180098641  neg     r14d
0x180098644  lea     rsi, [rax+rcx*2]
0x180098648  mov     rcx, qword ptr [rbp+0BB0h+var_B30+8]
0x18009864f  add     rcx, r15
0x180098652  movsxd  r15, [rbp+0BB0h+var_1C4]
0x180098659  mov     [rbp+0BB0h+var_B80], rcx
0x18009865d  cmp     r15, 1
0x180098661  jge     loc_180098701
0x180098667  mov     rbx, rcx
0x18009866a  nop     word ptr [rax+rax+00h]
0x180098670  cmp     r14d, r13d
0x180098673  jge     short loc_1800986E5
0x180098675  lea     eax, ds:0[r14*8]
0x18009867d  movsxd  rdi, eax
0x180098680  lea     rcx, [rbx+rdi]
0x180098684  vzeroupper
0x180098687  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009868c  mov     rcx, [rbp+0BB0h+var_B90]
0x180098690  add     rcx, rdi
0x180098693  vmovaps xmm7, xmm0
0x180098697  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009869c  lea     rcx, [rdi+r12]
0x1800986a0  vmovaps xmm6, xmm0
0x1800986a4  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x1800986a9  vaddss  xmm1, xmm0, xmm7
0x1800986ad  vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x1800986b5  vaddss  xmm2, xmm1, xmm6
0x1800986b9  vmulss  xmm1, xmm2, xmm0
0x1800986bd  vminss  xmm2, xmm15, xmm1
0x1800986c1  vxorps  xmm0, xmm0, xmm0
0x1800986c5  vmaxss  xmm0, xmm0, xmm2
0x1800986c9  vcvttss2si eax, xmm0
0x1800986cd  mov     [rsi], ax
0x1800986d0  add     rsi, 2
0x1800986d4  mov     eax, [rbp+r15*4+0BB0h+var_B70]
0x1800986d9  inc     r15
0x1800986dc  add     r14d, eax
0x1800986df  cmp     r15, 1
0x1800986e3  jl      short loc_180098670
0x1800986e5  mov     r11d, [rbp+0BB0h+var_1DC]
0x1800986ec  mov     edi, [rbp+0BB0h+var_7C0]
0x1800986f2  mov     r13d, [rbp+0BB0h+var_7EC]
0x1800986f9  mov     rbx, qword ptr [rbp+0BB0h+var_B68]
0x1800986fd  mov     r10, [rbp+0BB0h+var_B90]
0x180098701  mov     r15, [rbp+0BB0h+var_BA8]
0x180098705  lea     ecx, [r13-1Fh]
0x180098709  cmp     r14d, ecx
0x18009870c  jge     loc_180098AC9
0x180098712  vmovdqu ymm14, cs:__ymm@7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff
0x18009871a  sub     ecx, r14d
0x18009871d  movsxd  r8, r14d
0x180098720  add     r8, 0Ah
0x180098724  mov     r11, r12
0x180098727  sub     r11, rbx
0x18009872a  sub     r11, r15
0x18009872d  lea     eax, [rcx-1]
0x180098730  shr     eax, 5
0x180098733  lea     r8, [rbx+r8*8]
0x180098737  inc     eax
0x180098739  add     r8, r15
0x18009873c  mov     r9d, eax
0x18009873f  shl     eax, 5
0x180098742  add     r14d, eax
0x180098745  nop     word ptr [rax+rax+00000000h]
0x180098750  vmovups xmm0, xmmword ptr [r8+r11-50h]
0x180098757  vinsertf128 ymm7, ymm0, xmmword ptr [r8-10h], 1
0x18009875e  vmovups xmm1, xmmword ptr [r8-40h]
0x180098764  vinsertf128 ymm9, ymm1, xmmword ptr [r8], 1
0x18009876a  vmovups xmm0, xmmword ptr [r8-30h]
0x180098770  vinsertf128 ymm11, ymm0, xmmword ptr [r8+10h], 1
0x180098777  vmovups xmm1, xmmword ptr [r8-20h]
0x18009877d  vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
0x180098784  vmovups xmm0, xmmword ptr [r8+30h]
0x18009878a  vinsertf128 ymm2, ymm0, xmmword ptr [r8+70h], 1
0x180098791  vmovups xmm1, xmmword ptr [r8+40h]
0x180098797  vinsertf128 ymm3, ymm1, xmmword ptr [r8+80h], 1
0x1800987a1  vmovups xmm0, xmmword ptr [r8+50h]
0x1800987a7  vinsertf128 ymm4, ymm0, xmmword ptr [r8+90h], 1
0x1800987b1  vmovups xmm1, xmmword ptr [r8+60h]
0x1800987b7  vinsertf128 ymm5, ymm1, xmmword ptr [r8+0A0h], 1
0x1800987c1  vpunpckhwd ymm8, ymm7, ymm2
0x1800987c5  vpunpcklwd ymm0, ymm11, ymm4
0x1800987c9  vpunpcklwd ymm6, ymm7, ymm2
0x1800987cd  vpunpcklwd ymm7, ymm6, ymm0
0x1800987d1  vpunpcklwd ymm10, ymm9, ymm3
0x1800987d5  vpunpckhwd ymm1, ymm11, ymm4
0x1800987d9  vpunpcklwd ymm11, ymm8, ymm1
0x1800987dd  vpunpcklwd ymm2, ymm13, ymm5
0x1800987e1  vpunpckhwd ymm12, ymm9, ymm3
0x1800987e5  vpunpckhwd ymm9, ymm6, ymm0
0x1800987e9  vpunpckhwd ymm4, ymm13, ymm5
0x1800987ed  vpunpckhwd ymm13, ymm8, ymm1
0x1800987f1  vpunpckhwd ymm1, ymm10, ymm2
0x1800987f5  vpunpcklwd ymm8, ymm9, ymm1
0x1800987f9  vpunpckhwd ymm9, ymm9, ymm1
0x1800987fd  vpunpcklwd ymm0, ymm10, ymm2
0x180098801  vpunpcklwd ymm6, ymm7, ymm0
0x180098805  vpunpckhwd ymm7, ymm7, ymm0
0x180098809  vpunpcklwd ymm3, ymm12, ymm4
0x18009880d  vpunpcklwd ymm1, ymm11, ymm3
0x180098811  vpunpcklwd ymm0, ymm6, ymm1
0x180098815  vpunpckhwd ymm1, ymm6, ymm1
0x180098819  vpunpckhwd ymm2, ymm11, ymm3
0x18009881d  vmovdqu [rbp+0BB0h+var_9F0], ymm1
0x180098825  vmovdqu [rbp+0BB0h+var_A70], ymm0
0x18009882d  vpunpckhwd ymm5, ymm12, ymm4
0x180098831  vpunpckhwd ymm1, ymm7, ymm2
0x180098835  vpunpcklwd ymm0, ymm7, ymm2
0x180098839  vpunpcklwd ymm4, ymm13, ymm5
0x18009883d  vmovdqu [rbp+0BB0h+var_9D0], ymm1
0x180098845  vmovdqu [rbp+0BB0h+var_A50], ymm0
0x18009884d  vpunpckhwd ymm1, ymm8, ymm4
0x180098851  vpunpcklwd ymm0, ymm8, ymm4
0x180098855  vpunpckhwd ymm3, ymm13, ymm5
0x180098859  vmovdqu [rbp+0BB0h+var_9B0], ymm1
0x180098861  vmovdqu [rbp+0BB0h+var_A30], ymm0
0x180098869  vpunpckhwd ymm1, ymm9, ymm3
0x18009886d  vpunpcklwd ymm0, ymm9, ymm3
0x180098871  vmovdqu [rbp+0BB0h+var_990], ymm1
0x180098879  vmovdqu [rbp+0BB0h+var_A10], ymm0
0x180098881  lea     rax, [rbp+0BB0h+var_170]
0x180098888  mov     edx, 2
0x18009888d  lea     rcx, [rbp+0BB0h+var_A30]
0x180098894  nop     dword ptr [rax+00h]
0x180098898  nop     dword ptr [rax+rax+00000000h]
0x1800988a0  lea     rax, [rax+60h]
0x1800988a4  vmovdqu ymm0, ymmword ptr [rcx-40h]
0x1800988a9  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x1800988ae  lea     rcx, [rcx+80h]
0x1800988b5  vmovdqu ymmword ptr [rax-0A0h], ymm0
0x1800988bd  vmovdqu ymm0, ymmword ptr [rcx-80h]
0x1800988c2  vmovdqu ymmword ptr [rax-60h], ymm0
0x1800988c7  vmovdqu ymmword ptr [rax-80h], ymm1
0x1800988cc  sub     rdx, 1
0x1800988d0  jnz     short loc_1800988A0
0x1800988d2  lea     rcx, [rbp+0BB0h+var_170]
0x1800988d9  mov     edx, 2
0x1800988de  lea     rax, [rbp+0BB0h+var_950]
0x1800988e5  nop     word ptr [rax+rax+00000000h]
0x1800988f0  lea     rax, [rax+0C0h]
0x1800988f7  vpcmpeqw ymm0, ymm14, ymmword ptr [rcx-40h]
0x1800988fc  vpandn  ymm2, ymm0, ymmword ptr [rcx-40h]
0x180098901  lea     rcx, [rcx+60h]
0x180098905  vcvtph2ps ymm0, xmm2
0x18009890a  vmovups ymmword ptr [rax-0E0h], ymm0
0x180098912  vpcmpeqw ymm0, ymm14, ymmword ptr [rcx-80h]
0x180098917  vextracti128 xmm1, ymm2, 1
0x18009891d  vcvtph2ps ymm2, xmm1
0x180098922  vpandn  ymm1, ymm0, ymmword ptr [rcx-80h]
0x180098927  vcvtph2ps ymm0, xmm1
0x18009892c  vmovups ymmword ptr [rax-0C0h], ymm0
0x180098934  vpcmpeqw ymm0, ymm14, ymmword ptr [rcx-60h]
0x180098939  vextracti128 xmm1, ymm1, 1
0x18009893f  vmovups ymmword ptr [rax-80h], ymm2
0x180098944  vcvtph2ps ymm2, xmm1
0x180098949  vpandn  ymm1, ymm0, ymmword ptr [rcx-60h]
0x18009894e  vcvtph2ps ymm0, xmm1
0x180098953  vmovups ymmword ptr [rax-60h], ymm2
0x180098958  vextracti128 xmm1, ymm1, 1
0x18009895e  vcvtph2ps ymm2, xmm1
0x180098963  vmovups ymmword ptr [rax-40h], ymm2
0x180098968  vmovups ymmword ptr [rax-0A0h], ymm0
0x180098970  sub     rdx, 1
0x180098974  jnz     loc_1800988F0
0x18009897a  vmovups ymm6, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
0x180098982  vmovups ymm8, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
0x18009898a  vmovups ymm0, [rbp+0BB0h+var_970]
0x180098992  vaddps  ymm1, ymm0, [rbp+0BB0h+var_950]
0x18009899a  vaddps  ymm2, ymm1, [rbp+0BB0h+var_930]
0x1800989a2  vmovups ymm0, [rbp+0BB0h+var_910]
0x1800989aa  vaddps  ymm1, ymm0, [rbp+0BB0h+var_8F0]
0x1800989b2  vaddps  ymm5, ymm1, [rbp+0BB0h+var_8D0]
0x1800989ba  vmovups ymm0, [rbp+0BB0h+var_8B0]
0x1800989c2  vaddps  ymm1, ymm0, [rbp+0BB0h+var_890]
0x1800989ca  vaddps  ymm4, ymm1, [rbp+0BB0h+var_870]
0x1800989d2  vmovups ymm0, [rbp+0BB0h+var_850]
0x1800989da  vaddps  ymm1, ymm0, [rbp+0BB0h+var_830]
0x1800989e2  vaddps  ymm3, ymm1, [rbp+0BB0h+var_810]
0x1800989ea  vmulps  ymm0, ymm6, ymm2
0x1800989ee  vminps  ymm1, ymm0, ymm8
0x1800989f3  vxorps  xmm7, xmm7, xmm7
0x1800989f7  vmaxps  ymm2, ymm1, ymm7
0x1800989fb  vmovups [rbp+0BB0h+var_AF0], ymm2
0x180098a03  vmulps  ymm0, ymm6, ymm5
0x180098a07  vminps  ymm1, ymm0, ymm8
0x180098a0c  vmaxps  ymm2, ymm1, ymm7
0x180098a10  vmulps  ymm0, ymm6, ymm4
0x180098a14  vminps  ymm1, ymm0, ymm8
0x180098a19  vmovups [rbp+0BB0h+var_AD0], ymm2
0x180098a21  vmaxps  ymm2, ymm1, ymm7
  ... truncated ...
```
