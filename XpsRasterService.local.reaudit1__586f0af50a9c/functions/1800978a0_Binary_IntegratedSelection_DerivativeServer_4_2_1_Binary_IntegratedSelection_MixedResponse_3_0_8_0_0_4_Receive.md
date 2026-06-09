# Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,4,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x1800978a0`
- end: `0x180097f92`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$03$01$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$03$01$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1778`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180099c00`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x1800978a0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,2,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,4,2,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int64 _R9)
{
  __int64 v9; // r14
  unsigned __int8 *v10; // rcx
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rdx
  unsigned __int8 *v13; // rbx
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // r12
  int v17; // r13d
  int v18; // esi
  int v19; // edx
  int v20; // edi
  int v21; // ecx
  int v22; // r11d
  int v23; // edx
  int v24; // r10d
  __int64 v25; // r8
  int v27; // r9d
  int v28; // r10d
  int v29; // eax
  unsigned __int8 *v30; // rsi
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r15
  __int64 v36; // r14
  _WORD *v37; // r9
  int v39; // edx
  __int64 i; // r10
  __int64 v41; // r8
  unsigned int v42; // ecx
  int v43; // eax
  int v44; // r10d
  int v45; // ecx
  __int64 v50; // r11
  __int64 v100; // rdx
  __int64 v106; // rdx
  int v145; // r8d
  __int64 v146; // r14
  unsigned __int8 *v147; // rsi
  unsigned __int8 *v148; // rdx
  __int64 v149; // r8
  unsigned int v150; // ecx
  __int64 v151; // rcx
  int v152; // ecx
  __int64 v165; // [rsp+58h] [rbp+0h] BYREF
  char v166; // [rsp+AF0h] [rbp+A98h] BYREF

  _RBP = (__int64 *)((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL);
  __asm { vmovups xmm0, xmmword ptr [r9] }
  _RBP[1] = (__int64)a3;
  *_RBP = a1;
  v9 = a1;
  __asm { vmovups xmmword ptr [rbp+0AD0h+var_AB0], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 736,
    2,
    1,
    a3,
    (_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 32),
    (_DWORD *)(a1 + 8));
  v10 = a2[1];
  v11 = a2[2];
  v12 = a2[3];
  if ( *a2 <= v10 )
    v10 = *a2;
  if ( v10 <= v11 )
    v11 = v10;
  if ( v11 <= v12 )
    v12 = v11;
  v13 = &v12[*(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E8)];
  *(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = v13;
  *(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = v13 + 1;
  *(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = v13 + 2;
  *(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v13 + 3;
  LOBYTE(v14) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)(_RBP + 94),
                  v12,
                  (unsigned __int8 **)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 32),
                  (unsigned __int8 **)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 16));
  if ( (_BYTE)v14 )
  {
    v15 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E0);
    v16 = 0;
    *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 2;
    v17 = 0;
    if ( v15 > 0 )
    {
      v18 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x318);
      v19 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310);
      v20 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310) = ++v19;
        if ( v19 == 1 )
        {
          v21 = *(_DWORD *)(v9 + 44);
          v22 = 0;
          v23 = *(_DWORD *)(v9 + 40);
          v24 = *(_DWORD *)(v9 + 28);
          v25 = *(int *)(v9 + 52);
          __asm { vmovups ymm0, [rbp+0AD0h+var_A90] }
          if ( *(int *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x314) <= 0 )
            v22 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x314);
          __asm { vmovups [rbp+0AD0h+var_AB0], ymm0 }
          v27 = v25 - 1;
          if ( v24 < v21 )
            v24 = v21;
          v28 = v24 - v21;
          if ( v18 < v23 )
            v18 = v23;
          v29 = v18 - v23;
          v30 = &v13[v16];
          v31 = v29 % *(_DWORD *)(v9 + 48);
          v32 = *(_QWORD *)(v9 + 56);
          v33 = v25 * v31;
          v34 = *(int *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90C);
          if ( v28 <= v27 )
            v27 = v28;
          v35 = v16 + *(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
          v36 = v16 + *(_QWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
          v37 = (_WORD *)(v32 + 2 * v33 + 2LL * v27);
          *v37 = (85
                * (v30[-4 * v22]
                 + *(unsigned __int8 *)(v35 + -4 * v22)
                 + (unsigned int)*(unsigned __int8 *)(v36 + -4 * v22))) >> 6;
          _R9 = v37 + 1;
          v39 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10 + 4 * v34) - v22;
          for ( i = (int)v34 + 1; i < 1; v39 += v43 )
          {
            if ( v39 >= v20 )
              break;
            v41 = 4 * v39;
            v42 = *(unsigned __int8 *)(v35 + v41) + *(unsigned __int8 *)(v36 + v41) + v30[v41];
            if ( v42 > 0x2F4 )
              v42 = *(unsigned __int8 *)(v35 + v41 - 4) + *(unsigned __int8 *)(v36 + v41 - 4) + v30[v41 - 4];
            *_R9++ = (85 * v42) >> 6;
            v43 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10 + 4 * i++);
          }
          v20 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
          v44 = v39 - 1;
          v45 = v20 - 63;
          if ( v39 - 1 < v20 - 63 )
          {
            __asm
            {
              vmovdqu ymm14, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
              vmovdqu ymm15, cs:__ymm@03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec
            }
            _RDI = 0;
            _R8 = &v13[4 * v44 + 144 + v16];
            v50 = ((unsigned int)(v45 - v39) >> 6) + 1;
            v44 += (_DWORD)v50 << 6;
            do
            {
              __asm
              {
                vmovups xmm0, xmmword ptr [r8+rdi-90h]
                vinsertf128 ymm7, ymm0, xmmword ptr [r8+rdi-10h], 1
                vmovups xmm1, xmmword ptr [r8-80h]
                vinsertf128 ymm9, ymm1, xmmword ptr [r8], 1
                vmovups xmm0, xmmword ptr [r8-70h]
                vinsertf128 ymm11, ymm0, xmmword ptr [r8+10h], 1
                vmovups xmm1, xmmword ptr [r8-60h]
                vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
                vmovups xmm0, xmmword ptr [r8-50h]
                vinsertf128 ymm2, ymm0, xmmword ptr [r8+rdi+30h], 1
                vmovups xmm1, xmmword ptr [r8-40h]
                vinsertf128 ymm3, ymm1, xmmword ptr [r8+40h], 1
                vmovups xmm0, xmmword ptr [r8-30h]
                vinsertf128 ymm4, ymm0, xmmword ptr [r8+50h], 1
                vmovups xmm1, xmmword ptr [r8-20h]
                vinsertf128 ymm5, ymm1, xmmword ptr [r8+60h], 1
                vpunpckhbw ymm8, ymm7, ymm2
                vpunpcklbw ymm0, ymm11, ymm4
                vpunpcklbw ymm6, ymm7, ymm2
                vpunpcklbw ymm7, ymm6, ymm0
                vpunpcklbw ymm10, ymm9, ymm3
                vpunpckhbw ymm1, ymm11, ymm4
                vpunpcklbw ymm11, ymm8, ymm1
                vpunpcklbw ymm2, ymm13, ymm5
                vpunpckhbw ymm12, ymm9, ymm3
                vpunpckhbw ymm9, ymm6, ymm0
                vpunpckhbw ymm4, ymm13, ymm5
                vpunpckhbw ymm13, ymm8, ymm1
                vpunpckhbw ymm1, ymm10, ymm2
                vpunpcklbw ymm8, ymm9, ymm1
                vpunpckhbw ymm9, ymm9, ymm1
                vpunpcklbw ymm0, ymm10, ymm2
                vpunpcklbw ymm6, ymm7, ymm0
                vpunpckhbw ymm7, ymm7, ymm0
                vpunpcklbw ymm3, ymm12, ymm4
                vpunpcklbw ymm1, ymm11, ymm3
                vpunpcklbw ymm0, ymm6, ymm1
                vpunpckhbw ymm1, ymm6, ymm1
                vpunpckhbw ymm2, ymm11, ymm3
                vmovdqu [rbp+0AD0h+var_A50], ymm1
                vmovdqu [rbp+0AD0h+var_A70], ymm0
                vpunpckhbw ymm5, ymm12, ymm4
                vpunpckhbw ymm1, ymm7, ymm2
                vpunpcklbw ymm0, ymm7, ymm2
                vpunpcklbw ymm4, ymm13, ymm5
                vmovdqu [rbp+0AD0h+var_A10], ymm1
                vmovdqu [rbp+0AD0h+var_A30], ymm0
                vpunpckhbw ymm1, ymm8, ymm4
                vpunpcklbw ymm0, ymm8, ymm4
                vpunpckhbw ymm3, ymm13, ymm5
                vmovdqu [rbp+0AD0h+var_9D0], ymm1
                vmovdqu [rbp+0AD0h+var_9F0], ymm0
                vpunpckhbw ymm1, ymm9, ymm3
                vpunpcklbw ymm0, ymm9, ymm3
                vmovdqu [rbp+0AD0h+var_990], ymm1
                vmovdqu [rbp+0AD0h+var_9B0], ymm0
              }
              _RAX = _RBP + 300;
              v100 = 2;
              _RCX = _RBP + 20;
              do
              {
                _RAX += 12;
                __asm
                {
                  vmovdqu ymm0, ymmword ptr [rcx-40h]
                  vmovdqu ymm1, ymmword ptr [rcx-20h]
                }
                _RCX += 16;
                __asm
                {
                  vmovdqu ymmword ptr [rax-0A0h], ymm0
                  vmovdqu ymm0, ymmword ptr [rcx-80h]
                  vmovdqu ymmword ptr [rax-60h], ymm0
                  vmovdqu ymmword ptr [rax-80h], ymm1
                }
                --v100;
              }
              while ( v100 );
              _RCX = _RBP + 296;
              v106 = 2;
              _RAX = _RBP + 48;
              do
              {
                _RAX += 24;
                __asm
                {
                  vmovdqu ymm3, ymmword ptr [rcx]
                  vmovdqu ymm1, ymmword ptr [rcx-20h]
                }
                _RCX += 12;
                __asm
                {
                  vpmovzxbw ymm0, xmm1
                  vextracti128 xmm1, ymm1, 1
                  vpmovzxbw ymm2, xmm1
                  vmovdqu ymmword ptr [rax-0E0h], ymm0
                  vextracti128 xmm1, ymm3, 1
                  vpmovzxbw ymm0, xmm3
                  vmovdqu ymm3, ymmword ptr [rcx-40h]
                  vmovdqu ymmword ptr [rax-80h], ymm2
                  vpmovzxbw ymm2, xmm1
                  vmovdqu ymmword ptr [rax-60h], ymm2
                  vmovdqu ymmword ptr [rax-0C0h], ymm0
                  vextracti128 xmm1, ymm3, 1
                  vpmovzxbw ymm2, xmm1
                  vpmovzxbw ymm0, xmm3
                  vmovdqu ymmword ptr [rax-40h], ymm2
                  vmovdqu ymmword ptr [rax-0A0h], ymm0
                }
                --v106;
              }
              while ( v106 );
              __asm
              {
                vmovdqu ymm0, [rbp+0AD0h+var_890]
                vpaddw  ymm1, ymm0, [rbp+0AD0h+var_8B0]
                vpaddw  ymm2, ymm1, [rbp+0AD0h+var_870]
                vmovdqu ymm0, [rbp+0AD0h+var_830]
                vpaddw  ymm1, ymm0, [rbp+0AD0h+var_850]
                vmovdqu ymm0, [rbp+0AD0h+var_950]
                vpmullw ymm3, ymm2, ymm14
                vpaddw  ymm2, ymm1, [rbp+0AD0h+var_810]
                vpaddw  ymm1, ymm0, [rbp+0AD0h+var_970]
                vpsrlw  ymm4, ymm3, 6
                vpmullw ymm3, ymm2, ymm14
                vpaddw  ymm2, ymm1, [rbp+0AD0h+var_930]
                vpsrlw  ymm7, ymm3, 6
                vpmullw ymm3, ymm2, ymm14
                vpcmpgtw ymm5, ymm4, ymm15
                vpsrlw  ymm0, ymm3, 6
                vpand   ymm1, ymm0, ymm5
                vmovdqu ymm0, [rbp+0AD0h+var_8F0]
                vpandn  ymm4, ymm5, ymm4
                vpaddw  ymm6, ymm1, ymm4
                vpaddw  ymm1, ymm0, [rbp+0AD0h+var_910]
                vpaddw  ymm2, ymm1, [rbp+0AD0h+var_8D0]
                vpmullw ymm3, ymm2, ymm14
                vpcmpgtw ymm5, ymm7, ymm15
                vmovdqu ymmword ptr [r9], ymm6
                vpsrlw  ymm0, ymm3, 6
                vpand   ymm1, ymm0, ymm5
                vpandn  ymm4, ymm5, ymm7
                vpaddw  ymm2, ymm1, ymm4
                vmovdqu ymmword ptr [r9+20h], ymm2
              }
              _R9 += 32;
              _R8 += 256;
              --v50;
            }
            while ( v50 );
            v20 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
          }
          v145 = v44 + 1;
          if ( v44 + 1 < v20 )
          {
            v146 = v36 - v35;
            v147 = &v30[-v35];
            v148 = (unsigned __int8 *)(v35 + 4 * v145 - 4LL);
            v149 = ((unsigned int)(v20 - v145 - 1) >> 1) + 1;
            do
            {
              v150 = v148[4] + v148[(_QWORD)v147 + 4] + v148[v146 + 4];
              if ( v150 > 0x2F4 )
                v150 = *v148 + v148[v146] + v148[(_QWORD)v147];
              v148 += 8;
              *_R9++ = (85 * v150) >> 6;
              --v149;
            }
            while ( v149 );
            v20 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
          }
          v151 = *(int *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4);
          v9 = *_RBP;
          v19 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310)
              - *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x31C + 4 * v151);
          v152 = v151 + 1;
          if ( v152 >= *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8FC) )
            v152 = 0;
          v18 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x318) + 1;
          *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4) = v152;
          v15 = *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E0);
          *(_DWORD *)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 0x318) = v18;
        }
        ++v17;
        v14 = **(int **)(((unsigned __int64)&v165 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        v16 += v14;
      }
      while ( v17 < v15 );
    }
  }
  __asm { vzeroupper }
  _R11 = &v166;
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
  return v14;
}

```

## disassembly

```asm
0x1800978a0  mov     rax, rsp
0x1800978a3  push    rbp
0x1800978a4  push    rbx
0x1800978a5  push    rsi
0x1800978a6  push    rdi
0x1800978a7  push    r12
0x1800978a9  push    r13
0x1800978ab  push    r14
0x1800978ad  push    r15
0x1800978af  sub     rsp, 0AE8h
0x1800978b6  vmovaps xmmword ptr [rax-58h], xmm6
0x1800978bb  vmovaps xmmword ptr [rax-68h], xmm7
0x1800978c0  vmovaps xmmword ptr [rax-78h], xmm8
0x1800978c5  vmovaps xmmword ptr [rax-88h], xmm9
0x1800978cd  vmovaps xmmword ptr [rax-98h], xmm10
0x1800978d5  vmovaps xmmword ptr [rax-0A8h], xmm11
0x1800978dd  vmovaps xmmword ptr [rax-0B8h], xmm12
0x1800978e5  vmovaps xmmword ptr [rax-0C8h], xmm13
0x1800978ed  vmovaps xmmword ptr [rax-0D8h], xmm14
0x1800978f5  vmovaps xmmword ptr [rax-0E8h], xmm15
0x1800978fd  lea     rbp, [rsp+0B20h+var_AD0]
0x180097902  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180097906  mov     rax, cs:__security_cookie
0x18009790d  xor     rax, rsp
0x180097910  mov     [rbp+0AD0h+var_F0], rax
0x180097917  vmovups xmm0, xmmword ptr [r9]
0x18009791c  lea     rax, [rcx+8]
0x180097920  mov     [rbp+0AD0h+var_AC8], r8
0x180097924  mov     [rsp+0B20h+var_AF8], rax
0x180097929  mov     rbx, rdx
0x18009792c  mov     edx, 2
0x180097931  mov     [rbp+0AD0h+var_AD0], rcx
0x180097935  mov     r14, rcx
0x180097938  lea     rax, [rbp+0AD0h+var_AB0]
0x18009793c  mov     r9, r8
0x18009793f  mov     [rsp+0B20h+var_B00], rax
0x180097944  lea     rcx, [rbp+0AD0h+var_7F0]
0x18009794b  lea     r8d, [rdx-1]
0x18009794f  vmovups xmmword ptr [rbp+0AD0h+var_AB0], xmm0
0x180097954  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180097959  mov     rcx, [rbx+8]
0x18009795d  lea     r9, [rbp+0AD0h+var_AC0]; unsigned __int8 **
0x180097961  mov     rax, [rbx+10h]
0x180097965  lea     r8, [rbp+0AD0h+var_AB0]; unsigned __int8 **
0x180097969  mov     rdx, [rbx+18h]
0x18009796d  xor     r15d, r15d
0x180097970  cmp     [rbx], rcx
0x180097973  cmovbe  rcx, [rbx]
0x180097977  mov     rbx, [rbp+0AD0h+var_7E8]
0x18009797e  cmp     rcx, rax
0x180097981  cmovbe  rax, rcx
0x180097985  lea     rcx, [rbp+0AD0h+var_7E0]; this
0x18009798c  cmp     rax, rdx
0x18009798f  cmovbe  rdx, rax; unsigned __int8 *
0x180097993  add     rbx, rdx
0x180097996  mov     qword ptr [rbp+0AD0h+var_A90], rbx
0x18009799a  lea     rax, [rbx+1]
0x18009799e  mov     qword ptr [rbp+0AD0h+var_A90+8], rax
0x1800979a2  lea     rax, [rbx+2]
0x1800979a6  mov     qword ptr [rbp+0AD0h+var_A90+10h], rax
0x1800979aa  lea     rax, [rbx+3]
0x1800979ae  mov     qword ptr [rbp+0AD0h+var_A90+18h], rax
0x1800979b2  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800979b7  test    al, al
0x1800979b9  jz      loc_180097F23
0x1800979bf  mov     ecx, [rbp+0AD0h+var_7F0]
0x1800979c5  mov     r12d, r15d
0x1800979c8  mov     dword ptr [rbp+0AD0h+var_AC0], 2
0x1800979cf  mov     r13d, r15d
0x1800979d2  test    ecx, ecx
0x1800979d4  jle     loc_180097F23
0x1800979da  mov     esi, [rbp+0AD0h+var_7B8]
0x1800979e0  mov     edx, [rbp+0AD0h+var_7C0]
0x1800979e6  mov     edi, [rbp+0AD0h+var_7EC]
0x1800979ec  nop     dword ptr [rax+00h]
0x1800979f0  inc     edx
0x1800979f2  mov     [rbp+0AD0h+var_7C0], edx
0x1800979f8  cmp     edx, 1
0x1800979fb  jnz     loc_180097F0D
0x180097a01  mov     ecx, [r14+2Ch]
0x180097a05  mov     r11d, r15d
0x180097a08  mov     edx, [r14+28h]
0x180097a0c  mov     r10d, [r14+1Ch]
0x180097a10  mov     eax, [rbp+0AD0h+var_7BC]
0x180097a16  test    eax, eax
0x180097a18  movsxd  r8, dword ptr [r14+34h]
0x180097a1c  vmovups ymm0, [rbp+0AD0h+var_A90]
0x180097a21  cmovle  r11d, eax
0x180097a25  cmp     r10d, ecx
0x180097a28  vmovups [rbp+0AD0h+var_AB0], ymm0
0x180097a2d  mov     r15, qword ptr [rbp+0AD0h+var_AB0+8]
0x180097a31  lea     r9d, [r8-1]
0x180097a35  cmovl   r10d, ecx
0x180097a39  sub     r10d, ecx
0x180097a3c  cmp     esi, edx
0x180097a3e  cmovl   esi, edx
0x180097a41  sub     esi, edx
0x180097a43  mov     eax, esi
0x180097a45  lea     rsi, [rbx+r12]
0x180097a49  cdq
0x180097a4a  idiv    dword ptr [r14+30h]
0x180097a4e  mov     rax, [r14+38h]
0x180097a52  mov     r14, qword ptr [rbp+0AD0h+var_AB0+10h]
0x180097a56  movsxd  rcx, edx
0x180097a59  imul    rcx, r8
0x180097a5d  movsxd  r8, [rbp+0AD0h+var_1C4]
0x180097a64  cmp     r10d, r9d
0x180097a67  cmovle  r9d, r10d
0x180097a6b  add     r15, r12
0x180097a6e  add     r14, r12
0x180097a71  lea     rax, [rax+rcx*2]
0x180097a75  movsxd  rcx, r9d
0x180097a78  lea     r9, [rax+rcx*2]
0x180097a7c  mov     eax, r11d
0x180097a7f  neg     eax
0x180097a81  shl     eax, 2
0x180097a84  movsxd  rcx, eax
0x180097a87  movzx   eax, byte ptr [r15+rcx]
0x180097a8c  movzx   edx, byte ptr [r14+rcx]
0x180097a91  add     edx, eax
0x180097a93  movzx   eax, byte ptr [rsi+rcx]
0x180097a97  add     edx, eax
0x180097a99  imul    eax, edx, 55h ; 'U'
0x180097a9c  shr     eax, 6
0x180097a9f  mov     [r9], ax
0x180097aa3  lea     eax, [r8+1]
0x180097aa7  mov     edx, dword ptr [rbp+r8*4+0AD0h+var_AC0]
0x180097aac  add     r9, 2
0x180097ab0  sub     edx, r11d
0x180097ab3  movsxd  r10, eax
0x180097ab6  cmp     r10, 1
0x180097aba  jge     short loc_180097B1D
0x180097abc  nop     dword ptr [rax+00h]
0x180097ac0  cmp     edx, edi
0x180097ac2  jge     short loc_180097B1D
0x180097ac4  lea     eax, ds:0[rdx*4]
0x180097acb  movsxd  r8, eax
0x180097ace  movzx   eax, byte ptr [r14+r8]
0x180097ad3  movzx   ecx, byte ptr [r8+rsi]
0x180097ad8  add     ecx, eax
0x180097ada  movzx   eax, byte ptr [r15+r8]
0x180097adf  add     ecx, eax
0x180097ae1  cmp     ecx, 2F4h
0x180097ae7  jbe     short loc_180097AFF
0x180097ae9  movzx   eax, byte ptr [r14+r8-4]
0x180097aef  movzx   ecx, byte ptr [r8+rsi-4]
0x180097af5  add     ecx, eax
0x180097af7  movzx   eax, byte ptr [r15+r8-4]
0x180097afd  add     ecx, eax
0x180097aff  imul    eax, ecx, 55h ; 'U'
0x180097b02  shr     eax, 6
0x180097b05  mov     [r9], ax
0x180097b09  add     r9, 2
0x180097b0d  mov     eax, dword ptr [rbp+r10*4+0AD0h+var_AC0]
0x180097b12  inc     r10
0x180097b15  add     edx, eax
0x180097b17  cmp     r10, 1
0x180097b1b  jl      short loc_180097AC0
0x180097b1d  mov     edi, [rbp+0AD0h+var_7EC]
0x180097b23  lea     r10d, [rdx-1]
0x180097b27  lea     ecx, [rdi-3Fh]
0x180097b2a  cmp     r10d, ecx
0x180097b2d  jge     loc_180097E46
0x180097b33  vmovdqu ymm14, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
0x180097b3b  vmovdqu ymm15, cs:__ymm@03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec03ec
0x180097b43  sub     ecx, r10d
0x180097b46  movsxd  r8, r10d
0x180097b49  add     r8, 24h ; '$'
0x180097b4d  mov     rdi, rsi
0x180097b50  sub     rdi, rbx
0x180097b53  sub     rdi, r12
0x180097b56  lea     eax, [rcx-1]
0x180097b59  shr     eax, 6
0x180097b5c  lea     r8, [rbx+r8*4]
0x180097b60  inc     eax
0x180097b62  add     r8, r12
0x180097b65  mov     r11d, eax
0x180097b68  shl     eax, 6
0x180097b6b  add     r10d, eax
0x180097b6e  xchg    ax, ax
0x180097b70  vmovups xmm0, xmmword ptr [r8+rdi-90h]
0x180097b7a  vinsertf128 ymm7, ymm0, xmmword ptr [r8+rdi-10h], 1
0x180097b82  vmovups xmm1, xmmword ptr [r8-80h]
0x180097b88  vinsertf128 ymm9, ymm1, xmmword ptr [r8], 1
0x180097b8e  vmovups xmm0, xmmword ptr [r8-70h]
0x180097b94  vinsertf128 ymm11, ymm0, xmmword ptr [r8+10h], 1
0x180097b9b  vmovups xmm1, xmmword ptr [r8-60h]
0x180097ba1  vinsertf128 ymm13, ymm1, xmmword ptr [r8+20h], 1
0x180097ba8  vmovups xmm0, xmmword ptr [r8-50h]
0x180097bae  vinsertf128 ymm2, ymm0, xmmword ptr [r8+rdi+30h], 1
0x180097bb6  vmovups xmm1, xmmword ptr [r8-40h]
0x180097bbc  vinsertf128 ymm3, ymm1, xmmword ptr [r8+40h], 1
0x180097bc3  vmovups xmm0, xmmword ptr [r8-30h]
0x180097bc9  vinsertf128 ymm4, ymm0, xmmword ptr [r8+50h], 1
0x180097bd0  vmovups xmm1, xmmword ptr [r8-20h]
0x180097bd6  vinsertf128 ymm5, ymm1, xmmword ptr [r8+60h], 1
0x180097bdd  vpunpckhbw ymm8, ymm7, ymm2
0x180097be1  vpunpcklbw ymm0, ymm11, ymm4
0x180097be5  vpunpcklbw ymm6, ymm7, ymm2
0x180097be9  vpunpcklbw ymm7, ymm6, ymm0
0x180097bed  vpunpcklbw ymm10, ymm9, ymm3
0x180097bf1  vpunpckhbw ymm1, ymm11, ymm4
0x180097bf5  vpunpcklbw ymm11, ymm8, ymm1
0x180097bf9  vpunpcklbw ymm2, ymm13, ymm5
0x180097bfd  vpunpckhbw ymm12, ymm9, ymm3
0x180097c01  vpunpckhbw ymm9, ymm6, ymm0
0x180097c05  vpunpckhbw ymm4, ymm13, ymm5
0x180097c09  vpunpckhbw ymm13, ymm8, ymm1
0x180097c0d  vpunpckhbw ymm1, ymm10, ymm2
0x180097c11  vpunpcklbw ymm8, ymm9, ymm1
0x180097c15  vpunpckhbw ymm9, ymm9, ymm1
0x180097c19  vpunpcklbw ymm0, ymm10, ymm2
0x180097c1d  vpunpcklbw ymm6, ymm7, ymm0
0x180097c21  vpunpckhbw ymm7, ymm7, ymm0
0x180097c25  vpunpcklbw ymm3, ymm12, ymm4
0x180097c29  vpunpcklbw ymm1, ymm11, ymm3
0x180097c2d  vpunpcklbw ymm0, ymm6, ymm1
0x180097c31  vpunpckhbw ymm1, ymm6, ymm1
0x180097c35  vpunpckhbw ymm2, ymm11, ymm3
0x180097c39  vmovdqu [rbp+0AD0h+var_A50], ymm1
0x180097c41  vmovdqu [rbp+0AD0h+var_A70], ymm0
0x180097c46  vpunpckhbw ymm5, ymm12, ymm4
0x180097c4a  vpunpckhbw ymm1, ymm7, ymm2
0x180097c4e  vpunpcklbw ymm0, ymm7, ymm2
0x180097c52  vpunpcklbw ymm4, ymm13, ymm5
0x180097c56  vmovdqu [rbp+0AD0h+var_A10], ymm1
0x180097c5e  vmovdqu [rbp+0AD0h+var_A30], ymm0
0x180097c66  vpunpckhbw ymm1, ymm8, ymm4
0x180097c6a  vpunpcklbw ymm0, ymm8, ymm4
0x180097c6e  vpunpckhbw ymm3, ymm13, ymm5
0x180097c72  vmovdqu [rbp+0AD0h+var_9D0], ymm1
0x180097c7a  vmovdqu [rbp+0AD0h+var_9F0], ymm0
0x180097c82  vpunpckhbw ymm1, ymm9, ymm3
0x180097c86  vpunpcklbw ymm0, ymm9, ymm3
0x180097c8a  vmovdqu [rbp+0AD0h+var_990], ymm1
0x180097c92  vmovdqu [rbp+0AD0h+var_9B0], ymm0
0x180097c9a  lea     rax, [rbp+0AD0h+var_170]
0x180097ca1  mov     edx, 2
0x180097ca6  lea     rcx, [rbp+0AD0h+var_A30]
0x180097cad  nop     dword ptr [rax]
0x180097cb0  lea     rax, [rax+60h]
0x180097cb4  vmovdqu ymm0, ymmword ptr [rcx-40h]
0x180097cb9  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x180097cbe  lea     rcx, [rcx+80h]
0x180097cc5  vmovdqu ymmword ptr [rax-0A0h], ymm0
0x180097ccd  vmovdqu ymm0, ymmword ptr [rcx-80h]
0x180097cd2  vmovdqu ymmword ptr [rax-60h], ymm0
0x180097cd7  vmovdqu ymmword ptr [rax-80h], ymm1
0x180097cdc  sub     rdx, 1
0x180097ce0  jnz     short loc_180097CB0
0x180097ce2  lea     rcx, [rbp+0AD0h+var_190]
0x180097ce9  mov     edx, 2
0x180097cee  lea     rax, [rbp+0AD0h+var_950]
0x180097cf5  nop     word ptr [rax+rax+00000000h]
0x180097d00  lea     rax, [rax+0C0h]
0x180097d07  vmovdqu ymm3, ymmword ptr [rcx]
0x180097d0b  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x180097d10  lea     rcx, [rcx+60h]
0x180097d14  vpmovzxbw ymm0, xmm1
0x180097d19  vextracti128 xmm1, ymm1, 1
0x180097d1f  vpmovzxbw ymm2, xmm1
0x180097d24  vmovdqu ymmword ptr [rax-0E0h], ymm0
0x180097d2c  vextracti128 xmm1, ymm3, 1
0x180097d32  vpmovzxbw ymm0, xmm3
0x180097d37  vmovdqu ymm3, ymmword ptr [rcx-40h]
0x180097d3c  vmovdqu ymmword ptr [rax-80h], ymm2
0x180097d41  vpmovzxbw ymm2, xmm1
0x180097d46  vmovdqu ymmword ptr [rax-60h], ymm2
0x180097d4b  vmovdqu ymmword ptr [rax-0C0h], ymm0
0x180097d53  vextracti128 xmm1, ymm3, 1
0x180097d59  vpmovzxbw ymm2, xmm1
0x180097d5e  vpmovzxbw ymm0, xmm3
0x180097d63  vmovdqu ymmword ptr [rax-40h], ymm2
0x180097d68  vmovdqu ymmword ptr [rax-0A0h], ymm0
0x180097d70  sub     rdx, 1
0x180097d74  jnz     short loc_180097D00
0x180097d76  vmovdqu ymm0, [rbp+0AD0h+var_890]
0x180097d7e  vpaddw  ymm1, ymm0, [rbp+0AD0h+var_8B0]
0x180097d86  vpaddw  ymm2, ymm1, [rbp+0AD0h+var_870]
0x180097d8e  vmovdqu ymm0, [rbp+0AD0h+var_830]
0x180097d96  vpaddw  ymm1, ymm0, [rbp+0AD0h+var_850]
0x180097d9e  vmovdqu ymm0, [rbp+0AD0h+var_950]
0x180097da6  vpmullw ymm3, ymm2, ymm14
0x180097dab  vpaddw  ymm2, ymm1, [rbp+0AD0h+var_810]
0x180097db3  vpaddw  ymm1, ymm0, [rbp+0AD0h+var_970]
0x180097dbb  vpsrlw  ymm4, ymm3, 6
0x180097dc0  vpmullw ymm3, ymm2, ymm14
0x180097dc5  vpaddw  ymm2, ymm1, [rbp+0AD0h+var_930]
0x180097dcd  vpsrlw  ymm7, ymm3, 6
0x180097dd2  vpmullw ymm3, ymm2, ymm14
0x180097dd7  vpcmpgtw ymm5, ymm4, ymm15
0x180097ddc  vpsrlw  ymm0, ymm3, 6
0x180097de1  vpand   ymm1, ymm0, ymm5
0x180097de5  vmovdqu ymm0, [rbp+0AD0h+var_8F0]
0x180097ded  vpandn  ymm4, ymm5, ymm4
0x180097df1  vpaddw  ymm6, ymm1, ymm4
0x180097df5  vpaddw  ymm1, ymm0, [rbp+0AD0h+var_910]
0x180097dfd  vpaddw  ymm2, ymm1, [rbp+0AD0h+var_8D0]
0x180097e05  vpmullw ymm3, ymm2, ymm14
0x180097e0a  vpcmpgtw ymm5, ymm7, ymm15
  ... truncated ...
```
