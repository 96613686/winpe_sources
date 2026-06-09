# Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,8,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x180098c30`
- end: `0x18009952f`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$07$01$00$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$07$01$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `2303`
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
- `0x180098c30`

## pseudocode

```c
bool __fastcall Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,8,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int64 _R9)
{
  __int64 v9; // rsi
  unsigned __int8 *v10; // rcx
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rdx
  unsigned __int8 *v13; // rcx
  bool result; // al
  int v15; // ecx
  __int64 v16; // rdi
  int v18; // r11d
  int v19; // edx
  int v20; // r13d
  int v21; // ecx
  int v22; // r15d
  int v23; // edx
  int v24; // r10d
  __int64 v25; // r8
  int v27; // r9d
  int v28; // r10d
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rsi
  __int64 v32; // r14
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // r12
  __int64 v37; // rax
  __int64 v38; // rdi
  int v48; // eax
  int v49; // r14d
  __int64 v50; // rsi
  __int64 v51; // r15
  __int64 v58; // rbx
  __int64 v59; // rax
  _DWORD *v65; // rax
  int v66; // r14d
  __int64 v69; // r9
  __int64 v111; // rdx
  int v167; // ecx
  __int64 v168; // rdx
  __int64 v169; // r15
  __int64 v170; // rsi
  __int64 v171; // r12
  __int64 v172; // rbx
  __int64 v173; // r14
  __int64 v189; // rcx
  int v190; // ecx
  int v191; // eax
  bool v192; // cc
  int v204; // [rsp+58h] [rbp+0h] BYREF
  char v205; // [rsp+C00h] [rbp+BA8h] BYREF

  _RBP = (unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL;
  __asm { vmovups xmm0, xmmword ptr [r9] }
  *(_QWORD *)(_RBP + 48) = a3;
  *(_QWORD *)(_RBP + 40) = a1;
  v9 = a1;
  __asm { vmovups [rbp+0BE0h+var_BA0], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 1216,
    2,
    1,
    a3,
    (_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 64),
    (_DWORD *)(a1 + 8));
  v10 = a2[1];
  v11 = a2[2];
  if ( *a2 <= v10 )
    v10 = *a2;
  v12 = a2[3];
  if ( v10 <= v11 )
    v11 = v10;
  if ( v11 <= v12 )
    v12 = v11;
  v13 = &v12[*(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C8)];
  *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = v13;
  *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90) = v13 + 2;
  *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = v13 + 4;
  *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0) = v13 + 6;
  result = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
             (Binary::IntegratedSelection::SmoothControl *)(_RBP + 1232),
             v12,
             (unsigned __int8 **)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 80),
             (unsigned __int8 **)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 88));
  if ( result )
  {
    v15 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C0);
    result = 0;
    *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    v16 = 0;
    *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 2;
    *(_DWORD *)_RBP = 0;
    if ( v15 > 0 )
    {
      __asm { vmovss  xmm15, cs:__real@447fc000 }
      v18 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F8);
      v19 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F0);
      v20 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C4);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F0) = ++v19;
        if ( v19 == 1 )
        {
          v21 = *(_DWORD *)(v9 + 44);
          v22 = 0;
          v23 = *(_DWORD *)(v9 + 40);
          v24 = *(_DWORD *)(v9 + 28);
          v25 = *(int *)(v9 + 52);
          if ( *(int *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F4) <= 0 )
            v22 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F4);
          __asm { vmovups ymm0, [rbp+0BE0h+var_B58] }
          __asm { vmovups [rbp+0BE0h+var_B78], ymm0 }
          if ( v24 < v21 )
            v24 = v21;
          v27 = v25 - 1;
          v28 = v24 - v21;
          if ( v18 < v23 )
            v18 = v23;
          v29 = (v18 - v23) % *(_DWORD *)(v9 + 48);
          v30 = *(_QWORD *)(v9 + 56);
          v31 = *(int *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0xAEC);
          if ( v28 <= v27 )
            v27 = v28;
          v32 = v27;
          v33 = v30 + 2 * v25 * v29;
          v34 = v16 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70);
          v35 = v16 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = v34;
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = v35;
          v36 = v35;
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = v35;
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = v35;
          v37 = v16 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78);
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v34;
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = v37;
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = v37;
          *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = v34;
          v38 = -8 * v22;
          __asm { vzeroupper }
          *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v38 + v34);
          __asm { vmovaps xmm7, xmm0 }
          *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v38 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
          __asm { vmovaps xmm6, xmm0 }
          *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v38 + v36);
          __asm
          {
            vaddss  xmm1, xmm0, xmm7
            vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
          }
          __asm
          {
            vaddss  xmm2, xmm1, xmm6
            vmulss  xmm1, xmm2, xmm0
            vminss  xmm2, xmm15, xmm1
            vxorps  xmm8, xmm8, xmm8
            vmaxss  xmm0, xmm8, xmm2
            vcvttss2si eax, xmm0
          }
          *(_WORD *)(v33 + 2 * v32) = _EAX;
          _RDI = (_WORD *)(v33 + 2 * (v32 + 1));
          v48 = v31 + 1;
          v49 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60 + 4 * v31) - v22;
          v50 = v48;
          if ( v48 < 1LL )
          {
            v51 = _RBP + 96 + 4LL * v48;
            do
            {
              if ( v49 >= v20 )
                break;
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(8 * v49 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20));
              __asm { vmovaps xmm7, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(8 * v49 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
              __asm { vmovaps xmm6, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(8 * v49 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 8));
              __asm
              {
                vaddss  xmm1, xmm0, xmm7
                vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                vaddss  xmm2, xmm1, xmm6
                vmulss  xmm1, xmm2, xmm0
                vminss  xmm2, xmm15, xmm1
                vmaxss  xmm0, xmm8, xmm2
                vcvttss2si eax, xmm0
              }
              if ( (unsigned __int16)_EAX <= 0x3ECu )
              {
                v36 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
              }
              else
              {
                _mm_lfence();
                v58 = 8 * v49 - 8;
                v59 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70);
                *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v59;
                *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v59 + v58);
                __asm { vmovaps xmm7, xmm0 }
                *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v58 + *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78));
                v36 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68);
                __asm { vmovaps xmm6, xmm0 }
                *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = v36;
                *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v36 + v58);
                __asm
                {
                  vaddss  xmm1, xmm0, xmm7
                  vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                  vaddss  xmm2, xmm1, xmm6
                  vmulss  xmm1, xmm2, xmm0
                  vminss  xmm2, xmm15, xmm1
                  vmaxss  xmm0, xmm8, xmm2
                  vcvttss2si eax, xmm0
                }
              }
              *_RDI = _EAX;
              ++v50;
              v65 = (_DWORD *)v51;
              ++_RDI;
              v51 += 4;
              v49 += *v65;
            }
            while ( v50 < 1 );
          }
          v20 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C4);
          v66 = v49 - 1;
          if ( v66 < v20 - 31 )
          {
            __asm { vmovdqu ymm14, cs:__ymm@7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff }
            _R8 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 8) + 144LL + 8LL * v66;
            v69 = ((unsigned int)(v20 - 31 - v66 - 1) >> 5) + 1;
            v66 += 32 * v69;
            do
            {
              __asm
              {
                vmovups xmm0, xmmword ptr [r8-90h]
                vinsertf128 ymm7, ymm0, xmmword ptr [r8-10h], 1
                vmovups xmm1, xmmword ptr [r8-80h]
                vinsertf128 ymm10, ymm1, xmmword ptr [r8], 1
                vmovups xmm0, xmmword ptr [r8-70h]
                vinsertf128 ymm12, ymm0, xmmword ptr [r8+10h], 1
                vmovups xmm1, xmmword ptr [r8-60h]
                vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
                vmovups xmm0, xmmword ptr [r8-50h]
                vinsertf128 ymm2, ymm0, xmmword ptr [r8+30h], 1
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
                vmovdqu [rbp+0BE0h+var_8C0], ymm1
                vmovdqu [rbp+0BE0h+var_8E0], ymm0
                vpunpckhwd ymm2, ymm9, ymm2
                vpunpckhwd ymm4, ymm13, ymm5
                vpunpckhwd ymm1, ymm6, ymm2
                vpunpcklwd ymm0, ymm6, ymm2
                vpunpcklwd ymm3, ymm11, ymm4
                vmovdqu [rbp+0BE0h+var_880], ymm1
                vmovdqu [rbp+0BE0h+var_8A0], ymm0
                vpunpckhwd ymm1, ymm10, ymm3
                vpunpcklwd ymm0, ymm10, ymm3
                vpunpckhwd ymm5, ymm11, ymm4
                vmovdqu [rbp+0BE0h+var_840], ymm1
                vmovdqu [rbp+0BE0h+var_860], ymm0
                vpunpckhwd ymm1, ymm8, ymm5
                vpunpcklwd ymm0, ymm8, ymm5
                vmovdqu [rbp+0BE0h+var_800], ymm1
                vmovdqu [rbp+0BE0h+var_820], ymm0
              }
              _RAX = _RBP + 1088;
              v111 = 2;
              _RCX = _RBP + 832;
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
                --v111;
              }
              while ( v111 );
              for ( _RAX = 0; _RAX < 192; _RAX += 96 )
              {
                __asm
                {
                  vmovdqu ymm1, [rbp+rax+0BE0h+var_7E0]
                  vmovdqu ymm3, [rbp+rax+0BE0h+var_7A0]
                  vpcmpeqw ymm0, ymm1, ymm14
                  vpandn  ymm2, ymm0, ymm1
                  vcvtph2ps ymm0, xmm2
                  vmovups [rbp+rax+0BE0h+var_A60], ymm0
                  vextracti128 xmm0, ymm2, 1
                  vmovdqu ymm2, [rbp+rax+0BE0h+var_7C0]
                  vcvtph2ps ymm1, xmm0
                  vmovups [rbp+rax+0BE0h+var_9A0], ymm1
                  vpcmpeqw ymm0, ymm2, ymm14
                  vpandn  ymm1, ymm0, ymm2
                  vcvtph2ps ymm0, xmm1
                  vmovups [rbp+rax+0BE0h+var_A40], ymm0
                  vextracti128 xmm1, ymm1, 1
                  vcvtph2ps ymm2, xmm1
                  vpcmpeqw ymm0, ymm3, ymm14
                  vpandn  ymm1, ymm0, ymm3
                  vcvtph2ps ymm0, xmm1
                  vmovups [rbp+rax+0BE0h+var_980], ymm2
                  vextracti128 xmm1, ymm1, 1
                  vcvtph2ps ymm2, xmm1
                  vmovups [rbp+rax+0BE0h+var_960], ymm2
                  vmovups [rbp+rax+0BE0h+var_A20], ymm0
                }
              }
              __asm
              {
                vmovups ymm6, cs:__ymm@43aa800043aa800043aa800043aa800043aa800043aa800043aa800043aa8000
                vmovups ymm8, cs:__ymm@447fc000447fc000447fc000447fc000447fc000447fc000447fc000447fc000
                vmovups ymm0, [rbp+0BE0h+var_A60]
                vaddps  ymm1, ymm0, [rbp+0BE0h+var_A40]
                vaddps  ymm2, ymm1, [rbp+0BE0h+var_A20]
                vmovups ymm0, [rbp+0BE0h+var_A00]
                vaddps  ymm1, ymm0, [rbp+0BE0h+var_9E0]
                vaddps  ymm5, ymm1, [rbp+0BE0h+var_9C0]
                vmovups ymm0, [rbp+0BE0h+var_9A0]
                vaddps  ymm1, ymm0, [rbp+0BE0h+var_980]
                vaddps  ymm4, ymm1, [rbp+0BE0h+var_960]
                vmovups ymm0, [rbp+0BE0h+var_920]
                vaddps  ymm1, ymm0, [rbp+0BE0h+var_940]
                vaddps  ymm3, ymm1, [rbp+0BE0h+var_900]
                vmulps  ymm0, ymm2, ymm6
                vminps  ymm1, ymm0, ymm8
                vxorps  xmm7, xmm7, xmm7
                vmaxps  ymm2, ymm1, ymm7
                vmovups [rbp+0BE0h+var_B20], ymm2
                vmulps  ymm0, ymm5, ymm6
                vminps  ymm1, ymm0, ymm8
                vmaxps  ymm2, ymm1, ymm7
                vmulps  ymm0, ymm4, ymm6
                vminps  ymm1, ymm0, ymm8
                vmovups [rbp+0BE0h+var_B00], ymm2
                vmaxps  ymm2, ymm1, ymm7
                vmulps  ymm0, ymm3, ymm6
                vminps  ymm1, ymm0, ymm8
                vmovups [rbp+0BE0h+var_AE0], ymm2
                vmaxps  ymm2, ymm1, ymm7
                vmovups [rbp+0BE0h+var_AC0], ymm2
              }
              for ( _RAX = 0; _RAX < 64; _RAX += 32 )
              {
                __asm
                {
                  vcvttps2dq ymm1, [rbp+rax+0BE0h+var_AE0]
                  vcvttps2dq ymm0, [rbp+rax+0BE0h+var_B20]
                  vpackusdw ymm1, ymm0, ymm1
                  vpermq  ymm2, ymm1, 0D8h
                  vmovdqu [rbp+rax+0BE0h+var_AA0], ymm2
                }
              }
              __asm
              {
                vmovdqu ymm0, [rbp+0BE0h+var_A80]
                vpcmpgtw ymm2, ymm0, cs:__ymm@03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec
                vpandn  ymm1, ymm2, ymm0
                vpand   ymm0, ymm2, [rbp+0BE0h+var_AA0]
                vpaddw  ymm2, ymm0, ymm1
                vmovdqu ymmword ptr [rdi], ymm2
              }
              _RDI += 16;
              _R8 += 256;
              --v69;
            }
            while ( v69 );
            v20 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C4);
            v36 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
            __asm { vxorps  xmm8, xmm8, xmm8 }
          }
          v167 = v66 + 1;
          if ( v66 + 1 < v20 )
          {
            v168 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78);
            v169 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) - v168;
            v170 = v168 + 8 * v167;
            v171 = v36 - v168;
            v172 = v168 + 8 * v167 - 8;
            v173 = ((unsigned int)(v20 - v167 - 1) >> 1) + 1;
            do
            {
              __asm { vzeroupper }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v169 + v170);
              __asm { vmovaps xmm7, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v170);
              __asm { vmovaps xmm6, xmm0 }
              *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v171 + v170);
              __asm
              {
                vaddss  xmm1, xmm0, xmm7
                vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                vaddss  xmm2, xmm1, xmm6
                vmulss  xmm1, xmm2, xmm0
                vminss  xmm2, xmm15, xmm1
                vmaxss  xmm0, xmm8, xmm2
                vcvttss2si eax, xmm0
              }
              if ( (unsigned __int16)_EAX > 0x3ECu )
              {
                _mm_lfence();
                *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v169 + v172);
                __asm { vmovaps xmm7, xmm0 }
                *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v172);
                __asm { vmovaps xmm6, xmm0 }
                *(double *)&_XMM0 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v171 + v172);
                __asm
                {
                  vaddss  xmm1, xmm0, xmm7
                  vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
                  vaddss  xmm2, xmm1, xmm6
                  vmulss  xmm1, xmm2, xmm0
                  vminss  xmm2, xmm15, xmm1
                  vmaxss  xmm0, xmm8, xmm2
                  vcvttss2si eax, xmm0
                }
              }
              *_RDI = _EAX;
              v170 += 16;
              ++_RDI;
              v172 += 16;
              --v173;
            }
            while ( v173 );
            v20 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C4);
          }
          v189 = *(int *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0xAD4);
          v16 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
          v19 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F0)
              - *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4FC + 4 * v189);
          v190 = v189 + 1;
          v9 = *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
          if ( v190 >= *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0xADC) )
            v190 = 0;
          v18 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F8) + 1;
          *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0xAD4) = v190;
          v15 = *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C0);
          *(_DWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4F8) = v18;
        }
        v16 += **(int **)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
        v191 = *(_DWORD *)_RBP + 1;
        *(_QWORD *)(((unsigned __int64)&v204 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = v16;
        *(_DWORD *)_RBP = v191;
        v192 = v191 < v15;
        result = 0;
      }
      while ( v192 );
    }
  }
  __asm { vzeroupper }
  _R11 = &v205;
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
  return result;
}

```

## disassembly

```asm
0x180098c30  mov     rax, rsp
0x180098c33  push    rbp
0x180098c34  push    rbx
0x180098c35  push    rsi
0x180098c36  push    rdi
0x180098c37  push    r12
0x180098c39  push    r13
0x180098c3b  push    r14
0x180098c3d  push    r15
0x180098c3f  sub     rsp, 0BF8h
0x180098c46  vmovaps xmmword ptr [rax-58h], xmm6
0x180098c4b  vmovaps xmmword ptr [rax-68h], xmm7
0x180098c50  vmovaps xmmword ptr [rax-78h], xmm8
0x180098c55  vmovaps xmmword ptr [rax-88h], xmm9
0x180098c5d  vmovaps xmmword ptr [rax-98h], xmm10
0x180098c65  vmovaps xmmword ptr [rax-0A8h], xmm11
0x180098c6d  vmovaps xmmword ptr [rax-0B8h], xmm12
0x180098c75  vmovaps xmmword ptr [rax-0C8h], xmm13
0x180098c7d  vmovaps xmmword ptr [rax-0D8h], xmm14
0x180098c85  vmovaps xmmword ptr [rax-0E8h], xmm15
0x180098c8d  lea     rbp, [rsp+0C30h+var_BE0]
0x180098c92  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180098c96  mov     rax, cs:__security_cookie
0x180098c9d  xor     rax, rsp
0x180098ca0  mov     [rbp+0BE0h+var_F0], rax
0x180098ca7  vmovups xmm0, xmmword ptr [r9]
0x180098cac  lea     rax, [rcx+8]
0x180098cb0  mov     [rbp+0BE0h+var_BB0], r8
0x180098cb4  mov     [rsp+0C30h+var_C08], rax
0x180098cb9  mov     rbx, rdx
0x180098cbc  mov     edx, 2
0x180098cc1  mov     [rbp+0BE0h+var_BB8], rcx
0x180098cc5  mov     rsi, rcx
0x180098cc8  lea     rax, [rbp+0BE0h+var_BA0]
0x180098ccc  mov     r9, r8
0x180098ccf  mov     [rsp+0C30h+var_C10], rax
0x180098cd4  lea     rcx, [rbp+0BE0h+var_720]
0x180098cdb  lea     r8d, [rdx-1]
0x180098cdf  vmovups [rbp+0BE0h+var_BA0], xmm0
0x180098ce4  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180098ce9  mov     rcx, [rbx+8]
0x180098ced  lea     r9, [rbp+0BE0h+var_B88]; unsigned __int8 **
0x180098cf1  cmp     [rbx], rcx
0x180098cf4  lea     r8, [rbp+0BE0h+var_B90]; unsigned __int8 **
0x180098cf8  mov     rax, [rbx+10h]
0x180098cfc  cmovbe  rcx, [rbx]
0x180098d00  mov     rdx, [rbx+18h]
0x180098d04  cmp     rcx, rax
0x180098d07  cmovbe  rax, rcx
0x180098d0b  mov     rcx, [rbp+0BE0h+var_718]
0x180098d12  cmp     rax, rdx
0x180098d15  cmovbe  rdx, rax; unsigned __int8 *
0x180098d19  add     rcx, rdx
0x180098d1c  mov     qword ptr [rbp+0BE0h+var_B58], rcx
0x180098d23  lea     rax, [rcx+2]
0x180098d27  mov     qword ptr [rbp+0BE0h+var_B58+8], rax
0x180098d2e  lea     rax, [rcx+4]
0x180098d32  mov     qword ptr [rbp+0BE0h+var_B58+10h], rax
0x180098d39  lea     rax, [rcx+6]
0x180098d3d  lea     rcx, [rbp+0BE0h+var_710]; this
0x180098d44  mov     qword ptr [rbp+0BE0h+var_B58+18h], rax
0x180098d4b  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x180098d50  test    al, al
0x180098d52  jz      loc_1800994C0
0x180098d58  mov     ecx, [rbp+0BE0h+var_720]
0x180098d5e  xor     eax, eax
0x180098d60  mov     [rbp+0BE0h+var_BC8], rax
0x180098d64  mov     edi, eax
0x180098d66  mov     [rbp+0BE0h+var_B80], 2
0x180098d6d  mov     [rbp+0BE0h+var_BE0], eax
0x180098d70  test    ecx, ecx
0x180098d72  jle     loc_1800994C0
0x180098d78  vmovss  xmm15, cs:__real@447fc000
0x180098d80  mov     r11d, [rbp+0BE0h+var_6E8]
0x180098d87  mov     edx, [rbp+0BE0h+var_6F0]
0x180098d8d  mov     r13d, [rbp+0BE0h+var_71C]
0x180098d94  inc     edx
0x180098d96  mov     [rbp+0BE0h+var_6F0], edx
0x180098d9c  cmp     edx, 1
0x180098d9f  jnz     loc_18009949D
0x180098da5  mov     ecx, [rsi+2Ch]
0x180098da8  mov     r15d, eax
0x180098dab  mov     edx, [rsi+28h]
0x180098dae  mov     eax, [rbp+0BE0h+var_6EC]
0x180098db4  test    eax, eax
0x180098db6  mov     r10d, [rsi+1Ch]
0x180098dba  movsxd  r8, dword ptr [rsi+34h]
0x180098dbe  cmovle  r15d, eax
0x180098dc2  vmovups ymm0, [rbp+0BE0h+var_B58]
0x180098dca  cmp     r10d, ecx
0x180098dcd  vmovups [rbp+0BE0h+var_B78], ymm0
0x180098dd2  cmovl   r10d, ecx
0x180098dd6  lea     r9d, [r8-1]
0x180098dda  sub     r10d, ecx
0x180098ddd  cmp     r11d, edx
0x180098de0  cmovl   r11d, edx
0x180098de4  sub     r11d, edx
0x180098de7  mov     eax, r11d
0x180098dea  cdq
0x180098deb  idiv    dword ptr [rsi+30h]
0x180098dee  mov     rax, [rsi+38h]
0x180098df2  movsxd  rsi, [rbp+0BE0h+var_F4]
0x180098df9  movsxd  rcx, edx
0x180098dfc  imul    rcx, r8
0x180098e00  cmp     r10d, r9d
0x180098e03  cmovle  r9d, r10d
0x180098e07  movsxd  r14, r9d
0x180098e0a  lea     rbx, [rax+rcx*2]
0x180098e0e  mov     rcx, qword ptr [rbp+0BE0h+var_B78+8]
0x180098e12  mov     rax, qword ptr [rbp+0BE0h+var_B58]
0x180098e19  add     rcx, rdi
0x180098e1c  add     rax, rdi
0x180098e1f  mov     [rbp+0BE0h+var_BC0], rcx
0x180098e23  mov     [rbp+0BE0h+var_BD8], rax
0x180098e27  mov     r12, rax
0x180098e2a  mov     [rbp+0BE0h+var_B90], rax
0x180098e2e  mov     qword ptr [rbp+0BE0h+var_B78], rax
0x180098e32  mov     rax, qword ptr [rbp+0BE0h+var_B78+10h]
0x180098e36  add     rax, rdi
0x180098e39  mov     [rbp+0BE0h+var_B88], rcx
0x180098e3d  mov     [rbp+0BE0h+var_BD0], rax
0x180098e41  mov     qword ptr [rbp+0BE0h+var_B78+10h], rax
0x180098e45  mov     eax, r15d
0x180098e48  neg     eax
0x180098e4a  mov     qword ptr [rbp+0BE0h+var_B78+8], rcx
0x180098e4e  shl     eax, 3
0x180098e51  movsxd  rdi, eax
0x180098e54  add     rcx, rdi
0x180098e57  vzeroupper
0x180098e5a  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098e5f  mov     rcx, [rbp+0BE0h+var_BD0]
0x180098e63  add     rcx, rdi
0x180098e66  vmovaps xmm7, xmm0
0x180098e6a  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098e6f  lea     rcx, [rdi+r12]
0x180098e73  vmovaps xmm6, xmm0
0x180098e77  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098e7c  vaddss  xmm1, xmm0, xmm7
0x180098e80  vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180098e88  lea     rdi, [r14+1]
0x180098e8c  vaddss  xmm2, xmm1, xmm6
0x180098e90  vmulss  xmm1, xmm2, xmm0
0x180098e94  vminss  xmm2, xmm15, xmm1
0x180098e98  vxorps  xmm8, xmm8, xmm8
0x180098e9d  vmaxss  xmm0, xmm8, xmm2
0x180098ea1  vcvttss2si eax, xmm0
0x180098ea5  mov     [rbx+r14*2], ax
0x180098eaa  lea     rdi, [rbx+rdi*2]
0x180098eae  mov     r14d, [rbp+rsi*4+0BE0h+var_B80]
0x180098eb3  lea     eax, [rsi+1]
0x180098eb6  sub     r14d, r15d
0x180098eb9  movsxd  rsi, eax
0x180098ebc  cmp     rsi, 1
0x180098ec0  jge     loc_180098FBF
0x180098ec6  lea     r15, [rbp+0BE0h+var_B80]
0x180098eca  lea     r15, [r15+rsi*4]
0x180098ece  xchg    ax, ax
0x180098ed0  cmp     r14d, r13d
0x180098ed3  jge     loc_180098FBF
0x180098ed9  mov     rcx, [rbp+0BE0h+var_BC0]
0x180098edd  lea     r12d, ds:0[r14*8]
0x180098ee5  movsxd  rbx, r12d
0x180098ee8  add     rcx, rbx
0x180098eeb  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098ef0  mov     rcx, [rbp+0BE0h+var_BD0]
0x180098ef4  add     rcx, rbx
0x180098ef7  vmovaps xmm7, xmm0
0x180098efb  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098f00  mov     rcx, [rbp+0BE0h+var_BD8]
0x180098f04  add     rcx, rbx
0x180098f07  vmovaps xmm6, xmm0
0x180098f0b  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098f10  vaddss  xmm1, xmm0, xmm7
0x180098f14  vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180098f1c  vaddss  xmm2, xmm1, xmm6
0x180098f20  vmulss  xmm1, xmm2, xmm0
0x180098f24  vminss  xmm2, xmm15, xmm1
0x180098f28  vmaxss  xmm0, xmm8, xmm2
0x180098f2c  vcvttss2si eax, xmm0
0x180098f30  mov     ecx, 3ECh
0x180098f35  cmp     ax, cx
0x180098f38  jbe     short loc_180098F9D
0x180098f3a  lfence
0x180098f3d  lea     eax, [r12-8]
0x180098f42  movsxd  rbx, eax
0x180098f45  mov     rax, qword ptr [rbp+0BE0h+var_B78+8]
0x180098f49  mov     [rbp+0BE0h+var_B88], rax
0x180098f4d  lea     rcx, [rax+rbx]
0x180098f51  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098f56  mov     rcx, qword ptr [rbp+0BE0h+var_B78+10h]
0x180098f5a  add     rcx, rbx
0x180098f5d  vmovaps xmm7, xmm0
0x180098f61  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098f66  mov     r12, qword ptr [rbp+0BE0h+var_B78]
0x180098f6a  vmovaps xmm6, xmm0
0x180098f6e  mov     [rbp+0BE0h+var_B90], r12
0x180098f72  lea     rcx, [r12+rbx]
0x180098f76  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x180098f7b  vaddss  xmm1, xmm0, xmm7
0x180098f7f  vdivss  xmm0, xmm15, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x180098f87  vaddss  xmm2, xmm1, xmm6
0x180098f8b  vmulss  xmm1, xmm2, xmm0
0x180098f8f  vminss  xmm2, xmm15, xmm1
0x180098f93  vmaxss  xmm0, xmm8, xmm2
0x180098f97  vcvttss2si eax, xmm0
0x180098f9b  jmp     short loc_180098FA1
0x180098f9d  mov     r12, [rbp+0BE0h+var_B90]
0x180098fa1  mov     [rdi], ax
0x180098fa4  inc     rsi
0x180098fa7  mov     rax, r15
0x180098faa  add     rdi, 2
0x180098fae  add     r15, 4
0x180098fb2  add     r14d, [rax]
0x180098fb5  cmp     rsi, 1
0x180098fb9  jl      loc_180098ED0
0x180098fbf  mov     r13d, [rbp+0BE0h+var_71C]
0x180098fc6  dec     r14d
0x180098fc9  lea     ecx, [r13-1Fh]
0x180098fcd  cmp     r14d, ecx
0x180098fd0  jge     loc_180099359
0x180098fd6  mov     rdx, [rbp+0BE0h+var_BD8]
0x180098fda  sub     ecx, r14d
0x180098fdd  vmovdqu ymm14, cs:__ymm@7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff7fff
0x180098fe5  movsxd  r8, r14d
0x180098fe8  add     rdx, 90h
0x180098fef  lea     eax, [rcx-1]
0x180098ff2  shr     eax, 5
0x180098ff5  inc     eax
0x180098ff7  lea     r8, [rdx+r8*8]
0x180098ffb  mov     r9d, eax
0x180098ffe  shl     eax, 5
0x180099001  add     r14d, eax
0x180099004  xor     r12d, r12d
0x180099007  nop     word ptr [rax+rax+00000000h]
0x180099010  vmovups xmm0, xmmword ptr [r8-90h]
0x180099019  vinsertf128 ymm7, ymm0, xmmword ptr [r8-10h], 1
0x180099020  vmovups xmm1, xmmword ptr [r8-80h]
0x180099026  vinsertf128 ymm10, ymm1, xmmword ptr [r8], 1
0x18009902c  vmovups xmm0, xmmword ptr [r8-70h]
0x180099032  vinsertf128 ymm12, ymm0, xmmword ptr [r8+10h], 1
0x180099039  vmovups xmm1, xmmword ptr [r8-60h]
0x18009903f  vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
0x180099046  vmovups xmm0, xmmword ptr [r8-50h]
0x18009904c  vinsertf128 ymm2, ymm0, xmmword ptr [r8+30h], 1
0x180099053  vmovups xmm1, xmmword ptr [r8-40h]
0x180099059  vinsertf128 ymm3, ymm1, xmmword ptr [r8+40h], 1
0x180099060  vmovups xmm0, xmmword ptr [r8-30h]
0x180099066  vinsertf128 ymm4, ymm0, xmmword ptr [r8+50h], 1
0x18009906d  vmovups xmm1, xmmword ptr [r8-20h]
0x180099073  vinsertf128 ymm5, ymm1, xmmword ptr [r8+60h], 1
0x18009907a  vpunpckhwd ymm8, ymm7, ymm2
0x18009907e  vpunpckhwd ymm1, ymm12, ymm4
0x180099082  vpunpcklwd ymm6, ymm7, ymm2
0x180099086  vpunpcklwd ymm9, ymm10, ymm3
0x18009908a  vpunpcklwd ymm0, ymm12, ymm4
0x18009908e  vpunpcklwd ymm7, ymm6, ymm0
0x180099092  vpunpckhwd ymm6, ymm6, ymm0
0x180099096  vpunpckhwd ymm11, ymm10, ymm3
0x18009909a  vpunpcklwd ymm10, ymm8, ymm1
0x18009909e  vpunpckhwd ymm8, ymm8, ymm1
0x1800990a2  vpunpcklwd ymm2, ymm13, ymm5
0x1800990a6  vpunpcklwd ymm1, ymm9, ymm2
0x1800990aa  vpunpcklwd ymm0, ymm7, ymm1
0x1800990ae  vpunpckhwd ymm1, ymm7, ymm1
0x1800990b2  vmovdqu [rbp+0BE0h+var_8C0], ymm1
0x1800990ba  vmovdqu [rbp+0BE0h+var_8E0], ymm0
0x1800990c2  vpunpckhwd ymm2, ymm9, ymm2
0x1800990c6  vpunpckhwd ymm4, ymm13, ymm5
0x1800990ca  vpunpckhwd ymm1, ymm6, ymm2
0x1800990ce  vpunpcklwd ymm0, ymm6, ymm2
0x1800990d2  vpunpcklwd ymm3, ymm11, ymm4
0x1800990d6  vmovdqu [rbp+0BE0h+var_880], ymm1
0x1800990de  vmovdqu [rbp+0BE0h+var_8A0], ymm0
0x1800990e6  vpunpckhwd ymm1, ymm10, ymm3
0x1800990ea  vpunpcklwd ymm0, ymm10, ymm3
0x1800990ee  vpunpckhwd ymm5, ymm11, ymm4
0x1800990f2  vmovdqu [rbp+0BE0h+var_840], ymm1
0x1800990fa  vmovdqu [rbp+0BE0h+var_860], ymm0
0x180099102  vpunpckhwd ymm1, ymm8, ymm5
0x180099106  vpunpcklwd ymm0, ymm8, ymm5
0x18009910a  vmovdqu [rbp+0BE0h+var_800], ymm1
0x180099112  vmovdqu [rbp+0BE0h+var_820], ymm0
0x18009911a  lea     rax, [rbp+0BE0h+var_7A0]
0x180099121  mov     edx, 2
0x180099126  lea     rcx, [rbp+0BE0h+var_8A0]
0x18009912d  nop     dword ptr [rax]
0x180099130  lea     rax, [rax+60h]
0x180099134  vmovdqu ymm0, ymmword ptr [rcx-40h]
0x180099139  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x18009913e  lea     rcx, [rcx+80h]
0x180099145  vmovdqu ymmword ptr [rax-0A0h], ymm0
0x18009914d  vmovdqu ymm0, ymmword ptr [rcx-80h]
0x180099152  vmovdqu ymmword ptr [rax-60h], ymm0
0x180099157  vmovdqu ymmword ptr [rax-80h], ymm1
0x18009915c  sub     rdx, 1
0x180099160  jnz     short loc_180099130
0x180099162  mov     rax, r12
0x180099165  vmovdqu ymm1, [rbp+rax+0BE0h+var_7E0]
0x18009916e  vmovdqu ymm3, [rbp+rax+0BE0h+var_7A0]
0x180099177  vpcmpeqw ymm0, ymm1, ymm14
  ... truncated ...
```
