# Binary::IntegratedSelection::DerivativeServer<4,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,4,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x1800971d0`
- end: `0x180097898`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$02$03$00$00$0A@V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$03$00$00V?$MixedResponse@$02$0A@$07$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `1736`
- prototype: `char __fastcall(__int64, unsigned __int8 **, __int64, __int64 _R9)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180099bf0`

## callees

- `0x180003180`
- `0x180067110`
- `0x1800963a0`
- `0x1800971d0`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<4,1,1,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<3,4,1,1,0,Binary::IntegratedSelection::MixedResponse<3,0,8,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        __int64 a3,
        __int64 _R9)
{
  __int64 v10; // r15
  unsigned __int8 *v11; // rcx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rdx
  unsigned __int8 *v14; // rbx
  int v15; // eax
  __int64 v16; // r13
  int v18; // edi
  int v19; // r14d
  int v20; // esi
  int v21; // ecx
  int v22; // r11d
  int v23; // r10d
  __int64 v24; // r8
  int v25; // eax
  int v26; // r9d
  int v27; // r10d
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // r12
  __int64 v31; // rax
  unsigned __int8 *v32; // r10
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // r11d
  __int64 v37; // r15
  int v39; // eax
  int v40; // ecx
  __int64 v44; // rdi
  __int64 v102; // rdx
  __int64 v120; // rdx
  __int64 v143; // r15
  unsigned __int8 *v144; // r10
  __int64 v145; // rdx
  __int64 v146; // r9
  int v147; // eax
  int v148; // ecx
  __int64 v149; // rax
  __int64 v162; // [rsp+58h] [rbp+0h] BYREF
  char v163; // [rsp+C30h] [rbp+BD8h] BYREF

  _RBP = (__int64 *)((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL);
  __asm { vmovups xmm0, xmmword ptr [r9] }
  _RBP[1] = a3;
  *_RBP = a1;
  v10 = a1;
  __asm { vmovups xmmword ptr [rbp+0C10h+var_BF0], xmm0 }
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
    ((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 736,
    1,
    1,
    a3,
    ((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 32,
    a1 + 8);
  v11 = a2[1];
  v12 = a2[2];
  v13 = a2[3];
  if ( *a2 <= v11 )
    v11 = *a2;
  if ( v11 <= v12 )
    v12 = v11;
  if ( v12 <= v13 )
    v13 = v12;
  v14 = &v13[*(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E8)];
  *(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = v14;
  *(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = v14 + 1;
  *(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = v14 + 2;
  *(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = v14 + 3;
  LOBYTE(v15) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)(_RBP + 94),
                  v13,
                  (unsigned __int8 **)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 16),
                  (unsigned __int8 **)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 32));
  if ( (_BYTE)v15 )
  {
    v16 = 0;
    *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 1;
    *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    if ( *(int *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E0) > 0 )
    {
      __asm { vmovups ymm15, [rbp+0C10h+var_BE0] }
      v18 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4);
      v19 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310);
      v20 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
      do
      {
        *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310) = ++v19;
        if ( v19 == 1 )
        {
          v21 = *(_DWORD *)(v10 + 40);
          v22 = 0;
          v23 = *(_DWORD *)(v10 + 28);
          v24 = *(int *)(v10 + 52);
          if ( *(int *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x314) <= 0 )
            v22 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x314);
          v25 = *(_DWORD *)(v10 + 44);
          __asm { vmovups [rbp+0C10h+var_BE0], ymm15 }
          v26 = v24 - 1;
          if ( v23 < v25 )
            v23 = v25;
          v27 = v23 - v25;
          v28 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x318);
          if ( v28 < v21 )
            v28 = v21;
          v29 = v24 * ((v28 - v21) % *(_DWORD *)(v10 + 48));
          if ( v27 <= v26 )
            v26 = v27;
          v30 = v16 + *(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
          v31 = v26;
          v32 = &v14[v16];
          v33 = *(int *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90C);
          v34 = v31 + v29;
          v35 = *(_QWORD *)(v10 + 56);
          v36 = -v22;
          v37 = v16 + *(_QWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
          _R8 = (_WORD *)(v35 + 2 * v34);
          if ( v33 < 1 )
          {
            do
            {
              if ( v36 >= v20 )
                break;
              *_R8++ = (85
                      * (v32[4 * v36]
                       + *(unsigned __int8 *)(v30 + 4 * v36)
                       + (unsigned int)*(unsigned __int8 *)(v37 + 4 * v36))) >> 6;
              v39 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20 + 4 * v33++);
              v36 += v39;
            }
            while ( v33 < 1 );
            v18 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4);
            v19 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310);
            v20 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
          }
          v40 = v20 - 63;
          if ( v36 < v20 - 63 )
          {
            __asm { vmovdqu ymm14, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055 }
            _RSI = 0;
            _R9 = &v14[4 * v36 + 80 + v16];
            v44 = ((unsigned int)(v40 - v36 - 1) >> 6) + 1;
            v36 += (_DWORD)v44 << 6;
            do
            {
              __asm
              {
                vmovups xmm0, xmmword ptr [rsi+r9-50h]
                vinsertf128 ymm7, ymm0, xmmword ptr [r9-10h], 1
                vmovups xmm1, xmmword ptr [r9-40h]
                vinsertf128 ymm9, ymm1, xmmword ptr [r9], 1
                vmovups xmm0, xmmword ptr [r9-30h]
                vinsertf128 ymm11, ymm0, xmmword ptr [r9+10h], 1
                vmovups xmm1, xmmword ptr [r9-20h]
                vinsertf128 ymm13, ymm1, xmmword ptr [r9+20h], 1
                vmovups xmm0, xmmword ptr [r9+30h]
                vinsertf128 ymm2, ymm0, xmmword ptr [r9+70h], 1
                vmovups xmm1, xmmword ptr [r9+40h]
                vinsertf128 ymm3, ymm1, xmmword ptr [r9+80h], 1
                vmovups xmm0, xmmword ptr [r9+50h]
                vinsertf128 ymm4, ymm0, xmmword ptr [r9+90h], 1
                vmovups xmm1, xmmword ptr [r9+60h]
                vinsertf128 ymm5, ymm1, xmmword ptr [r9+0A0h], 1
                vpunpckhbw ymm8, ymm7, ymm2
                vpunpcklbw ymm6, ymm7, ymm2
                vpunpcklbw ymm10, ymm9, ymm3
                vpunpcklbw ymm0, ymm11, ymm4
                vpunpcklbw ymm7, ymm6, ymm0
                vpunpcklbw ymm2, ymm13, ymm5
                vpunpckhbw ymm12, ymm9, ymm3
                vpunpckhbw ymm9, ymm6, ymm0
                vpunpcklbw ymm0, ymm10, ymm2
                vpunpcklbw ymm6, ymm7, ymm0
                vpunpckhbw ymm1, ymm11, ymm4
                vpunpcklbw ymm11, ymm8, ymm1
                vpunpckhbw ymm4, ymm13, ymm5
                vpunpckhbw ymm13, ymm8, ymm1
                vpunpckhbw ymm8, ymm7, ymm0
                vpunpckhbw ymm1, ymm10, ymm2
                vpunpcklbw ymm10, ymm9, ymm1
                vpunpcklbw ymm3, ymm12, ymm4
                vpunpckhbw ymm5, ymm12, ymm4
                vpunpckhbw ymm12, ymm9, ymm1
                vpunpckhbw ymm1, ymm11, ymm3
                vpunpcklbw ymm9, ymm8, ymm1
                vpunpckhbw ymm8, ymm8, ymm1
                vpunpcklbw ymm0, ymm11, ymm3
                vpunpcklbw ymm7, ymm6, ymm0
                vpunpckhbw ymm6, ymm6, ymm0
                vpunpcklbw ymm2, ymm13, ymm5
                vpunpcklbw ymm1, ymm10, ymm2
                vpunpcklbw ymm0, ymm7, ymm1
                vpunpckhbw ymm1, ymm7, ymm1
                vmovdqu [rbp+0C10h+var_B30], ymm1
                vmovdqu [rbp+0C10h+var_BB0], ymm0
                vpunpckhbw ymm2, ymm10, ymm2
                vpunpckhbw ymm4, ymm13, ymm5
                vpunpckhbw ymm1, ymm6, ymm2
                vpunpcklbw ymm0, ymm6, ymm2
                vpunpcklbw ymm3, ymm12, ymm4
                vmovdqu [rbp+0C10h+var_B10], ymm1
                vmovdqu [rbp+0C10h+var_B90], ymm0
                vpunpckhbw ymm1, ymm9, ymm3
                vpunpcklbw ymm0, ymm9, ymm3
                vpunpckhbw ymm5, ymm12, ymm4
                vmovdqu [rbp+0C10h+var_AF0], ymm1
                vmovdqu [rbp+0C10h+var_B70], ymm0
                vpunpckhbw ymm1, ymm8, ymm5
                vpunpcklbw ymm0, ymm8, ymm5
                vmovdqu [rbp+0C10h+var_AD0], ymm1
                vmovdqu [rbp+0C10h+var_B50], ymm0
              }
              _RCX = _RBP + 16;
              v102 = 2;
              _RAX = _RBP + 296;
              do
              {
                _RAX += 32;
                __asm
                {
                  vmovdqu ymm3, ymmword ptr [rcx]
                  vmovdqu ymm1, ymmword ptr [rcx-20h]
                }
                _RCX += 16;
                __asm
                {
                  vpmovzxbw ymm0, xmm1
                  vextracti128 xmm1, ymm1, 1
                  vpmovzxbw ymm2, xmm1
                  vmovdqu ymmword ptr [rax-120h], ymm0
                  vextracti128 xmm1, ymm3, 1
                  vpmovzxbw ymm0, xmm3
                  vmovdqu ymm3, ymmword ptr [rcx-60h]
                  vmovdqu ymmword ptr [rax-0A0h], ymm2
                  vpmovzxbw ymm2, xmm1
                  vmovdqu ymmword ptr [rax-100h], ymm0
                  vpmovzxbw ymm0, xmm3
                  vextracti128 xmm1, ymm3, 1
                  vmovdqu ymm3, ymmword ptr [rcx-40h]
                  vmovdqu ymmword ptr [rax-80h], ymm2
                  vpmovzxbw ymm2, xmm1
                  vmovdqu ymmword ptr [rax-60h], ymm2
                  vmovdqu ymmword ptr [rax-0E0h], ymm0
                  vextracti128 xmm1, ymm3, 1
                  vpmovzxbw ymm2, xmm1
                  vpmovzxbw ymm0, xmm3
                  vmovdqu ymmword ptr [rax-40h], ymm2
                  vmovdqu ymmword ptr [rax-0C0h], ymm0
                }
                --v102;
              }
              while ( v102 );
              _RAX = _RBP + 52;
              v120 = 4;
              _RCX = _RBP + 300;
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
                --v120;
              }
              while ( v120 );
              __asm
              {
                vmovdqu ymm0, [rbp+0C10h+var_A90]
                vpaddw  ymm1, ymm0, [rbp+0C10h+var_AB0]
                vpaddw  ymm2, ymm1, [rbp+0C10h+var_A70]
                vmovdqu ymm0, [rbp+0C10h+var_A30]
                vpaddw  ymm1, ymm0, [rbp+0C10h+var_A50]
                vmovdqu ymm0, [rbp+0C10h+var_9D0]
                vpmullw ymm3, ymm2, ymm14
                vpaddw  ymm2, ymm1, [rbp+0C10h+var_A10]
                vpaddw  ymm1, ymm0, [rbp+0C10h+var_9F0]
                vmovdqu ymm0, [rbp+0C10h+var_970]
                vpsrlw  ymm6, ymm3, 6
                vpmullw ymm3, ymm2, ymm14
                vpaddw  ymm2, ymm1, [rbp+0C10h+var_9B0]
                vpaddw  ymm1, ymm0, [rbp+0C10h+var_990]
                vmovdqu ymmword ptr [r8], ymm6
                vpsrlw  ymm5, ymm3, 6
                vpmullw ymm3, ymm2, ymm14
                vpaddw  ymm2, ymm1, [rbp+0C10h+var_950]
                vmovdqu ymmword ptr [r8+20h], ymm5
                vpsrlw  ymm4, ymm3, 6
                vmovdqu ymmword ptr [r8+40h], ymm4
                vpmullw ymm3, ymm2, ymm14
                vpsrlw  ymm0, ymm3, 6
                vmovdqu ymmword ptr [r8+60h], ymm0
              }
              _R8 += 64;
              _R9 += 256;
              --v44;
            }
            while ( v44 );
            v18 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4);
            v19 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310);
            v20 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
          }
          if ( v36 < v20 )
          {
            v143 = v37 - v30;
            v144 = &v32[-v30];
            v145 = v30 + 4 * v36;
            v146 = (unsigned int)(v20 - v36);
            do
            {
              v147 = v144[v145];
              ++_R8;
              v148 = *(unsigned __int8 *)(v143 + v145);
              v145 += 4;
              *(_R8 - 1) = (85 * ((unsigned int)*(unsigned __int8 *)(v145 - 4) + v147 + v148)) >> 6;
              --v146;
            }
            while ( v146 );
            v18 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4);
            v19 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x310);
            v20 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E4);
          }
          v10 = *_RBP;
          v149 = v18++;
          v19 -= *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x31C + 4 * v149);
          if ( v18 >= *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8FC) )
            v18 = 0;
          ++*(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x318);
          *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8F4) = v18;
        }
        v16 += **(int **)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        v15 = *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) + 1;
        *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = v15;
      }
      while ( v15 < *(_DWORD *)(((unsigned __int64)&v162 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2E0) );
    }
  }
  __asm { vzeroupper }
  _R11 = &v163;
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
  return v15;
}

```

## disassembly

```asm
0x1800971d0  mov     rax, rsp
0x1800971d3  push    rbp
0x1800971d4  push    rbx
0x1800971d5  push    rsi
0x1800971d6  push    rdi
0x1800971d7  push    r12
0x1800971d9  push    r13
0x1800971db  push    r14
0x1800971dd  push    r15
0x1800971df  sub     rsp, 0C28h
0x1800971e6  vmovaps xmmword ptr [rax-58h], xmm6
0x1800971eb  vmovaps xmmword ptr [rax-68h], xmm7
0x1800971f0  vmovaps xmmword ptr [rax-78h], xmm8
0x1800971f5  vmovaps xmmword ptr [rax-88h], xmm9
0x1800971fd  vmovaps xmmword ptr [rax-98h], xmm10
0x180097205  vmovaps xmmword ptr [rax-0A8h], xmm11
0x18009720d  vmovaps xmmword ptr [rax-0B8h], xmm12
0x180097215  vmovaps xmmword ptr [rax-0C8h], xmm13
0x18009721d  vmovaps xmmword ptr [rax-0D8h], xmm14
0x180097225  vmovaps xmmword ptr [rax-0E8h], xmm15
0x18009722d  lea     rbp, [rsp+0C60h+var_C10]
0x180097232  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180097236  mov     rax, cs:__security_cookie
0x18009723d  xor     rax, rsp
0x180097240  mov     [rbp+0C10h+var_F0], rax
0x180097247  vmovups xmm0, xmmword ptr [r9]
0x18009724c  lea     rax, [rcx+8]
0x180097250  mov     [rbp+0C10h+var_C08], r8
0x180097254  mov     [rsp+0C60h+var_C38], rax
0x180097259  mov     rbx, rdx
0x18009725c  mov     edx, 1
0x180097261  mov     [rbp+0C10h+var_C10], rcx
0x180097265  lea     rax, [rbp+0C10h+var_BF0]
0x180097269  mov     r15, rcx
0x18009726c  mov     r9, r8
0x18009726f  mov     [rsp+0C60h+var_C40], rax
0x180097274  mov     r8d, edx
0x180097277  lea     rcx, [rbp+0C10h+var_930]
0x18009727e  vmovups xmmword ptr [rbp+0C10h+var_BF0], xmm0
0x180097283  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x180097288  mov     rcx, [rbx+8]
0x18009728c  lea     r9, [rbp+0C10h+var_BF0]; unsigned __int8 **
0x180097290  mov     rax, [rbx+10h]
0x180097294  lea     r8, [rbp+0C10h+var_C00]; unsigned __int8 **
0x180097298  mov     rdx, [rbx+18h]
0x18009729c  xor     r12d, r12d
0x18009729f  cmp     [rbx], rcx
0x1800972a2  cmovbe  rcx, [rbx]
0x1800972a6  mov     rbx, [rbp+0C10h+var_928]
0x1800972ad  cmp     rcx, rax
0x1800972b0  cmovbe  rax, rcx
0x1800972b4  lea     rcx, [rbp+0C10h+var_920]; this
0x1800972bb  cmp     rax, rdx
0x1800972be  cmovbe  rdx, rax; unsigned __int8 *
0x1800972c2  add     rbx, rdx
0x1800972c5  mov     qword ptr [rbp+0C10h+var_BE0], rbx
0x1800972c9  lea     rax, [rbx+1]
0x1800972cd  mov     qword ptr [rbp+0C10h+var_BE0+8], rax
0x1800972d1  lea     rax, [rbx+2]
0x1800972d5  mov     qword ptr [rbp+0C10h+var_BE0+10h], rax
0x1800972d9  lea     rax, [rbx+3]
0x1800972dd  mov     qword ptr [rbp+0C10h+var_BE0+18h], rax
0x1800972e1  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x1800972e6  test    al, al
0x1800972e8  jz      loc_180097829
0x1800972ee  mov     r13d, r12d
0x1800972f1  mov     dword ptr [rbp+0C10h+var_BF0], 1
0x1800972f8  mov     dword ptr [rbp+0C10h+var_C00], r12d
0x1800972fc  cmp     [rbp+0C10h+var_930], r12d
0x180097303  jle     loc_180097829
0x180097309  vmovups ymm15, [rbp+0C10h+var_BE0]
0x18009730e  mov     edi, [rbp+0C10h+var_31C]
0x180097314  mov     r14d, [rbp+0C10h+var_900]
0x18009731b  mov     esi, [rbp+0C10h+var_92C]
0x180097321  inc     r14d
0x180097324  mov     [rbp+0C10h+var_900], r14d
0x18009732b  cmp     r14d, 1
0x18009732f  jnz     loc_18009780B
0x180097335  mov     ecx, [r15+28h]
0x180097339  mov     r11d, r12d
0x18009733c  mov     r10d, [r15+1Ch]
0x180097340  mov     eax, [rbp+0C10h+var_8FC]
0x180097346  test    eax, eax
0x180097348  movsxd  r8, dword ptr [r15+34h]
0x18009734c  cmovle  r11d, eax
0x180097350  mov     eax, [r15+2Ch]
0x180097354  cmp     r10d, eax
0x180097357  vmovups [rbp+0C10h+var_BE0], ymm15
0x18009735c  mov     r12, qword ptr [rbp+0C10h+var_BE0+8]
0x180097360  lea     r9d, [r8-1]
0x180097364  cmovl   r10d, eax
0x180097368  sub     r10d, eax
0x18009736b  mov     eax, [rbp+0C10h+var_8F8]
0x180097371  cmp     eax, ecx
0x180097373  cmovl   eax, ecx
0x180097376  sub     eax, ecx
0x180097378  cdq
0x180097379  idiv    dword ptr [r15+30h]
0x18009737d  movsxd  rcx, edx
0x180097380  imul    rcx, r8
0x180097384  cmp     r10d, r9d
0x180097387  cmovle  r9d, r10d
0x18009738b  add     r12, r13
0x18009738e  movsxd  rax, r9d
0x180097391  lea     r10, [rbx+r13]
0x180097395  movsxd  r9, [rbp+0C10h+var_304]
0x18009739c  add     rcx, rax
0x18009739f  mov     rax, [r15+38h]
0x1800973a3  neg     r11d
0x1800973a6  mov     r15, qword ptr [rbp+0C10h+var_BE0+10h]
0x1800973aa  add     r15, r13
0x1800973ad  lea     r8, [rax+rcx*2]
0x1800973b1  cmp     r9, 1
0x1800973b5  jge     short loc_18009740C
0x1800973b7  cmp     r11d, esi
0x1800973ba  jge     short loc_1800973F9
0x1800973bc  lea     eax, ds:0[r11*4]
0x1800973c4  movsxd  rcx, eax
0x1800973c7  movzx   eax, byte ptr [r12+rcx]
0x1800973cc  movzx   edx, byte ptr [r15+rcx]
0x1800973d1  add     edx, eax
0x1800973d3  movzx   eax, byte ptr [rcx+r10]
0x1800973d8  add     edx, eax
0x1800973da  imul    eax, edx, 55h ; 'U'
0x1800973dd  shr     eax, 6
0x1800973e0  mov     [r8], ax
0x1800973e4  add     r8, 2
0x1800973e8  mov     eax, dword ptr [rbp+r9*4+0C10h+var_BF0]
0x1800973ed  inc     r9
0x1800973f0  add     r11d, eax
0x1800973f3  cmp     r9, 1
0x1800973f7  jl      short loc_1800973B7
0x1800973f9  mov     edi, [rbp+0C10h+var_31C]
0x1800973ff  mov     r14d, [rbp+0C10h+var_900]
0x180097406  mov     esi, [rbp+0C10h+var_92C]
0x18009740c  lea     ecx, [rsi-3Fh]
0x18009740f  cmp     r11d, ecx
0x180097412  jge     loc_180097779
0x180097418  vmovdqu ymm14, cs:__ymm@0055005500550055005500550055005500550055005500550055005500550055
0x180097420  sub     ecx, r11d
0x180097423  movsxd  r9, r11d
0x180097426  add     r9, 14h
0x18009742a  mov     rsi, r10
0x18009742d  sub     rsi, rbx
0x180097430  sub     rsi, r13
0x180097433  lea     eax, [rcx-1]
0x180097436  shr     eax, 6
0x180097439  lea     r9, [rbx+r9*4]
0x18009743d  inc     eax
0x18009743f  add     r9, r13
0x180097442  mov     edi, eax
0x180097444  shl     eax, 6
0x180097447  add     r11d, eax
0x18009744a  nop     word ptr [rax+rax+00h]
0x180097450  vmovups xmm0, xmmword ptr [rsi+r9-50h]
0x180097457  vinsertf128 ymm7, ymm0, xmmword ptr [r9-10h], 1
0x18009745e  vmovups xmm1, xmmword ptr [r9-40h]
0x180097464  vinsertf128 ymm9, ymm1, xmmword ptr [r9], 1
0x18009746a  vmovups xmm0, xmmword ptr [r9-30h]
0x180097470  vinsertf128 ymm11, ymm0, xmmword ptr [r9+10h], 1
0x180097477  vmovups xmm1, xmmword ptr [r9-20h]
0x18009747d  vinsertf128 ymm13, ymm1, xmmword ptr [r9+20h], 1
0x180097484  vmovups xmm0, xmmword ptr [r9+30h]
0x18009748a  vinsertf128 ymm2, ymm0, xmmword ptr [r9+70h], 1
0x180097491  vmovups xmm1, xmmword ptr [r9+40h]
0x180097497  vinsertf128 ymm3, ymm1, xmmword ptr [r9+80h], 1
0x1800974a1  vmovups xmm0, xmmword ptr [r9+50h]
0x1800974a7  vinsertf128 ymm4, ymm0, xmmword ptr [r9+90h], 1
0x1800974b1  vmovups xmm1, xmmword ptr [r9+60h]
0x1800974b7  vinsertf128 ymm5, ymm1, xmmword ptr [r9+0A0h], 1
0x1800974c1  vpunpckhbw ymm8, ymm7, ymm2
0x1800974c5  vpunpcklbw ymm6, ymm7, ymm2
0x1800974c9  vpunpcklbw ymm10, ymm9, ymm3
0x1800974cd  vpunpcklbw ymm0, ymm11, ymm4
0x1800974d1  vpunpcklbw ymm7, ymm6, ymm0
0x1800974d5  vpunpcklbw ymm2, ymm13, ymm5
0x1800974d9  vpunpckhbw ymm12, ymm9, ymm3
0x1800974dd  vpunpckhbw ymm9, ymm6, ymm0
0x1800974e1  vpunpcklbw ymm0, ymm10, ymm2
0x1800974e5  vpunpcklbw ymm6, ymm7, ymm0
0x1800974e9  vpunpckhbw ymm1, ymm11, ymm4
0x1800974ed  vpunpcklbw ymm11, ymm8, ymm1
0x1800974f1  vpunpckhbw ymm4, ymm13, ymm5
0x1800974f5  vpunpckhbw ymm13, ymm8, ymm1
0x1800974f9  vpunpckhbw ymm8, ymm7, ymm0
0x1800974fd  vpunpckhbw ymm1, ymm10, ymm2
0x180097501  vpunpcklbw ymm10, ymm9, ymm1
0x180097505  vpunpcklbw ymm3, ymm12, ymm4
0x180097509  vpunpckhbw ymm5, ymm12, ymm4
0x18009750d  vpunpckhbw ymm12, ymm9, ymm1
0x180097511  vpunpckhbw ymm1, ymm11, ymm3
0x180097515  vpunpcklbw ymm9, ymm8, ymm1
0x180097519  vpunpckhbw ymm8, ymm8, ymm1
0x18009751d  vpunpcklbw ymm0, ymm11, ymm3
0x180097521  vpunpcklbw ymm7, ymm6, ymm0
0x180097525  vpunpckhbw ymm6, ymm6, ymm0
0x180097529  vpunpcklbw ymm2, ymm13, ymm5
0x18009752d  vpunpcklbw ymm1, ymm10, ymm2
0x180097531  vpunpcklbw ymm0, ymm7, ymm1
0x180097535  vpunpckhbw ymm1, ymm7, ymm1
0x180097539  vmovdqu [rbp+0C10h+var_B30], ymm1
0x180097541  vmovdqu [rbp+0C10h+var_BB0], ymm0
0x180097546  vpunpckhbw ymm2, ymm10, ymm2
0x18009754a  vpunpckhbw ymm4, ymm13, ymm5
0x18009754e  vpunpckhbw ymm1, ymm6, ymm2
0x180097552  vpunpcklbw ymm0, ymm6, ymm2
0x180097556  vpunpcklbw ymm3, ymm12, ymm4
0x18009755a  vmovdqu [rbp+0C10h+var_B10], ymm1
0x180097562  vmovdqu [rbp+0C10h+var_B90], ymm0
0x18009756a  vpunpckhbw ymm1, ymm9, ymm3
0x18009756e  vpunpcklbw ymm0, ymm9, ymm3
0x180097572  vpunpckhbw ymm5, ymm12, ymm4
0x180097576  vmovdqu [rbp+0C10h+var_AF0], ymm1
0x18009757e  vmovdqu [rbp+0C10h+var_B70], ymm0
0x180097586  vpunpckhbw ymm1, ymm8, ymm5
0x18009758a  vpunpcklbw ymm0, ymm8, ymm5
0x18009758e  vmovdqu [rbp+0C10h+var_AD0], ymm1
0x180097596  vmovdqu [rbp+0C10h+var_B50], ymm0
0x18009759e  lea     rcx, [rbp+0C10h+var_B90]
0x1800975a5  mov     edx, 2
0x1800975aa  lea     rax, [rbp+0C10h+var_2D0]
0x1800975b1  nop     dword ptr [rax+00h]
0x1800975b5  nop     word ptr [rax+rax+00000000h]
0x1800975c0  lea     rax, [rax+100h]
0x1800975c7  vmovdqu ymm3, ymmword ptr [rcx]
0x1800975cb  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x1800975d0  lea     rcx, [rcx+80h]
0x1800975d7  vpmovzxbw ymm0, xmm1
0x1800975dc  vextracti128 xmm1, ymm1, 1
0x1800975e2  vpmovzxbw ymm2, xmm1
0x1800975e7  vmovdqu ymmword ptr [rax-120h], ymm0
0x1800975ef  vextracti128 xmm1, ymm3, 1
0x1800975f5  vpmovzxbw ymm0, xmm3
0x1800975fa  vmovdqu ymm3, ymmword ptr [rcx-60h]
0x1800975ff  vmovdqu ymmword ptr [rax-0A0h], ymm2
0x180097607  vpmovzxbw ymm2, xmm1
0x18009760c  vmovdqu ymmword ptr [rax-100h], ymm0
0x180097614  vpmovzxbw ymm0, xmm3
0x180097619  vextracti128 xmm1, ymm3, 1
0x18009761f  vmovdqu ymm3, ymmword ptr [rcx-40h]
0x180097624  vmovdqu ymmword ptr [rax-80h], ymm2
0x180097629  vpmovzxbw ymm2, xmm1
0x18009762e  vmovdqu ymmword ptr [rax-60h], ymm2
0x180097633  vmovdqu ymmword ptr [rax-0E0h], ymm0
0x18009763b  vextracti128 xmm1, ymm3, 1
0x180097641  vpmovzxbw ymm2, xmm1
0x180097646  vpmovzxbw ymm0, xmm3
0x18009764b  vmovdqu ymmword ptr [rax-40h], ymm2
0x180097650  vmovdqu ymmword ptr [rax-0C0h], ymm0
0x180097658  sub     rdx, 1
0x18009765c  jnz     loc_1800975C0
0x180097662  lea     rax, [rbp+0C10h+var_A70]
0x180097669  mov     edx, 4
0x18009766e  lea     rcx, [rbp+0C10h+var_2B0]
0x180097675  nop     word ptr [rax+rax+00000000h]
0x180097680  lea     rax, [rax+60h]
0x180097684  vmovdqu ymm0, ymmword ptr [rcx-40h]
0x180097689  vmovdqu ymm1, ymmword ptr [rcx-20h]
0x18009768e  lea     rcx, [rcx+80h]
0x180097695  vmovdqu ymmword ptr [rax-0A0h], ymm0
0x18009769d  vmovdqu ymm0, ymmword ptr [rcx-80h]
0x1800976a2  vmovdqu ymmword ptr [rax-60h], ymm0
0x1800976a7  vmovdqu ymmword ptr [rax-80h], ymm1
0x1800976ac  sub     rdx, 1
0x1800976b0  jnz     short loc_180097680
0x1800976b2  vmovdqu ymm0, [rbp+0C10h+var_A90]
0x1800976ba  vpaddw  ymm1, ymm0, [rbp+0C10h+var_AB0]
0x1800976c2  vpaddw  ymm2, ymm1, [rbp+0C10h+var_A70]
0x1800976ca  vmovdqu ymm0, [rbp+0C10h+var_A30]
0x1800976d2  vpaddw  ymm1, ymm0, [rbp+0C10h+var_A50]
0x1800976da  vmovdqu ymm0, [rbp+0C10h+var_9D0]
0x1800976e2  vpmullw ymm3, ymm2, ymm14
0x1800976e7  vpaddw  ymm2, ymm1, [rbp+0C10h+var_A10]
0x1800976ef  vpaddw  ymm1, ymm0, [rbp+0C10h+var_9F0]
0x1800976f7  vmovdqu ymm0, [rbp+0C10h+var_970]
0x1800976ff  vpsrlw  ymm6, ymm3, 6
0x180097704  vpmullw ymm3, ymm2, ymm14
0x180097709  vpaddw  ymm2, ymm1, [rbp+0C10h+var_9B0]
0x180097711  vpaddw  ymm1, ymm0, [rbp+0C10h+var_990]
0x180097719  vmovdqu ymmword ptr [r8], ymm6
0x18009771e  vpsrlw  ymm5, ymm3, 6
0x180097723  vpmullw ymm3, ymm2, ymm14
0x180097728  vpaddw  ymm2, ymm1, [rbp+0C10h+var_950]
0x180097730  vmovdqu ymmword ptr [r8+20h], ymm5
0x180097736  vpsrlw  ymm4, ymm3, 6
0x18009773b  vmovdqu ymmword ptr [r8+40h], ymm4
0x180097741  vpmullw ymm3, ymm2, ymm14
0x180097746  vpsrlw  ymm0, ymm3, 6
0x18009774b  vmovdqu ymmword ptr [r8+60h], ymm0
0x180097751  sub     r8, 0FFFFFFFFFFFFFF80h
0x180097755  add     r9, 100h
0x18009775c  sub     rdi, 1
0x180097760  jnz     loc_180097450
0x180097766  mov     edi, [rbp+0C10h+var_31C]
0x18009776c  mov     r14d, [rbp+0C10h+var_900]
0x180097773  mov     esi, [rbp+0C10h+var_92C]
0x180097779  cmp     r11d, esi
0x18009777c  jge     short loc_1800977DE
0x18009777e  lea     eax, ds:0[r11*4]
0x180097786  sub     r15, r12
  ... truncated ...
```
